# imgbox
点击图片放大预览

<div class='image-list'>
  <div class='cover'><img  style='width:80px;height: 80px;display: inline-block;margin:5px 5px 0 0' src=''></div>
  <div class='cover'><img  style='width:80px;height: 80px;display: inline-block;margin:5px 5px 0 0' src=''></div>
  <div class='cover'><img  style='width:80px;height: 80px;display: inline-block;margin:5px 5px 0 0' src=''></div>
</div>

$('.cover').click( function() {
                var this_ = $(this);
                var images = this_.parents('.image-list').find('.cover');
                var imagesArr = new Array();
                $.each(images, function(i, image) {
                    imagesArr.push($(image).children('img').attr('src'));
                });
                $.pictureViewer({
                    images: imagesArr, //需要查看的图片，数据类型为数组
                    initImageIndex: this_.index() + 1, //初始查看第几张图片，默认1
                    scrollSwitch: true //是否使用鼠标滚轮切换图片，默认false（此功能需要jquery.mousewheel插件的支持）
                });
            });
