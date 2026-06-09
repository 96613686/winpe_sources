# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180013140`
- end: `0x180013246`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `262`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d228`
- `0x18001d578`
- `0x180044914`

## callees

- `0x180013140`
- `0x18002bbe2`
- `0x18002bc68`
- `0x18002e495`
- `0x18002f91c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013205`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800131c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800131c8`

## string_xrefs

- `0x18001315f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  char *v8; // rdi
  __int64 v9; // r15
  SIZE_T v10; // rbp
  _WORD *v11; // rax
  _WORD *v12; // rsi
  size_t v13; // rdi
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v6 = (v8 - a2) >> 1;
    if ( a3 == -1 )
      a3 = v6;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        a4);
    v6 = a3;
  }
  v9 = a3;
  v10 = 2 * a3 + 2;
  v11 = CoTaskMemAlloc(v10);
  v12 = v11;
  if ( v11 )
  {
    if ( !a2 )
    {
      *v11 = 0;
      goto LABEL_20;
    }
    v13 = 2 * v6;
    if ( v13 )
    {
      if ( v10 >= v13 )
      {
        memcpy_0(v11, a2, v13);
        v12[v13 / 2] = 0;
LABEL_20:
        v12[v9] = 0;
        goto LABEL_21;
      }
      memset_0(v11, 0, v10);
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
    }
    v12[v13 / 2] = 0;
    goto LABEL_20;
  }
LABEL_21:
  result = a1;
  *a1 = v12;
  return result;
}

```

## disassembly

```asm
0x180013140  push    rbx
0x180013142  push    rdi
0x180013143  push    r14
0x180013145  sub     rsp, 20h
0x180013149  mov     rbx, rdx
0x18001314c  mov     r14, rcx
0x18001314f  test    rdx, rdx
0x180013152  jnz     short loc_180013176
0x180013154  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180013158  jnz     short loc_180013171
0x18001315a  mov     rcx, [rsp+38h]; this
0x18001315f  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013166  mov     edx, 0F89h; void *
0x18001316b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013171  mov     rdi, r8
0x180013174  jmp     short loc_1800131AE
0x180013176  mov     ecx, 7FFFFFFFh
0x18001317b  mov     rax, r8
0x18001317e  cmp     r8, rcx
0x180013181  mov     rdi, rbx
0x180013184  cmovnb  rax, rcx
0x180013188  test    rax, rax
0x18001318b  jz      short loc_1800131A0
0x18001318d  nop     dword ptr [rax]
0x180013190  cmp     word ptr [rdi], 0
0x180013194  jz      short loc_1800131A0
0x180013196  add     rdi, 2
0x18001319a  sub     rax, 1
0x18001319e  jnz     short loc_180013190
0x1800131a0  sub     rdi, rbx
0x1800131a3  sar     rdi, 1
0x1800131a6  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800131aa  cmovz   r8, rdi
0x1800131ae  mov     [rsp+38h+arg_0], rbp
0x1800131b3  mov     [rsp+38h+arg_8], rsi
0x1800131b8  mov     [rsp+38h+arg_10], r15
0x1800131bd  lea     r15, [r8+r8]
0x1800131c1  lea     rbp, [r15+2]
0x1800131c5  mov     rcx, rbp; cb
0x1800131c8  call    cs:__imp_CoTaskMemAlloc
0x1800131ce  mov     rsi, rax
0x1800131d1  test    rax, rax
0x1800131d4  jz      short loc_180013228
0x1800131d6  test    rbx, rbx
0x1800131d9  jz      short loc_18001321E
0x1800131db  add     rdi, rdi
0x1800131de  jz      short loc_180013216
0x1800131e0  mov     rcx, rax; void *
0x1800131e3  cmp     rbp, rdi
0x1800131e6  jb      short loc_1800131FB
0x1800131e8  mov     r8, rdi; Size
0x1800131eb  mov     rdx, rbx; Src
0x1800131ee  call    memcpy_0
0x1800131f3  xor     eax, eax
0x1800131f5  mov     [rdi+rsi], ax
0x1800131f9  jmp     short loc_180013223
0x1800131fb  mov     r8, rbp; Size
0x1800131fe  xor     edx, edx; Val
0x180013200  call    memset_0
0x180013205  call    cs:__imp__o__errno
0x18001320b  mov     dword ptr [rax], 22h ; '"'
0x180013211  call    _invalid_parameter_noinfo
0x180013216  xor     eax, eax
0x180013218  mov     [rdi+rsi], ax
0x18001321c  jmp     short loc_180013223
0x18001321e  xor     eax, eax
0x180013220  mov     [rsi], ax
0x180013223  mov     [r15+rsi], ax
0x180013228  mov     r15, [rsp+38h+arg_10]
0x18001322d  mov     rax, r14
0x180013230  mov     rbp, [rsp+38h+arg_0]
0x180013235  mov     [r14], rsi
0x180013238  mov     rsi, [rsp+38h+arg_8]
0x18001323d  add     rsp, 20h
0x180013241  pop     r14
0x180013243  pop     rdi
0x180013244  pop     rbx
0x180013245  retn
```
