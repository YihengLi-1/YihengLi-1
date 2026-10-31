# Yiheng Li

Arizona State University, Computer Science. I study whether neural decoders generalize to people and days they have not seen, and I keep the bookkeeping that makes the question answerable: which datasets each public EEG and intracranial foundation model was pretrained on.

### Registry

Pretraining-overlap table for 23 EEG foundation models: 142 reported downstream results, each labelled in-corpus, same-collection or held-out, with page-cited quotes. Rows for FEMBA, LUNA, LuMamba, BrainCodes, CodeBrain, Uni-NTFM, Neuro-GPT and NeuroLM confirmed by their authors. Per-checkpoint lists for the `braindecode/*` Hub models (about 50, EEG and intracranial) are being merged into their model cards in [braindecode#1493](https://github.com/braindecode/braindecode/pull/1493).
[table](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md) · [json](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.json) · [challenge datasets sheet](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/neurips2026_challenge_checkpoint_provenance.md)

To add or correct a row, [open an issue](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/issues/new/choose) with the pretraining list and its source.

### Leaderboard

Subject-independent accuracy for public checkpoints under one protocol, each cell marked with whether the checkpoint saw that dataset in pretraining.
[heldout_leaderboard.md](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/heldout_leaderboard.md)

### decay-bench

How fast intracortical decoders lose accuracy with days since training, against a per-session normalization control, on FALCON.
[decay-bench](https://github.com/YihengLi-1/decay-bench)

### Results

In-corpus versus out-of-corpus: LaBraM over EEGNet is 79.1 vs 54.9 on PhysioNet MI (in LaBraM's corpus) and 65.8 vs 52.3 on Cho2017 (outside it); a model that saw neither (CBraMod) shrinks by about as much, and pretraining on the test subjects' own unlabeled EEG changes accuracy by −0.4 ± 1.4 points. Report: [10.5281/zenodo.23423535](https://doi.org/10.5281/zenodo.23423535). Full manuscript in preparation.

### Code elsewhere

braindecode [#1037](https://github.com/braindecode/braindecode/pull/1037) [#1033](https://github.com/braindecode/braindecode/pull/1033) [#1034](https://github.com/braindecode/braindecode/pull/1034) [#1493](https://github.com/braindecode/braindecode/pull/1493) · torch_brain [#396](https://github.com/neuro-galaxy/torch_brain/pull/396)

At ASU I work with Yalin Wang (SCAI) and Bradley Greger (SBHSE). Summer 2027: open to a research visit in the US.

yihengl4@asu.edu
