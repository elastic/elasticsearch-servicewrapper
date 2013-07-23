A service wrapper execution for elasticsearch using [Java Service Wrapper](http://wrapper.tanukisoftware.org/). 
Simply place the `service` directory under the elasticsearch `bin` directory and edit the `elasticsearch.conf` file to point to the correct elasticsearch home path.

ElasticSearch can be run as a service using the `elasticsearch` script located under `bin/service` location. The script accepts a single parameter with the following values:

<table>
	<tr>
		<th>Parameter</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>console</td>
		<td>Run the elasticsearch in the foreground.</td>
	</tr>
	<tr>
		<td>start</td>
		<td>Run elasticsearch in the background.</td>
	</tr>
	<tr>
		<td>stop</td>
		<td>Stops elasticsearch if its running.</td>
	</tr>
	<tr>
		<td>install</td>
		<td>Install elasticsearch to run on system startup (init.d / service).</td>
	</tr>
	<tr>
		<td>remove</td>
		<td>Removes elasticsearch from system startup (init.d / service).</td>
	</tr>
</table>

The service uses Java Service Wrapper which is a small native wrapper around the Java virtual machine which also monitors it.

Note, passing JVM level configuration (such as -X parameters) should be set within the `elasticsearch.conf` file.

The `ES_HEAP_SIZE` environment variable controls the maximum memory allocation for the JVM (set in megabytes). It defaults to `1024`.