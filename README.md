# Wandb_files_cleaning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1jmPd_KG95NGxE_nIJ1t8pX_69PnYx1Es?usp=sharing)

When trainning neural network with Wandb, saved weight can make you run out of disk space. This notebook allow you to reduce the number of saved weights automaticaly by only keeping the weight saved at each n epochs.

## How to use it?
When saving models' weights, you should add the epoch number to it's name. Ex: `1_net.pth` for the weights of a pytorch model trained at the first epoch.
1. Open the notebook in colab and connect to wandb if you never use it on Google colab.
2. Go the `To customise:` section and:
    1. If you have files not containing the epoch number, such as `latest_net.pth`, `best_net.pth` you can add there names in `SKIP_FILES` and they will be avoided.
    2. If you are not using the same name convension than me, you can update the `extract_epoch_number` to extract the epoch number of your file (Warning, ti must retrun an str to be compared to SKIP_FILES)
    3. Specify the project to clean with `PROJECT_NAME`
    4. Specify the extension the model files with `FILE_EXTENSION`
3. Run the 2 other cells, the files of files that will be deleted will be displayed. This will be a dry run (will not remove files on wandb), if your are hapy with the results, go to the next steps.
4. Re run the cell and modify `dry_run = True, verbos = True` by `dry_run = False, verbos = False` to remove the files from wandb.
