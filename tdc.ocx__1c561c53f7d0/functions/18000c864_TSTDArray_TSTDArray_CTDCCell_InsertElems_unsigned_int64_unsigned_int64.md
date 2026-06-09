# TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(unsigned __int64,unsigned __int64)

- ea: `0x18000c864`
- end: `0x18000c90d`
- name: `?InsertElems@?$TSTDArray@PEAV?$TSTDArray@VCTDCCell@@@@@@QEAAJ_K0@Z`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000b190`
- `0x18000b370`
- `0x18000baa0`
- `0x18000d9b0`

## callees

- `0x18000c864`
- `0x180014232`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000c8bc`
- `ole32!CoTaskMemRealloc` at `0x18000c8bc`

## pseudocode

```c
__int64 __fastcall TSTDArray<TSTDArray<CTDCCell> *>::InsertElems(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r8
  __int64 v9; // rdi
  LPVOID v10; // rax
  unsigned int v11; // edi

  v3 = *(_QWORD *)(a1 + 8);
  v7 = v3 + a3;
  if ( v3 + a3 < v3 || v7 >= 0x7FFFFFFF )
    return (unsigned int)-2147024809;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v7 <= v8 )
    goto LABEL_11;
  if ( !v8 )
    LODWORD(v8) = 8;
  while ( v7 > (unsigned int)v8 )
    LODWORD(v8) = 2 * v8;
  v9 = (unsigned int)v8;
  v10 = CoTaskMemRealloc(*(LPVOID *)a1, 8LL * (unsigned int)v8);
  if ( v10 )
  {
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 16) = v9;
LABEL_11:
    v11 = 0;
    memmove_0(
      (void *)(*(_QWORD *)a1 + 8 * (a2 + a3)),
      (const void *)(*(_QWORD *)a1 + 8 * a2),
      8 * (*(_QWORD *)(a1 + 8) - a2));
    *(_QWORD *)(a1 + 8) += a3;
    return v11;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18000c864  push    rbx
0x18000c866  push    rsi
0x18000c867  push    rdi
0x18000c868  push    r14
0x18000c86a  sub     rsp, 28h
0x18000c86e  mov     rax, [rcx+8]
0x18000c872  mov     rbx, rcx
0x18000c875  mov     rsi, r8
0x18000c878  mov     r14, rdx
0x18000c87b  lea     rcx, [rax+r8]
0x18000c87f  cmp     rcx, rax
0x18000c882  jb      short loc_18000C8FC
0x18000c884  cmp     rcx, 7FFFFFFFh
0x18000c88b  jnb     short loc_18000C8FC
0x18000c88d  mov     r8, [rbx+10h]
0x18000c891  cmp     rcx, r8
0x18000c894  jbe     short loc_18000C8D5
0x18000c896  test    r8, r8
0x18000c899  jnz     short loc_18000C8A6
0x18000c89b  mov     r8d, 8
0x18000c8a1  jmp     short loc_18000C8A6
0x18000c8a3  add     r8d, r8d
0x18000c8a6  mov     eax, r8d
0x18000c8a9  cmp     rcx, rax
0x18000c8ac  ja      short loc_18000C8A3
0x18000c8ae  mov     rcx, [rbx]; pv
0x18000c8b1  mov     edi, r8d
0x18000c8b4  lea     rdx, ds:0[rdi*8]; cb
0x18000c8bc  call    cs:__imp_CoTaskMemRealloc
0x18000c8c2  test    rax, rax
0x18000c8c5  jnz     short loc_18000C8CE
0x18000c8c7  mov     edi, 8007000Eh
0x18000c8cc  jmp     short loc_18000C901
0x18000c8ce  mov     [rbx], rax
0x18000c8d1  mov     [rbx+10h], rdi
0x18000c8d5  mov     rcx, [rbx]
0x18000c8d8  lea     rax, [r14+rsi]
0x18000c8dc  mov     r8, [rbx+8]
0x18000c8e0  xor     edi, edi
0x18000c8e2  sub     r8, r14
0x18000c8e5  shl     r8, 3; Size
0x18000c8e9  lea     rdx, [rcx+r14*8]; Src
0x18000c8ed  lea     rcx, [rcx+rax*8]; void *
0x18000c8f1  call    memmove_0
0x18000c8f6  add     [rbx+8], rsi
0x18000c8fa  jmp     short loc_18000C901
0x18000c8fc  mov     edi, 80070057h
0x18000c901  mov     eax, edi
0x18000c903  add     rsp, 28h
0x18000c907  pop     r14
0x18000c909  pop     rdi
0x18000c90a  pop     rsi
0x18000c90b  pop     rbx
0x18000c90c  retn
```
