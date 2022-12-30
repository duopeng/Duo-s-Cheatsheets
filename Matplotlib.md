### subplots
```
# 4x4 plots
fig, axes = plt.subplots(nrows=4, ncols=4, figsize=(16,14))
fig.subplots_adjust(hspace=0.5, wspace=0.5)
fig.suptitle('main title')
idx=0
for tp in merged.obs["timepoint"].unique():
    for rep in merged.obs["replicate"].unique():
        _adata = merged[merged.obs["timepoint"]==tp]
        _adata = _adata[_adata.obs["replicate"]==rep]
        sc.pl.violin(_adata, ['AGAP029539'], groupby='treatment', cut=0, inner="box", use_raw=False,  stripplot=False,scale='width', ylabel = f"AGAP029539 @ {tp}", xlabel=f"{rep}", ax=axes.flatten()[idx], show=False)
        #ax.set(title=name[:-4].upper(), xlabel='cm')
        idx+=1
```
