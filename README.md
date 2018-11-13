# infrastructure-pipeline
Week 10 Class project
HiHi
----------------- Shell Script to add in jenkins stage pipeline------------
node('linux') {
stage ("GetInstances") {

    sh "aws ec2 describe-instances --region us-east-1"
}

stage ("CreateInstance") {
    
 sh "aws ec2 run-instances --image-id ami-04aea6bda3a47879d --count 1 --instance-type t2.micro --key-name mykeypair --security-group-ids sg-a3b8c2ef --subnet-id subnet-d674f3b1 --region us-east-1"

    output = sh returnStdout: true, script: 'aws ec2 describe-instances --region us-east-1 | jq .Instance[0].InstanceId'
}

# below portion is not working
stage("Terminate instances")
{
   sh "aws ec2 wait --region us-east-1 instance-running --instance-ids $instance_id"
   
    sh "aws terminate Intences --output"
}

}

---------------------------------------------
