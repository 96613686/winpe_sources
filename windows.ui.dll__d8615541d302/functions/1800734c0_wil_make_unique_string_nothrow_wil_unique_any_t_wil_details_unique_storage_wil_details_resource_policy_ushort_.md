# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800734c0`
- end: `0x18007358f`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e8f4`

## callees

- `0x18006c524`
- `0x1800734c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180073564`
- `msvcrt!memcpy_s` at `0x180073564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073542`

## string_xrefs

- `0x1800734eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800734c0  push    rbx
0x1800734c2  push    rbp
0x1800734c3  push    rsi
0x1800734c4  push    rdi
0x1800734c5  push    r12
0x1800734c7  push    r14
0x1800734c9  push    r15
0x1800734cb  sub     rsp, 20h
0x1800734cf  xor     r12d, r12d
0x1800734d2  mov     rdi, r8
0x1800734d5  mov     rbp, rdx
0x1800734d8  mov     r14, rcx
0x1800734db  test    rdx, rdx
0x1800734de  jnz     short loc_180073502
0x1800734e0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800734e4  jnz     short loc_1800734FD
0x1800734e6  mov     rcx, [rsp+58h]; this
0x1800734eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800734f2  mov     edx, 0F89h; void *
0x1800734f7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800734fd  mov     rbx, rdi
0x180073500  jmp     short loc_180073537
0x180073502  mov     ecx, 7FFFFFFFh
0x180073507  mov     rax, rdi
0x18007350a  cmp     rdi, rcx
0x18007350d  mov     rbx, rbp
0x180073510  cmovnb  rax, rcx
0x180073514  test    rax, rax
0x180073517  jz      short loc_180073529
0x180073519  cmp     [rbx], r12w
0x18007351d  jz      short loc_180073529
0x18007351f  add     rbx, 2
0x180073523  sub     rax, 1
0x180073527  jnz     short loc_180073519
0x180073529  sub     rbx, rbp
0x18007352c  sar     rbx, 1
0x18007352f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180073533  cmovz   rdi, rbx
0x180073537  lea     r15, ds:2[rdi*2]
0x18007353f  mov     rcx, r15; cb
0x180073542  call    cs:__imp_CoTaskMemAlloc
0x180073548  mov     rsi, rax
0x18007354b  test    rax, rax
0x18007354e  jz      short loc_18007357A
0x180073550  test    rbp, rbp
0x180073553  jz      short loc_180073571
0x180073555  add     rbx, rbx
0x180073558  mov     r8, rbp; Source
0x18007355b  mov     r9, rbx; SourceSize
0x18007355e  mov     rdx, r15; DestinationSize
0x180073561  mov     rcx, rax; Destination
0x180073564  call    cs:__imp_memcpy_s
0x18007356a  mov     [rbx+rsi], r12w
0x18007356f  jmp     short loc_180073575
0x180073571  mov     [rax], r12w
0x180073575  mov     [rsi+rdi*2], r12w
0x18007357a  mov     [r14], rsi
0x18007357d  mov     rax, r14
0x180073580  add     rsp, 20h
0x180073584  pop     r15
0x180073586  pop     r14
0x180073588  pop     r12
0x18007358a  pop     rdi
0x18007358b  pop     rsi
0x18007358c  pop     rbp
0x18007358d  pop     rbx
0x18007358e  retn
```
