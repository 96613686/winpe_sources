# SendRequestInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::function<void (void *)>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,ushort)

- ea: `0x14009ba9c`
- end: `0x14009c0b7`
- name: `?SendRequestInternal@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@V?$function@$$A6AXPEAX@Z@2@0_NG@Z`
- size: `1563`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pswzServerName@<rcx>, LPCWSTR pwszObjectName@<rdx>, __int64, LPCWSTR pwszVerb, char, __int16)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x14009b894`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000b744`
- `0x14000b814`
- `0x14000ccac`
- `0x140010e18`
- `0x14001f62c`
- `0x14001f654`
- `0x14001f6b4`
- `0x14002c2e4`
- `0x140047e78`
- `0x14005bbac`
- `0x140060ba4`
- `0x140060f58`
- `0x1400999a0`
- `0x140099a3c`
- `0x140099ad8`
- `0x14009aac0`
- `0x14009ba9c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14009be89`
- `KERNEL32!GetLastError` at `0x14009beba`
- `KERNEL32!GetLastError` at `0x14009bf1c`
- `KERNEL32!GetLastError` at `0x14009bf77`
- `KERNEL32!GetLastError` at `0x14009bfd2`
- `KERNEL32!GetLastError` at `0x14009c086`
- `KERNEL32!GetLastError` at `0x14009be89`
- `KERNEL32!GetLastError` at `0x14009beba`
- `KERNEL32!GetLastError` at `0x14009bf1c`
- `KERNEL32!GetLastError` at `0x14009bf77`
- `KERNEL32!GetLastError` at `0x14009bfd2`
- `KERNEL32!GetLastError` at `0x14009c086`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14009bdef`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14009bdef`
- `WINHTTP!WinHttpReceiveResponse` at `0x14009bdce`
- `WINHTTP!WinHttpReceiveResponse` at `0x14009bdce`
- `WINHTTP!WinHttpSendRequest` at `0x14009bdb9`
- `WINHTTP!WinHttpSendRequest` at `0x14009bdb9`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x14009bce7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x14009bce7`
- `WINHTTP!WinHttpOpenRequest` at `0x14009bc11`
- `WINHTTP!WinHttpOpenRequest` at `0x14009bc11`
- `WINHTTP!WinHttpConnect` at `0x14009bba2`
- `WINHTTP!WinHttpConnect` at `0x14009bba2`
- `WINHTTP!WinHttpOpen` at `0x14009bb1c`
- `WINHTTP!WinHttpOpen` at `0x14009bb1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SendRequestInternal(
        _QWORD *pswzServerName,
        const WCHAR *pwszObjectName,
        _QWORD *a3,
        __int64 ***a4,
        __int64 a5,
        LPCWSTR pwszVerb,
        unsigned __int8 a7,
        INTERNET_PORT a8)
{
  const WCHAR *v10; // rdi
  INTERNET_PORT v11; // r15
  _QWORD *v12; // r9
  __int64 *v13; // rbx
  Private::Format *v14; // rax
  Private::Format *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  BOOL v18; // edi
  __int64 **v19; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v22; // rax
  LPVOID *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rbx
  signed int v28; // eax
  signed int LastError; // eax
  unsigned int v30; // ebx
  signed int v31; // eax
  unsigned int v32; // ebx
  signed int v33; // eax
  unsigned int v34; // ebx
  signed int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rbx
  signed int v38; // eax
  HINTERNET hRequest; // [rsp+40h] [rbp-C0h] BYREF
  HINTERNET *p_hSession; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v41; // [rsp+50h] [rbp-B0h] BYREF
  HINTERNET hSession; // [rsp+58h] [rbp-A8h] BYREF
  HINTERNET hConnect; // [rsp+60h] [rbp-A0h] BYREF
  __int64 ***v44; // [rsp+68h] [rbp-98h]
  __int128 v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  char *v49[5]; // [rsp+98h] [rbp-68h] BYREF
  LPVOID lpOptional[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD dwOptionalLength[2]; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-28h]
  char *pExceptionObject[8]; // [rsp+E0h] [rbp-20h] BYREF
  char *v54[4]; // [rsp+120h] [rbp+20h] BYREF
  char *v55[4]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v56[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v57[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v58[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v44 = a4;
  v41 = a3;
  v10 = pwszVerb;
  v48 = a5;
  v11 = a8;
  if ( !a8 )
  {
    v11 = 443;
    if ( !a7 )
      v11 = 80;
  }
  hSession = WinHttpOpen(0, 4u, 0, 0, 0);
  if ( !hSession )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v30);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hSession;
  ScopeGuard::ScopeGuard__lambda_dff20fe531c161d312228c3011b1ee86___(v58, &p_hSession);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( pswzServerName[3] <= 7u )
      v12 = pswzServerName;
    else
      v12 = (_QWORD *)*pswzServerName;
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v12);
  }
  if ( pswzServerName[3] > 7u )
    pswzServerName = (_QWORD *)*pswzServerName;
  hConnect = WinHttpConnect(hSession, (LPCWSTR)pswzServerName, v11, 0);
  if ( !hConnect )
  {
    v31 = GetLastError();
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v32);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v32);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hConnect;
  ScopeGuard::ScopeGuard__lambda_a37f6ebc28d708e5d633bdd02f7a3cad___(v57, &p_hSession);
  if ( *((_QWORD *)pwszObjectName + 3) > 7u )
    pwszObjectName = *(const WCHAR **)pwszObjectName;
  if ( *((_QWORD *)pwszVerb + 3) > 7u )
    v10 = *(const WCHAR **)pwszVerb;
  hRequest = WinHttpOpenRequest(hConnect, v10, pwszObjectName, 0, 0, 0, a7 << 23);
  if ( !hRequest )
  {
    v33 = GetLastError();
    v34 = v33;
    if ( v33 > 0 )
      v34 = (unsigned __int16)v33 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v34);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hRequest;
  ScopeGuard::ScopeGuard__lambda_bf43a75a91dfa73a8e629cdbcec234d7___(v56, &p_hSession);
  v13 = **v44;
  while ( !*((_BYTE *)v13 + 25) )
  {
    std::wstring::wstring((__int64)v54, (__int64)(v13 + 4));
    std::wstring::wstring((__int64)v55, (__int64)(v13 + 8));
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v45, L"{0}: {1}", 8u);
    v14 = (Private::Format *)StringAlgo::FormatString(pExceptionObject, &v45);
    v15 = (Private::Format *)Private::Format::operator%<std::wstring>(v14);
    v16 = Private::Format::operator%<std::wstring>(v15);
    v17 = std::wstring::wstring((__int64)v49, v16);
    if ( *(_QWORD *)(v17 + 24) > 7u )
      v17 = *(_QWORD *)v17;
    v18 = WinHttpAddRequestHeaders(hRequest, (LPCWSTR)v17, 0xFFFFFFFF, 0);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(pExceptionObject);
    if ( !v18 )
    {
      v35 = GetLastError();
      v36 = v35;
      if ( v35 > 0 )
        v36 = (unsigned __int16)v35 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v36);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v36);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v54);
    v19 = (__int64 **)v13[2];
    if ( *((_BYTE *)v19 + 25) )
    {
      for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v13 = i;
      v13 = i;
    }
    else
    {
      v13 = (__int64 *)v13[2];
      for ( j = *v19; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v13 = j;
    }
  }
  v22 = v41;
  if ( v41[3] > 7u )
    v22 = (_QWORD *)*v41;
  StringAlgo::ToUtf8(lpOptional, v22);
  if ( *(_QWORD *)dwOptionalLength > 0xFFFFFFFF )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147024809);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v23 = lpOptional;
  if ( v52 > 0xF )
    v23 = (LPVOID *)lpOptional[0];
  if ( !WinHttpSendRequest(hRequest, 0, 0, v23, dwOptionalLength[0], dwOptionalLength[0], 0) )
  {
    v37 = std::wstring::wstring(v49, L"SendRequest");
    v38 = GetLastError();
    if ( v38 > 0 )
      v38 = (unsigned __int16)v38 | 0x80070000;
    MessageException::MessageException(pExceptionObject, (unsigned int)v38, v37);
    throw (MessageException *)pExceptionObject;
  }
  if ( !WinHttpReceiveResponse(hRequest, 0) )
  {
    v27 = std::wstring::wstring(v49, L"ReceiveResponse");
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    MessageException::MessageException(pExceptionObject, (unsigned int)v28, v27);
    throw (MessageException *)pExceptionObject;
  }
  v41 = hRequest;
  v24 = *(_QWORD *)(a5 + 56);
  if ( !v24 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v24 + 16LL))(v24, &v41);
  std::string::~string((char **)lpOptional);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v56);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v57);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v58);
  v26 = *(_QWORD *)(a5 + 56);
  if ( v26 )
  {
    LOBYTE(v25) = v26 != a5;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 32LL))(v26, v25);
    *(_QWORD *)(a5 + 56) = 0;
  }
}

