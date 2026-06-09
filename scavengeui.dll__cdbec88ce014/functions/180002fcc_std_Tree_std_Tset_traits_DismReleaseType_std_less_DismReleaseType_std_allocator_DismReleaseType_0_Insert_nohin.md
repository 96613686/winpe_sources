# std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)

- ea: `0x180002fcc`
- end: `0x1800030e9`
- name: `??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z`
- size: `285`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, int *, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003300`

## callees

- `0x180002d48`
- `0x180002fcc`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int *a4,
        char a5)
{
  __int64 v8; // rax
  int v9; // r8d
  __int64 v10; // r9
  char v11; // r11
  __int64 v12; // rax
  __int64 result; // rax
  __int64 j; // rcx
  __int64 i; // rcx
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(*a1 + 8);
  if ( *(_BYTE *)(v8 + 25) )
  {
    v11 = 1;
    v10 = *a1;
  }
  else
  {
    v9 = *a4;
    do
    {
      v10 = v8;
      v11 = v9 < *(_DWORD *)(v8 + 28);
      if ( v9 >= *(_DWORD *)(v8 + 28) )
        v8 = *(_QWORD *)(v8 + 16);
      else
        v8 = *(_QWORD *)v8;
    }
    while ( !*(_BYTE *)(v8 + 25) );
  }
  try
  {
    v12 = v10;
    if ( v11 )
    {
      if ( v10 == *(_QWORD *)*a1 )
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_at<enum _DismReleaseType,std::_Nil>(
                           a1,
                           &v16,
                           1,
                           (__int64 *)v10,
                           a4);
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
      if ( *(_BYTE *)(v10 + 25) )
      {
        v12 = *(_QWORD *)(v10 + 16);
      }
      else if ( *(_BYTE *)(*(_QWORD *)v10 + 25LL) )
      {
        for ( i = *(_QWORD *)(v10 + 8); !*(_BYTE *)(i + 25) && v12 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
          v12 = i;
        if ( !*(_BYTE *)(v12 + 25) )
          v12 = i;
      }
      else
      {
        v12 = *(_QWORD *)v10;
        for ( j = *(_QWORD *)(*(_QWORD *)v10 + 16LL); !*(_BYTE *)(j + 25); j = *(_QWORD *)(v12 + 16) )
          v12 = *(_QWORD *)(v12 + 16);
      }
    }
    if ( *(_DWORD *)(v12 + 28) >= *a4 )
    {
      *(_QWORD *)a2 = v12;
      *(_BYTE *)(a2 + 8) = 0;
    }
    else
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_at<enum _DismReleaseType,std::_Nil>(
                         a1,
                         &v16,
                         v11,
                         (__int64 *)v10,
                         a4);
      *(_BYTE *)(a2 + 8) = 1;
    }
    result = a2;
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
0x180002fcc  mov     [rsp+arg_8], rbx
0x180002fd1  push    rdi
0x180002fd2  sub     rsp, 30h
0x180002fd6  mov     r10, r9
0x180002fd9  mov     rbx, rdx
0x180002fdc  mov     rdi, rcx
0x180002fdf  mov     rdx, [rcx]
0x180002fe2  mov     rax, [rdx+8]
0x180002fe6  cmp     byte ptr [rax+19h], 0
0x180002fea  jnz     short loc_18000300D
0x180002fec  mov     r8d, [r9]
0x180002fef  mov     r9, rax
0x180002ff2  cmp     r8d, [rax+1Ch]
0x180002ff6  setl    r11b
0x180002ffa  jge     short loc_180003001
0x180002ffc  mov     rax, [rax]
0x180002fff  jmp     short loc_180003005
0x180003001  mov     rax, [rax+10h]
0x180003005  cmp     byte ptr [rax+19h], 0
0x180003009  jz      short loc_180002FEF
0x18000300b  jmp     short loc_180003013
0x18000300d  mov     r11b, 1
0x180003010  mov     r9, rdx
0x180003013  mov     rax, r9
0x180003016  test    r11b, r11b
0x180003019  jz      loc_18000309F
0x18000301f  cmp     r9, [rdx]
0x180003022  jnz     short loc_180003050
0x180003024  mov     al, [rsp+38h+arg_20]
0x180003028  mov     [rsp+38h+var_10], al
0x18000302c  mov     [rsp+38h+var_18], r10
0x180003031  mov     r8b, 1
0x180003034  lea     rdx, [rsp+38h+arg_0]
0x180003039  call    ??$_Insert_at@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@1@_NPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@1@$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_at<_DismReleaseType,std::_Nil>(bool,std::_Tree_node<_DismReleaseType,void *> *,_DismReleaseType &&,std::_Nil)
0x18000303e  mov     rax, [rax]
0x180003041  mov     [rbx], rax
0x180003044  mov     byte ptr [rbx+8], 1
0x180003048  mov     rax, rbx
0x18000304b  jmp     loc_1800030DD
0x180003050  cmp     byte ptr [r9+19h], 0
0x180003055  jz      short loc_18000305D
0x180003057  mov     rax, [r9+10h]
0x18000305b  jmp     short loc_18000309F
0x18000305d  mov     rcx, [r9]
0x180003060  cmp     byte ptr [rcx+19h], 0
0x180003064  jnz     short loc_18000307F
0x180003066  mov     rax, rcx
0x180003069  mov     rcx, [rcx+10h]
0x18000306d  jmp     short loc_180003077
0x18000306f  mov     rax, [rax+10h]
0x180003073  mov     rcx, [rax+10h]
0x180003077  cmp     byte ptr [rcx+19h], 0
0x18000307b  jz      short loc_18000306F
0x18000307d  jmp     short loc_18000309F
0x18000307f  mov     rcx, [r9+8]
0x180003083  jmp     short loc_180003091
0x180003085  cmp     rax, [rcx]
0x180003088  jnz     short loc_180003097
0x18000308a  mov     rax, rcx
0x18000308d  mov     rcx, [rcx+8]
0x180003091  cmp     byte ptr [rcx+19h], 0
0x180003095  jz      short loc_180003085
0x180003097  cmp     byte ptr [rax+19h], 0
0x18000309b  cmovz   rax, rcx
0x18000309f  mov     ecx, [r10]
0x1800030a2  cmp     [rax+1Ch], ecx
0x1800030a5  jge     short loc_1800030D3
0x1800030a7  mov     al, [rsp+38h+arg_20]
0x1800030ab  mov     [rsp+38h+var_10], al
0x1800030af  mov     [rsp+38h+var_18], r10
0x1800030b4  mov     r8b, r11b
0x1800030b7  lea     rdx, [rsp+38h+arg_0]
0x1800030bc  mov     rcx, rdi
0x1800030bf  call    ??$_Insert_at@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@1@_NPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@1@$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_at<_DismReleaseType,std::_Nil>(bool,std::_Tree_node<_DismReleaseType,void *> *,_DismReleaseType &&,std::_Nil)
0x1800030c4  mov     rax, [rax]
0x1800030c7  mov     [rbx], rax
0x1800030ca  mov     byte ptr [rbx+8], 1
0x1800030ce  mov     rax, rbx
0x1800030d1  jmp     short loc_1800030DD
0x1800030d3  mov     [rbx], rax
0x1800030d6  mov     byte ptr [rbx+8], 0
0x1800030da  mov     rax, rbx
0x1800030dd  mov     rbx, [rsp+38h+arg_8]
0x1800030e2  add     rsp, 30h
0x1800030e6  pop     rdi
0x1800030e7  retn
```
