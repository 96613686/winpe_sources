# wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x1800d1030`
- end: `0x1800d10a3`
- name: `??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d2a8c`

## callees

- `0x180056534`
- `0x1800878c4`
- `0x1800d1030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d106e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d106e`

## string_xrefs

- `0x1800d104b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
    memcpy_s_0(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x1800d1030  push    rbx
0x1800d1032  push    rbp
0x1800d1033  push    rsi
0x1800d1034  push    rdi
0x1800d1035  push    r14
0x1800d1037  sub     rsp, 20h
0x1800d103b  mov     rbp, rdx
0x1800d103e  mov     rsi, rcx
0x1800d1041  test    rdx, rdx
0x1800d1044  jnz     short loc_1800D105D
0x1800d1046  mov     rcx, [rsp+48h]; this
0x1800d104b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d1052  mov     edx, 0FBDh; void *
0x1800d1057  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d105d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d1061  inc     rbx
0x1800d1064  cmp     byte ptr [rbx+rdx], 0
0x1800d1068  jnz     short loc_1800D1061
0x1800d106a  lea     rcx, [rbx+1]; cb
0x1800d106e  call    cs:__imp_CoTaskMemAlloc
0x1800d1074  mov     rdi, rax
0x1800d1077  test    rax, rax
0x1800d107a  jz      short loc_1800D1092
0x1800d107c  mov     r9, rbx; SourceSize
0x1800d107f  lea     rdx, [rbx+1]; DestinationSize
0x1800d1083  mov     r8, rbp; Source
0x1800d1086  mov     rcx, rax; Destination
0x1800d1089  call    memcpy_s_0
0x1800d108e  mov     byte ptr [rbx+rdi], 0
0x1800d1092  mov     [rsi], rdi
0x1800d1095  mov     rax, rsi
0x1800d1098  add     rsp, 20h
0x1800d109c  pop     r14
0x1800d109e  pop     rdi
0x1800d109f  pop     rsi
0x1800d10a0  pop     rbp
0x1800d10a1  pop     rbx
0x1800d10a2  retn
```
