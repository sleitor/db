---
"@tanstack/db": patch
---

fix(db): infer non-nullable return type from first arg in `coalesce()`

`coalesce()` was typed as returning `BasicExpression<any>`, losing all type information when used in `.select()`. The signature now infers `T` from the first argument so the return type is `BasicExpression<NonNullable<ExtractType<T>>>`.
