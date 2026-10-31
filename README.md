# Yiheng Li

I keep the **pretraining-provenance registry for EEG and intracranial foundation models**: for each public checkpoint, which datasets it was pretrained on, so that a "new subject" result can be checked against what the encoder has already seen. CS junior at Arizona State University.

## Checked by the people who built the models

Rows confirmed by their authors: **FEMBA, LUNA, LuMamba** (ETH Zürich), **BrainCodes** (USC / Microsoft), **CodeBrain, Uni-NTFM** (Beijing Jiaotong), **Neuro-GPT** (USC), **NeuroLM** (Microsoft Research).
The braindecode maintainers are moving the registry into the Hugging Face model cards of the `braindecode/*` checkpoints ([braindecode#1493](https://github.com/braindecode/braindecode/pull/1493)): "the problem is real and your audit is very useful" ([lead maintainer, 2026-10-31](https://github.com/braindecode/braindecode/pull/1493#issuecomment-6547829480)).

## Use it

| | |
|---|---|
| Audit table, 23 models, 142 results, page-cited | [pretraining_overlap_eeg_fm.md](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md) · [JSON](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.json) |
| Held-out leaderboard, every cell badged with provenance | [heldout_leaderboard.md](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/heldout_leaderboard.md) |
| Checkpoints vs. the NeurIPS 2026 Neural Interfaces challenge datasets | [provenance sheet](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/neurips2026_challenge_checkpoint_provenance.md) |
| Decoder decay across days (intracortical, FALCON) | [decay-bench](https://github.com/YihengLi-1/decay-bench) |

**Maintain a model?** Open an [issue](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/issues/new) with your pretraining list and I will add or correct your row within a few days. Verified rows can carry this badge:

[![pretraining provenance: checked](https://img.shields.io/badge/pretraining%20provenance-checked-2ea44f)](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md)

**Cite:** Y. Li, *Does an EEG foundation model's cross-subject advantage survive outside its pretraining corpus?*, Zenodo, 2026. [doi:10.5281/zenodo.23423535](https://doi.org/10.5281/zenodo.23423535) (a full manuscript is in preparation for TMLR).

## What the registry has shown so far

- 33 of 142 reported downstream results use a dataset that is in, or a sub-corpus of, the model's own pretraining data; 4 of the 33 have a control.
- Removing the overlap barely changes the answer: on a dataset outside LaBraM's corpus the gain over EEGNet shrinks from 24 to 13 points, but a control model that saw neither dataset shrinks by a similar amount, and continued pretraining on the test subjects' own unlabeled EEG changes accuracy by −0.4 ± 1.4 points (4 seeds). Most of the shrinkage is the dataset, not the overlap.
- Four public intracranial models (BrainBERT, PoPT, BaRISTA, MAPA) are pretrained on Brain Treebank and evaluated on other sessions of the same ten subjects; three EEG models (ZUNA, STEEGFormer, DIVER-1) cannot be fully declared because their corpora are not itemised.

## Code in other people's repositories

braindecode: [#1037](https://github.com/braindecode/braindecode/pull/1037), [#1033](https://github.com/braindecode/braindecode/pull/1033), [#1034](https://github.com/braindecode/braindecode/pull/1034) merged, [#1493](https://github.com/braindecode/braindecode/pull/1493) under review · torch_brain: [#396](https://github.com/neuro-galaxy/torch_brain/pull/396) FALCON H1/M1/M2 brainsets, merged.

## Now

Working with Prof. Yalin Wang (ASU SCAI) on EEG foundation-model evaluation and with Prof. Bradley Greger (ASU SBHSE) on intracranial recordings. Open to a **summer 2027 research position in the US** on neural-interface evaluation or intracranial decoding.

<details>
<summary>Before research: production software</summary>

A scheduling and AI-agent platform two clinics run on daily (650+ bookings a month), a retrieval-evaluation framework at ASU's W. P. Carey School (Recall@5 71% → 89%), backend work at LEQISMART (MySQL latency 420 ms → 95 ms). Code: [forward-deployed-agent-lab](https://github.com/YihengLi-1/forward-deployed-agent-lab), [horizon](https://github.com/YihengLi-1/horizon). This is why the research above ships as runnable code with tests.
</details>

yihengl4@asu.edu
