# wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort const (&)[2],ushort const *,ushort const (&)[2],ushort const *>(ushort const * &&,ushort const (&)[2],ushort const * &&,ushort const (&)[2],ushort const * &&)

- ea: `0x14005124c`
- end: `0x1400512b1`
- name: `??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGAEAY01$$CBGPEBGAEAY01$$CBGPEBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@$$QEAPEBGAEAY01$$CBG010@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140057044`

## callees

- `0x14005124c`
- `0x1400512b8`
- `0x14005d1a8`

## string_xrefs

- `0x140051295`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const (&)[2],unsigned short const *,unsigned short const (&)[2],unsigned short const *>(
        _QWORD *a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  int v7; // eax
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v7 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short [2],unsigned short const *,unsigned short [2],unsigned short const *>(
         (_DWORD)a1,
         a2,
         (unsigned int)L"\\",
         a4,
         (__int64)L"\\",
         a6);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7B3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v7,
      v9);
  return a1;
}

```

## disassembly

```asm
0x14005124c  mov     [rsp+arg_0], rcx
0x140051251  push    rbx
0x140051252  sub     rsp, 40h
0x140051256  mov     rbx, rcx
0x140051259  mov     [rsp+48h+var_18], 0
0x140051261  xor     eax, eax
0x140051263  mov     [rcx], rax
0x140051266  mov     [rsp+48h+var_18], 1
0x14005126e  mov     rax, [rsp+48h+arg_28]
0x140051273  mov     [rsp+48h+var_20], rax
0x140051278  lea     r8, asc_14006EB64; "\\"
0x14005127f  mov     qword ptr [rsp+48h+var_28], r8; int
0x140051284  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG$$BY01GPEBG$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBGAEAY01$$CBG121@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort [2],ushort const *,ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const (&)[2],ushort const * const &,ushort const (&)[2],ushort const * const &)
0x140051289  test    eax, eax
0x14005128b  jns     short loc_1400512A7
0x14005128d  mov     rcx, [rsp+48h]; this
0x140051292  mov     r9d, eax; char *
0x140051295  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005129c  mov     edx, 7B3h; void *
0x1400512a1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400512a7  mov     rax, rbx
0x1400512aa  add     rsp, 40h
0x1400512ae  pop     rbx
0x1400512af  retn
```
