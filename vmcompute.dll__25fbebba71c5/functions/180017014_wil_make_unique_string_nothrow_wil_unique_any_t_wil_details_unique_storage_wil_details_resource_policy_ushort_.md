# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180017014`
- end: `0x1800170db`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `199`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026640`
- `0x180026e20`
- `0x180039050`

## callees

- `0x180003b92`
- `0x180003c78`
- `0x180004829`
- `0x180008c34`
- `0x180017014`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017094`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001705c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001705c`

## string_xrefs

- `0x1800170c9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
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
  v9 = v8 + 2;
  v10 = (char *)CoTaskMemAlloc(v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180017014  push    rbx
0x180017016  push    rbp
0x180017017  push    rsi
0x180017018  push    rdi
0x180017019  push    r14
0x18001701b  push    r15
0x18001701d  sub     rsp, 28h
0x180017021  xor     r15d, r15d
0x180017024  mov     rsi, rdx
0x180017027  mov     r14, rcx
0x18001702a  test    rdx, rdx
0x18001702d  jz      loc_1800170C4
0x180017033  mov     ecx, 7FFFFFFFh
0x180017038  mov     rax, rdx
0x18001703b  cmp     [rax], r15w
0x18001703f  jz      short loc_18001704B
0x180017041  add     rax, 2
0x180017045  sub     rcx, 1
0x180017049  jnz     short loc_18001703B
0x18001704b  sub     rax, rsi
0x18001704e  sar     rax, 1
0x180017051  lea     rbx, [rax+rax]
0x180017055  lea     rbp, [rbx+2]
0x180017059  mov     rcx, rbp; cb
0x18001705c  call    cs:__imp_CoTaskMemAlloc
0x180017063  nop     dword ptr [rax+rax+00h]
0x180017068  mov     rdi, rax
0x18001706b  test    rax, rax
0x18001706e  jz      short loc_1800170B0
0x180017070  test    rbx, rbx
0x180017073  jz      short loc_1800170AB
0x180017075  mov     rcx, rax; void *
0x180017078  cmp     rbp, rbx
0x18001707b  jb      short loc_18001708A
0x18001707d  mov     r8, rbx; Size
0x180017080  mov     rdx, rsi; Src
0x180017083  call    memcpy_0
0x180017088  jmp     short loc_1800170AB
0x18001708a  mov     r8, rbp; Size
0x18001708d  xor     edx, edx; Val
0x18001708f  call    memset_0
0x180017094  call    cs:__imp__o__errno
0x18001709b  nop     dword ptr [rax+rax+00h]
0x1800170a0  mov     dword ptr [rax], 22h ; '"'
0x1800170a6  call    _invalid_parameter_noinfo
0x1800170ab  mov     [rbx+rdi], r15w
0x1800170b0  mov     [r14], rdi
0x1800170b3  mov     rax, r14
0x1800170b6  add     rsp, 28h
0x1800170ba  pop     r15
0x1800170bc  pop     r14
0x1800170be  pop     rdi
0x1800170bf  pop     rsi
0x1800170c0  pop     rbp
0x1800170c1  pop     rbx
0x1800170c2  retn
0x1800170c4  mov     rcx, [rsp+58h]; this
0x1800170c9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800170d0  mov     edx, 0F89h; void *
0x1800170d5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
