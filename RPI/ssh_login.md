<head><h1>ssh 자동 로그인 방법</h1></head>
<body>
<h2>Client computer에서 할 것.</h2>
<ul>
$ cd ~ <br/>
$ mv .ssh .ssh.bak  (.ssh가 존재 한다면) <br/>
// ssh key 생성하기. <br/>
$ ssh-keygen -t rsa (엔터 계속쳐서 추가할 요소들 스킵)<br/>
// id_rsa는 private key, id_rsa.pub는 public key<br/>
// (private key가 있는 컴퓨터는 public key에 로그인 자동 로그인 가능)<br/>
$ cd .ssh<br/>
$ cat id_rsa.pub<br/>
// public key 내용 복사해두기<br/>
</ul>


<h2>Server Computer에서 할 것.</h2>

<ul>
$ cd .ssh<br/>
$ vim authorized_keys<br/>
// Client computer에서 만든 id_rsa.pub 내용을 autorized_keys에 붙여넣고 저장.<br/>
</ul>

>원리: <br/>
>client 컴퓨터의 rsa는 열쇠, rsa_pub는 자물쇠 역할.<br/>
>isa_pub을 server 컴퓨터에 걸어놓기위해 authorized_keys 사용.<br/> 
</body>
