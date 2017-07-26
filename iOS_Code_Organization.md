# iOS Code Organization

## controller

.h 文件

.m 文件

### part : import

1）引入其他复用代码
//Controller
//UI
//Model 数据结构定义
2）工具性代码
//Category
//Helper
3）宏、Protocol、单独的头文件
4）库
//Library

### part : define 和 常量定义

### part : @interface

1）需要confirm的@protocol （按字母表顺序排序）
2）property
（1）系统自带
//非对象
BOOL
NSInteger
CGFloat
NSArray
NSDictionary
//对象
UITapGestureRecognizer //手势
UIView
UIImageView
UIScrollView
UILabel
UIButton
（2）自定义的
结构体
Block
id
NSObject/自定义数据结构
自定义对象（顺序同系统自带对象）
（3）按功能划分

### part : @implementation

// 各个生命周期
- #pragma mark - Lifecycle

// 初始化和析构
- (void)dealloc
- (instancetype)init 
- (instancetype)initWithXXX
- (void)load
- (void)viewDidLoad
- (void)viewWillAppear:(BOOL)animated
- (void)viewDidAppear:(BOOL)animated
- (void)viewWillDisappear:(BOOL)animated
- (void)viewWillLayoutSubviews

// 懒加载（排序按定义顺序）
- #pragma mark - Custom Accessors

// 公开方法
- #pragma mark - Public

// 私有方法
- #pragma mark - Private

- #pragma mark - Dev Logic Handler 

//研发逻辑处理 
- (void)fetchXXX //数据获取
- (void)setupXXX //界面设置
- (void)configXXX //数据设置、监听设置

//业务逻辑处理
- (void)trigger_bizName //业务触发
- (void)onClick_XXX //物理交互

- #pragma mark - feature ： FeatureName
//业务逻辑代码块

- #pragma mark - Protocol conformance
（按字母表顺序排序）
//系统 protocol
//自定义 protocol

- #pragma mark - convenient methods


