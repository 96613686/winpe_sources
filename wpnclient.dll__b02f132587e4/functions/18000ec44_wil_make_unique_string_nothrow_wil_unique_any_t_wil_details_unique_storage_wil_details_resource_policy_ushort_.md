# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000ec44`
- end: `0x18000ed12`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eab0`

## callees

- `0x18000ec44`
- `0x18001f634`
- `0x18002c198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ecc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ecc6`

## string_xrefs

- `0x18000ec6f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  rsize_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = v7;
      memcpy_s(v10, 2 * v4 + 2, a2, v12 * 2);
      v11[v12] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18000ec44  push    rbx
0x18000ec46  push    rbp
0x18000ec47  push    rsi
0x18000ec48  push    rdi
0x18000ec49  push    r12
0x18000ec4b  push    r14
0x18000ec4d  push    r15
0x18000ec4f  sub     rsp, 20h
0x18000ec53  xor     r12d, r12d
0x18000ec56  mov     rdi, r8
0x18000ec59  mov     rbp, rdx
0x18000ec5c  mov     r14, rcx
0x18000ec5f  test    rdx, rdx
0x18000ec62  jnz     short loc_18000EC86
0x18000ec64  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ec68  jnz     short loc_18000EC81
0x18000ec6a  mov     rcx, [rsp+58h]; this
0x18000ec6f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ec76  mov     edx, 0F89h; void *
0x18000ec7b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ec81  mov     rbx, rdi
0x18000ec84  jmp     short loc_18000ECBB
0x18000ec86  mov     ecx, 7FFFFFFFh
0x18000ec8b  mov     rax, rdi
0x18000ec8e  cmp     rdi, rcx
0x18000ec91  mov     rbx, rbp
0x18000ec94  cmovnb  rax, rcx
0x18000ec98  test    rax, rax
0x18000ec9b  jz      short loc_18000ECAD
0x18000ec9d  cmp     [rbx], r12w
0x18000eca1  jz      short loc_18000ECAD
0x18000eca3  add     rbx, 2
0x18000eca7  sub     rax, 1
0x18000ecab  jnz     short loc_18000EC9D
0x18000ecad  sub     rbx, rbp
0x18000ecb0  sar     rbx, 1
0x18000ecb3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ecb7  cmovz   rdi, rbx
0x18000ecbb  lea     r15, ds:2[rdi*2]
0x18000ecc3  mov     rcx, r15; cb
0x18000ecc6  call    cs:__imp_CoTaskMemAlloc
0x18000eccc  mov     rsi, rax
0x18000eccf  test    rax, rax
0x18000ecd2  jz      short loc_18000ECFD
0x18000ecd4  test    rbp, rbp
0x18000ecd7  jz      short loc_18000ECF4
0x18000ecd9  add     rbx, rbx
0x18000ecdc  mov     r8, rbp; Source
0x18000ecdf  mov     r9, rbx; SourceSize
0x18000ece2  mov     rdx, r15; DestinationSize
0x18000ece5  mov     rcx, rax; Destination
0x18000ece8  call    memcpy_s
0x18000eced  mov     [rbx+rsi], r12w
0x18000ecf2  jmp     short loc_18000ECF8
0x18000ecf4  mov     [rax], r12w
0x18000ecf8  mov     [rsi+rdi*2], r12w
0x18000ecfd  mov     [r14], rsi
0x18000ed00  mov     rax, r14
0x18000ed03  add     rsp, 20h
0x18000ed07  pop     r15
0x18000ed09  pop     r14
0x18000ed0b  pop     r12
0x18000ed0d  pop     rdi
0x18000ed0e  pop     rsi
0x18000ed0f  pop     rbp
0x18000ed10  pop     rbx
0x18000ed11  retn
```
