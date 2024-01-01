# FBTools
Facebook Automation Tools  
>Python 3.10 - 3.12   
<br>  
<br>

## Installation
```python
pip install FBTools
```
<br>  
<br>  
<br>

## Create Account
```python
from FBTools.CreateAccount import CreateAccount

name = 'Input Your Name Here'
password = 'Input Your Password Here'
birthday = '25/12/1995' # DD/MM/YYYY
email = 'examplename@example.com'
gender = 1 # 1=Male, 0=Female
CA = CreateAccount()
CA.SetData(name=name, password=password, birthday=birthday, email=email, gender=gender)
CA.Create()
```
Parameter  
>name : Name You Want To Create (string, default=None)  
password : Password You Want To Create (string, default=None)  
birthday : Birth Date You Want To Set (string, default=None)  
email : Email You Want To Register (string, default=None)  
phone : Phone You Want To Register (string, default=None)  
gender : Gender You Want To Set (bool, default=0 -> female)  
<br>  
<br>  
<br>

## Login

#### Parameter
```python
cookie   = 'datr=nxbaxnynx; sb=axn...' # Input Your Cookie Here
email    = 'dapuntaxayonara@gmail.com' # Input Your Email Here
phone    = '6282245780524'             # Input Your Phone Here
password = 'satusampaidelapan'         # Input Your Password Here
```

#### Login With Cookie
```python
from FBTools import Start
FB = Start(cookie=cookie)
```

#### Login With Email & Password
```python
from FBTools import Start
FB = Start(email=email, password=password)
```

#### Login With Phone & Password
```python
from FBTools import Start
FB = Start(phone=phone, password=password)
```
<br>  
<br>  
<br>

## Get Access Token

#### Parameter
```python
# Must Be Included
cookie  = 'Input Your Cookie Here'       # Cookie (string, default=None)
```

### Token
```python
from FBTools import Start
FB = Start(cookie=cookie)

TokenEAAG = FB.TokenEAAG()
TokenEAAB = FB.TokenEAAB()
TokenEAAD = FB.TokenEAAD()
TokenEAAC = FB.TokenEAAC()
TokenEAAF = FB.TokenEAAF()
TokenEABB = FB.TokenEABB()
```
<br>  
<br>  
<br>

## Get Info Account, Page, Group

#### Parameter
```python
# Must Be Included
cookie  = 'Input Your Cookie Here'       # Cookie (string, default=None)
profile = 'Input ID Profile Here'        # ID/URL Profile Target (string, default=False)
page    = 'Input ID Page Here'           # ID/URL Page Target (string, default=False)
group   = 'Input ID Group Here'          # ID/URL Group Target (string, default=False)
```

#### Get Info Profile
```python
from FBTools import Start
FB = Start(cookie=cookie)

Info = FB.GetInfoProfile(profile)
print(Info.id)
print(Info.username)
print(Info.name)
print(Info.short_name)
print(Info.gender)
print(Info.work)
print(Info.education)
print(Info.current_city)
print(Info.hometown)
print(Info.relationship)
print(Info.birthday)
print(Info.language)
print(Info.website)
print(Info.github)
print(Info.instagram)
print(Info.friend)
print(Info.follower)
```
<br>  
<br>  
<br>

## Auto Post

#### Parameter
```python
# Must Be Included
cookie  = 'Input Your Cookie Here'                           # Cookie (string, default=None)
text    = 'Hello! Test Bot Post'                             # Caption (string, default=None)
group   = '1824553201274304'                                 # Group ID (string, default=None)
# 'group' must include if post to group
# You must post at least 1 text or 1 photo

# Optional
url     = ['https://e.top4top.io/p_2916o42201.jpg']          # Picture URL (list, default=None)
tag     = ['1827084332','100000415317575','100000200420913'] # Friend ID You Want To Tag (list, default=None)
privacy = 1 # 1=Public, 2=Friends, 3=OnlyMe                  # Post Privacy (int, default=None)
```

#### Post To Feed
```python
from FBTools import Start

FB = Start(cookie=cookie)
Post = FB.PostToFeed(text=text, url=url, tag=tag, privacy=privacy)
```

