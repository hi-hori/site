# ranges
* ranges[meta header]
* cpp20[meta cpp]

`<ranges>` では、イテレータの組ではなく、コンテナや配列、部分的なコンテナなどを扱う範囲ライブラリを提供する。

C++17までは、標準アルゴリズム関数はイテレータの組を扱い、範囲を直接扱ってはいなかった。
範囲ライブラリはBoost.Rangeやrange-v3などで実績があり、C++標準にも取り込まれることになった。

## 範囲アクセス

| 名前                                   | 説明                                                                             | 対応バージョン |
|---------------------------------------|----------------------------------------------------------------------------------|----------------|
| [`begin`](ranges/begin.md.nolink)     | 範囲の先頭を指すイテレータを取得する (customization point object)                    | C++20          |
| [`end`](ranges/end.md.nolink)         | 範囲の末尾の次を指すイテレータを取得する (customization point object)                | C++20          |
| [`cbegin`](ranges/cbegin.md.nolink)   | 範囲の先頭を指す読み取り専用イテレータを取得する (customization point object)        | C++20          |
| [`cend`](ranges/cend.md.nolink)       | 範囲の末尾の次を指す読み取り専用イテレータを取得する (customization point object)    | C++20          |
| [`rbegin`](ranges/rbegin.md.nolink)   | 範囲の末尾を指す逆イテレータを取得する (customization point object)                  | C++20          |
| [`rend`](ranges/rend.md.nolink)       | 範囲の先頭の前を指す逆イテレータを取得する (customization point object)              | C++20          |
| [`crbegin`](ranges/crbegin.md.nolink) | 範囲の末尾を指す読み取り専用逆イテレータを取得する (customization point object)      | C++20          |
| [`crend`](ranges/crend.md.nolink)     | 範囲の先頭の前を指す読み取り専用逆イテレータを取得する (customization point object)  | C++20          |
| [`size`](ranges/size.md.nolink)       | 範囲の要素数を取得する (customization point object)                                  | C++20          |
| [`ssize`](ranges/ssize.md.nolink)     | 範囲の要素数を、符号付き整数型で取得する (customization point object)                | C++20          |
| [`empty`](ranges/empty.md.nolink)     | 範囲が空かどうかを判定する (customization point object)                              | C++20          |
| [`data`](ranges/data.md.nolink)       | 範囲の要素配列へのポインタを取得する (customization point object)                    | C++20          |
| [`cdata`](ranges/cdata.md.nolink)     | 範囲の要素配列への読み取り専用ポインタを取得する (customization point object)        | C++20          |

## 範囲に関連する型へのアクセス

| 名前                                                                     | 説明                                              | 対応バージョン |
|-------------------------------------------------------------------------|---------------------------------------------------|----------------|
| [`iterator_t`](ranges/iterator_t.md.nolink)                             | 範囲のイテレータ型を取得する (alias template)        | C++20          |
| [`sentinel_t`](ranges/sentinel_t.md.nolink)                             | 範囲の番兵型を取得する (alias template)              | C++20          |
| [`range_difference_t`](ranges/range_difference_t.md.nolink)             | 範囲のイテレータの差の型を取得する (alias template)  | C++20          |
| [`range_size_t`](ranges/range_size_t.md.nolink)                         | 範囲のサイズの型を取得する(alias template)           | C++20          |
| [`range_value_t`](ranges/range_value_t.md.nolink)                       | 範囲の要素の型を取得する (alias template)            | C++20          |
| [`range_reference_t`](ranges/range_reference_t.md.nolink)               | 範囲の要素の参照型を取得する (alias template)        | C++20          |
| [`range_rvalue_reference_t`](ranges/range_rvalue_reference_t.md.nolink) | 範囲の要素の右辺値参照型を取得する (alias template)  | C++20          |

## 範囲コンセプト

| 名前                                                          | 説明                                                  | 対応バージョン |
|---------------------------------------------------------------|-------------------------------------------------------|----------------|
| [`range`](ranges/range.md.nolink)                             | 範囲を定義するコンセプト (concept)                      | C++20          |
| [`borrowed_range`](ranges/borrowed_range.md.nolink)           | 所有権を持たない範囲 (concept)                         | C++20          |
| [`sized_range`](ranges/sized_range.md.nolink)                 | サイズを一定時間で求められる範囲 (concept)               | C++20          |
| [`output_range`](ranges/output_range.md.nolink)               | イテレータが出力イテレータである範囲 (concept)           | C++20          |
| [`input_range`](ranges/input_range.md.nolink)                 | イテレータが入力イテレータである範囲 (concept)           | C++20          |
| [`forward_range`](ranges/forward_range.md.nolink)             | イテレータが前進イテレータである範囲 (concept)           | C++20          |
| [`bidirectional_range`](ranges/bidirectional_range.md.nolink) | イテレータが双方向イテレータである範囲 (concept)          | C++20          |
| [`random_access_range`](ranges/random_access_range.md.nolink) | イテレータがランダムアクセスイテレータである範囲 (concept) | C++20          |
| [`contiguous_range`](ranges/contiguous_range.md.nolink)       | イテレータが隣接イテレータである範囲 (concept)            | C++20          |
| [`common_range`](ranges/common_range.md.nolink)               | イテレータと番兵の型が等しい範囲 (concept)               | C++20          |
| [`viewable_range`](ranges/viewable_range.md.nolink)           | ビューに変換できる範囲 (concept)                        | C++20          |

