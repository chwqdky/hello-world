���壺
#define DLLEXPORT extern "C"  __declspec(dllexport)
������Ϣ��
#define WM_MSG  (WM_USER+101)
        ����������WPARAMָʾ�����Ƿ���ɣ�
        ���ĸ�����LPARAMָʾ����Ľ��ȣ�
��������ԭ�ͣ�
DLLEXPORT int __stdcall RD_HRRP(HWND hWnd, complex<double> dataSrc[],
	double freqStart, double freqStop, int nk, 
	complex<double>  dataRes[],
	double drStart, double drStop, int nPt);
�������ܣ�һά�������HRRP��
����˵����hWnd--���ô��ھ����������NULL��
          dataSrc--ԭʼɨƵRCS���ݣ���Ӧ��ѹ�źŵĸ�����ʽ����
          freqStart--��ʼƵ�ʣ���λ��GHz����
          freqStop--��ֹƵ�ʣ���λ��GHz����
          nk--Ƶ�ʵ�����
          dataRes--ת��������ݣ���һά�����ݣ���ӦRCS�����ĸ�����ʽ����
          drStart--�����ݺ�������ʼ����λ��m����
          drStop--�����ݺ�������ֹ����λ��m����
          nPt--�����ݵ�����

DLLEXPORT int __stdcall RD_ISAR_BP(HWND hWnd, complex<double> ** dataSrc,
	double azimStart, double azimStop, int np,
	double freqStart, double freqStop, int nk,
	double bisAngle,
	int iWnd,
	complex<double> ** dataRes,
	double xrStart, double xrStop, int nx,
	double drStart, double drStop, int ny);
�������ܣ���άת̨�����˲�-��touyingf��
����˵����hWnd--���ô��ھ����������NULL��
          dataSrc--ԭʼɨƵRCS���ݣ���Ӧ��ѹ�źŵĸ�����ʽ����
          azimStart--��ʼ�Ƕȣ���λ���ȣ���
          azimStop--��ֹ�Ƕȣ���λ���ȣ���
          np--�Ƕȵ�����
          freqStart--��ʼƵ�ʣ���λ��GHz����
          freqStop--��ֹƵ�ʣ���λ��GHz����
          nk--Ƶ�ʵ�����
          bisAngle--���ݻ�ȡʱ�״��˫վ�ǣ���λ���ȣ���
          iWnd--���������ͣ�0���δ���1��������2������������
          dataRes--ת��������ݣ���һά�����ݣ���ӦRCS�����ĸ�����ʽ����
          xrStart--��ά���������ʼ����λ��m����
          xrStop--��ά���������ֹ����λ��m����
          nx--�����������
          drStart--��ά����������ʼ����λ��m����
          drStop--��ά����������ʼ����λ��m����
          ny--�����������

DLLEXPORT int __stdcall GetOptimalDrBinNumber(double freqStart, double freqStop,
	double drStart, double drStop, int nPt);
�������ܣ���ȡ��������ѿ����ȴ�С
����˵�������������ȷ������ϸ��������
freqStart--��ʼƵ�ʣ���λ��GHz����
freqStop--��ֹƵ�ʣ���λ��GHz����
drStart--�����ݺ�������ʼ����λ��m����
drStop--�����ݺ�������ֹ����λ��m����
nPt--��ʼ�������������
