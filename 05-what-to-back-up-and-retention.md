# What to back up and retention

Beyond how backups are placed and tested, two practical questions remain: what to include in the backups, and how long to keep them. Backing up too little leaves gaps that make recovery incomplete; keeping backups for too short a period leaves you unable to recover from problems you discover late. Getting both right ensures the backups actually cover what recovery needs and reach back far enough to be useful.

## Back up everything recovery needs

The scope of a backup should be everything required to rebuild a working system, not just the most obvious data. The primary data, like a database, is the clear part, but a working recovery often also needs configuration, uploaded files and assets, and the settings that make the system run. A backup of only the database, missing the configuration and the uploaded files, restores an incomplete system that does not actually work. Thinking through what a full recovery requires, and ensuring the backup includes all of it, prevents the discovery during recovery that something essential was never backed up. The test of scope is whether the backup, restored, produces a genuinely working system, which a restore test reveals.

## Some things should never be in backups

While backups should be complete, certain things should be handled with care or kept out. Secrets and credentials need protection wherever they live, including in backups, so a backup containing secrets must be protected as strongly as the live secrets, which the secrets-management reference covers. Data subject to handling rules, like personal data, carries those rules into the backup, so backups of sensitive data need the same protections as the live data, including encryption and controlled access. The point is that a backup is not a place where data protection relaxes; the backed-up copy of sensitive data is just as sensitive and just as much a target, and it must be protected accordingly rather than left as an easier way in.

## Set a backup schedule from the RPO

How often you back up follows from the recovery point objective: the backup frequency must be at least as frequent as the most data you can afford to lose. Data that changes constantly and matters needs frequent backups so the most recent one is never far behind; data that changes slowly can be backed up less often. The schedule should be set deliberately from the RPO for each kind of data, rather than at some arbitrary interval, so that the gap between backups is always within tolerance. Automating the schedule, so backups happen reliably without depending on someone remembering, and monitoring it, so a failure is noticed, are what make the schedule real rather than aspirational.

## Retention: keep them long enough

Retention is how long you keep backups before deleting old ones, and it matters because of the failure where a problem is already in recent backups. If corruption or a compromise developed before you noticed it, the recent backups contain it, and only a backup from before the problem is clean. Keeping backups going back far enough means you can reach a clean copy from before a problem you discovered late, rather than finding that every retained backup has the problem. The retention period should be long enough to cover the realistic window between a problem occurring and being noticed, which for slow-developing problems can be substantial. Too short a retention leaves you with only recent, possibly-contaminated copies.

## Document the whole thing

The scope, the schedule, the retention, and the recovery procedure together form the backup and recovery plan, and it should be written down, including the RTO and RPO targets it is built to meet. Documented, the plan can be followed under pressure, checked against the targets, and verified by testing. Undocumented, it lives in someone's memory and falls apart exactly when it is needed, during a stressful recovery. The documentation is also what a restore test exercises and refines: each test confirms the documented procedure works and updates it where it does not. As with the rest of this portfolio's baselines, backup and recovery is not a one-time setup but a maintained capability, scoped completely, scheduled and retained appropriately, protected like the live data, tested regularly, and documented so it works when it finally matters.
