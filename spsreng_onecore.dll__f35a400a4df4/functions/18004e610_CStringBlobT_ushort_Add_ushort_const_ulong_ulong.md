# CStringBlobT<ushort>::Add(ushort const *,ulong *,ulong *)

- ea: `0x18004e610`
- end: `0x18004e78a`
- name: `?Add@?$CStringBlobT@G@@QEAAJPEBGPEAK1@Z`
- size: `378`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800509a0`
- `0x18007c6ec`
- `0x18007cf78`
- `0x18007d724`

## callees

- `0x180004312`
- `0x18004c204`
- `0x18004e610`
- `0x18004fc78`
- `0x180053208`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004e6f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004e6f2`

## pseudocode

```c
__int64 __fastcall CStringBlobT<unsigned short>::Add(__int64 a1, _WORD *a2, _DWORD *a3)
{
  int v6; // ecx
  __int64 result; // rax
  __int64 Index; // rbp
  int v9; // eax
  int v10; // ecx
  _DWORD *v11; // rax
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // r14
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdi
  _WORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // edx

  if ( !a2 )
    goto LABEL_18;
  v6 = *(_DWORD *)(a1 + 24);
  if ( (unsigned int)(2 * v6) < *(_DWORD *)(a1 + 40)
    || (result = CStringBlobT<unsigned short>::SetHashSize(a1, (unsigned int)(v6 + 2 * v6 + 17)), (int)result >= 0) )
  {
    Index = (unsigned int)CStringBlobT<unsigned short>::FindIndex(a1, a2);
    v9 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * Index);
    if ( v9 )
      goto LABEL_17;
    v10 = *(_DWORD *)(a1 + 24);
    if ( (unsigned int)(v10 + 1) >= *(_DWORD *)(a1 + 28) )
    {
      v11 = heap_realloc(*(void **)(a1 + 16), 4LL * (unsigned int)(v10 + 100));
      if ( !v11 )
        return 2147942414LL;
      v12 = *(_DWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 16) = v11;
      *(_DWORD *)(a1 + 28) = v12 + 100;
      *v11 = 1;
    }
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    v14 = v13 + 1;
    v15 = *(unsigned int *)(a1 + 8);
    if ( v13 + 1 + (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 16) + 4LL * *(unsigned int *)(a1 + 24)) > v15 )
    {
      v16 = (2 * (v15 + v14) + 8195) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v16 > 0x70000000 )
        return 2147942414LL;
      v17 = CoTaskMemRealloc(*(LPVOID *)a1, (2 * (v15 + v14) + 8195) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( !v17 )
        return 2147942414LL;
      *(_QWORD *)a1 = v17;
      *v17 = 0;
      *(_DWORD *)(a1 + 8) = (unsigned int)v16 >> 1;
    }
    memcpy_0(
      (void *)(*(_QWORD *)a1 + 2LL * *(unsigned int *)(*(_QWORD *)(a1 + 16) + 4LL * *(unsigned int *)(a1 + 24))),
      a2,
      2 * v14);
    v18 = *(unsigned int *)(a1 + 24);
    v19 = *(_QWORD *)(a1 + 16);
    v20 = (unsigned int)(v18 + 1);
    *(_DWORD *)(a1 + 24) = v20;
    *(_DWORD *)(v19 + 4 * v20) = v14 + *(_DWORD *)(v19 + 4 * v18);
    v21 = *(unsigned int *)(a1 + 24);
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4 * v21) < *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * (unsigned int)(v21 - 1)) )
      return 2147942414LL;
    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * Index) = v21;
    v9 = *(_DWORD *)(a1 + 24);
    if ( v9 )
    {
LABEL_17:
      v22 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * (unsigned int)(v9 - 1));
LABEL_19:
      *a3 = v22;
      return 0;
    }
LABEL_18:
    v22 = 0;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x18004e610  push    rbx
0x18004e612  push    rbp
0x18004e613  push    rsi
0x18004e614  push    rdi
0x18004e615  push    r12
0x18004e617  push    r14
0x18004e619  push    r15
0x18004e61b  sub     rsp, 20h
0x18004e61f  xor     r12d, r12d
0x18004e622  mov     r15, r8
0x18004e625  mov     rsi, rdx
0x18004e628  mov     rbx, rcx
0x18004e62b  test    rdx, rdx
0x18004e62e  jz      loc_18004E773
0x18004e634  mov     ecx, [rcx+18h]
0x18004e637  lea     eax, [rcx+rcx]
0x18004e63a  cmp     eax, [rbx+28h]
0x18004e63d  jb      short loc_18004E658
0x18004e63f  lea     edx, ds:11h[rcx*2]
0x18004e646  add     edx, ecx
0x18004e648  mov     rcx, rbx
0x18004e64b  call    ?SetHashSize@?$CStringBlobT@G@@QEAAJK@Z; CStringBlobT<ushort>::SetHashSize(ulong)
0x18004e650  test    eax, eax
0x18004e652  js      loc_18004E77B
0x18004e658  mov     rdx, rsi
0x18004e65b  mov     rcx, rbx
0x18004e65e  call    ?FindIndex@?$CStringBlobT@G@@QEAAKPEBG@Z; CStringBlobT<ushort>::FindIndex(ushort const *)
0x18004e663  mov     ebp, eax
0x18004e665  mov     rax, [rbx+20h]
0x18004e669  mov     eax, [rax+rbp*4]
0x18004e66c  test    eax, eax
0x18004e66e  jnz     loc_18004E767
0x18004e674  mov     ecx, [rbx+18h]
0x18004e677  lea     eax, [rcx+1]
0x18004e67a  cmp     eax, [rbx+1Ch]
0x18004e67d  jb      short loc_18004E6AB
0x18004e67f  lea     edx, [rcx+64h]
0x18004e682  mov     rcx, [rbx+10h]; lpMem
0x18004e686  shl     rdx, 2; unsigned __int64
0x18004e68a  call    ?heap_realloc@@YAPEAXPEAX_K@Z; heap_realloc(void *,unsigned __int64)
0x18004e68f  test    rax, rax
0x18004e692  jz      loc_18004E752
0x18004e698  mov     ecx, [rbx+18h]
0x18004e69b  add     ecx, 64h ; 'd'
0x18004e69e  mov     [rbx+10h], rax
0x18004e6a2  mov     [rbx+1Ch], ecx
0x18004e6a5  mov     dword ptr [rax], 1
0x18004e6ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e6af  inc     rax
0x18004e6b2  cmp     [rsi+rax*2], r12w
0x18004e6b7  jnz     short loc_18004E6AF
0x18004e6b9  mov     ecx, [rbx+18h]
0x18004e6bc  lea     r14, [rax+1]
0x18004e6c0  mov     rax, [rbx+10h]
0x18004e6c4  mov     r8d, [rbx+8]
0x18004e6c8  mov     edx, [rax+rcx*4]
0x18004e6cb  add     rdx, r14
0x18004e6ce  cmp     rdx, r8
0x18004e6d1  jbe     short loc_18004E709
0x18004e6d3  lea     rax, [r8+r14]
0x18004e6d7  lea     rdi, ds:2003h[rax*2]
0x18004e6df  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18004e6e3  cmp     rdi, 70000000h
0x18004e6ea  ja      short loc_18004E752
0x18004e6ec  mov     rcx, [rbx]; pv
0x18004e6ef  mov     rdx, rdi; cb
0x18004e6f2  call    cs:__imp_CoTaskMemRealloc
0x18004e6f8  test    rax, rax
0x18004e6fb  jz      short loc_18004E752
0x18004e6fd  mov     [rbx], rax
0x18004e700  shr     edi, 1
0x18004e702  mov     [rax], r12w
0x18004e706  mov     [rbx+8], edi
0x18004e709  mov     ecx, [rbx+18h]
0x18004e70c  lea     r8, [r14+r14]; Size
0x18004e710  mov     rax, [rbx+10h]
0x18004e714  mov     edx, [rax+rcx*4]
0x18004e717  mov     rax, [rbx]
0x18004e71a  lea     rcx, [rax+rdx*2]; void *
0x18004e71e  mov     rdx, rsi; Src
0x18004e721  call    memcpy_0
0x18004e726  mov     eax, [rbx+18h]
0x18004e729  mov     r8, [rbx+10h]
0x18004e72d  lea     r9d, [rax+1]
0x18004e731  mov     [rbx+18h], r9d
0x18004e735  mov     edx, [r8+rax*4]
0x18004e739  add     edx, r14d
0x18004e73c  mov     [r8+r9*4], edx
0x18004e740  mov     edx, [rbx+18h]
0x18004e743  mov     rcx, [rbx+10h]
0x18004e747  lea     eax, [rdx-1]
0x18004e74a  mov     eax, [rcx+rax*4]
0x18004e74d  cmp     [rcx+rdx*4], eax
0x18004e750  jnb     short loc_18004E759
0x18004e752  mov     eax, 8007000Eh
0x18004e757  jmp     short loc_18004E77B
0x18004e759  mov     rax, [rbx+20h]
0x18004e75d  mov     [rax+rbp*4], edx
0x18004e760  mov     eax, [rbx+18h]
0x18004e763  test    eax, eax
0x18004e765  jz      short loc_18004E773
0x18004e767  lea     ecx, [rax-1]
0x18004e76a  mov     rax, [rbx+10h]
0x18004e76e  mov     edx, [rax+rcx*4]
0x18004e771  jmp     short loc_18004E776
0x18004e773  mov     edx, r12d
0x18004e776  mov     [r15], edx
0x18004e779  xor     eax, eax
0x18004e77b  add     rsp, 20h
0x18004e77f  pop     r15
0x18004e781  pop     r14
0x18004e783  pop     r12
0x18004e785  pop     rdi
0x18004e786  pop     rsi
0x18004e787  pop     rbp
0x18004e788  pop     rbx
0x18004e789  retn
```
