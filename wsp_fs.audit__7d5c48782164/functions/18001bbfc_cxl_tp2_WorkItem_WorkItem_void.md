# cxl::tp2::WorkItem::~WorkItem(void)

- ea: `0x18001bbfc`
- end: `0x18001bc53`
- name: `??1WorkItem@tp2@cxl@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bf80`

## callees

- `0x18000e194`
- `0x18001bb14`
- `0x18001bbfc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001bc1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001bc1b`

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
0x18001bbfc  push    rbx
0x18001bbfe  sub     rsp, 20h
0x18001bc02  lea     rax, ??_7WorkItem@tp2@cxl@@6B@; const cxl::tp2::WorkItem::`vftable'
0x18001bc09  mov     rbx, rcx
0x18001bc0c  mov     [rcx], rax
0x18001bc0f  mov     eax, [rcx+18h]
0x18001bc12  cmp     eax, 3
0x18001bc15  jz      short loc_18001BC27
0x18001bc17  mov     rcx, [rcx+58h]; pwk
0x18001bc1b  call    cs:__imp_CloseThreadpoolWork
0x18001bc22  nop     dword ptr [rax+rax+00h]
0x18001bc27  lea     rcx, [rbx+68h]; this
0x18001bc2b  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001bc30  lea     rcx, [rbx+40h]; this
0x18001bc34  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001bc39  lea     rcx, [rbx+20h]
0x18001bc3d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001bc42  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001bc49  mov     [rbx], rax
0x18001bc4c  add     rsp, 20h
0x18001bc50  pop     rbx
0x18001bc51  retn
```
