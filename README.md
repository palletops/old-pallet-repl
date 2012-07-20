pallet-repl
===========

A set of utilities for the REPL and beyond (lein maybe?)

This project is meant to privide facilities for using pallet at the
REPL. Pallet's main APIs are meant to be programmed upon, but they are
not that user friendly sometimes (e.g. try listing the nodes in a
compute provider)

A secondary goal is to make whatever functions here reusable, for
example from Leiningen. What this probably means is that for each
implemented functionality there will be at least two functions, one
that generates the data, and its counterpart that prints the data, in
a pretty pretty way.

You, the Pallet user, have a major stake in this project. You are the
one dealing with Pallet day to day and finding annoyances here and
there. We want your input! Also, we want your help too! This is a
perfect project to start contributing to Pallet while scratching your
own itch. For this reason, we crave your feature request, but also,
we'll splice the work into easy, medium or hard issues, and then you
can pick according to your comfort level.

What does this all mean?
------------------------

This is what we have in mind:

```clojure
user> (pallet.repl/show-nodes vmfest)
===========================================================
:host-name       | :running? | :primary-ip    | :private-ip
===========================================================
Test-1           | false     |                |            
SmartOS          | false     |                |            
SmartOS from IMG | false     |                |            
ubuntu           | false     | 10.0.2.15      |            
slaves-1         | true      | 192.168.56.103 |            
jobtracker-0     | true      | 192.168.56.101 |            
slaves-0         | true      | 192.168.56.102 |            
===========================================================
```

or this:

```clojure
user> (pallet.repl/running-nodes? ec2-service)

true
```

Some bookkeeping
----------------

- This project is in the pallet.repl namespace, and will eventually be
  folded into Pallet proper.
  
- This project uses leingingen 2, for now, and will be pushed to
  clojars.
  
- We use [Git Flow](https://github.com/nvie/gitflow/) to manage the
  repository. So, releases are on `master` and the bulk of development
  happens in feature branches that are folded into `develop`. Develop
  should always compile and work. Make sure of it!!!
  
- We do high level feature planning using GitHub's issues and
  milestones. We try to make the milestones thematic, and pin them to
  a future release. But of course all can be changed.
  
- We maintain a ReleaseNotes.md document, for the Release Notes. If
  you are releasing a new version, make sure you add the new changes
  into that document.
  
- Don't pollute clojars with SNAPSHOTS.

License
-------

Licensed under [EPL](http://www.eclipse.org/legal/epl-v10.html)

Copyright 2010, 2011, 2012 Antoni Batchelli &  Hugo Duncan.
