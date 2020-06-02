Bootstrap: docker
From: julia:1.4.2

%post
    apt-get -y update
    apt-get -y install emacs-nox
    apt-get -y install python3-pip
    pip3 install matplotlib
    ln -s /usr/local/julia/bin/julia /usr/local/bin/julia
    echo $HOME $JULIA_DEPOT_PATH
    export JULIA_DEPOT_PATH=/opt/julia-depot
    julia --eval 'using Pkg; pkg"add HTTP"'
    julia --eval 'using Pkg; pkg"add PhysOcean"'
    julia --eval 'using Pkg; pkg"add https://github.com/gher-ulg/OceanPlot.jl#master"'
    julia --eval 'using Pkg; pkg"add https://github.com/gher-ulg/DIVAnd.jl#master"'
    julia --eval 'using Pkg; pkg"add Missings"'
    julia --eval 'using Pkg; pkg"add PackageCompiler"'
    julia --eval 'using Pkg; pkg"add PyPlot Interpolations MAT"'
    julia --eval 'using Pkg; pkg"add JSON SpecialFunctions Interact Roots"'
    julia --eval 'using Pkg; pkg"add Gumbo AbstractTrees Glob NCDatasets Knet CSV"'
    julia --eval 'using Pkg; pkg"add DataStructures Compat Mustache"'


%environment
    export LC_ALL=C
    export JULIA_DEPOT_PATH=/opt/julia-depot

%runscript
    # first depot entry must be writable
    # https://github.com/JuliaLang/Pkg.jl/pull/733#issuecomment-420811091
    # https://github.com/JuliaLang/Pkg.jl/issues/763
    export JULIA_DEPOT_PATH=$PWD/.julia-depot-singularity:/opt/julia-depot
    echo JULIA_DEPOT_PATH: $JULIA_DEPOT_PATH
    julia "$@"
