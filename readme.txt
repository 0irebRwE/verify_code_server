#verify_code_server  [https://github.com/duanyifei/verify_code_server.git]

verify_code_server  ���ڴһ����֤��ʶ��ķ���

֧����֤������
	1��http://shixin.court.gov.cn/image.jsp
	2��http://zhixing.court.gov.cn/search/security/jcaptcha.jpg

	

��֤��ʶ�����python��PILģ��

����ʹ��python��bottleģ��


�÷�:

��������:
	python code_server.py

�������:
```#coding:utf8
import urllib2
import urllib

def code(fd,ty=1):
    '''
    ���ͼƬ��֤��
    '''
    url = "http://localhost:8080/code"
    cod = open(fd,"rb").read()
    dat = {
        "code":cod,
        "type":ty,
        }
    data = urllib.urlencode(dat)
    req = urllib2.Request(url,data)
    resp = urllib2.urlopen(req,timeout=20)
    ma = resp.read()
    return ma

if __name__=="__main__":
    print code("./temp/1.jpg")
```
