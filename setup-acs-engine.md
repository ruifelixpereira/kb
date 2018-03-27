## Setup acs-engine

```shell
mkdir acs-engine
cd acs_engine

wget https://github.com/Azure/acs-engine/releases/download/v0.12.0/acs-engine-v0.12.0-linux-amd64.tar.gz

tar xvzf acs-engine-v0.12.0-linux-amd64.tar.gz

cd acs-engine-v0.12.0-linux-amd64
mv * ..
cd ..
rm -rf acs-engine-v0.12.0-linux-amd64*
```

In the end you will have this:

![Setup 01](./media/setup-01.png)

Just add it to your path by adding this line in the end of your `.profile` file:

```
PATH="/home/rfp/dev/acs-engine:$PATH"
```

Execute `.profile` to reflect the changes:

```shell
 . .profile
```

Test it:

![Setup 02](./media/setup-02.png)
