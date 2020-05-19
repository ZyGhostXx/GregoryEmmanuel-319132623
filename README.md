## 2. Exercícios de Funções Agregadas

1. Quais são os valores máximo e mínimo das seguintes colunas:
    * total
    * hp
    * ataque
    * defesa
    * ataque_especial
    * defesa_especial
    * velocidade
    * taxa_captura

```sql
Select Max(total), Max(hp), Max(ataque), Max(defesa), Max(ataque_especial), Max(defesa_especial), Max(velocidade), Max(taxa_captura), Min(hp), Min(ataque),Min(defesa),Min(ataque_especial), Min(defesa_especial),Min(velocidade),Min(taxa_captura),Min(total) FROM Pokemon;
```

2. Quantas cores diferentes possuem os pokémons?

```sql

Select count(distinct cor)  from Pokemon;

```

3. Qual é o peso médio dos pokémons?

```sql

Select avg(distinct peso_kg) from Pokemon;

```

4. Qual é a soma das alturas dos pokémons?

```sql

Select Sum(altura_m) from Pokemon;

```

5. Quantos pokémons estão cadastrados no banco de dados?

```sql

select count(nome) from Pokemon;

```

6. Qual é o altura média dos pokémons?

```sql

Select avg(altura_m) from Pokemon;

```

7. Qual é o desvio padrão do valor de HP dos pokémons?
```sql

Select Std(hp) from Pokemon;

```

8. Quantos pokémons possuem tipo2?

```sql

Select Count(nome) from Pokemon where tipo2 is not null;

```

9. Quantos são os diferentes tipos primários dos pokémons? 

```sql

Select Count(Distinct tipo1) from Pokemon;

```

10. Qual é a soma dos pesos dos pokémons?

```sql

Select Sum(peso_kg) from Pokemon;

```

11. Qual é a quantidade de Pokémons lendários e não lendários

```sql

Select lendario, Count(lendario) from Pokemon group by lendario order by Count(lendario) desc;

```

12. Qual é a quantidade de pokémons para cada uma das diferentes cores ordenadas decrescente?

```sql

Select cor, Count(cor) from Pokemon Group by cor order by Count(cor) desc;

```

13. Qual é a média de peso e altura de cada um dos tipos primários dos pokémons? Ordene os resultados decrescente respectivamente por média de peso e altura.
```sql

Select tipo1, avg(peso_kg), avg(altura_m) from Pokemon group by tipo1 order by avg(peso_kg) desc , avg(altura_m) desc;

```

14. Qual é a taxa de captura média por cor de cada um dos pokémons lendários?

```sql

Select cor, avg(taxa_captura) from Pokemon where lendario = true group by cor order by avg(taxa_captura) desc;

```

15. Qual os tipos primários que possuem a taxa de captura média acima de 100

```sql

Select tipo1, avg(taxa_captura) as 'Media' from Pokemon where 'Media_captura' > 100 group by tipo1 order by 'Media_captura' desc;

```

16. Agrupados por cor, quais pokémons não lendários possuem média total abaixo de 400

```sql

Select cor, avg(total) as 'Em_Media' from Pokemon where lendario = False and 'Media' < 400 group by cor order by avg(total) desc;

```

17. Qual o valor máximo total em cada uma das gerações?

```sql

Select Max(total), geracao from Pokemon group by geracao order by Max(total) desc;

```

18. Quantos pokémons lendários existem em cada uma das gerações?

```sql

Select geracao, Count(lendario) from Pokemon where lendario = true group by geracao order by Count(lendario) desc;

```

19. Em cada uma das gerações, quantos pokémons tem tipos primários e secundários e qual a taxa_captura média deles?

```sql

Select geracao, Count(tipo2), avg(taxa_captura) from Pokemon where tipo2 is not null group by geracao order by Count(tipo2) desc;

```

20. Qual é a quantidade de cores de cada um dos pokémons lendários em todas as gerações?

```sql

Select Count(distinct cor) from Pokemon order by Count(cor) desc;

```
