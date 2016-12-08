# Towards Static Analysis of Virtualization-Obfuscated Binaries

## Abstract

Virtualization-obfuscationは、ランダムな仮想アーキテクチャのバイトコードに変換して、インタプリタを添付することで保護する技術らしい

これを静的解析するために何が課題になるかを説明するよ

変数の可能な値は、プログラムの位置に対してのみ正確であるよ.
でもインタプリタループでは、異なる場所からの無関係なデータフローと結びついている

既存の静的解析手法をどうやって適用するかを提案.

JAKSTAB static analyzer


## Introduction

難読化バイトコードとインタプリタが与えられ、インタプリタは、バイトコードを実行する形になる.

インタープリタをコードとして見て、難読化されたものをデータとして考えれば良いのでは. 天才.

マルウェア作者に人気.
インタプリタ自体は悪意のあるコードではないので、誤検知してしまうことがある.

データフロー情報の計算は、普通は有用なんだけど、今回の場合はインタプリタ上でのみ計算されてしまう


- domain flattening状態になっていて有益な情報が得られない
- 仮想プログラムカウンタに対して、個別の抽象状態を保持
- Bounded Address TrackingをVPCレベルにしてJAKSTABで実装

## Background

例でざっと説明しますよ

### Virtualization Obfuscation

オペコードとバイトコード命令の対応をランダムにする.
関数を分解なり、併合するなりしているわけだから、解析とかパターンマッチングで取れなくもない.

- CodeVirtualizer
- VMProtect

### Static Analysis

記号 <- 不明

## Static Analysis of Interpreted Code

location-sensitiveだけでなく、VPC-sensitiveが必要

## VPC-Sensitive Static Analysis



## Lifting Bounded Address Tracking

## Experiments

## Related Work

## Conclusion

Virtualization-obfuscationによる効果を正確に特徴づけられた.

野良コードもこれからやりますよ〜

難読化コードを提供してくれた人に謝辞を書いてた.
僕も欲しい.
