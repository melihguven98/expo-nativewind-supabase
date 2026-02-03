# Supabase Query Patterns

## Select
```typescript
const { data, error } = await supabase
  .from('table')
  .select('*')
  .eq('id', id)
  .single();
```

## Insert
```typescript
const { data, error } = await supabase
  .from('table')
  .insert({ name: 'value' })
  .select()
  .single();
```

## Update
```typescript
const { data, error } = await supabase
  .from('table')
  .update({ name: 'new' })
  .eq('id', id);
```

## Delete
```typescript
const { error } = await supabase
  .from('table')
  .delete()
  .eq('id', id);
```
