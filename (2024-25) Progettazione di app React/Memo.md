## React memorandum

### useEffect e dipendenze  
- `useEffect(callback, [])` → Eseguito **solo al primo render**.  
- `useEffect(callback, [state])` → Eseguito al primo render e quando `state` cambia.  
- `useEffect(callback)` → Eseguito a ogni render (quasi mai utile).  

> [!WARNING]
>
>  ⚠ Errore: Passare un oggetto/array ricreato a ogni render causa un loop infinito!

### supabase 

- Selezionare dati: 
  
  ```ts 
  const { data, error } = await supabase.from('meals').select('*');```
  ```
  
- Filtrare dati:  
  
  ```ts
  const { data, error } = await supabase.from('meals').select('*').eq('type', 'vegan');
  ```
  
- Ordinare dati: 
  ```ts
  const { data, error } = await supabase.from('meals').select('*').order('created_at', { ascending: false });
  ```
  
  Limitare dati:  
  
  ```ts
  const { data, error } = await supabase.from('meals').select('*').limit(5);
  ```

* Inserire dati:  
  ```ts 
  const { error } = await supabase.from('meals').insert([{ name: 'Pizza', type: 'vegetarian' }]);
  ```

- Aggiornare dati:  
  ```ts
   const { error } = await supabase.from('meals').update({ type: 'vegan' }).eq('id', 1);
  ```

- Eliminare dati:  
  ```ts 
  const { error } = await supabase.from('meals').delete().eq('id', 1);
  ```

- Caricare un file nello storage:  
  ```ts 
  const { error } = await supabase.storage.from('images').upload('meal.jpg', file);
  ```

- Ottenere URL pubblico di un file:  
  ``` ts
   const { data } = supabase.storage.from('images').getPublicUrl('meal.jpg');
  ```

- Login con email e password:  
  ```ts
   const { error } = await supabase.auth.signInWithPassword({ email, password });
  ```

- Logout:  
  ```ts
  await supabase.auth.signOut();
  ```

- Ottenere l'utente autenticato:  
  ```ts 
  const { data: user } = await supabase.auth.getUser();
  ```

  

Snippet inizializzazione: 

```ts
  //DB manager
  const supabaseManager: SupabaseManager = SupabaseManager.getInstance();

  // Effects (load meals)
  useEffect(() => {
    supabaseManager.getAllMeals().then((meals) => setMeals(meals));
    setIsLoading(false);
  }, []);
```

