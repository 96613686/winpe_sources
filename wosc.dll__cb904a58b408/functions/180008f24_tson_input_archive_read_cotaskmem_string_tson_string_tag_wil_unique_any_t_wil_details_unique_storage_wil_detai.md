# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180008f24`
- end: `0x180008fbf`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011024`

## callees

- `0x180008f24`
- `0x180009130`
- `0x180011acc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f70`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180008f24  mov     rax, rsp
0x180008f27  mov     [rax+8], rbx
0x180008f2b  push    rdi
0x180008f2c  sub     rsp, 40h
0x180008f30  mov     qword ptr [rax-28h], 0
0x180008f38  lea     r8, [rsp+48h+var_28]
0x180008f3d  mov     qword ptr [rax-20h], 0
0x180008f45  mov     rdi, rdx
0x180008f48  mov     byte ptr [rax-18h], 0
0x180008f4c  mov     rbx, rcx
0x180008f4f  xor     eax, eax
0x180008f51  mov     [rsp+48h+var_17], eax
0x180008f55  mov     [rsp+48h+var_13], ax
0x180008f5a  mov     [rsp+48h+var_11], al
0x180008f5e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180008f63  mov     rcx, [rsp+48h+var_20]
0x180008f68  test    rcx, rcx
0x180008f6b  jz      short loc_180008FAA
0x180008f6d  add     rcx, rcx; cb
0x180008f70  call    cs:__imp_CoTaskMemAlloc
0x180008f76  mov     rdx, rax
0x180008f79  mov     rcx, rdi
0x180008f7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180008f81  mov     rax, [rdi]
0x180008f84  test    rax, rax
0x180008f87  jz      short loc_180008F9D
0x180008f89  lea     r8, [rsp+48h+var_28]
0x180008f8e  mov     [rsp+48h+var_28], rax
0x180008f93  mov     rcx, rbx; this
0x180008f96  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180008f9b  jmp     short loc_180008FB4
0x180008f9d  cmp     dword ptr [rbx+8], 0
0x180008fa1  jl      short loc_180008FAA
0x180008fa3  mov     dword ptr [rbx+8], 8007000Eh
0x180008faa  xor     edx, edx
0x180008fac  mov     rcx, rdi
0x180008faf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180008fb4  mov     rbx, [rsp+48h+arg_0]
0x180008fb9  add     rsp, 40h
0x180008fbd  pop     rdi
0x180008fbe  retn
```
