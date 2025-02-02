..
..
.. Licensed under the Apache License, Version 2.0 (the "License");
.. you may not use this file except in compliance with the License.
.. You may obtain a copy of the License at
..
..     http://www.apache.org/licenses/LICENSE-2.0
..
.. Unless required by applicable law or agreed to in writing, software
.. distributed under the License is distributed on an "AS IS" BASIS,
.. WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
.. See the License for the specific language governing permissions and
.. limitations under the License.
..

.. _to-api-user-login:

**************
``user/login``
**************

``POST``
========
Authentication of a user using username and password. Traffic Ops will send back a session cookie.

:Auth. Required: No
:Roles Required: None
:Permissions Required: None
:Response Type:  ``undefined``

Request Structure
-----------------
:p: Password
:u: Username

.. code-block:: http
	:caption: Request Example

	POST /api/4.0/user/login HTTP/1.1
	Host: trafficops.infra.ciab.test
	User-Agent: curl/7.47.0
	Accept: */*
	Cookie: mojolicious=...
	Content-Length: 26
	Content-Type: application/json

	{
		"u": "admin",
		"p": "twelve"
	}

Response Structure
------------------
.. code-block:: http
	:caption: Response Example

	HTTP/1.1 200 OK
	Access-Control-Allow-Credentials: true
	Access-Control-Allow-Headers: Origin, X-Requested-With, Content-Type, Accept, Set-Cookie, Cookie
	Access-Control-Allow-Methods: POST,GET,OPTIONS,PUT,DELETE
	Access-Control-Allow-Origin: *
	Content-Type: application/json
	Set-Cookie: mojolicious=...; Path=/; Expires=Mon, 18 Nov 2019 17:40:54 GMT; Max-Age=3600; HttpOnly
	Whole-Content-Sha512: UdO6T3tMNctnVusDXzRjVwwYOnD7jmnBzPEB9PvOt2bHajTv3SKTPiIZjDzvhU6EX4p+JoG4fA5wlhgxpsejIw==
	X-Server-Name: traffic_ops_golang/
	Date: Thu, 13 Dec 2018 15:21:33 GMT
	Content-Length: 65

	{ "alerts": [
		{
			"text": "Successfully logged in.",
			"level": "success"
		}
	]}
