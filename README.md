# RequestsCache.jl

[![Build Status](https://travis-ci.org/femtotrader/RequestsCache.jl.svg?branch=master)](https://travis-ci.org/femtotrader/RequestsCache.jl)

RequestsCache.jl is a transparent persistent cache using [Requests.jl](https://github.com/JuliaWeb/Requests.jl) library.

It's written using [Julia](http://julialang.org/).

[JLD.jl](https://github.com/JuliaLang/JLD.jl) library is used as backend.

Inspired by [requests-cache](http://requests-cache.readthedocs.org/).

## Install

```julia
Pkg.clone("https://github.com/femtotrader/RequestsCache.jl.git")
```

## Usage

```julia
import RequestsCache: Session, CachedSession
import RequestsCache: get

session = Session()
#session = CachedSession()
session = CachedSession(cache_name="cache.jld", backend="jld", expire_after=Base.Dates.Day(1))
#println(session)

response = get(session, "http://httpbin.org/get", query = Dict("title" => "page1"))

println(readall(response))
```

## Projects using RequestsCache.jl
 - [DataReader.jl](https://github.com/femtotrader/DataReader.jl)
