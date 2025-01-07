利用power bi为上市公司进行财报数据的分析

1.Power Bi产品介绍：


PPower Bi是由微软（Microsoft）开发的一款商业智能工具（BI），用于对财报等数据分析，可视化报告生成，它能够帮助企业和个人进行轻松的原始数据操作转换成可操作的洞察，支持多个数据源导入数据，并且通过强大的可视化功能提供交互式的报表和仪表盘


2.确定数据源：


在我们制作报表之前我们需要有一个明确和靠谱的数据来源，因为本次分析是基于Power BI Desktop可视化展示希荻微连续4年的财务指标对应的数据。所以我们的数据来源通常在Wind上能够获取，Wind终端上提供了该公司相关的资产负债，利润表，资金流量表，成长分析，杜邦分析等一系列数据表格。所以本次会以分析资产负债表为例子来说明power bi的使用方式。


3.获取数据


如何在wind中获取我们所需要的数据，首先我们需要注册并且登录wind终端数据，然后点击搜索引擎输入需要分析的公司，然后点击深度资料，最后找到资产负债表并且找到xls图标将其导出。本文件一共做了四个板块，资产负债表，利润表，现金流量表以及成长分析。但这次的教程只以现金流量表为例。


1),搜索引擎搜索希荻微


<img width="976" alt="希荻微 png" src="https://github.com/user-attachments/assets/8ff08ba0-dd27-4859-9923-0e2ae8b823f0" />


2),点击上图左下深度资料，并且找到现金流量表


<img width="976" alt="深度资料" src="https://github.com/user-attachments/assets/7f55f629-a3a6-4f66-8a03-846c77b3adf9" />


3),找到数据流量表后，点击xls图标并对目标数据进行导出，导出形式为Excel表格


<img width="813" alt="数据 png" src="https://github.com/user-attachments/assets/7b9bd320-2331-4752-871e-204d174e9396" />



4,利用Power Query清洗数据：


在进入正式的数据分析之前，在wind上面获取的数据是以二维表的形式呈现的，然而将以二维表形式呈现的原始数据直接导入会使得导入进power bi的数据发生混乱，所以我们需要再导入数据前对数据进行整理和清洗，清除相关null的数据。首先我们需要导入数据，点击power query中的获取数据，选择Excel，选择指定的excel表格，点击转换数据，在转换页面中点击“将第一行用作标题”，再使用逆透视其他列，将二维表转换为一维表。在转换为一维表，并且在power Bi中倒入结构表，以及日历表。


1),透视后的一维表


![一维表 png](https://github.com/user-attachments/assets/fedea214-01ca-4bca-a84a-796ba2d8d40a)


2),结构表，日历表


![结构表](https://github.com/user-attachments/assets/8187f051-fba4-4419-ad05-7ef8da759fa3)


![日期表](https://github.com/user-attachments/assets/ae98e78c-27a8-45d8-8ec3-ffed1840dff3)


5,将结构表，数据表和日期表（逆透视后的一维表相关联），进行建模，在模型视图上，结构表和日期表是和数据表呈现一对多的关系


![模型视图 PNG](https://github.com/user-attachments/assets/f15b1817-50e5-48ec-b215-83623a746ea7)


6,接下来将添加相关度量值，并且利用DAX公式，计算出对应的数据以及增长率，在合适的位置添加切片器，以展示年份，以下具体展示公式的编写和运用


1),负债


![负债](https://github.com/user-attachments/assets/0e16dca7-7424-420a-a4e7-43ef50729c13)


2),资产


![资产](https://github.com/user-attachments/assets/194eb457-38a1-4d81-ad7c-3bd8c04c592e)


3）,所有者权益


![所有者权益](https://github.com/user-attachments/assets/fd0a9126-ec48-4aa8-907b-0177247f1c54)


4),资产负债表金额


![资产负债表金额](https://github.com/user-attachments/assets/25128443-9423-4d26-9c4f-3875313be082)


5),资产负债表金额YoY%(同比情况下，我们一般用Power Bi里面的语言来表示（去年-今年）/去年，如__PREV_YEAR, __PREV_YEAR。


![YOY](https://github.com/user-attachments/assets/81ff0fc6-9755-453b-ae77-7275e6bffb2c)


6),资产增长率


![资产增长率](https://github.com/user-attachments/assets/aaffa51f-34aa-49f7-b737-a2e2e69d30a7)


7),所有者权益增长率


![所有者权益增长率](https://github.com/user-attachments/assets/6b4b29af-616b-43c2-a849-3e26d671c730)


7,在填写完公式之后，在可视化分析中选取合适的图标，来展示对应的交互式仪表盘，以方便读者更加清晰的阅读数据，并且加工美化，最后是及效果图为这样


![资产负债表分析](https://github.com/user-attachments/assets/d93e7e25-1984-47f0-ac0e-21061f4c27a9)


8,产出分析



