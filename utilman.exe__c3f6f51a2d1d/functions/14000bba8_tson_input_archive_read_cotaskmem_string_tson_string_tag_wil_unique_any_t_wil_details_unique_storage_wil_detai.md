# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14000bba8`
- end: `0x14000bc4a`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140010954`

## callees

- `0x14000bba8`
- `0x14000bea0`
- `0x140011868`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14000bbf4`
- `ole32!CoTaskMemAlloc` at `0x14000bbf4`

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
0x14000bba8  mov     rax, rsp
0x14000bbab  mov     [rax+8], rbx
0x14000bbaf  push    rdi
0x14000bbb0  sub     rsp, 40h
0x14000bbb4  mov     qword ptr [rax-28h], 0
0x14000bbbc  lea     r8, [rsp+48h+var_28]
0x14000bbc1  mov     qword ptr [rax-20h], 0
0x14000bbc9  mov     rdi, rdx
0x14000bbcc  mov     byte ptr [rax-18h], 0
0x14000bbd0  mov     rbx, rcx
0x14000bbd3  xor     eax, eax
0x14000bbd5  mov     [rsp+48h+var_17], eax
0x14000bbd9  mov     [rsp+48h+var_13], ax
0x14000bbde  mov     [rsp+48h+var_11], al
0x14000bbe2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14000bbe7  mov     rcx, [rsp+48h+var_20]
0x14000bbec  test    rcx, rcx
0x14000bbef  jz      short loc_14000BC34
0x14000bbf1  add     rcx, rcx; cb
0x14000bbf4  call    cs:__imp_CoTaskMemAlloc
0x14000bbfb  nop     dword ptr [rax+rax+00h]
0x14000bc00  mov     rdx, rax
0x14000bc03  mov     rcx, rdi
0x14000bc06  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14000bc0b  mov     rax, [rdi]
0x14000bc0e  test    rax, rax
0x14000bc11  jz      short loc_14000BC27
0x14000bc13  lea     r8, [rsp+48h+var_28]
0x14000bc18  mov     [rsp+48h+var_28], rax
0x14000bc1d  mov     rcx, rbx; this
0x14000bc20  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14000bc25  jmp     short loc_14000BC3E
0x14000bc27  cmp     dword ptr [rbx+8], 0
0x14000bc2b  jl      short loc_14000BC34
0x14000bc2d  mov     dword ptr [rbx+8], 8007000Eh
0x14000bc34  xor     edx, edx
0x14000bc36  mov     rcx, rdi
0x14000bc39  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14000bc3e  mov     rbx, [rsp+48h+arg_0]
0x14000bc43  add     rsp, 40h
0x14000bc47  pop     rdi
0x14000bc48  retn
```
