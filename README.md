# Longurl.jl
 A Julia implementation of the R package longurl. For transforming short url's back into their long form. 
 
## Installation

Clone this repository to your local system

Install depencies with

```
using Pkg
Pkg.add("DataFrames")
Pkg.add("HTTP")
```

Now all thats left to use this project is starting up the project environment with ```Pkg.activate("path/to/Longurl.jl")```

This allows you to use ```using Longurl```

## Usage

This package provides function expand_urls that will take an array of short urls and return a dataframe with the original url, expanded url and status code. If the request itself fails expanded_url and status_code will equal 'missing'. 

```
  expand_urls(urls_to_expand)
  
Takes a list of short urls and exands them into their long form

...
# Arguments
- `urls_to_expand::Array`: the list of short urls
- `seconds::Int64`: the timeout in seconds
# Returns
- `Urls`: Struct containing properties expanded_url and status_code
...
```

## Examples

```
expand_urls(["https://tinyurl.com/yfr3dtha"])

...

Longurl.Urls(Union{Nothing, String}["www.google.com/"], Union{Nothing, String}["200"])

```
