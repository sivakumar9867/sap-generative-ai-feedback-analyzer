# Sample Test Cases

## Purpose and Evidence Scope

This document catalogs the nine customer-feedback examples defined in:

`02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`

The examples are assessment sample inputs. They are not automatically treated as executed tests. Executed-test evidence is listed only where a repository screenshot visibly shows a corresponding Prompt Editor run or response.

The following distinctions are used:

- **Assessment sample input** — feedback text supplied by the assessment PDF.
- **Executed test evidence** — a screenshot visibly associated with a model run or response.
- **Partial or uncertain evidence** — a screenshot contains related content, but does not conclusively establish a complete response for the exact sample.
- **Assessment summary** — a concise description of the supplied feedback; it is not a generated model result.

No expected sentiment, category, department, priority, or JSON response is inferred.

## Relevant Schema Fields

For single-issue examples, the relevant documented schema fields are:

- `Feedback_ID`
- `Main_Category`
- `Customer_Sentiment`
- `Issue_Summary`
- `Order_Reference_ID`
- `Product_Reference`
- `Suggested_Department`
- `Actionable_Resolution_Points`

For multi-issue examples, the relevant documented schema fields are:

- `Feedback_ID`
- `Overall_Customer_Sentiment`
- `Issues`
- `Issue_ID`
- `Main_Category`
- `Customer_Sentiment_for_Issue`
- `Issue_Summary`
- `Order_Reference_ID`
- `Product_Reference`
- `Actionable_Resolution_Points`
- `Priority`

The field lists identify applicable schema fields only. They do not assign values to those fields.

## Test Case 1: Missing Item

**Status:** Assessment sample input.

**Source:** Assessment PDF, Task 1.3, printed p. 5.

**Subject:**

```text
My recent order #GGX56789 - missing item
```

**Assessment summary:** The customer received order `#GGX56789`, but the `Wireless Headphones` listed on the invoice were missing. The customer requests the missing item or an immediate refund.

**References:**

- Order reference: `#GGX56789`
- Product reference: `Wireless Headphones`

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** Partial or uncertain. `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png` shows a Prompt Editor Response panel and JSON-shaped content, but the available evidence does not conclusively establish that it is a complete executed response for this exact assessment sample. It is not treated as proof of automated validation.

## Test Case 2: Delivery Confusion

**Status:** Assessment sample input and executed comparison test.

**Source:** Assessment PDF, Task 3.1, printed p. 7.

**Subject:**

```text
Delivery confusion for order #GGX33445
```

**Assessment summary:** The `Premium Coffee Maker` for order `#GGX33445` was marked delivered two days ago, but the customer and neighbor did not receive it. The tracking link only says `delivered`. The customer requests an investigation with the shipping company and an update.

**References:**

- Order reference: `#GGX33445`
- Product reference: `Premium Coffee Maker`

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** Available as visual comparison evidence in:

- `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`
- `03_Screenshots/02-GPT-4.1-nano-Response.png`
- `03_Screenshots/03-GPT-5-Mini-Response.png`

The screenshots show model-response panels for the delivery comparison. They do not establish formal evaluation metrics or automated JSON validation.

## Test Case 3: Problems with Recent Order and Account

**Status:** Assessment sample input.

**Source:** Assessment PDF, Task 4.2, printed pp. 9–10.

**Subject:**

```text
Problems with my recent order and account!
```

**Assessment summary:** The customer describes two problems. The `Smart Coffee Maker` from order `#GGX88990` is defective and leaking, and the customer requests a replacement or full refund. The online account shows incorrect order history, the shipping address cannot be updated, and the customer requests account correction and return instructions.

**References:**

- Order reference: `#GGX88990`
- Product reference: `Smart Coffee Maker`

**Explicitly distinct issues:** 2:

1. Defective Smart Coffee Maker and replacement/refund request.
2. Incorrect account order history and inability to update the shipping address.

**Relevant schema fields:**

- Multi-issue header fields
- All eight issue-level fields

**Actual model response availability:** No complete executed response for this sample is available in the repository evidence.

## Test Case 4: Faulty Smart Blender

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed p. 9.

**Subject:**

```text
Faulty "Smart Blender" - Order #BLEND1234
```

**Assessment summary:** The `Smart Blender Pro X` from order `#BLEND1234` has a weak motor and stops during blending. The customer requests an immediate replacement or a full refund.

**References:**

- Order reference: `#BLEND1234`
- Product reference: `Smart Blender Pro X`

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** No actual model response is available in the repository evidence.

## Test Case 5: Lost Premium Coffee Subscription Package

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed pp. 9–10.

**Subject:**

```text
Where is my order #PKG5678? Tracking shows delivered but I have nothing!
```

**Assessment summary:** The `Premium Coffee Subscription` for order `#PKG5678` was marked delivered but was not received. The customer checked with neighbors and building management and requests an investigation, package location, or a replacement.

**References:**

- Order reference: `#PKG5678`
- Product reference: `Premium Coffee Subscription`

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** No actual model response is available in the repository evidence.

