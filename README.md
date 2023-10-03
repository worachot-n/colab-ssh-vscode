# colab-ssh-vscode

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/worachot-n/colab-ssh-vscode/blob/main/colab_ssh_vscode.ipynb)

# [Youtube tutorial](https://www.youtube.com/watch?v=Q78_MMaNe_U&t=4s)

Credit:Wassim Benzarti

# Install colab_ssh on google colab

```
!pip install colab_ssh --upgrade --quiet
from colab_ssh import launch_ssh_cloudflared, init_git_cloudflared
```

# Set Password before set up cloudflared to your laptop

1. Download Cloudflared binary: cloudflared.exe from https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/install-and-setup/installation/

  For Window:

2. Move file to folder: 'C:\Users\\{laptop_name}\\.cloudflared\'

3. Open CMD/Terminal: Typing: 'notepad ./.ssh/config'

4. Edit file 'config'
```	
HostName %h
	User root
	Port 22
	ProxyCommand <PUT_THE_ABSOLUTE_CLOUDFLARE_PATH_HERE> access ssh --hostname %h'
```
Example
```	
HostName %h
	User root
	Port 22
	ProxyCommand C:\Users\{laptop_name}\.cloudflared access ssh --hostname %h'
```

5. Set Password: launch_ssh_cloudflared("12345678")

6. Github repository: repository_url="github repository link" "https://github.com/#######/vscode.git"

# Set github config you can push you code to github

init_git_cloudflared("https://github.com/######/vscode.git", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;personal_token="ghp_xxxxxxxxxxdfhcbgertfxxxxxxxxxxxad", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;branch="main", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;email="######@gmail.com", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;username="#######") <br>
         
# How to set personal_token

Go to this link:
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
