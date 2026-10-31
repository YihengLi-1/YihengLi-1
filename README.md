# Yiheng Li

I test whether EEG and intracranial foundation models generalize to people they have never seen. Most papers say they do. I check the data.

**The audit.** I read the pretraining and evaluation sections of 23 EEG foundation-model papers. 33 of the 142 reported "new subject" results were on data the model had already seen in pretraining; 4 of the 33 had a control. Eight model groups have confirmed their rows (ETH Zürich, Microsoft Research, USC, Beijing Jiaotong). braindecode is writing the results into the model cards of about 50 Hub checkpoints with me ([#1493](https://github.com/braindecode/braindecode/pull/1493)).
[table](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md) · [json](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.json) · [disclosure spec](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_disclosure.md) · [add a row](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/issues/new/choose)

**The experiments.** One protocol, four subject-level splits, only the model changes. LaBraM beats EEGNet by 24 points on a dataset inside its pretraining corpus and by 13 on one outside it. A model that saw neither dataset drops by as much. Pretraining on the test subjects' own unlabeled EEG moves accuracy by −0.4 ± 1.4 points. The overlap is real; the inflation is not.
[report](https://doi.org/10.5281/zenodo.23423535) · manuscript for TMLR in preparation

**The leaderboard.** Every number computed by me under that protocol, every cell marked with whether the checkpoint had seen the dataset. Used to map the NeurIPS 2026 Neural Interfaces challenge datasets against every public checkpoint.
[leaderboard](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/heldout_leaderboard.md) · [challenge sheet](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/neurips2026_challenge_checkpoint_provenance.md)

**Intracranial.** BrainBERT, PoPT, BaRISTA and MAPA are pretrained and evaluated on the same ten Brain Treebank patients. As far as I can find, no released intracranial model has been scored on recordings from a hospital outside its pretraining data. That is the test I am building toward at ASU.
[intracranial section](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md#intracranial-ieegseegecog-foundation-models-pretraining-corpora-and-the-same-subject-problem)

**decay-bench.** How fast intracortical decoders lose accuracy with days since training, against a per-session normalization control, on FALCON.
[decay-bench](https://github.com/YihengLi-1/decay-bench)

Code upstream: braindecode [#1037](https://github.com/braindecode/braindecode/pull/1037) [#1493](https://github.com/braindecode/braindecode/pull/1493) · torch_brain [#396](https://github.com/neuro-galaxy/torch_brain/pull/396)

Arizona State University, with Yalin Wang (SCAI) and Bradley Greger (SBHSE). yihengl4@asu.edu
