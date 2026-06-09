# UdfVmcbPurgeSomeMappings

- ea: `0x140018ff8`
- end: `0x14001923e`
- name: `UdfVmcbPurgeSomeMappings`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400576b0`

## callees

- `0x14001093c`
- `0x140010990`
- `0x140018db4`
- `0x140018ff8`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x140019151`
- `ntoskrnl!CcPurgeCacheSection` at `0x140019151`

## pseudocode

```c
int *__fastcall UdfVmcbPurgeSomeMappings(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  unsigned int v3; // r14d
  unsigned int v4; // ebp
  int v5; // r15d
  unsigned int v8; // esi
  unsigned int v9; // r8d
  __int64 v10; // r9
  unsigned int i; // edx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // r9
  int v16; // eax
  unsigned int v17; // r14d
  int *result; // rax
  int v19; // [rsp+20h] [rbp-38h]
  int v20; // [rsp+68h] [rbp+10h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  FileOffset.QuadPart = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    WPP_SF_DDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      21,
      WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
      *(unsigned int *)(a2 + 304),
      *(_DWORD *)(a2 + 312),
      *(_DWORD *)(a2 + 316));
  }
  v8 = *(_DWORD *)(a2 + 304);
  v9 = *(_DWORD *)(a2 + 288);
  while ( 1 )
  {
    if ( v4 >= 16 << *(_DWORD *)(a2 + 300) )
      goto LABEL_34;
    v10 = *(_QWORD *)(a2 + 328);
    if ( v10 )
    {
      for ( i = 0; i < v9; ++i )
      {
        if ( ((*(char *)(((unsigned __int64)(i + v8) >> 3) + v10) >> ((v8 + i) & 7)) & 1) != 0 )
        {
          v12 = 1;
          goto LABEL_13;
        }
      }
      v12 = 0;
LABEL_13:
      if ( v12 )
        goto LABEL_34;
    }
    if ( v8 <= v2 )
    {
LABEL_34:
      if ( v4 )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
        {
          WPP_SF_dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            22,
            WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
            v2,
            v4);
        }
        v13 = *(_DWORD *)(a2 + 296);
        FileOffset.QuadPart = (unsigned __int64)v2 << v13;
        CcPurgeCacheSection(
          *(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 272LL) + 504LL) + 40LL),
          &FileOffset,
          v4 << v13,
          0);
        UdfRemoveVmcbMappingInternal(v14, a2, v2, v4, v19, &v20);
        v3 = v4;
        v5 += v4 - v20;
        v4 = 0;
      }
    }
    else
    {
      if ( !v4 )
        v2 = v8;
      v4 += *(_DWORD *)(a2 + 288);
    }
    v9 = *(_DWORD *)(a2 + 288);
    v8 += v9;
    if ( v8 == *(_DWORD *)(a2 + 308) )
      v8 = 16;
    if ( v3 )
      break;
    v15 = *(unsigned int *)(a2 + 304);
    if ( v8 == (_DWORD)v15 )
      goto LABEL_29;
  }
  v16 = v3 - v5;
  v17 = v3 >> *(_DWORD *)(a2 + 300);
  *(_DWORD *)(a2 + 312) += v16;
  v15 = v2;
  *(_DWORD *)(a2 + 316) += v17;
  *(_DWORD *)(a2 + 304) = v2;
LABEL_29:
  result = &WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    return (int *)WPP_SF_DDD(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    23,
                    WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
                    v15,
                    *(_DWORD *)(a2 + 312),
                    *(_DWORD *)(a2 + 316));
  }
  return result;
}

```

## disassembly

