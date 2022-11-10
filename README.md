# Dwarf Fortress + dfhack + dfplex in Docker

USAGE:
```
docker run --security-opt=seccomp=unconfined -it -p 1234:1234 -p 8000:8000/tcp fullbl/dfplex:latest
```

FORKED FROM: https://github.com/BenLubar/df-docker

INSPIRATIONS: 
- https://github.com/vexingcodes/dwarf-fortress-docker
- https://github.com/DockerDemos/DwarfFortressServer