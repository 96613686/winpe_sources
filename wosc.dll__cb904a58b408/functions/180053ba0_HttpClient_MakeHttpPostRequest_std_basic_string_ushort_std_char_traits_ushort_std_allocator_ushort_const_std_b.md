# HttpClient::MakeHttpPostRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,ushort const *,ulong,void * const &,ulong,uint,HttpRequestOptions)

- ea: `0x180053ba0`
- end: `0x180053e6a`
- name: `?MakeHttpPostRequest@HttpClient@@UEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@PEBGKAEBQEAXKIW4HttpRequestOptions@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWSTR lpszHeaders, DWORD dwHeadersLength, __int64, DWORD dwOptionalLength, int nReceiveTimeout, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053ac0`

## callees

- `0x180003110`
- `0x1800101e0`
- `0x1800101fc`
- `0x180010278`
- `0x180014b08`
- `0x180019e68`
- `0x180052fbc`
- `0x180053084`
- `0x1800533ac`
- `0x18005348c`
- `0x180053ba0`
- `0x180054470`

## import_xrefs

- `WINHTTP!WinHttpReceiveResponse` at `0x180053d92`
- `WINHTTP!WinHttpReceiveResponse` at `0x180053d92`
- `WINHTTP!WinHttpSendRequest` at `0x180053d6d`
- `WINHTTP!WinHttpSendRequest` at `0x180053d6d`
- `WINHTTP!WinHttpSetOption` at `0x180053ce8`
- `WINHTTP!WinHttpSetOption` at `0x180053d35`
- `WINHTTP!WinHttpSetOption` at `0x180053ce8`
- `WINHTTP!WinHttpSetOption` at `0x180053d35`
- `WINHTTP!WinHttpSetTimeouts` at `0x180053cc9`
- `WINHTTP!WinHttpSetTimeouts` at `0x180053cc9`
- `WINHTTP!WinHttpOpenRequest` at `0x180053c89`
- `WINHTTP!WinHttpOpenRequest` at `0x180053c89`
- `WINHTTP!WinHttpConnect` at `0x180053c2f`
- `WINHTTP!WinHttpConnect` at `0x180053c2f`
- `WINHTTP!WinHttpOpen` at `0x180053bf0`
- `WINHTTP!WinHttpOpen` at `0x180053bf0`

## string_xrefs

