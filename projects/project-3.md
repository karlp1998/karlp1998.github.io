---
layout: project
type: project
image: images/cpppic.jpg
title: ICS 212 Project 
# All dates must be YYYY-MM-DD format!
date: 2021-01-21
labels:
  - C++
  - User Interface
summary: A mid-term project for ICS 212 
---
For this project, I had to create a program that calculated the total amount of money someone has made over a year, taking into account state and/or federal taxes. Although this was a pretty simple program, writing in a new language was a bit hard at first, but overall we can benefit from learning new languages to develop our skills in Computer Science/Programming.

#include <iostream>;
	
using namespace std;

// Const values for federl and state taxes

const double FEDERALTAX = .085;

const double STATETAX = .145;

double annualIncome() {

	int jobs;
	
	double total = 0;
	
	double moneyMade;
	
	double fedTaxTotal;
	
	double stateTaxTotal;
	
	// Ask the user for the amount of jobs hey currently have
	
	cout << "Enter amount of jobs you currently have: " << endl;
	
	cin >> jobs; 

	// I decided to use a for loop so it'll loop the same amount of times to the amount of jobs that the user has
	for (int i = 0; i < jobs; i++) {
		// Ask the user for the amount of money they made for each job
		cout << "Enter amount of money made for job #" << i + 1 << endl;
		cin >> moneyMade;
		// Add the amount of moneyMade to the total
		total += moneyMade;
		// If they enter a negative value, let the user know and break
		if (moneyMade <= 0) {
			cout << "You entered an insufficient amount." << endl;
			break;
		}

	}
	// Calculate the federal tax for the total amount of money the user has made
	fedTaxTotal = total * FEDERALTAX;
	cout << "Your total federal tax deductions amount to $" << fedTaxTotal << "." << endl;
	// Calculate the state tax for the total amount of money the user has made
	stateTaxTotal = total * STATETAX;
	cout << "Your total state tax deductions amount to $" << stateTaxTotal << "." << endl;
	// Deduct the taxes from the total and print it out. 
	total = total - fedTaxTotal - stateTaxTotal;
	cout << "Your total income is $" << total << endl;

	return total;
}

int main() {

	annualIncome();

	return 0;
}



