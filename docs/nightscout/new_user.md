

# New Nightscout Users

</br>

Nightscout is DIY, if you don’t feel confident you’ll have necessary skills, give it a try, you’ll find open heart people ready to help you building it in many Facebook groups. For free. Paying it forward.

If you want to [sell installations](https://github.com/nightscout/nightscout.github.io/wiki/Can-I-sell-Nightscout), keep in mind you will be legally liable and can easily be sued by your buyers should anything bad happen to them because of Nightscout. Nightscout is not approved by FDA, CE, ... this is the reason why it's DIY.

</br>

#### Here is a step-by-step guide for completing your own Nightscout site DIY style.

</br>

Create your Heroku, GitHub and Atlas accounts from a computer.

Do not change device/computer/browser during the creation process!

!!! note
    If you have unexpected issues whilst creating your site restart with another browser.

!!! warning "If this is not your first attempt to deploy Nightscout"
    You might want to do some [cleanup](../../troubleshoot/cleanup/) before.

</br></br>


## Step 1: Create a GitHub account

</br>

!!! warning "If you already have a GitHub account and previously forked cgm-remote-monitor"
    Make sure you delete your current cgm-remote-monitor fork using [Step 1 of this guide (ONLY STEP1!)](../../update/redeploy/#step-1-cleanup-github).

</br>

- Click this link to create a GitHub account: [https://github.com/](https://github.com/)
- Enter a username (anything you want and that is accepted, not very important), email, and password.
- Then click `Sign up for GitHub`

<img src="..\img\NewNS00.png" style="zoom:80%;" />

</br>

- Play and solve the puzzle then click `Join a free plan`.

<img src="..\img\NewNS01.png" style="zoom:80%;" />

</br>

- Select whatever choices (not important) then click `Complete setup`.



<img src="..\img\NewNS02.png" style="zoom:80%;" />

</br>

- GitHub will send you a verification email, open your mailbox and check for it (look into spam also).

<img src="..\img\NewNS03.png" style="zoom:80%;" />

</br>

- On the received email, click `Verify email address`.

<img src="..\img\NewNS04.png" style="zoom:80%;" />

</br>



- A new page will open in your browser, click `Skip this for now`.

<img src="..\img\NewNS05.png" style="zoom:80%;" />

</br>

- Leave the page open as it is.

<img src="..\img\NewNS06.png" style="zoom:80%;" />

</br></br>

## Step 2: Create a Heroku account

</br>

- Click this link to create an Heroku account: [https://signup.heroku.com/login](https://signup.heroku.com/login)

- Enter mandatory data (*) and click `CREATE FREE ACCOUNT`

<img src="..\img\NewNS07.png" style="zoom:80%;" />

</br>

- Heroku will send a confirmation email, open your mailbox and look for it (also check spam folder).

<img src="..\img\NewNS09.png" style="zoom:70%;" />

</br>

- Click on the activation link

<img src="..\img\NewNS10.png" style="zoom:80%;" />

</br>

- Create a password an write it down. Click `SET PASSWORD AND LOG IN`

<img src="..\img\NewNS11.png" style="zoom:80%;" />

</br>

- Click `CLICK HERE TO PROCEED`

<img src="..\img\NewNS12.png" style="zoom:70%;" />

</br>

- Your Heroku page will open, click on your profile picture top right and select `Account Settings`

<img src="..\img\NewNS13.png" style="zoom:80%;" />

</br>

- Click on `Billing`

<img src="..\img\NewNS14.png" style="zoom:80%;" />

</br>

- Click `Add credit card`

<img src="..\img\NewNS15.png" style="zoom:80%;" />

</br>

- Enter a valid credit card information and click `Save Details`

!!! note "Note"
    Unless you voluntarily select billable features, your credit card information is only used for verifications and you will not be charged anything. Worst case you’ll be charged $0.00</br>

<img src="..\img\NewNS16.png" style="zoom:80%;" />

</br>

- You should now have 2 pages open: Heroku and GitHub. Leave them open.</br></br>

## Step 3: Create an Atlas account

</br>

- Open another tab at: [https://www.mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas) and click `Start Free`



<img src="..\img\NewNS17.png" style="zoom:70%;" />

</br>

- Enter information then click `Get Started Free`

<img src="..\img\NewNS18.png" style="zoom:80%;" />

</br>

- Select `Create a cluster in Shared Clusters (FREE)`

<img src="..\img\NewNS19.png" style="zoom:80%;" />

</br>

- Leave all default values and click `Create Cluster`

<img src="..\img\NewNS20.png" style="zoom:80%;" />

</br>

Atlas will create your default cluster, wait until completion… (can take more than 3 minutes)

<img src="..\img\NewNS21.png" style="zoom:80%;" />

</br>

- Click on `CONNECT`

<img src="..\img\NewNS22.png" style="zoom:100%;" />

</br>

- Click on `Allow Access from Anywhere`

!!!warning "If you don't allow access from anywhere (IP 0.0.0.0/0) Nightscout will not be able to access your database."

<img src="..\img\NewNS23.png" style="zoom:80%;" />

</br>

- Click on `Add IP Address`

<img src="..\img\NewNS24.png" style="zoom:80%;" />

</br>

- Add a database username (for example `nightscout`) and a database password (in the example below `soo5ecret`).

!!! warning "Database credentials"
    Do not use your Atlas account credentials. Do not use special characters: only letters and numbers.

!!! warning "Write down these credentials in the boxes below: you’ll need them later."

Database password: <input type="text" id="myPwd" value="soo5ecret" size="20">

Database username: <input type="text" id="mydB" value="mycgmic" size="20">

</br>

- Then click `Create Database User`.

<img src="..\img\NewNS25.png" style="zoom:80%;" />

</br>

- Click on `Choose a connection method`

<img src="..\img\NewNS26.png" style="zoom:80%;" />

</br>

- Select `Connect your application`

<img src="..\img\NewNS27.png" style="zoom:80%;" />

</br>

- Copy the connection string: click `Copy` and paste it somewhere to edit it (like Notepad).

<img src="..\img\NewNS28.png" style="zoom:100%;" />

</br>

- Paste the string in the box below.

<input type="text" id="myAtlas" value="" size="100">

!!!info "It should be similar to this (`xxxxx` will be different):"
    `mongodb+srv://nightscout:<password>@cluster0.xxxxx.mongodb.net/<dbname>?retryWrites=true&w=majority`
</br>

- Click the `Generate` button:

<button onclick="Generate()">Generate</button>

<p style="font-size:25px" id="result">The connection string will appear here</p>

<script>
var bAtlas;
var sdB, sPwd;
var sFinalString = "Not defined yet";

function Generate()
{
  var sString = sFinalString;

  bAtlas=0;
  var sString = "Looks good!";
  var sAtlas = document.getElementById("myAtlas").value;
  sPwd = document.getElementById("myPwd").value;
  sdB = document.getElementById("mydB").value;
  var iAS = sAtlas.search("://");
  if(iAS!=11) { sString = "Atlas URI should start with mongodb+srv://"; }
  else
  {
    var iAP = sAtlas.search("<password>");
    if(iAP==-1) { sString = "Atlas URI should contain &lt;password&gt;"; }
    else
    {
      var iAD = sAtlas.search("<dbname>");
      if(iAD==-1) { sString = "Atlas URI should contain &lt;dbname&gt;"; }
      else
      {
      	bAtlas=1;
        sString = sAtlas.substring(0,iAP);
        sFinalString = sString.concat(sPwd, sAtlas.substring(iAP+10, iAD));
        sString = sAtlas.substring(iAP+10, iAD);
        sFinalString = sFinalString.concat(sdB, sAtlas.substring(iAD+8));
      }
    }
  }

  if(bAtlas) document.getElementById("result").innerHTML = sFinalString;
  else document.getElementById("result").innerHTML = sString;
}
</script>

</br>

!!!warning
    Keep this string safely aside, it is called your `MONGODB_URI`

</br>

**If you didn't manage to get the string with the automated script:** (else proceed to [Step 4](./#step-4-fork-and-deploy-cgm-remote-monitor))

!!!info "Helper page"
    Open [this helper page](./stringhelp.html) in another tab and insert the original connection string and both your database password and the name you decided for your database name (not important), then click `Generate` to get the final string (leave the page open).

- If you want to do it manually: replace `<password>` with your database password as noted previously (in the example below `soo5ecret`) and `<dbname>` by any text you want, say `mycgmic` for example. The result will be like this:

`mongodb+srv://nightscout:soo5ecret@cluster0.xxxxx.mongodb.net/mycgmic?retryWrites=true&w=majority`

!!! note
    There are no < and > characters in the final string, neither for password nor for database name.

</br></br>



## Step 4: Fork and deploy cgm-remote-monitor

</br>

!!! warning "If you previously forked cgm-remote-monitor before reaching this step, you should delete the existing cgm-remote-monitor repository before proceeding"
    Delete your current cgm-remote-monitor fork using [Step 1 of this guide (ONLY STEP1!)](../../update/redeploy/#step-1-cleanup-github). </br>

- You should now have three pages opened in your browser: Heroku, Atlas and Github, make sur each one is logged in
   (i.e. not asking you to login) before you continue.

- Click this link [https://github.com/nightscout/cgm-remote-monitor](https://github.com/nightscout/cgm-remote-monitor), a new GitHub page will open. Click on `Fork`

  

  <img src="..\img\NewNS29.png" style="zoom:80%;" />

  </br>

- Wait a moment

<img src="..\img\NewNS30.png" style="zoom:80%;" />

</br>

- Scroll down and click `Deploy to Heroku`

<img src="..\img\NewNS31.png" style="zoom:80%;" />

<img src="..\img\NewNS32.png" style="zoom:80%;" />

</br>

!!! note "You're getting into the core setup of your site"
    Below you'll see the minimum required configuration, you can modify the variables later in Heroku. A more complete list here: [Setup](..\setup_variables)

</br>

- Enter your CGM in the Cloud site name: invent a name you will use to see your BG in the cloud. Check the name is available.

- Don’t change the region.

<img src="..\img\NewNS33.png" style="zoom:80%;" />

</br>

Scroll down and setup the following variables:

 </br>

- `API_SECRET` will be your Nightscout site password, it needs to be at least 12 characters long and should **NOT use spaces and @ or ! symbols**: it is recommended to use only letters and numbers.

<img src="..\img\NewNS34.png" style="zoom:80%;" />

</br>

- If you want to link your Dexcom Share account as a data source, compile the following lines:

<img src="..\img\NewNS35.png" style="zoom:80%;" />

</br>

!!!info "MOST COMMON ERRORS"
    The `BRIDGE_PASSWORD` and `BRIDGE_USER_NAME` are NOT visible from within your Dexcom app or online account. The values for them are what you entered into your Dexcom mobile app when you VERY FIRST logged into that app however long ago. The `BRIDGE_USER_NAME` is not an email address. The most common error on initial Nightscout setups is that people incorrectly use an old account or an old password. To test your username and password, go to Dexcom's Clarity page (check [here for USA accounts](https://clarity.dexcom.com) and [here for the others](https://clarity.dexcom.eu)) and try logging into your Dexcom account. If your account info doesn't let you in, or you don't see data in your Clarity account...then you need to figure out your actual credentials before moving ahead.

!!! note "Password"
    *Some people have had problems with their bridge connecting when their Dexcom passwords are entirely numeric. If you have connection issues in that case, try changing your password to something with a mix of numbers and letters.*

!!! info
    You need to have at least one follower to use Dexcom Share. See [here](../../uploader/setup/#dexcom).

</br>

- If you want to link your CareLink account as a data source, compile the following lines:

<img src="..\img\NewNS36.png" style="zoom:80%;" />

</br>

- Select the units you’re using in `DISPLAY_UNITS` acceptable choices are `mg/dl` or `mmol/L` (or just `mmol`).

<img src="..\img\NewNS37.png" style="zoom:80%;" />

</br>

- In `ENABLE` copy and paste the following words (separated by a space) so that won't have to think about which you want now:

`careportal basal dbsize rawbg iob maker bridge cob bwp cage iage sage boluscalc pushover treatmentnotify mmconnect loop pump profile food openaps bage alexa override`

<img src="..\img\NewNS38.png" style="zoom:80%;" />

!!! note "More on `ENABLE` words"
    If you want to know more about them, look here: [Setup](..\setup_variables)

</br>

- Now you need that connection string you defined during the Atlas cluster creation (as the example below, but not the string below). Copy and paste it in the `MONGODB_URI` variable field.

`mongodb+srv://nightscout:soo5ecret@cluster0.xxxxx.mongodb.net/mycgmic?retryWrites=true&w=majority`

!!! note
    This is the string generated in the helper page if you decided to use it.

<img src="..\img\NewNS39.png" style="zoom:80%;" />

</br>

- Browse down to the end of the list and click `Deploy app`

<img src="..\img\NewNS40.png" style="zoom:80%;" />

</br>

- **WAIT** until completion (will take some time). Do not interfere with the process until it's complete.

<img src="..\img\NewNS41.png" style="zoom:80%;" />

</br>

- Then click `View` (if nothing happens click `Manage App` then upper right `Open App`)

<img src="..\img\NewNS42.png" style="zoom:80%;" />

</br>

- Your Nightscout site should open, click on the hamburger menu top right and select `Profile Editor`.

<img src="..\img\NewNS43.png" style="zoom:80%;" />

</br>

- Setup your `Time zone` and eventually all other fields. Do not leave empty fields. If you don't know which value you should use, just leave default. You can change them later.

<img src="..\img\NewNS44.png" style="zoom:80%;" />

</br>

- Browse down to `Authentication status` and click `Authenticate`. Enter your API secret. Click `Update`.

<img src="..\img\NewNS45.png" style="zoom:80%;" />

</br>

- Click `Save`.

<img src="..\img\NewNS46.png" style="zoom:80%;" />

</br>

- If the following pop-up shows up click `OK`, and check status (upper right of the window).

<img src="..\img\NewNS47.png" style="zoom:80%;" />

</br>

- Dexcom Share and CareLink users should see data flowing in after some minutes, other uploaders like xDrip+, Spike, xDrip4iOS, etc will need to be setup with the Nightscout address and API secret in the app.

<img src="..\img\NewNS48.png" style="zoom:80%;" />

</br>

- Finally, you might want to modify the `PAPERTRAIL_API_TOKEN` line. Heroku offers a free, tiny amount of Papertrail service (like a logging service for how the site is running), but really generates more confusion to most people later when they get a message that their "Free Papertrail Service has run out of room". Papertrail is not needed, edit the line and add `DISABLED` at the end, so that you can recover the function should you need it.

<img src="..\img\NewNS49.png" style="zoom:80%;" />

</br></br>



## Step 5: Uploader setup

</br>

[Configure your uploader](..\..\uploader\setup.md).



