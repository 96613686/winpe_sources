# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180003204`
- end: `0x180003318`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003140`
- `0x1800031bc`

## callees

- `0x180003204`
- `0x180003320`
- `0x18003645e`
- `0x1800364ac`
- `0x18003f704`
- `0x180047a4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003305`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000326f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000326f`

## string_xrefs

- `0x1800032e1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _WORD *v15; // [rsp+58h] [rbp+10h] BYREF

  v4 = a3;
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
    v9 = (v8 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v9;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v9 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v15 = v10;
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v9;
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
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
    a1,
    &v15);
  return a1;
}

```

## disassembly

```asm
0x180003204  mov     [rsp+arg_0], rbx
0x180003209  mov     [rsp+arg_10], rbp
0x18000320e  push    rsi
0x18000320f  push    rdi
0x180003210  push    r12
0x180003212  push    r14
0x180003214  push    r15
0x180003216  sub     rsp, 20h
0x18000321a  xor     r12d, r12d
0x18000321d  mov     rdi, r8
0x180003220  mov     rbp, rdx
0x180003223  mov     r15, rcx
0x180003226  test    rdx, rdx
0x180003229  jz      loc_1800032D6
0x18000322f  mov     ecx, 7FFFFFFFh
0x180003234  mov     rax, r8
0x180003237  cmp     r8, rcx
0x18000323a  mov     rbx, rdx
0x18000323d  cmovnb  rax, rcx
0x180003241  test    rax, rax
0x180003244  jz      short loc_180003256
0x180003246  cmp     [rbx], r12w
0x18000324a  jz      short loc_180003256
0x18000324c  add     rbx, 2
0x180003250  sub     rax, 1
0x180003254  jnz     short loc_180003246
0x180003256  sub     rbx, rbp
0x180003259  sar     rbx, 1
0x18000325c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003260  cmovz   rdi, rbx
0x180003264  lea     r14, ds:2[rdi*2]
0x18000326c  mov     rcx, r14; cb
0x18000326f  call    cs:__imp_CoTaskMemAlloc
0x180003275  mov     [rsp+48h+arg_8], rax
0x18000327a  mov     rsi, rax
0x18000327d  test    rax, rax
0x180003280  jz      short loc_1800032A9
0x180003282  test    rbp, rbp
0x180003285  jz      short loc_1800032D0
0x180003287  add     rbx, rbx
0x18000328a  jz      short loc_18000329F
0x18000328c  mov     rcx, rax; void *
0x18000328f  cmp     r14, rbx
0x180003292  jb      short loc_1800032FB
0x180003294  mov     r8, rbx; Size
0x180003297  mov     rdx, rbp; Src
0x18000329a  call    memcpy_0
0x18000329f  mov     [rbx+rsi], r12w
0x1800032a4  mov     [rsi+rdi*2], r12w
0x1800032a9  lea     rdx, [rsp+48h+arg_8]
0x1800032ae  mov     rcx, r15
0x1800032b1  call    ??$?0AEAPEAG$$V@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@AEAPEAG@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(ushort * &)
0x1800032b6  mov     rbx, [rsp+48h+arg_0]
0x1800032bb  mov     rax, r15
0x1800032be  mov     rbp, [rsp+48h+arg_10]
0x1800032c3  add     rsp, 20h
0x1800032c7  pop     r15
0x1800032c9  pop     r14
0x1800032cb  pop     r12
0x1800032cd  pop     rdi
0x1800032ce  pop     rsi
0x1800032cf  retn
0x1800032d0  mov     [rax], r12w
0x1800032d4  jmp     short loc_1800032A4
0x1800032d6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800032da  jnz     short loc_1800032F3
0x1800032dc  mov     rcx, [rsp+48h]; this
0x1800032e1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800032e8  mov     edx, 0F89h; void *
0x1800032ed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800032f3  mov     rbx, rdi
0x1800032f6  jmp     loc_180003264
0x1800032fb  mov     r8, r14; Size
0x1800032fe  xor     edx, edx; Val
0x180003300  call    memset_0
0x180003305  call    cs:__imp__o__errno
0x18000330b  mov     dword ptr [rax], 22h ; '"'
0x180003311  call    _invalid_parameter_noinfo
0x180003316  jmp     short loc_18000329F
```
