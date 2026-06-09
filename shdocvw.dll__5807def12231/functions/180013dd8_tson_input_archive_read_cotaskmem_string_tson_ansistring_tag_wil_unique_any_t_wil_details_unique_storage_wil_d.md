# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180013dd8`
- end: `0x180013e70`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800129cc`
- `0x180013724`

## callees

- `0x180013dd8`
- `0x1800140c4`
- `0x18001c2e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e21`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180013dd8  mov     rax, rsp
0x180013ddb  mov     [rax+8], rbx
0x180013ddf  push    rdi
0x180013de0  sub     rsp, 40h
0x180013de4  mov     qword ptr [rax-28h], 0
0x180013dec  lea     r8, [rsp+48h+var_28]
0x180013df1  mov     qword ptr [rax-20h], 0
0x180013df9  mov     rdi, rdx
0x180013dfc  mov     byte ptr [rax-18h], 0
0x180013e00  mov     rbx, rcx
0x180013e03  xor     eax, eax
0x180013e05  mov     [rsp+48h+var_17], eax
0x180013e09  mov     [rsp+48h+var_13], ax
0x180013e0e  mov     [rsp+48h+var_11], al
0x180013e12  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180013e17  mov     rcx, [rsp+48h+cb]; cb
0x180013e1c  test    rcx, rcx
0x180013e1f  jz      short loc_180013E5B
0x180013e21  call    cs:__imp_CoTaskMemAlloc
0x180013e27  mov     rdx, rax
0x180013e2a  mov     rcx, rdi
0x180013e2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013e32  mov     rax, [rdi]
0x180013e35  test    rax, rax
0x180013e38  jz      short loc_180013E4E
0x180013e3a  lea     r8, [rsp+48h+var_28]
0x180013e3f  mov     [rsp+48h+var_28], rax
0x180013e44  mov     rcx, rbx; this
0x180013e47  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180013e4c  jmp     short loc_180013E65
0x180013e4e  cmp     dword ptr [rbx+8], 0
0x180013e52  jl      short loc_180013E5B
0x180013e54  mov     dword ptr [rbx+8], 8007000Eh
0x180013e5b  xor     edx, edx
0x180013e5d  mov     rcx, rdi
0x180013e60  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013e65  mov     rbx, [rsp+48h+arg_0]
0x180013e6a  add     rsp, 40h
0x180013e6e  pop     rdi
0x180013e6f  retn
```
