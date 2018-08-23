Redis image without persistence and a maxmemory / eviction policy.

Thought to be used as a simple object-cache for speeding up things, but persistence is not necessary (Like memcache(d)).

Problem with persistence is that the process of writing the dump file can use huge amounts of RAM (especially without THP).
