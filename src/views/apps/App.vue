<template>
  <b-row>
    <b-col cols="12" lg="6">
      <b-card no-header>
        <template slot="header">User id: {{ $route.params.id }}</template>
        <b-table
          striped
          small
          fixed
          responsive="sm"
          :items="items($route.params.id)"
          :fields="fields"
        >
          <template slot="value" slot-scope="data">
            <strong>{{data.item.value}}</strong>
          </template>
        </b-table>
        <template slot="footer">
          <b-button @click="goBack">Back</b-button>
        </template>
      </b-card>
    </b-col>
  </b-row>
</template>

<script>
import appsData from "./AppsData";
export default {
  name: "App",
  props: {
    caption: {
      type: String,
      default: "App id"
    }
  },
  data: () => {
    return {
      items: id => {
        const app = appsData.find(app => app.id.toString() === id);
        const appDetails = app ? Object.entries(app) : [["id", "Not found"]];
        return appDetails.map(([key, value]) => {
          return { key: key, value: value };
        });
      },
      fields: [{ key: "key" }, { key: "value" }]
    };
  },
  methods: {
    goBack() {
      this.$router.go(-1);
      // this.$router.replace({path: '/users'})
    }
  }
};
</script>
