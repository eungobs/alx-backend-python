0x00-pagination
This repository contains Python scripts that demonstrate various pagination techniques. Here's an overview of each script:

0-simple_helper_function.py
This script contains a simple helper function named index_range.
The function takes two integer arguments: page and page_size.
It returns a tuple of size two containing a start index and an end index corresponding to the range of indexes for pagination parameters.

1-simple_pagination.py
This script extends the functionality of index_range by implementing pagination for a dataset of popular baby names.
It includes a Server class with a get_page method that retrieves a specified page of the dataset based on pagination parameters.
The method takes two integer arguments: page (default value: 1) and page_size (default value: 10).
It returns a list of rows corresponding to the requested page of the dataset.
The script includes assertions to verify that input arguments are integers greater than 0.

2-hypermedia_pagination.py
This script builds upon the pagination functionality implemented in the previous script.
It introduces a get_hyper method in the Server class to provide hypermedia pagination capabilities.
The method returns a dictionary containing information about the dataset page, including page size, current page number, data, and links to the next and previous pages.
The script demonstrates hypermedia pagination by returning paginated data along with metadata for navigation.

3-hypermedia_del_pagination.py
This script enhances hypermedia pagination to handle deletion-resilient pagination.
It introduces a get_hyper_index method in the Server class to facilitate deletion-resilient pagination.
The method returns a dictionary with information about the dataset page, similar to the get_hyper method.
It ensures that users do not miss items from the dataset when rows are removed between queries by dynamically adjusting the index range.
Assertions are used to validate input arguments and handle out-of-range requests.

License
This project is licensed under the MIT License - see the LICENSE file for details.
