# Campus Confessions App - IITK

## Overview
Did you know recently there exists a platform, built exclusively for the campus student community, where you can express yourself without revealing your identity at all! If not, you should definitely check out this app in the Playstore: [IITK Confessions](https://play.google.com/store/apps/details?id=com.gamingentertainment.iitkconfessions).

This platform is a BIG IMPROVEMENT to the already existing platforms that enables students write confessions in our campus community. The above folders are the complete implementation, of which most of them are irrelevant for you unless you are a high-level app developer. What you can focus on is the `lib` folder where all the front-end/backend/encryption code is present. Each file follows `.dart` extension implying that this application is developed using Flutter framework utilizing Dart as the programming language.

## Why did we open-source the code?
The primary reason for open-sourcing the code is to build trust among the campus student community. We know nobody is gonna believe what we are about to say unless we show them what we did and explain it ourself. If you are really worried about your privacy and to use this app, read the following content. Everything is well organized and easy to skip through different sections!

## Purpose of this platform
We, the team behind the existence of this platform, imagine a place where everyone can express themselves freely without any fear of reprimand/disapproval/rejection. Yes, I am talking about Confessions. Think of it like entering an arena where everybody is blindfolded but are free to say whatever they want. The platform is the digitized version of this arena. You might ask we already have this kind of platform enabled since a long time in our campus. But they are very limited to what actually can be done. <br>
<br>
Look at the video below to understand most of the app 🙂
<br>
[video]
<br>

## What you can do with this app
+ **Confess to specific individuals without disclosing your identity**. They will be notified if they have this app and you will be notified if they have seen your confession. [video timestamp] <br>
+ **They can’t just see but can chat with you while you are anonymous (anonymous chat)**. Your identity won’t be disclosed (unless you mention your name in the chat 🙂). [video timestamp] <br>
+ **Your identity is encrypted using a prevalently-used RSA encryption mechanism**, which means not even admins/backend handlers can know about you. (Go to the ‘Encryption Mechanism’ section for high-level description) <br>
+ **Ask a public poll along with confession**. Do you have a question and longing for a public opinion? Now you can do that too! [video timestamp] <br>
+ **Give your opinion on a confession anonymously**. Come on, I think you can agree that most people who read confession won’t comment on it due to fear of judgement, as their identity will be revealed. You don’t have to worry about this with this platform as your comment will be encrypted (even backend handlers wont be able to decrypt, unless you reveal your private key that is securely stored only in your mobile 🙂). [video timestamp] <br>
+ Other features: Rankings, upvotes/downvotes, reactions, sharing, etc.

## Encryption & Security
This is the most important part of this app and essential for user anonymity. I know many will be concerned about this. So, I will try to give a lucid explanation and demystify this part to my best. <br>
We are using RSA encryption mechanism. It is not necessary to get into the intricate details for understanding its mechanism. It’s a widely used algorithm and provides more than sufficient security against user privacy breach for this task. Basically, when you write a confession, a **random shared key** will be generated. Your details (userID) and specific individual details (their emails) will be encrypted using this shared key. Then this shared key is again encrypted using yours (confessor) and specific individual’s public keys and stored as a list in the backend. This list of `confessionSharedKeys` can be decrypted only using the respective user private-keys that will be only stored in corresponding mobile phones implying that not even admins/backend-handlers will be able to decrypt. If any of the shared keys cannot be decrypted that means confessor’s UID and specific individual’s emails cannot be decrypted. When a specific individual opens your confession, a loop runs through this list and if his private key is able to decrypt any of the confession-shared-keys in the list, that means the confession is for him and it will be displayed correspondingly. A video snippet is also added below for further evidence 👇 <br> 
<br>
[video] 
<br>
<br>
If it still seems unconvincing, you are highly encouraged to go through the open-sourced code. <br>
**Anonymous chats** (both messages and user details) are also encrypted using the same RSA mechanism but this time directly with the user’s private keys as only 2 parties are involved.


## Admin Privileges
To maintain a smooth decorum of expressions and free speech, we have also included admin functionality. When you post a confession, it won’t be displayed directly to the public/specific individuals. It needs to be approved by the anonymous admin-team first. They will be responsible for the content validation. If you are facing any trouble with the app, please mail to [teamconfessionsiitk@gmail.com](mailto:teamconfessionsiitk@gmail.com) and it will be handled with priority.

## Final Thoughts
This application is a product of our curiosity and effort in enabling free speech more efficient compared to the already existing platforms in our campus community. It is designed with a lot of care with a paramount emphasis on user-anonymity and data-confidentiality. Thus, there shouldn’t be any major loop holes and many more features and functionality can be included in the future. The other reason for open-sourcing this code, apart from acquiring students trust, is to improve this application and make writing confessions more efficient in the future.
