# Flock
To Accelerate Decentralised AI
 Website: https://www.flock.io/
 Discord: https://discord.gg/7eF2nzzK
 Twitter: https://x.com/flock_io
  Guide dev: https://docs.flock.io/flock-product/ai-arena

##################SETUP NODE VALIDATOR#####################
# Install WSL with ubuntu22 on Windows:
wsl.exe --install

# Install adacona on WLS
wget https://repo.anaconda.com/archive/Anaconda3-2024.06-1-Linux-x86_64.sh
bash Anaconda3-2024.06-1-Linux-x86_64
bash Anaconda3-latest-Linux-x86_64.sh
source ~/anaconda3/bin/activate
conda update conda
source ~/.bashrc
conda --version

# Install python3 && pip
sudo apt install python3
python --version
sudo apt install python3-pip

# Install node:
git clone https://github.com/FLock-io/llm-loss-validator.git
conda create -n llm-loss-validator python==3.12.4
conda activate llm-loss-validator
cd /llm-loss-validator/
pip install -r requirements.txt

# Create new token:
- Website: https://huggingface.co/
=> Setting -> Access Token:
Get your_hf_token (1)

# Stake FML token and get API:
 https://train.flock.io/flock_api
 Chose tab TranningNode or Validator
 Select a task you want to validate Task ID (2)
 Minimum Stake: 50FML
 Get API (3)


# Run validator node:
cd /src/
CUDA_VISIBLE_DEVICES=0 \
bash start.sh \
--hf_token your_hf_token (1) \
--flock_api_key your_flock_api_key (3) \
--task_id your_task_id (2) \
--validation_args_file validation_config.json.example \
--auto_clean_cache False \
--lora_only True

