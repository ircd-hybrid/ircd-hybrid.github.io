## History * ::

When talking about the history of ircd-hybrid, we have to look backwards to the times of **The Great Split** (the split in 1996 which divided the original IRC network into **EFnet** and **IRCnet**). One of the technical arguments beyond this event was how an IRC daemon should deal with duplicated entities after servers are re-linked. Generally, further EFnet admins supported the idea of **TimeStamping** nicknames and channels (so that in normal case only the newer one is dropped). Time has proved that TS along with some nick/channel delay options can be a very good choice.

Since then, several implementations of the TS protocol were created. The original one from **Comstud** (Chris Behrens) was +CS patch for ircd-2.8.21. Another one is **Taner**'s extension for 2.8 called +th, which actually begins the history of hybrid. Because of little cooperation with Taner, in 1997 **Jon Lusky** (Rodder) spawned his own project based on 2.8/th.v5a.3, which later became **2.8/hybrid-2**.

(Note, version 1 never really existed.)

From the very early days of the project it was developed and greatly supported also by **Diane Bruce** (Dianora), who contributed a lot of code and continues to be an informal leader of our coding team. In April 1997 hybrid was first released and started to evolve quickly. After h3 and h4, **version 5** was ready yet in September 1997. Apart from the technical details, it brought in the well-known, fresh numerics, which are nowadays collected in **custom.lang**. About 1998, hybrid became the most popular IRC daemon on EFnet.

**hybrid-6** (Dec 1998) was a very successful release, introducing many fixes, cleanups and new features (such as CAPAB, +e, PRIVMSG @#chan, REJECT_HOLD, improved X/Q lines support, better flood control). The project managed to get a large development team of individuals, who helped clean up or rewrite old and dirty 2.8 code. Among others, all server commands which used to be condensed were finally moved to their own files.

As of 2006, h6 branch is still being used on EFnet. Its current maintainer is **Arnvid Karstad** (ievil).

In August 1999 developers decided to spawn another branch of hybrid. The main aim was to sweep away and rewrite everything that looked dirty and hard to analyse. A good illustration of what have been done is the change that took place on server VERSION reply: 2.8/hybrid-6.0 was renamed to ircd-hybrid-7.0, as the ircd really no longer resembled the old 2.8. In fact, some of the good changes are:

* source tree was reorganized once again;
* I/O was rewritten with a clear interface borrowed from Squid;
* new metacode, such as event/hook subsystems;
* dynamically loaded modules \-\- almost any command can be loaded/unloaded at any time;
* completely new configuration file, considered more human-friendly (block oriented rather than line/field oriented);
* halfops (restricted ops, mode +h, marked with % on NAMES);
* reorganised ziplinks, i.e. moved zlib stuff out of the core code to a separate process named 'servlink';
* support for encrypted (OpenSSL) links, as requested by EFnet admins;
* innovative idea of LazyLeafs, which could lead IRC to better scalability (although it's not usable at this moment; we are going to fix it in the near future).

It took 4 years before 7.0 was released, and when it finally was (2003), we weren't quite happy of it. Unfortunately, during this time many controversial ideas were implemented, some of them visible to end users (like anonymous ops, gettext), some not (linebufs, adns, 4 separate lists for channel members). The code was pretty readable, but still unnecessarily convoluted. The algorithms just needed rethinking, and many junky/untested features were bothering. The real end of the whole cleanup and development process, started in 1999, is **ircd-hybrid-7.1** (2005). We use to say 7.1 is what 7.0 (no longer supported) **should** be.

The latest STABLE release, 7.2, introduces another new metacode (generic hooks and callbacks manager), makes all connection limits dynamically changeable at runtime, and as always carries a lot of bugfixes and various improvements. We plan to further increase the flexibility and modularity with ideas like modular configuration parser, modular user and channel modes etc.; you can watch our work by checking out the -CURRENT tree.

\* ***Please note that this is an archived section with data that is most likely out of date and exists solely for historical information purposes.***
