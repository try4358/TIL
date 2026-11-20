# Convert number to reversed array of digits (8 kyu)

## 문제 설명
Given a random non-negative number, you have to return the digits of this number within an array in reverse order.

## 문제 풀이
```
#include <vector>

std::vector<int> digitize(unsigned long n)
{
	std::vector<int> ret;

	// 예외 : n이 0일때
	if (n == 0)
		return std::vector<int>(1, 0);

	while (n) {
		ret.push_back(n % 10);
		n /= 10;
	}

	return ret;
}
```
정수형으로 주어진 인수를 역으로 뒤집어 vector로 반환한다.

모든 자릿수를 탐색하기 때문에 O(N)의 시간복잡도를 갖는다.

주어진 n에서 자릿수를 추출할 때, 뒷자리부터 시작되므로 이 값을 바로
vector에 push_back해주면 자연스럽게 reverse된다고 생각했다.

다만, 인수가 0인 경우의 결과값을 생각하지 못했기 때문에, 예외 사항으로 분리하였다.

## 
