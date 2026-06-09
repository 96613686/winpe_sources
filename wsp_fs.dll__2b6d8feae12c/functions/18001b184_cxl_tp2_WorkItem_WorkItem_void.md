# cxl::tp2::WorkItem::~WorkItem(void)

- ea: `0x18001b184`
- end: `0x18001b1d4`
- name: `??1WorkItem@tp2@cxl@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b4f0`

## callees

- `0x18000ddbc`
- `0x18001b0a4`
- `0x18001b184`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b1a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b1a3`

## pseudocode

```c
void __fastcall cxl::tp2::WorkItem::~WorkItem(PTP_WORK *this)
{
  *this = (PTP_WORK)&cxl::tp2::WorkItem::`vftable';
  if ( *((_DWORD *)this + 6) != 3 )
    CloseThreadpoolWork(this[11]);
  cxl::detail::DelegateBase::~DelegateBase((cxl::detail::DelegateBase *)(this + 13));
  cxl::detail::DelegateBase::~DelegateBase((cxl::detail::DelegateBase *)(this + 8));
  std::string::_Tidy_deallocate(this + 4);
  *this = (PTP_WORK)&cxl::RefCounted::`vftable';
}

```

## disassembly

```asm
0x18001b184  push    rbx
0x18001b186  sub     rsp, 20h
0x18001b18a  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x18001b191  mov     rbx, rcx
0x18001b194  mov     [rcx], rax
0x18001b197  mov     eax, [rcx+18h]
0x18001b19a  cmp     eax, 3
0x18001b19d  jz      short loc_18001B1A9
0x18001b19f  mov     rcx, [rcx+58h]; pwk
0x18001b1a3  call    cs:__imp_CloseThreadpoolWork
0x18001b1a9  lea     rcx, [rbx+68h]; this
0x18001b1ad  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001b1b2  lea     rcx, [rbx+40h]; this
0x18001b1b6  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001b1bb  lea     rcx, [rbx+20h]
0x18001b1bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001b1c4  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001b1cb  mov     [rbx], rax
0x18001b1ce  add     rsp, 20h
0x18001b1d2  pop     rbx
0x18001b1d3  retn
```
