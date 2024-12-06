## Angular Update

Angular is usually upgraded to the next major version twice a year (spring and autumn).

As we use an NX monorepo for s.o.l.i.d., the upgrade must be carried out using the upgrade tools - see [Documentation](https://nx.dev/using-nx/updating-nx).

Note: The migration with the Angular tools does not necessarily work for libraries but only for the primary app.

The general procedure is as follows:
* only _one_ major version per update
* Fix all problems until the app works properly (e.g. syntax changes, deprecations...)
* only then can you upgrade to the next major version

Tip: Perform the Angular update branch in a separate, newly cloned repository, then it won't mess up the dependencies.
