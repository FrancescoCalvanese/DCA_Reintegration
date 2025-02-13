# Running the Reintegration Procedure from Terminal Using adabmDCA

## About adabmDCA
[adabmDCA](https://www.biorxiv.org/content/10.1101/2025.01.31.635874v1) is the primary package designed for training Direct Coupling Analysis (DCA) generative models and generating artificial protein/RNA designs. 
Detailed instructions on operating the package can be found in the [documentation]([#](https://spqb.github.io/adabmDCApy/)). This guide explains how to use adabmDCA to train a reintegrated bmDCA model.

## Command Syntax
To run the training of a reintegrated DCA model, use the following command:

```bash
adabmDCA reintegrate -d Nat_MSA -o output_folder --reint Reint_MSA --adj ADJ_vector --lambda lambda_value --alphabet 'proteins'
```

## Parameters
- **`-d Nat_MSA`**: The multiple sequence alignment (MSA) file of the reintegration dataset.
- **`-o output_folder`**: The directory where the output files will be stored.
- **`--reint Reint_MSA`**: The reintegration MSA file.
- **`--adj ADJ_vector`**: A text file containing experimental results for the reintegration dataset. Each line of the file should contain `+1` or `-1`, where the i-th line corresponds to:
  - `1` if the i-th sequence of the `Reint_MSA` passes the experimental test.
  - `-1` if the i-th sequence does not pass the experimental test.
- **`--lambda lambda_value`**: Sets the reintegration strength. A value of `1` has been observed to yield consistently good results.
- **`--alphabet 'proteins' or 'rna'`**: Specifies whether the dataset corresponds to RNA or proteins.

It is possible to use continuous values from `-1` to `1` for the `ADJ_vector`, depending on the performance of the sequence in the experiment. Additionally, the `lambda` parameter can be fine-tuned to adjust the reintegration strength. If unsure, a good starting point is to use `lambda = 1` and `±1` values for the `ADJ_vector`.

## Additional Configuration
These options are specific to the reintegration process. However, all other standard **DCA model parameters** can be adjusted using the general adabmDCA options available in the [documentation](https://spqb.github.io/adabmDCApy/).

For more details on the methodology, refer to the main associated [publications](#).

---
If you encounter any issues, please check the documentation or open an issue in the repository.

