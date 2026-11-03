[Seed for a medium task. Expand or change it until the pass@ check solves it in at most 3 of 5 trials. Make one small change per push: a big rewrite of a task that is too easy often jumps straight to 0 of 5. Replace this line and the seed with your final instruction.]

Re-running discovery should drop removed devices and pick up renames

We run discover_devices(prefer_cache=False) every few hours so Home Assistant picks up account changes without a restart. New vacuums show up fine, but nothing else about the account is noticed. I removed my old S5 in the Roborock app and it is still listed, still online in the background, and its leftovers are still in our cache file. I also renamed the S7 from "Robot" to "Upstairs" and it still reports "Robot" until I restart. The rooms I renamed in the app keep their old names too, even after the rooms refresh.

After a fresh discovery I want the manager to match the account. A device that is gone should be shut down, stop being listed, and leave nothing behind in the cache, including when it was in the middle of reconnecting at that moment. It should not quietly come back in the cache file a minute later. Vacuums other people shared with me are still part of my account, so those must stay. A device that is still there should show its new details. Put simply, what I read from a device after re-discovery should match what I'd read if I restarted with the same account data.

Devices that didn't change should be left completely alone: no reconnecting and no second "ready" notification.

If the cloud call fails we already fall back to the cached data, and that should keep meaning nothing changed. A flaky network should never make my vacuums disappear.
