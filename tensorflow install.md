


```

# Python 2.7
conda create -n tensorflow python=2.7

# Python 3.4
conda create -n tensorflow python=3.4

# Python 3.5
conda create -n tensorflow python=3.5


source activate tensorflow

conda install -c conda-forge tensorflow

source deactivate tensorflow
```


### 测试代码

```
import tensorflow as tf

hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
a = tf.constant(10)
b = tf.constant(32)
print(sess.run(a + b))

```