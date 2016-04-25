# Example LTI Tool Consumer Using ims-lti Gem

This is a basic and simple LTI Tool Consumer that uses the
[ims-lti](https://github.com/instructure/ims-lti) gem.
To get this running in your development environment, check out the repo then:

    bundle install
    shotgun

You can use this with the [example LTI Tool Provider](https://github.com/instructure/lti_tool_provider_example)
to do some simple LTI testing.

## Usage
Visit http://localhost:9393/tool_config to configure a Tool Provider and launch to it.

You can POST directly to the http://localhost:9393/tool_launch url with configuration params in the request body:

```
curl -X POST -d "tool_name=test&consumer_key=aHM1S8HfmsNVWyySQZUS&consumer_secret=H7W9aAKsrwCowHZhSs9M&launch_url=http%3A%2F%2Flocalhost%3A3000%2Flti-launch&background=true&role=learner&context_id=123&curstom_resource_view=DEFAULT&resource_lookup_type=EXERCISE_BY_PARENT_ID&custom_resource_lookup_value=571e7b895fad558029000044&parent_group_id=571e753e5fad55a7f500000f" http://localhost:9393/tool_launch
```

`background=true` tells the app the immediately POST an LTI request to launch_url
