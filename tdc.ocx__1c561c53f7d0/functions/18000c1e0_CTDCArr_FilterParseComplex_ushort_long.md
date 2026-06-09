# CTDCArr::FilterParseComplex(ushort * *,long *)

- ea: `0x18000c1e0`
- end: `0x18000c305`
- name: `?FilterParseComplex@CTDCArr@@AEAAPEAVCTDCFilterNode@@PEAPEAGPEAJ@Z`
- size: `293`
- prototype: `struct CTDCFilterNode *__fastcall(CTDCArr *__hidden this, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b370`
- `0x18000c30c`

## callees

- `0x180001194`
- `0x1800011b8`
- `0x18000b104`
- `0x18000c1e0`
- `0x18000c30c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c274`
- `OLEAUT32!__imp_VariantInit` at `0x18000c274`
- `OLEAUT32!__imp_VariantClear` at `0x18000c2e2`
- `OLEAUT32!__imp_VariantClear` at `0x18000c2e2`

## pseudocode

```c
struct CTDCFilterNode *__fastcall CTDCArr::FilterParseComplex(CTDCArr *this, unsigned __int16 **a2, int *a3)
{
  unsigned __int16 v4; // bp
  struct CTDCFilterNode *v7; // rax
  unsigned int v8; // edx
  struct CTDCFilterNode *v9; // rbx
  unsigned __int16 *v10; // rax
  char *v11; // rax
  char *v12; // rsi
  CTDCFilterNode *v13; // rcx
  CTDCFilterNode *v14; // rcx

  *a3 = 0;
  v4 = 0;
  v7 = CTDCArr::FilterParseSimple(this, a2, a3);
  v9 = v7;
  while ( v7 )
  {
    v10 = *a2;
    if ( **a2 == 41 || !*v10 )
      break;
    if ( *v10 != 38 && *v10 != 124 )
    {
LABEL_13:
      *a3 = -2147467259;
      goto LABEL_16;
    }
    if ( v4 )
    {
      if ( v4 != *v10 )
        goto LABEL_13;
    }
    else
    {
      v4 = *v10;
    }
    *a2 = v10 + 1;
    v11 = (char *)operator new(0x40u);
    v12 = v11;
    if ( !v11 )
    {
      *a3 = -2147024882;
      break;
    }
    *(_DWORD *)v11 = 9;
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_DWORD *)v11 + 6) = 0;
    *((_WORD *)v11 + 28) = 0;
    VariantInit((VARIANTARG *)(v11 + 32));
    *((_QWORD *)v12 + 1) = v9;
    v9 = (struct CTDCFilterNode *)v12;
    *(_DWORD *)v12 = v4 != 38;
    v7 = CTDCArr::FilterParseSimple(this, a2, a3);
    *((_QWORD *)v12 + 2) = v7;
  }
  if ( *a3 >= 0 )
    return v9;
LABEL_16:
  if ( v9 )
  {
    v13 = (CTDCFilterNode *)*((_QWORD *)v9 + 1);
    if ( v13 )
      CTDCFilterNode::`scalar deleting destructor'(v13, v8);
    v14 = (CTDCFilterNode *)*((_QWORD *)v9 + 2);
    if ( v14 )
      CTDCFilterNode::`scalar deleting destructor'(v14, v8);
    VariantClear((VARIANTARG *)((char *)v9 + 32));
    operator delete(v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000c1e0  push    rbx
0x18000c1e2  push    rbp
0x18000c1e3  push    rsi
0x18000c1e4  push    rdi
0x18000c1e5  push    r12
0x18000c1e7  push    r14
0x18000c1e9  push    r15
0x18000c1eb  sub     rsp, 20h
0x18000c1ef  xor     r12d, r12d
0x18000c1f2  mov     rdi, r8
0x18000c1f5  mov     [r8], r12d
0x18000c1f8  mov     ebp, r12d
0x18000c1fb  mov     r14, rdx
0x18000c1fe  mov     r15, rcx
0x18000c201  call    ?FilterParseSimple@CTDCArr@@AEAAPEAVCTDCFilterNode@@PEAPEAGPEAJ@Z; CTDCArr::FilterParseSimple(ushort * *,long *)
0x18000c206  mov     rbx, rax
0x18000c209  jmp     loc_18000C29F
0x18000c20e  mov     rax, [r14]
0x18000c211  cmp     word ptr [rax], 29h ; ')'
0x18000c215  jz      loc_18000C2B8
0x18000c21b  cmp     [rax], r12w
0x18000c21f  jz      loc_18000C2B8
0x18000c225  cmp     word ptr [rax], 26h ; '&'
0x18000c229  jz      short loc_18000C231
0x18000c22b  cmp     word ptr [rax], 7Ch ; '|'
0x18000c22f  jnz     short loc_18000C2AA
0x18000c231  test    bp, bp
0x18000c234  jnz     short loc_18000C23B
0x18000c236  movzx   ebp, word ptr [rax]
0x18000c239  jmp     short loc_18000C240
0x18000c23b  cmp     bp, [rax]
0x18000c23e  jnz     short loc_18000C2AA
0x18000c240  add     rax, 2
0x18000c244  mov     ecx, 40h ; '@'; Size
0x18000c249  mov     [r14], rax
0x18000c24c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c251  mov     rsi, rax
0x18000c254  test    rax, rax
0x18000c257  jz      short loc_18000C2B2
0x18000c259  lea     rcx, [rax+20h]; pvarg
0x18000c25d  mov     dword ptr [rax], 9
0x18000c263  mov     [rax+8], r12
0x18000c267  mov     [rax+10h], r12
0x18000c26b  mov     [rax+18h], r12d
0x18000c26f  mov     [rax+38h], r12w
0x18000c274  call    cs:__imp_VariantInit
0x18000c27a  mov     ecx, r12d
0x18000c27d  mov     [rsi+8], rbx
0x18000c281  cmp     bp, 26h ; '&'
0x18000c285  mov     r8, rdi; int *
0x18000c288  mov     rdx, r14; unsigned __int16 **
0x18000c28b  mov     rbx, rsi
0x18000c28e  setnz   cl
0x18000c291  mov     [rsi], ecx
0x18000c293  mov     rcx, r15; this
0x18000c296  call    ?FilterParseSimple@CTDCArr@@AEAAPEAVCTDCFilterNode@@PEAPEAGPEAJ@Z; CTDCArr::FilterParseSimple(ushort * *,long *)
0x18000c29b  mov     [rsi+10h], rax
0x18000c29f  test    rax, rax
0x18000c2a2  jnz     loc_18000C20E
0x18000c2a8  jmp     short loc_18000C2B8
0x18000c2aa  mov     dword ptr [rdi], 80004005h
0x18000c2b0  jmp     short loc_18000C2BD
0x18000c2b2  mov     dword ptr [rdi], 8007000Eh
0x18000c2b8  cmp     [rdi], r12d
0x18000c2bb  jge     short loc_18000C2F3
0x18000c2bd  test    rbx, rbx
0x18000c2c0  jz      short loc_18000C2F3
0x18000c2c2  mov     rcx, [rbx+8]; this
0x18000c2c6  test    rcx, rcx
0x18000c2c9  jz      short loc_18000C2D0
0x18000c2cb  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000c2d0  mov     rcx, [rbx+10h]; this
0x18000c2d4  test    rcx, rcx
0x18000c2d7  jz      short loc_18000C2DE
0x18000c2d9  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000c2de  lea     rcx, [rbx+20h]; pvarg
0x18000c2e2  call    cs:__imp_VariantClear
0x18000c2e8  mov     rcx, rbx; Block
0x18000c2eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c2f0  mov     rbx, r12
0x18000c2f3  mov     rax, rbx
0x18000c2f6  add     rsp, 20h
0x18000c2fa  pop     r15
0x18000c2fc  pop     r14
0x18000c2fe  pop     r12
0x18000c300  pop     rdi
0x18000c301  pop     rsi
0x18000c302  pop     rbp
0x18000c303  pop     rbx
0x18000c304  retn
```
