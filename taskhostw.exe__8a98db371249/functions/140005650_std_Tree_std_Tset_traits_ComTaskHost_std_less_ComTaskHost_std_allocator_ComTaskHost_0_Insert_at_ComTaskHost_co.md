# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_at<ComTaskHost * const &,std::_Nil>(bool,std::_Tree_node<ComTaskHost *,void *> *,ComTaskHost * const &,std::_Nil)

- ea: `0x140005650`
- end: `0x14000584c`
- name: `??$_Insert_at@AEBQEAVComTaskHost@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@1@_NPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@1@AEBQEAVComTaskHost@@U_Nil@1@@Z`
- size: `508`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, char, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005340`

## callees

- `0x140005650`
- `0x140005854`
- `0x1400070c0`
- `0x140008298`
- `0x140009ad0`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_at<ComTaskHost * const &,std::_Nil>(
        _QWORD *a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        _QWORD *a5)
{
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 *result; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // rax

  if ( a1[1] >= 0x666666666666665uLL )
    std::_Xlength_error("map/set<T> too long");
  v9 = std::_Tree_buy<ComTaskHost *>::_Buynode<ComTaskHost * const &>((__int64)a1, a5);
  ++a1[1];
  v10 = v9;
  *(_QWORD *)(v9 + 8) = a4;
  if ( a4 == (__int64 *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = v9;
    *(_QWORD *)*a1 = v9;
    v11 = *a1;
LABEL_5:
    *(_QWORD *)(v11 + 16) = v10;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    a4[2] = v9;
    v11 = *a1;
    if ( a4 != *(__int64 **)(*a1 + 16LL) )
      goto LABEL_6;
    goto LABEL_5;
  }
  *a4 = v9;
  if ( a4 == *(__int64 **)*a1 )
    *(_QWORD *)*a1 = v9;
LABEL_6:
  v12 = v10;
  while ( !*(_BYTE *)(*(_QWORD *)(v12 + 8) + 24LL) )
  {
    v16 = *(_QWORD *)(v12 + 8);
    v17 = *(__int64 **)(v16 + 8);
    v18 = *v17;
    if ( v16 == *v17 )
    {
      v19 = v17[2];
      if ( *(_BYTE *)(v19 + 24) )
      {
        if ( v12 == *(_QWORD *)(v16 + 16) )
          std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(a1);
        *(_BYTE *)(*(_QWORD *)(v12 + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL) + 24LL) = 0;
        std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL));
      }
      else
      {
        *(_BYTE *)(v16 + 24) = 1;
        *(_BYTE *)(v19 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL) + 24LL) = 0;
        v12 = *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL);
      }
    }
    else if ( *(_BYTE *)(v18 + 24) )
    {
      if ( v12 == *(_QWORD *)v16 )
        std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(
          a1,
          v16);
      *(_BYTE *)(*(_QWORD *)(v12 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL) + 24LL) = 0;
      v20 = *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL);
      v21 = *(_QWORD **)(v20 + 16);
      *(_QWORD *)(v20 + 16) = *v21;
      if ( !*(_BYTE *)(*v21 + 25LL) )
        *(_QWORD *)(*v21 + 8LL) = v20;
      v21[1] = *(_QWORD *)(v20 + 8);
      if ( v20 == *(_QWORD *)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v21;
      }
      else
      {
        v22 = *(_QWORD **)(v20 + 8);
        if ( v20 == *v22 )
          *v22 = v21;
        else
          v22[2] = v21;
      }
      *v21 = v20;
      *(_QWORD *)(v20 + 8) = v21;
    }
    else
    {
      *(_BYTE *)(v16 + 24) = 1;
      *(_BYTE *)(v18 + 24) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL) + 24LL) = 0;
      v12 = *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL);
    }
  }
  v13 = *a1;
  *a2 = v10;
  v14 = *(_QWORD *)(v13 + 8);
  result = a2;
  *(_BYTE *)(v14 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x140005650  push    rbx
0x140005652  push    rbp
0x140005653  push    rsi
0x140005654  push    rdi
0x140005655  sub     rsp, 28h
0x140005659  mov     rax, 666666666666665h
0x140005663  mov     rsi, r9
0x140005666  movzx   ebp, r8b
0x14000566a  mov     rdi, rdx
0x14000566d  mov     rbx, rcx
0x140005670  cmp     [rcx+8], rax
0x140005674  jnb     loc_1400057BB
0x14000567a  mov     rdx, [rsp+48h+arg_20]
0x14000567f  call    ??$_Buynode@AEBQEAVComTaskHost@@@?$_Tree_buy@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@1@AEBQEAVComTaskHost@@@Z; std::_Tree_buy<ComTaskHost *>::_Buynode<ComTaskHost * const &>(ComTaskHost * const &)
0x140005684  inc     qword ptr [rbx+8]
0x140005688  mov     r9, rax
0x14000568b  mov     [rax+8], rsi
0x14000568f  mov     rax, [rbx]
0x140005692  cmp     rsi, rax
0x140005695  jz      loc_14000571E
0x14000569b  test    bpl, bpl
0x14000569e  jnz     loc_1400057C8
0x1400056a4  mov     [rsi+10h], r9
0x1400056a8  mov     rax, [rbx]
0x1400056ab  cmp     rsi, [rax+10h]
0x1400056af  jnz     short loc_1400056B5
0x1400056b1  mov     [rax+10h], r9
0x1400056b5  mov     rax, [r9+8]
0x1400056b9  mov     r10, r9
0x1400056bc  cmp     byte ptr [rax+18h], 0
0x1400056c0  jz      short loc_1400056E0
0x1400056c2  mov     rax, [rbx]
0x1400056c5  mov     [rdi], r9
0x1400056c8  mov     rcx, [rax+8]
0x1400056cc  mov     rax, rdi
0x1400056cf  mov     byte ptr [rcx+18h], 1
0x1400056d3  add     rsp, 28h
0x1400056d7  pop     rdi
0x1400056d8  pop     rsi
0x1400056d9  pop     rbp
0x1400056da  pop     rbx
0x1400056db  retn
0x1400056e0  mov     rdx, [r10+8]
0x1400056e4  mov     rcx, [rdx+8]
0x1400056e8  mov     rax, [rcx]
0x1400056eb  cmp     rdx, rax
0x1400056ee  jz      short loc_14000572D
0x1400056f0  cmp     byte ptr [rax+18h], 0
0x1400056f4  jnz     short loc_140005759
0x1400056f6  mov     byte ptr [rdx+18h], 1
0x1400056fa  mov     byte ptr [rax+18h], 1
0x1400056fe  mov     rax, [r10+8]
0x140005702  mov     rcx, [rax+8]
0x140005706  mov     byte ptr [rcx+18h], 0
0x14000570a  mov     rax, [r10+8]
0x14000570e  mov     r10, [rax+8]
0x140005712  mov     rax, [r10+8]
0x140005716  cmp     byte ptr [rax+18h], 0
0x14000571a  jnz     short loc_1400056C2
0x14000571c  jmp     short loc_1400056E0
0x14000571e  mov     [rax+8], r9
0x140005722  mov     rax, [rbx]
0x140005725  mov     [rax], r9
0x140005728  mov     rax, [rbx]
0x14000572b  jmp     short loc_1400056B1
0x14000572d  mov     rax, [rcx+10h]
0x140005731  cmp     byte ptr [rax+18h], 0
0x140005735  jnz     loc_1400057DF
0x14000573b  mov     byte ptr [rdx+18h], 1
0x14000573f  mov     byte ptr [rax+18h], 1
0x140005743  mov     rax, [r10+8]
0x140005747  mov     rcx, [rax+8]
0x14000574b  mov     byte ptr [rcx+18h], 0
0x14000574f  mov     rax, [r10+8]
0x140005753  mov     r10, [rax+8]
0x140005757  jmp     short loc_140005712
0x140005759  cmp     r10, [rdx]
0x14000575c  jz      loc_140005819
0x140005762  mov     rax, [r10+8]
0x140005766  mov     byte ptr [rax+18h], 1
0x14000576a  mov     rax, [r10+8]
0x14000576e  mov     rcx, [rax+8]
0x140005772  mov     byte ptr [rcx+18h], 0
0x140005776  mov     rax, [r10+8]
0x14000577a  mov     rdx, [rax+8]
0x14000577e  mov     rcx, [rdx+10h]
0x140005782  mov     rax, [rcx]
0x140005785  mov     [rdx+10h], rax
0x140005789  mov     rax, [rcx]
0x14000578c  cmp     byte ptr [rax+19h], 0
0x140005790  jz      loc_140005829
0x140005796  mov     rax, [rdx+8]
0x14000579a  mov     [rcx+8], rax
0x14000579e  mov     rax, [rbx]
0x1400057a1  cmp     rdx, [rax+8]
0x1400057a5  jnz     loc_140005832
0x1400057ab  mov     [rax+8], rcx
0x1400057af  mov     [rcx], rdx
0x1400057b2  mov     [rdx+8], rcx
0x1400057b6  jmp     loc_140005712
0x1400057bb  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x1400057c2  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400057c8  mov     [rsi], r9
0x1400057cb  mov     rax, [rbx]
0x1400057ce  cmp     rsi, [rax]
0x1400057d1  jnz     loc_1400056B5
0x1400057d7  mov     [rax], r9
0x1400057da  jmp     loc_1400056B5
0x1400057df  cmp     r10, [rdx+10h]
0x1400057e3  jnz     short loc_1400057F0
0x1400057e5  mov     rcx, rbx
0x1400057e8  mov     r10, rdx
0x1400057eb  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Lrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x1400057f0  mov     rax, [r10+8]
0x1400057f4  mov     byte ptr [rax+18h], 1
0x1400057f8  mov     rax, [r10+8]
0x1400057fc  mov     rcx, [rax+8]
0x140005800  mov     byte ptr [rcx+18h], 0
0x140005804  mov     rcx, rbx
0x140005807  mov     rdx, [r10+8]
0x14000580b  mov     rdx, [rdx+8]
0x14000580f  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140005814  jmp     loc_140005712
0x140005819  mov     rcx, rbx
0x14000581c  mov     r10, rdx
0x14000581f  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Rrotate(std::_Tree_node<ComTaskHost *,void *> *)
0x140005824  jmp     loc_140005762
0x140005829  mov     [rax+8], rdx
0x14000582d  jmp     loc_140005796
0x140005832  mov     rax, [rdx+8]
0x140005836  cmp     rdx, [rax]
0x140005839  jnz     short loc_140005843
0x14000583b  mov     [rax], rcx
0x14000583e  jmp     loc_1400057AF
0x140005843  mov     [rax+10h], rcx
0x140005847  jmp     loc_1400057AF
```
