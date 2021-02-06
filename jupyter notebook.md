# Jupyter Notebook

## 1. Set/Change Password

1. `$ python`
2. `>>> from notebook.auth import passwd`
3. `>>> passwd()`
4. `Enter password:`
5. `Verify password:`
6. `'sha1:a49da6d9c13c:27789bc3865c752e54ca0e339ceb6150bda97b0d'`
7. `^D` to quit python
8. `jupyter notebook --generate-config` if you do not have a config file, or
9. `$ vim ~/.jupyter/jupyter_notebook_config.py`
10. find `c.NotebookApp.password`, replace with `sha1:xxx` in step 6
11. `:wq` to save 
12. restart jupyter
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzk1NjUwNjQ3LDQ3ODQyMjU5MCwyNzk0NT
U3OTRdfQ==
-->