# Yiheng Li

I maintain the author-verified registry of what public EEG and intracranial foundation models were pretrained on, and the held-out leaderboard built on it. The question behind both: when a decoder is said to generalize to new people or new days, has it really never seen them? Arizona State University, Computer Science.

### Registry

23 EEG foundation models, 142 reported downstream results, each labelled in-corpus, same-collection or held-out with page-cited quotes; per-checkpoint lists for about 50 `braindecode/*` Hub checkpoints, EEG and intracranial, now being written into their Hugging Face model cards with the braindecode maintainers ([braindecode#1493](https://github.com/braindecode/braindecode/pull/1493)). Rows confirmed by the authors of FEMBA, LUNA, LuMamba (ETH Zürich), BrainCodes (USC/Microsoft), CodeBrain and Uni-NTFM (Beijing Jiaotong), Neuro-GPT (USC) and NeuroLM (Microsoft Research). Used to map the NeurIPS 2026 Neural Interfaces challenge datasets against every public checkpoint.
[table](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md) · [json](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.json) · [challenge sheet](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/neurips2026_challenge_checkpoint_provenance.md) · [add a row](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/issues/new/choose)

### Leaderboard

Subject-independent accuracy for public checkpoints under one protocol, every cell marked with whether that checkpoint saw the dataset in pretraining. The only EEG leaderboard where a number comes with its provenance.
[heldout_leaderboard.md](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/heldout_leaderboard.md)

### decay-bench

How fast intracortical decoders lose accuracy with days since training, against a per-session normalization control, on FALCON.
[decay-bench](https://github.com/YihengLi-1/decay-bench)

### Results

33 of 142 published results are in-corpus or same-collection; 4 of those have a control. Removing the overlap barely moves the answer: LaBraM over EEGNet is 79.1 vs 54.9 on PhysioNet MI (in LaBraM's corpus) and 65.8 vs 52.3 on Cho2017 (outside it); a model that saw neither shrinks by about as much, and pretraining on the test subjects' own unlabeled EEG changes accuracy by −0.4 ± 1.4 points. Four public intracranial models (BrainBERT, PoPT, BaRISTA, MAPA) are pretrained and evaluated on the same ten Brain Treebank subjects. Report: [10.5281/zenodo.23423535](https://doi.org/10.5281/zenodo.23423535); full manuscript in preparation.

### Code elsewhere

braindecode [#1037](https://github.com/braindecode/braindecode/pull/1037) [#1033](https://github.com/braindecode/braindecode/pull/1033) [#1034](https://github.com/braindecode/braindecode/pull/1034) [#1493](https://github.com/braindecode/braindecode/pull/1493) · torch_brain [#396](https://github.com/neuro-galaxy/torch_brain/pull/396)

At ASU I work with Yalin Wang (SCAI) on EEG foundation-model evaluation and with Bradley Greger (SBHSE) on intracranial recordings. Available for a research internship in summer 2027.

yihengl4@asu.edu
