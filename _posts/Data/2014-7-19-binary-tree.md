---
layout: post
title: 二叉树
description: ""
categories: [data]
tags: [数据结构与算法]
---


二叉树

## 遍历方法：前，中，后，层遍历 ##

前：相对根节点为第一个
![](http://xiaolong.info/images/data/qian.jpg)

中：相对根节点为第二个
![](http://xiaolong.info/images/data/zhong.jpg)

后：相对根节点为第三个
![](http://xiaolong.info/images/data/hou.jpg)

层：相对根节点为第四个
![](http://xiaolong.info/images/data/floor.jpg)

####创建一个二叉树：一般用前序遍历方式 输入(  其他比较麻烦) 没有的用NULL来表示

	typedef char ElemType;
	
	typedef struct BinNode{
	    char data;
	    struct BiTNode *lchild,*rchild;
	
	}BiTNode,*BiTree;
	//创建一个二叉树
	CreateBiTree(BiTree *T){
	    char c;
	
	    scanf("%c",c);
	    if(' '==c){
	        *T=NULL;
	    }
	    else{
	        *T=(BiTNode *)malloc(sizeof(BiTNode));
	        (*T)->data=c;
	        CreateBiTree((*T)->lchild);//创建左孩子
	        CreateBiTree((*T->rchild));//创建右孩子
	    }
	}
	
	//访问二叉树的具体操作 
	visit(char c,int level){
	    printf("%c 位于第%d层\n",c,level);
	}
	//前序遍历二叉树
	PreOrderTraverse(BiTree T,int level){
	    if(T){
	        visit(T->data,level);
	        PreOrderTraverse(T->lchild,level+1);
	        PreOrderTraverse(T->rchild,level+1);
	
	    }
	}
	int main(){
	    int level =1;
	    BiTree T =NULL;
	
	    CreateBiTree(&T);
	    PreOrderTraverse(T,level);
	
	}
	
