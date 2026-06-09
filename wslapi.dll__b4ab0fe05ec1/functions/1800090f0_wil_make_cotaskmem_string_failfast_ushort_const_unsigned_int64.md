# wil::make_cotaskmem_string_failfast(ushort const *,unsigned __int64)

- ea: `0x1800090f0`
- end: `0x180009129`
- name: `?make_cotaskmem_string_failfast@wil@@YA@PEBG_K@Z`
- size: `57`
- prototype: `wil *__fastcall(wil *this, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180008bd8`

## callees

- `0x180006b80`
- `0x180008454`
- `0x1800090f0`

## string_xrefs

- `0x18000910e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
wil *__fastcall wil::make_cotaskmem_string_failfast(wil *this, char *a2, unsigned __int64 a3, const char *a4)
{
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    this,
    a2,
    a3,
    a4);
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0xFDC,
      (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  return this;
}

```

## disassembly

```asm
0x1800090f0  push    rbx
0x1800090f2  sub     rsp, 20h
0x1800090f6  xor     eax, eax
0x1800090f8  mov     rbx, rcx
0x1800090fb  mov     [rcx], rax
0x1800090fe  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009103  cmp     qword ptr [rbx], 0
0x180009107  mov     rcx, [rsp+28h]; this
0x18000910c  jnz     short loc_180009120
0x18000910e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009115  mov     edx, 0FDCh; void *
0x18000911a  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180009120  mov     rax, rbx
0x180009123  add     rsp, 20h
0x180009127  pop     rbx
0x180009128  retn
```
