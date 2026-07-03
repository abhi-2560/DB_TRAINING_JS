I am giving and example of an e-commerce website

### Cases where soft deletes are necessary: Accounts

User accounts are commonly **soft deleted**, rather than immediately hard deleted.

Why?

* Order information, bills, and payments are required to be related for legal and financial reasons.
* The user might want to activate the account at a later date.
* Investigation into any transaction is required for customer service.
* Some business regulations require keeping records of transactions for a specified time frame.

How?

* In place of deleting the entire row, you can simply change the values of some fields:

  * deleted = true
  * deleted_at = '2026-07-03 10:15:00'

* Query normally does not display these records unless otherwise requested.

### Cases where hard deletes are better: Temporary session information

Session information, password reset tokens, or outdated shopping cart cache records should typically be hard deleted.

Why?

* These records do not have any long-term value for the business.
* These records only add up to the size of the database.
* Security risks arise from retaining old records unnecessarily.
* These records can easily be re-generated.
Implementation:

* Delete records from the database permanently using database DELETE functionality.