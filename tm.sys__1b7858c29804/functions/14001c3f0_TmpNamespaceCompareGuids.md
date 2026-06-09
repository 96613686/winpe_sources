# TmpNamespaceCompareGuids

- ea: `0x14001c3f0`
- end: `0x14001c494`
- name: `TmpNamespaceCompareGuids`
- size: `164`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002e60`
- `0x14001c3f0`

## pseudocode

```c
__int64 __fastcall TmpNamespaceCompareGuids(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)
{
  _DWORD *TableContext; // rax
  char *v6; // rax
  char *v7; // rcx
  bool v8; // zf
  char *v9; // rdx
  int v10; // ecx
  __int64 result; // rax

  TableContext = Table->TableContext;
  if ( TableContext[2] != 1 )
  {
    v9 = 0;
LABEL_7:
    v7 = &FirstStruct[WORD1(Table[1].RestartKey) - (unsigned __int64)LOWORD(Table[1].RestartKey) - 32];
    goto LABEL_8;
  }
  v6 = *(char **)TableContext;
  v7 = FirstStruct;
  v8 = v6 == FirstStruct;
  v9 = SecondStruct;
  if ( !v8 )
    v7 = 0;
  if ( v6 != SecondStruct )
    v9 = 0;
  if ( !v7 )
    goto LABEL_7;
LABEL_8:
  if ( !v9 )
    v9 = &SecondStruct[WORD1(Table[1].RestartKey) - (unsigned __int64)LOWORD(Table[1].RestartKey) - 32];
  v10 = memcmp(v7, v9, 0x10u);
  if ( v10 > 0 )
    return 1;
  result = 2;
  if ( v10 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14001c3f0  push    rbx
0x14001c3f2  sub     rsp, 20h
0x14001c3f6  mov     rax, [rcx+60h]
0x14001c3fa  xor     ebx, ebx
0x14001c3fc  mov     r10, rdx
0x14001c3ff  mov     r9, rcx
0x14001c402  cmp     dword ptr [rax+8], 1
0x14001c406  jnz     loc_14001C48F
0x14001c40c  mov     rax, [rax]
0x14001c40f  mov     rcx, rdx
0x14001c412  cmp     rax, rdx
0x14001c415  mov     rdx, r8
0x14001c418  cmovnz  rcx, rbx
0x14001c41c  cmp     rax, r8
0x14001c41f  cmovnz  rdx, rbx
0x14001c423  test    rcx, rcx
0x14001c426  jnz     short loc_14001C442
0x14001c428  movzx   ecx, word ptr [r9+0A2h]
0x14001c430  movzx   eax, word ptr [r9+0A0h]
0x14001c438  sub     rcx, rax
0x14001c43b  add     rcx, 0FFFFFFFFFFFFFFE0h
0x14001c43f  add     rcx, r10; Buf1
0x14001c442  test    rdx, rdx
0x14001c445  jnz     short loc_14001C461
0x14001c447  movzx   edx, word ptr [r9+0A2h]
0x14001c44f  movzx   eax, word ptr [r9+0A0h]
0x14001c457  sub     rdx, rax
0x14001c45a  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14001c45e  add     rdx, r8; Buf2
0x14001c461  mov     r8d, 10h; Size
0x14001c467  call    memcmp
0x14001c46c  mov     ecx, eax
0x14001c46e  test    eax, eax
0x14001c470  jg      short loc_14001C483
0x14001c472  test    ecx, ecx
0x14001c474  mov     eax, 2
0x14001c479  cmovs   eax, ebx
0x14001c47c  add     rsp, 20h
0x14001c480  pop     rbx
0x14001c481  retn
0x14001c483  mov     eax, 1
0x14001c488  add     rsp, 20h
0x14001c48c  pop     rbx
0x14001c48d  retn
0x14001c48f  mov     rdx, rbx
0x14001c492  jmp     short loc_14001C428
```
