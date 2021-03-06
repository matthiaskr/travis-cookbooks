# Neo4J Server Chef Cookbook

This is an OpsCode Chef cookbook for Neo4J Server Community Edition.

It uses officially released tarballs to install Neo4J under /usr/local/neo4j-server,
provides Upstart service script and allows you to tweak many parameters using Chef node
attributes.


## Neo4J Server Version

This cookbook currently provides Neo4J Server 1.6 (Community Edition) but can be used
to install other versions by overriding data bag attributes.


## Recipes

Main recipe is `neo4j-server::tarball`.


## Attributes

All the attributes below are namespaced under `node[:neo4j][:server]`, so `:version` is accessible
via `node[:neo4j][:server][:version]` or `node.neo4j.server.version` and so on.

* `:version`: Neo4J Server version to install (default: 1.6)
* `:installation_dir`: installation location (default: /usr/local/neo4j-server)
* `:user`: OS user Neo4J Server will be using (default: neo4j)
* `:lib_dir`: Neo4J libraries location (default: /var/lib/neo4j-server/)
* `:data_dir`: graph database location (default: /var/lib/neo4j-server/data/graph.db)
* `:conf_dir`: configuration directory location (default: /usr/local/neo4j-server/conf)
* `:lock_path`: .lock file location (default: /var/run/neo4j-server.lock)
* `:pid_path`: .pid file location (default: /var/run/neo4j-server.pid)
* `[:jvm][:xmx]`: maximum allowed JVM heap size, in MB (-Xmx JVM flag value) (default: 512)
* `[:https][:enabled]`: whether HTTPS transport is enabled (default: true)


## Dependencies

OpenJDK 6 or Sun JDK 6.


## Copyright & License

Michael S. Klishin, 2012.

Released under the [MIT license](http://www.opensource.org/licenses/mit-license.php).
