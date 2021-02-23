# Operators

An **operator** is a statement that evaluates some code, and makes a decision about what to do next. Operators can be used for comparing two values, inspecting a single value, or evaluating whether or not some code returns `true`.

## Comparison operators

If `b = 6`, the table below illustrates the comparison operators and the way they interact with `b`:

| Operator | Description | Example | Result |
| :--- | :--- | :--- | :--- |
| `==` | equal to | `b == 6` | `true` |
| `!=` | not equal | `b != 6` | `false` |
| `>` | greater than  | `b > 5` | `true` |
| `<` | less than | `b < 6` | `false` |
| `>=` | greater than or equal to | `b >= 6` | `true` |
| `<=` | less than or equal to | `b <= 6` | `true` |

### Examples

```javascript
{% assign order_qualifies = false %}

{% if order.cancelled_at == blank and cancel_risk %}
  {% assign order_qualifies = true %}
{% endif %}
```

```javascript
{% if has_product != true %}
  {% log "Order has no products; skipping" %}
  {% assign send_email = false %}
{% endif %}
```

## Contains operator

The `contains` operator is used to check for the existence of a substring in a string, or for a specific element in an array.

### Substring containment

```javascript
{% if email_domain contains "@" %}
  {% error "Do not include '@' symbols in email domains. Thanks!" %}
{% endif %}
```

### Array element containment 

```javascript
{% assign product_tags = "foo, bar, baz" | split: ", " %}
{% assign product_is_tagged_bar = false %}

{% if product_tags contains "bar" %}
  {% assign product_is_tagged_bar = true %}
{% endif %}
```

## Logical operators

Liquid has two logical operators: `and` and `or`.

If `b = 3` and `c = 6`, the table below illustrates the logical operators in Liquid, and the way they interact with `b` and `b`:

| Operator | Example | Result |
| :--- | :--- | :--- |
| `and` | `b < 2 and c < 6` | `false` |
| `or` | `b < 2 or c < 6` | `true` |

### Check if both the shipping address and billing are blank

```javascript
{% if order.shipping_address != blank and order.billing_address != blank %}
  {% comment %} do something {% endcomment %}
{% endif %}
```

### Check if tag equals blank or a customer's tags contains a certain tag

```javascript
{% if tag == blank or customer.tags contains tag %}
  {% comment %} do something {% endcomment %}
{% endif %}
```
