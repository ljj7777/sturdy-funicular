#include<stdio.h>
#include<stdlib.h>
#include<string.h>
struct s
{
	char name[100];  //名字
	int count;   //数量
	struct s* next;  
};
struct s* head = NULL;   //头
struct s* p=NULL, * tail=NULL;
void add(char name[100],int count);
void remove1(char name[100]);
void print();
void change(char name[100], int count);
void clean();
int totalcount();
void find(char name[100]);
void sort();
void combine();
void del(char name[100], int delall);
int main()
{
	int u=0;
	char name[100];
	int count;
	int shu;
	int f = 0;
	printf("您可以输入1到10数字进行操作，注意先输入商品！！\n");
	while (1)
	{	
		printf("请输入你想要的操作：\n 1:添加商品\n 2:移除商品\n 3:查看购物清单\n 4:修改商品数量\n 5:清空购物单\n 6:商品数总量\n 7:查找商品\n 8:排序商品\n 9:合并清单\n 10:删除商品\n 0:结束\n");
		scanf("%d", &shu);
		if (shu == 1)
		{
		while (1)//存入购买物品；
	{
		printf("请输入商品名和数量，以符合a表示结束！！\n");
		scanf("%s", name);
		if (strcmp(name,"a") == 0)//以a为结束
		{
			printf("操作完成\n");
			break;
		}
		scanf("%d", &count);
		add(name, count);
		u = 1;
	}
		}
		else if (shu == 2&&u==1)
		{
			char name1[100];
			printf("请输入你要移除的数据！\n");
			scanf("%s", name1);
			remove1(name1);
			printf("操作完成\n");
		}
		else if (shu == 3 && u == 1)
		{
			if (f == 1)
			{
				printf("无\n");
			}
			else
			{
			print();
			printf("\n操作完成\n");
			}

		}
		else if (shu == 4 && u == 1)
		{
			char name1[100];
			int count1;
			printf("请输入你要修改的数据！\n");
			scanf("%s", name1);
			printf("请输入你要修改的数量！\n");
			scanf("%d", &count1);
			change(name1, count1);
			printf("操作完成\n");
		}
		else if (shu == 5 && u == 1)
		{
			clean();
			printf("操作完成\n");
			f=1;
		}
		else if (shu == 6 && u == 1)
		{
			int x;
			x=totalcount();
			printf("总数为:%d\n", x);
		}
		else if (shu == 7 && u == 1)
		{
			char name1[100];
			printf("请输入你要查询的数据！\n");
			scanf("%s", name1);
			find(name1);
			printf("操作完成\n");
		}
		else if (shu == 8 && u == 1)
		{
			sort();
			printf("操作完成\n");
		}
		else if (shu == 9 && u == 1)
		{
			void combine();
			printf("经过宿舍讨论，没人能做出来，我也不例外\n");
			printf("操作完成\n");
		}
		else if (shu == 10 && u == 1)
		{
			char iname[100];
			int delall;
			printf("请输入你要查询的数据！\n");
			scanf("%s", iname);
			printf("请输入你是否要进行多次删除，输入0不是，1是！\n");
			scanf("%d", &delall);
			del(iname, delall);
			printf("操作完成\n");
		}
		else if (shu == 0)
		{
			break;
		}
		else
		{
			printf("您可能输入错误数字或为未进行存入数据！请重新操作！\n");
			break;
		}
	}

}
void add(char name[100], int count)//记录购买数据
{
	p = (struct s*)malloc(sizeof(struct s));
    p->next = NULL;
	strcpy(p->name, name);
	p->count=count;
	if (head == NULL)
	{
		head = p;
	}
	else
	{
		tail->next = p;
	}
	tail = p;
}
void remove1(char name[100])//移除数据
{
	struct s* p1 = NULL, * p2 = head;
	while (p2!=NULL)
	{
		if (strcmp(p2->name, name) == 0)
		{
			if (p1 != NULL)
			{
				p1->next = p2->next;
			}
			else
			{
				head = p2->next;
			}
			break;
		}
		p1 = p2;
		p2 = p2->next;
	}
}
void print()//打印链表内容
{
	struct s* p = head;
	printf("购物清单:\n");
	while (p != NULL)
	{
		printf("%s 数量: %d\n", p->name,p->count);
		p = p->next;
	}
}
void change(char name[100], int count)//修改商品数量
{
	struct s* p = head;
	while (p != NULL)
	{
		if (strcmp(p->name, name) == 0)
		{
			p->count = count;
			break;
		}
		p = p->next;
	}
}
void clean()//清空数据
{
	struct s* p=head,*p1=NULL;
	while (p != NULL)
	{
		p1 = p->next;
		free(p);
		p = p1;
	}
}
int totalcount()//计算总量
{
	struct s* p = head;
	int total = 0;
	while (p != NULL)
	{
		total = total + p->count;
		p = p->next;
	}
	return total;
}
void find(char name[100])//查找
{
	int k=0;
	struct s* p=head;
	printf("查找商品 \%s\ \n", name);
	while (p != NULL)
	{
		if (strcmp(p->name, name) == 0)
		{
			printf("%s 数量: %d\n", p->name, p->count);
			k = 1;
		}
		p = p->next;
	}
	if (k == 0)
	{
		printf("未找到“%s”", name);
	}
}
void sort()//商品排序
{
	struct s* p1 = head, * p2 = NULL;
	char tempname[100];
	int tempcount;
	while (p1 != NULL)
	{
		p2 = p1->next;
		while (p2 != NULL)
		{
			if (strcmp(p1->name, p2->name) > 0)
			{
				strcpy(tempname, p1->name);
				strcpy(p1->name, p2->name);
				strcpy(p2->name, tempname);
				tempcount = p1->count;
				p1->count = p2->count;
				p2->count = tempcount;
			}
			p2 = p2->next;
		}
		p1 = p1->next;
	}
}
void combine()//合并两个链表
{
	printf("经过宿舍讨论，没人能做出来，我也不例外");
}
void del(char name[100], int delall)//删除商品
{
	struct s* p2 = head,*p1 = NULL;
	while (p2 != NULL)
	{
		if (strcmp(p2->name, name) == 0)
		{
			if (p1 == NULL)
			{
				struct s* p3 = head;
				head = head->next;
				free(p3);
				if (!delall)break;
			}
			else
			{
				p1->next = p2->next;
				free(p2);
				p2 = p1->next;
				if (!delall)break;
			}
		}
		else
		{
			p1 = p2;
			p2 = p2->next;
		}
	}
}
