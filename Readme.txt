git init
gpg --gen-key
gpg --list-secret-keys --keyid-format LONG

Вывод:
	sec   rsa2048/849B714F91A3D7DC 2020-03-27 [SC] [expires: 2022-03-27]
      		98BF91367C35742B84EA45AB849B714F91A3D7DC	
	uid                 [ultimate] Nikitin <nik.ant38@mail.ru>
	ssb   rsa2048/7BACF14F8EBEADCA 2020-03-27 [E] [expires: 2022-03-27]

git config --global user.signingkey "849B714F91A3D7DC"

touch Readme.txt
git add -A
git commit
git tad -s Test1
touch file1
git add -A
git commit
touch file2
git add -A
git commit

gpg --armor --export "849B714F91A3D7DC"

git remote add origin https://github.com/toshanik/Nikitin.git
git push -u origin master

touch KeyFriend.txt
nano KeyFriend.txt
gpg --import KeyFriend.txt

git tag -v Test1
git verify-commit cbc5227