# cxl::tp2::WorkItem::~WorkItem(void)

- ea: `0x180018a30`
- end: `0x180018a87`
- name: `??1WorkItem@tp2@cxl@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018db0`

## callees

- `0x18000dab8`
- `0x180018948`
- `0x180018a30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180018a4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180018a4f`

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
0x180018a30  push    rbx
0x180018a32  sub     rsp, 20h
0x180018a36  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x180018a3d  mov     rbx, rcx
0x180018a40  mov     [rcx], rax
0x180018a43  mov     eax, [rcx+18h]
0x180018a46  cmp     eax, 3
0x180018a49  jz      short loc_180018A5B
0x180018a4b  mov     rcx, [rcx+58h]; pwk
0x180018a4f  call    cs:__imp_CloseThreadpoolWork
0x180018a56  nop     dword ptr [rax+rax+00h]
0x180018a5b  lea     rcx, [rbx+68h]; this
0x180018a5f  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x180018a64  lea     rcx, [rbx+40h]; this
0x180018a68  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x180018a6d  lea     rcx, [rbx+20h]
0x180018a71  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018a76  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180018a7d  mov     [rbx], rax
0x180018a80  add     rsp, 20h
0x180018a84  pop     rbx
0x180018a85  retn
```
