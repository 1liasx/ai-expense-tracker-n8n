# Test Inputs

## 1. Normal PDF

Subject:

```text
Expense - Software Subscription
```

Body:

```text
Bonjour,

Veuillez trouver ma facture en pièce jointe.

Merci.
```

Attachment:

```text
clear-software-invoice.pdf
```

## 2. No Attachment

Subject:

```text
Expense - Missing Receipt
```

Body:

```text
Bonjour,

Voici ma demande de remboursement.

Merci.
```

Expected status:

```text
NO_ATTACHMENT
```

## 3. Unsupported File

Attach:

```text
receipt.txt
```

Expected status:

```text
UNSUPPORTED_FILE
```

## 4. Low Quality Image

Attach a blurry JPG or PNG where the amount is difficult to read.

Expected route:

```text
NEEDS_REVIEW or REJECTED_EXTRACTION
```

## 5. Missing Amount

Use a document containing a merchant and date but no valid total.

Expected status:

```text
REJECTED_EXTRACTION
```