## Test Case 6: Website Payment Error

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed p. 10.

**Subject:**

```text
Cannot complete purchase - Payment Error on website
```

**Assessment summary:** The customer is attempting to purchase an `Ergonomic Office Chair` and accessories, but the website displays a generic payment error. The customer reports that the card works on other sites and asks for the payment gateway to be investigated.

**References:**

- Order reference: Not stated in the assessment sample.
- Product reference: `Ergonomic Office Chair` and accessories.

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** No actual model response is available in the repository evidence.

## Test Case 7: Eco-Friendly Tablet Case Compatibility

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed p. 10.

**Subject:**

```text
Question about "Eco-Friendly Tablet Case" compatibility
```

**Assessment summary:** The customer asks whether the `Eco-Friendly Tablet Case` is compatible with an older `TabPro 7` tablet from 2021 before making a purchase.

**References:**

- Order reference: Not stated in the assessment sample.
- Product reference: `Eco-Friendly Tablet Case`.
- Referenced device: `TabPro 7`.

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** No actual model response is available in the repository evidence.

## Test Case 8: Broken Headset and Duplicate Membership Charge

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed pp. 10–11.

**Subject:**

```text
Two problems: broken headset & duplicate charge for membership!
```

**Assessment summary:** The `Gaming Headset` from order `#GAME9012` has a broken microphone. The customer also reports a duplicate charge for `SimpleBest Premium Membership` and requests a headset fix and a refund of the duplicate charge.

**References:**

- Order reference: `#GAME9012`
- Product/reference: `Gaming Headset` and `SimpleBest Premium Membership`

**Explicitly distinct issues:** 2:

1. Broken Gaming Headset microphone.
2. Duplicate SimpleBest Premium Membership charge.

**Relevant schema fields:**

- Multi-issue header fields
- All eight issue-level fields

**Actual model response availability:** No actual model response is available in the repository evidence.

## Test Case 9: Incorrect Item Sent

**Status:** Assessment sample input.

**Source:** Assessment PDF, Sample Messages, printed p. 11.

**Subject:**

```text
Incorrect item sent - Order #CLOTH3456
```

**Assessment summary:** The customer ordered a `Blue Summer Dress, size Medium` under order `#CLOTH3456`, but received a `Red Winter Jacket, size Large`. The customer requests return instructions and either the correct dress or a full refund.

**References:**

- Order reference: `#CLOTH3456`
- Ordered product: `Blue Summer Dress, size Medium`
- Received product: `Red Winter Jacket, size Large`

**Explicitly distinct issues:** 1.

**Relevant schema fields:**

- Single-issue fields
- `Actionable_Resolution_Points`

**Actual model response availability:** No actual model response is available in the repository evidence.

## Summary Matrix

| # | Test case | Order reference | Product reference | Explicitly distinct issues | Assessment source | Actual response evidence |
|---|---|---|---|---:|---|---|
| 1 | Missing Item | `#GGX56789` | `Wireless Headphones` | 1 | Task 1.3, p. 5 | Partial or uncertain; screenshot 04 shows related Response content |
| 2 | Delivery Confusion | `#GGX33445` | `Premium Coffee Maker` | 1 | Task 3.1, p. 7 | Available; screenshots 01–03 |
| 3 | Problems with Recent Order and Account | `#GGX88990` | `Smart Coffee Maker` | 2 | Task 4.2, pp. 9–10 | Not available |
| 4 | Faulty Smart Blender | `#BLEND1234` | `Smart Blender Pro X` | 1 | Sample Messages, p. 9 | Not available |
| 5 | Lost Premium Coffee Subscription Package | `#PKG5678` | `Premium Coffee Subscription` | 1 | Sample Messages, pp. 9–10 | Not available |
| 6 | Website Payment Error | Not stated | `Ergonomic Office Chair` and accessories | 1 | Sample Messages, p. 10 | Not available |
| 7 | Eco-Friendly Tablet Case Compatibility | Not stated | `Eco-Friendly Tablet Case` | 1 | Sample Messages, p. 10 | Not available |
| 8 | Broken Headset and Duplicate Membership Charge | `#GAME9012` | `Gaming Headset` and `SimpleBest Premium Membership` | 2 | Sample Messages, pp. 10–11 | Not available |
| 9 | Incorrect Item Sent | `#CLOTH3456` | `Blue Summer Dress, size Medium`; `Red Winter Jacket, size Large` | 1 | Sample Messages, p. 11 | Not available |

## Evidence and Uncertainty Notes

- The nine examples are assessment sample inputs unless explicitly identified as executed comparison tests.
- Assessment samples do not provide expected model outputs.
- No sentiment labels, categories, department assignments, priorities, or JSON values are assigned in this document.
- Issue counts include only explicitly distinct problems described in the input.
- Test Case 1 is marked partial or uncertain because screenshot 04 shows a Response panel and JSON-shaped content, but the available evidence does not conclusively establish a complete executed response for that exact assessment sample.
- The presence of a response screenshot does not prove automated JSON validation.
