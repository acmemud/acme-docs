---
published: true
layout: blog
category: blog
---

I made a rather drastic design decision a few weeks ago and haven't really told anyone about it. What prompted it was the question of exactly what to do with EotL. It was probably the first question I asked myself, even before I knew what I was building. Until now, the plan has always been some variant of having a "compatibility layer" between the Acme mudlib and the EotL mudlib. EotL and Acme would run side-by-side in the same runtime environment the result would be some sort of EotL-Acme hybrid where most new content would be developed using the Acme toolkit and the legacy stuff would run off in its own bubble. This was what spurred the whole 'flavor' concept because I thought I might be able to make an 'eotl' flavor. The solution has never sat quite right with me though, it's just ugly.
Then it dawned on me -- yo dawg, what if I just keep running EotL as it is and create a telnet client in the Acme mudlib and you can mud while you mud? I can build some adapters for the messaging, send them to a console pane in the GUI, and easy peasy, you get an authentic EotL experience while still being in the Acme ecosystem. But let's not stop there, let's say this is how we build the entire Acme network! What Acme network? I haven't talked much about the Acme network, but there is one.

<!-- more -->

I'm finding that one of the complexities of designing "real games" as characterized by gamification is, what reality do you pick? Do you try to capture a macro-perspective or micro-perspective? There are merits to managing a MUD both at the city or state level and at the workplace or home level. You can only do so much on a single synchronous process, and that synchronousnessnessss is vital to the game experience.  So we'll have to network these things together, and the question of how resources get carved up demands attention.
I expect a lot of this to take shape organically, but at the very least I believe that you'll experience multiple MUDs simultaneously, penetrating reality at different "focal lengths" per se, and they'll be vertically integrated through telnet. At least they will be now, until I figure out something better. It will need to support a whole new intermud protocol that can make the most out of the Acme feature set, so there's a lot to figure out still.

What's important right now is that it guarantees a free and independent EotL, and if it's possible I can guarantee Acme players the greater freedom to assemble however they want. This isn't exactly revolutionary stuff, but ideas are starting to crystallize nicely.
