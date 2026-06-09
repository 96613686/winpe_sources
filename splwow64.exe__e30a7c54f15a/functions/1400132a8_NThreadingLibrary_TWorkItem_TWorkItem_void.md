# NThreadingLibrary::TWorkItem::~TWorkItem(void)

- ea: `0x1400132a8`
- end: `0x140013308`
- name: `??1TWorkItem@NThreadingLibrary@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(NThreadingLibrary::TWorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010810`
- `0x1400133c0`

## callees

- `0x140013174`
- `0x140014038`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkItem::~TWorkItem(NThreadingLibrary::TWorkItem *this)
{
  NCoreLibrary::TLink *v2; // rcx

  *(_QWORD *)this = &NThreadingLibrary::TWorkItem::`vftable'{for `NCoreLibrary::TReferenceCount'};
  *((_QWORD *)this + 2) = &NThreadingLibrary::TWorkItem::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  v2 = (NThreadingLibrary::TWorkItem *)((char *)this + 32);
  *(_QWORD *)v2 = &NThreadingLibrary::TWorkItem::`vftable'{for `NCoreLibrary::TLink'};
  *(_QWORD *)((char *)this + 68) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 10) = 0;
  NCoreLibrary::TLink::~TLink(v2);
  NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv((NThreadingLibrary::TWorkItem *)((char *)this + 16));
  *(_QWORD *)this = &NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x1400132a8  mov     [rsp+arg_0], rbx
0x1400132ad  push    rdi
0x1400132ae  sub     rsp, 20h
0x1400132b2  mov     rdi, rcx
0x1400132b5  lea     rax, ??_7TWorkItem@NThreadingLibrary@@6BTReferenceCount@NCoreLibrary@@@; const NThreadingLibrary::TWorkItem::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x1400132bc  mov     [rcx], rax
0x1400132bf  lea     rax, ??_7TWorkItem@NThreadingLibrary@@6BTTpSetWorkEnv@1@@; const NThreadingLibrary::TWorkItem::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x1400132c6  mov     [rcx+10h], rax
0x1400132ca  add     rcx, 20h ; ' '; this
0x1400132ce  lea     rax, ??_7TWorkItem@NThreadingLibrary@@6BTLink@NCoreLibrary@@@; const NThreadingLibrary::TWorkItem::`vftable'{for `NCoreLibrary::TLink'}
0x1400132d5  mov     [rcx], rax
0x1400132d8  xor     eax, eax
0x1400132da  mov     [rdi+44h], rax
0x1400132de  mov     [rdi+58h], eax
0x1400132e1  mov     [rdi+50h], rax
0x1400132e5  call    ??1TLink@NCoreLibrary@@UEAA@XZ; NCoreLibrary::TLink::~TLink(void)
0x1400132ea  lea     rcx, [rdi+10h]; this
0x1400132ee  call    ??1TTpSetWorkEnv@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(void)
0x1400132f3  mov     rbx, [rsp+28h+arg_0]
0x1400132f8  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x1400132ff  mov     [rdi], rax
0x140013302  add     rsp, 20h
0x140013306  pop     rdi
0x140013307  retn
```
