# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180008454`
- end: `0x180008543`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008a48`
- `0x180008ea0`
- `0x1800090ac`
- `0x1800090f0`
- `0x1800093ec`

## callees

- `0x180002a4a`
- `0x180002ab4`
- `0x180008454`
- `0x180008a24`
- `0x18000bb04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000850d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000850d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084d6`

## string_xrefs

- `0x18000847f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
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
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
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
0x180008454  push    rbx
0x180008456  push    rbp
0x180008457  push    rsi
0x180008458  push    rdi
0x180008459  push    r12
0x18000845b  push    r14
0x18000845d  push    r15
0x18000845f  sub     rsp, 20h
0x180008463  xor     r12d, r12d
0x180008466  mov     rbx, r8
0x180008469  mov     rbp, rdx
0x18000846c  mov     r15, rcx
0x18000846f  test    rdx, rdx
0x180008472  jnz     short loc_180008496
0x180008474  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008478  jnz     short loc_180008491
0x18000847a  mov     rcx, [rsp+58h]; this
0x18000847f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008486  mov     edx, 0F89h; void *
0x18000848b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008491  mov     rdi, rbx
0x180008494  jmp     short loc_1800084CB
0x180008496  mov     ecx, 7FFFFFFFh
0x18000849b  mov     rax, rbx
0x18000849e  cmp     rbx, rcx
0x1800084a1  mov     rdi, rbp
0x1800084a4  cmovnb  rax, rcx
0x1800084a8  test    rax, rax
0x1800084ab  jz      short loc_1800084BD
0x1800084ad  cmp     [rdi], r12w
0x1800084b1  jz      short loc_1800084BD
0x1800084b3  add     rdi, 2
0x1800084b7  sub     rax, 1
0x1800084bb  jnz     short loc_1800084AD
0x1800084bd  sub     rdi, rbp
0x1800084c0  sar     rdi, 1
0x1800084c3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800084c7  cmovz   rbx, rdi
0x1800084cb  lea     r14, ds:2[rbx*2]
0x1800084d3  mov     rcx, r14; cb
0x1800084d6  call    cs:__imp_CoTaskMemAlloc
0x1800084dc  mov     rsi, rax
0x1800084df  test    rax, rax
0x1800084e2  jz      short loc_18000852E
0x1800084e4  test    rbp, rbp
0x1800084e7  jz      short loc_180008525
0x1800084e9  add     rdi, rdi
0x1800084ec  jz      short loc_18000851E
0x1800084ee  mov     rcx, rax; void *
0x1800084f1  cmp     r14, rdi
0x1800084f4  jb      short loc_180008503
0x1800084f6  mov     r8, rdi; Size
0x1800084f9  mov     rdx, rbp; Src
0x1800084fc  call    memcpy_0
0x180008501  jmp     short loc_18000851E
0x180008503  mov     r8, r14; Size
0x180008506  xor     edx, edx; Val
0x180008508  call    memset_0
0x18000850d  call    cs:__imp__o__errno
0x180008513  mov     dword ptr [rax], 22h ; '"'
0x180008519  call    _invalid_parameter_noinfo
0x18000851e  mov     [rdi+rsi], r12w
0x180008523  jmp     short loc_180008529
0x180008525  mov     [rax], r12w
0x180008529  mov     [rsi+rbx*2], r12w
0x18000852e  mov     [r15], rsi
0x180008531  mov     rax, r15
0x180008534  add     rsp, 20h
0x180008538  pop     r15
0x18000853a  pop     r14
0x18000853c  pop     r12
0x18000853e  pop     rdi
0x18000853f  pop     rsi
0x180008540  pop     rbp
0x180008541  pop     rbx
0x180008542  retn
```
