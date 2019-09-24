.. _cn_api_fluid_Variable:

Variable
-------------------------------

.. py:class:: paddle.fluid.Variable

**注意：**
  **1. 请不要直接调用** `Variable` **的构造函数，因为这会造成严重的错误发生！**

  **2. 在静态图形模式下：请使用** `Block.create_var` **创建一个静态的** `Variable` **，该静态的** `Variable` **在使用** :ref:`cn_api_fluid_executor` **执行前是没有实际是数据的。**

  **3. 在** `Dygraph <../../user_guides/howto/dygraph/DyGraph.html>`_ **模式下请使用** :ref:`cn_api_fluid_dygraph_to_variable`

在Fluid中，OP的每个输入和输出都是 :ref:`api_guide_Variable` 。多数情况下， :ref:`api_guide_Variable` 用于保存不同种类的数据或训练标签。 :ref:`api_guide_Variable` 总是属于某一个 :ref:`api_guide_Block` 。所有 :ref:`api_guide_Variable` 都有其自己的 ``name`` ,不同 :ref:`api_guide_Block` 中的两个 :ref:`api_guide_Variable` 可以具有相同的名称。如果您使用的 **不是** `Dygraph <../../user_guides/howto/dygraph/DyGraph.html>`_ 模式，那么当同一个 :ref:`api_guide_Block` 中的 :ref:`api_guide_Variable` 拥有相同 ``name`` 将意味着他们会共享相同的内容。 :ref:`api_guide_Variable` 有很多种。它们每种都有自己的属性和用法。请参考 `framework.proto <https://github.com/PaddlePaddle/Paddle/blob/develop/paddle/fluid/framework/framework.proto>`_ 以获得详细信息。 :ref:`api_guide_Variable` 的大多数成员变量可以设置为 ``None``。它的意思是它不可用或稍后指定。