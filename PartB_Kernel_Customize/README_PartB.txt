Part B is Jupyter Kernel Customization on JupyterHub: http://jupyter.nersc.gov.

The notebook follows the instruction from NERSC Website (https://docs.nersc.gov/connect/jupyter/) or the training documents 'Python-and-Jupyter-New-User-Training-2019-06-21.pdf', which is in the same folder. The commands from these two sources are a little different, but both of them work.

There are three steps:

Step 1: Log in Jupyterhub;
Step 2: 
     2-1 Create Jupyter Kernel (Website)
     2-2 Create Jupyter Kernel (Training Documents)
     2-3 Select Kernel
Step 3: Set PATH and LD_LIBRARY _PATH;
Step 4: Test (Optional)

If you do not need to compile packages, you can stop after Step 2.

**For Jupyterhub-familiar-users:
You can see the website or the documents directly, which is clear and compact.

**For Jupyterhub-new-user:
Please check and set your own path carefully. The commands and kernel_name are for test case. You need to set them according to your
own case.

Tips: The home path '/global/homes/v/vthw28' and '/global/u1/v/vthw28' have the same files. So when you set PATH and LD_LIBRARY_PATH,
both of them are acceptable. Hope the corresponding part in the notebook 'PartA_2_Jupyter_Customize' will not cause confusion to you.

Also, if you find any problems about kernels, like kernel disappear or kernel import error or something like that. Here is possible
solution:

1. Activate the problemed kernel, for example: source activate kernel_doc_test;

2. Run the command: python -m ipykernel install --user --name kernel_doc_test --display-name "kernel_doc_test";

3. Restart the kernels and try again.

Hope it can solve your problems.
This is the end of 'README_PartB.txt'. Thank you for your reading and I will add something I missed once I realized that. And if you find any problems or have any advice about my commands or anything else, please contact me: hongsheng.wang@pnnl.gov.