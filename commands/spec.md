---
description: "spec-driven development"
---

Claude Code を用いた spec-driven development を行う

## spec-driven development とは

spec-driven development は、以下の 5 つのフェーズからなる開発手法である。

### 1. 事前準備フェーズ

- ユーザーが Claude Code に対して、実行したいタスクの概要を伝える
- `mkdir -p ./.specs` を実行する
- `./.specs` 内にタスクの概要から適切な spec 名を考えて、その名前のディレクトリを作成する
  - たとえば、「記事コンポーネントを作成する」というタスクなら `./.specs/create-article-component` を作成する
- 以下ファイルを作成するときはこのディレクトリの中に作成する

### 2. 要件フェーズ

- Claude Code がユーザーから伝えられたタスクの概要に基づいて、タスクが満たすべき`requirements.md`を作成する
- Claude Code がユーザーに対して`requirements.md`を提示し、問題がないかを尋ねる
- ユーザーが`requirements.md`を確認し、問題があれば Claude Code に対してフィードバックする
- ユーザーが`requirements.md`を確認し、問題がないと答えるまで`requirements.md`に対して修正を繰り返す

### 3. 設計フェーズ

- Claude Code は、`requirements.md`に記載されている要件を満たすような設計を記述した`design.md`を作成する
- Claude Code がユーザーに対して`design.md`を提示し、問題がないかを尋ねる
- ユーザーが`design.md`を確認し、問題があれば Claude Code に対してフィードバックする
- ユーザーが`design.md`を確認し、問題がないと答えるまで`design.md`に対して修正を繰り返す

### 4. 実装計画フェーズ

- Claude Code は、`design.md`に記載されている設計を実装するための`implementation-plan`を作成する
  - PR の単位ごとにファイルを分けて欲しい (`implementation-plan-1`, `implementation-plan-2`, ..)
- `implementation-plan`には以下の内容を含める：
  - **PR と commit の単位を意識した実装の流れ**
    - PR の単位は重要：レビュー可能な単位で分割する
    - commit は参考程度：実装中に適宜調整可能
  - **チェックボックス形式の進捗管理**
    - 各タスクにチェックボックスを用意し、進捗が瞬時にわかるようにする
  - **大まかな実装の流れ**
    - 具体的な設計は`design.md`に記載されているため、実装計画では大まかな流れのみを記述
    - 実装順序の基本方針：
      1. ドメインロジック（domain 層）から実装
      2. ユースケース層（use-cases 層）を実装
      3. 既存のバックエンド（GraphQL、REST API 等）と接続
      4. フロントエンドと接続
- Claude Code がユーザーに対して`implementation-plan`を提示し、問題がないかを尋ねる
- ユーザーが`implementation-plan`を確認し、問題があれば Claude Code に対してフィードバックする
- ユーザーが`implementation-plan`を確認し、問題がないと答えるまで`implementation-plan`に対して修正を繰り返す

### 5. 実装フェーズ

- Claude Code は、`implementation-plan.md`に基づいて実装を開始する
- 実装するときは`requirements.md`,`design.md`に記載されている内容を守りながら実装すること
