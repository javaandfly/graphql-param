## 获取币对名称数组
```
- param
        'query MyQuery {
            pairs {
                token0 {
                name
                }
            token1 {
                name
            }
            }
        }'
```
## 获取用户交易记录(分页)

- 币对 California Carbon Allowance Vintage 2022 Future <> usdt
  - California Carbon Allowance Vintage 2022 Future -> usdt
     ```
     query MyQuery {
  swaps(
    skip: 0
    first: 1000
    where: {pair_: {id: "0xa58ca32b40de2d1be8818968a58182ee86b2df7a"}, amount1Out_gt: "0"}
  ) {
    to
    amount0In
    amount0Out
    amount1Out
    amount1In
    timestamp
  }
}
    ```
  - usdt -> California Carbon Allowance Vintage 2022 Future
     ```
     query MyQuery {
  swaps(
    skip: 0
    first: 1000
    where: {pair_: {id: "0xa58ca32b40de2d1be8818968a58182ee86b2df7a"}, amount0Out_gt: "0"}
  ) {
    to
    amount0In
    amount0Out
    amount1Out
    amount1In
    timestamp
  }
}
    ```
- 币对 EUA Futures (Dec 2023) <> usdt
  - EUA Futures (Dec 2023) -> usdt
     ```
     query MyQuery {
        swaps(
        skip: 0
        first: 10
        orderBy: timestamp
        orderDirection: desc
        where: {pair_: {id: "0xe9fd2adc7ac2556da8fd2167b61f7c626895c3e4"}, amount1In_gt: "0"}
        ) {
        to
        amount0In
        amount0Out
        amount1In
        amount1Out
        timestamp
        }
        }
    ```
  - usdt -> EUA Futures (Dec 2023)
     ```
    query MyQuery {
        swaps(
        skip: 0
        first: 10
        orderBy: timestamp
        orderDirection: desc
        where: {pair_: {id: "0xe9fd2adc7ac2556da8fd2167b61f7c626895c3e4"}, amount0In_gt: "0"}
        ) {
        to
        amount0In
        amount0Out
        amount1In
        amount1Out
        timestamp
        }
        }
    ```
## 用户自己
  - California Carbon Allowance Vintage 2022 Future -> usdt
     ```
            query MyQuery {
                swaps(
                skip: 0
                first: 10
                orderBy: timestamp
                orderDirection: desc
                where: {pair_: {id: "0xa58ca32b40de2d1be8818968a58182ee86b2df7a"}, amount1In_gt: "0", to: "0x8f35eb07eb0d28ce75f5fa62cab367e74d084df6"}
                ) {
                    to
                    amount0In
                    amount0Out
                    amount1In
                    amount1Out
                    timestamp
                }
                }
        ```
  - usdt -> California Carbon Allowance Vintage 2022 Future

     ```

        query MyQuery {
            swaps(
            skip: 0
            first: 10
            orderBy: timestamp
            orderDirection: desc
            where: {pair_: {id: "0xa58ca32b40de2d1be8818968a58182ee86b2df7a"}, amount0In_gt: "0" to: "0x8f35eb07eb0d28ce75f5fa62cab367e74d084df6"}
        ) {
            to
            amount0In
            amount0Out
            amount1In
            amount1Out
            timestamp
        }
        }
        ```

  - EUA Futures (Dec 2023) -> usdt

     ```
        query MyQuery {
            swaps(
            skip: 0
            first: 10
            orderBy: timestamp
            orderDirection: desc
            where: {pair_: {id: "0xe9fd2adc7ac2556da8fd2167b61f7c626895c3e4"}, amount1In_gt: "0" to: "0x8f35eb07eb0d28ce75f5fa62cab367e74d084df6"}
            ) {
            to
            amount0In
            amount0Out
            amount1In
            amount1Out
            timestamp
            }
            }
        ```

  - usdt -> EUA Futures (Dec 2023)

     ```

       query MyQuery {
        swaps(
        skip: 0
        first: 10
        orderBy: timestamp
        orderDirection: desc
        where: {pair_: {id: "0xe9fd2adc7ac2556da8fd2167b61f7c626895c3e4"}, amount0In_gt: "0" to: "0x8f35eb07eb0d28ce75f5fa62cab367e74d084df6"}
        ) {
        to
        amount0In
        amount0Out
        amount1In
        amount1Out
        timestamp
        }
        }
    ```

