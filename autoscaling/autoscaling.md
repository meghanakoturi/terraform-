- **Source:** ./autoscaling
- **Description:** Configures an Auto Scaling Group (ASG) for dynamically scaling EC2 instances based on demand.
- **Input Variables:**
  asg_name                = "my-asg"
  max_size                = 3
  min_size                = 1
  desired_capacity        = 1
  vpc_zone_identifiers     = [module.networking.subnet1_id]
  launch_configuration_name   = module.launch_configuration.launch_configuration_id
  target_group_arns       = [module.load_balancer.target_group_arn]
- **Output Variables:**
  - None
