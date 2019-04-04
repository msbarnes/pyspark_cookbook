# PySpark Cookbook

Since 'Spark: The Definitive Guide' can be lacking detail or examples, and I frequently find myself needing to look up how to do something (especially if I've been working a lot in pandas), I'm writing this cookbook with snippets. Regular updates to follow, including a cookbook (and a benchmarking blog post to follow) on Spark ML.

## Select

## Count and Count Distinct

To perform counts in PySpark:

```
df.count()
```

To perform count distinct, you can select on one or many columns:

```
df.select('id').distinct().count()
```

or, say we wanted to get distinct id's by date:

```
df.select('id', 'date').distinct().count()
```

## Counting Null Values

To count null values or missing values:

```
df.select([count(when(isnan(c) | col(c).isNull(), c)).alias(c) for c in df.columns]).show()
```

## Filtering

## Sorting

## Aggregations

## Joins
