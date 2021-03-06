# XYQCollectionLayout
UICollectionView Layout (Defalut、Circle、Stack、Line、Water)

### 一、CollectionView是iOS中一个非常重要的控件，它可以实现很多的炫酷的效果，例如轮播图、瀑布流、相册浏览等。其实它和TableView很相似，都是对cell进行复用，提高系统性能。然后也有一点不同的地方，CollectionView的展示由布局决定。但是它只是提供默认的布局方式流式布局，我们可以自定义布局，实现自己想要的各种效果。

### 自定义的布局方式需要选择性重写CollectionViewLayout中的方法，实现自己需要的效果，方法如下所示：

    //每一次布局前的准备工作
    -(void)prepareLayout
    
    //设置collectionView滚动区域 
    -(CGSize)collectionViewContentSize
    
    //允许每一次重新布局   
    -(BOOL)shouldInvalidateLayoutForBoundsChange:(CGRect)newBounds
    
    //布局每一个属性
    -(UICollectionViewLayoutAttributes *)layoutAttributesForItemAtIndexPath:(NSIndexPath *)indexPath
    
    //布局所有item的属性,包括header、footer
    -(NSArray *)layoutAttributesForElementsInRect:(CGRect)rect
 
 
### 二、自定义的集中布局方式如下：
 
- 圆式布局：将所有的图片环绕成一圈，可以用在相册中
 
![image](https://github.com/xiayuanquan/XYQCollectionLayout/blob/master/Demo/CollectionViewLayout/CollectionViewLayout/screenshots/circle.png)
 
- 堆叠式布局：将所有的图片堆叠起来，只有最上面的三张图片可以看到，例如”探探app“
 
![image](https://github.com/xiayuanquan/XYQCollectionLayout/blob/master/Demo/CollectionViewLayout/CollectionViewLayout/screenshots/stack.png)
 
- 线式布局：将图片左右轮播滚动显示，图片滚到离中间一定距离时，图片开始放大
 
![image](https://github.com/xiayuanquan/XYQCollectionLayout/blob/master/Demo/CollectionViewLayout/CollectionViewLayout/screenshots/line.png)
 
- 瀑布流布局：图片相错排列，增加美感，例如”蘑菇街“
![image](https://github.com/xiayuanquan/XYQCollectionLayout/blob/master/Demo/CollectionViewLayout/CollectionViewLayout/screenshots/water.png)



### 三、CocoaPods
    
pod 'XYQCollectionLayout', '~> 1.0.0'
   
   
    
### 四、How to use Api

    
    
    
    //使用圆式布局
    _collectionView = [[UICollectionView alloc] initWithFrame:frame collectionViewLayout:[[CustomCircleLayout alloc]init]];
    
    //使用线式布局 
    _collectionView = [[UICollectionView alloc] initWithFrame:frame collectionViewLayout:[[CustomLineLayout alloc]init]];
    
    //使用堆叠式布局  
     _collectionView = [[UICollectionView alloc] initWithFrame:frame collectionViewLayout:[[CustomStackLayout alloc]init]];
    
    //使用瀑布流布局，比较特别，还需要实现代理，设置图片真实宽高，详见demo
    _collectionView = [[UICollectionView alloc] initWithFrame:frame collectionViewLayout:[[WaterFlowLayout alloc]init]];
    
  
    
    
