---
title: Seriously publishing a video game, my 2 year journey so far.
description: A spaceship drift racing game development adventure
date: 2024-01-26T19:45:00+05:30
preview: /posts/anxracers-2-year-journey/hero.png
slug: anxracers-2-year-journey
published: true
---

Content Warning: Too many words, distractions, programmer art, brackets, videos, geeky terms, hyperlinks, attempts at humor.

* * *

Prologue
--------

Note: 95-99.9% game projects started never get published. Source: [Random Reddit question I found](https://www.reddit.com/r/gamedev/comments/ndj6mg/what_is_the_percentage_of_unreleased_indie_games/)

  

In early 2021, after my previous 2 year long personal project ([ANXCamera](https://camera.aeonax.com/)) and 3 Games ([ANXBounce](https://play.google.com/store/apps/details?id=com.aeonax.bounce), [ANXBattle](https://www.youtube.com/watch?v=U_scB-i3QwY) and [ANXDefense](https://aeonax.itch.io/defense)). I was getting bored and craving to build something new and share with the world.

* * *

I tried making some prototypes in [Unity Game Engine](https://unity.com/products/unity-engine) inspired from [Elite Dangerous](https://www.youtube.com/watch?v=FGVUptIPFYU), like an asymmetrical spaceship doing [6DoF](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) movement

{{< youtube FeJMFf_VEpM >}}

* * *

I dabbled on some realistic thruster based flight stabilization and guns

{{< youtube Z20iBzdaR-s >}}

* * *

I destroyed some rocky rings with pointy defense canons (as seen in [The Expanse](https://www.youtube.com/watch?v=Sax5tURLTrw))

{{< youtube AYD_qldCyuk >}}

* * *

Got distracted and made something inspired from [Just Cause Grappling Hook](https://www.youtube.com/watch?v=FbMi6WAM2U4)

{{< youtube i2ISpXY7XUM >}}

Combined that with [Portal](https://www.youtube.com/watch?v=TluRVBhmf8w)

{{< youtube XFQXQmoWAw8 >}}

Broke the in-game reality (maybe it was just a bug with my code) (WARNING: strobing effect)

{{< youtube iKAwJUplJDY >}}

(All above 3D Models made in [blender](https://www.blender.org/))

And I stopped working on the above ideas as I couldn't think of a game idea around those mechanics.

* * *

The Journey
-----------

When one fine day I thought about combining [Trackmania](https://www.youtube.com/watch?v=tkTPl0A_Bk4) and [Elite Dangerous](https://www.youtube.com/watch?v=FGVUptIPFYU) and making a game.

Since I didn't have the time (had a full-time job working on a widget) and skills ([I am a grate artist](https://x.com/imgur/status/1384356160124465152?s=20)) to make a full-fledged 3D game with 3D graphics and 3D music, I disintegrated one dimension to reduce the scope, efforts, skills and time needed to make the game. I decided to make a 2D game with 2D graphics and 2D (stereo) music.

So I took a 2 weeks Christmas vacation from work in 2021 (I had accrued enough leaves, and they were at risk of getting lapsed). And I embarked on the journey of creating and publishing a game seriously (meaning on the platforms where big (AAA and AA) companies publish their games, and not only on Google Play Store).

Goal: Publish a game on multiple platforms.

I researched what I needed to do and found an easy tutorial somewhere as below:

1.  Have an Idea
    
2.  Make game
    
3.  Publish
    

Very similar to Van Oktop's ["how to draw a horse" tutorial](https://oktop.tumblr.com/post/15352780846)

* * *

So I started working on it. I fleshed out the idea as below:

> Make a racing game like Trackmania, but with spaceships. It should have good replayability, be physics based, with non-irritating music. The game should be easy to learn but hard to master.

> We should also have a track editor as well as a spaceship skin painter. Bonus: Have a spaceship creator too.

> Elite Dangerous has a Flight assist system. That ensures your spaceship always stays in control and doesn't reach relativistic velocities/vomit inducing spins. We also should have a similar system. But it should be only enabled when user is applying power to the thrusters of the spaceship

I then started developing this in [Godot](https://godotengine.org/) because I read somewhere that Godot is a great engine for 2D game development and I also wanted to learn Godot, but dropped it and went back to Unity due to [weird physics decisions](https://github.com/godotengine/godot/issues/38646) taken by Godot. Within 2 weeks I had basic core loop ready using [Kenney Assets](https://www.kenney.nl/assets/space-shooter-redux) as below:

{{< youtube OA3p9d7F2Lw >}}

Shared it few friends, few of them played it and liked it.

And one even offered to create music for the game.

![Mibris](/posts/anxracers-2-year-journey/images/1.Mib.png)

  

(Their music is now in-game as well as in the official trailer).

Added an online leaderboard and a basic track-editor in a week and released a beta version on Google Play Store on 4th Jan 2022.

The game server stored data in LiteDB (an embeddable NoSQL .NET DB)

I also integrated a telegram bot to administrate the game server.
![Telegram Bot](/posts/anxracers-2-year-journey/images/2.Bot.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFrNYtCZ1h0Eg/article-inline_image-shrink_400_744/0/1703171841965?e=1711584000&v=beta&t=zwp_ViK559X6nCF95oR027CxiGDQnon-psln1Oqt3nk) -->

Administrating the game server using telegram

The game published had 3 tracks, 1 spaceship, 4 input modes and worldwide ranking leaderboards.

{{< youtube JxewpnSHKN4 >}}

Note the Android 12's Material You inspired rounded corner UI.

* * *

5 days later a friend discovered an exploit

![Timur](/posts/anxracers-2-year-journey/images/3.Exploit.jpg)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFyqjzz-AI_gA/article-inline_image-shrink_400_744/0/1698682400340?e=1711584000&v=beta&t=-6ZWd4rf440wtAHpMQJkL1d80XJHrC-8wEs-YVxpIEo) -->

Speedrunners/Bug Exploiters when they discover time traveling.

20 days later he discovers a way to modify tracks to finish them instantly

{{< youtube TQ7ykk8eWFI >}}

It seemed people were putting serious effort into testing it. After this I added hash-based validation on spaceship and track data. Also moved the server from NoSQL based LiteDB to SQLite + Dapper ORM. (Due to some unresolved issues regarding DB [corruption](https://github.com/mbdavid/LiteDB/issues?q=is%3Aissue+is%3Aopen+corrupt+sort%3Acomments-desc) in LiteDB)

* * *

N.B. Everyone needs friends who make memes

![Meme](/posts/anxracers-2-year-journey/images/4.Meme.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQHJMhzYFj0cig/article-inline_image-shrink_1000_1488/0/1698683545834?e=1711584000&v=beta&t=wu7FXTIo_GSA42wGKdbeSo_4q8-SfLfwwHJHY1WneGc) -->

  

No Trackmania inspired game is complete without a [press-forward track](https://www.youtube.com/watch?v=0QweZzejPcU).

{{< youtube jv9DFLHRz7E >}}

After fixing some bugs and a month of development, integrated first external sign-in mechanism

{{< youtube wTeNX3VRKQQ >}}

Also added a Track Draw-er

{{< youtube MKvsNJ629WM >}}

* * *

In April 2022, made the first trailer for the game. (Using [Shotcut](https://shotcut.org/))

{{< youtube bPrfHsL9NIQ >}}

* * *

6 months after start of the game's development, first windows build was published, with Discord's [rich presence](https://discord.com/developers/docs/rich-presence/how-to#so-what-is-it) and sign-in mechanism.

and then Mod Support was added

{{< youtube NnvMgWjAJ0Y >}}

By this time the game was available as Open Beta in [Google Play Store](https://play.google.com/store/apps/details?id=com.aeonax.racers) and Early access in [Itch.io](http://Itch.io) (Itchio is like [Valve](https://en.wikipedia.org/wiki/Valve_Corporation)'s [Steam](https://en.wikipedia.org/wiki/Steam_(service)), but without an entry fee)

Many people said by this time that game felt slow for a racing game. One of the players created a (uncontrollably) fast spaceship, using the spaceship creator as seen below:

{{< youtube 78h9DZyaBl8 >}}

8 months after the start of the development, real-time multiplayer was added. I used reliable UDP library known as [LiteNetLib.](https://github.com/RevenantX/LiteNetLib) To save on server resources/cost, only 1 track+spaceship combination is available for real-time racing, as "Race of the Day" (changed weekly or bi-weekly, because why not), Everyone joins the same multiplayer session.

Skip the below video to 8m:14s to see it in action.

{{< youtube HCnqrg2mZ8s >}}

* * *

By this time my first major bug was discovered. The game was not as deterministic as I had thought it was supposed to be. Players discovered, that the first run, without any resets was faster, than consecutive attempts after reset.

This was due to a combination of two bugs.

One, I had set the [physics timestep](https://www.gamedev.net/forums/topic/673798-what-is-a-timestep/5265985/) to 0.02 sec, and was measuring timestamp accurate to 0.001s, which doesn't make sense.

And second, Unity misses applying forces on first physics frame after re-enabling a physics object. Making next race attempts slower. This was very difficult to find out. I had to analyze multiple recorded ghosts/replays.

First one was fixed by changing the physics time to 0.001. Second was fixed by re-enabling the physics object at the start it self. So as to be consistently slow everytime.

After this I had to reset the leaderboards, since previous timings had become invalid.

* * *

Then I implemented a [web-based spaceship painter](https://studios.aeonax.com/racers/skinner.html#eyJVc2VyRGlzcGxheU5hbWUiOiJBbm9uLTEwOTkiLCJVc2VySWQiOiIxZGVhZmFkZS1iMDFkLTUwZGEtYzBkZS1hYzFkMWNmYWNhZGUiLCJTaGlwSWQiOiIwMDAwMDAwMi1mMDBkLWZlZWQtYmVlNS1iYTUxYzViMGQxY2UiLCJTa2luSWQiOiIxZGVhZmFkZS0wOWFmLTQyNzUtYjU0My1lMjgxYjEwMDgyNzMifQ==), (The actual skin editor needs to be launched from inside the game)

![Spaceship Skinner](/posts/anxracers-2-year-journey/images/5.Skinner.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQGPSzgC6DLp_g/article-inline_image-shrink_1000_1488/0/1698854846907?e=1711584000&v=beta&t=in5huUg85_R3DTaQTfKP48SEkPuh2eoMX51_Oa9VIVo) -->

Svg-Based Skin Editor

* * *

The Game was shown 2nd in New and Popular Racing Games category of Itchio on 21st Aug 2022.

![Itchio Topper](/posts/anxracers-2-year-journey/images/6.Topper.jpg)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQEKywR4e5dWbQ/article-inline_image-shrink_400_744/0/1698855158773?e=1711584000&v=beta&t=LQbaGYjh8xx1-FLQSSHgX_eDE8wRfesHK7lkZlmr0M0) -->

  

In the same month the game participated in [Indie Racers Festival 2022](https://indieracers.com/2022/)

To gather feedback from non-friends, I started peddling the game to twitch streamers. I also made up an entry for the game on [IGDB](https://www.igdb.com/search?c=1&q=anxracers). This is used by Twitch streamers so they can select the correct game, while streaming.

Shared 1K Replay Video on Trackmania Reddit Sub

{{< youtube 5qVDyiuJ4uM >}}

Attracted attention of few pro-players from there, They still play the game.

Gathered a lot of feedback by talking with the players on reddit and discord.

* * *

{{< imgur "kC484bl" >}}

Players finally started learning the Flight Assist Off trick (Which didnt slow down the spaceships)

{{< imgur "X8sj9Jm" >}}

* * *

Around 10th September 2022, the game got 600th player's registration.

![600th Registration](/posts/anxracers-2-year-journey/images/7.600th.jpg)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQEifx5pbt87dQ/article-inline_image-shrink_1000_1488/0/1698857485008?e=1711584000&v=beta&t=Di0sX6HF2xKvxY6pZt-6MzTssrAPUPictfWt4LyIeGM) -->

  

* * *

Then development slowed down for few weeks. And suddenly YouTube suggested me this.

{{< youtube Dw3BZ6O_8LY >}}

Went down the rabbit hole and made an OpenAI Gym environment for the game.

{{< youtube QeKrhXZSOCw >}}

Note: No AI was trained during the making of this video. I lack hardware capable of training any AI.

Sadly this was my most viewed youtube video for a long time. Wrong audience had more interest in the game.

* * *

Went back to working on the fun part of the game.

Created the iconic [A-01 Race track](https://www.youtube.com/playlist?list=PLpCJO5OcPMKNbMNG-B2gXgU2v3rAFJW1U) in my game.

{{< youtube qoIWjOffPrU >}}

* * *

Improved the Telegram bot, to have interactive buttons.

![Bot Improvement 1](/posts/anxracers-2-year-journey/images/8.Bot.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQEG2o6JYAyRiA/article-inline_image-shrink_400_744/0/1703343223292?e=1711584000&v=beta&t=tE3Mzgtr3LQHmjtm3RLRGD1BkoyhgwriFrae5uqqo8E) -->

Ability to publish/unpublish tracks on demand, as well as Set Race of the Day track.

![Bot Improvement 2](/posts/anxracers-2-year-journey/images/9.Bot.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFh3wMoW6XtyQ/article-inline_image-shrink_400_744/0/1703343312429?e=1711584000&v=beta&t=IbWTBJ9jBitl3TFV40ZenTDF0llJheFhVpTYQapdhHE) -->

Same for spaceships

Also added notifications to Discord

![Discord FOMO](/posts/anxracers-2-year-journey/images/10.Disc.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQEcl3soa4uQLw/article-inline_image-shrink_400_744/0/1703342929488?e=1711584000&v=beta&t=H4gRhhPAKipvzzoZxjBUy5zptXksNzpOa100qx_ELRo) -->

Competitive server members get notified about latest world records

Now that I was approaching almost an year of development (Xmas 2022), I started working on a [Super Mega Update](https://aeonax.itch.io/racers/devlog/466529/super-mega-update), This update contained changes that moved me away from Kenney Assets, so that the game feels less of an [asset flip](https://en.wikipedia.org/wiki/Asset_flip). Leaderboards were cleared again. And official List of tracks was created. This tracks are still in current game. Leaderboards have not been cleared since then.

Very soon an updated trailer was created using [Kdenlive](https://kdenlive.org/en/).

{{< youtube 73iEXYpYHJ0 >}}

* * *

Early 2023, Generative AIs were on the rise. After having multiple discussions with them (Yeah, you read that right. I had multiple discussions with AIs, i.e prompt engineering), I updated the blurb on game's homepage.

https://studios.aeonax.com/racers/


Created an [Among Us](https://en.wikipedia.org/wiki/Among_Us) inspired track (on player request)

{{< youtube cvHJ08XTI3k >}}
  

And started a multi-month long UI overhaul project.

In April 2023, finished the first part (Visit below link for details)

https://aeonax.itch.io/racers/devlog/520505/bundle-123-for-androidwindows-x64-ui-overhaul-part-1

In March 2023, the a track from the game was part of Mobile Speedrunning Competition'23 Round 3. Video below shows everyone's attempts on the same track.

{{< youtube l5ZO5tDE39k >}}

In July 2023, finished the entire UI overhaul,

https://aeonax.itch.io/racers/devlog/566292/bundle-131-for-webglandroidwindows-x64-ui-overhaul-part-2

* * *

By this time a WebGL build was published on Itchio. The game was released on Microsoft Store for Windows and Xbox as well. Initially it was free, since I didn't have an Xbox to validate. It was made paid once few people tested it.

I also had a [Steam page](https://store.steampowered.com/app/2196780/ANXRacers/) up. And was slowly (in hindsight very slowly) accumulating wishlists.

Only thing remaining now was Apple. To publish on Apple App Store you need yearly subscription of Apple Developer Account. To get an Apple Developer Account, you need an Apple Device. Finally after much pondering and counting my savings, bought a Mac Studio M2 Max. Spent a month along with multiple calls to apple support to get the Developer account activated.

Luckily they didn't need me to have an iPhone and iPad to publish the game to iOS AppStore. Couldn't release it on tvOS App Store, since I don't have iTV or Apple TV device (whatever its called). Publishing apps to AppStore is a mindboggling slow, wasteful process. I guess when you have a secure walled garden, you need to ensure the devs take a lot of pain, to publish to your store. But the hardware and software integration is great.

The game published to iOS App Store just worked™

* * *

On 21st Aug 2023, moved the game from open beta testing to production release on Google Play Store. On that day Google sent around 30 new users to the game, and we crossed total 1600 player registrations in-game

![1600th Registration](/posts/anxracers-2-year-journey/images/11.1600th.jpg)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFekdMWMKjCXQ/article-inline_image-shrink_400_744/0/1702658560909?e=1711584000&v=beta&t=Sp8tLOyF_nVNcXJ-fuQfAL-KHNsCDSTMkZZK8Qet9O0) -->

Captured on the day the game went into production on Google Play Store, note the peak at the end.

On 27th Aug 2023, clicked the big green "Publish Now" button on steam

![Steam Release Button](/posts/anxracers-2-year-journey/images/12.Steam.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQGmJaeBSN8p1Q/article-inline_image-shrink_1000_1488/0/1702659297529?e=1711584000&v=beta&t=IYtMyWWZVfkFdZB7MQWeyD2kOXLxVpClvsEPO7J0f74) -->

Many indie game projects never reach this stage.

One thing of note, once you release the game on Steam, You receive many mails from allegedly in-active streamers saying, that want to start streaming again, and find your game perfect to start streaming again. They want at least 2 steam keys, so that they can play the game with their best friend on the stream. You can safely ignore this emails/spam them back broken keys or (1 working and 1 broken for maximum damage).

![Spam 1](/posts/anxracers-2-year-journey/images/13.Spam.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFQZy5NfKFVOQ/article-inline_image-shrink_400_744/0/1704218157822?e=1711584000&v=beta&t=trLAtdu2FG8iV1yQ6QcKf4uKqca_N9LJEihMlRrtQ58) -->

Nothing was whispered on Twitch. It doesn't matter coz this imposters don't have access to this twitch accounts.

![Spam 2](/posts/anxracers-2-year-journey/images/14.Spam.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQF-hX0bVxALUA/article-inline_image-shrink_400_744/0/1704218361738?e=1711584000&v=beta&t=H5-q6gd8EmylschbYglbTkGS9l_USDa7frjBKBM2eK4) -->

Again no keys were sent from my side. They don't complain about it either.

By 31st Aug 2023, I released it on Epic Games as well, Making the game available on 6 Game Stores, namely:

*   [Steam](https://store.steampowered.com/app/2196780/ANXRacers/)
    
*   [Epic Games](https://store.epicgames.com/en-US/p/anxracers-635368)
    
*   [Microsoft Xbox Store](https://www.xbox.com/en-in/games/store/anxracers/9pnj4fjpqdkj)
    
*   [Apple App Store](https://apps.apple.com/us/app/anxracers-drift-space/id6456943537)
    
*   [Google Play Store](https://play.google.com/store/apps/details?id=com.aeonax.racers)
    
*   [Itch.io](https://aeonax.itch.io/racers)
    

The game runs on Windows PC and Xbox, Linux, MacOS, iOS (iPhones and iPads) and Android Phones/Tablets and TVs, as well as browser (WebGL).

Around the same time I created the current trailer of the game in blender.

{{< youtube uOooOg8rD1s >}}

Post release continued on fixing bugs and adding few features.

A notable one, [Medals were added](https://store.steampowered.com/news/app/2196780?emclan=103582791472905212&emgid=5562564282369664332), since I got many requests for this. Players wanted a sense of achievement when they put in some effort. It shouldn't be necessary to be in top 3 world wide. Good enough time from good enough effort should be rewarded.

![Medals](/posts/anxracers-2-year-journey/images/15.Medals.jpg)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFO7fxRwMIcqA/article-inline_image-shrink_400_744/0/1703337585983?e=1711584000&v=beta&t=PFoxViCMRt6cWjztek6h0i0KxwnPele6oQLT5s8qOlI) -->

  

Since no more glaring bugs were in the game. I have been only creating new maps in last 2 months. Also since I switched jobs 2 months back, I wanted to take this a bit slow.

Epilogue
--------

Recently the game completed 2 Years of development.

I learnt a lot while working on this game, like 3D Modelling and [Video Editing](https://www.blender.org/features/video-editing/) in Blender, Vector Graphic Design in Affinity Designer, Discord Integration, Telegram Bot Integration, Compute Server Hosting, Database Design with [SQLite](https://www.sqlite.org/index.html) and [Dapper](https://github.com/DapperLib/Dapper), SEO, Publishing processes of Steam, Apple, Epic Games and Microsoft.

Some numbers/charts from my own self-implemented analytics are shown below as well as observations if any (Screenshots from [Metabase](https://www.metabase.com/) connected to my game server):

![9000th Registration](/posts/anxracers-2-year-journey/images/16.9000th.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFow3xYzQzYBg/article-inline_image-shrink_400_744/0/1703440337074?e=1711584000&v=beta&t=aeKsvNE2lvltqVjDj-ZAdFn__iZB6fc0jUvpU5X4Zq0) -->

Reached 9K Total Registrations on Christmas Eve of 2023. The steeper climb started after Google Play Production Release.

  
![Trivia Anonymoux](/posts/anxracers-2-year-journey/images/17.Trivia.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQHywy6FjPFJPQ/article-inline_image-shrink_400_744/0/1703440562608?e=1711584000&v=beta&t=lBwt1Z3WCWfQCxGAvrZ8oGxjJejDDy7V5XxiPnlPNZQ) -->

Good to see people caring about their privacy. (Or they are just lazy to fill the registration details)


![Trivia Devices](/posts/anxracers-2-year-journey/images/18.Trivia.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQFKCcLsBsFZIQ/article-inline_image-shrink_1000_1488/0/1703339534854?e=1711584000&v=beta&t=jaA0RQUIB-dDb7R9FAt8KqRppqAF0JyZYvglzY1VbvE) -->

Android TVs and Set-Top boxes seems to be in serious need of more games like mine

  

![Trivia Countries](/posts/anxracers-2-year-journey/images/19.Trivia.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQF60_P-qEmj2g/article-inline_image-shrink_1000_1488/0/1703340120347?e=1711584000&v=beta&t=YzxqIDzm5PHnhISYmSMHbxxVm-AlWYAWFppTrxZA2F0) -->

I have no idea why the game is so famous in Vietnam. I guess they have lots of Android TVs there, and they like a free game.

  
![Trivia Ships](/posts/anxracers-2-year-journey/images/20.Trivia.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQGnWR08cPe06A/article-inline_image-shrink_400_744/0/1703341465941?e=1711584000&v=beta&t=EGAi9Sil2CkOCqkxEBTWcE9vjd6a25fsjoa5mMlWrnM) -->

Players liked to race in the meme spaceship (HyperBoi) more than the slower official spaceships

  
![Trivia Events](/posts/anxracers-2-year-journey/images/21.Trivia.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQEEEiMOIGAr0g/article-inline_image-shrink_400_744/0/1703342080616?e=1711584000&v=beta&t=kazK-1ZJWosbs9wZldxgw3EicrCVAFrMJ2pso0iVAlw) -->

The above chart exposes a lots of trivia.

For e.g.

*   110K Races were started, but only 25K races were finished, 85K times they were reset.
    
*   800 times tracks were liked, but 240 times they were reverted.
    
*   2.2K times players studied how others played the tracks
    
*   5K times "Race of the Day" was joined, 850 times it was spectated.
    
*   240 attempts to login with non-existing user names. There were 7 attempts to send bogus scores.
    

You might have been thinking what about "Monetization" of the game.

Over the course of 2 Years, I researched it and thought about it a lot. I didn't like what I saw. Dark Patterns, like [lootboxes](https://en.wikipedia.org/wiki/Loot_box), [pay to win](https://en.wikipedia.org/wiki/Free-to-play#Pay-to-win), [daily rewards](https://www.darkpattern.games/pattern/11/daily-rewards.html), [sunk cost](https://www.darkpattern.games/pattern/24/invested-endowed-value.html), [FOMO](https://www.darkpattern.games/pattern/53/fear-of-missing-out.html) etc. Not everything could be avoided. A game needs to hook the player in, for them to keep playing. But I took care not to add something unethical intentionally. I have not added ads, but kept the path open for paid skins.

Currently the game is free on Android, because ads don't pay much there. But the game is priced at a small amount on other platforms so as to not be clubbed with free abandonware. Except Apple, If one can afford an apple, they can afford the apple tax.

Back to hard numbers, keeping in mind, monetization was never the goal.

People have paid the following sums:

*   31 USD on Itch.io (where payment was totally optional)
    
*   48 USD on Steam (where it was priced between 1 USD to 3 USD)
    
*   16 USD on Epic Games
    
*   9 USD on Microsoft Store
    

Whats Next
----------

Investigate paid advertising/marketing.

I plan to keep the game servers online for 3 more years assuming the costs are manageable, or game's revenue is enough to sustain them.

Some QoL improvements will be performed. SQL Query optimizations/Database cleanups, will be needed as the number of users, scores and tracks increases with time.

I plan to release a self-hostable multiplayer server.

Whenever the game servers I host online will be stopped permanently, I plan to release a self-hostable version of the same.

I think its now OK to say "**_Mission Accomplished_" of publishing the game to multiple platforms and stores**

**Thank You for Reading! Also Wish You a Happy and Prosperous New Year!!!**

Get/Try the game here: [https://studios.aeonax.com/racers/](https://studios.aeonax.com/racers/)

Credits from the game:

![Credits](/posts/anxracers-2-year-journey/images/22.Credits.png)
<!-- ![](https://media.licdn.com/dms/image/D4D12AQHyzkCJxathlQ/article-inline_image-shrink_1500_2232/0/1704219110182?e=1711584000&v=beta&t=h55AcfJz6dsytsCWEMxUFgHiwBVizD5EVnAhZE8SpyA) -->


{{ template "_internal/disqus.html" . }}

