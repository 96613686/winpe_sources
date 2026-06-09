# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800309fc`
- end: `0x180030a8c`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034180`

## callees

- `0x180010440`
- `0x1800309fc`
- `0x1800350ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030a54`

## string_xrefs

- `0x180030a1c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x1800309fc  push    rbx
0x1800309fe  push    rbp
0x1800309ff  push    rsi
0x180030a00  push    rdi
0x180030a01  push    r14
0x180030a03  push    r15
0x180030a05  sub     rsp, 28h
0x180030a09  xor     r15d, r15d
0x180030a0c  mov     rbx, rdx
0x180030a0f  mov     rsi, rcx
0x180030a12  test    rdx, rdx
0x180030a15  jnz     short loc_180030A2E
0x180030a17  mov     rcx, [rsp+58h]; this
0x180030a1c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030a23  mov     edx, 0F89h; void *
0x180030a28  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180030a2e  mov     ecx, 7FFFFFFFh
0x180030a33  mov     rax, rbx
0x180030a36  cmp     [rax], r15w
0x180030a3a  jz      short loc_180030A46
0x180030a3c  add     rax, 2
0x180030a40  sub     rcx, 1
0x180030a44  jnz     short loc_180030A36
0x180030a46  sub     rax, rbx
0x180030a49  sar     rax, 1
0x180030a4c  lea     r14, [rax+rax]
0x180030a50  lea     rcx, [r14+2]; cb
0x180030a54  call    cs:__imp_CoTaskMemAlloc
0x180030a5a  mov     rdi, rax
0x180030a5d  test    rax, rax
0x180030a60  jz      short loc_180030A79
0x180030a62  mov     r9, r14; SourceSize
0x180030a65  lea     rdx, [r14+2]; DestinationSize
0x180030a69  mov     r8, rbx; Source
0x180030a6c  mov     rcx, rax; Destination
0x180030a6f  call    memcpy_s
0x180030a74  mov     [r14+rdi], r15w
0x180030a79  mov     [rsi], rdi
0x180030a7c  mov     rax, rsi
0x180030a7f  add     rsp, 28h
0x180030a83  pop     r15
0x180030a85  pop     r14
0x180030a87  pop     rdi
0x180030a88  pop     rsi
0x180030a89  pop     rbp
0x180030a8a  pop     rbx
0x180030a8b  retn
```
