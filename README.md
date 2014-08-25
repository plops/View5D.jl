
In order to run on Gentoo GNU Linux:

Install this repository and its dependencies:

```
julia -e 'Pkg.clone("https://github.com/plops/View5D.jl")'
julia -e 'Pkg.clone("https://github.com/RainerHeintzmann/JavaShowMethods.jl")'


julia -e `Pkg.add("JavaCall")`
julia -e `Pkg.add("JavaShowMethods")`
```

before running julia you have to make sure that libjvm.so is found:

```
export JAVA_LIB=/usr/lib/jvm/oracle-jre-bin-1.7/lib/amd64/server/
```

You also have to compile the java sources of View5D into class files. On my machine it looks like this:
```
martin@labolg ~/.julia/v0.4/View5D/java/src $ ./compile 
ImageCanvas.java:1482: warning: [deprecation] PlotWindow(String,String,String,double[],double[]) in PlotWindow has been deprecated
     PlotWindow myplot = new PlotWindow("View5D Plot",XAxisTitle,YAxisTitle,AxisData,LineData);
                         ^
Note: Some input files use unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.
1 warning
```


This is an example of calling the viewer from within Julia:
```
julia> using View5D
Found libjvm @ /etc/java-config-2/current-system-vm/jre/lib/amd64/server

julia> view5d(rand(100,100))
created data 1
JavaObject{:View5D}(Ptr{Void} @0x000000000485f0c0)
```

In View5D is possible to change the scale and contrast and a cursor
allows to read the exact pixel values and coordinates. Many more
things are possible in View5D (projection, selection with 2d
histograms, tracking of features in 4D/5D stacks) but I only use it as
a viewer.


![Screenshot of View5D.](/doc/screen_example-view5d.png?raw=true "Screenshot of View5D.")