```

## disassembly

```asm
0x14009ba9c  push    rbp
0x14009ba9e  push    rbx
0x14009ba9f  push    rsi
0x14009baa0  push    rdi
0x14009baa1  push    r12
0x14009baa3  push    r13
0x14009baa5  push    r15
0x14009baa7  lea     rbp, [rsp-130h]
0x14009baaf  sub     rsp, 230h
0x14009bab6  mov     rax, cs:__security_cookie
0x14009babd  xor     rax, rsp
0x14009bac0  mov     [rbp+160h+var_40], rax
0x14009bac7  mov     [rsp+260h+var_1F8], r9
0x14009bacc  mov     [rsp+260h+var_210], r8
0x14009bad1  mov     r12, rdx
0x14009bad4  mov     rbx, rcx
0x14009bad7  mov     rdi, [rbp+160h+pwszVerb]
0x14009bade  mov     r13, [rbp+160h+arg_20]
0x14009bae5  mov     [rbp+160h+var_1D0], r13
0x14009bae9  movzx   r15d, [rbp+160h+arg_38]
0x14009baf1  xor     esi, esi
0x14009baf3  test    r15w, r15w
0x14009baf7  jnz     short loc_14009BB0C
0x14009baf9  cmp     [rbp+160h+arg_30], sil
0x14009bb00  mov     r15d, 1BBh
0x14009bb06  jnz     short loc_14009BB0C
0x14009bb08  lea     r15d, [rsi+50h]
0x14009bb0c  mov     [rsp+260h+dwFlags], esi; dwFlags
0x14009bb10  xor     r9d, r9d; pszProxyBypassW
0x14009bb13  xor     r8d, r8d; pszProxyW
0x14009bb16  lea     edx, [r9+4]; dwAccessType
0x14009bb1a  xor     ecx, ecx; pszAgentW
0x14009bb1c  call    cs:__imp_WinHttpOpen
0x14009bb22  mov     [rsp+260h+hSession], rax
0x14009bb27  test    rax, rax
0x14009bb2a  jz      loc_14009BEBA
0x14009bb30  lea     rax, [rsp+260h+hSession]
0x14009bb35  mov     [rsp+260h+var_218], rax
0x14009bb3a  lea     rdx, [rsp+260h+var_218]
0x14009bb3f  lea     rcx, [rbp+160h+var_80]
0x14009bb46  call    ScopeGuard__ScopeGuard__lambda_dff20fe531c161d312228c3011b1ee86___
0x14009bb4b  nop
0x14009bb4c  lea     rsi, WPP_GLOBAL_Control
0x14009bb53  mov     rcx, cs:WPP_GLOBAL_Control
0x14009bb5a  cmp     rcx, rsi
0x14009bb5d  jz      short loc_14009BB89
0x14009bb5f  test    byte ptr [rcx+1Ch], 4
0x14009bb63  jz      short loc_14009BB89
0x14009bb65  cmp     qword ptr [rbx+18h], 7
0x14009bb6a  jbe     short loc_14009BB71
0x14009bb6c  mov     r9, [rbx]
0x14009bb6f  jmp     short loc_14009BB74
0x14009bb71  mov     r9, rbx
0x14009bb74  mov     edx, 0Ch
0x14009bb79  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009bb80  mov     rcx, [rcx+10h]
0x14009bb84  call    WPP_SF_S
0x14009bb89  cmp     qword ptr [rbx+18h], 7
0x14009bb8e  jbe     short loc_14009BB93
0x14009bb90  mov     rbx, [rbx]
0x14009bb93  xor     r9d, r9d; dwReserved
0x14009bb96  movzx   r8d, r15w; nServerPort
0x14009bb9a  mov     rdx, rbx; pswzServerName
0x14009bb9d  mov     rcx, [rsp+260h+hSession]; hSession
0x14009bba2  call    cs:__imp_WinHttpConnect
0x14009bba8  mov     [rsp+260h+hConnect], rax
0x14009bbad  xor     r15d, r15d
0x14009bbb0  test    rax, rax
0x14009bbb3  jz      loc_14009BF1C
0x14009bbb9  lea     rax, [rsp+260h+hConnect]
0x14009bbbe  mov     [rsp+260h+var_218], rax
0x14009bbc3  lea     rdx, [rsp+260h+var_218]
0x14009bbc8  lea     rcx, [rbp+160h+var_C0]
0x14009bbcf  call    ScopeGuard__ScopeGuard__lambda_a37f6ebc28d708e5d633bdd02f7a3cad___
0x14009bbd4  nop
0x14009bbd5  movzx   eax, [rbp+160h+arg_30]
0x14009bbdc  shl     eax, 17h
0x14009bbdf  cmp     qword ptr [r12+18h], 7
0x14009bbe5  jbe     short loc_14009BBEB
0x14009bbe7  mov     r12, [r12]
0x14009bbeb  cmp     qword ptr [rdi+18h], 7
0x14009bbf0  jbe     short loc_14009BBF5
0x14009bbf2  mov     rdi, [rdi]
0x14009bbf5  mov     [rsp+260h+var_230], eax; dwFlags
0x14009bbf9  mov     [rsp+260h+ppwszAcceptTypes], r15; ppwszAcceptTypes
0x14009bbfe  mov     qword ptr [rsp+260h+dwFlags], r15; pwszReferrer
0x14009bc03  xor     r9d, r9d; pwszVersion
0x14009bc06  mov     r8, r12; pwszObjectName
0x14009bc09  mov     rdx, rdi; pwszVerb
0x14009bc0c  mov     rcx, [rsp+260h+hConnect]; hConnect
0x14009bc11  call    cs:__imp_WinHttpOpenRequest
0x14009bc17  mov     [rsp+260h+hRequest], rax
0x14009bc1c  test    rax, rax
0x14009bc1f  jz      loc_14009BF77
0x14009bc25  lea     rax, [rsp+260h+hRequest]
0x14009bc2a  mov     [rsp+260h+var_218], rax
0x14009bc2f  lea     rdx, [rsp+260h+var_218]
0x14009bc34  lea     rcx, [rbp+160h+var_100]
0x14009bc38  call    ScopeGuard__ScopeGuard__lambda_bf43a75a91dfa73a8e629cdbcec234d7___
0x14009bc3d  nop
0x14009bc3e  mov     rbx, [rsp+260h+var_1F8]
0x14009bc43  mov     rbx, [rbx]
0x14009bc46  mov     rbx, [rbx]
0x14009bc49  mov     r12d, 0FFFFFFFFh
0x14009bc4f  cmp     [rbx+19h], r15b
0x14009bc53  jnz     loc_14009BD6B
0x14009bc59  lea     rdx, [rbx+20h]
0x14009bc5d  lea     rcx, [rbp+160h+var_140]
0x14009bc61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14009bc66  nop
0x14009bc67  lea     rdx, [rbx+40h]
0x14009bc6b  lea     rcx, [rbp+160h+var_120]
0x14009bc6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14009bc74  nop
0x14009bc75  xorps   xmm0, xmm0
0x14009bc78  movups  [rsp+260h+var_1F0], xmm0
0x14009bc7d  mov     [rbp+160h+var_1E0], r15
0x14009bc81  mov     [rbp+160h+var_1D8], r15
0x14009bc85  mov     r8d, 8
0x14009bc8b  lea     rdx, a01; "{0}: {1}"
0x14009bc92  lea     rcx, [rsp+260h+var_1F0]
0x14009bc97  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14009bc9c  lea     rdx, [rsp+260h+var_1F0]
0x14009bca1  lea     rcx, [rbp+160h+pExceptionObject]
0x14009bca5  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x14009bcaa  nop
0x14009bcab  lea     rdx, [rbp+160h+var_140]
0x14009bcaf  mov     rcx, rax; this
0x14009bcb2  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x14009bcb7  lea     rdx, [rbp+160h+var_120]
0x14009bcbb  mov     rcx, rax; this
0x14009bcbe  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x14009bcc3  mov     rdx, rax
0x14009bcc6  lea     rcx, [rbp+160h+var_1C8]
0x14009bcca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14009bccf  cmp     qword ptr [rax+18h], 7
0x14009bcd4  jbe     short loc_14009BCD9
0x14009bcd6  mov     rax, [rax]
0x14009bcd9  xor     r9d, r9d; dwModifiers
0x14009bcdc  mov     r8d, r12d; dwHeadersLength
0x14009bcdf  mov     rdx, rax; lpszHeaders
0x14009bce2  mov     rcx, [rsp+260h+hRequest]; hRequest
0x14009bce7  call    cs:__imp_WinHttpAddRequestHeaders
0x14009bced  mov     edi, eax
0x14009bcef  lea     rcx, [rbp+160h+var_1C8]
0x14009bcf3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009bcf8  nop
0x14009bcf9  lea     rcx, [rbp+160h+pExceptionObject]
0x14009bcfd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009bd02  test    edi, edi
0x14009bd04  jz      loc_14009BFD2
0x14009bd0a  lea     rcx, [rbp+160h+var_120]
0x14009bd0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009bd13  lea     rcx, [rbp+160h+var_140]
0x14009bd17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009bd1c  mov     rcx, [rbx+10h]
0x14009bd20  cmp     [rcx+19h], r15b
0x14009bd24  jz      short loc_14009BD47
0x14009bd26  mov     rax, [rbx+8]
0x14009bd2a  jmp     short loc_14009BD39
0x14009bd2c  cmp     rbx, [rax+10h]
0x14009bd30  jnz     short loc_14009BD3F
0x14009bd32  mov     rbx, rax
0x14009bd35  mov     rax, [rax+8]
0x14009bd39  cmp     [rax+19h], r15b
0x14009bd3d  jz      short loc_14009BD2C
0x14009bd3f  mov     rbx, rax
0x14009bd42  jmp     loc_14009BC4F
0x14009bd47  mov     rbx, rcx
0x14009bd4a  mov     rcx, [rcx]
0x14009bd4d  cmp     [rcx+19h], r15b
0x14009bd51  jnz     loc_14009BC4F
0x14009bd57  mov     rbx, rcx
0x14009bd5a  mov     rax, [rcx]
0x14009bd5d  mov     rcx, rax
0x14009bd60  cmp     [rax+19h], r15b
0x14009bd64  jz      short loc_14009BD57
0x14009bd66  jmp     loc_14009BC4F
0x14009bd6b  mov     rax, [rsp+260h+var_210]
0x14009bd70  cmp     qword ptr [rax+18h], 7
0x14009bd75  jbe     short loc_14009BD7A
0x14009bd77  mov     rax, [rax]
0x14009bd7a  mov     rdx, rax
0x14009bd7d  lea     rcx, [rbp+160h+lpOptional]
0x14009bd81  call    ?ToUtf8@StringAlgo@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; StringAlgo::ToUtf8(ushort const *)
0x14009bd86  nop
0x14009bd87  mov     rax, qword ptr [rbp+160h+dwOptionalLength]
0x14009bd8b  cmp     rax, r12
0x14009bd8e  ja      loc_14009C02D
0x14009bd94  lea     r9, [rbp+160h+lpOptional]
0x14009bd98  cmp     [rbp+160h+var_188], 0Fh
0x14009bd9d  cmova   r9, [rbp+160h+lpOptional]; lpOptional
0x14009bda2  mov     qword ptr [rsp+260h+var_230], r15; dwContext
0x14009bda7  mov     dword ptr [rsp+260h+ppwszAcceptTypes], eax; dwTotalLength
0x14009bdab  mov     [rsp+260h+dwFlags], eax; dwOptionalLength
0x14009bdaf  xor     r8d, r8d; dwHeadersLength
0x14009bdb2  xor     edx, edx; lpszHeaders
0x14009bdb4  mov     rcx, [rsp+260h+hRequest]; hRequest
0x14009bdb9  call    cs:__imp_WinHttpSendRequest
0x14009bdbf  test    eax, eax
0x14009bdc1  jz      loc_14009C073
0x14009bdc7  xor     edx, edx; lpReserved
0x14009bdc9  mov     rcx, [rsp+260h+hRequest]; hRequest
0x14009bdce  call    cs:__imp_WinHttpReceiveResponse
0x14009bdd4  test    eax, eax
0x14009bdd6  jz      loc_14009BE76
0x14009bddc  mov     rax, [rsp+260h+hRequest]
0x14009bde1  mov     [rsp+260h+var_210], rax
0x14009bde6  mov     rcx, [r13+38h]
0x14009bdea  test    rcx, rcx
0x14009bded  jnz     short loc_14009BDF6
0x14009bdef  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14009bdf5  int     3; Trap to Debugger
0x14009bdf6  mov     rax, [rcx]
0x14009bdf9  lea     rdx, [rsp+260h+var_210]
0x14009bdfe  mov     rax, [rax+10h]
0x14009be02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009be07  nop
0x14009be08  lea     rcx, [rbp+160h+lpOptional]
0x14009be0c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14009be11  nop
0x14009be12  lea     rcx, [rbp+160h+var_100]; this
0x14009be16  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x14009be1b  nop
0x14009be1c  lea     rcx, [rbp+160h+var_C0]; this
0x14009be23  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x14009be28  nop
0x14009be29  lea     rcx, [rbp+160h+var_80]; this
0x14009be30  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x14009be35  nop
0x14009be36  mov     rcx, [r13+38h]
0x14009be3a  test    rcx, rcx
0x14009be3d  jz      short loc_14009BE55
0x14009be3f  mov     rax, [rcx]
0x14009be42  cmp     rcx, r13
0x14009be45  setnz   dl
0x14009be48  mov     rax, [rax+20h]
0x14009be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009be51  mov     [r13+38h], r15
0x14009be55  mov     rcx, [rbp+160h+var_40]
0x14009be5c  xor     rcx, rsp; StackCookie
0x14009be5f  call    __security_check_cookie
0x14009be64  add     rsp, 230h
0x14009be6b  pop     r15
0x14009be6d  pop     r13
0x14009be6f  pop     r12
0x14009be71  pop     rdi
0x14009be72  pop     rsi
0x14009be73  pop     rbx
0x14009be74  pop     rbp
0x14009be75  retn
0x14009be76  lea     rdx, aReceiverespons; "ReceiveResponse"
0x14009be7d  lea     rcx, [rbp+160h+var_1C8]
0x14009be81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14009be86  mov     rbx, rax
0x14009be89  call    cs:__imp_GetLastError
0x14009be8f  test    eax, eax
0x14009be91  jle     short loc_14009BE9B
0x14009be93  movzx   eax, ax
0x14009be96  or      eax, 80070000h
0x14009be9b  mov     r8, rbx
0x14009be9e  mov     edx, eax
0x14009bea0  lea     rcx, [rbp+160h+pExceptionObject]
0x14009bea4  call    ??0MessageException@@QEAA@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MessageException::MessageException(long,std::wstring)
0x14009bea9  lea     rdx, _TI3?AVMessageException@@; pThrowInfo
0x14009beb0  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x14009beb4  call    _CxxThrowException_0
0x14009beba  call    cs:__imp_GetLastError
0x14009bec0  mov     ebx, eax
0x14009bec2  test    eax, eax
0x14009bec4  jle     short loc_14009BECF
0x14009bec6  movzx   ebx, ax
0x14009bec9  or      ebx, 80070000h
0x14009becf  lea     rsi, WPP_GLOBAL_Control
0x14009bed6  mov     rcx, cs:WPP_GLOBAL_Control
0x14009bedd  cmp     rcx, rsi
0x14009bee0  jz      short loc_14009BF00
0x14009bee2  test    byte ptr [rcx+1Ch], 1
0x14009bee6  jz      short loc_14009BF00
0x14009bee8  mov     edx, 0Bh
0x14009beed  mov     r9d, ebx
0x14009bef0  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009bef7  mov     rcx, [rcx+10h]
0x14009befb  call    WPP_SF_d
0x14009bf00  mov     edx, ebx; int
0x14009bf02  lea     rcx, [rbp+160h+var_1C8]; this
0x14009bf06  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14009bf0b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14009bf12  lea     rcx, [rbp+160h+var_1C8]; pExceptionObject
0x14009bf16  call    _CxxThrowException_0
0x14009bf1c  call    cs:__imp_GetLastError
0x14009bf22  mov     ebx, eax
0x14009bf24  test    eax, eax
0x14009bf26  jle     short loc_14009BF31
0x14009bf28  movzx   ebx, ax
0x14009bf2b  or      ebx, 80070000h
0x14009bf31  mov     rcx, cs:WPP_GLOBAL_Control
0x14009bf38  cmp     rcx, rsi
0x14009bf3b  jz      short loc_14009BF5B
0x14009bf3d  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
