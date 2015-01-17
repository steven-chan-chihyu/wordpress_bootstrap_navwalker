# wordpress_bootstrap_navwalker

Why not english?
Please ask my PE teacher, he teaches me english.

# 用法

在主题目录的 functions.php 文件中引入这个文件，如

require_once('wordpress_bootstrap_navwalker.php');

然后输出主题的时候声明这个类就可以，如：

 <?php
				if ( has_nav_menu( 'header_menu' ) ) {
					wp_nav_menu( array(
						'menu'              => 'header_menu',
						'theme_location'    => 'header_menu',
						'depth'             => 0,
						'container'         => '',
						'container_class'   => '',
						'menu_class'        => 'nav navbar-nav',
						'items_wrap' 		=> '<ul class="%2$s">%3$s</ul>',
						'walker'            => new wordpress_bootstrap_navwalker()
					)	);
				}
        ?>
        
如果说和 Bootstrap 的代码结构一起，那么就这样的：

<div class="navbar navbar-default" role="banner">
  <div class="navbar-header">
    <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".header-navbar-collapse">
      <span class="sr-only">切换菜单</span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
    </button>
		<a class="navbar-brand" href="http://www.dmeng.net/" rel="home">多梦网络</a>
  </div>
  <nav id="navbar" class="collapse navbar-collapse header-navbar-collapse">
    <?php
				if ( has_nav_menu( 'header_menu' ) ) {
					wp_nav_menu( array(
						'menu'              => 'header_menu',
						'theme_location'    => 'header_menu',
						'depth'             => 0,
						'container'         => '',
						'container_class'   => '',
						'menu_class'        => 'nav navbar-nav',
						'items_wrap' 		=> '<ul class="%2$s">%3$s</ul>',
						'walker'            => new wordpress_bootstrap_navwalker()
					)	);
				}
    ?>
  </nav>
</div>
  
# 独特之处

单是GitHub上类似的项目就有好几个，这个有什独特之处？

首先，在二级菜单，是允许显示菜单项的图像描述的；其次，如果菜单项自定义CSS第一个是以 glyphicon 开头的，会自动提取为 glyphicon 图标显示在文本之前，如在自定义CSS类填写一个 glyphicon-star ，那么在菜单文本之前就会显示一个星星图标。



