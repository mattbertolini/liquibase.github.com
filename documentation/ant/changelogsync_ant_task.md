---
layout: default
title: Changelogsync ant task
subnav: subnav_documentation.md
---

## changeLogSync Ant Task ##

Marks all change sets as ran against the database.  Useful when you have manually updated your database.  

### Sample ###

{% highlight xml %}
<target name="sync-database" depends="prepare">
    <fail unless="db.changelog.file">db.changelog.file not set</fail>
    <fail unless="database.url">database.url not set</fail>

    <fail unless="database.username">database.username not set</fail>
    <fail unless="database.password">database.password not set</fail>

    <taskdef resource="liquibasetasks.properties">
        <classpath refid="classpath"/>

    </taskdef>

    <changeLogSync
            changeLogFile="${db.changelog.file}"
            driver="${database.driver}"
            url="${database.url}"
            username="${database.username}"
            password="${database.password}"
            classpathref="classpath"
            >
    </changeLogSync>
</target>
{% endhighlight %}



### Available Parameters ###
<table>
<tr><th>Attribute</th><th>Description</th></tr>
<tr><td>changeLogFile</td><td>The change log file to run  <b>required</b>  </td></tr>
<tr><td>driver</td><td>The name of the database driver to connect with</td></tr>
<tr><td>url</td><td>The database URL <b>required</b>  </td></tr>
<tr><td>username</td><td>The database username to connect with <b>required</b>  </td></tr>
<tr><td>password</td><td>The password to use when connecting to the database <b>required</b>  </td></tr>
<tr><td>defaultSchemaName</td><td>Schema to use by default for managed database objects and Liquibase control tables  </td></tr>
<tr><td>outputFile</td><td>Save SQL to given file rather than executing <b>required</b>  </td></tr>
<tr><td>classpathref</td><td>A reference to the classpath that contains the database driver, liquibase.jar, and the changelog.xml file <b>required</b>  </td></tr>
<tr><td>databaseChangeLogTableName</td><td>Overrides the name of the databasechangelog table to use <b>Since Liquibase 1.9</b> </td></tr>
<tr><td>databaseChangeLogLockTableName</td><td>Overrides the name of the databasechangeloglock table to use <b>Since Liquibase 1.9</b> </td></tr>
<tr><td>logLevel</td><td>Specifies one of the following logging levels: debug, info, warning, severe, off. The default level is info.</td></tr>
</table>

### Available Sub Tags ###
<table>
<tr><th>Tag</th><th>Description</th></tr>
<tr><td>changeLogProperty</td><td>Sets a [changelog_parameters](../changelog_parameters.html) set <b>Since Liquibase 1.7</b> </td></tr>
</table>

#### Available &lt;changeLogProperty&gt; Parameters ####
<table>
<tr><th>Attribute</th><th>Description</th></tr>
<tr><td>name</td><td>The name of the property to set</td></tr>
<tr><td>value</td><td>The value of the property to set</td></tr>
</table>