## 範囲の特性のオプトイン

| 名前                                                              | 説明                                                  | 対応バージョン |
|-------------------------------------------------------------------|-------------------------------------------------------|----------------|
| [`enable_borrowed_range`](ranges/enable_borrowed_range.md.nolink) | 範囲を`borrowed_range`にする (variable template) | C++20          |
| [`enable_view`](ranges/enable_view.md.nolink)                        | 範囲を`view`にする (variable template)           | C++20          |

## 部分範囲

| 名前                                                | 説明                 | 対応バージョン |
|-----------------------------------------------------|----------------------|----------------|
| [`view_interface`](ranges/view_interface.md.nolink) | ビューの基底クラスとして推奨されるクラス (class template)     | C++20          |
| [`subrange_kind`](ranges/subrange_kind.md.nolink)   | 部分範囲の種類を表す列挙体 (enum class)         | C++20          |
| [`subrange`](ranges/subrange.md.nolink)             | イテレータペアを範囲として扱う (class template)     | C++20          |


## ダングリングイテレータハンドリング

| 名前                                                   | 説明           | 対応バージョン |
|--------------------------------------------------------|----------------|----------------|
| [`dangling`](ranges/dangling.md.nolink)                       | ダングリングイテレータ、ダングリング範囲を表す型 (class)      | C++20          |
| [`borrowed_iterator_t`](ranges/borrowed_iterator_t.md.nolink) | 範囲が`borrowed_range`ではないとき`dangling`となるイテレータ (alias template) | C++20          |
| [`borrowed_subrange_t`](ranges/borrowed_subrange_t.md.nolink) | 範囲が`borrowed_range`ではないとき`dangling`となる部分範囲 (alias template) | C++20          |

## ビュー

| 名前                                   | 説明                | 対応バージョン |
|----------------------------------------|---------------------|----------------|
| [`view_base`](ranges/view_base.md.nolink) | 基底クラスとすることで`view`となるタグ型 (class) | C++20          |
| [`view`](ranges/view.md.nolink)           | ビューである範囲 (concept)                     | C++20          |

### Rangeファクトリ

#### empty view

| 名前                                        | 説明           | 対応バージョン |
|---------------------------------------------|----------------|----------------|
| [`empty_view`](ranges/empty_view.md.nolink) | 空の範囲 (class template)     | C++20          |
| [`empty`](ranges/empty.md.nolink)           | `empty_view`を生成する (variable template)  | C++20          |

#### single view

| 名前                                          | 説明           | 対応バージョン |
|-----------------------------------------------|----------------|----------------|
| [`single_view`](ranges/single_view.md.nolink) | 指定した値1つからなる範囲 (class template)     | C++20          |
| [`single`](ranges/single.md.nolink)           | `single_view`を生成する (variable template)  | C++20          |

#### iota view

| 名前                                      | 説明           | 対応バージョン |
|-------------------------------------------|----------------|----------------|
| [`iota_view`](ranges/iota_view.md.nolink) | 単調増加列である範囲 (class template)     | C++20          |
| [`iota`](ranges/iota.md.nolink)           | `iota_view`を生成する (customization point object)  | C++20          |

#### istream view

| 名前                                                        | 説明           | 対応バージョン |
|-------------------------------------------------------------|----------------|----------------|
| [`basic_istream_view`](ranges/basic_istream_view.md.nolink) | 入力ストリームから値を読む範囲 (class template)     | C++20          |
| [`istream_view`](ranges/istream_view.md.nolink)             | `basic_istream_view`を生成する (function template)     | C++20          |

### Rangeアダプタ

#### all view

| 名前                                    | 説明           | 対応バージョン |
|-----------------------------------------|----------------|----------------|
| [`ref_view`](ranges/ref_view.md.nolink) | 範囲への参照として振る舞うビュー (class template)     | C++20          |
| [`all`](ranges/all.md.nolink)           | 範囲への参照として振る舞うビューを生成する (customization point object) | C++20          |
| [`all_t`](ranges/all_t.md.nolink)       | `all`の戻り値型 (alias template)     | C++20          |

#### filter view

| 名前                                          | 説明           | 対応バージョン |
|-----------------------------------------------|----------------|----------------|
| [`filter_view`](ranges/filter_view.md.nolink) | 指定した条件を満たす要素だけを集めるビュー (class template)     | C++20          |
| [`filter`](ranges/filter.md.nolink)           | 指定した条件を満たす要素だけを集めるビューを生成する (customization point object)  | C++20          |

#### transform view

