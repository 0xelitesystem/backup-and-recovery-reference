# The 3-2-1 rule

The 3-2-1 rule is a simple, durable guideline for backup placement that addresses the failure of backups sharing the original's fate. It says: keep at least three copies of your data, on at least two different kinds of storage, with at least one copy kept offsite, away from the others. Each part of the rule closes a specific gap, and together they ensure that no single event, a disk failure, a site disaster, a provider incident, takes out both the data and all its backups.

## Three copies

The three copies are the original plus at least two backups. The reasoning is that one backup can itself fail, be corrupted, or be unreadable, so a single backup is a single point of failure for your recovery. With two backups in addition to the original, the loss of any one copy still leaves a way to recover. Three copies is the minimum that gives recovery redundancy: if the original is lost and one backup also turns out to be bad, the second backup is still there. Counting the original, this means two separate backups, not one, because relying on a single backup repeats at the recovery level the same single-point-of-failure problem backups were meant to solve.

## Two different kinds of storage

The two kinds of storage mean the copies should not all live on the same type of medium or system, because a flaw or failure mode affecting that type could take out all copies on it at once. Spreading copies across different kinds of storage means a failure specific to one kind does not destroy every copy. The point is to avoid correlated failure: if all your copies depend on the same technology, the same device type, or the same system, then a problem with that one thing is a problem with all of them. Using more than one kind of storage breaks that correlation, so the copies fail independently rather than together.

## One copy offsite

The offsite copy is the part that addresses site-level disasters and provider-level incidents. If all copies are in the same physical location or with the same provider, an event affecting that location or provider, a fire, a flood, an account compromise, a provider outage, can destroy them all together regardless of how many copies there are. Keeping at least one copy somewhere separate, a different physical location or a different provider, means such an event leaves that copy intact. The offsite copy is what survives the disaster that takes out everything in one place, which is exactly the scenario co-located backups fail to protect against.

## Why each part matters together

The rule works because each part covers a different failure, and omitting any part reopens a gap. Three copies cover a backup itself being bad. Two kinds of storage cover a failure mode specific to one storage type. One offsite copy covers a disaster affecting one location or provider. A strategy with three copies all on the same storage in the same place still falls to a single site disaster; one with copies in two places but only one total has no redundancy if that copy is bad. The combination is what ensures that the realistic disasters, hardware failure, site disaster, provider incident, each leave at least one good, recoverable copy standing.

## Apply it proportionately

The 3-2-1 rule is a guideline to adapt to what your data is worth, not a rigid mandate for every file. Critical data, the data whose loss would be a serious problem, warrants the full rule and more. Trivial or easily regenerated data may not need the same rigor. The judgment is to identify the data that genuinely matters, the data you could not easily recreate and whose loss would hurt, and ensure that data has the redundancy, the storage diversity, and the offsite copy the rule describes. Applying it proportionately, with the most protection on the most important data, keeps the effort focused where recovery actually matters, which is the data you would be desperate to get back.
