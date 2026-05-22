Deadcoin bootstrap tree
======================

Deadcoin is being revived from this historical NovaCoin-derived codebase as a separate network bootstrap. This update starts that work by giving the project its own runtime identity and by stopping automatic peer discovery from the legacy NovaCoin network.

Current bootstrap changes
-------------------------

* default binaries now build as `deadcoind` and `deadcoin-qt`
* runtime defaults now use Deadcoin names for the app, data directory, config file, pid file, and URI scheme
* bootstrap networking now uses Deadcoin-specific message magic and ports
* automatic DNS/IRC seeding is disabled by default until dedicated Deadcoin bootstrap infrastructure exists
* compiled checkpoints are reduced to genesis so the chain can diverge from legacy NovaCoin history

Build
-----

Headless daemon build entrypoint:

    cd /home/runner/work/Deadcoin/Deadcoin/src
    make -f makefile.unix

The current sandbox does not include the legacy Boost/Berkeley DB development packages required by this codebase, so the build stops early until those dependencies are installed.

Next bootstrap work
-------------------

* generate and wire in Deadcoin-specific genesis blocks
* replace placeholder bootstrap discovery with real Deadcoin seed nodes
* update branding assets and installer resources
* modernize the dependency/toolchain story so the daemon can build on current systems
