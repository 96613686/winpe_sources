# CreateArchiveImpl::~CreateArchiveImpl(void)

- ea: `0x18005b760`
- end: `0x18005b811`
- name: `??1CreateArchiveImpl@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CreateArchiveImpl *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005ca84`
- `0x18005e420`

## callees

- `0x18002abd0`
- `0x180030a3c`
- `0x180036f50`
- `0x180040e04`
- `0x18005b6b0`
- `0x18005b6d0`
- `0x18005b6f0`
- `0x18005b760`

## import_xrefs

- `archiveint!archive_write_fail` at `0x18005b7a4`
- `archiveint!archive_write_fail` at `0x18005b7a4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005b79a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005b79a`

## pseudocode

```c
void __fastcall CreateArchiveImpl::~CreateArchiveImpl(CreateArchiveImpl *this)
{
  void *v2; // rcx
  char FileInformation[8]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 != (void *)-1LL )
  {
    FileInformation[0] = 1;
    SetFileInformationByHandle(v2, FileDispositionInfo, FileInformation, 1u);
    archive_write_fail(*((_QWORD *)this + 8));
  }
  Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>((char *)this + 192);
  std::wstring::_Tidy_deallocate((char *)this + 160);
  std::wstring::_Tidy_deallocate((char *)this + 128);
  if ( *((_QWORD *)this + 11) )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref((char *)this + 88);
  wil::details::unique_storage<wil::details::resource_policy<archive_entry_linkresolver *,void (*)(archive_entry_linkresolver *),&void archive_entry_linkresolver_free(archive_entry_linkresolver *),wistd::integral_constant<unsigned __int64,0>,archive_entry_linkresolver *,archive_entry_linkresolver *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry_linkresolver *,void (*)(archive_entry_linkresolver *),&void archive_entry_linkresolver_free(archive_entry_linkresolver *),wistd::integral_constant<unsigned __int64,0>,archive_entry_linkresolver *,archive_entry_linkresolver *,0,std::nullptr_t>>((char *)this + 80);
  wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>((char *)this + 72);
  wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>((char *)this + 64);
}

```

## disassembly

```asm
0x18005b760  mov     [rsp+arg_8], rbx
0x18005b765  push    rdi
0x18005b766  sub     rsp, 30h
0x18005b76a  mov     rax, cs:__security_cookie
0x18005b771  xor     rax, rsp
0x18005b774  mov     [rsp+38h+var_10], rax
0x18005b779  mov     rbx, rcx
0x18005b77c  mov     rcx, [rcx+20h]; hFile
0x18005b780  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b784  jz      short loc_18005B7AA
0x18005b786  mov     [rsp+38h+FileInformation], 1
0x18005b78b  mov     r9d, 1; dwBufferSize
0x18005b791  lea     r8, [rsp+38h+FileInformation]; lpFileInformation
0x18005b796  lea     edx, [r9+3]; FileInformationClass
0x18005b79a  call    cs:__imp_SetFileInformationByHandle
0x18005b7a0  mov     rcx, [rbx+40h]
0x18005b7a4  call    cs:__imp_archive_write_fail
0x18005b7aa  lea     rcx, [rbx+0C0h]
0x18005b7b1  call    ??1?$MakeAllocator@VCLocalCopyDownloadSink@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(void)
0x18005b7b6  lea     rcx, [rbx+0A0h]
0x18005b7bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b7c2  lea     rcx, [rbx+80h]
0x18005b7c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b7ce  lea     rcx, [rbx+58h]
0x18005b7d2  cmp     qword ptr [rcx], 0
0x18005b7d6  jz      short loc_18005B7DD
0x18005b7d8  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005b7dd  lea     rcx, [rbx+50h]
0x18005b7e1  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive_entry_linkresolver@@P6AXPEAU1@@Z$1?archive_entry_linkresolver_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive_entry_linkresolver *,void (*)(archive_entry_linkresolver *),&archive_entry_linkresolver_free(archive_entry_linkresolver *),wistd::integral_constant<unsigned __int64,0>,archive_entry_linkresolver *,archive_entry_linkresolver *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry_linkresolver *,void (*)(archive_entry_linkresolver *),&archive_entry_linkresolver_free(archive_entry_linkresolver *),wistd::integral_constant<unsigned __int64,0>,archive_entry_linkresolver *,archive_entry_linkresolver *,0,std::nullptr_t>>(void)
0x18005b7e6  lea     rcx, [rbx+48h]
0x18005b7ea  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive_entry@@P6AXPEAU1@@Z$1?archive_entry_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(void)
0x18005b7ef  lea     rcx, [rbx+40h]
0x18005b7f3  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_write_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x18005b7f8  nop
0x18005b7f9  mov     rcx, [rsp+38h+var_10]
0x18005b7fe  xor     rcx, rsp; StackCookie
0x18005b801  call    __security_check_cookie
0x18005b806  mov     rbx, [rsp+38h+arg_8]
0x18005b80b  add     rsp, 30h
0x18005b80f  pop     rdi
0x18005b810  retn
```
