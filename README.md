#define _CRT_SECURE_NO_WARNINGS 
#include<stdio.h>
#include<stdlib.h>
#define open sizeof(struct Student)

struct Student
{
	int  num;
	struct Student* front;
	struct Student* next;
};
int n;
struct Student* creat()
{
	struct Student* head;
	head = NULL;
	struct Student* p1, * p2;
	n = 0;
	p1 = p2 = (struct Student*)malloc(open);
	scanf("%d", &p1->num);

	while (p1->num != 0)
	{
		n = n + 1;
		if (n == 1)
			head = p1;
		else
			(p2->next = p1, p1->front = p2);
		p2= p1;
		p1 = (struct Student*)malloc(open);
		scanf("%d", &p1->num);

	}
	p2->next = NULL;

	return(head);

}
int main()
{
	printf("请输入数据 \n");
	struct Student* p;
	p = creat();
	do {
		printf("num:%d\n", p->num);
		p = p->next;
	} while (p->num != 0);

	return 0;
}

