# Order respecting symbols

If you wish to respect symbols in sorts and your normal locale collation rules skip symbols, you can force C collation.

```sql
SELECT * FROM provinces ORDER BY name COLLATE "C"
```
