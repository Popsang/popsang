Actor的目的是处理消息，这些消息是从其它actor（或者从actor系统外部）发送过来的。连接发送者与接收者的纽带是actor的邮箱：每个actor有且仅有一个邮箱，所有的发来的消息都在邮箱里排队。排队按照发送操作的时间顺序来进行，这意味着由于actor分布在不同的线程中，所以从不同的actor发来的消息在运行时没有一个固定的顺序。从另一个角度讲，从同一个actor发送到相同目标actor的多个消息，会按发送的顺序排队。