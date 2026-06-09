# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001472c`
- end: `0x180014786`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `90`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800146dc`
- `0x18003cd38`
- `0x18004f22c`

## callees

- `0x18001472c`
- `0x180019c88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014761`

## string_xrefs

- `0x180014747`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _WORD *v6; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = CoTaskMemAlloc(2 * a3 + 2);
  if ( v6 )
  {
    *v6 = 0;
    v6[a3] = 0;
  }
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x18001472c  mov     [rsp+arg_0], rbx
0x180014731  push    rdi
0x180014732  sub     rsp, 20h
0x180014736  mov     rdi, r8
0x180014739  mov     rbx, rcx
0x18001473c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180014740  jnz     short loc_180014759
0x180014742  mov     rcx, [rsp+28h]; this
0x180014747  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001474e  mov     edx, 0F89h; void *
0x180014753  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180014759  lea     rcx, ds:2[r8*2]; cb
0x180014761  call    cs:__imp_CoTaskMemAlloc
0x180014767  test    rax, rax
0x18001476a  jz      short loc_180014775
0x18001476c  xor     ecx, ecx
0x18001476e  mov     [rax], cx
0x180014771  mov     [rax+rdi*2], cx
0x180014775  mov     [rbx], rax
0x180014778  mov     rax, rbx
0x18001477b  mov     rbx, [rsp+28h+arg_0]
0x180014780  add     rsp, 20h
0x180014784  pop     rdi
0x180014785  retn
```
