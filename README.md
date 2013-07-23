A service wrapper execution for elasticsearch using [Java Service Wrapper](http://wrapper.tanukisoftware.org/).

Installation guide
==================

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

Running on 64-bit Windows
-------------------------

This requires a commercial license for Java Service Wrapper. Licenses are bound to a specific machine, so make sure you send the correct host id when ordering the license.

Once you have your license information, paste the extra `wrapper.license.*` lines into the `elasticsearch.conf` file. Then download the corresponding windows x86 64 bit build of the JSW.

Copy `bin\wrapper.exe` to `bin\service\exec\elasticsearch-windows-x86-64.exe`, and `lib\wrapper.dll` and `lib\wrapper.jar` to `bin\service\lib` in your elasticsearch directory. Also make sure you have a 64-bit JRE installed. The service can then be installed and started as described above.
