FROM jupyter/datascience-notebook:julia-1.9.3

ENV JULIA_NUM_THREADS=4

USER root

RUN groupadd -f jovyan && \
    usermod -a -G jovyan jovyan

RUN mkdir -p /home/jovyan/.cursor-server/data/User/globalStorage/julialang.language-julia/lsdepot/v1 && \
    chown -R jovyan:jovyan /home/jovyan/.cursor-server && \
    chmod -R u+rw /home/jovyan/.cursor-server

COPY ./init.jl /tmp/init.jl

USER jovyan

RUN julia /tmp/init.jl
