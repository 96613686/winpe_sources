# TSTDArray<CTDCCell>::InsertElems(unsigned __int64,unsigned __int64)

- ea: `0x18000c914`
- end: `0x18000ca01`
- name: `?InsertElems@?$TSTDArray@VCTDCCell@@@@QEAAJ_K0@Z`
- size: `237`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000b190`
- `0x18000baa0`
- `0x18000c770`
- `0x18000d9b0`

## callees

- `0x18000c914`
- `0x180014232`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000c973`
- `ole32!CoTaskMemRealloc` at `0x18000c973`
- `OLEAUT32!__imp_VariantInit` at `0x18000c9d1`
- `OLEAUT32!__imp_VariantInit` at `0x18000c9d1`

## pseudocode

```c
__int64 __fastcall TSTDArray<CTDCCell>::InsertElems(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rcx
  __int64 v9; // rbx
  LPVOID v10; // rax
  unsigned int v11; // esi
  VARIANTARG *i; // rbx

  v3 = *(_QWORD *)(a1 + 8);
  v7 = v3 + a3;
  if ( v3 + a3 < v3 || v7 >= 0x7FFFFFFF )
    return (unsigned int)-2147024809;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v7 > v8 )
  {
    if ( !v8 )
      LODWORD(v8) = 8;
    while ( v7 > (unsigned int)v8 )
      LODWORD(v8) = 2 * v8;
    v9 = (unsigned int)v8;
    v10 = CoTaskMemRealloc(*(LPVOID *)a1, 24LL * (unsigned int)v8);
    if ( !v10 )
      return (unsigned int)-2147024882;
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 16) = v9;
  }
  v11 = 0;
  memmove_0(
    (void *)(*(_QWORD *)a1 + 24 * (a2 + a3)),
    (const void *)(*(_QWORD *)a1 + 24 * a2),
    24 * (*(_QWORD *)(a1 + 8) - a2));
  for ( i = (VARIANTARG *)(*(_QWORD *)a1 + 24 * a2); (unsigned __int64)i < *(_QWORD *)a1 + 24 * (a2 + a3); ++i )
  {
    if ( i )
      VariantInit(i);
  }
  *(_QWORD *)(a1 + 8) += a3;
  return v11;
}

```

## disassembly

```asm
0x18000c914  push    rbx
0x18000c916  push    rbp
0x18000c917  push    rsi
0x18000c918  push    rdi
0x18000c919  push    r14
0x18000c91b  push    r15
0x18000c91d  sub     rsp, 28h
0x18000c921  mov     rax, [rcx+8]
0x18000c925  mov     rbp, r8
0x18000c928  mov     r15, rdx
0x18000c92b  mov     rdi, rcx
0x18000c92e  lea     r9, [rax+r8]
0x18000c932  cmp     r9, rax
0x18000c935  jb      loc_18000C9ED
0x18000c93b  cmp     r9, 7FFFFFFFh
0x18000c942  jnb     loc_18000C9ED
0x18000c948  mov     rcx, [rcx+10h]
0x18000c94c  cmp     r9, rcx
0x18000c94f  jbe     short loc_18000C98C
0x18000c951  test    rcx, rcx
0x18000c954  jnz     short loc_18000C95F
0x18000c956  mov     ecx, 8
0x18000c95b  jmp     short loc_18000C95F
0x18000c95d  add     ecx, ecx
0x18000c95f  mov     eax, ecx
0x18000c961  cmp     r9, rax
0x18000c964  ja      short loc_18000C95D
0x18000c966  mov     ebx, ecx
0x18000c968  mov     rcx, [rdi]; pv
0x18000c96b  lea     rdx, [rbx+rbx*2]
0x18000c96f  shl     rdx, 3; cb
0x18000c973  call    cs:__imp_CoTaskMemRealloc
0x18000c979  test    rax, rax
0x18000c97c  jnz     short loc_18000C985
0x18000c97e  mov     esi, 8007000Eh
0x18000c983  jmp     short loc_18000C9F2
0x18000c985  mov     [rdi], rax
0x18000c988  mov     [rdi+10h], rbx
0x18000c98c  mov     rcx, [rdi]
0x18000c98f  lea     rax, [r15+rbp]
0x18000c993  lea     r14, [rax+rax*2]
0x18000c997  xor     esi, esi
0x18000c999  mov     rax, [rdi+8]
0x18000c99d  lea     rbx, [r15+r15*2]
0x18000c9a1  sub     rax, r15
0x18000c9a4  lea     rdx, [rcx+rbx*8]; Src
0x18000c9a8  lea     rcx, [rcx+r14*8]; void *
0x18000c9ac  lea     r8, [rax+rax*2]
0x18000c9b0  shl     r8, 3; Size
0x18000c9b4  call    memmove_0
0x18000c9b9  mov     rax, [rdi]
0x18000c9bc  lea     rbx, [rax+rbx*8]
0x18000c9c0  lea     rax, [rax+r14*8]
0x18000c9c4  cmp     rbx, rax
0x18000c9c7  jnb     short loc_18000C9E7
0x18000c9c9  test    rbx, rbx
0x18000c9cc  jz      short loc_18000C9D7
0x18000c9ce  mov     rcx, rbx; pvarg
0x18000c9d1  call    cs:__imp_VariantInit
0x18000c9d7  mov     rax, [rdi]
0x18000c9da  add     rbx, 18h
0x18000c9de  lea     rcx, [rax+r14*8]
0x18000c9e2  cmp     rbx, rcx
0x18000c9e5  jb      short loc_18000C9C9
0x18000c9e7  add     [rdi+8], rbp
0x18000c9eb  jmp     short loc_18000C9F2
0x18000c9ed  mov     esi, 80070057h
0x18000c9f2  mov     eax, esi
0x18000c9f4  add     rsp, 28h
0x18000c9f8  pop     r15
0x18000c9fa  pop     r14
0x18000c9fc  pop     rdi
0x18000c9fd  pop     rsi
0x18000c9fe  pop     rbp
0x18000c9ff  pop     rbx
0x18000ca00  retn
```
