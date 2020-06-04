"DB First" Strategy

Apply migration (+ write defaults)
Push code changes where a column is no longer used
Apply migration **DROP COLUMN**

Apply migration **ADD COLUMN** (+ write defaults)
Push code changes where a new column is used
Apply migration (- write defaults)
  
-- requires to apply migrations one-by-one
-- does not violate standard migration/deployment workflows
-- stable, SHOULD BE USED

== vs ==

"Code First" Strategy

Push code changes (+ read defaults)
Apply migration **DROP COLUMN**
Push code changes (- read defaults)

Push code changes (+ read defaults)
Apply migration **ADD COLUMN**
Push code (- read defaults)

-- this requires to add commits on the fly
-- violates standard migration/deployment workflow
-- error-prone, SHOULD NOT BE USED
