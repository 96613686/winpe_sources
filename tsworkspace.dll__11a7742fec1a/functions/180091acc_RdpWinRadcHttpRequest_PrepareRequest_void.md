# RdpWinRadcHttpRequest::PrepareRequest(void)

- ea: `0x180091acc`
- end: `0x1800921d5`
- name: `?PrepareRequest@RdpWinRadcHttpRequest@@AEAAJXZ`
- size: `1801`
- prototype: `__int64 __fastcall(RdpWinRadcHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18008f830`

## callees

- `0x18000ec94`
- `0x18000ece0`
- `0x18001a008`
- `0x1800223b4`
- `0x180062a08`
- `0x180062a30`
- `0x18008fd1c`
- `0x1800903b0`
- `0x180091acc`
- `0x180092928`
- `0x180092cac`
- `0x180092eb4`
- `0x180093224`
- `0x180093e50`
- `0x1800941c4`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800921a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800921b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800921a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800921b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092165`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180091c8b`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180091c8b`
- `WINHTTP!WinHttpConnect` at `0x180091bfe`
- `WINHTTP!WinHttpConnect` at `0x180091bfe`
- `WINHTTP!WinHttpSetOption` at `0x18009215b`
- `WINHTTP!WinHttpSetOption` at `0x18009215b`
- `WINHTTP!WinHttpOpenRequest` at `0x180091f84`
- `WINHTTP!WinHttpOpenRequest` at `0x180091f84`

## string_xrefs

- `0x180091b10`: `application/xml`
- `0x180091b61`: `application/x-msts-radc+xml;radc_schema_version=2.0`
- `0x180091b6c`: `application/x-msts-radc-discovery+xml`
- `0x180091d19`: `GetProxyConfig failed`
- `0x180091bbc`: `StringCchCopyN(hostname) failed`
- `0x180091d86`: `bstrUrlPath.Append failed`
- `0x180091dde`: `bstrUrlPath.Append(empty string) failed`
- `0x180091efd`: `RadcCombineUrl failed`
- `0x180092052`: `SetClaimsTokenIfExists failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::PrepareRequest(RdpWinRadcHttpRequest *this)
{
  unsigned __int64 v1; // r9
  const unsigned __int16 *v2; // r8
  __int64 v4; // rcx
  signed int LastError; // ebx
  int ActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  void *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rdx
  int v20; // r8d
  __int64 v21; // rcx
  unsigned int v22; // r9d
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  int v26; // eax
  int v27; // r8d
  HINTERNET v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // ebx
  int v35; // eax
  __int64 v36; // rcx
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v40; // [rsp+48h] [rbp-B8h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h]
  LPCWSTR v43[7]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pwszObjectName[2088]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pswzServerName[2088]; // [rsp+10F0h] [rbp+FF0h] BYREF

  v1 = *((unsigned int *)this + 24);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 11);
  v42 = 0;
  v40 = 0;
  v43[0] = L"application/xml";
  bstrString = 0;
  v43[1] = L"Image/*";
  v43[6] = 0;
  v43[2] = L"Application/*";
  v43[3] = L"text/*";
  v43[4] = L"application/x-msts-radc+xml;radc_schema_version=2.0";
  v43[5] = L"application/x-msts-radc-discovery+xml";
  Buffer = 0;
  LastError = StringCchCopyNW(pswzServerName, 0x824u, v2, v1);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v4);
      v7 = 54;
      v8 = "StringCchCopyN(hostname) failed";
