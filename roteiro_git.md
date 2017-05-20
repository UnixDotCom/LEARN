# Comandos uteis

Comandos que salva a vida no dia a dia

## Blame

Mostra quem fez alterrações no arquivo roteiro.md
```sh
$ git pull
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:UnixDotCom/LEARN
   7ead0d8..3a12547  master     -> origin/master
Updating 7ead0d8..3a12547
Fast-forward
 roteiro.md | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)

$ git blame roteiro.md
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  1) # Initial
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  2)
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  3) Documentation related about to Initial environment aws
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  4)
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  5) (VPC)[http://docs.aws.amazon.com/cli/latest/reference/ec2/create-vpc.html]
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  6)
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  7) ## Network
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  8)
ba7862ae (Contributor 2017-05-20 14:25:43 -0300  9) VPC
ba7862ae (Contributor 2017-05-20 14:25:43 -0300 10)
ba7862ae (Contributor 2017-05-20 14:25:43 -0300 11) ```sh
ba7862ae (Contributor 2017-05-20 14:25:43 -0300 12) aws ec2 create-vpc --cidr-block 10.0.0.0/16
3a125476 (Owner                    2017-05-20 14:49:57 -0300 13) ```
3a125476 (Owner                    2017-05-20 14:49:57 -0300 14)
3a125476 (Owner                    2017-05-20 14:49:57 -0300 15) ## Subnets
```