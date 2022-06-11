# Mutual Fund Securitization

Under the mutual fund securitization agreement, one party may provide monthly funding for the commission to brokers selling mutual fund units, up to one year. The purpose of the model is to determine, from a projected stream of future cashflows, whether all Commercial Paper used to fund the commissions to brokers for the sale of mutual funds will be repaid within a period. 

A broker charges the Partnership a commission on the net asset value of the mutual funds sold.  The buyer of the mutual funds, however, pays nothing up front; instead, a deferred sales charge, which depends on when the mutual funds are redeemed, is assessed.

The model assumes that the monthly net asset value of the mutual funds follows a deterministic process.  Administration and program fees, as well as mutual fund redemptions are then based on the monthly net asset value.  Issued Commercial Paper is amortized into equal monthly payments over a period of six years.  Here the cashflows generated from the administration and redemption fees are paid monthly to the Partnership, to be used for the payment of outstanding Commercial Paper and associated interest.  Furthermore, the model includes a test to determine whether a collateral infusion is required to aid in re-paying the Commercial Paper.

Based on the net value of all cashflows collected and paid by the Partnership, but without any discounting, the model yields a Boolean answer to the question of whether the Commercial Paper and associated interest are repaid.

The General Account collects monthly administrative and redemption fees and, if required, a collateral infusion amount.  This money is used to pay monthly program fees, as well as amortized principal and associated interest owed from issued Commercial Paper.  Any excess money is transferred to a Retention Account as future collateral.

Here monthly administration fees are set to a fixed percentage of the average of the respective current and previous month’s beginning mutual fund net asset values.  Program fees are similarly set to a fixed percentage of the current month’s beginning net asset value.  

Commissions to brokers from the sale of mutual fund units are funded on a monthly basis.  Each new funded amount is amortized into 72 equal monthly payments over six years.  Monthly interest is based on the remaining funded amount at the beginning of the month, multiplied by the monthly cost of Commercial Paper, and is paid from money in the General Account.  If the interest owed exceeds the General Account balance, then the unpaid interest is added to the remaining funded amount at the end of the month (i.e., unpaid interest is capitalized).

After the monthly interest obligations have been met, any remaining money in the General account, plus money in the Retention Account, is used to pay the required amortized amount.  Furthermore, in the event of a Lock-up, all money in the Retention Account is used immediately to pay down the remaining funded amount.  The Retention Account, is a collateral account, which is funded by the mutual funds.

The Retention Account holds collateral towards the repayment of Commercial Paper principal.  The Retention Account balance, at the beginning of a month, accrues based on a monthly reinvestment rate.  The balance at the end of the month includes this accrued amount plus the balance in the General Account (which may be negative if amortized principal obligations could not be met).  The month’s ending Retention Account balance is, however, compared against an upper bound for required collateral; if the month’s ending Retention Account balance exceeds the upper bound, then the positive difference from the upper bound is returned.

References:

https://finpricing.com/lib/EqSpread.html

https://osf.io/vzfaw/download
