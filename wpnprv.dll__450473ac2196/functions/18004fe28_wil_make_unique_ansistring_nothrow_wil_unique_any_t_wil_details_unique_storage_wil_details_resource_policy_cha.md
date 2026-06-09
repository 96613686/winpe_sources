# wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x18004fe28`
- end: `0x18004fe9b`
- name: `??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *, __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004fdd8`
- `0x18007e840`

## callees

- `0x18000d4a8`
- `0x18002ed5c`
- `0x18004fe28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fe66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fe66`

## string_xrefs

- `0x18004fe43`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3,
        const char *a4)
{
  rsize_t v6; // rbx
  _BYTE *v7; // rax
  _BYTE *v8; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = CoTaskMemAlloc(v6 + 1);
  v8 = v7;
  if ( v7 )
  {
    memcpy_s(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x18004fe28  push    rbx
0x18004fe2a  push    rbp
0x18004fe2b  push    rsi
0x18004fe2c  push    rdi
0x18004fe2d  push    r14
0x18004fe2f  sub     rsp, 20h
0x18004fe33  mov     rbp, rdx
0x18004fe36  mov     rsi, rcx
0x18004fe39  test    rdx, rdx
0x18004fe3c  jnz     short loc_18004FE55
0x18004fe3e  mov     rcx, [rsp+48h]; this
0x18004fe43  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004fe4a  mov     edx, 0FBDh; void *
0x18004fe4f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004fe55  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004fe59  inc     rbx
0x18004fe5c  cmp     byte ptr [rbx+rdx], 0
0x18004fe60  jnz     short loc_18004FE59
0x18004fe62  lea     rcx, [rbx+1]; cb
0x18004fe66  call    cs:__imp_CoTaskMemAlloc
0x18004fe6c  mov     rdi, rax
0x18004fe6f  test    rax, rax
0x18004fe72  jz      short loc_18004FE8A
0x18004fe74  mov     r9, rbx; SourceSize
0x18004fe77  lea     rdx, [rbx+1]; DestinationSize
0x18004fe7b  mov     r8, rbp; Source
0x18004fe7e  mov     rcx, rax; Destination
0x18004fe81  call    memcpy_s
0x18004fe86  mov     byte ptr [rbx+rdi], 0
0x18004fe8a  mov     [rsi], rdi
0x18004fe8d  mov     rax, rsi
0x18004fe90  add     rsp, 20h
0x18004fe94  pop     r14
0x18004fe96  pop     rdi
0x18004fe97  pop     rsi
0x18004fe98  pop     rbp
0x18004fe99  pop     rbx
0x18004fe9a  retn
```