```asm
0x140018ff8  mov     rax, rsp
0x140018ffb  mov     [rax+8], rbx
0x140018fff  mov     [rax+20h], rbp
0x140019003  push    rsi
0x140019004  push    rdi
0x140019005  push    r13
0x140019007  push    r14
0x140019009  push    r15
0x14001900b  sub     rsp, 30h
0x14001900f  xor     edi, edi
0x140019011  xor     r14d, r14d
0x140019014  xor     ebp, ebp
0x140019016  mov     [rax+10h], edi
0x140019019  xor     r15d, r15d
0x14001901c  mov     [rax+18h], rdi
0x140019020  mov     rbx, rdx
0x140019023  mov     r13, rcx
0x140019026  mov     rcx, cs:WPP_GLOBAL_Control
0x14001902d  lea     r10, WPP_GLOBAL_Control
0x140019034  cmp     rcx, r10
0x140019037  jz      short loc_140019077
0x140019039  test    dword ptr [rcx+2Ch], 400000h
0x140019040  jz      short loc_140019077
0x140019042  mov     eax, [rbx+13Ch]
0x140019048  lea     edx, [rdi+15h]
0x14001904b  mov     r9d, [rbx+130h]
0x140019052  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x140019059  mov     rcx, [rcx+18h]
0x14001905d  mov     dword ptr [rsp+58h+var_30], eax
0x140019061  mov     eax, [rbx+138h]
0x140019067  mov     [rsp+58h+var_38], eax
0x14001906b  call    WPP_SF_DDD
0x140019070  lea     r10, WPP_GLOBAL_Control
0x140019077  mov     esi, [rbx+130h]
0x14001907d  mov     eax, 10h
0x140019082  mov     r8d, [rbx+120h]
0x140019089  mov     ecx, [rbx+12Ch]
0x14001908f  shl     eax, cl
0x140019091  cmp     ebp, eax
0x140019093  jnb     short loc_1400190E4
0x140019095  mov     r9, [rbx+148h]
0x14001909c  test    r9, r9
0x14001909f  jz      short loc_1400190D0
0x1400190a1  xor     edx, edx
0x1400190a3  cmp     edx, r8d
0x1400190a6  jnb     short loc_1400190CA
0x1400190a8  lea     eax, [rdx+rsi]
0x1400190ab  shr     rax, 3
0x1400190af  lea     ecx, [rsi+rdx]
0x1400190b2  and     cl, 7
0x1400190b5  mov     al, [rax+r9]
0x1400190b9  sar     al, cl
0x1400190bb  test    al, 1
0x1400190bd  jnz     short loc_1400190C3
0x1400190bf  inc     edx
0x1400190c1  jmp     short loc_1400190A3
0x1400190c3  mov     eax, 1
0x1400190c8  jmp     short loc_1400190CC
0x1400190ca  xor     eax, eax
0x1400190cc  test    eax, eax
0x1400190ce  jnz     short loc_1400190E4
0x1400190d0  cmp     esi, edi
0x1400190d2  jbe     short loc_1400190E4
0x1400190d4  test    ebp, ebp
0x1400190d6  cmovz   edi, esi
0x1400190d9  add     ebp, [rbx+120h]
0x1400190df  jmp     loc_140019183
0x1400190e4  test    ebp, ebp
0x1400190e6  jz      loc_140019183
0x1400190ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190f3  cmp     rcx, r10
0x1400190f6  jz      short loc_14001911D
0x1400190f8  test    dword ptr [rcx+2Ch], 400000h
0x1400190ff  jz      short loc_14001911D
0x140019101  mov     rcx, [rcx+18h]
0x140019105  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x14001910c  mov     edx, 16h
0x140019111  mov     [rsp+58h+var_38], ebp
0x140019115  mov     r9d, edi
0x140019118  call    WPP_SF_dd
0x14001911d  mov     ecx, [rbx+128h]
0x140019123  lea     rdx, [rsp+58h+FileOffset]; FileOffset
0x140019128  mov     r8d, ebp
0x14001912b  mov     eax, edi
0x14001912d  shl     rax, cl
0x140019130  xor     r9d, r9d; Flags
0x140019133  mov     qword ptr [rsp+58h+FileOffset], rax
0x140019138  mov     rax, [r13+10h]
0x14001913c  shl     r8d, cl; Length
0x14001913f  mov     rcx, [rax+110h]
0x140019146  mov     rcx, [rcx+1F8h]
0x14001914d  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140019151  call    cs:__imp_CcPurgeCacheSection
0x140019158  nop     dword ptr [rax+rax+00h]
0x14001915d  lea     rax, [rsp+58h+arg_8]
0x140019162  mov     r9d, ebp
0x140019165  mov     r8d, edi
0x140019168  mov     [rsp+58h+var_30], rax
0x14001916d  mov     rdx, rbx
0x140019170  call    UdfRemoveVmcbMappingInternal
0x140019175  mov     eax, ebp
0x140019177  mov     r14d, ebp
0x14001917a  sub     eax, [rsp+58h+arg_8]
0x14001917e  add     r15d, eax
0x140019181  xor     ebp, ebp
0x140019183  mov     r8d, [rbx+120h]
0x14001918a  lea     eax, [r8+rsi]
0x14001918e  cmp     eax, [rbx+134h]
0x140019194  mov     esi, eax
0x140019196  mov     eax, 10h
0x14001919b  cmovz   esi, eax
0x14001919e  test    r14d, r14d
0x1400191a1  jnz     short loc_1400191BC
0x1400191a3  mov     r9d, [rbx+130h]
0x1400191aa  lea     r10, WPP_GLOBAL_Control
0x1400191b1  cmp     esi, r9d
0x1400191b4  jnz     loc_140019089
0x1400191ba  jmp     short loc_1400191E1
0x1400191bc  mov     ecx, [rbx+12Ch]
0x1400191c2  mov     eax, r14d
0x1400191c5  sub     eax, r15d
0x1400191c8  shr     r14d, cl
0x1400191cb  add     [rbx+138h], eax
0x1400191d1  mov     r9d, edi
0x1400191d4  add     [rbx+13Ch], r14d
0x1400191db  mov     [rbx+130h], edi
0x1400191e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191e8  lea     rax, WPP_GLOBAL_Control
0x1400191ef  cmp     rcx, rax
0x1400191f2  jz      short loc_140019226
0x1400191f4  test    dword ptr [rcx+2Ch], 400000h
0x1400191fb  jz      short loc_140019226
0x1400191fd  mov     eax, [rbx+13Ch]
0x140019203  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x14001920a  mov     rcx, [rcx+18h]
0x14001920e  mov     edx, 17h
0x140019213  mov     dword ptr [rsp+58h+var_30], eax
0x140019217  mov     eax, [rbx+138h]
0x14001921d  mov     [rsp+58h+var_38], eax
0x140019221  call    WPP_SF_DDD
0x140019226  mov     rbx, [rsp+58h+arg_0]
0x14001922b  mov     rbp, [rsp+58h+arg_18]
0x140019230  add     rsp, 30h
0x140019234  pop     r15
0x140019236  pop     r14
0x140019238  pop     r13
0x14001923a  pop     rdi
0x14001923b  pop     rsi
0x14001923c  retn
```
