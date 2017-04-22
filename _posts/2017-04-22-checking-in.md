---
published: true
category: blog
layout: blog
---

I haven't worked on the mudlib in a while but I've been pretty active with the project in other ways. The biggest thing I did was to start on the web application. It's Flux+React and all I've really done is stand it up and implement a couple small features for connection management. Still it's been a great learning experience and I think I'm going to have a lot of fun working on it. Probably before I go any farther I want to try swapping out Flux for Redux and see how they compare. Flux seems the more accessible solution which is semi-important to me if I want people be able to mod the UI.

<!-- more -->

Over on the mudlib side, things are pretty stable. You can register and login. My longer-term goal is to get login and register working in the UI, but to do that I'm going to need to hack on things a bit. So before I go any further there, I want to get the basic shell working again so I don't have to keep restarting the driver every time I make a change. I know for a fact I have stability issues but I rarely have long enough uptimes for them to show up. Hacking on the driver is a little out of my comfort zone so I'd like to get a handle on this stuff sooner rather than later.

So for getting the shell commands working, I have to port them over to use the new command controller. That actually shouldn't be too painful, except the first command I went to work on was the 'which' command and it has some special command options. I want you to be able to do like 'which -u obj' to update your current ospec context when the command runs, but that's something that needs to be applied to a specific field which makes expressing the whole thing in the command spec a little hairy.

I still haven't decided on how I want this to work but it'll probably be something like 

```
<field id="target" type="object" updateContext="targetUpdateContext" />
<field id="targetUpdateContext" type="boolean" />`
```

and then maybe you could put a `<value>true</value>` inside the field element to hardcode it. I played with the idea of using format strings, but those aren't really meant to generate values other than new strings. This allows for complex types to be passed around. The only thing is that it now requires fields to be parsed in a priority order, as opposed to what it does now which is args, then opts, then extra. That's fine, except it introduces new  questions, like should the order be explicit or implicit, and should I bother with error checking for circular relationships and the like? I'd also be signing up to refactor a sizable chunk of command_controller.c, which is a lot heavier than just fixing up a bunch of broken UNIX commands.

I've got other ways to occupy my time until I'm ready to tackle it, and not just the UI. I've taken on a new Frob over on EotL, and his project is really ambitious. That means he'll need a lot of help, possibly in the form of me writing chunks of the code with him. It's nice to have some new blood around the place, though, and as ambitious as his project is, it's a lark compared to all the stuff I have to do for Acme. This might even give the opportunity to blog about some stuff that isn't just engineering updates.

We shall see!