LABEL_6:
      LODWORD(ppwszAcceptTypes) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        ActivityIdPrefix,
        (__int64)v8,
        ppwszAcceptTypes);
      goto LABEL_97;
    }
    goto LABEL_97;
  }
  v9 = WinHttpConnect(*((HINTERNET *)this + 3), pswzServerName, *((_WORD *)this + 50), 0);
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = RdpX_GetActivityIdPrefix(v10);
    v12 = 55;
    goto LABEL_12;
  }
  if ( WinHttpSetStatusCallback(v9, RdpWinRadcHttpRequest::WinHttpCallbackFn, 0x4000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = RdpX_GetActivityIdPrefix(v13);
    v12 = 56;
    goto LABEL_12;
  }
  LastError = RdpWinRadcHttpRequest::GetProxyConfig(this, *((void **)this + 3), (struct _WINHTTP_PROXY_INFO *)&Buffer);
  if ( LastError >= 0 )
  {
    v15 = (const unsigned __int16 *)*((_QWORD *)this + 17);
    if ( v15 && (v16 = *((_DWORD *)this + 36)) != 0 )
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&v40, v15, v16);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v17);
          v7 = 59;
          v8 = "bstrUrlPath.Append failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    else
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&v40, &LocaleName);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v18);
          v7 = 58;
          v8 = "bstrUrlPath.Append(empty string) failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    v19 = (const unsigned __int16 *)*((_QWORD *)this + 19);
    if ( v19 && (v20 = *((_DWORD *)this + 40)) != 0 )
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v19, v20);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v21);
          v7 = 61;
          v8 = "bstrUrlExtraInfo.Append failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    else
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, &LocaleName);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v23);
          v7 = 60;
          v8 = "bstrUrlExtraInfo.Append(empty string) failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    LastError = RadcCombineUrl(v40, bstrString, pwszObjectName, v22);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(v24);
        v7 = 62;
        v8 = "RadcCombineUrl failed";
        goto LABEL_6;
      }
      goto LABEL_97;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v25 = *((_QWORD *)this + 2);
      v26 = RdpX_GetActivityIdPrefix(v24);
      WPP_SF_DIS(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v27, v26, v25, (__int64)pwszObjectName);
    }
    v28 = WinHttpOpenRequest(*((HINTERNET *)this + 4), *((LPCWSTR *)this + 6), pwszObjectName, 0, 0, v43, 0x800100u);
    *((_QWORD *)this + 5) = v28;
    if ( v28 )
    {
      LastError = RdpWinRadcHttpRequest::SetAuthCookieIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v30);
          v7 = 65;
          v8 = "SetAuthCookieIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetClaimsTokenIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v31);
          v7 = 66;
          v8 = "SetClaimsTokenIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetActivityIdIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v32);
          v7 = 67;
          v8 = "SetActivityIdIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetIfNoneMatchHeaderIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v33);
          v7 = 68;
          v8 = "SetIfNoneMatchHeaderIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      v34 = RdpWinRadcHttpRequest::GetAndSetClientVersionHeaders(this);
      if ( v34 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        LODWORD(ppwszAcceptTypes) = v34;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          v35,
          (__int64)"GetAndSetClientVersionHeaders failed",
          ppwszAcceptTypes);
      }
      if ( WinHttpSetOption(*((HINTERNET *)this + 5), 0x26u, &Buffer, 0x18u) )
      {
        LastError = 0;
        goto LABEL_97;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_13:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        goto LABEL_97;
      }
      v11 = RdpX_GetActivityIdPrefix(v36);
      v12 = 70;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v11 = RdpX_GetActivityIdPrefix(v29);
      v12 = 64;
    }
LABEL_12:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      v11,
      LastError);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v14);
    v7 = 57;
    v8 = "GetProxyConfig failed";
    goto LABEL_6;
  }
LABEL_97:
  SysFreeString(bstrString);
  SysFreeString(v40);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180091acc  push    rbp
