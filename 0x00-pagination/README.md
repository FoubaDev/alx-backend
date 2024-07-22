# 0x00. Pagination
In this project, I learned :

* How to paginate a dataset with simple page and page_size parameters
* How to paginate a dataset with hypermedia metadata
* How to paginate in a deletion-resilient manner



## Function Prototypes :

Prototypes for functions written in this project:

| File                    | Prototype                             |
| ----------------------- | ------------------------------------- |
| `0-simple_helper_function.py`        |                        |
| `1-simple_pagination.py`            |                                       |
| `2-hypermedia_pagination.py`        |                        |
| `3-hypermedia_del_pagination.py`        |                        |


## Tasks :

* **0. Simple helper function**
  * [0-simple_helper_function.py](./0-simple_helper_function.py): 
  Write a function named index_range that takes two integer arguments page and page_size.

The function should return a tuple of size two containing a start index and an end index corresponding to the range of indexes to return in a list for those particular pagination parameters.

Page numbers are 1-indexed, i.e. the first page is page 1.


* **1. Simple pagination**
  * [1-simple_pagination.py](./1-simple_pagination.py): 
 Copy index_range from the previous task and the following class into your code

* **2. Hypermedia pagination**
  * [2-hypermedia_pagination.py](./2-hypermedia_pagination.py):

 Replicate code from the previous task.

Implement a get_hyper method that takes the same arguments (and defaults) as get_page and returns a dictionary containing the following key-value pairs:

* __page_size__: the length of the returned dataset page
* __page: the__ current page number
* __data: the__ dataset page (equivalent to return from previous task)
* __next_page__: number of the next page, None if no next page
* __prev_page__: number of the previous page, None if no previous page
* __total_pages__: the total number of pages in the dataset as an integer
Make sure to reuse __get_page__ in your implementation.

You can use the __math__ module if necessary.


* **3. Deletion-resilient hypermedia pagination**
  * [3-hypermedia_del_pagination.py](./3-hypermedia_del_pagination.py):

 he goal here is that if between two queries, certain rows are removed from the dataset, the user does not miss items from dataset when changing page.