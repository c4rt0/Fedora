## How To Install MongoDB in Fedora 35

### Step 1, Configure Repository

The MongoDB official team provides an Yum repository for installing MongoDB on a Fedora system. Create a new configuration file with Mongodb yum repository. Edit a file in a editor:

```bash
sudo nano /etc/yum.repos.d/mongodb.repo
```

Add the below content

```bash
[Mongodb]

name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/8/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
```

Save the file and close it.

### Step 2, Install MongoDB on Fedora

Lets use the DNF package manager to install the MongoDB server on the Fedora system. This will also install all required dependencies to your system. To install MongoDB on Fedora, type:

```bash
sudo dnf install mongodb-org mongodb-org-server
```

### Step 3, Start MongoDB Service

MongoDB server has been installed on your Fedora systems. Lets enable the MongoDB systemd service and start it.

```bash
sudo systemctl enable mongod.service
sudo systemctl start mongod.service
```

Once the service is started, check the current status with the following
command:

```bash
sudo systemctl status mongod.service
```

### Step 4, Connect to MongoDB Shell

Use the following command to check the installed MongoDB version

```bash
mongod --version
```

This command should return something like:

```bash
db version v4.4.4
Build Info: {
    "version": "4.4.4",
    "gitVersion": "8db30a63db1a9d84bdcad0c83369623f708e0397",
    "openSSLVersion": "OpenSSL 1.1.1l  FIPS 24 Aug 2021",
    "modules": [],
    "allocator": "tcmalloc",
    "environment": {
        "distmod": "rhel80",
        "distarch": "x86_64",
        "target_arch": "x86_64"
    }
}
```

Please keep in mind, the version will most likely be different.

<!-- ### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```bash
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/c4rt0/Fedora/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out. -->
