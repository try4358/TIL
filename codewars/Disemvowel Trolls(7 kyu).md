# Disemvowel Trolls(7 kyu)

## 문제 설명
Trolls are attacking your comment section!

A common way to deal with this situation is to remove all of the vowels from the trolls' comments, neutralizing the threat.

Your task is to write a function that takes a string and return a new string with all vowels removed.

For example, the string "This website is for losers LOL!" would become "Ths wbst s fr lsrs LL!".

Note: for this kata y isn't considered a vowel.

## 문제 풀이
제목의 disemvowel의 뜻은 모음을 제거한다는 뜻이다.

영어의 모음은 a e i o u 5가지 이므로, 주어진 문자열 str의 요소를 for문으로 방문하여
a e i o u A E I O U 인 경우에는 제외해주면 된다.

```
#include <string>

std::string disemvowel(const std::string& str) {
	std::string ret;

	for (size_t i = 0; i < str.size(); i++) {
		if (str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || str[i] == 'o' || str[i] == 'u')
			continue;
		if (str[i] == 'A' || str[i] == 'E' || str[i] == 'I' || str[i] == 'O' || str[i] == 'U')
			continue;
		ret.push_back(str[i]);
	}
	return ret;
}
```

## 다른 풀이
```
# include <string>
# include <regex>
std::string disemvowel(std::string str)
{
  std::regex vowels("[aeiouAEIOU]");
  return std::regex_replace(str, vowels, "");
}
```
좋은 답변에서는 정규 표현식 regex를 이용했다.

정규 표현식 regex는 정해진 문자열 패턴을 규칙으로 정하고, 주어지는 문자열들이 이에 따르는지 **확인, 검색, 치환**할때 이용된다.

해당 문제에서는 std::regex vowels에 영어 모음(aeiouAEIOU)를 기준으로 **검색**해야할 문자들의 기준을 정하고,

std::regex_replace를 이용해 str에서 해당 vowels와 일치하면 ""로 **치환(사실 ""이기에 지우는 것)** 하게 된다.

## 작은 고찰
막상 C/C++의 기본문법으로 문제는 쉽게 풀 수 있었으나, 좋은 답변을 보면 C++을 다시 배우거나 더 배워야 한다는 생각이 들었다.

위의 정규 표현식에 대해 검색할 때, 씹어먹는 C++ 사이트에서 참고했는데, 좋은 강좌를 찾은 느낌이다.
