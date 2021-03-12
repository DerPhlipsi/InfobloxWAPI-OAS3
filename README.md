# InfobloxWAPI-OAS3

OpenAPI3 files describing the Infoblox WAPI. Original files taken from Vedant Sethia (infobloxopen/infoblox-swagger-wapi) with some fixes.

## What is this repository?

This repository contains the OpenAPI3 compliant definition of the Infoblox WAPI. The original files are taken from [an official Infoblox repo](https://github.com/infobloxopen/infoblox-swagger-wapi/), where they are stored in non JSON-spec compliant form, which made them not OAS3-spec compliant.

All credits for the definitions go to Vedant Sethia from Infoblox. Some corrections or enhancements will be made in the future. The specifications have been formatted using [Prettier](https://prettier.io/).

## TODO

The definitions contain some issues.

- The parameters "\_return_fields" and "\_return_fields+" create problems with code generators, since the + is stripped for the variable name, resulting in a duplicate variable declaration.
- At least using swagger-codegen and Java (jersey2-client) the return objects are parsed into POJOs that cannot be deserialized by Jackson given the actual response of an Infoblox system. Both returning the object directly as well as using "\_return_as_object" result in deserialization failures.
- Generated code uses generic Body1 - Bodyn class names for request bodies. Maybe this can be influenced to generate speaking names.

These issues could be resolved in a future version of this repo. I will add my current workarounds in the coming days.
