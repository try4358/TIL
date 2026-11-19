# DNA to RNA Conversion

## 문제 설명
Deoxyribonucleic acid, DNA is the primary information storage molecule in biological systems.
It is composed of four nucleic acid bases Guanine ('G'), Cytosine ('C'), Adenine ('A'), and Thymine ('T').

Ribonucleic acid, RNA, is the primary messenger molecule in cells. RNA differs slightly from DNA its chemical structure and contains no Thymine.
In RNA Thymine is replaced by another nucleic acid Uracil ('U').

Create a function which translates a given DNA string into RNA.

## 풀이 방법
```
#include <string>

std::string DNAtoRNA(std::string dna) {
	for (int i = 0; i < dna.length(); i++) {
		if (dna[i] == 'T') {
			dna[i] = 'U';
		}
	}
	return dna;
}
```
DNA에서 RNA로 변경될 때, 'T'가 'U'로 변하기 때문에, 
인자로 받은 dna 문자열에서 T만 찾아서 U로 바꿔주면 된다.

## 다른 풀이방법
```
#include <string>
#include <algorithm>

std::string DNAtoRNA(std::string dna){
  std::replace(dna.begin(), dna.end(), 'T', 'U');
  return dna;
}
```

algorithm 헤더파일의 std::replace를 사용하면 위의 풀이법과 같은 동작을 수행한다.
