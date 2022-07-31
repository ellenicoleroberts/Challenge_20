<img src= "Images/banner.png" width="930" height="200">

# SMART CONTRACTS FOR JOINT SAVINGS ACCOUNTS

This Python script creates a Streamlit application to assist in hiring and paying FinTech professionals via Ethereum. The application permits the selection of a professional and specification of how many hours you wish to hire them for. After details are filled in, the applicaiton transacts the user's selection and pays the hired candidate accordingly.

---
## Technologies

This application leverages Python 3.7.2.

---
## Installation Guide

* Begin by cloning the GitHub repo (the same repo that this README.md file is contained within) into your terminal. 

*  Create a new environment and install the below listed dependencies. To do so, in your terminal while in this same repo, pass the following commands in order:

```python
conda create -n env_whatever_name python==3.7.2+ (i.e. any python version above 3.7.1)
conda activae env_whatever_name
pip install streamlit
pip install web3==5.17
pip install eth-tester==0.5.0b3
pip install mnemonic
pip install bip44
```
* Next, download [Ganache](https://www.trufflesuite.com/ganache).

* After installing and opening Ganache, copy the mnemonic phrase listed up top. For reference (the 12 words behind the black highlight):
<p style="text-align:center;"><img src="./Images/mnemonic.png" width="500" height="200"/></p>

* Create a '.env' file and within it paste the following: 
```bash
MNEMONIC = "(Whatever you copied from Ganache)"
```
* Within your terminal, navigate to the folder where you cloned the repo.

---
## Running the Code

* While in your terminal in this cloned repo, enter the following command:

```python
streamlit run fintech_finder.py
```
* A web browser window or tab will open. You will now be able to interact with the application.
---
## Usage

There are two Python scripts contained within this repo: **fintech_finder.py** and **crypto_wallet.py.** The first script runs the Streamlit code and imports various Etherum-based wallet functions from **crypto_wallet.py.**

The application first generates a new Ethereum account instance using the user's mnemonic seed phrase (created during the Installation section of the README.md detailed above). Next, the account balance associated with the user's Ethereum account address is fetched and displayed.

After the user selects their candidate to hire and how many hours they wish to hire them for, the total value of the Ethereum transaction, including the gas fee, is calculated 

The user then digitally signs the transaction to pay the candidate, and sends this transaction to the Ganache blockchain.

A transaction hash code associated with the validated blockchain transaction is generated below in the Streamlit sidebar.

For further confirmation, the user can navigate to the Transactions section of Ganache to review the blockchain transaction details. Here is an example of a successful transaction and the balance deducted from the user's account in Ganache:

![transaction example.](Images/transaction.png)
![user account example.](Images/account.png)

---
## Contributors

Nicole Roberts,
elle.nicole.roberts@gmail.com

---

## License

[BSD 3](https://choosealicense.com/licenses/bsd-3-clause-clear/): BSD 3-clause is a permissive licence, allowing nearly unlimited freedom with the software as long as BSD copyright and license notice is included.