- `0x180053c06`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053c45`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053c9f`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053cf6`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053d7b`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053da0`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053dd6`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053e09`: `onecore\base\flighting\common\httpclient\httpclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HttpClient::MakeHttpPostRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPCWSTR lpszHeaders,
        DWORD dwHeadersLength,
        LPVOID *a7,
        DWORD dwOptionalLength,
        int nReceiveTimeout,
        int a10)
{
  const char *v13; // r9
  const WCHAR *v14; // rax
  HINTERNET v15; // r10
  const char *v16; // r9
  const WCHAR *v17; // rax
  HINTERNET v18; // r10
  void *v19; // rbx
  const char *v20; // r9
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // eax
  __int64 v27; // rcx
  int FullHeadersString; // eax
  unsigned int v29; // ebx
  int dwFlags; // [rsp+20h] [rbp-69h]
  unsigned int v32; // [rsp+40h] [rbp-49h] BYREF
  int v33; // [rsp+44h] [rbp-45h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-41h] BYREF
  void *v35; // [rsp+50h] [rbp-39h] BYREF
  HINTERNET v36; // [rsp+58h] [rbp-31h] BYREF
  HINTERNET v37; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v38[32]; // [rsp+68h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+2Fh]

  v37 = WinHttpOpen(L"Wosc", 4u, 0, 0, 0);
  if ( !v37 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v13);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v36 = WinHttpConnect(v15, v14, 0x1BBu, 0);
  if ( !v36 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v16);
  v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v19 = WinHttpOpenRequest(v18, L"POST", v17, 0, 0, 0, 0x800000u);
  v35 = v19;
  if ( !v19 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v20);
  WinHttpSetTimeouts(v19, 0, 60000, 30000, nReceiveTimeout);
  Buffer = a10;
  if ( !WinHttpSetOption(v19, 0x2Du, &Buffer, 8u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v21);
  HttpClient::AddRequestHeaders(retaddr, v19, a4);
  if ( (a10 & 2) != 0 )
  {
    v33 = 1;
    if ( !WinHttpSetOption(v19, 0x76u, &v33, 4u) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xCD, v22, v23);
  }
  if ( !WinHttpSendRequest(v19, lpszHeaders, dwHeadersLength, *a7, dwOptionalLength, dwOptionalLength, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v24);
  if ( !WinHttpReceiveResponse(v19, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v25);
  v32 = 0;
  v26 = HttpClient::ExtractHeaderAsDword(retaddr, v19, 0x13u, &v32);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      (const char *)(unsigned int)v26,
      dwFlags);
  std::wstring::wstring(v38);
  FullHeadersString = HttpClient::ExtractFullHeadersString(v27, v19, v38);
  if ( FullHeadersString < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      (const char *)(unsigned int)FullHeadersString,
      dwFlags);
  v29 = v32;
  std::wstring::_Tidy_deallocate(v38);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v36);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
  return v29;
}

```

## disassembly

```asm
0x180053ba0  mov     [rsp-8+arg_0], rbx
0x180053ba5  push    rbp
0x180053ba6  push    rsi
0x180053ba7  push    rdi
0x180053ba8  push    r14
0x180053baa  push    r15
0x180053bac  lea     rbp, [rsp-7]
0x180053bb1  sub     rsp, 90h
0x180053bb8  mov     rax, cs:__security_cookie
0x180053bbf  xor     rax, rsp
0x180053bc2  mov     [rbp+27h+var_28], rax
0x180053bc6  mov     rdi, r9
0x180053bc9  mov     rsi, r8
0x180053bcc  mov     rbx, rdx
0x180053bcf  mov     r14, [rbp+27h+lpszHeaders]
0x180053bd3  mov     r15, [rbp+27h+arg_30]
0x180053bd7  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x180053bdf  xor     r9d, r9d; pszProxyBypassW
0x180053be2  xor     r8d, r8d; pszProxyW
0x180053be5  lea     edx, [r9+4]; dwAccessType
0x180053be9  lea     rcx, pszAgentW; "Wosc"
0x180053bf0  call    cs:__imp_WinHttpOpen
0x180053bf6  mov     r10, rax
0x180053bf9  mov     [rbp+27h+var_50], rax
0x180053bfd  mov     rcx, [rbp+2Fh]; this
0x180053c01  test    rax, rax
0x180053c04  jnz     short loc_180053C18
0x180053c06  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053c0d  mov     edx, 0B2h; void *
0x180053c12  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053c18  mov     rcx, rbx
0x180053c1b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053c20  mov     r8d, 1BBh; nServerPort
0x180053c26  xor     r9d, r9d; dwReserved
0x180053c29  mov     rdx, rax; pswzServerName
0x180053c2c  mov     rcx, r10; hSession
0x180053c2f  call    cs:__imp_WinHttpConnect
0x180053c35  mov     r10, rax
0x180053c38  mov     [rbp+27h+var_58], rax
0x180053c3c  mov     rcx, [rbp+2Fh]; this
0x180053c40  test    rax, rax
0x180053c43  jnz     short loc_180053C57
0x180053c45  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053c4c  mov     edx, 0B5h; void *
0x180053c51  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053c57  mov     rcx, rsi
0x180053c5a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053c5f  mov     [rsp+0B0h+var_80], 800000h; dwFlags
0x180053c67  mov     [rsp+0B0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180053c70  mov     qword ptr [rsp+0B0h+dwFlags], 0; pwszReferrer
0x180053c79  xor     r9d, r9d; pwszVersion
0x180053c7c  mov     r8, rax; pwszObjectName
0x180053c7f  lea     rdx, pwszVerb; "POST"
0x180053c86  mov     rcx, r10; hConnect
0x180053c89  call    cs:__imp_WinHttpOpenRequest
0x180053c8f  mov     rbx, rax
0x180053c92  mov     [rbp+27h+var_60], rax
0x180053c96  mov     rcx, [rbp+2Fh]; this
0x180053c9a  test    rax, rax
0x180053c9d  jnz     short loc_180053CB1
0x180053c9f  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053ca6  mov     edx, 0B9h; void *
0x180053cab  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053cb1  mov     eax, [rbp+27h+nReceiveTimeout]
0x180053cb4  mov     [rsp+0B0h+dwFlags], eax; nReceiveTimeout
0x180053cb8  xor     edx, edx; nResolveTimeout
0x180053cba  mov     r9d, 7530h; nSendTimeout
0x180053cc0  mov     r8d, 0EA60h; nConnectTimeout
0x180053cc6  mov     rcx, rbx; hInternet
0x180053cc9  call    cs:__imp_WinHttpSetTimeouts
0x180053ccf  movsxd  rax, [rbp+27h+arg_48]
0x180053cd3  mov     [rbp+27h+Buffer], rax
0x180053cd7  mov     r9d, 8; dwBufferLength
0x180053cdd  lea     r8, [rbp+27h+Buffer]; lpBuffer
0x180053ce1  lea     edx, [r9+25h]; dwOption
0x180053ce5  mov     rcx, rbx; hInternet
0x180053ce8  call    cs:__imp_WinHttpSetOption
0x180053cee  mov     rcx, [rbp+2Fh]; this
0x180053cf2  test    eax, eax
0x180053cf4  jnz     short loc_180053D08
0x180053cf6  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053cfd  mov     edx, 0C4h; void *
0x180053d02  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053d08  mov     r8, rdi
0x180053d0b  mov     rdx, rbx
0x180053d0e  call    ?AddRequestHeaders@HttpClient@@AEAAXPEAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; HttpClient::AddRequestHeaders(void *,std::map<std::wstring,std::wstring> const &)
0x180053d13  test    byte ptr [rbp+27h+arg_48], 2
0x180053d17  jz      short loc_180053D4C
0x180053d19  mov     [rbp+27h+var_6C], 1
0x180053d20  mov     rdi, [rbp+2Fh]
0x180053d24  mov     r9d, 4; dwBufferLength
0x180053d2a  lea     r8, [rbp+27h+var_6C]; lpBuffer
0x180053d2e  lea     edx, [r9+72h]; dwOption
0x180053d32  mov     rcx, rbx; hInternet
0x180053d35  call    cs:__imp_WinHttpSetOption
0x180053d3b  test    eax, eax
0x180053d3d  jnz     short loc_180053D4C
0x180053d3f  mov     edx, 0CDh; void *
0x180053d44  mov     rcx, rdi; this
0x180053d47  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180053d4c  mov     qword ptr [rsp+0B0h+var_80], 0; dwContext
0x180053d55  mov     eax, [rbp+27h+dwOptionalLength]
0x180053d58  mov     dword ptr [rsp+0B0h+ppwszAcceptTypes], eax; dwTotalLength
0x180053d5c  mov     [rsp+0B0h+dwFlags], eax; int
0x180053d60  mov     r9, [r15]; lpOptional
0x180053d63  mov     r8d, [rbp+27h+dwHeadersLength]; dwHeadersLength
0x180053d67  mov     rdx, r14; lpszHeaders
0x180053d6a  mov     rcx, rbx; hRequest
0x180053d6d  call    cs:__imp_WinHttpSendRequest
0x180053d73  mov     rcx, [rbp+2Fh]; this
0x180053d77  test    eax, eax
0x180053d79  jnz     short loc_180053D8D
0x180053d7b  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053d82  mov     edx, 0D8h; void *
0x180053d87  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053d8d  xor     edx, edx; lpReserved
0x180053d8f  mov     rcx, rbx; hRequest
0x180053d92  call    cs:__imp_WinHttpReceiveResponse
0x180053d98  mov     rcx, [rbp+2Fh]; this
0x180053d9c  test    eax, eax
0x180053d9e  jnz     short loc_180053DB2
0x180053da0  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053da7  mov     edx, 0D9h; void *
0x180053dac  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053db2  mov     [rbp+27h+var_70], 0
0x180053db9  lea     r9, [rbp+27h+var_70]; unsigned int *
0x180053dbd  mov     r8d, 13h; unsigned int
0x180053dc3  mov     rdx, rbx; void *
0x180053dc6  call    ?ExtractHeaderAsDword@HttpClient@@AEAAJPEAXKPEAK@Z; HttpClient::ExtractHeaderAsDword(void *,ulong,ulong *)
0x180053dcb  mov     rcx, [rbp+2Fh]; this
0x180053dcf  test    eax, eax
0x180053dd1  jns     short loc_180053DE8
0x180053dd3  mov     r9d, eax; char *
0x180053dd6  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053ddd  mov     edx, 0DCh; void *
0x180053de2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053de8  lea     rcx, [rbp+27h+var_48]
0x180053dec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180053df1  nop
0x180053df2  lea     r8, [rbp+27h+var_48]
0x180053df6  mov     rdx, rbx
0x180053df9  call    ?ExtractFullHeadersString@HttpClient@@AEAAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HttpClient::ExtractFullHeadersString(void *,std::wstring &)
0x180053dfe  mov     rcx, [rbp+2Fh]; this
0x180053e02  test    eax, eax
0x180053e04  jns     short loc_180053E1B
0x180053e06  mov     r9d, eax; char *
0x180053e09  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053e10  mov     edx, 0DEh; void *
0x180053e15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053e1b  mov     ebx, [rbp+27h+var_70]
0x180053e1e  lea     rcx, [rbp+27h+var_48]
0x180053e22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053e27  nop
0x180053e28  lea     rcx, [rbp+27h+var_60]
0x180053e2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180053e31  nop
0x180053e32  lea     rcx, [rbp+27h+var_58]
0x180053e36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180053e3b  nop
0x180053e3c  lea     rcx, [rbp+27h+var_50]
0x180053e40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180053e45  mov     eax, ebx
0x180053e47  mov     rcx, [rbp+27h+var_28]
0x180053e4b  xor     rcx, rsp; StackCookie
0x180053e4e  call    __security_check_cookie
0x180053e53  mov     rbx, [rsp+0B0h+arg_0]
0x180053e5b  add     rsp, 90h
0x180053e62  pop     r15
0x180053e64  pop     r14
0x180053e66  pop     rdi
0x180053e67  pop     rsi
0x180053e68  pop     rbp
0x180053e69  retn
```
