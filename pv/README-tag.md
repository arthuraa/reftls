# Experimenting with tagged composition

We compared the difference of verifying TLS 1.3 in isolation with verifying it
together with 1.2.  The results are shown in `results-13-tag.txt` and
`results-13-12-tag.txt`, respectively.  We ran the following command:

    proverif -lib tls-lib-tag.pvl tls12-tls13-tag.pv
    
The `lib` file was adapted from `tls-lib.pvl` to ensure that the two versions
use disjoint message formats, so that the type of composition is closer to what
is analyzed in Cryptis.  We also commented out the sanity queries in that file,
to speed up the time taken in the experiment.  The first experiment was run by
commenting out the 1.2 code from the `process` declaration.
