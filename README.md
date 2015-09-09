<h1>Liftmo</h1>

Backend for JSON Web API used by Liftmo Android app.

<h2>RESTful API service (JSON)</h2>
<h3>How to use</h3>
<ul>
	<li>POST, PUT, DELETE parameters are packaged</li>
	<li>GET parameters are url-encoded</li>
	<li>Parameters in () are primary key</li>
	<li>Parameters in [] are optional</li>
	<li>All other parameters are required</li>
</ul>
<h3>API URL calls</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>URL</th>
			<th>Method</th>
			<th>Parameters</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>/register</td>
			<td>POST</td>
			<td>(email, password)</td>
			<td>New user registration</td>
		</tr>
		<tr>
			<td>/register</td>
			<td>PUT</td>
			<td>(email), [fname, lname, password, unit, city, state, country]</td>
			<td>Update user info</td>
		</tr>
		<tr>
			<td>/login</td>
			<td>POST</td>
			<td>(email, password)</td>
			<td>User login</td>
		</tr>
		<tr>
			<td>/lifts</td>
			<td>GET</td>
			<td>none</td>
			<td>Fetch all lifts</td>
		</tr>
		<tr>
			<td>/workouts</td>
			<td>POST</td>
			<td>name, description, authorfname, authorlname</td>
			<td>Create new workout</td>
		</tr>
		<tr>
			<td>/workouts</td>
			<td>GET</td>
			<td>(id)</td>
			<td>Fetch workout</td>
		</tr>
		<tr>
			<td>/workouts</td>
			<td>PUT</td>
			<td>(id), name, description, authorfname, authorlname</td>
			<td>Update workout</td>
		</tr>
		<tr>
			<td>/workouts</td>
			<td>DELETE</td>
			<td>(id)</td>
			<td>Delete a workout along with all its lifts</td>
		</tr>
		<tr>
			<td>/workoutlifts</td>
			<td>POST</td>
			<td>(workoutid, liftnum), liftsid, reps, amt</td>
			<td>Add new lift within a workout</td>
		</tr>
		<tr>
			<td>/workoutlifts</td>
			<td>GET</td>
			<td>(workoutid)</td>
			<td>Get all lifts from a workout</td>
		</tr>	
		<tr>
			<td>/userlifts</td>
			<td>POST</td>
			<td>userid, liftid, reps, amt, [success]</td>
			<td>Create new user lift</td>
		</tr>
		<tr>
			<td>/userlifts</td>
			<td>GET</td>
			<td>(userid), [date range]</td>
			<td>Get user lifts in a date range</td>
		</tr>
		<tr>
			<td>/userlifts</td>
			<td>PUT</td>
			<td>(id), userid, liftid, reps, amt, [success]</td>
			<td>Update user lift</td>
		</tr>
		<tr>
			<td>/userlifts</td>
			<td>DELETE</td>
			<td>(id)</td>
			<td>Remove user lift</td>
		</tr>
		<tr>
			<td>/maxes</td>
			<td>POST</td>
			<td>(usersid, liftid, amt, reps)</td>
			<td>Adds new max for a user</td>
		</tr>
		<tr>
			<td>/maxes</td>
			<td>GET</td>
			<td>(userid)</td>
			<td>Get all maxes for a user</td>
		</tr>
		<tr>
			<td>/maxes</td>
			<td>PUT</td>
			<td>(usersid, liftid, amt, reps)</td>
			<td>Edits incorrect max for a user</td>
		</tr>
	</tbody>
</table>
<h2>Database Schema</h2>
<h3>users</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td>int</td>
			<td>20</td>
			<td></td>
		</tr>
		<tr>
			<td>fname</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>lname</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>email</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>passhash</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>apikey</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>status</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>createdate</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>unit</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>city</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>state</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>country</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>lifts</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td>int</td>
			<td>20</td>
			<td></td>
		</tr>
		<tr>
			<td>name</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>nickname</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>description</td>
			<td>medium text</td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>videourl</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
		<tr>
			<td>parentname</td>
			<td>varchar</td>
			<td>255</td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>userlifts</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>userid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>liftid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>timestamp</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>success</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>reps</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>workouts</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>name</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>description</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>fname</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>lname</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>createdate</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>workoutlifts</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>workoutid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>liftid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>liftnum</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>reps</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>amt</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>maxes</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>userid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>liftid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>amt</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>timestamp</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>reps</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>muscles</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>id</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>name</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>imageurl</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>nickname</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>
<h3>liftmuscles</h3>
<table class="table table-hover table-bordered">
	<thead>
		<tr>
			<th>name</th>
			<th>type</th>
			<th>size</th>
			<th>description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>muscleid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>liftid</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>

## About

Written by [Jiawei Zhang](https://github.com/jiaweizhang)

## Libraries

App built with the help of these libs:

* [Slim, a micro framework for PHP](http://www.slimframework.com/)
* [AngularJS, HTML enhanced for web apps](https://angularjs.org/)

## Services

App built with the help of these services:

* [Google Cloud SQL](https://cloud.google.com/sql/)
* [Google App Engine](https://cloud.google.com/appengine/)

## Acknowledgements

* Alan Guo for helping with Android application
* Jeremy Lai for weightlifting knowledge