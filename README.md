# QuanTEEum paper

> QuanTEEum: Quantum Cryptography via TEEs

Status: Preprint under review for Financial Cryptography & Data Security 2026  
PDF: [paper.pdf](./paper.pdf)

## Abstract
One-shot signatures (OSS) have emerged as a versatile abstraction underpinning various blockchain-facing applications. Existing OSS constructions rely on quantum hardware that will not be widely available soon. Naïve emulations using a single trusted execution environment (TEE) inherit brittle unclonability requirements and concentrate integrity risk in one enclave, while certified deletion on a single device is notoriously hard.

We present QuanTEEum, an honest-minority distributed protocol that realizes certified deletion and OSS by running threshold signing entirely inside heterogeneous TEEs. In QuanTEEum, n enclaves run a threshold DKG, produce exactly one threshold signature on the designated message m⋆, and each emits a remote attestation (RA) binding an in-enclave deletion event; security is additive across heterogeneous TEEs, as independent deletion attestations strictly raise the minimum cost- of- attack, and TEE heterogeneity provides defense-in-depth against supply-chain risks.

We formalize the exact-one acceptance condition for one-shot signing in a remote attestation model under an abstract replay predicate Fresh (enforcing per-session counter monotonicity), and we discuss pluggable attestation back ends—(a) conventional TEE RA, (b) cryptoeconomic attestations via escrowed collateral, and (c) future quantum instantiations—yielding a clean upgrade path. We sketch applications to OSS and Quantum money, and discuss liveness, freshness, and rollback subtleties.

## Build locally
```bash
# requires TeX Live (or MacTeX) with latexmk and xelatex
cd paper
latexmk -xelatex -interaction=nonstopmode -file-line-error main.tex
# output: paper/main.pdf (repo root copy: paper.pdf)
```

## Repository layout
```
/paper/
├── sources/               # LaTeX sources
│   ├── main.tex
│   ├── refs.bib
│   ├── llncs.cls
│   ├── splncs04.bst
│   └── figures/
├── paper.pdf              # built PDF at repo root 
├── .gitignore
└── LICENSE
```

## Cite
Use the BibTeX below.
```bibtex
@misc{quanteeum_paper_2025,
  title        = {QuanTEEum: Quantum Cryptography via TEEs},
  author       = {Ahmed, Shoaib},
  year         = {2025},
  howpublished = {\url{https://github.com/quanteeum/paper}},
  note         = {paper preprint}
}
```

## License
Text is licensed under CC BY 4.0. See [LICENSE](./LICENSE).

