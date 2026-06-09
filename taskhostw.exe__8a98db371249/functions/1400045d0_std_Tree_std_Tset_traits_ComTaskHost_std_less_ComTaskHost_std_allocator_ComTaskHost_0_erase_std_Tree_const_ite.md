# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>>)

- ea: `0x1400045d0`
- end: `0x140004930`
- name: `?erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@2@V32@@Z`
- size: `864`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1400043a0`

## callees

- `0x1400045d0`
- `0x1400070c0`
- `0x14000733c`
- `0x1400082c4`
- `0x140009ad0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004706`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004706`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // r11
  _BYTE *v6; // r10
  _QWORD *v7; // rbp
  __int64 *v8; // r14
  char v9; // r9
  _QWORD *v10; // r15
  _QWORD *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  _BYTE *v15; // rax
  char v16; // dl
  __int64 v17; // rax
  __int64 i; // rdx
  _QWORD *v20; // rax
  _BYTE *v21; // rdx
  __int64 v22; // rcx

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3[2];
  v6 = a3;
  v7 = a3;
  v8 = a3 + 1;
  v9 = *(_BYTE *)(v5 + 25);
  v10 = a3 + 2;
  if ( v9 )
  {
    v11 = (_QWORD *)*v8;
    if ( !*(_BYTE *)(*v8 + 25) )
    {
      do
      {
        if ( a3 != (_QWORD *)v11[2] )
          break;
        a3 = v11;
        v11 = (_QWORD *)v11[1];
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
  }
  else
  {
    v11 = std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min((_QWORD *)v5);
  }
  if ( *(_BYTE *)(*(_QWORD *)v6 + 25LL) )
    goto LABEL_7;
  if ( v9 )
  {
    v5 = *(_QWORD *)v6;
    goto LABEL_7;
  }
  v5 = v11[2];
  if ( v11 == (_QWORD *)v6 )
  {
LABEL_7:
    v12 = *v8;
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v12;
    if ( *(_BYTE **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v5;
    }
    else if ( *(_BYTE **)v12 == v6 )
    {
      *(_QWORD *)v12 = v5;
    }
    else
    {
      *(_QWORD *)(v12 + 16) = v5;
    }
    if ( *(_BYTE **)*a1 == v6 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        v14 = v12;
      }
      else
      {
        v13 = *(_QWORD *)v5;
        if ( *(_BYTE *)(*(_QWORD *)v5 + 25LL) )
        {
          v14 = v5;
        }
        else
        {
          do
          {
            v14 = v13;
            v13 = *(_QWORD *)v13;
          }
          while ( !*(_BYTE *)(v13 + 25) );
        }
      }
      *(_QWORD *)*a1 = v14;
    }
    if ( *(_BYTE **)(*a1 + 16LL) == v6 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        i = v12;
      }
      else
      {
        for ( i = v5; !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
          ;
      }
      *(_QWORD *)(*a1 + 16LL) = i;
    }
    v15 = v7 + 3;
    goto LABEL_26;
  }
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = v11;
  *v11 = *(_QWORD *)v6;
  if ( v11 == (_QWORD *)*v10 )
  {
    v12 = (__int64)v11;
  }
  else
  {
    v12 = v11[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v12;
    *(_QWORD *)v12 = v5;
    v11[2] = *v10;
    *(_QWORD *)(*v10 + 8LL) = v11;
  }
  if ( *(_BYTE **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = v11;
  }
  else
  {
    v20 = (_QWORD *)*v8;
    if ( *(_BYTE **)*v8 == v6 )
      *v20 = v11;
    else
      v20[2] = v11;
  }
  v11[1] = *v8;
  v15 = v6 + 24;
  v16 = *((_BYTE *)v11 + 24);
  *((_BYTE *)v11 + 24) = v6[24];
  v6[24] = v16;
LABEL_26:
  if ( *v15 != 1 )
    goto LABEL_27;
  while ( v5 != *(_QWORD *)(*a1 + 8LL) && *(_BYTE *)(v5 + 24) == 1 )
  {
    v21 = *(_BYTE **)v12;
    if ( v5 == *(_QWORD *)v12 )
    {
      v21 = *(_BYTE **)(v12 + 16);
      if ( !v21[24] )
      {
        v21[24] = 1;
        *(_BYTE *)(v12 + 24) = 0;
        std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(
          (__int64)a1,
          v12);
        v21 = *(_BYTE **)(v12 + 16);
      }
      if ( !v21[25] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) != 1 || *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v21 + 24LL) = 1;
            v21[24] = 0;
            std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
              (__int64)a1,
              v21);
            v21 = *(_BYTE **)(v12 + 16);
          }
          v21[24] = *(_BYTE *)(v12 + 24);
          *(_BYTE *)(v12 + 24) = 1;
          *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) = 1;
          std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(
            (__int64)a1,
            v12);
          break;
        }
LABEL_65:
        v21[24] = 0;
      }
    }
    else
    {
      if ( !v21[24] )
      {
        v21[24] = 1;
        *(_BYTE *)(v12 + 24) = 0;
        std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
          (__int64)a1,
          (_QWORD *)v12);
        v21 = *(_BYTE **)v12;
      }
      if ( !v21[25] )
      {
        v22 = *((_QWORD *)v21 + 2);
        if ( *(_BYTE *)(v22 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v21 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) == 1 )
          {
            *(_BYTE *)(v22 + 24) = 1;
            v21[24] = 0;
            std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(
              (__int64)a1,
              (__int64)v21);
            v21 = *(_BYTE **)v12;
          }
          v21[24] = *(_BYTE *)(v12 + 24);
          *(_BYTE *)(v12 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v21 + 24LL) = 1;
          std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
            (__int64)a1,
            (_QWORD *)v12);
          break;
        }
        goto LABEL_65;
      }
    }
    v5 = v12;
    v12 = *(_QWORD *)(v12 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_27:
  operator delete(v6);
  v17 = a1[1];
  if ( v17 )
    a1[1] = v17 - 1;
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1400045d0  push    rsi
0x1400045d2  push    rdi
0x1400045d3  sub     rsp, 28h
0x1400045d7  cmp     byte ptr [r8+19h], 0
0x1400045dc  mov     rsi, rdx
0x1400045df  mov     rdi, rcx
0x1400045e2  jnz     loc_14000472B
0x1400045e8  mov     r11, [r8+10h]
0x1400045ec  mov     r10, r8
0x1400045ef  mov     [rsp+38h+arg_0], rbx
0x1400045f4  mov     [rsp+38h+arg_8], rbp
0x1400045f9  mov     rbp, r8
0x1400045fc  mov     [rsp+38h+arg_10], r14
0x140004601  lea     r14, [r8+8]
0x140004605  movzx   r9d, byte ptr [r11+19h]
0x14000460a  mov     [rsp+38h+var_18], r15
0x14000460f  lea     r15, [r8+10h]
0x140004613  test    r9b, r9b
0x140004616  jz      loc_140004738
0x14000461c  mov     rbx, [r14]
0x14000461f  cmp     byte ptr [rbx+19h], 0
0x140004623  jnz     short loc_140004638
0x140004625  cmp     r8, [rbx+10h]
0x140004629  jnz     short loc_140004638
0x14000462b  mov     r8, rbx
0x14000462e  mov     rbx, [rbx+8]
0x140004632  cmp     byte ptr [rbx+19h], 0
0x140004636  jz      short loc_140004625
0x140004638  mov     rax, [r10]
0x14000463b  cmp     byte ptr [rax+19h], 0
0x14000463f  jz      short loc_140004682
0x140004641  cmp     byte ptr [r11+19h], 0
0x140004646  mov     r9, [r14]
0x140004649  jz      loc_140004750
0x14000464f  mov     rax, [rdi]
0x140004652  cmp     [rax+8], r10
0x140004656  jnz     loc_140004759
0x14000465c  mov     [rax+8], r11
0x140004660  mov     rcx, [rdi]
0x140004663  cmp     [rcx], r10
0x140004666  jnz     short loc_1400046DA
0x140004668  cmp     byte ptr [r11+19h], 0
0x14000466d  jnz     short loc_1400046D4
0x14000466f  mov     r8, [r11]
0x140004672  cmp     byte ptr [r8+19h], 0
0x140004677  jz      loc_14000476F
0x14000467d  mov     rdx, r11
0x140004680  jmp     short loc_1400046D7
0x140004682  test    r9b, r9b
0x140004685  jnz     loc_140004748
0x14000468b  mov     r11, [rbx+10h]
0x14000468f  cmp     rbx, r10
0x140004692  jz      short loc_140004641
0x140004694  mov     [rax+8], rbx
0x140004698  mov     rax, [r10]
0x14000469b  mov     [rbx], rax
0x14000469e  cmp     rbx, [r15]
0x1400046a1  jnz     loc_1400047B3
0x1400046a7  mov     r9, rbx
0x1400046aa  mov     rax, [rdi]
0x1400046ad  cmp     [rax+8], r10
0x1400046b1  jnz     loc_1400047D8
0x1400046b7  mov     [rax+8], rbx
0x1400046bb  mov     rax, [r14]
0x1400046be  mov     [rbx+8], rax
0x1400046c2  lea     rax, [r10+18h]
0x1400046c6  movzx   ecx, byte ptr [rax]
0x1400046c9  movzx   edx, byte ptr [rbx+18h]
0x1400046cd  mov     [rbx+18h], cl
0x1400046d0  mov     [rax], dl
0x1400046d2  jmp     short loc_1400046EB
0x1400046d4  mov     rdx, r9
0x1400046d7  mov     [rcx], rdx
0x1400046da  mov     rcx, [rdi]
0x1400046dd  cmp     [rcx+10h], r10
0x1400046e1  jz      loc_140004783
0x1400046e7  lea     rax, [rbp+18h]
0x1400046eb  cmp     byte ptr [rax], 1
0x1400046ee  mov     r15, [rsp+38h+var_18]
0x1400046f3  mov     r14, [rsp+38h+arg_10]
0x1400046f8  mov     rbp, [rsp+38h+arg_8]
0x1400046fd  jz      loc_1400047F1
0x140004703  mov     rcx, r10
0x140004706  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000470c  mov     rax, [rdi+8]
0x140004710  test    rax, rax
0x140004713  jnz     loc_140004924
0x140004719  mov     [rsi], rbx
0x14000471c  mov     rax, rsi
0x14000471f  mov     rbx, [rsp+38h+arg_0]
0x140004724  add     rsp, 28h
0x140004728  pop     rdi
0x140004729  pop     rsi
0x14000472a  retn
0x14000472b  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x140004732  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x140004738  mov     rcx, r11
0x14000473b  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@SAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(std::_Tree_node<ComTaskHost *,void *> *)
0x140004740  mov     rbx, rax
0x140004743  jmp     loc_140004638
0x140004748  mov     r11, rax
0x14000474b  jmp     loc_140004641
0x140004750  mov     [r11+8], r9
0x140004754  jmp     loc_14000464F
0x140004759  cmp     [r9], r10
0x14000475c  jnz     short loc_140004766
0x14000475e  mov     [r9], r11
0x140004761  jmp     loc_140004660
0x140004766  mov     [r9+10h], r11
0x14000476a  jmp     loc_140004660
0x14000476f  mov     rax, [r8]
0x140004772  mov     rdx, r8
0x140004775  mov     r8, rax
0x140004778  cmp     byte ptr [rax+19h], 0
0x14000477c  jz      short loc_14000476F
0x14000477e  jmp     loc_1400046D7
0x140004783  cmp     byte ptr [r11+19h], 0
0x140004788  jz      short loc_14000478F
0x14000478a  mov     rdx, r9
0x14000478d  jmp     short loc_1400047AA
0x14000478f  mov     rax, [r11+10h]
0x140004793  mov     rdx, r11
0x140004796  cmp     byte ptr [rax+19h], 0
0x14000479a  jnz     short loc_1400047AA
0x14000479c  mov     rdx, [rdx+10h]
0x1400047a0  mov     rax, [rdx+10h]
0x1400047a4  cmp     byte ptr [rax+19h], 0
0x1400047a8  jz      short loc_14000479C
0x1400047aa  mov     [rcx+10h], rdx
0x1400047ae  jmp     loc_1400046E7
0x1400047b3  cmp     byte ptr [r11+19h], 0
0x1400047b8  mov     r9, [rbx+8]
0x1400047bc  jnz     short loc_1400047C2
0x1400047be  mov     [r11+8], r9
0x1400047c2  mov     [r9], r11
0x1400047c5  mov     rax, [r15]
0x1400047c8  mov     [rbx+10h], rax
0x1400047cc  mov     rax, [r15]
0x1400047cf  mov     [rax+8], rbx
0x1400047d3  jmp     loc_1400046AA
0x1400047d8  mov     rax, [r14]
0x1400047db  cmp     [rax], r10
0x1400047de  jnz     short loc_1400047E8
0x1400047e0  mov     [rax], rbx
0x1400047e3  jmp     loc_1400046BB
0x1400047e8  mov     [rax+10h], rbx
0x1400047ec  jmp     loc_1400046BB
0x1400047f1  mov     rax, [rdi]
0x1400047f4  cmp     r11, [rax+8]
0x1400047f8  jz      loc_14000491A
0x1400047fe  cmp     byte ptr [r11+18h], 1
0x140004803  jnz     loc_14000491A
0x140004809  mov     rdx, [r9]
0x14000480c  cmp     r11, rdx
0x14000480f  jnz     loc_140004899
0x140004815  mov     rdx, [r9+10h]
0x140004819  cmp     byte ptr [rdx+18h], 0
0x14000481d  jnz     short loc_140004837
0x14000481f  mov     byte ptr [rdx+18h], 1
0x140004823  mov     rcx, rdi
0x140004826  mov     rdx, r9
0x140004829  mov     byte ptr [r9+18h], 0
0x14000482e  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140004833  mov     rdx, [r9+10h]
0x140004837  cmp     byte ptr [rdx+19h], 0
0x14000483b  jnz     loc_1400048D3
0x140004841  mov     r8, [rdx]
0x140004844  cmp     byte ptr [r8+18h], 1
0x140004849  jnz     short loc_140004855
0x14000484b  mov     rax, [rdx+10h]
0x14000484f  cmp     byte ptr [rax+18h], 1
0x140004853  jz      short loc_1400048CF
0x140004855  mov     rax, [rdx+10h]
0x140004859  cmp     byte ptr [rax+18h], 1
0x14000485d  jnz     short loc_140004874
0x14000485f  mov     byte ptr [r8+18h], 1
0x140004864  mov     rcx, rdi
0x140004867  mov     byte ptr [rdx+18h], 0
0x14000486b  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140004870  mov     rdx, [r9+10h]
0x140004874  movzx   eax, byte ptr [r9+18h]
0x140004879  mov     rcx, rdi
0x14000487c  mov     [rdx+18h], al
0x14000487f  mov     byte ptr [r9+18h], 1
0x140004884  mov     rax, [rdx+10h]
0x140004888  mov     rdx, r9
0x14000488b  mov     byte ptr [rax+18h], 1
0x14000488f  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140004894  jmp     loc_14000491A
0x140004899  cmp     byte ptr [rdx+18h], 0
0x14000489d  jnz     short loc_1400048B6
0x14000489f  mov     byte ptr [rdx+18h], 1
0x1400048a3  mov     rcx, rdi
0x1400048a6  mov     rdx, r9
0x1400048a9  mov     byte ptr [r9+18h], 0
0x1400048ae  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x1400048b3  mov     rdx, [r9]
0x1400048b6  cmp     byte ptr [rdx+19h], 0
0x1400048ba  jnz     short loc_1400048D3
0x1400048bc  mov     rcx, [rdx+10h]
0x1400048c0  cmp     byte ptr [rcx+18h], 1
0x1400048c4  jnz     short loc_1400048DF
0x1400048c6  mov     rax, [rdx]
0x1400048c9  cmp     byte ptr [rax+18h], 1
0x1400048cd  jnz     short loc_1400048DF
0x1400048cf  mov     byte ptr [rdx+18h], 0
0x1400048d3  mov     r11, r9
0x1400048d6  mov     r9, [r9+8]
0x1400048da  jmp     loc_1400047F1
0x1400048df  mov     rax, [rdx]
0x1400048e2  cmp     byte ptr [rax+18h], 1
0x1400048e6  jnz     short loc_1400048FB
0x1400048e8  mov     byte ptr [rcx+18h], 1
0x1400048ec  mov     rcx, rdi
0x1400048ef  mov     byte ptr [rdx+18h], 0
0x1400048f3  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x1400048f8  mov     rdx, [r9]
0x1400048fb  movzx   eax, byte ptr [r9+18h]
0x140004900  mov     rcx, rdi
0x140004903  mov     [rdx+18h], al
0x140004906  mov     byte ptr [r9+18h], 1
0x14000490b  mov     rax, [rdx]
0x14000490e  mov     rdx, r9
0x140004911  mov     byte ptr [rax+18h], 1
0x140004915  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x14000491a  mov     byte ptr [r11+18h], 1
0x14000491f  jmp     loc_140004703
0x140004924  dec     rax
0x140004927  mov     [rdi+8], rax
0x14000492b  jmp     loc_140004719
```
