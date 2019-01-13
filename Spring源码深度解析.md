<h3>第三章默认标签的解析</h3>
Spring通过BeanDefinition将配置文件中的<bean>配置信息转换为容器的内部表示，将这些BeanDefinition注册到BeanDefinitionRegistry中。Spring容器的BeanDefinitionRegistry就像Spring配置信息的内存数据库，主要是以map的形式保存，后续操作直接从BeanDefinitionRegistry中读取配置信息。要解析属性首先要创建用于承载属性的实例。也就是创建GenericBeanDefinition类型的实例。当创建了bean信息的承载实例之后，可以进行bean信息的各种属性解析了。</br>
<a href="https://blog.csdn.net/lzgsea/article/details/79795290">bean标签的常用属性</a></br>