0x180091ace  push    rbx
0x180091acf  push    rsi
0x180091ad0  push    rdi
0x180091ad1  lea     rbp, [rsp-2058h]
0x180091ad9  mov     eax, 2158h
0x180091ade  call    _alloca_probe
0x180091ae3  sub     rsp, rax
0x180091ae6  mov     rax, cs:__security_cookie
0x180091aed  xor     rax, rsp
0x180091af0  mov     [rbp+2070h+var_30], rax
0x180091af7  mov     r9d, [rcx+60h]; unsigned __int64
0x180091afb  xor     eax, eax
0x180091afd  mov     r8, [rcx+58h]; unsigned __int16 *
0x180091b01  mov     rsi, rcx
0x180091b04  mov     [rsp+2170h+var_2110], rax
0x180091b09  lea     rcx, [rbp+2070h+pswzServerName]; unsigned __int16 *
0x180091b10  lea     rax, aApplicationXml; "application/xml"
0x180091b17  mov     [rsp+2170h+var_2128], 0
0x180091b20  mov     [rsp+2170h+var_2108], rax
0x180091b25  xorps   xmm0, xmm0
0x180091b28  lea     rax, aImage; "Image/*"
0x180091b2f  mov     [rsp+2170h+bstrString], 0
0x180091b38  mov     [rsp+2170h+var_2100], rax
0x180091b3d  mov     edx, 824h; unsigned __int64
0x180091b42  lea     rax, aApplication; "Application/*"
0x180091b49  mov     [rbp+2070h+var_20D8], 0
0x180091b51  mov     [rsp+2170h+var_20F8], rax
0x180091b56  lea     rax, aText; "text/*"
0x180091b5d  mov     [rbp+2070h+var_20F0], rax
0x180091b61  lea     rax, aApplicationXMs; "application/x-msts-radc+xml;radc_schema"...
0x180091b68  mov     [rbp+2070h+var_20E8], rax
0x180091b6c  lea     rax, aApplicationXMs_0; "application/x-msts-radc-discovery+xml"
0x180091b73  mov     [rbp+2070h+var_20E0], rax
0x180091b77  movups  [rsp+2170h+Buffer], xmm0
0x180091b7c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180091b81  mov     ebx, eax
0x180091b83  test    eax, eax
0x180091b85  jns     short loc_180091BEB
0x180091b87  mov     rax, cs:WPP_GLOBAL_Control
0x180091b8e  lea     rdi, WPP_GLOBAL_Control
0x180091b95  cmp     rax, rdi
0x180091b98  jz      loc_1800921A2
0x180091b9e  test    byte ptr [rax+1Ch], 8
0x180091ba2  jz      loc_1800921A2
0x180091ba8  cmp     byte ptr [rax+19h], 2
0x180091bac  jb      loc_1800921A2
0x180091bb2  call    RdpX_GetActivityIdPrefix
0x180091bb7  mov     edx, 36h ; '6'
0x180091bbc  lea     rcx, aStringcchcopyn_1; "StringCchCopyN(hostname) failed"
0x180091bc3  mov     dword ptr [rsp+2170h+ppwszAcceptTypes], ebx
0x180091bc7  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180091bce  mov     [rsp+2170h+pwszReferrer], rcx
0x180091bd3  mov     r9d, eax
0x180091bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180091bdd  mov     rcx, [rcx+10h]
0x180091be1  call    WPP_SF_DsD
0x180091be6  jmp     loc_1800921A2
0x180091beb  movzx   r8d, word ptr [rsi+64h]; nServerPort
0x180091bf0  lea     rdx, [rbp+2070h+pswzServerName]; pswzServerName
0x180091bf7  mov     rcx, [rsi+18h]; hSession
0x180091bfb  xor     r9d, r9d; dwReserved
0x180091bfe  call    cs:__imp_WinHttpConnect
0x180091c04  mov     [rsi+20h], rax
0x180091c08  test    rax, rax
0x180091c0b  jnz     short loc_180091C78
0x180091c0d  call    cs:__imp_GetLastError
0x180091c13  mov     ebx, eax
0x180091c15  mov     rax, cs:WPP_GLOBAL_Control
0x180091c1c  lea     rdi, WPP_GLOBAL_Control
0x180091c23  cmp     rax, rdi
0x180091c26  jz      short loc_180091C5C
0x180091c28  test    byte ptr [rax+1Ch], 8
0x180091c2c  jz      short loc_180091C5C
0x180091c2e  cmp     byte ptr [rax+19h], 2
0x180091c32  jb      short loc_180091C5C
0x180091c34  call    RdpX_GetActivityIdPrefix
0x180091c39  mov     edx, 37h ; '7'
0x180091c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180091c45  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180091c4c  mov     r9d, eax
0x180091c4f  mov     dword ptr [rsp+2170h+pwszReferrer], ebx
0x180091c53  mov     rcx, [rcx+10h]
0x180091c57  call    WPP_SF_Dd
0x180091c5c  test    ebx, ebx
0x180091c5e  jle     short loc_180091C69
0x180091c60  movzx   ebx, bx
0x180091c63  or      ebx, 80070000h
0x180091c69  test    ebx, ebx
0x180091c6b  mov     eax, 80004005h
0x180091c70  cmovns  ebx, eax
0x180091c73  jmp     loc_1800921A2
0x180091c78  xor     r9d, r9d; dwReserved
0x180091c7b  lea     rdx, ?WinHttpCallbackFn@RdpWinRadcHttpRequest@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x180091c82  mov     r8d, 4000h; dwNotificationFlags
0x180091c88  mov     rcx, rax; hInternet
0x180091c8b  call    cs:__imp_WinHttpSetStatusCallback
0x180091c91  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180091c95  jnz     short loc_180091CCD
0x180091c97  call    cs:__imp_GetLastError
0x180091c9d  mov     ebx, eax
0x180091c9f  mov     rax, cs:WPP_GLOBAL_Control
0x180091ca6  lea     rdi, WPP_GLOBAL_Control
0x180091cad  cmp     rax, rdi
0x180091cb0  jz      short loc_180091C5C
0x180091cb2  test    byte ptr [rax+1Ch], 8
0x180091cb6  jz      short loc_180091C5C
0x180091cb8  cmp     byte ptr [rax+19h], 2
0x180091cbc  jb      short loc_180091C5C
0x180091cbe  call    RdpX_GetActivityIdPrefix
0x180091cc3  mov     edx, 38h ; '8'
0x180091cc8  jmp     loc_180091C3E
0x180091ccd  mov     rdx, [rsi+18h]; void *
0x180091cd1  lea     r8, [rsp+2170h+Buffer]; struct _WINHTTP_PROXY_INFO *
0x180091cd6  mov     rcx, rsi; this
0x180091cd9  call    ?GetProxyConfig@RdpWinRadcHttpRequest@@AEAAJPEAXPEAU_WINHTTP_PROXY_INFO@@@Z; RdpWinRadcHttpRequest::GetProxyConfig(void *,_WINHTTP_PROXY_INFO *)
0x180091cde  mov     ebx, eax
0x180091ce0  test    eax, eax
0x180091ce2  jns     short loc_180091D25
0x180091ce4  mov     rax, cs:WPP_GLOBAL_Control
0x180091ceb  lea     rdi, WPP_GLOBAL_Control
0x180091cf2  cmp     rax, rdi
0x180091cf5  jz      loc_1800921A2
0x180091cfb  test    byte ptr [rax+1Ch], 8
0x180091cff  jz      loc_1800921A2
0x180091d05  cmp     byte ptr [rax+19h], 2
0x180091d09  jb      loc_1800921A2
0x180091d0f  call    RdpX_GetActivityIdPrefix
0x180091d14  mov     edx, 39h ; '9'
0x180091d19  lea     rcx, aGetproxyconfig; "GetProxyConfig failed"
0x180091d20  jmp     loc_180091BC3
0x180091d25  mov     rdx, [rsi+88h]; unsigned __int16 *
0x180091d2c  test    rdx, rdx
0x180091d2f  jz      short loc_180091D92
0x180091d31  mov     r8d, [rsi+90h]; int
0x180091d38  test    r8d, r8d
0x180091d3b  jz      short loc_180091D92
0x180091d3d  lea     rcx, [rsp+2170h+var_2128]; this
0x180091d42  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180091d47  mov     ebx, eax
0x180091d49  test    eax, eax
0x180091d4b  jns     loc_180091DEA
0x180091d51  mov     rax, cs:WPP_GLOBAL_Control
0x180091d58  lea     rdi, WPP_GLOBAL_Control
0x180091d5f  cmp     rax, rdi
0x180091d62  jz      loc_1800921A2
0x180091d68  test    byte ptr [rax+1Ch], 8
0x180091d6c  jz      loc_1800921A2
0x180091d72  cmp     byte ptr [rax+19h], 2
0x180091d76  jb      loc_1800921A2
0x180091d7c  call    RdpX_GetActivityIdPrefix
0x180091d81  mov     edx, 3Bh ; ';'
0x180091d86  lea     rcx, aBstrurlpathApp; "bstrUrlPath.Append failed"
0x180091d8d  jmp     loc_180091BC3
0x180091d92  lea     rdx, LocaleName; unsigned __int16 *
0x180091d99  lea     rcx, [rsp+2170h+var_2128]; this
0x180091d9e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180091da3  mov     ebx, eax
0x180091da5  test    eax, eax
0x180091da7  jns     short loc_180091DEA
0x180091da9  mov     rax, cs:WPP_GLOBAL_Control
0x180091db0  lea     rdi, WPP_GLOBAL_Control
0x180091db7  cmp     rax, rdi
0x180091dba  jz      loc_1800921A2
0x180091dc0  test    byte ptr [rax+1Ch], 8
0x180091dc4  jz      loc_1800921A2
0x180091dca  cmp     byte ptr [rax+19h], 2
0x180091dce  jb      loc_1800921A2
0x180091dd4  call    RdpX_GetActivityIdPrefix
0x180091dd9  mov     edx, 3Ah ; ':'
0x180091dde  lea     rcx, aBstrurlpathApp_0; "bstrUrlPath.Append(empty string) failed"
0x180091de5  jmp     loc_180091BC3
0x180091dea  mov     rdx, [rsi+98h]; unsigned __int16 *
0x180091df1  test    rdx, rdx
0x180091df4  jz      short loc_180091E57
0x180091df6  mov     r8d, [rsi+0A0h]; int
0x180091dfd  test    r8d, r8d
0x180091e00  jz      short loc_180091E57
0x180091e02  lea     rcx, [rsp+2170h+bstrString]; this
0x180091e07  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180091e0c  mov     ebx, eax
0x180091e0e  test    eax, eax
0x180091e10  jns     loc_180091EAF
0x180091e16  mov     rax, cs:WPP_GLOBAL_Control
0x180091e1d  lea     rdi, WPP_GLOBAL_Control
0x180091e24  cmp     rax, rdi
0x180091e27  jz      loc_1800921A2
0x180091e2d  test    byte ptr [rax+1Ch], 8
0x180091e31  jz      loc_1800921A2
0x180091e37  cmp     byte ptr [rax+19h], 2
0x180091e3b  jb      loc_1800921A2
0x180091e41  call    RdpX_GetActivityIdPrefix
0x180091e46  mov     edx, 3Dh ; '='
0x180091e4b  lea     rcx, aBstrurlextrain; "bstrUrlExtraInfo.Append failed"
0x180091e52  jmp     loc_180091BC3
0x180091e57  lea     rdx, LocaleName; unsigned __int16 *
0x180091e5e  lea     rcx, [rsp+2170h+bstrString]; this
0x180091e63  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180091e68  mov     ebx, eax
0x180091e6a  test    eax, eax
0x180091e6c  jns     short loc_180091EAF
0x180091e6e  mov     rax, cs:WPP_GLOBAL_Control
0x180091e75  lea     rdi, WPP_GLOBAL_Control
0x180091e7c  cmp     rax, rdi
0x180091e7f  jz      loc_1800921A2
0x180091e85  test    byte ptr [rax+1Ch], 8
0x180091e89  jz      loc_1800921A2
0x180091e8f  cmp     byte ptr [rax+19h], 2
0x180091e93  jb      loc_1800921A2
0x180091e99  call    RdpX_GetActivityIdPrefix
0x180091e9e  mov     edx, 3Ch ; '<'
0x180091ea3  lea     rcx, aBstrurlextrain_0; "bstrUrlExtraInfo.Append(empty string) f"...
0x180091eaa  jmp     loc_180091BC3
0x180091eaf  mov     rdx, [rsp+2170h+bstrString]; unsigned __int16 *
0x180091eb4  lea     r8, [rbp+2070h+pwszObjectName]; unsigned __int16 *
0x180091eb8  mov     rcx, [rsp+2170h+var_2128]; unsigned __int16 *
0x180091ebd  call    ?RadcCombineUrl@@YAJPEBG0PEAGK@Z; RadcCombineUrl(ushort const *,ushort const *,ushort *,ulong)
0x180091ec2  mov     ebx, eax
0x180091ec4  test    eax, eax
0x180091ec6  jns     short loc_180091F09
0x180091ec8  mov     rax, cs:WPP_GLOBAL_Control
0x180091ecf  lea     rdi, WPP_GLOBAL_Control
0x180091ed6  cmp     rax, rdi
0x180091ed9  jz      loc_1800921A2
0x180091edf  test    byte ptr [rax+1Ch], 8
0x180091ee3  jz      loc_1800921A2
0x180091ee9  cmp     byte ptr [rax+19h], 2
0x180091eed  jb      loc_1800921A2
0x180091ef3  call    RdpX_GetActivityIdPrefix
0x180091ef8  mov     edx, 3Eh ; '>'
0x180091efd  lea     rcx, aRadccombineurl; "RadcCombineUrl failed"
0x180091f04  jmp     loc_180091BC3
0x180091f09  mov     rax, cs:WPP_GLOBAL_Control
0x180091f10  lea     rdi, WPP_GLOBAL_Control
0x180091f17  cmp     rax, rdi
0x180091f1a  jz      short loc_180091F5A
0x180091f1c  test    dword ptr [rax+1Ch], 10000h
0x180091f23  jz      short loc_180091F5A
0x180091f25  cmp     byte ptr [rax+19h], 5
0x180091f29  jb      short loc_180091F5A
0x180091f2b  mov     rbx, [rsi+10h]
0x180091f2f  call    RdpX_GetActivityIdPrefix
0x180091f34  lea     rcx, [rbp+2070h+pwszObjectName]
0x180091f38  mov     edx, 3Fh ; '?'
0x180091f3d  mov     [rsp+2170h+ppwszAcceptTypes], rcx
0x180091f42  mov     r9d, eax
0x180091f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180091f4c  mov     [rsp+2170h+pwszReferrer], rbx
0x180091f51  mov     rcx, [rcx+10h]
0x180091f55  call    WPP_SF_DIS
0x180091f5a  mov     rdx, [rsi+30h]; pwszVerb
0x180091f5e  lea     rax, [rsp+2170h+var_2108]
0x180091f63  mov     rcx, [rsi+20h]; hConnect
0x180091f67  lea     r8, [rbp+2070h+pwszObjectName]; pwszObjectName
0x180091f6b  mov     [rsp+2170h+dwFlags], 800100h; dwFlags
0x180091f73  xor     r9d, r9d; pwszVersion
0x180091f76  mov     [rsp+2170h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x180091f7b  mov     [rsp+2170h+pwszReferrer], 0; pwszReferrer
0x180091f84  call    cs:__imp_WinHttpOpenRequest
0x180091f8a  mov     [rsi+28h], rax
0x180091f8e  test    rax, rax
0x180091f91  jnz     short loc_180091FCE
0x180091f93  call    cs:__imp_GetLastError
0x180091f99  mov     ebx, eax
0x180091f9b  mov     rax, cs:WPP_GLOBAL_Control
0x180091fa2  cmp     rax, rdi
0x180091fa5  jz      loc_180091C5C
0x180091fab  test    byte ptr [rax+1Ch], 8
0x180091faf  jz      loc_180091C5C
0x180091fb5  cmp     byte ptr [rax+19h], 2
0x180091fb9  jb      loc_180091C5C
0x180091fbf  call    RdpX_GetActivityIdPrefix
0x180091fc4  mov     edx, 40h ; '@'
0x180091fc9  jmp     loc_180091C3E
0x180091fce  mov     rcx, rsi; this
0x180091fd1  call    ?SetAuthCookieIfExists@RdpWinRadcHttpRequest@@AEAAJXZ; RdpWinRadcHttpRequest::SetAuthCookieIfExists(void)
0x180091fd6  mov     ebx, eax
0x180091fd8  test    eax, eax
0x180091fda  jns     short loc_180092016
0x180091fdc  mov     rax, cs:WPP_GLOBAL_Control
0x180091fe3  cmp     rax, rdi
0x180091fe6  jz      loc_1800921A2
0x180091fec  test    byte ptr [rax+1Ch], 8
0x180091ff0  jz      loc_1800921A2
0x180091ff6  cmp     byte ptr [rax+19h], 2
0x180091ffa  jb      loc_1800921A2
0x180092000  call    RdpX_GetActivityIdPrefix
0x180092005  mov     edx, 41h ; 'A'
0x18009200a  lea     rcx, aSetauthcookiei; "SetAuthCookieIfExists failed"
0x180092011  jmp     loc_180091BC3
0x180092016  mov     rcx, rsi; this
0x180092019  call    ?SetClaimsTokenIfExists@RdpWinRadcHttpRequest@@AEAAJXZ; RdpWinRadcHttpRequest::SetClaimsTokenIfExists(void)
0x18009201e  mov     ebx, eax
0x180092020  test    eax, eax
0x180092022  jns     short loc_18009205E
0x180092024  mov     rax, cs:WPP_GLOBAL_Control
0x18009202b  cmp     rax, rdi
0x18009202e  jz      loc_1800921A2
0x180092034  test    byte ptr [rax+1Ch], 8
0x180092038  jz      loc_1800921A2
  ... truncated ...
```
