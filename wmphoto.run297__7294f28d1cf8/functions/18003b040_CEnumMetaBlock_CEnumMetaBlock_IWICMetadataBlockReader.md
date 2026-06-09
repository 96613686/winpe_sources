# CEnumMetaBlock::CEnumMetaBlock(IWICMetadataBlockReader *)

- ea: `0x18003b040`
- end: `0x18003b0ce`
- name: `??0CEnumMetaBlock@@QEAA@PEAUIWICMetadataBlockReader@@@Z`
- size: `142`
- prototype: `CEnumMetaBlock *__fastcall(CEnumMetaBlock *__hidden this, struct IWICMetadataBlockReader *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180038ee0`
- `0x18003a7f0`
- `0x18003b160`

## callees

- `0x18002ee30`
- `0x18003b040`
- `0x180044010`

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
0x18003b040  mov     [rsp+arg_8], rbx
0x18003b045  mov     [rsp+arg_10], rsi
0x18003b04a  mov     [rsp+arg_0], rcx
0x18003b04f  push    rdi
0x18003b050  sub     rsp, 20h
0x18003b054  mov     rsi, rdx
0x18003b057  mov     rdi, rcx
0x18003b05a  mov     dword ptr [rcx+8], 0
0x18003b061  lea     rax, ??_7CWmpCodecBase@@6B@; const CWmpCodecBase::`vftable'
0x18003b068  mov     [rcx], rax
0x18003b06b  add     rcx, 18h; this
0x18003b06f  call    ??0CMTALock@@QEAA@XZ; CMTALock::CMTALock(void)
0x18003b074  nop
0x18003b075  lea     rax, ??_7CEnumMetaBlock@@6BCWmpCodecBase@@@; const CEnumMetaBlock::`vftable'{for `CWmpCodecBase'}
0x18003b07c  mov     [rdi], rax
0x18003b07f  lea     rax, ??_7CEnumMetaBlock@@6BCMTALock@@@; const CEnumMetaBlock::`vftable'{for `CMTALock'}
0x18003b086  mov     [rdi+18h], rax
0x18003b08a  lea     rax, ??_7CEnumMetaBlock@@6BIEnumUnknown@@@; const CEnumMetaBlock::`vftable'{for `IEnumUnknown'}
0x18003b091  mov     [rdi+50h], rax
0x18003b095  mov     dword ptr [rdi+58h], 0
0x18003b09c  mov     [rdi+60h], rsi
0x18003b0a0  test    rsi, rsi
0x18003b0a3  jz      short loc_18003B0B4
0x18003b0a5  mov     rax, [rsi]
0x18003b0a8  mov     rcx, rsi
0x18003b0ab  mov     rax, [rax+8]
0x18003b0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0b4  mov     dword ptr [rdi+10h], 2
0x18003b0bb  mov     rax, rdi
0x18003b0be  mov     rbx, [rsp+28h+arg_8]
0x18003b0c3  mov     rsi, [rsp+28h+arg_10]
0x18003b0c8  add     rsp, 20h
0x18003b0cc  pop     rdi
0x18003b0cd  retn
```
