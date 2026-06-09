# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x14005090c`
- end: `0x1400509da`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005e4f4`

## callees

- `0x140046a30`
- `0x14004b970`
- `0x14005090c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005098e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005098e`

## string_xrefs

- `0x140050937`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x14005090c  push    rbx
0x14005090e  push    rbp
0x14005090f  push    rsi
0x140050910  push    rdi
0x140050911  push    r12
0x140050913  push    r14
0x140050915  push    r15
0x140050917  sub     rsp, 20h
0x14005091b  xor     r12d, r12d
0x14005091e  mov     rdi, r8
0x140050921  mov     rbp, rdx
0x140050924  mov     r14, rcx
0x140050927  test    rdx, rdx
0x14005092a  jnz     short loc_14005094E
0x14005092c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140050930  jnz     short loc_140050949
0x140050932  mov     rcx, [rsp+58h]; this
0x140050937  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005093e  mov     edx, 0F89h; void *
0x140050943  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140050949  mov     rbx, rdi
0x14005094c  jmp     short loc_140050983
0x14005094e  mov     ecx, 7FFFFFFFh
0x140050953  mov     rax, rdi
0x140050956  cmp     rdi, rcx
0x140050959  mov     rbx, rbp
0x14005095c  cmovnb  rax, rcx
0x140050960  test    rax, rax
0x140050963  jz      short loc_140050975
0x140050965  cmp     [rbx], r12w
0x140050969  jz      short loc_140050975
0x14005096b  add     rbx, 2
0x14005096f  sub     rax, 1
0x140050973  jnz     short loc_140050965
0x140050975  sub     rbx, rbp
0x140050978  sar     rbx, 1
0x14005097b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14005097f  cmovz   rdi, rbx
0x140050983  lea     r15, ds:2[rdi*2]
0x14005098b  mov     rcx, r15; cb
0x14005098e  call    cs:__imp_CoTaskMemAlloc
0x140050994  mov     rsi, rax
0x140050997  test    rax, rax
0x14005099a  jz      short loc_1400509C5
0x14005099c  test    rbp, rbp
0x14005099f  jz      short loc_1400509BC
0x1400509a1  add     rbx, rbx
0x1400509a4  mov     r8, rbp; Source
0x1400509a7  mov     r9, rbx; SourceSize
0x1400509aa  mov     rdx, r15; DestinationSize
0x1400509ad  mov     rcx, rax; Destination
0x1400509b0  call    memcpy_s
0x1400509b5  mov     [rbx+rsi], r12w
0x1400509ba  jmp     short loc_1400509C0
0x1400509bc  mov     [rax], r12w
0x1400509c0  mov     [rsi+rdi*2], r12w
0x1400509c5  mov     [r14], rsi
0x1400509c8  mov     rax, r14
0x1400509cb  add     rsp, 20h
0x1400509cf  pop     r15
0x1400509d1  pop     r14
0x1400509d3  pop     r12
0x1400509d5  pop     rdi
0x1400509d6  pop     rsi
0x1400509d7  pop     rbp
0x1400509d8  pop     rbx
0x1400509d9  retn
```
