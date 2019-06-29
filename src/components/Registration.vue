<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="columns is-centered">
                    <div class="column is-half">
                        <div class="field">
                            <div class="control">
                                <input
                                        id="fullname"
                                        class="input is-primary"
                                        type="text"
                                        placeholder="Fullname"
                                        v-model="userData.fullname">
                            </div>
                        </div>
                        <div class="field">
                            <div class="control">
                                <input
                                        id="mail"
                                        class="input is-primary"
                                        type="text"
                                        placeholder="Mail"
                                        v-model="userData.mail">
                            </div>
                        </div>
                        <div class="field">
                            <div class="control">
                                <input
                                        id="password"
                                        class="input is-primary"
                                        type="password"
                                        placeholder="Password"/>
                            </div>
                        </div>
                        <app-switch></app-switch>
                        <div class="column">
                            <div class="field is-grouped">
                                <div class="control">
                                    <button class="button is-link">Submit</button>
                                </div>
                                <div class="control">
                                    <button class="button is-text">Cancel</button>
                                </div>
                            </div>
                        </div>
                        <div class="column">
                            <div class="field is-grouped">
                                <div class="control">
                                    <label for="sendmail">
                                    <input
                                            id="sendMail"
                                            type="checkbox"
                                            v-model="sendMail">Send Email
                                    </label>
                                </div>
                                <div class="control">
                                    <label for="share">
                                    <input
                                            id="share"
                                            type="checkbox"
                                            v-model="sendMail">Share
                                    </label>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </form>
        <hr>
        <div class="row">
            <div>
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.fullname }}</p>
                        <p>Mail: {{ userData.mail }}</p>
                        <p>Password:</p>
                        <p>Send in mail?</p>
                        <ul>
                            <li v-for="item in sendMail">{{ item }}</li>
                        </ul>
                        <p>Store in Database?: </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Switch from './Switch.vue'
export default {
  data () {
    return {
      userData: { // as an Object
        mail: '',
        fullname: ''
      },
      sendMail: []
    }
  },
  components: {
    appSwitch: Switch
  }
}
</script>

<style>
.container{
    text-align: left;
}
</style>
