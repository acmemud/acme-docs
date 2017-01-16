---
publish: true
layout: blog
category: blog
----

Some stuff I did:

I went through and added #pragma no_clone to a bunch of stuff. Mostly mixins and libs and the trackers and stuff. I guess basically most stuff, except for the few things that actually get cloned. Part of me is anti-pragma. I didn't add no_inherit or no_shadow to anything; no_inherit just is wrong to me, and shadowing should be configuarable. The pragma statements don't leave a lot of room for negotiation. But no_clone is a little different, it's a compile time thing and I don't mind invoking something lower level like a pragma.
<!-- more -->
I also ditched all the calls to is_capable() in favor of ob->is_foo(). A mixin should be able to be enabled or disabled at runtime, and is_whatever() should reflect that. Usage of is_capable() should be limited to low-level checks or situations where you want to know whether a mixin can be enabled or disabled.

Thing number three that I did was scrub all that platform code for function and variable modifiers. I ditched all usage of the default statements, and declare visibility in all the individual function declarations. I also generated prototypes for all functions. As far as the individual visibility goes, public are things that must be implemented to satisfy the conditions of the API, private is private, protected is most stuff that isn't public, and then I left all the accessors as default visibility. I want them to be public, but I'm okay with the visibility being restricted by an inheriting program. All variables are private.

Now I'm writing PromptLib, which flips the idea of input_to() around and basically does a push-style interaction where there's a single function you can call, prompt(), and it issues prompt via the appropriate mechanism depending on whether it's a command prompt or input_to() prompt. Hopefully it's something I can expand to include a more comprehensive encapsulation of state and stuff like retries and maybe even validation. In someways I'm extracting functionality that I built into CommandController.

That's it for now!
