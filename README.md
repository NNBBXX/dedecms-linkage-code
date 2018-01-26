#dedecms联动筛选功能开发（www.dedejs.com）

已经修改好的文件仅为GBK编码，UTF-8编码的请自行转换。

使用说明：

1.模型筛选调用的核心函数写在include下的extend.func.php文件，wwwcms_filter函数用于过滤字符，防止sql注入；AddFilter是用来处理筛选过程的函数。

2.真正实现筛选的文件是arc.listview.class.php，主要靠$filtersql这个变量增加查询条件，当没有检测到筛选参数时此变量为空值，不会影响原查询。

3.调用方法说明：
  相当简单，在列表页模板需要显示筛选的地方加入{dede:php}AddFilter(模型ID,筛选样式,'字段1,字段2,字段3');{/dede:php} 即可，例：{dede:php}AddFilter(1,1,'linestyle,linethem,youdays,jgqujian');{/dede:php}。
'linestyle,linethem,youdays,jgqujian'是指定的字段名，多个字段用半角逗号分隔。

#注意事项：

1.模型ID可以在核心 - 频道模型 - 内容模型管理 找到，该页面的id号即是模型ID；

2.前台调用时，不能嵌套于织梦标签之内。

3.如果前台调不出来，请到后台：系统 - 系统设置 - 系统基本参数 - 其他选项 - 禁用模板标签 ，把“php”删除后保存。

