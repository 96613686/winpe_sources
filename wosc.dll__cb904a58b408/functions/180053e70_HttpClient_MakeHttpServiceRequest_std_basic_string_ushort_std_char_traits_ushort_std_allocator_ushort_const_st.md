# HttpClient::MakeHttpServiceRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,uint,HttpRequestOptions)

- ea: `0x180053e70`
- end: `0x1800541da`
- name: `?MakeHttpServiceRequest@HttpClient@@UEAA?AV?$shared_ptr@VHttpResponse@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@0AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@IW4HttpRequestOptions@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int nReceiveTimeout, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003110`
- `0x180003210`
- `0x180009f90`
- `0x1800101e0`
- `0x1800101fc`
- `0x180014884`
- `0x180019e68`
- `0x180019e88`
- `0x180019f58`
- `0x180052c88`
- `0x180052fbc`
- `0x180053084`
- `0x18005348c`
- `0x1800534dc`
- `0x180053604`
- `0x180053e70`
- `0x180054470`

## import_xrefs

- `WINHTTP!WinHttpReceiveResponse` at `0x18005408f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005408f`
- `WINHTTP!WinHttpSendRequest` at `0x18005406c`
- `WINHTTP!WinHttpSendRequest` at `0x18005406c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180053fe9`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180053fe9`
- `WINHTTP!WinHttpSetOption` at `0x180053fb6`
- `WINHTTP!WinHttpSetOption` at `0x180054033`
- `WINHTTP!WinHttpSetOption` at `0x180053fb6`
- `WINHTTP!WinHttpSetOption` at `0x180054033`
- `WINHTTP!WinHttpSetTimeouts` at `0x180053f97`
- `WINHTTP!WinHttpSetTimeouts` at `0x180053f97`
- `WINHTTP!WinHttpOpenRequest` at `0x180053f59`
- `WINHTTP!WinHttpOpenRequest` at `0x180053f59`
- `WINHTTP!WinHttpConnect` at `0x180053f01`
- `WINHTTP!WinHttpConnect` at `0x180053f01`
- `WINHTTP!WinHttpOpen` at `0x180053ec4`
- `WINHTTP!WinHttpOpen` at `0x180053ec4`

## string_xrefs

- `0x180053eda`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053f17`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053f6f`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053fc4`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x180053ff5`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x18005407a`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x18005409d`: `onecore\base\flighting\common\httpclient\httpclient.cpp`
- `0x1800540d1`: `onecore\base\flighting\common\httpclient\httpclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall HttpClient::MakeHttpServiceRequest(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int nReceiveTimeout,
        int a8)
{
  const char *v11; // r9
  const WCHAR *v12; // rax
  HINTERNET v13; // r10
  const char *v14; // r9
  const WCHAR *v15; // rax
  HINTERNET v16; // r10
  void *v17; // rbx
  const char *v18; // r9
  const char *v19; // r9
  __int64 v20; // rcx
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // eax
  __int64 v27; // rcx
  _BYTE *ResponseBody; // rdi
  _DWORD *v29; // rdi
  int dwFlags; // [rsp+20h] [rbp-99h]
  unsigned int v32; // [rsp+40h] [rbp-79h] BYREF
  _DWORD *v33; // [rsp+48h] [rbp-71h] BYREF
  HINTERNET v34[2]; // [rsp+50h] [rbp-69h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp-59h] BYREF
  void *v36; // [rsp+68h] [rbp-51h] BYREF
  HINTERNET v37; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v38[16]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v39[32]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v40[32]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  v34[0] = WinHttpOpen(L"Wosc", 4u, 0, 0, 0);
  if ( !v34[0] )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v11);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v37 = WinHttpConnect(v13, v12, 0x1BBu, 0);
  if ( !v37 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v14);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
  v17 = WinHttpOpenRequest(v16, L"GET", v15, 0, 0, 0, 0x800000u);
  v36 = v17;
  if ( !v17 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v18);
  WinHttpSetTimeouts(v17, 0, 60000, 30000, nReceiveTimeout);
  Buffer = a8;
  if ( !WinHttpSetOption(v17, 0x2Du, &Buffer, 8u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v19);
  if ( WinHttpSetStatusCallback(v17, HttpClient::HttpRequestCallback, 0xFFFFFFFF, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v21);
  HttpClient::AddRequestHeaders(v20, v17, a5);
  if ( (a8 & 2) != 0 )
  {
    LODWORD(v33) = 1;
    if ( !WinHttpSetOption(v17, 0x76u, &v33, 4u) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x75, v22, v23);
  }
  if ( !WinHttpSendRequest(v17, 0, 0, 0, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v24);
  if ( !WinHttpReceiveResponse(v17, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      v25);
  v32 = 0;
  v26 = HttpClient::ExtractHeaderAsDword(retaddr, v17, 0x13u, &v32);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
      (const char *)(unsigned int)v26,
      dwFlags);
  std::string::string(v39);
  if ( v32 == 200 )
  {
    ResponseBody = (_BYTE *)HttpClient::ExtractResponseBody(v27, v40, v17);
    if ( v39 != ResponseBody )
    {
      std::string::_Tidy_deallocate(v39);
      std::string::_Take_contents(v39, ResponseBody);
    }
    std::string::_Tidy_deallocate(v40);
  }
  HttpClient::ExtractResponseHeaders(v27, v38, v17, a6);
  v29 = operator new(0x48u);
  v33 = v29;
  *(_OWORD *)v29 = 0;
  v29[2] = 1;
  v29[3] = 1;
  *(_QWORD *)v29 = &std::_Ref_count_obj2<HttpResponse>::`vftable';
  std::_Construct_in_place<HttpResponse,unsigned long &,std::string,std::map<std::wstring,std::wstring> const>(
    v29 + 4,
    &v32,
    v39,
    v38);
  *a2 = v29 + 4;
  a2[1] = v29;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v38);
  std::string::_Tidy_deallocate(v39);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v36);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v34);
  return a2;
}

```

## disassembly

```asm
0x180053e70  mov     [rsp-8+arg_0], rbx
0x180053e75  push    rbp
0x180053e76  push    rsi
0x180053e77  push    rdi
0x180053e78  push    r14
0x180053e7a  push    r15
0x180053e7c  lea     rbp, [rsp-17h]
0x180053e81  sub     rsp, 0D0h
0x180053e88  mov     rax, cs:__security_cookie
0x180053e8f  xor     rax, rsp
0x180053e92  mov     [rbp+37h+var_28], rax
0x180053e96  mov     rdi, r9
0x180053e99  mov     rbx, r8
0x180053e9c  mov     r14, rdx
0x180053e9f  mov     [rbp+37h+var_A0], rdx
0x180053ea3  mov     rsi, [rbp+37h+arg_20]
0x180053ea7  mov     r15, [rbp+37h+arg_28]
0x180053eab  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x180053eb3  xor     r9d, r9d; pszProxyBypassW
0x180053eb6  xor     r8d, r8d; pszProxyW
0x180053eb9  lea     edx, [r9+4]; dwAccessType
0x180053ebd  lea     rcx, pszAgentW; "Wosc"
0x180053ec4  call    cs:__imp_WinHttpOpen
0x180053eca  mov     r10, rax
0x180053ecd  mov     [rbp+37h+var_A0], rax
0x180053ed1  mov     rcx, [rbp+3Fh]; this
0x180053ed5  test    rax, rax
0x180053ed8  jnz     short loc_180053EEA
0x180053eda  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053ee1  lea     edx, [rax+52h]; void *
0x180053ee4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053eea  mov     rcx, rbx
0x180053eed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053ef2  mov     r8d, 1BBh; nServerPort
0x180053ef8  xor     r9d, r9d; dwReserved
0x180053efb  mov     rdx, rax; pswzServerName
0x180053efe  mov     rcx, r10; hSession
0x180053f01  call    cs:__imp_WinHttpConnect
0x180053f07  mov     r10, rax
0x180053f0a  mov     [rbp+37h+var_80], rax
0x180053f0e  mov     rcx, [rbp+3Fh]; this
0x180053f12  test    rax, rax
0x180053f15  jnz     short loc_180053F27
0x180053f17  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053f1e  lea     edx, [rax+55h]; void *
0x180053f21  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053f27  mov     rcx, rdi
0x180053f2a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053f2f  mov     [rsp+0F0h+var_C0], 800000h; dwFlags
0x180053f37  mov     [rsp+0F0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180053f40  mov     qword ptr [rsp+0F0h+dwFlags], 0; pwszReferrer
0x180053f49  xor     r9d, r9d; pwszVersion
0x180053f4c  mov     r8, rax; pwszObjectName
0x180053f4f  lea     rdx, aGet; "GET"
0x180053f56  mov     rcx, r10; hConnect
0x180053f59  call    cs:__imp_WinHttpOpenRequest
0x180053f5f  mov     rbx, rax
0x180053f62  mov     [rbp+37h+var_88], rax
0x180053f66  mov     rcx, [rbp+3Fh]; this
0x180053f6a  test    rax, rax
0x180053f6d  jnz     short loc_180053F7F
0x180053f6f  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053f76  lea     edx, [rax+5Fh]; void *
0x180053f79  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053f7f  mov     eax, [rbp+37h+nReceiveTimeout]
0x180053f82  mov     [rsp+0F0h+dwFlags], eax; nReceiveTimeout
0x180053f86  xor     edx, edx; nResolveTimeout
0x180053f88  mov     r9d, 7530h; nSendTimeout
0x180053f8e  mov     r8d, 0EA60h; nConnectTimeout
0x180053f94  mov     rcx, rbx; hInternet
0x180053f97  call    cs:__imp_WinHttpSetTimeouts
0x180053f9d  movsxd  rax, [rbp+37h+arg_38]
0x180053fa1  mov     [rbp+37h+Buffer], rax
0x180053fa5  mov     r9d, 8; dwBufferLength
0x180053fab  lea     r8, [rbp+37h+Buffer]; lpBuffer
0x180053faf  lea     edx, [r9+25h]; dwOption
0x180053fb3  mov     rcx, rbx; hInternet
0x180053fb6  call    cs:__imp_WinHttpSetOption
0x180053fbc  mov     rcx, [rbp+3Fh]; this
0x180053fc0  test    eax, eax
0x180053fc2  jnz     short loc_180053FD4
0x180053fc4  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053fcb  lea     edx, [rax+69h]; void *
0x180053fce  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053fd4  mov     rdi, [rbp+3Fh]
0x180053fd8  xor     r9d, r9d; dwReserved
0x180053fdb  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x180053fdf  lea     rdx, ?HttpRequestCallback@HttpClient@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x180053fe6  mov     rcx, rbx; hInternet
0x180053fe9  call    cs:__imp_WinHttpSetStatusCallback
0x180053fef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053ff3  jnz     short loc_180054008
0x180053ff5  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180053ffc  lea     edx, [rax+6Eh]; void *
0x180053fff  mov     rcx, rdi; this
0x180054002  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180054008  mov     r8, rsi
0x18005400b  mov     rdx, rbx
0x18005400e  call    ?AddRequestHeaders@HttpClient@@AEAAXPEAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; HttpClient::AddRequestHeaders(void *,std::map<std::wstring,std::wstring> const &)
0x180054013  mov     esi, 1
0x180054018  test    byte ptr [rbp+37h+arg_38], 2
0x18005401c  jz      short loc_180054048
0x18005401e  mov     dword ptr [rbp+37h+var_A8], esi
0x180054021  mov     rdi, [rbp+3Fh]
0x180054025  lea     r9d, [rsi+3]; dwBufferLength
0x180054029  lea     r8, [rbp+37h+var_A8]; lpBuffer
0x18005402d  lea     edx, [rsi+75h]; dwOption
0x180054030  mov     rcx, rbx; hInternet
0x180054033  call    cs:__imp_WinHttpSetOption
0x180054039  test    eax, eax
0x18005403b  jnz     short loc_180054048
0x18005403d  lea     edx, [rsi+74h]; void *
0x180054040  mov     rcx, rdi; this
0x180054043  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180054048  mov     qword ptr [rsp+0F0h+var_C0], 0; dwContext
0x180054051  mov     dword ptr [rsp+0F0h+ppwszAcceptTypes], 0; dwTotalLength
0x180054059  mov     [rsp+0F0h+dwFlags], 0; int
0x180054061  xor     r9d, r9d; lpOptional
0x180054064  xor     r8d, r8d; dwHeadersLength
0x180054067  xor     edx, edx; lpszHeaders
0x180054069  mov     rcx, rbx; hRequest
0x18005406c  call    cs:__imp_WinHttpSendRequest
0x180054072  mov     rcx, [rbp+3Fh]; this
0x180054076  test    eax, eax
0x180054078  jnz     short loc_18005408A
0x18005407a  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x180054081  lea     edx, [rax+79h]; void *
0x180054084  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005408a  xor     edx, edx; lpReserved
0x18005408c  mov     rcx, rbx; hRequest
0x18005408f  call    cs:__imp_WinHttpReceiveResponse
0x180054095  mov     rcx, [rbp+3Fh]; this
0x180054099  test    eax, eax
0x18005409b  jnz     short loc_1800540AD
0x18005409d  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x1800540a4  lea     edx, [rax+7Ah]; void *
0x1800540a7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800540ad  mov     [rbp+37h+var_B0], 0
0x1800540b4  lea     r9, [rbp+37h+var_B0]; unsigned int *
0x1800540b8  mov     r8d, 13h; unsigned int
0x1800540be  mov     rdx, rbx; void *
0x1800540c1  call    ?ExtractHeaderAsDword@HttpClient@@AEAAJPEAXKPEAK@Z; HttpClient::ExtractHeaderAsDword(void *,ulong,ulong *)
0x1800540c6  mov     rcx, [rbp+3Fh]; this
0x1800540ca  test    eax, eax
0x1800540cc  jns     short loc_1800540E3
0x1800540ce  mov     r9d, eax; char *
0x1800540d1  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x1800540d8  mov     edx, 7Dh ; '}'; void *
0x1800540dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800540e3  lea     rcx, [rbp+37h+var_68]
0x1800540e7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800540ec  nop
0x1800540ed  cmp     [rbp+37h+var_B0], 0C8h
0x1800540f4  jnz     short loc_18005412C
0x1800540f6  mov     r8, rbx
0x1800540f9  lea     rdx, [rbp+37h+var_48]
0x1800540fd  call    ?ExtractResponseBody@HttpClient@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; HttpClient::ExtractResponseBody(void *)
0x180054102  mov     rdi, rax
0x180054105  lea     rax, [rbp+37h+var_68]
0x180054109  cmp     rax, rdi
0x18005410c  jz      short loc_180054123
0x18005410e  lea     rcx, [rbp+37h+var_68]
0x180054112  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180054117  mov     rdx, rdi
0x18005411a  lea     rcx, [rbp+37h+var_68]
0x18005411e  call    ?_Take_contents@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXAEAV12@@Z; std::string::_Take_contents(std::string &)
0x180054123  lea     rcx, [rbp+37h+var_48]
0x180054127  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005412c  mov     r9, r15
0x18005412f  mov     r8, rbx
0x180054132  lea     rdx, [rbp+37h+var_78]
0x180054136  call    ?ExtractResponseHeaders@HttpClient@@AEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; HttpClient::ExtractResponseHeaders(void *,std::vector<std::wstring> const &)
0x18005413b  nop
0x18005413c  mov     ecx, 48h ; 'H'; Size
0x180054141  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054146  mov     rdi, rax
0x180054149  mov     [rbp+37h+var_A8], rax
0x18005414d  xorps   xmm0, xmm0
0x180054150  movups  xmmword ptr [rax], xmm0
0x180054153  mov     [rax+8], esi
0x180054156  mov     [rax+0Ch], esi
0x180054159  lea     rax, ??_7?$_Ref_count_obj2@VHttpResponse@@@std@@6B@; const std::_Ref_count_obj2<HttpResponse>::`vftable'
0x180054160  mov     [rdi], rax
0x180054163  lea     rbx, [rdi+10h]
0x180054167  lea     r9, [rbp+37h+var_78]
0x18005416b  lea     r8, [rbp+37h+var_68]
0x18005416f  lea     rdx, [rbp+37h+var_B0]
0x180054173  mov     rcx, rbx
0x180054176  call    ??$_Construct_in_place@VHttpResponse@@AEAKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$CBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@std@@YAXAEAVHttpResponse@@AEAK$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@0@@Z; std::_Construct_in_place<HttpResponse,ulong &,std::string,std::map<std::wstring,std::wstring> const>(HttpResponse &,ulong &,std::string &&,std::map<std::wstring,std::wstring> const &&)
0x18005417b  nop
0x18005417c  mov     [r14], rbx
0x18005417f  mov     [r14+8], rdi
0x180054183  lea     rcx, [rbp+37h+var_78]
0x180054187  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18005418c  nop
0x18005418d  lea     rcx, [rbp+37h+var_68]
0x180054191  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180054196  nop
0x180054197  lea     rcx, [rbp+37h+var_88]
0x18005419b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800541a0  nop
0x1800541a1  lea     rcx, [rbp+37h+var_80]
0x1800541a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800541aa  nop
0x1800541ab  lea     rcx, [rbp+37h+var_A0]
0x1800541af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800541b4  mov     rax, r14
0x1800541b7  mov     rcx, [rbp+37h+var_28]
0x1800541bb  xor     rcx, rsp; StackCookie
0x1800541be  call    __security_check_cookie
0x1800541c3  mov     rbx, [rsp+0F0h+arg_0]
0x1800541cb  add     rsp, 0D0h
0x1800541d2  pop     r15
0x1800541d4  pop     r14
0x1800541d6  pop     rdi
0x1800541d7  pop     rsi
0x1800541d8  pop     rbp
0x1800541d9  retn
```
