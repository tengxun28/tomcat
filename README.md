# .jenkins
# tomcat
0. 确保 /bin/sh --> /bin/bash
1. tomcat 下运行jenkins,两者从网上下载下来都是jar/war形式，运行设置的jdk版本号必须不低于
编译tomcat和jenkins的jdk版本号,否则tomcat无法启动或者jenkins无法启动
2. 由于使用jdk1.8版本编译的jenkins，无法编译android5.1源码(原因为android5.1代码编译需要使用openjdk-7,但在设置为
1.8jdk的tomcat和jenkins框架下运行始终报错,无法解决)，所以只能找到用jdk1.7编译的tomcat和jenkins，
最终能编译出android5.1代码,这里下载的是apache-tomcat-8.5.15和jenkins-2.7.1.war
3. .bashrc不设置环境变量,在 bin/startup.sh里设置环境变量
# cootf wangyaohui 20170620 add begin
export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/
export JRE_HOME=${JAVA_HOME}/jre 
export CATALINA_HOME=/home/wangyaohui/sd/android_env/tomcat
export CLASSPATH=.:${JRE_HOME}/lib/rt.jar:${JAVA_HOME}/lib/dt.jar:${JAVA_HOME}/lib/tools.jar:$JAVA_HOME/lib:$JRE_HOME/lib:$CATALINA_HOME/lib:$CLASSPATH

export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$CATALINA_HOME/bin:$PATH
java -version
# cootf wangyaohui 20170620 add end

4  出现过8080端口被占用，导致tomcat无法启动的情况，解决办法:
   修改 conf/server.xml,8080改成其他端口
5  jenkins　编译android5.1的job配置里:

date
ifconfig
whoami
pwd
echo $PATH

which java
which javap
java -version
gcc -v
cd src/LINUX/android
git checkout ruim
export PATH=.:/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:$GRADLE_HOME/bin
export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64
export JRE_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
source build/envsetup.sh


lunch msm8909-userdebug

which java
java -version
which javac
javac -version
which javap
javap -version
make -j32
