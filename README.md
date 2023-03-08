
![Python](https://img.shields.io/static/v1?label=Python&message=3.9.2&color=306998&logo=python&logoColor=white)
![Release](https://img.shields.io/static/v1?label=Release&message=v2.0&color=306998)
[![Donate](https://img.shields.io/badge/donate-buymeacoffee-green)](https://www.buymeacoffee.com/heva)

# addmember-telegram
Use `Python` to add member from Source Group to Target Group (migrate members of your group)


## Requirement
* Environment of python 3 (Linux, Window)
* Need about 20 accounts to run (Switches accounts automatically when blocked)
* Your group must have username (public group)
* Account have permission add member to your Target Group (not need join, script will be auto join target group)
* Source group is public group or accounts have joined Source Group

![Target Group is public](images/public-group.png)

### Guide line

[Video Tutorial](https://youtu.be/qnNsgHCMQYk)

<details>
  <summary>Show more</summary>

  Note: On Window, use `pip` instead of `pip3`, `python` instead of `python3`
  
 * Step 1: Install package `telethon` `readchar`
 ```
 pip3 install telethon
 
 pip3 install readchar
 ```

 or

 ```
 pip3 install -r requirements.txt
 ```

 Note: 
 
 * Step 2: create file config.json base on config.example.json
 
 
 ```
 {
  "group_source": "atmcommunityvn",
  "group_target": "ATMCommunityOfficial",
  "api_id": 1234566,
  "api_hash": "57c6f3c72c2f21676d53be2eXXXXXX",
  "from_date_active": "20201114",
  "accounts": [
    "+84Heva",
    "+84Love",
    "+84Have"
  ]
}
 ```
 > `group_source`: username of Group Source

 > `group_target`: username of Group Target

 > `api_id` and `api_hash`: Need only one (`api_id` and `api_hash`), how to get them: create an app in https://my.telegram.org/apps and copy the `api_id` and  `api_hash` into the config file

 > `group_target`: username of Group Target

 > `accounts`: list String of your phones


 * Step 3: After setting up your `config.json`, run `python3 init_session.py`, enter phone and the code you received

 ![Init session](images/step1.png)

 * Step 4: run `python3 get_members.py` to get data user and save file in folder `data` with path: `data/atmcommunityvn.json` (`atmcommunityvn` is username's Source Group)


 ```
 {
    "user_id": 847587728,
    "access_hash": 2393668282771176567,
    "username": None
 }
 ```

 Use `user_id` and `access_hash` to add member. Use username have also use to add member, but something use not have username

 One folder is created in folder `data` and have some file `.json` save data of members. If you change accounts (add more account) you need re-run `python3 get_members.py`.


 * Step 4: run `python3 add_members.py` to add member from `group_source` to `group_target`
 Logic: 
	* after adding 1 member, sleep 120s / total_client. If you have 2 accounts, it will sleep 60s
	* after each account adds 35 members --> sleep 2 hours
	* Remove account when there is a Flood, Flood Wait Error
	* Break if there are no more accounts

 Note: If your account gets blocked, go to https://web.telegram.org/k/#@SpamBot and chat /start to see the time the ban would be lifted

 ![Get data](images/block.png)

 If your account is not blocked, but error `FloodWaitError`, in Terminal like as:

 ![FloodWaitError](images/flood-wait.png)

 and you must wait 77464 seconds
 
 > You can Stop The script By crtl+z or crtl+c. type y

 Note: current_count.txt save current index. If It is interupt, please check number index in file. If note current index (base on log in Terminal), edit it to correct and re-run.

 ![Current index](images/current-index.png)

</details>


## Community Group

Telegram Group Official: [ATM Community Official](https://t.me/amtcommunityoffcial)

Telegram Group of Vietnamese: [ATM Community (Việt Nam)](https://t.me/atmcommunityvn)

## Request New Feature
[Write your request](https://github.com/south1907/addmember-telegram/discussions/72)

## Share your story
[Write your story](https://github.com/south1907/addmember-telegram/discussions/74)


<h2 tabindex="-1" dir="auto"><a id="user-content-️-donate" class="anchor" aria-hidden="true" href="#️-donate"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a><g-emoji class="g-emoji" alias="heart" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2764.png">❤️</g-emoji> Donate</h2>

<p dir="auto"><a href="https://www.paypal.com/donate/?hosted_button_id=F86F4AB65QNYL" title="https://paypal.me/Antoni" rel="nofollow"><img align="left" height="50" src="https://camo.githubusercontent.com/59cfbcf1ae58c3d6f862b1633f575920df6db1ac8974973b5e7f341a388b292d/68747470733a2f2f7777772e6d65646961666972652e636f6d2f636f6e766b65792f373264632f697a3738797337767466736c3935377a672e6a7067" alt="Paypal" data-canonical-src="https://www.mediafire.com/convkey/72dc/iz78ys7vtfsl957zg.jpg" style="max-width: 100%;"></a></p>

<br /><br />
