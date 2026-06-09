# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,char * &)

- ea: `0x18004b178`
- end: `0x18004b2cd`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_WAEAPEAD@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b104`

## callees

- `0x180037df8`
- `0x18004b178`
- `0x18004b530`
- `0x18004b5b0`
- `0x18004b894`
- `0x1800e34bc`
- `0x1800e3810`
- `0x18015d948`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b2a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b2a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b1bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b1bf`

## string_xrefs

- `0x18004b27f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004b2b1`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        va_list *a3)
{
  int v6; // eax
  const char *v7; // r9
  __int64 v8; // rdi
  _WORD *v9; // rax
  wchar_t **v10; // r8
  unsigned __int64 *v11; // r9
  STRSAFE_LPWSTR v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  char v20; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  STRSAFE_LPWSTR pszDest; // [rsp+88h] [rbp+20h] BYREF

  v6 = vscwprintf(a2, *a3);
  v8 = v6;
  pszDest = 0;
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\resource.h",
      v7);
  v9 = CoTaskMemAlloc(2LL * v6 + 2);
  if ( v9 )
  {
    *v9 = 0;
    v9[v8] = 0;
  }
  pv = v9;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v12 = pszDest;
  if ( !pszDest )
  {
    v14 = -2147024882;
    v16 = 1997;
    v17 = 2147942414LL;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v17,
      v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszDest);
    return v14;
  }
  v13 = StringCchVPrintfExW(pszDest, v8 + 1, v10, v11, v18, a2, *a3);
  v14 = v13;
  if ( v13 < 0 )
  {
    v17 = (unsigned int)v13;
    v16 = 2001;
    goto LABEL_12;
  }
  pszDest = 0;
  if ( a1 == &v20 )
  {
    if ( v12 )
      CoTaskMemFree(v12);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      a1,
      v12);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszDest);
  return 0;
}

```

## disassembly

```asm
0x18004b178  mov     [rsp+arg_0], rbx
0x18004b17d  mov     [rsp+arg_8], rbp
0x18004b182  push    rsi
0x18004b183  push    rdi
0x18004b184  push    r14
0x18004b186  sub     rsp, 50h
0x18004b18a  mov     rbp, rdx
0x18004b18d  mov     rsi, rcx
0x18004b190  mov     rdx, [r8]; ArgList
0x18004b193  mov     rcx, rbp; Format
0x18004b196  mov     r14, r8
0x18004b199  call    _vscwprintf
0x18004b19e  movsxd  rdi, eax
0x18004b1a1  mov     [rsp+68h+pszDest], 0
0x18004b1ad  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004b1b1  jz      loc_18004B2AC
0x18004b1b7  lea     rcx, ds:2[rdi*2]; cb
0x18004b1bf  call    cs:__imp_CoTaskMemAlloc
0x18004b1c5  test    rax, rax
0x18004b1c8  jz      short loc_18004B1D3
0x18004b1ca  xor     ecx, ecx
0x18004b1cc  mov     [rax], cx
0x18004b1cf  mov     [rax+rdi*2], cx
0x18004b1d3  lea     rdx, [rsp+68h+pv]
0x18004b1d8  mov     [rsp+68h+pv], rax
0x18004b1dd  lea     rcx, [rsp+68h+pszDest]
0x18004b1e5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18004b1ea  mov     rcx, [rsp+68h+pv]; pv
0x18004b1ef  test    rcx, rcx
0x18004b1f2  jz      short loc_18004B1FA
0x18004b1f4  call    cs:__imp_CoTaskMemFree
0x18004b1fa  mov     rbx, [rsp+68h+pszDest]
0x18004b202  test    rbx, rbx
0x18004b205  jz      short loc_18004B26D
0x18004b207  mov     rax, [r14]
0x18004b20a  lea     rdx, [rdi+1]; unsigned __int64
0x18004b20e  mov     [rsp+68h+var_38], rax; char *
0x18004b213  mov     rcx, rbx; pszDest
0x18004b216  mov     [rsp+68h+var_40], rbp; wchar_t *
0x18004b21b  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x18004b220  mov     edi, eax
0x18004b222  test    eax, eax
0x18004b224  js      loc_18004B2C3
0x18004b22a  lea     rax, [rsp+68h+var_20]
0x18004b22f  mov     [rsp+68h+pszDest], 0
0x18004b23b  cmp     rsi, rax
0x18004b23e  jz      short loc_18004B29C
0x18004b240  mov     rdx, rbx
0x18004b243  mov     rcx, rsi
0x18004b246  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18004b24b  lea     rcx, [rsp+68h+pszDest]
0x18004b253  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004b258  xor     eax, eax
0x18004b25a  mov     rbx, [rsp+68h+arg_0]
0x18004b25f  mov     rbp, [rsp+68h+arg_8]
0x18004b264  add     rsp, 50h
0x18004b268  pop     r14
0x18004b26a  pop     rdi
0x18004b26b  pop     rsi
0x18004b26c  retn
0x18004b26d  mov     edi, 8007000Eh
0x18004b272  mov     edx, 7CDh; void *
0x18004b277  mov     r9d, edi; char *
0x18004b27a  mov     rcx, [rsp+68h]; this
0x18004b27f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004b286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b28b  lea     rcx, [rsp+68h+pszDest]
0x18004b293  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004b298  mov     eax, edi
0x18004b29a  jmp     short loc_18004B25A
0x18004b29c  test    rbx, rbx
0x18004b29f  jz      short loc_18004B24B
0x18004b2a1  mov     rcx, rbx; pv
0x18004b2a4  call    cs:__imp_CoTaskMemFree
0x18004b2aa  jmp     short loc_18004B24B
0x18004b2ac  mov     rcx, [rsp+68h]; this
0x18004b2b1  lea     r8, aOnecoreInterna_31; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004b2b8  mov     edx, 0F89h; void *
0x18004b2bd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004b2c3  mov     r9d, eax
0x18004b2c6  mov     edx, 7D1h
0x18004b2cb  jmp     short loc_18004B27A
```
