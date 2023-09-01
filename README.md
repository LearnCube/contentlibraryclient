# LearnCube Content Library Client

### [Overview](README.md)
  * [Quickstart](README.md#quickstart)


### Overview
The LearnCube Content Library is a cloud-based document store to organise and integrate your teaching materials with the Learncube Virtual Classroom. 

<img src="/public/library.png" />


<br/>

### Quickstart Guide 

LearnCube's Content Library Client is a simple to use drop-in widget that allows you to embed a fully equipped virtual classroom in any web page or LMS.

LearnCube's Content Library is only available to LearnCube customers with API access enabled. Getting started is simple. 

- Log in to your [LearnCube Account](https://app.learncube.com/), or [Sign up here for free](https://app.learncube.com/app/create/).
- Get your public and private [API keys here](https://app.learncube.com/app/dashboard/#api) from your LearnCube API Dashboard. (Leave the account mode to testing in order to follow this example)
- Clone the quickstart app to your local machine and cd into the directory

  ```shell 
  git clone https://github.com/LearnCube/libraryclient.git
  cd libraryclient
  ```

- Create a configuration file for your application.
  
  ```shell
  cp template.env .env
  ```
  
- Replace the variables in the newly created `.env` file with real data from your LearnCube API account. 

  ```
  # Private Key
  privateKey={privatekeyfromyouraccount}

  # LearnCube user username
  username={usernamefromyouraccount}

  # LearnCube user id
  user_id={useridfromyouraccount}

  # LearnCube user email
  email={emailyouusedtosignup}
  ```
  ***Important: This must match the user data we have stored for the LearnCube account holder.***

- Replace the Classroom participant data in the `index.html` file with user data of a classroom participant. 

  ***Note: This does not have to match the user data in your `.env` file. All your classroom participants, teachers, students and admins, will access the classroom using your LearnCube account details.***
  ```html
      <div id="library-client"></div>
      <link rel="stylesheet" type="text/css" href="https://static.learncube.net/client/library.css">
      <script type="text/javascript" src="https://static.learncube.net/client/library.js"></script>
      <script type="text/javascript">
          const classroom = new Library('#library-client',
              {
                  'userid': {{TEST USER ID HERE}}, // Eg. 12345G
                  'username': {{TEST USERNAME HERE}}, // Eg. 'Test Widget Teacher',
                  'publicKey': {{YOUR PUBLIC KEY HERE}}',
                  'userType': 'admin', // Eg. 'admin | teacher | student'
                  'validateUrl': '/get-valid-token/'
              });
      </script>
  ```

- Install dependencies and run 
  ```shell
  npm install
  npm start
  ```

- Navigate to http://localhost:3001 to view your library.

<br/>

[Troubleshooting authentication issues](https://github.com/LearnCube/virtualclassroomclient/blob/main/AUTH.md#troubleshooting)  
[Training Videos](https://www.youtube.com/playlist?list=PLrlg2DdRh_t0k-VHU5R-u5GorWysBNUwp)  
