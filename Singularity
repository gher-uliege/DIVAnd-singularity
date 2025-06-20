Bootstrap: docker
From: julia:1.11.5

%help
    Julia 1.11.5 with DIVAnd (run from a writable directory to create .julia-depot-singularity)

%post
    ln -s /usr/local/julia/bin/julia /usr/local/bin/julia
    apt-get -y update
    apt-get -y install curl
    apt-get -y install emacs-nox
    apt-get -y libfuse3
    apt-get -y libfuse3-dev
    #apt-get -y install python3.10
    #apt-get -y install python3-matplotlib
    echo $HOME $JULIA_DEPOT_PATH
    export JULIA_DEPOT_PATH=/opt/julia-depot
    julia --eval 'import Pkg; Pkg.add("PhysOcean")'
    julia --eval 'import Pkg; Pkg.add("DIVAnd")'
    julia --eval 'import Pkg; Pkg.add("Missings")'
    julia --eval 'import Pkg; Pkg.add("PackageCompiler")'
    julia --eval 'import Pkg; Pkg.add("Interpolations")' 
    julia --eval 'import Pkg; Pkg.add("MAT")'
    julia --eval 'import Pkg; Pkg.add("JSON")' 
    julia --eval 'import Pkg; Pkg.add("SpecialFunctions")' 
    julia --eval 'import Pkg; Pkg.add("Roots")'
    julia --eval 'import Pkg; Pkg.add("Gumbo")'
    julia --eval 'import Pkg; Pkg.add("AbstractTrees")' 
    julia --eval 'import Pkg; Pkg.add("Glob")' 
    julia --eval 'import Pkg; Pkg.add("NCDatasets")' 
    julia --eval 'import Pkg; Pkg.add("CSV")'
    julia --eval 'import Pkg; Pkg.add("DataStructures")'
    julia --eval 'import Pkg; Pkg.add("Compat")'
    julia --eval 'import Pkg; Pkg.add("Mustache")'
    julia --eval 'import Pkg; Pkg.add("StableRNGs")'
    julia --eval 'import Pkg; Pkg.add("HTTP")'
    julia --eval 'import Pkg; Pkg.add("CairoMakie")'
    julia --eval 'import Pkg; Pkg.add("ColorSchemes")'
    julia --eval 'import Pkg; Pkg.add("DataFrames")'
    julia --eval 'import Pkg; Pkg.add("Dates")'
    julia --eval 'import Pkg; Pkg.add("DelimitedFiles")'
    julia --eval 'import Pkg; Pkg.add("GRIB")'
    julia --eval 'import Pkg; Pkg.add("GeoArrays")'
    julia --eval 'import Pkg; Pkg.add("GeoDatasets")'
    julia --eval 'import Pkg; Pkg.add("GeoJSON")'
    julia --eval 'import Pkg; Pkg.add("GeoMakie")'
    julia --eval 'import Pkg; Pkg.add("GeometryOps")'
    julia --eval 'import Pkg; Pkg.add("GeometryTypes")'
    julia --eval 'import Pkg; Pkg.add("JupyterFormatter")'
    julia --eval 'import Pkg; Pkg.add("LinearAlgebra")'
    julia --eval 'import Pkg; Pkg.add("Makie")'
    julia --eval 'import Pkg; Pkg.add("Random")'
    julia --eval 'import Pkg; Pkg.add("Statistics")'
    julia --eval 'import Pkg; Pkg.add("TIFFDatasets")'
    julia --eval 'import Pkg; Pkg.add("VectorizationBase")'

%environment
    export LC_ALL=C.UTF-8
    export LANG=C.UTF-8
    export JULIA_DEPOT_PATH=/opt/julia-depot

%test
    # PATH is set but not exported on singularity 3.4.0
    export PATH
    mkdir /tmp/julia-depot-tmp
    export JULIA_DEPOT_PATH=/tmp/julia-depot-tmp:/opt/julia-depot
    # julia --eval 'using Pkg; pkg"test DIVAnd"'

%runscript
    # first depot entry must be writable
    # https://github.com/JuliaLang/Pkg.jl/pull/733#issuecomment-420811091
    # https://github.com/JuliaLang/Pkg.jl/issues/763
    export JULIA_DEPOT_PATH=$PWD/.julia-depot-singularity:/opt/julia-depot
    echo JULIA_DEPOT_PATH: $JULIA_DEPOT_PATH
    julia "$@"
