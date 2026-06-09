# CTDCFilterNode::`scalar deleting destructor'(uint)

- ea: `0x18000b104`
- end: `0x18000b14e`
- name: `??_GCTDCFilterNode@@QEAAPEAXI@Z`
- size: `74`
- prototype: `void *__fastcall(CTDCFilterNode *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000af64`
- `0x18000b104`
- `0x18000b370`
- `0x18000bf3c`
- `0x18000c1e0`
- `0x18000c30c`

## callees

- `0x180001194`
- `0x18000b104`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b137`
- `OLEAUT32!__imp_VariantClear` at `0x18000b137`

## pseudocode

```c
CTDCFilterNode *__fastcall CTDCFilterNode::`scalar deleting destructor'(CTDCFilterNode *this)
{
  CTDCFilterNode *v2; // rcx
  CTDCFilterNode *v3; // rcx

  v2 = (CTDCFilterNode *)*((_QWORD *)this + 1);
  if ( v2 )
    CTDCFilterNode::`scalar deleting destructor'(v2, 1u);
  v3 = (CTDCFilterNode *)*((_QWORD *)this + 2);
  if ( v3 )
    CTDCFilterNode::`scalar deleting destructor'(v3, 1u);
  VariantClear((VARIANTARG *)((char *)this + 32));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b104  push    rbx
0x18000b106  sub     rsp, 20h
0x18000b10a  mov     rbx, rcx
0x18000b10d  mov     rcx, [rcx+8]; this
0x18000b111  test    rcx, rcx
0x18000b114  jz      short loc_18000B120
0x18000b116  mov     edx, 1; unsigned int
0x18000b11b  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000b120  mov     rcx, [rbx+10h]; this
0x18000b124  test    rcx, rcx
0x18000b127  jz      short loc_18000B133
0x18000b129  mov     edx, 1; unsigned int
0x18000b12e  call    ??_GCTDCFilterNode@@QEAAPEAXI@Z; CTDCFilterNode::`scalar deleting destructor'(uint)
0x18000b133  lea     rcx, [rbx+20h]; pvarg
0x18000b137  call    cs:__imp_VariantClear
0x18000b13d  mov     rcx, rbx; Block
0x18000b140  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b145  mov     rax, rbx
0x18000b148  add     rsp, 20h
0x18000b14c  pop     rbx
0x18000b14d  retn
```
