yaws-json2
==========

yaws-json2 is encoder/decoder taked from [Yaws](https://github.com/klacke/yaws) webserver.

Installing
----------

In rebar.config:

````Erlang
{yaws_json2, ".*", {git, "git://github.com/myua/yaws-json2", {tag, "master"}}}
````

Usage
-----

Use `yaws_json2:decode_string/1` to decode json. Example of input json:

````JavaScript
{
  first_name: "John",
  last_name: "Smith",
  enabled: true,
  phone_number: 937600131,
  avatar: {
    origin: "default.png",
    thumbnails: [
      "default_min.png"
    ]
  }
}
````

Output:

````Erlang
{ok, {struct, [
  {"first_name", "John"},
  {"last_name", "Smith"},
  {"enabled", true},
  {"phone_number", 937600131},
  {"avatar", {struct, [
    {"origin", "default.png"},
    {"thumbnails", {array, [
      "default_min.png"
    ]}}
  ]}}
]}}
````

And also use `yaws_json2:encode/1` to encode json.