# EC2_NLB_WAF_SSL
EC2_NLB_WAF_SSL

Will cover 
- deploy java app on EC2
- Create NLB (LB,TG)
- Create WAF rules
- Update NLB to use SSL (traffic will be shifted to https)

1. Run java app on EC2 instance

Install git/maven/java on EC2 instance.

    cd /opt
    yum install git -y

    sudo amazon-linux-extras enable corretto8
    sudo yum install java-1.8.0-amazon-corretto* -y

    wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.zip
    unzip apache-maven-3.8.6-bin.zip 

    export PATH=$PATH:/opt/apache-maven-3.8.6/bin:.

Download Springboot app and run it:

    git clone https://github.com/tushardashpute/springboohello-CICD.git
    cd springboohello-CICD/
    mvn clean install
    cd target
    java -jar gs-spring-boot-0.1.0.jar
