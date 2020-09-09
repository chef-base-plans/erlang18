[![Build Status](https://dev.azure.com/chefcorp-partnerengineering/Chef%20Base%20Plans/_apis/build/status/chef-base-plans.erlang18?branchName=master)](https://dev.azure.com/chefcorp-partnerengineering/Chef%20Base%20Plans/_build/latest?definitionId=224&branchName=master)

# erlang18

Erlang is a programming language used to build massively scalable soft real-time systems with requirements on high availability. Some of its uses are in telecoms, banking, e-commerce, computer telephony and instant messaging. See [documentation](https://www.erlang.org/docs)

## Maintainers

* The Core Planners: <chef-core-planners@chef.io>

## Type of Package

Binary package

### Use as Dependency

Binary packages can be set as runtime or build time dependencies. See [Defining your dependencies](https://www.habitat.sh/docs/developing-packages/developing-packages/#sts=Define%20Your%20Dependencies) for more information.

To add core/erlang18 as a dependency, you can add one of the following to your plan file.

#### Buildtime Dependency

> pkg_build_deps=(core/erlang18)

#### Runtime dependency

> pkg_deps=(core/erlang18)

### Use as Tool

#### Installation

To install this plan, you should run the following commands to first install, and then link the binaries this plan creates.

``hab pkg install core/erlang18 --binlink``

will add the following binaries to the PATH:

* /bin/ct_run
* /bin/dialyzer
* /bin/epmd
* /bin/erl
* /bin/erlc
* /bin/escript
* /bin/run_erl
* /bin/to_erl
* /bin/typer

For example:

```bash
$ hab pkg install core/erlang18 --binlink
» Installing core/erlang18
☁ Determining latest version of core/erlang18 in the 'stable' channel
→ Found newer installed version (core/erlang18/18.3/20200903164422) than remote version (core/erlang18/18.3/20200404000818)
→ Using core/erlang18/18.3/20200903164422
★ Install of core/erlang18/18.3/20200903164422 complete with 0 new packages installed.
» Binlinking typer from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked typer from core/erlang18/18.3/20200903164422 to /bin/typer
» Binlinking to_erl from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked to_erl from core/erlang18/18.3/20200903164422 to /bin/to_erl
» Binlinking ct_run from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked ct_run from core/erlang18/18.3/20200903164422 to /bin/ct_run
» Binlinking erl from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked erl from core/erlang18/18.3/20200903164422 to /bin/erl
» Binlinking escript from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked escript from core/erlang18/18.3/20200903164422 to /bin/escript
» Binlinking run_erl from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked run_erl from core/erlang18/18.3/20200903164422 to /bin/run_erl
» Binlinking epmd from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked epmd from core/erlang18/18.3/20200903164422 to /bin/epmd
» Binlinking dialyzer from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked dialyzer from core/erlang18/18.3/20200903164422 to /bin/dialyzer
» Binlinking erlc from core/erlang18/18.3/20200903164422 into /bin
★ Binlinked erlc from core/erlang18/18.3/20200903164422 to /bin/erlc
```

#### Using an example binary

You can now use the binary as normal.  For example, save the following erlang script and call it ``hello``:

```erlang
#!/usr/bin/env escript
-export([main/1]).
main([]) -> io:format("Hello, World!~n").
```

Then do the following:

``/bin/escript hello`` or ``escript hello``

```bash
$ escript hello
Hello, World!
```
