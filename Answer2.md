## �y���Q�z�������킹

### �����L���O��ʂ̊m�F

* �����L���O��ʂ��m�F���܂��傤
 * �A�v���Łu�����L���O������v���^�b�v����ƈȉ��̂悤�Ƀ����L���O���\������܂�

![ans2-1](/readme-img/ans2-1.png)

* ��}�͂P��V�񂾏ꍇ�̗�ł��B������V��ŁA�����L���O���\������邱�Ƃ��m�F���܂��傤�I

### �R�[�h�̓������킹

![Xcode](/readme-img/Xcode.png)

* �͔͉𓚂͈ȉ��ł�

```swift
// **********�y���Q�z�����L���O��\�����悤�I**********
// GameScore�N���X����������N�G�����쐬
let query = NCMBQuery(className: "GameScore")
// score�̍~���Ńf�[�^���擾����悤�ɐݒ肷��
query.addDescendingOrder("score")
// ����������ݒ�
query.limit = Int32(searchNum)
// �f�[�^�X�g�A������
query.findObjectsInBackgroundWithBlock { (objects: [AnyObject]!, error: NSError!) -> Void in
    if error != nil {
        // �����Ɏ��s�����ꍇ�̏���
        print("�����Ɏ��s���܂����B�G���[�R�[�h�F\(error.code)")
    } else {
        // �����ɐ��������ꍇ�̏���
        print("�����ɐ������܂����B")
        // �I�u�W�F�N�g����K�v��name��score�̒l�����o��
        var i = 0
        for object in objects {
            arrayNameData[i] = object.objectForKey("name")
            arrayScoreData[i] = object.objectForKey("score")
            i += 1
        }
    }
    // �擾�������O�ƃX�R�A��AppDelegate�̃t�B�[���h�l�ɐݒ�
    let appDelegate = UIApplication.sharedApplication().delegate as! AppDelegate
    appDelegate.nameData = arrayNameData
    appDelegate.scoreData = arrayScoreData
    // �����L���O��ʂɑJ��
    self.performSegueWithIdentifier("toLanking", sender: self)
}
// **************************************************
```
