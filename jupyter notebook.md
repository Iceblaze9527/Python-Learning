# Jupyter Notebook

## 1. Set/Change Password

1. `$ python`
2. `>>> from notebook.auth import passwd`
3. `>>> passwd()`
4. `Enter password:`
5. `Verify password:`
6. `'sha1:a49da6d9c13c:27789bc3865c752e54ca0e339ceb6150bda97b0d'`
7. `^D` to quit python
8. `$ vim ~/.jupyter/jupyter_notebook_config.py`
9. find `c.NotebookApp.password`, replace with `sha1:xxx` in step 6
10. `:wq` to save 
11. restart jupyter
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjc5NDU1Nzk0XX0=
-->