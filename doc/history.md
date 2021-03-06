# Version history

## 0.4.9

* `:spec-provider.provider/range` option to enable inference of range
  predicates for numerical fields.

## 0.4.8

* Fixes issues with key optionality in maps (Issued #10)
* Support for maps that contain mixed keyword and non-keyword keys.

## 0.4.7

* Support for symbols.
* Support for maps whose keys are not keywords (inferred as `s/map-of`).
* Minor fix for nilable sets.
* Rewrite `s/or` where all the options are `nilable` so that the
  `nilable` wraps the whole form.
* Fix handling of sets.
* Fix handling of empty collections.
* Infer values that match no known preds as `any?`.
* Better support for nested sequences, results in deeper specs.
* "Do I know you from somewhere?": nested specs that are identical
  with a named spec elsewhere will be replaced by the name of the
  known spec.
* Fixes for nested structures (Issue #7)
* Fix issue #7: Merging of key `:spec-provider.stats/elements-coll`
  of stats of the same key was failing with an NPE.
* Fix problem where `1.0` would spec'ed as `(s/or :double double? :float float?)`.
  You now get `double?` unless it's really `(float 1.0)`.

## 0.4.0

* Infer nilable: collect stats for nil values and wrap with
  `s/nilable` where appropriate.
* Fix issue #1: If a sample value was a collection, `s/coll-of` would
  override any other specs for the leaf. This is now fixed.
* Update to Clojure 1.9.0-alpha16 (spec namespaces were renamed).

## 0.3.1

Initial release
