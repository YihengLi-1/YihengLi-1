# Yiheng Li

CS junior at Arizona State University (4.0). I work on one question: **when a neural decoder is said to generalize to new people or new days, has it really never seen them?** I answer it with audits, held-out evaluations and tools that other people can run.

## What I maintain

**Pretraining-overlap audit of EEG foundation models** · [table](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.md) · [JSON](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/pretraining_overlap_eeg_fm.json)
For 23 public EEG foundation models, which datasets were in the pretraining corpus and which were used for evaluation, with page-cited quotes. 142 reported results: 33 are in-corpus or same-collection, and only 4 of those come with a control. Rows for FEMBA, LUNA, LuMamba, BrainCodes, CodeBrain, Uni-NTFM, Neuro-GPT and NeuroLM were checked by their authors. A per-checkpoint extension (about 50 `braindecode/*` Hub checkpoints, including intracranial models) is being merged into the braindecode model cards ([braindecode#1493](https://github.com/braindecode/braindecode/pull/1493)).

**Held-out leaderboard** · [page](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/heldout_leaderboard.md)
Every number computed under one subject-independent protocol, every cell badged with whether that checkpoint saw the dataset in pretraining. Companion sheet for the [NeurIPS 2026 Neural Interfaces challenge datasets](https://github.com/YihengLi-1/eeg-motor-imagery-decoding/blob/main/docs/neurips2026_challenge_checkpoint_provenance.md).

**decay-bench** · [repo](https://github.com/YihengLi-1/decay-bench)
How fast intracortical decoders lose accuracy across days: R² against days since training, with a per-session normalization control, on the FALCON benchmark.

## Findings so far

- On a dataset inside LaBraM's pretraining corpus (PhysioNet MI) it beats EEGNet 79.1% to 54.9%; on one outside it (Cho2017) the gap is 65.8% to 52.3%. A control model that saw neither (CBraMod) drops by a similar amount, so most of the shrinkage is the dataset, not the overlap. Report: [doi:10.5281/zenodo.23423535](https://doi.org/10.5281/zenodo.23423535).
- Continued self-supervised pretraining on the test subjects' own unlabeled EEG, versus an equal amount of other subjects' EEG, changes downstream accuracy by −0.4 ± 1.4 points over 4 seeds, even though it measurably improves how well the encoder models those subjects. Manuscript in preparation for TMLR.
- Four public intracranial foundation models (BrainBERT, PoPT, BaRISTA, MAPA) are pretrained on Brain Treebank and evaluated on other sessions of the same ten subjects; three EEG models (ZUNA, STEEGFormer, DIVER-1) cannot be fully declared because their corpora are not itemised.

## Open-source contributions

braindecode: [#1037](https://github.com/braindecode/braindecode/pull/1037) (preprocessing fix), [#1033](https://github.com/braindecode/braindecode/pull/1033), [#1034](https://github.com/braindecode/braindecode/pull/1034) merged; [#1493](https://github.com/braindecode/braindecode/pull/1493) (model-card pretraining metadata, with the maintainers) under review · torch_brain: [#396](https://github.com/neuro-galaxy/torch_brain/pull/396) FALCON H1/M1/M2 brainsets, merged.

## Before this

I pay my own way through school by building software that businesses run on: a scheduling and AI-agent platform used daily by two clinics (650+ bookings a month), a retrieval-evaluation framework at ASU's W. P. Carey School (Recall@5 71% → 89%), and backend work at LEQISMART (MySQL latency 420 ms → 95 ms). Code: [forward-deployed-agent-lab](https://github.com/YihengLi-1/forward-deployed-agent-lab), [horizon](https://github.com/YihengLi-1/horizon), [shijia-site](https://github.com/YihengLi-1/shijia-site). That background is why the research above ships as runnable code with tests rather than as a PDF.

## Now

Research with Prof. Yalin Wang (SCAI) on EEG foundation-model evaluation and with Prof. Bradley Greger (SBHSE) on intracranial recordings. Looking for a **summer 2027 research position in the US on neural-interface evaluation, intracranial decoding or BCI hardware/software integration**.

yihengl4@asu.edu · [LinkedIn](https://www.linkedin.com/in/yiheng-li-0bb984337)
