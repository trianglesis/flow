# General idea


Use this as basis: [FLOW](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

1. Create branch `main`.
2. Create development from the `main`
   1. Optionally: set `develop` as tracked branch, or leave `main`. People may forget to track `develop`. Should only create brances from `develop`!


## User perspective

1. Sync the latest changes from the `develop`
2. Checkout `develop` into the `u/alpha/feature-ticket-001`
3. Add code and changes into the `u/alpha/feature-ticket-001`
4. Create PR from `u/alpha/feature-ticket-001` to `develop`
5. Merge (Squash) from `u/alpha/feature-ticket-001` to `develop`
6. Delete the branch
7. Sync the latest changes from the `develop`


## Release manager perspective

1. Checkout `develop` as soon as all features are there, into `release/0.1.0`
   1. `release/0.1.0` becomes unaffected by future commits at `develop` branch 
2. When release is publised:
   1. Merge `release/0.1.0` into the `main`
   2. Merge `release/0.1.0` into the `develop` ONLY: if `release/0.1.0` obtained extra fixes
   3. Merge `main` into the `develop` rebasing commits. Now `develop` and `main` are up to date.