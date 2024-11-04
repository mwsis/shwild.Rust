# shwild - TODOS <!-- omit in toc -->


## Table of Contents <!-- omit in toc -->

- [Introduction](#introduction)
	- [Pattern Elements](#pattern-elements)


## General features

✅ benchmarks;
✅ see if can elide `if !s.is_empty() {`;
✅ combine parsing for `MatchRange` and `MatchNotRange`;
✅ eliminate `Option<>`;
✅ lots of multibyte character testing;
✅ parse error line/column capture;
✅ handling escape characters;
❌ can pass `s` into `parse_()`? - rejected, as adds 5-10% to benchmark times;
❓ use `auto_buffer<char>` in `parse_()`? - some positive signs, but need to do more research;
✅ reimplement `prepare_range_string()` (into `prepare_range_string_from_slice()`) to work directly from buffer - substantial improvements in performance;
✅ more detailed benchmarks;
❌ Unicode strings containing characters that require more than 4 bytes - rejected, as a non-issue;
✅ apply `UnicodePointMap` for range matching - 40-75% improvement on some pattern-compilation benchmarks;
✅ comparative performance tests against `std::regex`;
* implement `minimum_required`;
* separate the implementations when creating parser and calling API, so can decide which kinds of optimisations to make in the parsing (such as redundant repetitive match conditions, )


## Unit-testing features


* `matches!()`;
✅ `assert_shwild_matches!()`, `assert_shwild_not_matches!()`;
* `assert_contains!()` - needs (and supplements) **test_help-rs**;
* `assert_starts_with!()` - needs (and supplements) **test_help-rs**;
* `assert_ends_with!()` - needs (and supplements) **test_help-rs**;


## Behavioural modification features

* remove-redundant repetitive match conditions, e.g. "abc**" => "abc*", "abc*?*" => "abc?*";
* `SUPPRESS_BACKSLASH_ESCAPE`, `SUPPRESS_RANGE_SUPPORT`, `SHWILD_F_SUPPRESS_RANGE_CONTINUUM_SUPPORT`;
* `IGNORE_LEADING_SPACE`, `IGNORE_TRAILING_SPACE`, `IGNORE_SURROUNDING_SPACE`;
* `contains!()` (and `shwild_contains!()`);
* `starts_with!()` (and `shwild_starts_with!()`);
* `ends_with!()` (and `shwild_ends_with!()`);



<!-- ########################### end of file ########################### -->

