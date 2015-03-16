# contamination_checker
checks for contamination

Often labs work with many samples. Contamination of samples is a serious problem. It takes a very small amount of one sample to contaminate another.

When users of the lab have sequenced their samples, they are expected to submit their sequences to a repository, so others can use that to check for contamination.

This tool was built to assist with the process of checking for contamination.

The basic program flow is:
- Read user data
- Walk over data directory of all know sequences.
- Perform GLOBAL alignment using mafft. --> output to file.
- Calculate hamming distance score for the alignment.

The output is a sorted list of the lowest 10 Hamming distance scores, along with the associated sequence ID and file location.


Notes:

Performance
As there are potentially many global alignments which all need to be performed, this task may take some time.
In an effort to speed this up, we tried creating a ramdisk, and used to write the alignments to. 

