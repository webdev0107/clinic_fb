<template>
  <div class="tab-content">
    <p class="description">Choose how you want to receive notifications and the frequency. Notifications will include a link to login to this dashboard, but will not contain dashboard data.</p>
    <form action="" method="POST">
      <div class="form-container">
        <div class="container-left">
          <div class="receive-email-container">
            <icon-switch :switchData="switchEmail" />
            <p class="text-sendtoemail">Emails will be sent to</p>
            <a href="">Change Email</a><br/>
          </div>
          <div class="receive-sms-container">
            <icon-switch :switchData="switchSMS"/>
          </div>
          <div class="phone-number-container">
            <PhoneInput />
          </div>
          <p>Only For SMS Notification</p>
        </div>
        <div class="container-right">
          <label for="checkbox">Choose the frequency of your notifications</label>
          <div class="noti-group">
            <div class="input-checkbox field-br">
              <input type="checkbox" id="daily_check" checked/>
              <label for="daily_check">Daily remider notifications with link to dashboard</label>
            </div>
            <div class="input-checkbox field-br" id="weekly_check">
              <input type="checkbox" checked/>
              <label for="weekly_check">Weekly reminder notification with link to dashboard</label>
            </div>
            <div class="input-checkbox field-br" id="monthly_check">
              <input type="checkbox" checked/>
              <label for="monthly_check">Monthly reminder notification with link to dashboard</label>
            </div>
          </div>
        </div>
      </div>
      <input class="button-submit" type="submit" value="Save & Continue" />
    </form>
  </div>
</template>
<script>
import PhoneInput from '../../components/PhoneInput.vue'
import IconSwitch from '../../components/IconSwitch.vue'
export default {
  name: 'TestingNotifications',
  components: { IconSwitch, PhoneInput },
  data () {
    return {
      switchEmail: {
        label: 'Receive email notifications',
        icon: 'icon-email.svg',
        type: 'email-noti'
      },
      switchSMS: {
        label: 'Receive SMS notifications',
        icon: 'icon-comment.svg',
        type: 'email-noti'
      }
    }
  }
}
</script>

<style>
  .tab-content{
    padding:20px;
    margin:0px 10px;
  }
  .description {
    width: 50%;
    padding-right: 20px;
  }
  .form-container{
    margin:20px 0px;
    display:flex;
  }
  .receive-email-container{
    margin:0px 0px;
  }
  .receive-sms-container{
    margin:25px 0px;
  }
  .phone-number-container{
    margin:15px 0px;
  }
  .form-container a {
    text-decoration:none;
    font-size:12px;
    margin-top:15px;
  }
  .form-container p{
    font-size:12px;
    color:gray;
    position: relative;
  }

  .container-left{
    flex:1;
  }
  .container-right{
    flex:1;
  }
  .input-checkbox{
    white-space:nowrap;
    margin:25px 0px;
  }
  .input-checkbox input{
    background:blue;
    width:20px;
    height:20px;
    vertical-align: middle;
    position: relative;
    bottom: 1px;
  }
  .input-checkbox label{
    padding-left:15px;
  }
  .button-submit{
    margin-top: 35px;
    padding:10px 20px;
    background-color:blue;
    color:white;
    border-radius:5px;
    border-color:blue;
  }
</style>
