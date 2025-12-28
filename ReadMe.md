[![Built with Devbox](https://www.jetify.com/img/devbox/shield_galaxy.svg)](https://www.jetify.com/devbox/docs/contributor-quickstart/)

# I) Configure WSL 
## 1) check if WSL is installed then it will prompt the default version and distro
    wsl --status
## 2) even if you have already a current wsl session, create another
    wsl --install -d Ubuntu --name "enter your user session name"
curl -fsSL https://get.jetify.com/devbox | bash
# II) Clone the project and enter into it
    git clone https://github.com/karimDevWM/OpenInfraX.git;cd OpenInfrax

# Create

# Run this command
devbox shell


# To create a local Angular project in the OpenInfraX project :
pnpm exec ng new frontend --routing --style=scss
# check local angular version
pnpm exec ng version

# To create Nestjs project in the OpenInfraX project :
pnpm exec nest new backend
# check local Nestjs version
pnpm exec nest --version