#### Post To Group
```python
from FBTools import Start

FB = Start(cookie=cookie)
Post = FB.PostToGroup(group=group, text=text, url=url, tag=tag, privacy=privacy)
```

#### Return
```python
{'status':'success','id':idpost,'message':None}
{'status':'pending','id':idpost,'message':'Pending Post'}
{'status':'failed','id':None,'message':'cookie invalid'}
{'status':'failed','id':None,'message':"Don't Create Same/Duplicate Post"}
{'status':'failed','id':None,'message':'Your Account Restricted To Post In Group'}
{'status':'failed','id':None,'message':'Terjadi Kesalahan'}
```
<br>  
<br>  
<br>

## Auto Comment

#### Parameter
```python
# Must Be Included
cookie = 'Input Your Cookie Here'                           # Cookie (string, default=None)
post   = 'Facebook.com/6929777330379375'                    # ID/URL Post Target (string, default=None)
text   = 'Hello! Test Bot Comment'                          # Caption (string, default=None)
# You must comment at least 1 text or 1 photo

# Optional
photo  = 'https://e.top4top.io/p_2916o42201.jpg'            # Picture URL (string, default=None)
tag    = ['1827084332','100000415317575','100000200420913'] # Friend ID You Want To Tag (list, default=None)
```

#### Comment To Post
```python
from FBTools import Start

FB = Start(cookie=cookie)
Comment = FB.CommentToPost(post=post, text=text, photo=photo, tag=tag)
```

#### Return
```python
{'status':'success','id':comment_id,'message':None}
{'status':'failed','id':None,'message':'cookie invalid'}
{'status':'failed','id':None,'message':'Spam Or Something Else'}
{'status':'failed','id':None,'message':'Terjadi Kesalahan'}
```
<br>  
<br>  
<br>

## Auto React

#### Parameter
```python
# Must Be Included
cookie = 'Input Your Cookie Here'                                   # Cookie (string, default=None)
post   = 'Facebook.com/6929777330379375'                            # ID/URL Post Target (string, default=None)
react  = 5 # 1=Like, 2=Love, 3=Haha, 4=Wow, 5=Care, 6=Sad, 7=Angry  # Reaction Type (int, default=2=Love)
```

#### React To Post
```python
from FBTools import Start

FB = Start(cookie=cookie)
Reaction = FB.ReactToPost(post=post, react=react)
```

#### Return
```python
{'status':'success','react_type':react_type,'message':None}
{'status':'failed','react_type':react_type,'message':'Spam Or Something Else'}
{'status':'failed','react_type':react_type,'message':'Terjadi Kesalahan'}
```
<br>  
<br>  
<br>

## Auto Share

#### Parameter
```python
# Must Be Included
cookie  = 'Input Your Cookie Here'                           # Cookie (string, default=None)
post    = 'Facebook.com/6929777330379375'                    # ID/URL Post You Want To Share (string, default=None)
group   = '1824553201274304'                                 # Group ID (string, default=None)
# 'group' must include if share to group

# Optional
text    = 'Hello! Test Bot Share'                            # Caption (string, default=None)
tag     = ['1827084332','100000415317575','100000200420913'] # Friend ID You Want To Tag (list, default=None)
privacy = 1 # 1=Public, 2=Friends, 3=OnlyMe                  # Share Privacy (int, default=None)
```

#### Share To Feed
```python
from FBTools import Start

FB = Start(cookie=cookie)
Share = FB.ShareToFeed(post=post, text=text, tag=tag, privacy=privacy)
```

#### Share To Group
```python
from FBTools import Start

FB = Start(cookie=cookie)
Share = FB.ShareToGroup(post=post, group=group, text=text, tag=tag, privacy=privacy)
```

#### Return
```python
{'status':'success','id':idshare,'message':None}
{'status':'pending','id':idshare,'message':'Pending Post'}
{'status':'failed','id':None,'message':"Don't Create Same/Duplicate Post"}
{'status':'failed','id':None,'message':'post has been deleted or there is an error'}
{'status':'failed','id':None,'message':'Your Account Restricted To Post In Group'}
{'status':'failed','id':None,'message':'Terjadi Kesalahan'}
```
<br>  
<br>  
<br>

