# temp_memo

検体はブラウザやPDFビューアーでは正常に開けなかった。

Chrome

![image](https://github.com/r1k0t3k1/temp_memo/assets/57973603/c49bc88d-14d4-49aa-b940-7ce46e77ff87)

PDF-Xchange Viewer

![image](https://github.com/r1k0t3k1/temp_memo/assets/57973603/ce0f3ba7-0450-4f06-b080-a4a461123f72)

Adobe Acrobat Reader

![image](https://github.com/r1k0t3k1/temp_memo/assets/57973603/bb36d856-4c3b-4128-b19a-6bb1eeb11cfa)

PDFは`%%EOF`がファイルの最後に付与されるが、検体には確認できなかった。
![image](https://github.com/r1k0t3k1/temp_memo/assets/57973603/6e484128-df7a-4dcc-b3bd-f066020a1d3e)

検体をもとにmaldoc in pdfを作成する。

```python
import zlib

first = b'%PDF-1.7\n%\xc2\xb5\xc2\xb6\r\n1 0 obj\n<</Type/Catalog/Pages 2 0 R>>\nendobj\r\n2 0 obj\n<</Type/Pages/Count 1/Kids[4 0 R]>>\nendobj\r\n3 0 obj\n<</Font<</helv 5 0 R>>>>\nendobj\r\n4 0 obj\n<</Type/Page/MediaBox[0 0 595 842]/Rotate 0/Resources 3 0 R/Parent 2 0 R/Contents[6 0 R]>>\nendobj\r\n5 0 obj\n<</Type/Font/Subtype/Type1/BaseFont/Helvetica/Encoding/WinAnsiEncoding>>\nendobj\r\n6 0 obj\n<</Length 149/Filter/FlateDecode>>\nstream\n'

last = b'\nendstream\nendobj\r\nxref\n0 7\n0000000000 00001 f \n0000000016 00000 n \n0000000062 00000 n \n0000000114 00000 n \n0000000155 00000 n \n0000000262 00000 n \n0000000351 00000 n \r\ntrailer\n<</Size 7/Root 1 0 R/ID[<E944B61540478E3627A352C982AC25EE><8BA250B05678D897FEB0B85A7161C0B1>]>>\nstartxref\n569\n%%EOF\n'

stream = b'\nq\nBT\n1 0 0 1 50 742 Tm\n/helv 11 Tf [<412064656c6976722e746f2050444620746573742066696c652e>]TJ\n0 -15.114 TD\n[<4f70656e20696e204d6963726f736f667420576f726420666f72206120646966666572656e742066696c6521>]TJ\nET\nQ\n'

print(first+zlib.compress(stream)+last)
```

PDFの見た目を決める
![image](https://github.com/r1k0t3k1/temp_memo/assets/57973603/4e958773-99cd-4543-b672-f286f78424e5)





