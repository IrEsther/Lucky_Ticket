# Lucky_Ticket
hw

int #include <stdio.h>

int countDigit(int number);
int power(int power);
int sumDigit(int number);
int isLuckyNumber(int number);

int main() {
	int number = 2457452;
	int res = isLuckyNumber(number);
	if (res == 1) {
		printf("Number %d is lucky", number);
	} else {
		printf("Number %d is NOT lucky", number);

	}

	return 0;
}

int isLuckyNumber(int number)

{
	int count = countDigit(number);
	int pow_10 = power(count / 2);
	int right = number % pow_10;
	int left = number / pow_10;
	if (count % 2 != 0) {
		left = left / 10;
	}
	int sumRight = sumDigit(right);
	int sumLeft = sumDigit(left);
	if (sumRight == sumLeft) {
		return 1;
	}

	return 0;
}
int countDigit(int number) {
	int count = 0;
	for (; number > 0; number = number / 10) {
		count++;
	}

	return count;
}
int power(int power) {
	int res = 1;
	for (; power > 0; power--) {
		res = res * 10;
	}
	return res;
}
int sumDigit(int number) {
	int res = 0;
	for (; number > 0; number /= 10) {
		res = res + number % 10;
	}
	return res;
}
