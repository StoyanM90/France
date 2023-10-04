items_and_prices = input().split('|')
budget = float(input())

max_prices = {
    'Clothes': 50.00,
    'Shoes': 35.00,
    'Accessories': 20.50,
}

bought_items = []
total_profit = 0

for item_data in items_and_prices:
    item_price_parts = item_data.split('->')
    item = item_price_parts[0].strip()
    price = float(item_price_parts[1])

    if price <= max_prices.get(item, float('inf')) and budget >= price:
        bought_items.append(price)
        budget -= price
        total_profit += 0.4 * price

bought_items = [f'{price * 1.4:.2f}' for price in bought_items]
total_budget = budget + sum(float(price) for price in bought_items)
total_profit = round(total_profit, 2)

print(" ".join(bought_items))
print(f"Profit: {total_profit:.2f}")

if total_budget >= 150:
    print("Hello, France!")
else:
    print("Not enough money.")





