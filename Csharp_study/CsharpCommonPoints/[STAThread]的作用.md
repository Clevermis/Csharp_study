# [STAThread]������

## [STAThread]
- STAThread��Single Thread Apartment Thread.(��һ�̵߳�Ԫ�߳�)
- []��������ʾAttributes��

## [STAThread]
	��һ���߳�ģ�ͣ����ڳ������ڷ����ϣ���C#��VB.NET����Main()��������
	��ָ����ǰ�̵߳�ApartmentState ��STA���������������ϲ�����Ӱ�졣
	��aspxҳ���Ͽ���ʹ��AspCompat = "true" ���ﵽͬ����Ч����
	�������ֻ�� Com Interop ���ã����ȫ���� managed code �����á�
	�򵥵�˵��:[STAThread]ָʾӦ�ó����Ĭ���߳�ģ���ǵ��̵߳�Ԫ (STA)��
	�����߳�ģ�Ϳ�����Ϊ���̵߳�Ԫ����̵߳�Ԫ��
	���δ����������ã�����̲߳�����ʼ����
	Ҳ����˵������õ�.NET Framework������û��ʹ��COM Interop��
	һ�㲻��Ҫ���Attribute�������Ļ���MTA�����߳��׼䣩��Free Thread�������̣߳���

## [STAThread] 
	attributeָʾӦ�ó���� COM �߳�ģ���ǵ��̵߳�Ԫ��
	���ڴ˶�Ӧ�Ķ��̵߳�Ԫ���� [MTAThread] �����̵߳�Ԫ�̣߳�

COM �߳�ģ��ֻ������ʹ�� COM interop ��Ӧ�ó��������������Ӧ�õ���ʹ�� COM interop ��Ӧ�ó��򣬽�û���κ�Ч����

COM �߳�ģ�Ϳ�����Ϊ���̵߳�Ԫ����̵߳�Ԫ�����Ӧ�ó����߳�ʵ�ʵ����� COM ��������Ϊ COM interop ��ʼ�����̡߳����û��ʹ�� COM interop���򲻳�ʼ�����߳