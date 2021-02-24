# Ubuntu 
# Step 0
sudo apt update

sudo apt upgrade


# Step 1
sudo apt install cmake

sudo apt install build-essential

# Install new VulkanSDK: https://vulkan.lunarg.com/sdk/home#linux 

# Install VulkadSDK of current project
# Step 2
wget -qO - https://packages.lunarg.com/lunarg-signing-key-pub.asc | sudo apt-key add -

sudo wget -qO /etc/apt/sources.list.d/lunarg-vulkan-1.2.162-focal.list https://packages.lunarg.com/vulkan/1.2.162/lunarg-vulkan-1.2.162-focal.list

sudo apt update

sudo apt install vulkan-sdk
