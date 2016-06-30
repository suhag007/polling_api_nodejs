## Api's for poll management system

### Requirements
1. Install mongo db on your local <br />
Refer - https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04 <br />
2. Install Rockmongo to ( GUI for mongo ) <br />
Refer - http://blog.khairulazam.net/2013/05/19/install-rockmongo-on-ubuntu/ <br />

#### How to run
```bash
$ git clone https://github.com/excellencetechnologies/etech_testing_api.git
```
```bash
$ cd etech_testing_api
```
```bash
$ npm install
```
```bash
$ npm start
```

then open localhost:3000 <br />
which will show "Welcome to Express" on page. <br />

Now you are ready to use api's


#### API Details

##### 1. Add User
/add_user?username=admin&password=admin&role=admin

Response : 
User Already exists
{"error":1,"message":"Account Already Exists!"}

User created 
{"error":0,"data":{"username":"admian","password":"admin","role":"admin","id":"576d03da647a7ae24332fe48"}}

##### 2. Login
/login?username=admin&password=admin

Response : 
Success login
{"error":0,"data":{"username":"admin","password":"admin","role":"admin","_id":"576bc39508d7faee3abf9306","__v":0}}

Fail login
{"error":1,"data":"user not exists"}

##### 3. List Users
/list_users

Response : 
{"error":0,"data":[{"username":"admin","password":"admin","role":"admin","_id":"576bc39508d7faee3abf9306","__v":0},{"username":"guest","password":"guest","role":"guest","_id":"576bc6f7aa9e68513b55d410","__v":0},{"username":"admian","password":"admin","role":"admin","_id":"576d03da647a7ae24332fe48","__v":0}]}

##### 4. Add New Poll
/add_poll?title=first%20polll&options=opt1____opt2____opt3____opt4

Response : 
{"error":0,"data":{"title":"first polll","options":[{"option":"opt1","vote":0},{"option":"opt2","vote":0},{"option":"opt3","vote":0},{"option":"opt4","vote":0}],"id":"5770d42ca2dde3b0239044b2"}}

##### 5. List All Polls
/list_polls

##### 6. List a Poll
/list_poll

##### 7. Vote Api
/do_vote?id=577212fdd1bba33c17b5b64e&option_text=nodejs

##### 8. Add New Option to a poll
/add_new_option?id=577212fdd1bba33c17b5b64e&option_text=arunkumar

##### 9 Delete poll option
/delete_poll_option?id=577212fdd1bba33c17b5b64e&option_text=java

##### 10. Update Poll Title
/update_poll_title?id=577212fdd1bba33c17b5b64e&title=newtitle

##### 11. Delete Poll
/delete_poll?id=577212fdd1bba33c17b5b64e

