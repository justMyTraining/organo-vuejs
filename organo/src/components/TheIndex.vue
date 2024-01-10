<template>
  <section>
    <TheHeader />

    <main>
      <section class="container">
        <form class="ve-form">
          <fieldset class="ve-header">
            <p class="mb-5">Preencha os dados para criar o card do colaborador</p>
          </fieldset>
          <fieldset class="ve-form-inputs mb-5">
            <FormInput ref="name" :id="'nome'" :label="'Nome'" :placeholder="'Insira o nome do colaborador'" />
            <FormInput ref="occupation" :id="'cargo'" :label="'Cargo'" :placeholder="'Informe o cargo do colaborador'" />
            <FormInput ref="avatar" :id="'imagem'" :label="'Imagem'"
              :placeholder="'Informe um avatar para o colaborador'" />
            <FormSelect ref="team" :teams="teams.map(team => team.team)" />
          </fieldset>
          <fieldset>
            <FormButton @click.prevent="createCard()" />
          </fieldset>
        </form>
      </section>
      <section class="ve-title-section container d-flex justify-content-between align-items-center">
        <img class="opacity-0" :src="require('@/assets/images/btn.png')" alt="">
        <h2 class="m-0 pb-4">Minha Organização:</h2>
        <img :src="require('@/assets/images/btn.png')" alt="">
      </section>
      <template v-for="team in teams" :key="team.team">
        <section v-if="filterTeamCards(team.team).length">
          <BaseCardContainer :team="team">
            <template v-for="collaborator in filterTeamCards(team.team)" :key="collaborator.avatar">
              <AppCard :cardColor="team.primaryColor" :collaborator="collaborator" />
            </template>
          </BaseCardContainer>
        </section>

      </template>
    </main>

    <TheFooter />
  </section>
</template>

<script>
import AppCard from "@/components/AppCard.vue";
import BaseCardContainer from "@/components/BaseCardContainer.vue";
import FormButton from "@/components/FormButton.vue";
import FormInput from "@/components/FormInput.vue";
import FormSelect from "@/components/FormSelect.vue";
import TheFooter from "@/components/TheFooter.vue";
import TheHeader from "@/components/TheHeader.vue";

