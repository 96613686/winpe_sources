# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x18002ff28`
- end: `0x180030054`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fc94`
- `0x18003825c`
- `0x1800390b4`

## callees

- `0x180010890`
- `0x18002feb0`
- `0x18002ff28`
- `0x1800dd576`
- `0x1800dd62a`
- `0x1800e46b0`
- `0x1800e4a70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ff9e`

## string_xrefs

- `0x180030042`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDB5,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
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
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
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
  pv = v11;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    a1,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18002ff28  mov     [rsp+arg_0], rbx
0x18002ff2d  mov     [rsp+arg_10], rbp
0x18002ff32  push    rsi
0x18002ff33  push    rdi
0x18002ff34  push    r12
0x18002ff36  push    r14
0x18002ff38  push    r15
0x18002ff3a  sub     rsp, 20h
0x18002ff3e  xor     r12d, r12d
0x18002ff41  mov     rsi, r8
0x18002ff44  mov     rbp, rdx
0x18002ff47  mov     r15, rcx
0x18002ff4a  test    rdx, rdx
0x18002ff4d  jnz     short loc_18002FF59
0x18002ff4f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002ff53  jz      loc_18003003D
0x18002ff59  mov     rbx, rsi
0x18002ff5c  test    rbp, rbp
0x18002ff5f  jz      short loc_18002FF8B
0x18002ff61  mov     eax, 7FFFFFFFh
0x18002ff66  mov     rbx, rbp
0x18002ff69  cmp     rsi, rax
0x18002ff6c  cmovb   rax, rsi
0x18002ff70  test    rax, rax
0x18002ff73  jz      short loc_18002FF85
0x18002ff75  cmp     [rbx], r12w
0x18002ff79  jz      short loc_18002FF85
0x18002ff7b  add     rbx, 2
0x18002ff7f  sub     rax, 1
0x18002ff83  jnz     short loc_18002FF75
0x18002ff85  sub     rbx, rbp
0x18002ff88  sar     rbx, 1
0x18002ff8b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002ff8f  cmovz   rsi, rbx
0x18002ff93  lea     r14, ds:2[rsi*2]
0x18002ff9b  mov     rcx, r14; cb
0x18002ff9e  call    cs:__imp_CoTaskMemAlloc
0x18002ffa4  mov     rdi, rax
0x18002ffa7  test    rax, rax
0x18002ffaa  jz      short loc_18002FFF5
0x18002ffac  test    rbp, rbp
0x18002ffaf  jz      short loc_18002FFEC
0x18002ffb1  add     rbx, rbx
0x18002ffb4  jz      short loc_18002FFE5
0x18002ffb6  mov     rcx, rax; void *
0x18002ffb9  cmp     r14, rbx
0x18002ffbc  jb      short loc_18002FFCB
0x18002ffbe  mov     r8, rbx; Size
0x18002ffc1  mov     rdx, rbp; Src
0x18002ffc4  call    memmove
0x18002ffc9  jmp     short loc_18002FFE5
0x18002ffcb  mov     r8, r14; Size
0x18002ffce  xor     edx, edx; Val
0x18002ffd0  call    memset
0x18002ffd5  call    _o__errno_0
0x18002ffda  mov     dword ptr [rax], 22h ; '"'
0x18002ffe0  call    _invalid_parameter_noinfo
0x18002ffe5  mov     [rbx+rdi], r12w
0x18002ffea  jmp     short loc_18002FFF0
0x18002ffec  mov     [rax], r12w
0x18002fff0  mov     [rdi+rsi*2], r12w
0x18002fff5  lea     rdx, [rsp+48h+pv]
0x18002fffa  mov     [rsp+48h+pv], rdi
0x18002ffff  mov     rcx, r15
0x180030002  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180030007  mov     rcx, [rsp+48h+pv]; pv
0x18003000c  test    rcx, rcx
0x18003000f  jz      short loc_180030017
0x180030011  call    cs:__imp_CoTaskMemFree
0x180030017  mov     rax, [r15]
0x18003001a  mov     rbx, [rsp+48h+arg_0]
0x18003001f  neg     rax
0x180030022  mov     rbp, [rsp+48h+arg_10]
0x180030027  sbb     eax, eax
0x180030029  not     eax
0x18003002b  and     eax, 8007000Eh
0x180030030  add     rsp, 20h
0x180030034  pop     r15
0x180030036  pop     r14
0x180030038  pop     r12
0x18003003a  pop     rdi
0x18003003b  pop     rsi
0x18003003c  retn
0x18003003d  mov     rcx, [rsp+48h]; this
0x180030042  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180030049  mov     edx, 0DB5h; void *
0x18003004e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
