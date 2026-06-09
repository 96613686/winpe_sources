# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_nohint<ComTaskHost * const &,std::_Nil>(bool,ComTaskHost * const &,std::_Nil)

- ea: `0x140005340`
- end: `0x140005641`
- name: `??$_Insert_nohint@AEBQEAVComTaskHost@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@std@@_N@1@_NAEBQEAVComTaskHost@@U_Nil@1@@Z`
- size: `769`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009610`

## callees

- `0x140005340`
- `0x140005650`
- `0x140005854`
- `0x1400070c0`
- `0x140008298`
- `0x140009ad0`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_nohint<ComTaskHost * const &,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  __int64 *v6; // rcx
  __int64 *v7; // rdx
  bool v8; // r14
  __int64 *v9; // rdi
  __int64 j; // rax
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 result; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 i; // rcx
  _QWORD *v23; // rax
  __int64 v24; // [rsp+60h] [rbp+8h] BYREF

  try
  {
    v6 = *a1;
    v7 = (__int64 *)v6[1];
    if ( *((_BYTE *)v7 + 25) )
    {
      v8 = 1;
      v9 = v6;
    }
    else
    {
      v19 = *a4;
      do
      {
        v9 = v7;
        v8 = v19 < v7[4];
        if ( v19 >= v7[4] )
          v7 = (__int64 *)v7[2];
        else
          v7 = (__int64 *)*v7;
      }
      while ( !*((_BYTE *)v7 + 25) );
    }
    j = (__int64)v9;
    if ( v8 )
    {
      if ( v9 == (__int64 *)*v6 )
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_at<ComTaskHost * const &,std::_Nil>(
                           a1,
                           &v24,
                           1,
                           v9,
                           a4);
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
      if ( *((_BYTE *)v9 + 25) )
      {
        j = v9[2];
      }
      else if ( *(_BYTE *)(*v9 + 25) )
      {
        for ( i = v9[1]; !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
        {
          if ( j != *(_QWORD *)i )
            break;
          j = i;
        }
        if ( !*(_BYTE *)(j + 25) )
          j = i;
      }
      else
      {
        for ( j = *v9; !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
          ;
      }
    }
    if ( *(_QWORD *)(j + 32) >= *a4 )
    {
      *(_QWORD *)a2 = j;
      *(_BYTE *)(a2 + 8) = 0;
      result = a2;
    }
    else
    {
      if ( (unsigned __int64)a1[1] >= 0x666666666666665LL )
        std::_Xlength_error("map/set<T> too long");
      v11 = std::_Tree_buy<ComTaskHost *>::_Buynode<ComTaskHost * const &>((__int64)a1, a4);
      v12 = v11;
      a1[1] = (__int64 *)((char *)a1[1] + 1);
      *(_QWORD *)(v11 + 8) = v9;
      if ( v9 == *a1 )
      {
        (*a1)[1] = v11;
        **a1 = v11;
        (*a1)[2] = v11;
      }
      else if ( v8 )
      {
        *v9 = v11;
        if ( v9 == (__int64 *)**a1 )
          **a1 = v11;
      }
      else
      {
        v9[2] = v11;
        if ( v9 == (__int64 *)(*a1)[2] )
          (*a1)[2] = v11;
      }
      v13 = v11;
      while ( !*(_BYTE *)(*(_QWORD *)(v13 + 8) + 24LL) )
      {
        v15 = *(_QWORD *)(v13 + 8);
        v16 = *(__int64 **)(v15 + 8);
        v17 = *v16;
        if ( v15 == *v16 )
        {
          v18 = v16[2];
          if ( *(_BYTE *)(v18 + 24) )
          {
            if ( v13 == *(_QWORD *)(v15 + 16) )
              std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(a1);
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 24LL) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 24LL) = 0;
            std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
              a1,
              *(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL));
          }
          else
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v18 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 24LL) = 0;
            v13 = *(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL);
          }
        }
        else if ( *(_BYTE *)(v17 + 24) )
        {
          if ( v13 == *(_QWORD *)v15 )
            std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
              a1,
              v15);
          *(_BYTE *)(*(_QWORD *)(v13 + 8) + 24LL) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 24LL) = 0;
          v20 = *(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL);
          v21 = *(_QWORD **)(v20 + 16);
          *(_QWORD *)(v20 + 16) = *v21;
          if ( !*(_BYTE *)(*v21 + 25LL) )
            *(_QWORD *)(*v21 + 8LL) = v20;
          v21[1] = *(_QWORD *)(v20 + 8);
          if ( v20 == (*a1)[1] )
          {
            (*a1)[1] = (__int64)v21;
          }
          else
          {
            v23 = *(_QWORD **)(v20 + 8);
            if ( v20 == *v23 )
              *v23 = v21;
            else
              v23[2] = v21;
          }
          *v21 = v20;
          *(_QWORD *)(v20 + 8) = v21;
        }
        else
        {
          *(_BYTE *)(v15 + 24) = 1;
          *(_BYTE *)(v17 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 24LL) = 0;
          v13 = *(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL);
        }
      }
      *(_BYTE *)((*a1)[1] + 24) = 1;
      *(_QWORD *)a2 = v12;
      *(_BYTE *)(a2 + 8) = 1;
      result = a2;
    }
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x140005340  push    rbx
0x140005342  push    rsi
0x140005343  push    rdi
0x140005344  push    r14
0x140005346  sub     rsp, 38h
0x14000534a  mov     rsi, rdx
0x14000534d  mov     rbx, rcx
0x140005350  mov     rcx, [rcx]
0x140005353  mov     rdx, [rcx+8]
0x140005357  cmp     byte ptr [rdx+19h], 0
0x14000535b  jz      loc_140005494
0x140005361  mov     r14b, 1
0x140005364  mov     rdi, rcx
0x140005367  mov     rax, rdi
0x14000536a  test    r14b, r14b
0x14000536d  jnz     loc_14000551B
0x140005373  mov     rcx, [r9]
0x140005376  cmp     [rax+20h], rcx
0x14000537a  jnb     short loc_1400053F8
0x14000537c  mov     rax, 666666666666665h
0x140005386  cmp     [rbx+8], rax
0x14000538a  jnb     loc_1400055AF
0x140005390  mov     rdx, r9
0x140005393  mov     rcx, rbx
0x140005396  call    ??$_Buynode@AEBQEAVComTaskHost@@@?$_Tree_buy@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@1@AEBQEAVComTaskHost@@@Z; std::_Tree_buy<ComTaskHost *>::_Buynode<ComTaskHost * const &>(ComTaskHost * const &)
0x14000539b  mov     r9, rax
0x14000539e  inc     qword ptr [rbx+8]
0x1400053a2  mov     [rax+8], rdi
0x1400053a6  mov     rax, [rbx]
0x1400053a9  cmp     rdi, rax
0x1400053ac  jz      loc_140005452
0x1400053b2  test    r14b, r14b
0x1400053b5  jnz     loc_1400055BB
0x1400053bb  mov     [rdi+10h], r9
0x1400053bf  mov     rax, [rbx]
0x1400053c2  cmp     rdi, [rax+10h]
0x1400053c6  jnz     short loc_1400053CC
0x1400053c8  mov     [rax+10h], r9
0x1400053cc  mov     r10, r9
0x1400053cf  mov     rax, [r9+8]
0x1400053d3  cmp     byte ptr [rax+18h], 0
0x1400053d7  jz      short loc_140005410
0x1400053d9  mov     rax, [rbx]
0x1400053dc  mov     rcx, [rax+8]
0x1400053e0  mov     byte ptr [rcx+18h], 1
0x1400053e4  mov     [rsi], r9
0x1400053e7  mov     byte ptr [rsi+8], 1
0x1400053eb  mov     rax, rsi
0x1400053ee  add     rsp, 38h
0x1400053f2  pop     r14
0x1400053f4  pop     rdi
0x1400053f5  pop     rsi
0x1400053f6  pop     rbx
0x1400053f7  retn
0x1400053f8  mov     [rsi], rax
0x1400053fb  mov     byte ptr [rsi+8], 0
0x1400053ff  mov     rax, rsi
0x140005402  jmp     short loc_1400053EE
0x140005410  mov     rdx, [r10+8]
0x140005414  mov     rcx, [rdx+8]
0x140005418  mov     rax, [rcx]
0x14000541b  cmp     rdx, rax
0x14000541e  jz      short loc_140005468
0x140005420  cmp     byte ptr [rax+18h], 0
0x140005424  jnz     loc_1400054B3
0x14000542a  mov     byte ptr [rdx+18h], 1
0x14000542e  mov     byte ptr [rax+18h], 1
0x140005432  mov     rax, [r10+8]
0x140005436  mov     rcx, [rax+8]
0x14000543a  mov     byte ptr [rcx+18h], 0
0x14000543e  mov     rax, [r10+8]
0x140005442  mov     r10, [rax+8]
0x140005446  mov     rax, [r10+8]
0x14000544a  cmp     byte ptr [rax+18h], 0
0x14000544e  jnz     short loc_1400053D9
0x140005450  jmp     short loc_140005410
0x140005452  mov     [rax+8], r9
0x140005456  mov     rcx, [rbx]
0x140005459  mov     [rcx], r9
0x14000545c  mov     rcx, [rbx]
0x14000545f  mov     [rcx+10h], r9
0x140005463  jmp     loc_1400053CC
0x140005468  mov     rax, [rcx+10h]
0x14000546c  cmp     byte ptr [rax+18h], 0
0x140005470  jnz     loc_1400055D2
0x140005476  mov     byte ptr [rdx+18h], 1
0x14000547a  mov     byte ptr [rax+18h], 1
0x14000547e  mov     rax, [r10+8]
0x140005482  mov     rcx, [rax+8]
0x140005486  mov     byte ptr [rcx+18h], 0
0x14000548a  mov     rax, [r10+8]
0x14000548e  mov     r10, [rax+8]
0x140005492  jmp     short loc_140005446
0x140005494  mov     r8, [r9]
0x140005497  mov     rdi, rdx
0x14000549a  cmp     r8, [rdx+20h]
0x14000549e  setb    r14b
0x1400054a2  jnb     short loc_140005515
0x1400054a4  mov     rdx, [rdx]
0x1400054a7  cmp     byte ptr [rdx+19h], 0
0x1400054ab  jnz     loc_140005367
0x1400054b1  jmp     short loc_140005497
0x1400054b3  cmp     r10, [rdx]
0x1400054b6  jz      loc_14000560C
0x1400054bc  mov     rax, [r10+8]
0x1400054c0  mov     byte ptr [rax+18h], 1
0x1400054c4  mov     rax, [r10+8]
0x1400054c8  mov     rcx, [rax+8]
0x1400054cc  mov     byte ptr [rcx+18h], 0
0x1400054d0  mov     rax, [r10+8]
0x1400054d4  mov     rdx, [rax+8]
0x1400054d8  mov     rcx, [rdx+10h]
0x1400054dc  mov     rax, [rcx]
0x1400054df  mov     [rdx+10h], rax
0x1400054e3  mov     rax, [rcx]
0x1400054e6  cmp     byte ptr [rax+19h], 0
0x1400054ea  jz      loc_14000561C
0x1400054f0  mov     rax, [rdx+8]
0x1400054f4  mov     [rcx+8], rax
0x1400054f8  mov     rax, [rbx]
0x1400054fb  cmp     rdx, [rax+8]
0x1400054ff  jnz     loc_140005625
0x140005505  mov     [rax+8], rcx
0x140005509  mov     [rcx], rdx
0x14000550c  mov     [rdx+8], rcx
0x140005510  jmp     loc_140005446
0x140005515  mov     rdx, [rdx+10h]
0x140005519  jmp     short loc_1400054A7
0x14000551b  cmp     rdi, [rcx]
0x14000551e  jnz     short loc_14000554A
0x140005520  mov     [rsp+58h+var_38], r9
0x140005525  mov     r9, rdi
0x140005528  mov     r8b, 1
0x14000552b  lea     rdx, [rsp+58h+arg_0]
0x140005530  mov     rcx, rbx
0x140005533  call    ??$_Insert_at@AEBQEAVComTaskHost@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@1@_NPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@1@AEBQEAVComTaskHost@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_at<ComTaskHost * const &,std::_Nil>(bool,std::_Tree_node<ComTaskHost *,void *> *,ComTaskHost * const &,std::_Nil)
0x140005538  mov     rax, [rax]
0x14000553b  mov     [rsi], rax
0x14000553e  mov     byte ptr [rsi+8], 1
0x140005542  mov     rax, rsi
0x140005545  jmp     loc_1400053EE
0x14000554a  cmp     byte ptr [rdi+19h], 0
0x14000554e  jz      short loc_140005559
0x140005550  mov     rax, [rdi+10h]
0x140005554  jmp     loc_140005373
0x140005559  mov     rcx, [rdi]
0x14000555c  cmp     byte ptr [rcx+19h], 0
0x140005560  jnz     short loc_140005586
0x140005562  mov     rax, rcx
0x140005565  mov     rcx, [rcx+10h]
0x140005569  cmp     byte ptr [rcx+19h], 0
0x14000556d  jnz     loc_140005373
0x140005573  mov     rax, [rax+10h]
0x140005577  mov     rcx, [rax+10h]
0x14000557b  cmp     byte ptr [rcx+19h], 0
0x14000557f  jz      short loc_140005573
0x140005581  jmp     loc_140005373
0x140005586  mov     rcx, [rdi+8]
0x14000558a  cmp     byte ptr [rcx+19h], 0
0x14000558e  jnz     short loc_1400055A2
0x140005590  cmp     rax, [rcx]
0x140005593  jnz     short loc_1400055A2
0x140005595  mov     rax, rcx
0x140005598  mov     rcx, [rcx+8]
0x14000559c  cmp     byte ptr [rcx+19h], 0
0x1400055a0  jz      short loc_140005590
0x1400055a2  cmp     byte ptr [rax+19h], 0
0x1400055a6  cmovz   rax, rcx
0x1400055aa  jmp     loc_140005373
0x1400055af  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x1400055b6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400055bb  mov     [rdi], r9
0x1400055be  mov     rax, [rbx]
0x1400055c1  cmp     rdi, [rax]
0x1400055c4  jnz     loc_1400053CC
0x1400055ca  mov     [rax], r9
0x1400055cd  jmp     loc_1400053CC
0x1400055d2  cmp     r10, [rdx+10h]
0x1400055d6  jnz     short loc_1400055E3
0x1400055d8  mov     r10, rdx
0x1400055db  mov     rcx, rbx
0x1400055de  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x1400055e3  mov     rax, [r10+8]
0x1400055e7  mov     byte ptr [rax+18h], 1
0x1400055eb  mov     rax, [r10+8]
0x1400055ef  mov     rcx, [rax+8]
0x1400055f3  mov     byte ptr [rcx+18h], 0
0x1400055f7  mov     rdx, [r10+8]
0x1400055fb  mov     rdx, [rdx+8]
0x1400055ff  mov     rcx, rbx
0x140005602  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140005607  jmp     loc_140005446
0x14000560c  mov     r10, rdx
0x14000560f  mov     rcx, rbx
0x140005612  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140005617  jmp     loc_1400054BC
0x14000561c  mov     [rax+8], rdx
0x140005620  jmp     loc_1400054F0
0x140005625  mov     rax, [rdx+8]
0x140005629  cmp     rdx, [rax]
0x14000562c  jnz     short loc_140005636
0x14000562e  mov     [rax], rcx
0x140005631  jmp     loc_140005509
0x140005636  mov     [rax+10h], rcx
0x14000563a  jmp     loc_140005509
```
