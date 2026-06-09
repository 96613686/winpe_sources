# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180008e84`
- end: `0x180008f1c`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011024`

## callees

- `0x180008e84`
- `0x18000908c`
- `0x180011acc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ecd`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180008e84  mov     rax, rsp
0x180008e87  mov     [rax+8], rbx
0x180008e8b  push    rdi
0x180008e8c  sub     rsp, 40h
0x180008e90  mov     qword ptr [rax-28h], 0
0x180008e98  lea     r8, [rsp+48h+var_28]
0x180008e9d  mov     qword ptr [rax-20h], 0
0x180008ea5  mov     rdi, rdx
0x180008ea8  mov     byte ptr [rax-18h], 0
0x180008eac  mov     rbx, rcx
0x180008eaf  xor     eax, eax
0x180008eb1  mov     [rsp+48h+var_17], eax
0x180008eb5  mov     [rsp+48h+var_13], ax
0x180008eba  mov     [rsp+48h+var_11], al
0x180008ebe  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180008ec3  mov     rcx, [rsp+48h+cb]; cb
0x180008ec8  test    rcx, rcx
0x180008ecb  jz      short loc_180008F07
0x180008ecd  call    cs:__imp_CoTaskMemAlloc
0x180008ed3  mov     rdx, rax
0x180008ed6  mov     rcx, rdi
0x180008ed9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180008ede  mov     rax, [rdi]
0x180008ee1  test    rax, rax
0x180008ee4  jz      short loc_180008EFA
0x180008ee6  lea     r8, [rsp+48h+var_28]
0x180008eeb  mov     [rsp+48h+var_28], rax
0x180008ef0  mov     rcx, rbx; this
0x180008ef3  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180008ef8  jmp     short loc_180008F11
0x180008efa  cmp     dword ptr [rbx+8], 0
0x180008efe  jl      short loc_180008F07
0x180008f00  mov     dword ptr [rbx+8], 8007000Eh
0x180008f07  xor     edx, edx
0x180008f09  mov     rcx, rdi
0x180008f0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180008f11  mov     rbx, [rsp+48h+arg_0]
0x180008f16  add     rsp, 40h
0x180008f1a  pop     rdi
0x180008f1b  retn
```
