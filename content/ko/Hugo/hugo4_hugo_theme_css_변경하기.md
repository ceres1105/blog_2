---
title: "4. hugo theme css 변경하기"
date: 2020-06-29T12:43:33+09:00
type: docs
weight: 4
draft: false
description: >
    
---

> 전 포스팅에서 css를 바꾸기 위해서 theme를 fork 받은 후 사용하라고 얘기 했다. </br>
이번에 fork 받은 theme로 어떻게 css를 수정할 수 있는지 알아보자. 

요점은 변경된 css를 theme submoule로 push를 하고 deploy를 위해서 main repo에서 또 한번 push를 해야한다. 
### Flow 1
1. fork 한 docsy theme를 clone 받는다. `git remote -v`후 origin remote 주소가 fork 한 주소인지 확인한다.
2. clone 받은 theme에서 css를 변경한다.
3. docsy theme에서 git push 를 한다.
4. 로컬에서 바꾼 css를 보기위해 main repo에서 git pull
5. github.io에 deploy 하기위해 main repo 에서 git push를 한다.
그러면 git action이 작동하고, css를 변경한 dosy theme를 submodule 로 받아오면서 css가 적용된다.  

주의할점! main repo에 fork 한 theme주소가 submoulde로 등록이 되어있어야 한다.!

### Flow 2
따로 clone 받지 않고 main repo에서 모든 작업을 하는 방법이다. 
1. `cd main repo>theme>docsy` 에서 `remote -v` 를 통해 docsy 폴더의 origin remote가 fork 한 theme repo인지 확인한다. 
2. theme repo라면 css 변경한 후 theme repo에다 git push 하자 

아아아아아