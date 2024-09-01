## Types of Storage

1. **tmpfs(Temporary Storage)**: store data temporarily in memory (RAM) rather than on disk.
2. **volumes**: : Volumes are managed by Docker and are stored in a part of the host filesystem that’s specifically designated for Docker. They are stored outside the container’s filesystem
3. **bind**: Bind mounts allow you to map a specific directory or file on your host machine to a directory or file inside the container.   


```sh
docker run -d \
  -it \
  --name devtest \                                    
  --mount type=bind,source="$(pwd)"/target,target=/app    # create folder inside container named "app"  
  nginx:latest                                            # create pwd/target folder inside your hosts and mount it with app. 
```    
