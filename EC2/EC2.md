- **Source:** ./ec2
- **Description:** Launches an EC2 instance with specified configurations and user data.
- **Input Variables:**
  - `ami_id`: ami-080e1f13689e07408
  - `instance_type`: t2.micro
  - `key_name`: JENKINS
  - `subnet_id`: module.networking.subnet1_id
  - `security_group_id`: module.security_group.security_group_id
  - `user_data`: <<-EOF
                            #!/bin/bash
                            sudo apt-get update -y
                            sudo apt-get install -y openjdk-8-jdk
                            sudo apt-get install -y tomcat9
                            sudo systemctl enable tomcat9
                            sudo systemctl start tomcat9
                            EOF
- **Output Variables:**
  - `instance_id`: i-03eef14a433d6ae94
