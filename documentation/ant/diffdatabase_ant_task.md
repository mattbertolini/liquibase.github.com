---
layout: default
title: Diffdatabase ant task
subnav: subnav_documentation.md
---

## diffDatabase Ant Task ##

Outputs a [diff](../diff.html) report of the difference between two databases.

### Sample ###

{% highlight xml %}
<target name="diff-database" depends="prepare">

    <taskdef resource="liquibasetasks.properties">
        <classpath refid="classpath"/>

    </taskdef>

    <diffDatabase
            driver="${database.driver}"
            url="${database.url}"
            username="${database.username}"
            password="${database.password}"

            referenceUrl="${database.url}"
            referenceUsername="${database.username}"
            referencePassword="${database.password}"

            outputFile="path/to/outputfile.txt"
            classpathref="classpath"
            >
    </diffDatabase>
</target>
{% endhighlight %}




### Available Parameters ###

<table>
<tr><th>Attribute</th><th>Description</th></tr>
<tr><td>driver</td><td>The name of the database driver to connect with</td></tr>
<tr><td>url</td><td>The target database URL <b>required</b>  </td></tr>
<tr><td>username</td><td>The target database username to connect with <b>required</b>  </td></tr>
<tr><td>password</td><td>The target database password <b>required</b>  </td></tr>
<tr><td>defaultSchemaName</td><td>Schema to use by default for managed database objects and Liquibase control tables  </td></tr>
<tr><td>referenceDriver</td><td>The name of the database driver to connect with</td></tr>
<tr><td>referenceUrl</td><td>The base database URL <b>required</b>  </td></tr>
<tr><td>referenceUsername</td><td>The base database username to connect with <b>required</b>  </td></tr>
<tr><td>referencePassword</td><td>The base database password <b>required</b>  </td></tr>
<tr><td>baseDefaultSchemaName</td><td>Schema to use by default for managed database objects and Liquibase control tables  </td></tr>
<tr><td>outputFile</td><td>Location of file to save report to <b>required</b>  </td></tr>
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
