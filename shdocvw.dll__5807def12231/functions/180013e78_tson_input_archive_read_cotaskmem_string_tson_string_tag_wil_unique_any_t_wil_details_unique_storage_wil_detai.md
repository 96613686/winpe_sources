# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180013e78`
- end: `0x180013f13`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b840`

## callees

- `0x180013e78`
- `0x180014168`
- `0x18001c2e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ec4`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180013e78  mov     rax, rsp
0x180013e7b  mov     [rax+8], rbx
0x180013e7f  push    rdi
0x180013e80  sub     rsp, 40h
0x180013e84  mov     qword ptr [rax-28h], 0
0x180013e8c  lea     r8, [rsp+48h+var_28]
0x180013e91  mov     qword ptr [rax-20h], 0
0x180013e99  mov     rdi, rdx
0x180013e9c  mov     byte ptr [rax-18h], 0
0x180013ea0  mov     rbx, rcx
0x180013ea3  xor     eax, eax
0x180013ea5  mov     [rsp+48h+var_17], eax
0x180013ea9  mov     [rsp+48h+var_13], ax
0x180013eae  mov     [rsp+48h+var_11], al
0x180013eb2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180013eb7  mov     rcx, [rsp+48h+var_20]
0x180013ebc  test    rcx, rcx
0x180013ebf  jz      short loc_180013EFE
0x180013ec1  add     rcx, rcx; cb
0x180013ec4  call    cs:__imp_CoTaskMemAlloc
0x180013eca  mov     rdx, rax
0x180013ecd  mov     rcx, rdi
0x180013ed0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013ed5  mov     rax, [rdi]
0x180013ed8  test    rax, rax
0x180013edb  jz      short loc_180013EF1
0x180013edd  lea     r8, [rsp+48h+var_28]
0x180013ee2  mov     [rsp+48h+var_28], rax
0x180013ee7  mov     rcx, rbx; this
0x180013eea  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180013eef  jmp     short loc_180013F08
0x180013ef1  cmp     dword ptr [rbx+8], 0
0x180013ef5  jl      short loc_180013EFE
0x180013ef7  mov     dword ptr [rbx+8], 8007000Eh
0x180013efe  xor     edx, edx
0x180013f00  mov     rcx, rdi
0x180013f03  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013f08  mov     rbx, [rsp+48h+arg_0]
0x180013f0d  add     rsp, 40h
0x180013f11  pop     rdi
0x180013f12  retn
```
