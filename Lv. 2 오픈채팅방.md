[page](https://programmers.co.kr/learn/courses/30/lessons/42888)

    def solution(record):

        from collections import defaultdict
        nickname=defaultdict(str)

        result=[]
        for i in record:
            split=i.split()
            if len(split)<3:
                result.append([split[1],split[0]])
            elif len(split)==3 and split[0]!='Change':
                result.append([split[1], split[0]])
                nickname[split[1]]=split[2]
            elif len(split)==3 and split[0]=='Change':
                nickname[split[1]]=split[2]

        come_and_go=defaultdict(str)
        come_and_go['Enter']='들어왔습니다.'
        come_and_go['Leave']='나갔습니다.'

        answer=[]
        for i in result:
            answer.append(nickname[i[0]]+'님이 '+come_and_go[i[1]])

        return answer
