## 基于thiinkjs分页插件

* 环境要求：

  * Thinkjs 3.0

  * node

  * npm 

    ​

* 插件运用过程：

  * ```	
    npm install think-pagination
    ```

  * 在src\controller

  ```
  //后端
  async sku_pagination(){
    let datas = await this.model("sku").page(this.get("page")).countSelect();
    let html = pagination(datas,this.ctx,{
      desc:false,
      pagNum:2,
      url:'',
      class:'nomargin',
      text:{
        next:"下一页",
        prev:"上一页“,
        total:"count:${count},pages:${pages}"
      }
    })
    this.assign("pagination",html);
    this.assign({
      "data":datas.data
    })
  }
  ```

  ```
  //前端
  <table>
    {% for item in data %}
    <tr>
      <td>{{item.name}}</td>
    </tr>
    {% endfor %}
  </table>
  <nav class="pageNav">
  {{pagination | safe}}
  </nav>
  ```

  ​