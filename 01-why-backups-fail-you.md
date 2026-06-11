# Why backups fail you

Most people who lose data had backups. The backups existed; they just did not work when needed. This is the central, uncomfortable truth of backup and recovery: having a backup is not the same as being able to recover, and the gap between the two is where disasters happen. Understanding the ways backups fail is what turns a false sense of safety into actual protection, because the failures are predictable and avoidable once you know to look for them.

## The untested backup

The most common failure is the backup that was never tested by actually restoring from it. A backup process runs, files accumulate, and everyone assumes recovery is possible, until the day it is needed and the restore fails: the backup was incomplete, corrupted, in a format that cannot be read, or missing something essential. The backup looked fine because it produced files; whether those files could rebuild a working system was never checked. This is why a backup you have never restored is a hope rather than a backup. The only proof a backup works is a successful restore from it, and without that proof, you have confidence without basis.

## The backup that stopped silently

A second common failure is the backup process that quietly stopped working at some point and was not noticed, so the most recent usable backup is far older than anyone realizes. Backup jobs fail for many reasons, a credential expired, a disk filled, a configuration changed, and if no one is alerted when a backup fails, the failure goes unnoticed until a restore is needed and the only available backup is weeks or months stale. The data since then is gone. This is why backups need monitoring: a backup process you are not actively confirming is running is one that may have silently stopped, leaving you with old or no backups when you reach for them.

## The backup in the same place as the original

A third failure is keeping the backup in the same place as the data it protects, so that whatever destroys the original also destroys the backup. A backup on the same server, the same disk, or the same provider as the original shares the original's fate: the server fails, the account is compromised, the provider has an incident, and both the data and its backup are lost together. A backup only protects against an event it survives, so a backup co-located with the original protects against fewer things than it appears to. This is the reasoning behind keeping copies in separate places, which the next page formalizes.

## The backup that includes the corruption

A fourth, subtler failure is when the problem you are recovering from is already in the backups. If data is corrupted or compromised and the backup process faithfully copies the corrupted state, then recent backups contain the same problem, and restoring them restores the problem. This is common with issues that develop over time before being noticed: by the time you discover the corruption or the compromise, the recent backups have it too, and only an older backup from before the problem is clean. This is why retention matters, keeping backups going back far enough to predate a problem you might not notice immediately, which the retention page covers.

## The lesson: a backup is a recovery capability

The thread through every failure is that a backup is only meaningful as part of a recovery capability that actually works, not as a set of files that exist. The questions that matter are whether you can restore, whether the backup is recent, whether it survives the events you fear, and whether it predates problems you might discover late. Each failure above is a no to one of those questions despite backups appearing to exist. The rest of this reference is about making the answers yes: multiple copies in multiple places, tested by real restores, recent enough and old enough to cover what you need. A backup strategy is judged by recovery, and recovery is what the failures above all fail to deliver.
