# DigitalFury — Manual QA Pet Project

An independent manual testing project focused on PC selection and shopping flows in the [DigitalFury online store](https://www.digitalfury.pro).

## Objective

Explore the website, identify unexpected behavior, and document findings with reproduction steps, actual results, expected results, and screenshots.

## Scope and Activities

- Manual exploratory testing of PC configurations, filters, sorting, and product comparison.
- Negative testing of cart quantities and checkout contact and delivery fields.
- Pairwise test design for CPU brand, CPU performance level, GPU performance level, and RAM.
- Defect reporting with proposed severity and priority assessments.

## Documentation

| Artifact | Contents |
|---|---|
| [Bug reports workbook](DigitalFury_Bug_Reports.xlsx) | 13 bug reports, a summary, and one separate UX observation |
| [Pairwise test workbook](DigitalFury_Pairwise.xlsx) | 10 test combinations, execution statuses, and notes |
| [Screenshots](screenshots/) | Evidence named by the related bug ID |

## Recorded Results

### Bug Reports

| Severity | Count |
|---|---:|
| Major | 7 |
| Minor | 6 |
| **Total** | **13** |

One additional UX observation concerns the unclear meaning of the performance levels “Добре”, “Краще”, and “Супер”. It is excluded from the bug count.

Severity and priority are QA assessments for this pet project, not classifications approved by the website owner.

### Pairwise Tests

| Status | Count |
|---|---:|
| Passed | 6 |
| Failed | 1 |
| Needs Investigation | 3 |
| **Total** | **10** |

The 10 combinations cover all 37 value pairs across the four parameters and their listed values. This is pairwise input coverage, not proof that every website behavior has been tested.

Tests 2, 5, and 10 returned no products. Further investigation is needed to determine whether matching products were unavailable or the filter excluded them incorrectly. An empty result set alone does not establish a filtering defect.

## Selected Findings

- PC configuration titles differ from the displayed CPU or chipset.
- Selecting Intel returns a PC card describing an AMD CPU.
- Sorting changes the displayed product count from 186 to 176.
- The cart accepts a negative quantity and displays a negative order total.
- Checkout accepts invalid contact and delivery values as described in the reports.

## Evidence and Limitations

Screenshots are stored in `screenshots/` and named with the related bug IDs. `DF-BUG-10to12.png` is shared by the email, full-name, and city reports.

The exact failing filter combination should be checked against its evidence: DF-BUG-04 and its screenshot show Intel / Good / Good / 8GB, while pairwise test 9 records Intel / Better / Better / 8GB. These may be separate reproductions, but the distinction has not been confirmed.

The attached negative-quantity screenshots show the cart and checkout states. They do not show the final order confirmation. Final order creation is reported in the bug workbook, but that outcome is not independently demonstrated by the attached screenshots.

No formal product requirements were available for hardware performance levels or compatible product types in comparison. Related expectations may require clarification.
