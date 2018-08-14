Inconsistencies
###############

[Insert feature here] doesn't work!
-----------------------------------

Glowstone is a completely custom server software - that means that it does not use any of the Minecraft code.
CraftBukkit (commonly known as Bukkit) heavily used internal Minecraft code for a lot of the things that it does.

As Glowstone doesn't, and can't, use the relevant Minecraft code for anything it implements,
all of the features you'd expect from a Minecraft server must be rewritten from scratch.

As a result, Glowstone development is a little slow for some people's tastes,
and leaves many new users somewhat confused. While we are working to be a complete Minecraft server replacement,
these things take time.

I used the same world seed on [Platform], but Glowstone's world looks different
-------------------------------------------------------------------------------

Because our terrain generator was made from scratch, using the same seed with another platform will not generate the same terrain
(and may actually be completely different!). This is an expected caveat from a from-scratch implementation,
because of how pseudo-randomization works.
