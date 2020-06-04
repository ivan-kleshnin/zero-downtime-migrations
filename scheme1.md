"DB First" Strategy

Apply migration **DROP COLUMN**
  -> old code breaks unless it has read defaults -- why would it?
Push code changes where the old column is not used
  -> new code is working...

Apply migration **ADD COLUMN** (+ write defaults)
  -> old code is working...
Push code changes where a new column is used
  -> new code is working...
  -> new db has extra write defaults

== vs ==

"Code First" Strategy

Push code changes where a column is no longer used
  -> new code breaks unless db has write defaults -- why would it?
Apply migration **DROP COLUMN**
  -> new code is working...

Push code changes (+ read defaults)
  -> new code is working...
Apply migration **ADD COLUMN**
  -> new code is working...
  -> new code has extra read defaults
