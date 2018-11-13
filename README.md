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
}
}

---------------------------------------------
