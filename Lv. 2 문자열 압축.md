[page](https://programmers.co.kr/learn/courses/30/lessons/60057)

    def solution(s):    

        result_len=[]
        for i in range(1,len(s)//2+1):
            if len(s)==1:
                break
            result=[]
            count=1
            for j in range(0,len(s),i):
                if s[j:j+i]==s[j+i:j+i+i]:
                    count+=1
                else:
                    result.append(count)
                    result.append(s[j:j+i])
                    count=1
            while 1 in result:
                result.remove(1)
            result=''.join(map(str,result))
            result_len.append(len(result))

        if len(s)==1:
            result_len.append(len(s))

        answer=min(result_len)
        return answer
