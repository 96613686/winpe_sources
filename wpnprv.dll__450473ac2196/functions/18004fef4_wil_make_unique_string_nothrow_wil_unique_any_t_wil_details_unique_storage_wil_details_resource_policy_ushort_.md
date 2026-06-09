# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18004fef4`
- end: `0x18004ff84`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004fea4`
- `0x1800556f0`
- `0x180056538`

## callees

- `0x18000d4a8`
- `0x18002ed5c`
- `0x18004fef4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ff4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ff4c`

## string_xrefs

- `0x18004ff14`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x18004fef4  push    rbx
0x18004fef6  push    rbp
0x18004fef7  push    rsi
0x18004fef8  push    rdi
0x18004fef9  push    r14
0x18004fefb  push    r15
0x18004fefd  sub     rsp, 28h
0x18004ff01  xor     r15d, r15d
0x18004ff04  mov     rbx, rdx
0x18004ff07  mov     rsi, rcx
0x18004ff0a  test    rdx, rdx
0x18004ff0d  jnz     short loc_18004FF26
0x18004ff0f  mov     rcx, [rsp+58h]; this
0x18004ff14  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004ff1b  mov     edx, 0F89h; void *
0x18004ff20  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004ff26  mov     ecx, 7FFFFFFFh
0x18004ff2b  mov     rax, rbx
0x18004ff2e  cmp     [rax], r15w
0x18004ff32  jz      short loc_18004FF3E
0x18004ff34  add     rax, 2
0x18004ff38  sub     rcx, 1
0x18004ff3c  jnz     short loc_18004FF2E
0x18004ff3e  sub     rax, rbx
0x18004ff41  sar     rax, 1
0x18004ff44  lea     r14, [rax+rax]
0x18004ff48  lea     rcx, [r14+2]; cb
0x18004ff4c  call    cs:__imp_CoTaskMemAlloc
0x18004ff52  mov     rdi, rax
0x18004ff55  test    rax, rax
0x18004ff58  jz      short loc_18004FF71
0x18004ff5a  mov     r9, r14; SourceSize
0x18004ff5d  lea     rdx, [r14+2]; DestinationSize
0x18004ff61  mov     r8, rbx; Source
0x18004ff64  mov     rcx, rax; Destination
0x18004ff67  call    memcpy_s
0x18004ff6c  mov     [r14+rdi], r15w
0x18004ff71  mov     [rsi], rdi
0x18004ff74  mov     rax, rsi
0x18004ff77  add     rsp, 28h
0x18004ff7b  pop     r15
0x18004ff7d  pop     r14
0x18004ff7f  pop     rdi
0x18004ff80  pop     rsi
0x18004ff81  pop     rbp
0x18004ff82  pop     rbx
0x18004ff83  retn
```
