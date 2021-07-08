# HAT-P-41b two-limb retrievals posterior distributions(Espinoza & Jones, 2021)
-------------------

This repository stores posterior samples from the two-limb retrievals performed in Section 4.2 of [Espinoza & Jones (2021)](https://arxiv.org/abs/2106.15687). In particular:

- The file `hst_transit_fit_posterior.pkl` contains the posterior distribution of the fitted parameters to the HST transmission spectrum data of HAT-P-41b.

- The file `jwst_transit_fit_posterior.pkl` containts the same, but for the simulated JWST data.

- The file `jwst_limb_fit_posterior.pkl` contains the posterior distributions of the retrieval performed on the simulated _limb_ JWST data.

In addition, under the `data` folder, you can find the transit and limb spectra both from HST and simulated from JWST that were used in the paper to obtain the posteriors 
quoted above. 

## Extracting the samples

To extract the samples for, e.g., the HST data, you can do the following:

    import pickle
    data = pickle.load(open('hst_transit_fit_posterior.pkl', 'rb'), encoding='latin1')

    samples = data[:,:-1]

This will provide an array, `samples`, of length `(nsamples, parameters)`, where `nsamples` is 
the number of samples from the posterior, and `parameters` is the number of parameters in the 
given retrieval. The parameters (in the same order as they are in the array) are:

1. Irradiation temperature of the hot limb (K)
2. Log-10 metallicity.
3. Log-10 C/O ratio of the hot limb.
4. Log-Kzz of the hot limb.
5. fsed of the hot limb.
6. Log-10 cloud-base pressure of the hot limb.
7. Log-10 cloud VMR of the hot limb.
8. Factor multiplying the fiducial 10-bar radius.
9. T/P profile IR opacity.
10. Log visual-to-IR opacity.
11. Irradiation temperature of the cold limb.
12. Log-10 C/O ratio of the cold limb.
13. Log-Kzz of the cold limb.
14. fsed of the cold limb.
15. Log-10 cloud-base pressure of the cold limb.
16. Log-10 cloud VMR of the cold limb.


