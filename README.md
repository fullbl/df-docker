# Dwarf Fortress + dfhack + dfplex in Docker

USAGE:
```
docker run --security-opt=seccomp=unconfined -d -p 1234:1234 -p 8000:8000/tcp -v /home/debian/df/save:/df_linux/data/save -v /home/debian/df/movie:/df_linux/data/movie --cpus=".6" fullbl/dfplex:latest
```

FORKED FROM: https://github.com/BenLubar/df-docker

INSPIRATIONS: 
- https://github.com/vexingcodes/dwarf-fortress-docker
- https://github.com/DockerDemos/DwarfFortressServer