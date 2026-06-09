# cxl::tp2::WorkItem::~WorkItem(void)

- ea: `0x18001809c`
- end: `0x1800180ec`
- name: `??1WorkItem@tp2@cxl@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018410`

## callees

- `0x18000d69c`
- `0x180017fbc`
- `0x18001809c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800180bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800180bb`

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
0x18001809c  push    rbx
0x18001809e  sub     rsp, 20h
0x1800180a2  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x1800180a9  mov     rbx, rcx
0x1800180ac  mov     [rcx], rax
0x1800180af  mov     eax, [rcx+18h]
0x1800180b2  cmp     eax, 3
0x1800180b5  jz      short loc_1800180C1
0x1800180b7  mov     rcx, [rcx+58h]; pwk
0x1800180bb  call    cs:__imp_CloseThreadpoolWork
0x1800180c1  lea     rcx, [rbx+68h]; this
0x1800180c5  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x1800180ca  lea     rcx, [rbx+40h]; this
0x1800180ce  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x1800180d3  lea     rcx, [rbx+20h]
0x1800180d7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800180dc  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x1800180e3  mov     [rbx], rax
0x1800180e6  add     rsp, 20h
0x1800180ea  pop     rbx
0x1800180eb  retn
```
