<h1>Queuing Theory Simulation</h1>

queueTheorySimulation is a bash script that implements the solution of the queuing theory example proposed in pages 3 and 4 of the book <cite>"Systems Simulation: The Art and Science" by Robert Shannon (1975)</cite> 

<h3>Proposed example</h3>

Consider a single-channel queueing (waiting line) system such as a checkout stand at a small gift shop. Assume that
the time between arrivals of the customers is uniformly distributed from 1 through 10 minutes (for simplicity we
round off all times to the nearest whole minute). Let us assume further that the amount of time required to service
each customer is uniformly distributed from 1 through 6 minutes. We are interested in the average time a customer
spends in the system (both waiting and being serviced) and the percentage of time that the check-out clerk is not
occupied with work.


In brief, we are looking for:

<ul>
<b>i</b> Average time a customer spends in the system
</ul>
<ul>
<b>ii</b>. % of time that the check-out clerk is not occupied with work.

</ul>

<table>
<tr>
<td>Customer</td>
  <td>Time Since Last Arrival (min)</td>
  <td>Service Time (min)</td>
  <td>Arrival Clock Time</td>
  <td>Service Begins</td>
  <td>Service Ends</td>
  <td>Customer Wait (min)</td>
  <td>Clerk idle (min)</td>
</tr>
<tr>
<td>1</td>
  <td>-</td>
  <td>1</td>
  <td>0:00</td>
  <td>0:00</td>
  <td>0:01</td>
  <td>1</td>
  <td>0</td>
</tr>
<tr>
<td>2</td>
  <td>2</td>
  <td>3</td>
  <td>0:03</td>
  <td>0:03</td>
  <td>0:07</td>
  <td>4</td>
  <td>2</td>
</tr>
<tr>
<td>3</td>
  <td>7</td>
  <td>4</td>
  <td>0:10</td>
  <td>0:10</td>
  <td>0:14</td>
  <td>4</td>
  <td>3</td>
</tr>
<tr>
<td>4</td>
  <td>3</td>
  <td>2</td>
  <td>0:13</td>
  <td>0:14</td>
  <td>0:16</td>
  <td>3</td>
  <td>0</td>
</tr>
<tr>
<td>5</td>
  <td>9</td>
  <td>1</td>
  <td>0:22</td>
  <td>0:22</td>
  <td>0:23</td>
  <td>1</td>
  <td>6</td>
</tr>
<tr>
<td>6</td>
  <td>10</td>
  <td>5</td>
  <td>0:32</td>
  <td>0:32</td>
  <td>0:37</td>
  <td>5</td>
  <td>9</td>
</tr>
<tr>
<td>7</td>
  <td>6</td>
  <td>4</td>
  <td>0:38</td>
  <td>0:38</td>
  <td>0:42</td>
  <td>4</td>
  <td>1</td>
</tr>
<td>8</td>
  <td>8</td>
  <td>6</td>
  <td>0:46</td>
  <td>0:46</td>
  <td>0:52</td>
  <td>6</td>
  <td>4</td>
</tr>
<tr>
<td>9</td>
  <td>8</td>
  <td>1</td>
  <td>0:54</td>
  <td>0:54</td>
  <td>0:55</td>
  <td>1</td>
  <td>2</td>
</tr>
<tr>
<td>10</td>
  <td>8</td>
  <td>3</td>
  <td>1:02</td>
  <td>1:02</td>
  <td>1:05</td>
  <td>3</td>
  <td>7</td>
</tr>
<tr>
<td>11</td>
  <td>7</td>
  <td>5</td>
  <td>1:09</td>
  <td>1:09</td>
  <td>1:14</td>
  <td>5</td>
  <td>4</td>
</tr>
<td>12</td>
  <td>3</td>
  <td>5</td>
  <td>1:12</td>
  <td>1:14</td>
  <td>1:19</td>
  <td>7</td>
  <td>0</td>
</tr>
<tr>
<td>13</td>
  <td>8</td>
  <td>3</td>
  <td>1:20</td>
  <td>1:20</td>
  <td>1:23</td>
  <td>3</td>
  <td>1</td>
</tr>
<tr>
<td>14</td>
  <td>4</td>
  <td>6</td>
  <td>1:24</td>
  <td>1:24</td>
  <td>1:30</td>
  <td>6</td>
  <td>1</td>
</tr>
<tr>
<td>15</td>
  <td>4</td>
  <td>1</td>
  <td>1:28</td>
  <td>1:30</td>
  <td>1:31</td>
  <td>3</td>
  <td>0</td>
</tr>
<tr>
<td>16</td>
  <td>7</td>
  <td>1</td>
  <td>1:35</td>
  <td>1:35</td>
  <td>1:36</td>
  <td>1</td>
  <td>4</td>
</tr>
<tr>
<td>17</td>
  <td>1</td>
  <td>6</td>
  <td>1:36</td>
  <td>1:36</td>
  <td>1:42</td>
  <td>6</td>
  <td>0</td>
</tr>
<tr>
<td>18</td>
  <td>6</td>
  <td>1</td>
  <td>1:42</td>
  <td>1:42</td>
  <td>1:43</td>
  <td>1</td>
  <td>0</td>
</tr>
<tr>
<td>19</td>
  <td>7</td>
  <td>2</td>
  <td>1:49</td>
  <td>1:49</td>
  <td>1:51</td>
  <td>2</td>
  <td>6</td>
</tr>
<tr>
<td>20</td>
  <td>6</td>
  <td>2</td>
  <td>1:55</td>
  <td>1:55</td>
  <td>1:57</td>
  <td>2</td>
  <td>4</td>
</tr>
</table> 


<h3>Solution</h3>

I have only used the commands available in the BASH command interpreter in a linux debian system. 
Nevertheless, I have found a limitation while trying to obtain non-integer values in a division operation.
For this reason, I have installed bash calculator.<br>

<code>apt-get install bc</code> <br>

I have tested the script in ubuntu and derivatives (such as mint) and I have noticed that bc is already installed
on them.

<h3>Run</h3>

To run the script you must grant execution permissions to the user by doing<br>

<code>chmod +x queueTheorySimulation.sh</code><br>

and then

<code> ./queueTheorySimulation.sh </code>

Finally, you need to enter the amount of customers to be used in the simulation, for instance, n.
Two arrays with n random integers each will be generated. The first one is time between arrivals of the customers [1..10] and the second represents the time required to service each customer [1..6].

