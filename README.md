### To Noor:
After cloning the repo, please do the following:

1. Open a terminal
2. Navigate to the repo folder `cd /path/to/this/repo`
3. Install the dependencies `pip install -r requirements.txt`
4. Download the model from [here](https://drive.google.com/file/d/1SbSArI3KOOWHxRlxnjchO7_MbWzB4lNR/view?usp=sharing) and put it in the `pretrained` folder.
5. Check for the number of CPU cores in your machine, by running `nproc` in the terminal.
6. In `run_wsi.sh`, change the `nr_inference_workers` and `nr_post_proc_workers` to the number of CPU cores in your machine (or less), you got from the previous step.
7. In `run_wsi.sh`, change the `input_dir` to the path of the folder containing the WSI images.
8. By default, the output will be saved in the `preds` folder. You can change this in `run_wsi.sh` by changing the `output_dir` variable.
9. By default, a `cache` folder will be created in the repo folder and will contain the intermediate results. It will be deleted after the script finishes. It requires a lot of space, so make sure you have enough space in your machine (at least 100 GB).
10. Run the script `./run_wsi.sh`.

### Errors:

If you get an error like this:
```Out of memory. Tried to allocate 20.00 MiB (GPU 0; 10.76 GiB total capacity; 9.78 GiB already allocated; 4.94 MiB free; 9.79 GiB reserved in total by PyTorch)```

Then you need to reduce the batch size in `run_wsi.sh` by changing the `batch_size` variable.