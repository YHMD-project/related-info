---
noteId: "c6d6bcd0c58811ee8223b53b81422cd0"
tags: []

---

# dxf

## 图纸文件说明

dxf 是一种中性的图纸文件格式，可以被各类 CAD 软件读取或输出，有二进制或埃斯托玛编码两种形式。

官方关于dxf的说明文档如下:
<https://images.autodesk.com/adsk/files/autocad_2012_pdf_dxf-reference_enu.pdf>

DXF文件由标题段、表段、块段、实体段和文件结束段5部分组成

* 标题段（HEADER）标题段记录AutoCAD系统的所有标题变量的当前值或当前状态。标题变量记录了AutoCAD系统的当前工作环境，如SNAP捕捉当前状态、栅格间距式样、当前图层层名及线型、颜色等。

* 表段（TABLES）表段共包含4个表，每个表又包含可变数目的表项。这些表在文件中出现的顺序是线型表（LTYPE）、图层表（LAYER）、字样表（STYLE）、视图表（VIEW）。

* 块段（BLOCK）块段记录了所用块的块名，当前图层层名、块的种类、块的插入基点及组成该块的所有成员。块的种类分为图形块、带有属性的块和无名块三种。无名块包括用HATCH命令生成的剖面线和用DIM命令所完成的尺寸标准。

* 实体段（ENTITIES）实体段记录了每个实体的名称、所在图层及其名字、线型、颜色等。

* 文件结束段（EOF OF FILE）DXF文件的结束标志。

更加详细的解释见<https://www.cnblogs.com/xyb930826/p/4493373.html>

由于 R12 之后的 dxf 文件过大，内部信息较为复杂，所以不建议直接对其解析

有相关的轮子完成了 dxf 文件及读取功能

* netdxf
  * C#语言开发
  * git库在<https://github.com/haplokuon/netDxf>但是官方提供的例程和文档及其有限，使用情况比较模糊
  * 一篇基于netdxf的教程在<https://blog.csdn.net/u014608071/article/details/108163377>
* ezdxf
  * python语言开发
  * git库在<https://github.com/mozman/ezdxf?tab=readme-ov-file>
  * 官方文档完胜netdxf，在<https://ezdxf.readthedocs.io/en/stable/glossary.html>
* libreCAD
  * 这是一个开源的CAD软件，支持dxf文件的读取和编辑
  * git在<https://github.com/LibreCAD/LibreCAD>
