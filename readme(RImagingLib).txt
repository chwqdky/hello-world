定义：
#define DLLEXPORT extern "C"  __declspec(dllexport)
导出消息：
#define WM_MSG  (WM_USER+101)
        第三个参数WPARAM指示处理是否完成，
        第四个参数LPARAM指示处理的进度；
导出函数原型：
DLLEXPORT int __stdcall RD_HRRP(HWND hWnd, complex<double> dataSrc[],
	double freqStart, double freqStop, int nk, 
	complex<double>  dataRes[],
	double drStart, double drStop, int nPt);
函数功能：一维距离成像（HRRP）
参数说明：hWnd--调用窗口句柄，可以是NULL；
          dataSrc--原始扫频RCS数据（对应电压信号的复数形式）；
          freqStart--起始频率，单位（GHz）；
          freqStop--终止频率，单位（GHz）；
          nk--频率点数；
          dataRes--转换后的数据，即一维像数据（对应RCS方根的复数形式）；
          drStart--像数据横坐标起始，单位（m）；
          drStop--像数据横坐标终止，单位（m）；
          nPt--像数据点数；

DLLEXPORT int __stdcall RD_ISAR_BP(HWND hWnd, complex<double> ** dataSrc,
	double azimStart, double azimStop, int np,
	double freqStart, double freqStop, int nk,
	double bisAngle,
	int iWnd,
	complex<double> ** dataRes,
	double xrStart, double xrStop, int nx,
	double drStart, double drStop, int ny);
函数功能：二维转台成像（滤波-逆touyingf）
参数说明：hWnd--调用窗口句柄，可以是NULL；
          dataSrc--原始扫频RCS数据（对应电压信号的复数形式）；
          azimStart--起始角度，单位（度）；
          azimStop--终止角度，单位（度）；
          np--角度点数；
          freqStart--起始频率，单位（GHz）；
          freqStop--终止频率，单位（GHz）；
          nk--频率点数；
          bisAngle--数据获取时雷达的双站角，单位（度）；
          iWnd--窗函数类型，0矩形窗，1汉明窗，2布莱克曼窗；
          dataRes--转换后的数据，即一维像数据（对应RCS方根的复数形式）；
          xrStart--二维像横坐标起始，单位（m）；
          xrStop--二维像横坐标终止，单位（m）；
          nx--横坐标点数；
          drStart--二维像径向坐标起始，单位（m）；
          drStop--二维像径向坐标起始，单位（m）；
          ny--纵坐标点数；

DLLEXPORT int __stdcall GetOptimalDrBinNumber(double freqStart, double freqStop,
	double drStart, double drStop, int nPt);
函数功能：获取距离向最佳颗粒度大小
参数说明：按径向距离确定最优细化颗粒度
freqStart--起始频率，单位（GHz）；
freqStop--终止频率，单位（GHz）；
drStart--像数据横坐标起始，单位（m）；
drStop--像数据横坐标终止，单位（m）；
nPt--初始径向坐标点数；
