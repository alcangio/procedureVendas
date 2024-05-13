> [!NOTE]
> Planilha utilizada na atividade: [Supermaket sales](https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales).

# Desenvolvimento 3 #101836
Uma empresa de vendas tem um banco de dados com informações sobre os seus produtos. Para ajudar a empresa: 
- [ ] crie um *procedure* para que faça um levantamento diário da quantidade de produtos comprados por dia
### criando o *procedure*
```
DELIMITER //
CREATE PROCEDURE RelatorioDiarioCompras()
BEGIN
    SELECT Date, SUM(Quantity) as TotalComprasDiarias
    FROM supermarket_sales
    GROUP BY Date
    ORDER BY Date DESC;
END //
DELIMITER ;
```
![image](https://github.com/alcangio/procedureVendas/assets/142796669/97843671-d93f-4201-88e8-b925a13b5f14)
### chamando o *procedure*
```
CALL RelatorioDiarioCompras();
```
![image](https://github.com/alcangio/procedureVendas/assets/142796669/bdf440bc-bf41-4027-af08-102c5d6d26c9)
