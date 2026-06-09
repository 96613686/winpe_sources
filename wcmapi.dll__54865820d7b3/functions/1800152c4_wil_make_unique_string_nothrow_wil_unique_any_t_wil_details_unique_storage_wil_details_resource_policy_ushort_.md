# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800152c4`
- end: `0x18001535b`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e10`

## callees

- `0x18000aaf4`
- `0x180010c90`
- `0x1800152c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015305`

## string_xrefs

- `0x180015349`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = (char *)CoTaskMemAlloc(v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x1800152c4  push    rbx
0x1800152c6  push    rbp
0x1800152c7  push    rsi
0x1800152c8  push    rdi
0x1800152c9  push    r14
0x1800152cb  push    r15
0x1800152cd  sub     rsp, 28h
0x1800152d1  xor     r15d, r15d
0x1800152d4  mov     rbx, rdx
0x1800152d7  mov     rsi, rcx
0x1800152da  test    rdx, rdx
0x1800152dd  jz      short loc_180015344
0x1800152df  mov     ecx, 7FFFFFFFh
0x1800152e4  mov     rax, rdx
0x1800152e7  cmp     [rax], r15w
0x1800152eb  jz      short loc_1800152F7
0x1800152ed  add     rax, 2
0x1800152f1  sub     rcx, 1
0x1800152f5  jnz     short loc_1800152E7
0x1800152f7  sub     rax, rbx
0x1800152fa  sar     rax, 1
0x1800152fd  lea     r14, [rax+rax]
0x180015301  lea     rcx, [r14+2]; cb
0x180015305  call    cs:__imp_CoTaskMemAlloc
0x18001530c  nop     dword ptr [rax+rax+00h]
0x180015311  mov     rdi, rax
0x180015314  test    rax, rax
0x180015317  jz      short loc_180015330
0x180015319  mov     r9, r14; SourceSize
0x18001531c  lea     rdx, [r14+2]; DestinationSize
0x180015320  mov     r8, rbx; Source
0x180015323  mov     rcx, rax; Destination
0x180015326  call    memcpy_s
0x18001532b  mov     [r14+rdi], r15w
0x180015330  mov     [rsi], rdi
0x180015333  mov     rax, rsi
0x180015336  add     rsp, 28h
0x18001533a  pop     r15
0x18001533c  pop     r14
0x18001533e  pop     rdi
0x18001533f  pop     rsi
0x180015340  pop     rbp
0x180015341  pop     rbx
0x180015342  retn
0x180015344  mov     rcx, [rsp+58h]; this
0x180015349  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015350  mov     edx, 0F89h; void *
0x180015355  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