| 名前                                                | 説明           | 対応バージョン |
|-----------------------------------------------------|----------------|----------------|
| [`transform_view`](ranges/transform_view.md.nolink) | 指定した関数で各要素を変換するビュー (class template)     | C++20          |
| [`transform`](ranges/transform.md.nolink)           | 指定した関数で各要素を変換するビューを生成する (customization point object)  | C++20          |

#### take view

| 名前                                      | 説明           | 対応バージョン |
|-------------------------------------------|----------------|----------------|
| [`take_view`](ranges/take_view.md.nolink) | 先頭から指定した個数だけ取り出すビュー (class template)     | C++20          |
| [`take`](ranges/take.md.nolink)           | 先頭から指定した個数だけ取り出すビューを生成する (customization point object)  | C++20          |

#### take while view

| 名前                                                  | 説明           | 対応バージョン |
|-------------------------------------------------------|----------------|----------------|
| [`take_while_view`](ranges/take_while_view.md.nolink) | 先頭から指定した条件を満たす範囲を取り出すビュー (class template)     | C++20          |
| [`take_while`](ranges/take_while.md.nolink)           | 先頭から指定した条件を満たす範囲を取り出すビューを生成する (customization point object)  | C++20          |

#### drop view

| 名前                                      | 説明           | 対応バージョン |
|-------------------------------------------|----------------|----------------|
| [`drop_view`](ranges/drop_view.md.nolink) | 先頭から指定した個数だけ除外するビュー (class template)     | C++20          |
| [`drop`](ranges/drop.md.nolink)           | 先頭から指定した個数だけ除外するビューを生成する (customization point object)  | C++20          |

#### drop while view

| 名前                                                  | 説明           | 対応バージョン |
|-------------------------------------------------------|----------------|----------------|
| [`drop_while_view`](ranges/drop_while_view.md.nolink) | 先頭から指定した条件を満たす範囲を除外するビュー (class template)     | C++20          |
| [`drop_while`](ranges/drop_while.md.nolink)           | 先頭から指定した条件を満たす範囲を除外するビューを生成する (customization point object)  | C++20          |

#### join view

| 名前                                      | 説明           | 対応バージョン |
|-------------------------------------------|----------------|----------------|
| [`join_view`](ranges/join_view.md.nolink) | ネストされた範囲を平坦にするビュー (class template)     | C++20          |
| [`join`](ranges/join.md.nolink)           | ネストされた範囲を平坦にするビューを生成する (customization point object)  | C++20          |

#### split view

| 名前                                        | 説明           | 対応バージョン |
|---------------------------------------------|----------------|----------------|
| [`split_view`](ranges/split_view.md.nolink) | 範囲を指定したデリミタで分割するビュー (class template)     | C++20          |
| [`split`](ranges/split.md.nolink)           | 範囲を指定したデリミタで分割するビューを生成する (customization point object)  | C++20          |

#### counted view

| 名前                                  | 説明           | 対応バージョン |
|---------------------------------------|----------------|----------------|
| [`counted`](ranges/counted.md.nolink) | イテレータを指定した数だけ進めるビューを生成する (customization point object)  | C++20          |

#### common view

| 名前                                          | 説明           | 対応バージョン |
|-----------------------------------------------|----------------|----------------|
| [`common_view`](ranges/common_view.md.nolink) | `common_range`にしたビュー (class template)     | C++20          |
| [`common`](ranges/common.md.nolink)           | `common_range`なビューを生成する (customization point object)  | C++20          |

#### reverse view

| 名前                                            | 説明           | 対応バージョン |
|-------------------------------------------------|----------------|----------------|
| [`reverse_view`](ranges/reverse_view.md.nolink) | 逆順のビュー (class template)     | C++20          |
| [`reverse`](ranges/reverse.md.nolink)           | 逆順のビューを生成する (customization point object)  | C++20          |

#### elements view

| 名前                                              | 説明           | 対応バージョン |
|---------------------------------------------------|----------------|----------------|
| [`elements_view`](ranges/elements_view.md.nolink) | 第n要素を集めたビュー (class template)     | C++20          |
| [`keys_view`](ranges/keys_view.md.nolink)         | 第0要素を集めたビュー (alias template)     | C++20          |
| [`values_view`](ranges/values_view.md.nolink)     | 第1要素を集めたビュー (alias template)     | C++20          |
| [`elements`](ranges/elements.md.nolink)           | `elements_view`を生成する (variable template) | C++20          |
| [`keys`](ranges/keys.md.nolink)                   | `keys_view`を生成する (customization point object)  | C++20          |
| [`values`](ranges/values.md.nolink)               | `values_view`を生成する (customization point object)  | C++20          |

## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): 13.0.0
- [GCC](/implementation.md#gcc): 10.1.0
- [ICC](/implementation.md#icc): ?
- [Visual C++](/implementation.md#visual_cpp): 19.29

## 関連項目
- [`<iterator>`](iterator.md)
- [`<concepts>`](concepts.md)

## 参照
- [N4861 24 Ranges library](https://timsong-cpp.github.io/cppwp/n4861/ranges)
- [C++20 ranges](https://techbookfest.org/product/5134506308665344?utm_source=twitter&utm_medium=social&utm_campaign=bought)
