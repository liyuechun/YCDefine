# YCDefine
##iOS项目中常用到的宏整理，使用方便快捷。
/** 主屏幕的高度 */
#define YC_M_SCREEN_H [[UIScreen mainScreen] bounds].size.height
/** 主屏幕的宽度 */
#define YC_M_SCREEN_W  [[UIScreen mainScreen] bounds].size.width

/** 主屏幕的高度比例 */
#define YC_M_SCREEN_H_SCALE (M_SCREEN_H/640)
/** 主屏幕的宽度比例 */
#define YC_M_SCREEN_W_SCALE (M_SCREEN_W/320)


/** 屏幕的分辨率 当结果为1时，显示的是普通屏幕，结果为2时，显示的是Retian屏幕 */
#define YC_M_SCREEN_SCALE [[UIScreen mainScreen] scale]

/** 除去信号区的屏幕的frame */
#define YC_APP_FRAME  [[UIScreen mainScreen] applicationFrame]
/** 应用程序的屏幕高度 */
#define YC_APP_FRAME_H   [[UIScreen mainScreen] applicationFrame].size.height
/** 应用程序的屏幕宽度 */
#define YC_APP_FRAME_W    [[UIScreen mainScreen] applicationFrame].size.width


/** 系统控件的默认高度 */
#define YC_D_STATUS_BAR_H   (20.f)
#define YC_D_TOP_BAR_H      (44.f)
#define YC_D_BOTTOM_BAR_H   (49.f)
#define YC_D_CELL_H (44.f)

/** 中英状态下键盘的高度 */
#define YC_ENG_KEY_BOARD_H  (216.f)
#define YC_CHN_KEY_BOARD_H  (252.f)


#define YC_IS_IOS6 (SYSTEM_VERSION >= 6.0 && SYSTEM_VERSION < 7)
#define YC_IS_IOS7 (SYSTEM_VERSION >= 7.0 && SYSTEM_VERSION < 8.0)
#define YC_IS_IOS8 (SYSTEM_VERSION >= 8.0 && SYSTEM_VERSION < 9.0)
#define YC_IS_IOS9 (SYSTEM_VERSION >= 9.0 && SYSTEM_VERSION < 10.0)

/** 设备判断 */
#define YC_IS_IPHONE [[UIDevice currentDevice] userInterfaceIdiom] == UIUserInterfaceIdiomPhone
#define YC_IS_PAD (UI_USER_INTERFACE_IDIOM() == UIUserInterfaceIdiomPad)

/** iPhone的型号 */
#define YC_IS_IPHONE4 ([[UIScreen mainScreen] bounds].size.height == 480)
#define YC_IS_IPHONE5 ([[UIScreen mainScreen] bounds].size.height == 568)
#define YC_IS_IPHONE6 ([[UIScreen mainScreen] bounds].size.height == 667)
#define YC_IS_IPHONE6_PLUS ([[UIScreen mainScreen] bounds].size.height == 736)

/** 系统的版本号 */
#define YC_SYSTEM_VERSION [[[UIDevice currentDevice] systemVersion] floatValue]

/** APP版本号 */
#define YC_APP_VERSION  [[[NSBundle mainBundle] infoDictionary] objectForKey:@"CFBundleShortVersionString"]

/** APP BUILD 版本号 */
#define YC_APP_BUILD_VERSION  [[[NSBundle mainBundle] infoDictionary] objectForKey:@"CFBundleVersion"]

/** APP名字 */
#define YC_APP_DISPLAY_NAME  [[NSBundle mainBundle] objectForInfoDictionaryKey:@"CFBundleDisplayName"]

/** 当前语言 */
#define YC_LOCAL_LANGUAGE [[NSLocale currentLocale] objectForKey:NSLocaleLanguageCode]

/** 当前国家 */
#define YC_LOCAL_COUNTRY [[NSLocale currentLocale] objectForKey:NSLocaleCountryCode]

/** 当前使用Xcode iPhone OS SDK 的版本 */
#if __IPHONE_OS_VERSION_MAX_ALLOWED > __IPHONE_8_0
NSLog(@"当前使用Xcode iPhone OS SDK 8.0 以后版本的处理");
#else
NSLog(@"当前使用Xcode iPhone OS SDK 8.0 之前版本的处理");
#endif


/** 判断设备室真机还是模拟器 */
#if TARGET_OS_IPHONE
#endif

#if TARGET_IPHONE_SIMULATOR
#endif

/** 判断系统为64位还是32位 */
#if __LP64__
NSLog(@"64");
#else
NSLog(@"32");
#endif

<br/>

/** 字体大小 */
#define YC_FONT(NAME,FONTSIZE) [UIFont fontWithName:(NAME) size:(FONTSIZE)]
#define YC_S_FONT(FONTSIZE)    [UIFont systemFontOfSize:FONTSIZE]
#define YC_S_BOLD_FONT(FONTSIZE)   [UIFont boldSystemFontOfSize:FONTSIZE]


/** 颜色(RGB) */
#define YC_RGB(r,g,b)  [UIColor colorWithRed:(r)/255.0f green:(g)/255.0f blue:(b)/255.0f alpha:1];
#define YC_RGBA(r,g,b,a)   [UIColor colorWithRed:(r)/255.0f green:(g)/255.0f blue:(b)/255.0f alpha:(a)]

/** 颜色(0xFFFFFF) */
#define YC_HEX_RGB(rgbValue) [UIColor colorWithRed:((float)((rgbValue & 0xFF0000) >> 16))/255.0 green:((float)((rgbValue & 0xFF00) >> 8))/255.0 blue:((float)(rgbValue & 0xFF))/255.0 alpha:1.0]
#define YC_HEX_RGBA(rgbValue,a) [UIColor colorWithRed:((float)((rgbValue & 0xFF0000) >> 16))/255.0 green:((float)((rgbValue & 0xFF00) >> 8))/255.0 blue:((float)(rgbValue & 0xFF))/255.0 alpha:(a)]


/** 资源路径 */
#define YC_PNG_PATH(NAME) [[NSBundle mainBundle] pathForResource:[NSString stringWithUTF8String:NAME] ofType:@"png"]
#define YC_JPG_PATH(NAME) [[NSBundle mainBundle] pathForResource:[NSString stringWithUTF8String:NAME] ofType:@"jpg"]
#define YC_PATH(NAME,EXT) [[NSBundle mainBundle] pathForResource:(NAME) ofType:(EXT)]

/** 加载图片 */
#define YC_PNG_IMAGE_FILE(NAME)         [UIImage imageWithContentsOfFile:[[NSBundle mainBundle] pathForResource:(NAME) ofType:@"png"]]
#define YC_JPG_IMAGE_FILE(NAME)         [UIImage imageWithContentsOfFile:[[NSBundle mainBundle] pathForResource:(NAME) ofType:@"jpg"]]
#define YC_IMAGE_FILE(NAME,EXT)        [UIImage imageWithContentsOfFile:[[NSBundle mainBundle] pathForResource:(NAME) ofType:(EXT)]]
#define YC_IMAGE_NAMED(NAME)       [UIImage imageNamed:NAME]
