# SiWAF Search Engine

How to use the <b>SiWAF Search Engine</b> for search into your website events.


###Syntax
<table class="table table-striped">
<thead>
<tr>
<th>Parameter</th>
<th>Value</th>
<th>Example</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>src</td>
<td>regex</td>
<td>src:1.2.3.4
src:1.2.3.[1-9]+</td>
<td>Search for a specific IP Address or Class.</td>
</tr>
<tr>
<td>req</td>
<td>regex</td>
<td>req:(.*homepage.html)
req:(?!.*tor\-exit\-node)</td>
<td>Search for requests that contain (or not) specific text.</td>
</tr>
<tr>
<td>method</td>
<td>regex</td>
<td>method:GET
method:(GET|POST)</td>
<td>Search for all requests with a specific method.</td>
</tr>
<tr>
<td>status</td>
<td>regex</td>
<td>status:404
status:30[1-9]</td>
<td>Search for a specific response HTTP status code.</td>
</tr>
<tr>
<td>status</td>
<td>regex</td>
<td>status:404
status:30[1-9]</td>
<td>Search for a specific response HTTP status code.</td>
</tr>
<tr>
<td>month</td>
<td>regex</td>
<td>month:12
month:(11|12)</td>
<td>Search all logs in a specific month.</td>
</tr>
<tr>
<td>day</td>
<td>regex</td>
<td>day:31
day:2[0-9]</td>
<td>Search all logs in a specific day.</td>
</tr>
<tr>
<td>hour</td>
<td>regex</td>
<td>hour:14
hour:(14|15)</td>
<td>Search all logs in a specific hour.</td>
</tr>
<tr>
<td>minute</td>
<td>regex</td>
<td>minute:30
minute:3[0-9]</td>
<td>Search all logs in a specific minute.</td>
</tr>
<tr>
<td>second</td>
<td>regex</td>
<td>second:59
second:5[0-9]</td>
<td>Search all logs in a specific second.</td>
</tr>
<tr>
<td>country</td>
<td>regex</td>
<td>country:Italy
country:(Italy|France)</td>
<td>Search all requests from a specific country.</td>
</tr>
<tr>
<td>reqid</td>
<td>regex</td>
<td>reqid:123456789
reqid:12345678[0-9]+</td>
<td>Search a specific request by specify the request id.</td>
</tr>
</tbody>
</table>


###In the Real Life
All parameters in the previous table are usable in the same query, for example: if i want to see all request by IP 1.2.3.4 on 25 Dec at 9 am, i can use the following query:
<pre class="mdpre">src:1.2.3.4 month:12,day:25,hour:09
</pre>
or if i want to show all requests from Italy received on 25 Dec at 09 am, i can use this query:
<pre class="mdpre">country:Italy month:12,day:25,hour:09
</pre>
and if i want to show all 404 Not Found received? Just type:
<pre class="mdpre">status:404
</pre>


###Full text search
You can search over the full header of each request just typing a regex in the search form. For example if i want to search for all user coming from Google i can use this query:

<pre class="mdpre">referer:.*google</pre>

Or if i want to show all user that Sign Up to my website:

<pre class="mdpre">method:POST.*signup</pre>
