# js-
http://www.zhangxinxu.com/wordpress/2016/01/understand-css-stacking-context-order-z-index/

// 浏览器兼容性表
http://www.cnblogs.com/yangjie-space/p/4856109.html


http://blog.csdn.net/sinat_27790827/article/details/52637984  


http://efe.baidu.com/blog/mobile-fixed-layout/


https://www.zhihu.com/question/41441895

https://zhuanlan.zhihu.com/p/25370825

https://www.zhihu.com/search?type=content&q=javascript%E4%BB%A3%E7%A0%81%E8%B4%A8%E9%87%8F

https://www.amazon.cn/%E5%88%BB%E6%84%8F%E7%BB%83%E4%B9%A0-%E5%A6%82%E4%BD%95%E4%BB%8E%E6%96%B0%E6%89%8B%E5%88%B0%E5%A4%A7%E5%B8%88-%E5%AE%89%E5%BE%B7%E6%96%AF-%E8%89%BE%E5%88%A9%E5%85%8B%E6%A3%AE/dp/B01MDQ7RAX/ref=tmm_pap_swatch_0?_encoding=UTF8&qid=&sr=

http://www.ruanyifeng.com/blog/2010/05/object-oriented_javascript_encapsulation.html


聚合数据 API
https://www.jisuapi.com/api/train/

https://juejin.im/post/593021272f301e0058273468


http://www.codewars.com
const Components = {
  Button,
  Header,
  Footer,
  Swipe,
  SwipeItem,
  Cell
};

const install = (Vue) => {
  Object.keys(Components).forEach((key) => {
    Vue.component(`mp${key}`, Components[key]);
  });
  Vue.prototype.indicator = Indicator;
  Vue.prototype.toast = Toast;
};

export default Object.assign({}, Components, { install });
