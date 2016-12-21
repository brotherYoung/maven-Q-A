使用maven的时候，电脑装的JDK1.8，使用maven更新（maven-update project）项目后，默认会使用1.5版本的JDK，并且也是编译成1.5的，很纠结的问题。
后来在网上找到解决方案。修改maven安装目录下的conf文件夹，修改setting.xml文件，在profiles里面添加如下代码

    <profile>
        <id>jdk-1.8</id>
          <activation>
          <activeByDefault>true</activeByDefault>
          <jdk>1.8</jdk>
          </activation>
        <properties>
          <maven.compiler.source>1.8</maven.compiler.source>
          <maven.compiler.target>1.8</maven.compiler.target>
          <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>		
        </properties>
    </profile>

修改完成后，然后重新更新项目，此时jdk版本就自动更新到1.8了。到此结束搞定
