<h3>第三章 默认标签的解析</h3>
    Spring通过BeanDefinition将配置文件中的<bean>配置信息转换为容器的内部表示，将这些BeanDefinition注册到BeanDefinitionRegistry中。Spring容器的BeanDefinitionRegistry就像Spring配置信息的内存数据库，主要是以map的形式保存，后续操作直接从BeanDefinitionRegistry中读取配置信息。要解析属性首先要创建用于承载属性的实例。也就是创建GenericBeanDefinition类型的实例。当创建了bean信息的承载实例之后，可以进行bean信息的各种属性解析了。</br> 
    
![image](https://github.com/Love-with-Promise/manage/blob/master/images/20190113190058.png)
</br>RootBeanDefinition类图</br>

![image](https://github.com/Love-with-Promise/manage/blob/master/images/20190113194452.png)
</br>GenericBeanDefinition类图</br>
<a href="https://blog.csdn.net/lzgsea/article/details/79795290">bean标签的常用属性</a></br>
XML文档解析之后转换到GenericBeanDefinition，XML中所有的配置都可以在GenericBeanDefinition的实例类中找到对应的配置。从XML配置文件中读取到的bean信息是存储在GenericBeanDefinition中的，但是所有的Bean的后续处理都是针对于RootBeanDefinition的</br>
对alias标签，import标签的解析。</br>

<h3>第五章 Bean的加载</h3>
<h3>FactoryBean的使用</h3>
一般情况下，Spring通过反射机制利用bean的class属性指定实现类来实例化bean。</br>
单例在Spring的同一个容器内只会被创建一次，后续在获取bean直接从单例缓存中获取
在创建单例bean的时候会存在依赖注入的情况，而在创建依赖的时候为了避免循环依赖，Spring创建bean的原则是不等bean创建完成就会将bean的ObjectFactory提早曝光加入到缓存中，一旦下一个bean创建时需要依赖上个bean，则直接使用ObjectFactory。
