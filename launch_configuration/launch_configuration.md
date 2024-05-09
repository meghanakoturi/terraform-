- **Source:** ./launch_configuration
- **Description:** Creates launch configurations for launching EC2 instances with specified configurations.
- **Input Variables:**
  - `launch_configuration_name_prefix` = "my-lc-"
  - `source_instance_id` = module.ami.ami_id
  - `launch_configuration_instance_type` = "t2.micro"
  - `launch_configuration_key_name`    = "JENKINS"
  - `security_group_id` = module.security_group.security_group_id
  - `launch_configuration_user_data`   = <<-EOF
                                         #!/bin/bash
                                         sudo apt-get update -y
                                         sudo systemctl enable tomcat9
                                         sudo systemctl start tomcat9
                                         EOF.
