## �y���P�z�������킹

### �j�t�e�B�N���E�hmobile backend��ł̊m�F
![mBaaS](/readme-img/mBaaS.png)

* �ۑ����ꂽ�f�[�^���m�F���܂��傤
 * �u�f�[�^�X�g�A�v���N���b�N����ƁA�u`GameScore`�v�N���X�Ƀf�[�^���o�^����Ă��邱�Ƃ��m�F�ł��܂��B

![ans1-1](/readme-img/ans1-1.png)

* ��}�̓X�R�A��35�A�łŖ��O���u�����������v�Ƃ����ꍇ�̗�ł��B

### �R�[�h�̓������킹

![Xcode](/readme-img/Xcode.png)

* �͔͉𓚂͈ȉ��ł�

```swift
// **********�y���P�z���O�ƃX�R�A��ۑ����悤�I**********
// �ۑ���N���X���쐬
let obj = NCMBObject(className: "GameScore")
// �l��ݒ�
obj.setObject(name, forKey: "name")
obj.setObject(score, forKey: "score")
// �ۑ������{
obj.saveInBackgroundWithBlock{(error: NSError!) -> Void in 
    if (error != nil) {
        // �ۑ��Ɏ��s�����ꍇ�̏���
        print("�ۑ��Ɏ��s���܂����B�G���[�R�[�h:\(error.code)")
    }else{
        // �ۑ��ɐ��������ꍇ�̏���
        print("�ۑ��ɐ������܂����BobjectId:\(obj.objectId)")
    }
}
// **************************************************
```
