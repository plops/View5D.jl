
In order to run on Gentoo GNU Linux:

Install this repository and its dependencies:

```
julia -e 'Pkg.clone("https://github.com/RainerHeintzmann/View5D.jl")'
julia -e 'Pkg.clone("https://github.com/RainerHeintzmann/JavaShowMethods.jl")'


julia -e `Pkg.add("JavaCall")`
julia -e `Pkg.add("JavaShowMethods")`
```

before running julia you have to make sure that libjvm.so is found:

```
export JAVA_LIB=/usr/lib/jvm/oracle-jre-bin-1.7/lib/amd64/server/
```