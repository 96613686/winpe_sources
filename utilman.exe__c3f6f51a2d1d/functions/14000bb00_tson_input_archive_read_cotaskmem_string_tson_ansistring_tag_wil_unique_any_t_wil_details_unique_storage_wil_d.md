# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x14000bb00`
- end: `0x14000bb9f`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000af04`
- `0x14000b4a0`

## callees

- `0x14000bb00`
- `0x14000bdfc`
- `0x140011868`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14000bb49`
- `ole32!CoTaskMemAlloc` at `0x14000bb49`

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
0x14000bb00  mov     rax, rsp
0x14000bb03  mov     [rax+8], rbx
0x14000bb07  push    rdi
0x14000bb08  sub     rsp, 40h
0x14000bb0c  mov     qword ptr [rax-28h], 0
0x14000bb14  lea     r8, [rsp+48h+var_28]
0x14000bb19  mov     qword ptr [rax-20h], 0
0x14000bb21  mov     rdi, rdx
0x14000bb24  mov     byte ptr [rax-18h], 0
0x14000bb28  mov     rbx, rcx
0x14000bb2b  xor     eax, eax
0x14000bb2d  mov     [rsp+48h+var_17], eax
0x14000bb31  mov     [rsp+48h+var_13], ax
0x14000bb36  mov     [rsp+48h+var_11], al
0x14000bb3a  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14000bb3f  mov     rcx, [rsp+48h+cb]; cb
0x14000bb44  test    rcx, rcx
0x14000bb47  jz      short loc_14000BB89
0x14000bb49  call    cs:__imp_CoTaskMemAlloc
0x14000bb50  nop     dword ptr [rax+rax+00h]
0x14000bb55  mov     rdx, rax
0x14000bb58  mov     rcx, rdi
0x14000bb5b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14000bb60  mov     rax, [rdi]
0x14000bb63  test    rax, rax
0x14000bb66  jz      short loc_14000BB7C
0x14000bb68  lea     r8, [rsp+48h+var_28]
0x14000bb6d  mov     [rsp+48h+var_28], rax
0x14000bb72  mov     rcx, rbx; this
0x14000bb75  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14000bb7a  jmp     short loc_14000BB93
0x14000bb7c  cmp     dword ptr [rbx+8], 0
0x14000bb80  jl      short loc_14000BB89
0x14000bb82  mov     dword ptr [rbx+8], 8007000Eh
0x14000bb89  xor     edx, edx
0x14000bb8b  mov     rcx, rdi
0x14000bb8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14000bb93  mov     rbx, [rsp+48h+arg_0]
0x14000bb98  add     rsp, 40h
0x14000bb9c  pop     rdi
0x14000bb9d  retn
```
