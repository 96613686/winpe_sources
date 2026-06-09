# CHttpConnector::BuildProxyLists(ushort const *)

- ea: `0x18000b9f0`
- end: `0x18000be97`
- name: `?BuildProxyLists@CHttpConnector@@AEAAJPEBG@Z`
- size: `1191`
- prototype: `__int64 __fastcall(struct _PROXY_LIST **this, LPCWSTR lpcwszUrl)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c2a0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000b890`
- `0x18000b9f0`
- `0x18000bea0`
- `0x18000c1d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000baf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000baf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc53`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000bbae`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000bbae`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18000bb45`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18000bb45`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000bc46`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000bc46`

## pseudocode

```c
__int64 __fastcall CHttpConnector::BuildProxyLists(struct _PROXY_LIST **this, LPCWSTR lpcwszUrl)
{
  struct _PROXY_LIST **v3; // rdi
  signed int v4; // ebx
  struct _PROXY_LIST **v5; // rsi
  CHttpConnector *v6; // rcx
  struct _PROXY_LIST *v7; // rbx
  HANDLE v8; // rax
  struct _PROXY_LIST **v9; // r15
  CHttpConnector *v10; // rcx
  struct _PROXY_LIST *v11; // rbx
  HANDLE v12; // rax
  struct _PROXY_LIST **v13; // r14
  CHttpConnector *v14; // rcx
  struct _PROXY_LIST *v15; // rbx
  HANDLE v16; // rax
  signed int LastError; // eax
  bool v18; // sf
  signed int v19; // eax
  bool v20; // sf
  int v21; // esi
  DWORD dwFlags; // eax
  struct _PROXY_LIST *v23; // rcx
  BOOL ProxyForUrl; // r12d
  signed int v25; // eax
  int v26; // eax
  CHttpConnector *v27; // rcx
  struct _PROXY_LIST *v28; // rsi
  HANDLE ProcessHeap; // rax
  CHttpConnector *v30; // rcx
  struct _PROXY_LIST *v31; // rsi
  HANDLE v32; // rax
  CHttpConnector *v33; // rcx
  struct _PROXY_LIST *v34; // rsi
  HANDLE v35; // rax
  HANDLE v36; // rax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-59h] BYREF
  WINHTTP_PROXY_INFO v39; // [rsp+48h] [rbp-41h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+60h] [rbp-29h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+80h] [rbp-9h] BYREF

  v3 = this;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  memset(&v39, 0, sizeof(v39));
  if ( !lpcwszUrl )
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CHttpConnector::BuildProxyLists",
        -2147024809,
        (__int64)"Url");
LABEL_66:
    CHttpConnector::CloseProxyList((CHttpConnector *)this, v3[3]);
    v28 = v3[3];
    if ( v28 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v28);
      v3[3] = 0;
    }
    CHttpConnector::CloseProxyList(v27, v3[4]);
    v31 = v3[4];
    if ( v31 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
      v3[4] = 0;
    }
    CHttpConnector::CloseProxyList(v30, v3[5]);
    v34 = v3[5];
    if ( v34 )
    {
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v34);
      v3[5] = 0;
    }
    CHttpConnector::CloseProxyList(v33, v3[6]);
    goto LABEL_73;
  }
  if ( !*this )
  {
    v4 = -2147019873;
    goto LABEL_56;
  }
  v5 = this + 3;
  *((_DWORD *)this + 14) = 1;
  CHttpConnector::CloseProxyList((CHttpConnector *)this, this[3]);
  v7 = *v5;
  if ( *v5 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
    *v5 = 0;
  }
  v9 = v3 + 5;
  CHttpConnector::CloseProxyList(v6, v3[5]);
  v11 = v3[5];
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
    *v9 = 0;
  }
  v13 = v3 + 4;
  CHttpConnector::CloseProxyList(v10, v3[4]);
  v15 = v3[4];
  if ( v15 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    *v13 = 0;
  }
  v4 = CHttpConnector::InitializeProxyList(v14, v5);
  if ( v4 < 0 )
    goto LABEL_53;
  v4 = CHttpConnector::InitializeProxyList((CHttpConnector *)this, v3 + 5);
  if ( v4 < 0 )
    goto LABEL_53;
  v4 = CHttpConnector::InitializeProxyList((CHttpConnector *)this, v3 + 4);
  if ( v4 < 0 )
    goto LABEL_53;
  if ( WinHttpGetDefaultProxyConfiguration(&pProxyInfo) )
    goto LABEL_78;
  LastError = GetLastError();
  v18 = LastError < 0;
  if ( LastError > 0 )
    v18 = 1;
  if ( !v18 )
  {
LABEL_78:
    *((_DWORD *)*v5 + 7) = pProxyInfo.dwAccessType;
    *((_QWORD *)*v5 + 4) = pProxyInfo.lpszProxy;
    *((_QWORD *)*v5 + 5) = pProxyInfo.lpszProxyBypass;
    v4 = CHttpConnector::AddProxyServers(
           (CHttpConnector *)v3,
           *v5,
           pProxyInfo.dwAccessType,
           pProxyInfo.lpszProxy,
           pProxyInfo.lpszProxyBypass);
    if ( v4 < 0 )
      goto LABEL_53;
  }
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    goto LABEL_25;
  v19 = GetLastError();
  v20 = v19 < 0;
  if ( v19 > 0 )
    v20 = 1;
  if ( !v20 )
  {
LABEL_25:
    v21 = 0;
    *((_DWORD *)*v13 + 7) = 3;
    *((_QWORD *)*v13 + 4) = pProxyConfig.lpszProxy;
    *((_QWORD *)*v13 + 5) = pProxyConfig.lpszProxyBypass;
    if ( pProxyConfig.fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      v21 = 1;
    }
    else
    {
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( !pProxyConfig.lpszAutoConfigUrl )
      goto LABEL_31;
    pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    pAutoProxyOptions.dwFlags = dwFlags | 2;
  }
  else
  {
    pAutoProxyOptions.dwAutoDetectFlags = 3;
    pAutoProxyOptions.dwFlags = 1;
  }
  v21 = 1;
LABEL_31:
  v23 = *v3;
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  ProxyForUrl = WinHttpGetProxyForUrl(v23, lpcwszUrl, &pAutoProxyOptions, &v39);
  if ( !ProxyForUrl )
  {
    v25 = GetLastError();
    v4 = v25;
    if ( v25 > 0 )
      v4 = (unsigned __int16)v25 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_79;
  }
  *((_DWORD *)*v9 + 7) = v39.dwAccessType;
  *((_QWORD *)*v9 + 4) = v39.lpszProxy;
  *((_QWORD *)*v9 + 5) = v39.lpszProxyBypass;
  v4 = CHttpConnector::AddProxyServers((CHttpConnector *)v3, *v9, v39.dwAccessType, v39.lpszProxy, v39.lpszProxyBypass);
  if ( v4 >= 0 )
  {
LABEL_79:
    if ( v4 == -2147012894 && v21 )
      goto LABEL_56;
    v4 = 0;
    if ( v21 )
    {
      if ( ProxyForUrl )
        goto LABEL_80;
    }
    this = (struct _PROXY_LIST **)pProxyConfig.lpszProxy;
    if ( !pProxyConfig.lpszProxy )
      goto LABEL_80;
    if ( !*pProxyConfig.lpszProxy || *pProxyConfig.lpszProxy == 58 && !pProxyConfig.lpszProxy[1] )
    {
LABEL_60:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::BuildProxyLists");
      goto LABEL_73;
    }
    v26 = pProxyConfig.lpszProxyBypass
       && *pProxyConfig.lpszProxyBypass
       && (*pProxyConfig.lpszProxyBypass != 58 || pProxyConfig.lpszProxyBypass[1])
        ? CHttpConnector::AddProxyServers(
            (CHttpConnector *)v3,
            *v13,
            *((_DWORD *)*v13 + 7),
            *((unsigned __int16 **)*v13 + 4),
            *((unsigned __int16 **)*v13 + 5))
        : CHttpConnector::AddProxyServers(
            (CHttpConnector *)v3,
            *v13,
            *((_DWORD *)*v13 + 7),
            *((unsigned __int16 **)*v13 + 4),
            0);
    v4 = v26;
    if ( v26 >= 0 )
    {
LABEL_80:
      if ( *((_DWORD *)v3 + 14) )
        CHttpConnector::CloseProxyList((CHttpConnector *)this, v3[6]);
    }
  }
LABEL_53:
  switch ( v4 )
  {
    case -2147024882:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CHttpConnector::BuildProxyLists");
      goto LABEL_66;
    case -2147024809:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(this, lpcwszUrl, "CHttpConnector::BuildProxyLists", 2147942487LL);
      goto LABEL_66;
    case 0:
      goto LABEL_60;
  }
LABEL_56:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(this, lpcwszUrl, "CHttpConnector::BuildProxyLists", (unsigned int)v4);
  if ( v4 < 0 )
    goto LABEL_66;
LABEL_73:
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, pProxyConfig.lpszAutoConfigUrl);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b9f0  push    rbp
0x18000b9f2  push    rbx
0x18000b9f3  push    rsi
0x18000b9f4  push    rdi
0x18000b9f5  push    r12
0x18000b9f7  push    r13
0x18000b9f9  push    r14
0x18000b9fb  push    r15
0x18000b9fd  lea     rbp, [rsp-1Fh]
0x18000ba02  sub     rsp, 0A8h
0x18000ba09  xor     eax, eax
0x18000ba0b  xorps   xmm0, xmm0
0x18000ba0e  xorps   xmm1, xmm1
0x18000ba11  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x18000ba15  xor     r13d, r13d
0x18000ba18  mov     [rbp+57h+var_98.lpszProxyBypass], rax
0x18000ba1c  mov     r12, rdx
0x18000ba1f  mov     rdi, rcx
0x18000ba22  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.dwFlags], xmm0
0x18000ba26  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.lpvReserved], xmm0
0x18000ba2a  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm1
0x18000ba2e  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm1
0x18000ba32  movups  xmmword ptr [rbp+57h+pProxyInfo.dwAccessType], xmm0
0x18000ba36  movups  xmmword ptr [rbp+57h+var_98.dwAccessType], xmm1
0x18000ba3a  test    rdx, rdx
0x18000ba3d  jnz     short loc_18000BA74
0x18000ba3f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000ba46  mov     ebx, 80070057h
0x18000ba4b  jz      loc_18000BDDF
0x18000ba51  lea     rax, aUrl; "Url"
0x18000ba58  mov     r9d, 80070057h
0x18000ba5e  lea     r8, aChttpconnector_5; "CHttpConnector::BuildProxyLists"
0x18000ba65  mov     [rsp+0E0h+var_C0], rax
0x18000ba6a  call    McTemplateU0sqs_EventWriteTransfer
0x18000ba6f  jmp     loc_18000BDDF
0x18000ba74  cmp     [rcx], r13
0x18000ba77  jnz     short loc_18000BA83
0x18000ba79  mov     ebx, 8007139Fh
0x18000ba7e  jmp     loc_18000BD5F
0x18000ba83  lea     rsi, [rcx+18h]
0x18000ba87  mov     dword ptr [rcx+38h], 1
0x18000ba8e  mov     rdx, [rsi]; struct _PROXY_LIST *
0x18000ba91  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000ba96  mov     rbx, [rsi]
0x18000ba99  test    rbx, rbx
0x18000ba9c  jz      short loc_18000BAB5
0x18000ba9e  call    cs:__imp_GetProcessHeap
0x18000baa4  mov     r8, rbx; lpMem
0x18000baa7  xor     edx, edx; dwFlags
0x18000baa9  mov     rcx, rax; hHeap
0x18000baac  call    cs:__imp_HeapFree
0x18000bab2  mov     [rsi], r13
0x18000bab5  lea     r15, [rdi+28h]
0x18000bab9  mov     rdx, [r15]; struct _PROXY_LIST *
0x18000babc  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000bac1  mov     rbx, [r15]
0x18000bac4  test    rbx, rbx
0x18000bac7  jz      short loc_18000BAE0
0x18000bac9  call    cs:__imp_GetProcessHeap
0x18000bacf  mov     r8, rbx; lpMem
0x18000bad2  xor     edx, edx; dwFlags
0x18000bad4  mov     rcx, rax; hHeap
0x18000bad7  call    cs:__imp_HeapFree
0x18000badd  mov     [r15], r13
0x18000bae0  lea     r14, [rdi+20h]
0x18000bae4  mov     rdx, [r14]; struct _PROXY_LIST *
0x18000bae7  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000baec  mov     rbx, [r14]
0x18000baef  test    rbx, rbx
0x18000baf2  jz      short loc_18000BB0B
0x18000baf4  call    cs:__imp_GetProcessHeap
0x18000bafa  mov     r8, rbx; lpMem
0x18000bafd  xor     edx, edx; dwFlags
0x18000baff  mov     rcx, rax; hHeap
0x18000bb02  call    cs:__imp_HeapFree
0x18000bb08  mov     [r14], r13
0x18000bb0b  mov     rdx, rsi; struct _PROXY_LIST **
0x18000bb0e  call    ?InitializeProxyList@CHttpConnector@@AEAAJPEAPEAU_PROXY_LIST@@@Z; CHttpConnector::InitializeProxyList(_PROXY_LIST * *)
0x18000bb13  mov     ebx, eax
0x18000bb15  test    eax, eax
0x18000bb17  js      loc_18000BD4B
0x18000bb1d  mov     rdx, r15; struct _PROXY_LIST **
0x18000bb20  call    ?InitializeProxyList@CHttpConnector@@AEAAJPEAPEAU_PROXY_LIST@@@Z; CHttpConnector::InitializeProxyList(_PROXY_LIST * *)
0x18000bb25  mov     ebx, eax
0x18000bb27  test    eax, eax
0x18000bb29  js      loc_18000BD4B
0x18000bb2f  mov     rdx, r14; struct _PROXY_LIST **
0x18000bb32  call    ?InitializeProxyList@CHttpConnector@@AEAAJPEAPEAU_PROXY_LIST@@@Z; CHttpConnector::InitializeProxyList(_PROXY_LIST * *)
0x18000bb37  mov     ebx, eax
0x18000bb39  test    eax, eax
0x18000bb3b  js      loc_18000BD4B
0x18000bb41  lea     rcx, [rbp+57h+pProxyInfo]; pProxyInfo
0x18000bb45  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18000bb4b  test    eax, eax
0x18000bb4d  jnz     short loc_18000BB65
0x18000bb4f  call    cs:__imp_GetLastError
0x18000bb55  test    eax, eax
0x18000bb57  jle     short loc_18000BB63
0x18000bb59  movzx   eax, ax
0x18000bb5c  or      eax, 80070000h
0x18000bb61  test    eax, eax
0x18000bb63  js      short loc_18000BBAA
0x18000bb65  mov     rcx, [rsi]
0x18000bb68  mov     eax, [rbp+57h+pProxyInfo.dwAccessType]
0x18000bb6b  mov     [rcx+1Ch], eax
0x18000bb6e  mov     rcx, [rsi]
0x18000bb71  mov     rax, [rbp+57h+pProxyInfo.lpszProxy]
0x18000bb75  mov     [rcx+20h], rax
0x18000bb79  mov     rcx, [rsi]
0x18000bb7c  mov     rax, [rbp+57h+pProxyInfo.lpszProxyBypass]
0x18000bb80  mov     [rcx+28h], rax
0x18000bb84  mov     rcx, rdi; this
0x18000bb87  mov     rax, [rbp+57h+pProxyInfo.lpszProxyBypass]
0x18000bb8b  mov     r9, [rbp+57h+pProxyInfo.lpszProxy]; unsigned __int16 *
0x18000bb8f  mov     r8d, [rbp+57h+pProxyInfo.dwAccessType]; unsigned int
0x18000bb93  mov     rdx, [rsi]; struct _PROXY_LIST *
0x18000bb96  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18000bb9b  call    ?AddProxyServers@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@KPEAG1@Z; CHttpConnector::AddProxyServers(_PROXY_LIST *,ulong,ushort *,ushort *)
0x18000bba0  mov     ebx, eax
0x18000bba2  test    eax, eax
0x18000bba4  js      loc_18000BD4B
0x18000bbaa  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x18000bbae  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18000bbb4  test    eax, eax
0x18000bbb6  jnz     short loc_18000BBDF
0x18000bbb8  call    cs:__imp_GetLastError
0x18000bbbe  test    eax, eax
0x18000bbc0  jle     short loc_18000BBCC
0x18000bbc2  movzx   eax, ax
0x18000bbc5  or      eax, 80070000h
0x18000bbca  test    eax, eax
0x18000bbcc  jns     short loc_18000BBDF
0x18000bbce  mov     ebx, 1
0x18000bbd3  mov     [rbp+57h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18000bbda  mov     [rbp+57h+pAutoProxyOptions.dwFlags], ebx
0x18000bbdd  jmp     short loc_18000BC33
0x18000bbdf  mov     rax, [r14]
0x18000bbe2  mov     esi, r13d
0x18000bbe5  mov     ebx, 1
0x18000bbea  mov     dword ptr [rax+1Ch], 3
0x18000bbf1  mov     rcx, [r14]
0x18000bbf4  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x18000bbf8  mov     [rcx+20h], rax
0x18000bbfc  mov     rcx, [r14]
0x18000bbff  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x18000bc03  mov     [rcx+28h], rax
0x18000bc07  cmp     [rbp+57h+pProxyConfig.fAutoDetect], r13d
0x18000bc0b  jz      short loc_18000BC1D
0x18000bc0d  mov     eax, ebx
0x18000bc0f  mov     [rbp+57h+pAutoProxyOptions.dwFlags], ebx
0x18000bc12  mov     [rbp+57h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18000bc19  mov     esi, ebx
0x18000bc1b  jmp     short loc_18000BC20
0x18000bc1d  mov     eax, [rbp+57h+pAutoProxyOptions.dwFlags]
0x18000bc20  mov     rcx, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x18000bc24  test    rcx, rcx
0x18000bc27  jz      short loc_18000BC35
0x18000bc29  or      eax, 2
0x18000bc2c  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x18000bc30  mov     [rbp+57h+pAutoProxyOptions.dwFlags], eax
0x18000bc33  mov     esi, ebx
0x18000bc35  mov     rcx, [rdi]; hSession
0x18000bc38  lea     r9, [rbp+57h+var_98]; pProxyInfo
0x18000bc3c  lea     r8, [rbp+57h+pAutoProxyOptions]; pAutoProxyOptions
0x18000bc40  mov     [rbp+57h+pAutoProxyOptions.fAutoLogonIfChallenged], ebx
0x18000bc43  mov     rdx, r12; lpcwszUrl
0x18000bc46  call    cs:__imp_WinHttpGetProxyForUrl
0x18000bc4c  mov     r12d, eax
0x18000bc4f  test    eax, eax
0x18000bc51  jnz     short loc_18000BC6C
0x18000bc53  call    cs:__imp_GetLastError
0x18000bc59  mov     ebx, eax
0x18000bc5b  test    eax, eax
0x18000bc5d  jle     short loc_18000BC68
0x18000bc5f  movzx   ebx, ax
0x18000bc62  or      ebx, 80070000h
0x18000bc68  test    ebx, ebx
0x18000bc6a  js      short loc_18000BCB1
0x18000bc6c  mov     rcx, [r15]
0x18000bc6f  mov     eax, [rbp+57h+var_98.dwAccessType]
0x18000bc72  mov     [rcx+1Ch], eax
0x18000bc75  mov     rcx, [r15]
0x18000bc78  mov     rax, [rbp+57h+var_98.lpszProxy]
0x18000bc7c  mov     [rcx+20h], rax
0x18000bc80  mov     rcx, [r15]
0x18000bc83  mov     rax, [rbp+57h+var_98.lpszProxyBypass]
0x18000bc87  mov     [rcx+28h], rax
0x18000bc8b  mov     rcx, rdi; this
0x18000bc8e  mov     rax, [rbp+57h+var_98.lpszProxyBypass]
0x18000bc92  mov     r9, [rbp+57h+var_98.lpszProxy]; unsigned __int16 *
0x18000bc96  mov     r8d, [rbp+57h+var_98.dwAccessType]; unsigned int
0x18000bc9a  mov     rdx, [r15]; struct _PROXY_LIST *
0x18000bc9d  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18000bca2  call    ?AddProxyServers@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@KPEAG1@Z; CHttpConnector::AddProxyServers(_PROXY_LIST *,ulong,ushort *,ushort *)
0x18000bca7  mov     ebx, eax
0x18000bca9  test    eax, eax
0x18000bcab  js      loc_18000BD4B
0x18000bcb1  cmp     ebx, 80072EE2h
0x18000bcb7  jnz     short loc_18000BCC1
0x18000bcb9  test    esi, esi
0x18000bcbb  jnz     loc_18000BD5F
0x18000bcc1  mov     ebx, r13d
0x18000bcc4  test    esi, esi
0x18000bcc6  jz      short loc_18000BCCD
0x18000bcc8  test    r12d, r12d
0x18000bccb  jnz     short loc_18000BD3C
0x18000bccd  mov     rcx, [rbp+57h+pProxyConfig.lpszProxy]
0x18000bcd1  test    rcx, rcx
0x18000bcd4  jz      short loc_18000BD3C
0x18000bcd6  cmp     r13w, [rcx]
0x18000bcda  jz      loc_18000BD81
0x18000bce0  mov     edx, 3Ah ; ':'
0x18000bce5  cmp     dx, [rcx]
0x18000bce8  jnz     short loc_18000BCF5
0x18000bcea  cmp     r13w, [rcx+2]
0x18000bcef  jz      loc_18000BD81
0x18000bcf5  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x18000bcf9  test    rax, rax
0x18000bcfc  jz      short loc_18000BD1E
0x18000bcfe  cmp     [rax], r13w
0x18000bd02  jz      short loc_18000BD1E
0x18000bd04  cmp     [rax], dx
0x18000bd07  jnz     short loc_18000BD10
0x18000bd09  cmp     [rax+2], r13w
0x18000bd0e  jz      short loc_18000BD1E
0x18000bd10  mov     rdx, [r14]
0x18000bd13  mov     rax, [rdx+28h]
0x18000bd17  mov     [rsp+0E0h+var_C0], rax
0x18000bd1c  jmp     short loc_18000BD26
0x18000bd1e  mov     rdx, [r14]; struct _PROXY_LIST *
0x18000bd21  mov     [rsp+0E0h+var_C0], r13; unsigned __int16 *
0x18000bd26  mov     r9, [rdx+20h]; unsigned __int16 *
0x18000bd2a  mov     rcx, rdi; this
0x18000bd2d  mov     r8d, [rdx+1Ch]; unsigned int
0x18000bd31  call    ?AddProxyServers@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@KPEAG1@Z; CHttpConnector::AddProxyServers(_PROXY_LIST *,ulong,ushort *,ushort *)
0x18000bd36  mov     ebx, eax
0x18000bd38  test    eax, eax
0x18000bd3a  js      short loc_18000BD4B
0x18000bd3c  cmp     [rdi+38h], r13d
0x18000bd40  jz      short loc_18000BD4B
0x18000bd42  mov     rdx, [rdi+30h]; struct _PROXY_LIST *
0x18000bd46  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000bd4b  cmp     ebx, 8007000Eh
0x18000bd51  jz      short loc_18000BDC3
0x18000bd53  cmp     ebx, 80070057h
0x18000bd59  jz      short loc_18000BDA6
0x18000bd5b  test    ebx, ebx
0x18000bd5d  jz      short loc_18000BD81
0x18000bd5f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000bd66  jz      short loc_18000BD77
0x18000bd68  mov     r9d, ebx
0x18000bd6b  lea     r8, aChttpconnector_5; "CHttpConnector::BuildProxyLists"
0x18000bd72  call    McTemplateU0sq_EventWriteTransfer
0x18000bd77  test    ebx, ebx
0x18000bd79  jns     loc_18000BE66
0x18000bd7f  jmp     short loc_18000BDDF
0x18000bd81  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000bd88  jz      loc_18000BE66
0x18000bd8e  lea     r8, aChttpconnector_5; "CHttpConnector::BuildProxyLists"
0x18000bd95  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000bd9c  call    McTemplateU0s_EventWriteTransfer
0x18000bda1  jmp     loc_18000BE66
0x18000bda6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000bdad  jz      short loc_18000BDDF
0x18000bdaf  mov     r9d, 80070057h
0x18000bdb5  lea     r8, aChttpconnector_5; "CHttpConnector::BuildProxyLists"
0x18000bdbc  call    McTemplateU0sq_EventWriteTransfer
0x18000bdc1  jmp     short loc_18000BDDF
0x18000bdc3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000bdca  jz      short loc_18000BDDF
0x18000bdcc  lea     r8, aChttpconnector_5; "CHttpConnector::BuildProxyLists"
0x18000bdd3  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000bdda  call    McTemplateU0s_EventWriteTransfer
0x18000bddf  mov     rdx, [rdi+18h]; struct _PROXY_LIST *
0x18000bde3  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000bde8  mov     rsi, [rdi+18h]
0x18000bdec  test    rsi, rsi
0x18000bdef  jz      short loc_18000BE09
0x18000bdf1  call    cs:__imp_GetProcessHeap
0x18000bdf7  mov     r8, rsi; lpMem
0x18000bdfa  xor     edx, edx; dwFlags
0x18000bdfc  mov     rcx, rax; hHeap
0x18000bdff  call    cs:__imp_HeapFree
0x18000be05  mov     [rdi+18h], r13
0x18000be09  mov     rdx, [rdi+20h]; struct _PROXY_LIST *
0x18000be0d  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000be12  mov     rsi, [rdi+20h]
0x18000be16  test    rsi, rsi
0x18000be19  jz      short loc_18000BE33
0x18000be1b  call    cs:__imp_GetProcessHeap
0x18000be21  mov     r8, rsi; lpMem
0x18000be24  xor     edx, edx; dwFlags
0x18000be26  mov     rcx, rax; hHeap
0x18000be29  call    cs:__imp_HeapFree
0x18000be2f  mov     [rdi+20h], r13
0x18000be33  mov     rdx, [rdi+28h]; struct _PROXY_LIST *
0x18000be37  call    ?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z; CHttpConnector::CloseProxyList(_PROXY_LIST *)
0x18000be3c  mov     rsi, [rdi+28h]
0x18000be40  test    rsi, rsi
0x18000be43  jz      short loc_18000BE5D
  ... truncated ...
```
