
In order to run on Gentoo GNU Linux:

Install this repository and its dependencies:

julia -e 'Pkg.clone("https://github.com/RainerHeintzmann/View5D.jl")'
julia -e 'Pkg.clone("https://github.com/RainerHeintzmann/JavaShowMethods.jl")'


julia -e `Pkg.add("JavaCall")`
julia -e `Pkg.add("JavaShowMethods")`


