# 완전 탐색
## 모의고사 LV1

**문제 설명**
수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.

1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...
2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...
3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...

1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.

**제한 조건**
- 시험은 최대 10,000 문제로 구성되어있습니다.
- 문제의 정답은 1, 2, 3, 4, 5중 하나입니다.
- 가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.


**입출력 예**
```
answers	        return
[1,2,3,4,5]	[1]
[1,3,2,4,2]	[1,2,3]
```


**입출력 예 설명**


입출력 예 #1

- 수포자 1은 모든 문제를 맞혔습니다.
- 수포자 2는 모든 문제를 틀렸습니다.
- 수포자 3은 모든 문제를 틀렸습니다.
따라서 가장 문제를 많이 맞힌 사람은 수포자 1입니다.

입출력 예 #2

- 모든 사람이 2문제씩을 맞췄습니다.

```kt
class Solution {
    fun solution(answers: IntArray): IntArray {
        var answer = intArrayOf()
        var highScore = arrayListOf<Int>() //최고 점수
        var highScorePeople = arrayListOf<Int>() //가장 맞힌 사람
        var fst = arrayListOf(1,2,3,4,5) //첫번째 사람의 찍기 패턴
        var scd = arrayListOf(2,1,2,3,2,4,2,5) //두번째 사람의 찍기 패턴
        var thd = arrayListOf(3,3,1,1,2,2,4,4,5,5) //세번째 사람의 찍기 패턴
        var fstCorrect = 0
        var scdCorrect = 0
        var thdCorrect = 0

        //패턴에 문제가 들어맞으면 OOOCorrect++
        for(i in answers){
            if(i == fst[0]){
                fstCorrect++
            }
            if(i == scd[0]){
                scdCorrect++
            }
            if(i == thd[0]){
                
                thdCorrect++
            }

            //마지막 문제에 도달하기 전까지 0번째 인덱스 -> 마지막 인덱스, 0번째 인덱스 지우기
            fst.add(fst[0])
            scd.add(scd[0])
            thd.add(thd[0])
            fst.removeAt(0)
            scd.removeAt(0)
            thd.removeAt(0)
            
        }

        //가장 문제를 많이 맞힌 사람 찾기
        highScore = arrayListOf(fstCorrect,scdCorrect,thdCorrect)
        highScore[0] = highScore.max()!!.toInt()
        if(highScore[0] == fstCorrect){
            highScorePeople.add(1)
        }
        if(highScore[0] == scdCorrect){
            highScorePeople.add(2)
        }
        if(highScore[0] == thdCorrect){
            highScorePeople.add(3)
        }
        answer = highScorePeople.toIntArray()
        return answer
    }
}
```