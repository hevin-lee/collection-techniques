# 整理各种JS方法
平时用到各种JS，收集起来，合理利用

#1：form表单循环判断脚本
  
  	for(var j=0;j<$("input.JS_input").length;j++){
    		if($("input.JS_input").eq(j).val()==''  ){
    		
    			  alert("请输入功能分区！");
    			  
    			 return;
    			 
    		}
    } 

#2：表格实现的收起和展开功能 jquery

JS代码：

    $(".js-doshow").live("click",function(){
      var index=$(this).parents('tbody').find("tr").index($(this).parents("tr"));
      var text= $(this).html()=='展开'?'收起':'展开';
      $(this).html(text);
      for(var i=index+1;i<$(this).parents('tbody').find("tr").length;i++){
        if( $(this).parents('tbody').find("tr").eq(i).hasClass("js-trshow")){
           return;	
        };
         $(this).parents('tbody').find("tr").eq(i).toggle();
      };
    });
  
html结构：
  <table width="100%" border="0" cellspacing="0" cellpadding="0" class="table_grid mt10  ">
      <thead>
        <tr>
            <th width="23%"   class="tl"> 表格1</th>
            <th width="77%"   class="tl"> 表格2</th>
        </tr>
      </thead>
      <tbody>
      <tr class="js-trshow">
         <td colspan="2"   class="tl bgf4">【<a href="javascript:void(0);" class="fr js-doshow">展开</a>】标准解读 </td>
      </tr>
      <tr class="js-trhide">
          <td   class="tl"> 首页</td>
          <td   class="tl "><div class="label"><label><input type="checkbox" value="">导出</label><label><input type="checkbox" value="">导出</label></div></td>
      </tr>
      </tbody>
  </table>
