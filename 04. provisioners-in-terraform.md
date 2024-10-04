## PROVISIONERS & CONNECTION
Can be used to execute commands on the local machine or remote machine to prepare the infrastructure

### Three types of provisioners
1. **local-exec**: runs commands on local machine
2. **file**: used for copying
3. **remote-exec**: runs commands on remote machine

### Simple structure with null_resouece
```hcl
resource "null_resource" "simple_structure_of_running_provisioners" {
depends_on = [aws_instance.web]

  connection {
    type = "ssh"
    user = "ec2-user"
    private_key = file("~/.ssh/id_rsa")
    host = aws_instance.web.public_ip
  }

  provisioner "local-exec/file/remote-exec" {
    # simple structure to run command 
  }
}
```


### local-exec provisioner
```hcl
resource "null_resurce" "run_command" {
depends_on = [aws_instance.web]               # use if needed    

  connection {                                # connection block needed when you are executing ansible playbooks
    type = "ssh"
    user = "ec2-user"
    private_key = file("~/.ssh/id_rsa")
    host = aws_instance.web.public_ip
  }

  provisioner "local-exec" {                     
      command = "echo 'hello world'"              
  }
}
```

### remote-exec provisioner

```hcl
resource "null_resurce" "create_folder" {
depends_on = [aws_instance.web]                 

  connection {
    type = "ssh"
    user = "ec2-user"
    private_key = file("~/.ssh/id_rsa")
    host = aws_instance.web.public_ip
  }
  
  provisioner "remote-exec" {                      
      inline = [
        "mkdir temp",                           # directly run commands
      ]       
  }

  ##### OR 

   provisioner "remote-exec" {                      
      script = file("entry-script.sh")          # pass the shell script to run the commands
  } 
}
```

### file-provisioner

```hcl
resource "null_resource" "copy_script_to_ec2" {
depends_on = [aws_instance.web]

  connection {
    type = "ssh"
    user = "ec2-user"
    private_key = file("~/.ssh/id_rsa")
    host = aws_instance.web.public_ip
  }

  provisioner "file" {
    source = "entry-script.sh"                                  # copy the script
    destination = "/home/ec2-user/entry-script.sh"              # paste it to remote ec2
  }
}
```

## Why Provisioners are not recommended

- use user-data if available
- Breaks idempotency concept
- TF doesn't know what you execute
- Breaks current-desired state comparison
