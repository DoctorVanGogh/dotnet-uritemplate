# UriTemplate.Core
This is a fork of a  .NET library supporting RFC 6570 URI Templates (Level 4). It is compiled for .NET 4.6.1 and .NETStandard 1.6.

## Usage
Matching uri templates with this library is pretty straight-forward:
```
var variables = new Dictionary<string, object>{ { "id", "42" } };
var uriTemplate = new UriTemplate("www.campio.io/dolor/{id}");
var binding = uriTemplate.BindByName(variables);
Console.WriteLine(binding); //prints www.campio.io/dolor/42
```

There are also more complex templates supported:
```
var variables = new Dictionary<string, object>
{
    { "x", "foo" },
    { "y", "bar" }
};
var uriTemplate = new UriTemplate("www.campio.io/dolor{?x,y}");
var binding = uriTemplate.BindByName(variables);
Console.WriteLine(binding); //prints www.campio.io/dolor?x=foo&y=bar
```

For more examples I recommend reading RFC documentation or checking out unit tests.

