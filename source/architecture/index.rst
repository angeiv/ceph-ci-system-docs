..
   Copyright 2018 Xing Zhang

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

Teuthology 架构
===============

自动化测试框架流程大致如下：

.. code-block:: guess

   github push -> jenkins ->    baremetal slave    -> shaman <-> chacra -> teuthology -> fog -> testnode -> paddles
                            |                        OR                      |
                             \  mita  ->  prado  ->  OVH slave  /

软件组成
========

Teuthology 测试框架所使用到的软件组成如下：

* `Jenkins <https://jenkins.io/>`_ 持续集成工具
* `teuthology <https://github.com/ceph/teuthology>`_ Ceph 测试套件
* `mita <https://github.com/ceph/mita>`_ Jenkins Slave 编排服务，用于动态创建 Jenkins Slave
* `prado <https://github.com/ceph/prado>`_ 提供运行 Ansible 单个脚本的 Web 服务，用于节点初始化
* `shaman <https://github.com/ceph/shaman>`_ 查询提供软件包的 chacra 节点，水平扩展和调度 chacra 节点
* `chacra <https://github.com/ceph/chacra>`_ 提供不同架构二进制包或文件的管理 REST API 接口

参考连接
========

https://wiki.sepia.ceph.com/doku.php
