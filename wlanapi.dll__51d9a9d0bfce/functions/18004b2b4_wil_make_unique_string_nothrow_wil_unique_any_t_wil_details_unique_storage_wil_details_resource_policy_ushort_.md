# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18004b2b4`
- end: `0x18004b382`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d4d8`

## callees

- `0x180006ef0`
- `0x180026898`
- `0x18004b2b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b336`

## string_xrefs

- `0x18004b2df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18004b2b4  push    rbx
0x18004b2b6  push    rbp
0x18004b2b7  push    rsi
0x18004b2b8  push    rdi
0x18004b2b9  push    r12
0x18004b2bb  push    r14
0x18004b2bd  push    r15
0x18004b2bf  sub     rsp, 20h
0x18004b2c3  xor     r12d, r12d
0x18004b2c6  mov     rdi, r8
0x18004b2c9  mov     rbp, rdx
0x18004b2cc  mov     r14, rcx
0x18004b2cf  test    rdx, rdx
0x18004b2d2  jnz     short loc_18004B2F6
0x18004b2d4  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18004b2d8  jnz     short loc_18004B2F1
0x18004b2da  mov     rcx, [rsp+58h]; this
0x18004b2df  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b2e6  mov     edx, 0F89h; void *
0x18004b2eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004b2f1  mov     rbx, rdi
0x18004b2f4  jmp     short loc_18004B32B
0x18004b2f6  mov     ecx, 7FFFFFFFh
0x18004b2fb  mov     rax, rdi
0x18004b2fe  cmp     rdi, rcx
0x18004b301  mov     rbx, rbp
0x18004b304  cmovnb  rax, rcx
0x18004b308  test    rax, rax
0x18004b30b  jz      short loc_18004B31D
0x18004b30d  cmp     [rbx], r12w
0x18004b311  jz      short loc_18004B31D
0x18004b313  add     rbx, 2
0x18004b317  sub     rax, 1
0x18004b31b  jnz     short loc_18004B30D
0x18004b31d  sub     rbx, rbp
0x18004b320  sar     rbx, 1
0x18004b323  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004b327  cmovz   rdi, rbx
0x18004b32b  lea     r15, ds:2[rdi*2]
0x18004b333  mov     rcx, r15; cb
0x18004b336  call    cs:__imp_CoTaskMemAlloc
0x18004b33c  mov     rsi, rax
0x18004b33f  test    rax, rax
0x18004b342  jz      short loc_18004B36D
0x18004b344  test    rbp, rbp
0x18004b347  jz      short loc_18004B364
0x18004b349  add     rbx, rbx
0x18004b34c  mov     r8, rbp; Source
0x18004b34f  mov     r9, rbx; SourceSize
0x18004b352  mov     rdx, r15; DestinationSize
0x18004b355  mov     rcx, rax; Destination
0x18004b358  call    memcpy_s
0x18004b35d  mov     [rbx+rsi], r12w
0x18004b362  jmp     short loc_18004B368
0x18004b364  mov     [rax], r12w
0x18004b368  mov     [rsi+rdi*2], r12w
0x18004b36d  mov     [r14], rsi
0x18004b370  mov     rax, r14
0x18004b373  add     rsp, 20h
0x18004b377  pop     r15
0x18004b379  pop     r14
0x18004b37b  pop     r12
0x18004b37d  pop     rdi
0x18004b37e  pop     rsi
0x18004b37f  pop     rbp
0x18004b380  pop     rbx
0x18004b381  retn
```
