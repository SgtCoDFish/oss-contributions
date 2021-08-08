# libgdx/ashley

Done during university when I was using ashley quite regularly. Happened to have other students ask me about this too.

## Commits

```text
commit a276fe45c81d450f305ce1b5b0bd0fe837207a70
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Tue Oct 7 14:00:29 2014 +0100

    Fix #77 where attempt to remove a Component from an
    already-reset PooledEntity would cause an IllegalArgumentException.

commit 1c83eb52baf187c629d5c1c3e9d898df994eb03f
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Tue Sep 30 12:58:30 2014 +0100

    Update PooledEngine to correctly reset entity signals and
    update test accordingly.

commit 0e4fe98ab49f601401cbb5e17e507feb8c84c7c1
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Tue Sep 30 12:57:48 2014 +0100

    Add removeAllListeners method to Signal

commit 2bf9dea370b873e6d63430a375d789fc56639062
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 23:55:07 2014 +0100

    Update "resetEntityCorrectly" test to loop over multiple entities.

commit e1cf30f79840e3bb23e165fe84893e36734f91e8
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 23:44:01 2014 +0100

    Remove count method only used in test

commit c8c4e2f5cced420168973073f7b1c7bc8d994cbe
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 19:17:13 2014 +0100

    Update AUTHORS file.

commit 33e8dddd83837f35b628ed6f4e29cae21cbaf0b4
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 19:14:30 2014 +0100

    Fix ordering of arguments for test.

commit 67a9b1d7a16730e1049a4edc547e07100d4e3e6f
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 19:08:00 2014 +0100

    Fix #70; resets component operation handler when an Entity is
    removed from an engine.

commit 2546a3387f5575148397005724c2a6d1009df9a3
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Mon Sep 29 19:06:51 2014 +0100

    Add test for #70 and Signal#countListeners method used by the test.

commit a23b241fe14a9cf861f962aab57e9c3eeb6fbad8
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Sat Aug 30 18:40:42 2014 +0100

    Implement reccommendations in #50

commit 96676f6c90649f0b1e2163376f3e873179ddaf16
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Fri Aug 22 21:24:23 2014 +0100

    Fix all warnings reported by Eclipse by removing unused imports and
    variables, and adding @SuppressWarnings where appropriate.

commit c0d78c259cd3b7b1b9831c6c3cdc6387df41b1e9
Author: Ashley Davis (SgtCoDFish) <...>
Date:   Fri Aug 22 11:12:43 2014 +0100

    Add convenience Entity.getFor(Class<? extends Component>) method, as
    mentioned in #50 - "New getComponent overload for Entity".
```
