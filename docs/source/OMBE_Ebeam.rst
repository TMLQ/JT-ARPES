磁偏转电子束源操作
=======================

1. 使用前检查

   1. 循环水是否正常，

   2. Ebeam两根高压线是否接上，

   3. 确保两个接头有绝缘塑料套筒保护，之间有距离不会短路，

   4. Ebeam腔体外面有一个热偶，通过一个温控器连接读取温度，保证使用过程中不超过80℃

   5. 进入PLC的手动模式。

.. note::
    Ebeam开启后，需要操作人员一直在边上，直到Ebeam被关闭。

2. 启动Ebeam的控制电源（图中A区域），此时机柜风扇开始运转，前面板对应控制器上的绿色 LED (PWR)亮起，黄色 REG LED (Regulation)亮起，绿色互锁 LED 亮起（图中C区域），等10min待系统稳定

    .. image:: /_static/ebeam.png
      :alt: ebeam控制器
      :width: 500px
      :align: center
      

3. 面板中央的按钮选择LOCAL档位（图中B区域），此时方可在面板上手动调节电流和电压

4. 确保“VOLTAGE”和“EMISSION”旋钮归零

5. 对灯丝进行预热除气，延长灯丝的使用寿命，具体操作为：打开 FIL（SOURCE ON），至少保持30s，然后打开高压（HV ON）；

6. 打开 HV，其对应黄色LED亮绿灯，表示此时HV可调节。缓慢调节电位器旋钮将高压升至 6KV。随后将发射电流通过电位器调节至 2-5mA 观察光斑是否坩埚内；

.. note::
    可以通过调节电压和坩埚的前后移动，使得电子束打在坩埚正中间。电压调节最高到7KV。调节范围在6~6.3KV，就可以明显看出变化。 加电流时，必须非常慢。一开始拨到Fil挡位，从0A开始时，稍许转动，电流会自动升起到11.6A。观察真空，慢慢升起电流。充分初气后，生长时OMBE腔真空优于5E-9mbar，PUMP腔优于5E-8mbar。

7. 根据实验要求缓慢调节发射电流（Emission）至设定值。在电流增加过程中，随时注意光斑和真空变化。急剧调节发射电流会使灯丝变形甚至断裂

.. note::
    升电流方式，发射电流每增加2mA，等待30秒，观察真空和电流，如果都稳定，就重复上述步骤增加，直到束流合适，通常为0.01-0.04A/s

8. 完成实验过程后，缓慢将灯丝电流“EMISSION”和电压“Voltage”电位器调到零，然后关闭对应电流和高压；

9. 不要立即关掉电源，待电源散热10分钟后，再关闭高压电源前面板开关;



故障排除
--------------
1. 电流不稳：如果过程中发现电流有跳动，一般在上下2-3mA之间，这时请缓慢降低电流至不调动处（比如Emission=5mA）或者电流降到0，等待一会后继续缓慢升电流。正常情况下，电流会非常稳定，不会有波动。

2. 对XGS600控制器的干扰：在使用Ebeam的过程中，特别是升电流的过程中，可能会出现使XGS600出现报错"BD COM"。推测是由于两者共地，大功率的Ebeam对需要精细测量的XGS-600的干扰导致。如全量程硅出现这个报错，会在1-2秒中内自己恢复。如果离子硅出现这个报错，有可能会恢复，也有可能会自动将灯丝关闭，并无法直接开启，需要重启板卡后才能恢复。