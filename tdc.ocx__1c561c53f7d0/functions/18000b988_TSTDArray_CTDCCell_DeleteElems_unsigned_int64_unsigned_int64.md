# TSTDArray<CTDCCell>::DeleteElems(unsigned __int64,unsigned __int64)

- ea: `0x18000b988`
- end: `0x18000b9fc`
- name: `?DeleteElems@?$TSTDArray@VCTDCCell@@@@QEAAX_K0@Z`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b870`
- `0x18000c770`

## callees

- `0x18000b988`
- `0x180014232`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b9b6`
- `OLEAUT32!__imp_VariantClear` at `0x18000b9b6`

## pseudocode

```c
void *__fastcall TSTDArray<CTDCCell>::DeleteElems(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v4; // r15
  __int64 v7; // rsi
  VARIANTARG *i; // rbx
  void *result; // rax

  v3 = *a1;
  v4 = 3 * a2;
  v7 = 3 * (a2 + a3);
  for ( i = (VARIANTARG *)(*a1 + 24 * a2); (unsigned __int64)i < v3 + 8 * v7; ++i )
  {
    VariantClear(i);
    v3 = *a1;
  }
  result = memmove_0((void *)(v3 + 8 * v4), (const void *)(v3 + 8 * v7), 24 * (a1[1] - a2 - a3));
  a1[1] -= a3;
  return result;
}

```

## disassembly

```asm
0x18000b988  push    rbx
0x18000b98a  push    rbp
0x18000b98b  push    rsi
0x18000b98c  push    rdi
0x18000b98d  push    r14
0x18000b98f  push    r15
0x18000b991  sub     rsp, 28h
0x18000b995  mov     r9, [rcx]
0x18000b998  lea     r15, [rdx+rdx*2]
0x18000b99c  lea     rax, [rdx+r8]
0x18000b9a0  mov     rbp, r8
0x18000b9a3  mov     r14, rdx
0x18000b9a6  lea     rsi, [rax+rax*2]
0x18000b9aa  mov     rdi, rcx
0x18000b9ad  lea     rbx, [r9+r15*8]
0x18000b9b1  jmp     short loc_18000B9C3
0x18000b9b3  mov     rcx, rbx; pvarg
0x18000b9b6  call    cs:__imp_VariantClear
0x18000b9bc  mov     r9, [rdi]
0x18000b9bf  add     rbx, 18h
0x18000b9c3  lea     rax, [r9+rsi*8]
0x18000b9c7  cmp     rbx, rax
0x18000b9ca  jb      short loc_18000B9B3
0x18000b9cc  mov     rax, [rdi+8]
0x18000b9d0  lea     rdx, [r9+rsi*8]; Src
0x18000b9d4  sub     rax, r14
0x18000b9d7  lea     rcx, [r9+r15*8]; void *
0x18000b9db  sub     rax, rbp
0x18000b9de  lea     r8, [rax+rax*2]
0x18000b9e2  shl     r8, 3; Size
0x18000b9e6  call    memmove_0
0x18000b9eb  sub     [rdi+8], rbp
0x18000b9ef  add     rsp, 28h
0x18000b9f3  pop     r15
0x18000b9f5  pop     r14
0x18000b9f7  pop     rdi
0x18000b9f8  pop     rsi
0x18000b9f9  pop     rbp
0x18000b9fa  pop     rbx
0x18000b9fb  retn
```
