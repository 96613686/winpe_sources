# CEnumMetaBlock::CEnumMetaBlock(IWICMetadataBlockReader *)

- ea: `0x18003b7f8`
- end: `0x18003b887`
- name: `??0CEnumMetaBlock@@QEAA@PEAUIWICMetadataBlockReader@@@Z`
- size: `143`
- prototype: `CEnumMetaBlock *__fastcall(CEnumMetaBlock *__hidden this, struct IWICMetadataBlockReader *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800395a0`
- `0x18003af80`
- `0x18003b920`

## callees

- `0x18002f1c0`
- `0x18003b7f8`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CEnumMetaBlock *__fastcall CEnumMetaBlock::CEnumMetaBlock(CEnumMetaBlock *this, struct IWICMetadataBlockReader *a2)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CWmpCodecBase::`vftable';
  CMTALock::CMTALock((CEnumMetaBlock *)((char *)this + 24));
  *(_QWORD *)this = &CEnumMetaBlock::`vftable'{for `CWmpCodecBase'};
  *((_QWORD *)this + 3) = &CEnumMetaBlock::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 10) = &CEnumMetaBlock::`vftable'{for `IEnumUnknown'};
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IWICMetadataBlockReader *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 4) = 2;
  return this;
}

```

## disassembly

```asm
0x18003b7f8  mov     [rsp+arg_8], rbx
0x18003b7fd  mov     [rsp+arg_10], rsi
0x18003b802  mov     [rsp+arg_0], rcx
0x18003b807  push    rdi
0x18003b808  sub     rsp, 20h
0x18003b80c  mov     rsi, rdx
0x18003b80f  mov     rdi, rcx
0x18003b812  mov     dword ptr [rcx+8], 0
0x18003b819  lea     rax, ??_7CWmpCodecBase@@6B@; const CWmpCodecBase::`vftable'
0x18003b820  mov     [rcx], rax
0x18003b823  add     rcx, 18h; this
0x18003b827  call    ??0CMTALock@@QEAA@XZ; CMTALock::CMTALock(void)
0x18003b82c  nop
0x18003b82d  lea     rax, ??_7CEnumMetaBlock@@6BCWmpCodecBase@@@; const CEnumMetaBlock::`vftable'{for `CWmpCodecBase'}
0x18003b834  mov     [rdi], rax
0x18003b837  lea     rax, ??_7CEnumMetaBlock@@6BCMTALock@@@; const CEnumMetaBlock::`vftable'{for `CMTALock'}
0x18003b83e  mov     [rdi+18h], rax
0x18003b842  lea     rax, ??_7CEnumMetaBlock@@6BIEnumUnknown@@@; const CEnumMetaBlock::`vftable'{for `IEnumUnknown'}
0x18003b849  mov     [rdi+50h], rax
0x18003b84d  mov     dword ptr [rdi+58h], 0
0x18003b854  mov     [rdi+60h], rsi
0x18003b858  test    rsi, rsi
0x18003b85b  jz      short loc_18003B86C
0x18003b85d  mov     rax, [rsi]
0x18003b860  mov     rcx, rsi
0x18003b863  mov     rax, [rax+8]
0x18003b867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b86c  mov     dword ptr [rdi+10h], 2
0x18003b873  mov     rax, rdi
0x18003b876  mov     rbx, [rsp+28h+arg_8]
0x18003b87b  mov     rsi, [rsp+28h+arg_10]
0x18003b880  add     rsp, 20h
0x18003b884  pop     rdi
0x18003b885  retn
```