export default {
  data() {
    return {
      cards: [
        {
          name: "Iago Silva",
          occupation: "Programador",
          avatar: "https://www.github.com/iago.png",
          team: "Programação",
        },
        {
          name: "João Oliveira",
          occupation: "Programador",
          avatar: "https://www.github.com/joao.png",
          team: "Programação",
        },
        {
          name: "Maria Souza",
          occupation: "Programador",
          avatar: "https://www.github.com/maria.png",
          team: "Programação",
        },
        {
          name: "Lucas Silva",
          occupation: "Programador Front-end",
          avatar: "https://www.github.com/lusques.png",
          team: "Front-End",
        },
        {
          name: "Ana Silva",
          occupation: "Programador Front-end",
          avatar: "https://www.github.com/ana.png",
          team: "Front-End",
        },
        {
          name: "Pedro Pereira",
          occupation: "Programador Front-end",
          avatar: "https://www.github.com/pedro.png",
          team: "Front-End",
        },
        {
          name: "Larissa Oliveira",
          occupation: "Cientista de Dados",
          avatar: "https://www.github.com/larissa.png",
          team: "Data Science",
        },
        {
          name: "Mariana Lima",
          occupation: "Cientista de Dados",
          avatar: "https://www.github.com/mariana.png",
          team: "Data Science",
        },
        {
          name: "Rafael Costa",
          occupation: "Cientista de Dados",
          avatar: "https://www.github.com/rafael.png",
          team: "Data Science",
        },
        {
          name: "Gustavo Oliveira",
          occupation: "Engenheiro DevOps",
          avatar: "https://www.github.com/gustavo.png",
          team: "Devops",
        },
        {
          name: "Fernanda Santos",
          occupation: "Engenheiro DevOps",
          avatar: "https://www.github.com/fernanda.png",
          team: "Devops",
        },
        {
          name: "Lucas Mendes",
          occupation: "Engenheiro DevOps",
          avatar: "https://www.github.com/lucas.png",
          team: "Devops",
        },
        {
          name: "Gabriel Lima",
          occupation: "Designer",
          avatar: "https://www.github.com/gabriel.png",
          team: "Ux e Design",
        },
        {
          name: "Juliana Costa",
          occupation: "Designer",
          avatar: "https://www.github.com/juliana.png",
          team: "Ux e Design",
        },
        {
          name: "André Silva",
          occupation: "Designer",
          avatar: "https://www.github.com/andre.png",
          team: "Ux e Design",
        },
        {
          name: "Luciana Oliveira",
          occupation: "Programador Mobile",
          avatar: "https://www.github.com/luciana.png",
          team: "Mobile",
        },
        {
          name: "Rodrigo Santos",
          occupation: "Programador Mobile",
          avatar: "https://www.github.com/rodrigo.png",
          team: "Mobile",
        },
        {
          name: "Camila Lima",
          occupation: "Programador Mobile",
          avatar: "https://www.github.com/camila.png",
          team: "Mobile",
        },
        {
          name: "Marcelo Oliveira",
          occupation: "Gestor em Inovação",
          avatar: "https://www.github.com/marcelo.png",
          team: "Inovação e Gestão",
        },
        {
          name: "Isabela Costa",
          occupation: "Gestor em Inovação",
          avatar: "https://www.github.com/isabela.png",
          team: "Inovação e Gestão",
        },
        {
          name: "Diego Silva",
          occupation: "Gestor em Inovação",
          avatar: "https://www.github.com/diego.png",
          team: "Inovação e Gestão",
        },
      ],
      teams: [
        {
          team: "Programação",
          primaryColor: "#57C278",
          secondaryColor: "#D9F7E9"
        },
        {
          team: "Front-End",
          primaryColor: "#82CFFA",
          secondaryColor: "#E8F8FF"
        },
        {
          team: "Data Science",
          primaryColor: "#A6D157",
          secondaryColor: "#F0F8E2"
        },
        {
          team: "Develops",
          primaryColor: "#E06B69",
          secondaryColor: "#FDE7E8"
        },
        {
          team: "UX e Design",
          primaryColor: "#DB6EBF",
          secondaryColor: "#FAE9F5"
        },
        {
          team: "Mobile",
          primaryColor: "#FFBA05",
          secondaryColor: "#FFF5D9"
        },
        {
          team: "Inovação e Gestão",
          primaryColor: "#FF8A29",
          secondaryColor: "#FFEEDF"
        },
      ]
    }
  },
  components: {
    AppCard,
    BaseCardContainer,
    FormButton,
    FormInput,
    FormSelect,
    TheFooter,
    TheHeader
  },
  methods: {
    createCard() {
      const component = this.$refs;
      const name = component.name.getValue();
      const occupation = component.occupation.getValue();
      const avatar = component.avatar.getValue();
      const team = component.team.getValue();
      console.log(team);

      if (!name || !occupation || !avatar || !team) {
        alert(`Campo vazio -${!name ? ' nome' : ''}${!occupation ? ' cargo' : ''}${!avatar ? ' imagem' : ''}${!team ? ' time' : ''}.`)
        return
      }

      component.name.clearValue();
      component.occupation.clearValue();
      component.avatar.clearValue();
      component.team.clearValue();

      this.cards.push({ name, occupation, avatar, team });

    },
    filterTeamCards(team) {
      return this.cards.filter(collaborator => collaborator.team == team);
    }
  },
  watch: {
    cards() {
      alert("ok");
    }
  }
}
</script>

<style>
.ve-header p {
  color: #212121;
  font-family: Prata;
  font-size: 32px;
  font-weight: 400;
}

.ve-form {
  background-color: #f6f6f6;
  border-radius: 20px;
  padding: 35px 95px;
}

.ve-form-inputs {
  display: flex;
  flex-direction: column;
  row-gap: 30px;
}

.ve-title-section {
  color: #6278F7;
  font-family: Prata, sans-serif;
  font-size: 40px;
  font-style: normal;
  font-weight: 400;
  line-height: 72px;
  margin: 75px auto 80px;
}

.ve-title-section>h2 {
  position: relative;
}

.ve-title-section>h2::after {
  background-color: #6278F7;
  bottom: 0;
  content: '';
  display: block;
  height: 4px;
  left: 50%;
  position: absolute;
  transform: translateX(-50%);
  width: 64px;
}
</style>