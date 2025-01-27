### Common-crawl-processor
It's a pipeline to deal with web documents from Common Crawl. It selects documents from a pre-determined language, pre-processes them and removes samples with unwanted content. 

### Getting raw text out of Common Crawl dumps

We will be using the .wet files from Common Crawl. For more information on the WET format, please consult [...].

Note that processing Common Crawl files is a very intensive job. Please refer to the information we have compiled about benchmarking (here in the wiki) before launching your own jobs. At the same time, don't be shy: you can process small amounts of data on your laptop without problems. So give it a go, and find friends to collectively process *more* data!

Before you start, you will have to find the location of some .wet files to process. If you go to the Common Crawl website and look for monthly file listings, for instance [here](https://commoncrawl.s3.amazonaws.com/crawl-data/CC-MAIN-2020-50/index.html), you will find files named *wet.paths.gz*. If you uncompress one of those *wet.paths* file, you will get a list of URLs starting with *crawl-data...* Prepend *https://commoncrawl.s3.amazonaws.com/* to each line, and you will get a few tens of thousands of .wet files' URLs.


## Using the code

We recommend using a virtual environment. You can set it up from outside your clone repository, by doing:

     virtualenv common-crawl-processor

To process raw .wet files, do:

    python cc_process_wet.py --file=example-path-file.txt --lang=en
    
You should see the file being processed:

    1 documents processed 0 documents added...
    3 documents processed 0 documents added...
    383 documents processed 100 documents added...
    384 documents processed 100 documents added...
    385 documents processed 100 documents added...
    387 documents processed 100 documents added...
    768 documents processed 200 documents added...
