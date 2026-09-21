# DFT beta2 −0.03 student exercise

## Assignment

Complete the eight `TODO` functions in `DFT_beta2_-003_student_exercise.ipynb` and reproduce these three plots:

1. `frequency_time_pairing_beta2_-003_high_scale`
2. `peaks_linear_scale_onetoone_beta2_-003_high_scale`
3. `dft_statistics_beta2_-003_high_scale`

Reference PNG and SVG files are in `reference_plots/`. Save your results in `student_plots/`.

## How the references were generated

The complete instructor calculation identifies the high scale by the largest absolute measured voltage, computes statistics across 999 shots, converts the OSA spectrum from meters/dBm to nm/THz/mW, and restricts it to the hardware-supported 1200–1700 nm interval. It does **not** resample the DFT data. It uses `scipy.signal.resample` to reduce the OSA window to the same 1,250-point digital length before alignment and fitting, pairs prominent peaks one-to-one, refits frequency against measured DFT peak times, and uses the final fit to produce the common frequency/wavelength axes. The final calibrated overlay uses interpolation to evaluate OSA power at the fitted frequency coordinates.

## Environment

Install dependencies with:

```bash
python -m pip install -r requirements.txt
```

Start Jupyter in this folder so the relative `data/` paths work.

## Official documentation

- NumPy interpolation: https://numpy.org/doc/stable/reference/generated/numpy.interp.html
- NumPy polynomial fitting: https://numpy.org/doc/stable/reference/generated/numpy.polyfit.html
- SciPy peak detection: https://docs.scipy.org/doc/scipy/reference/generated/scipy.signal.find_peaks.html
- SciPy global optimization: https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.differential_evolution.html
- SciPy linear assignment: https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.linear_sum_assignment.html
- Matplotlib `fill_between`: https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.fill_between.html
- Matplotlib `savefig`: https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.savefig.html
- Jupyter Notebook documentation: https://jupyter-notebook.readthedocs.io/en/stable/
