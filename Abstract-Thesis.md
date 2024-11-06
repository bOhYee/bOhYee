# Extending the capabilities of a virtual prototyping framework for functional and non-functional properties

### Abstract
In recent years, the rapid advancements in Artificial Intelligence (AI) technologies and the increasing pervasiveness of Internet of Things (IoT) applications have made embedded platforms more complex to design and implement. Such systems are tightly coupled with the environment, that is continuously sensed to run the algorithms on fresh data, communicate the generated results to any external actors, and react accordingly through actuating features. This implies that, depending on the application, constraints that go beyond pure performance, such as response time, power consumption or safety, may be imposed, therefore requiring a greater amount of development time and resources to build the complete system. As a consequence, virtual prototyping solutions are steadily becoming more and more popular due to their ability to let designers explore multiple design variations and test them against the required specifications without (or before) building a hardware prototype. This allows also a drastic reduction in product costs and development time. Several simulators are already available on the market, targeting the simulation of specific properties of embedded systems. These properties can be divided into functional and extra-functional properties, where the former are related to the tasks that the system is expected to perform, while the latter refer to constraints on the manner in which the system implements and delivers its functionalities. This thesis focuses on the development of virtual platforms that include the monitoring of the extra-functional aspects. The cyber part (processor modeling and software simulation) is managed by a functional RISC-V instruction set simulator, GVSoC. This is integrated with the simulation of other peripherals and of power aspects (e.g., power consumption, power distribution policies and storage), that are implemented in SystemC-AMS. Both environments are C-based, and are part of a virtual platform called MESSY, constructed to run functional and power simulations in a single simulation run. To allow a more realistic simulation, it was necessary to open the platform to the communication with external tools, that would cover complex extra-functional aspects that would be too complex to model in a C-based approach. This has been addressed by implementing the capability to connect to external applications through a Unix socket component, named VirtualConnector. This module can be used by any simulated component contained within the tested system to exchange data during the simulation, allowing for more realistic scenarios to be created and validated. To demonstrate the potential introduced with the integration of the VirtualConnector, the virtual platform was connected to Webots, a popular robotic simulation software, to simulate the management of a robotic arm in a pick and place scenario. As an additional contribution, MESSY was extended with a more accurate implementation of the communication channel. Due to its original high-level implementation, data exchanges between the core of the architecture and the other system components occurred instantaneously and were very limited. For these reasons, the channel was reworked to establish a low-level functional bus. The Advanced eXtensible Interface (AXI) protocol was chosen for the newly developed interconnection. It was demonstrated that the integrated channel introduces a negligible simulation overhead of around 2\% compared to the original implementation.