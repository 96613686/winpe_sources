# InitializeSstpServer

- ea: `0x18000bd24`
- end: `0x18000c4bc`
- name: `InitializeSstpServer`
- size: `1944`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005e30`
- `0x18000aa44`
- `0x1800158c0`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x180008c70`
- `0x18000bd24`
- `0x18000c768`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18000c2a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18000c2a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000c27d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000c3bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000c27d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000c3bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18000c263`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18000c263`
- `rtutils!RouterLogEventStringW` at `0x18000c082`
- `rtutils!RouterLogEventStringW` at `0x18000c169`
- `rtutils!RouterLogEventStringW` at `0x18000c23a`
- `rtutils!RouterLogEventStringW` at `0x18000c082`
- `rtutils!RouterLogEventStringW` at `0x18000c169`
- `rtutils!RouterLogEventStringW` at `0x18000c23a`
- `HTTPAPI!HttpCreateRequestQueue` at `0x18000c0ed`
- `HTTPAPI!HttpCreateRequestQueue` at `0x18000c0ed`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18000c1be`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18000c1be`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000c3e9`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000c3e9`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000c40b`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000c40b`
- `HTTPAPI!HttpCreateUrlGroup` at `0x18000bfb4`
- `HTTPAPI!HttpCreateUrlGroup` at `0x18000bfb4`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x18000c049`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x18000c049`
- `HTTPAPI!HttpInitialize` at `0x18000be4e`
- `HTTPAPI!HttpInitialize` at `0x18000be4e`
- `HTTPAPI!HttpCreateServerSession` at `0x18000bf63`
- `HTTPAPI!HttpCreateServerSession` at `0x18000bf63`
- `HTTPAPI!HttpTerminate` at `0x18000c449`
- `HTTPAPI!HttpTerminate` at `0x18000c449`
- `HTTPAPI!HttpCloseServerSession` at `0x18000c42d`
- `HTTPAPI!HttpCloseServerSession` at `0x18000c42d`
- `sstpcfg!GetUrlForConfig` at `0x18000c025`
- `sstpcfg!GetUrlForConfig` at `0x18000c025`
- `sstpcfg!GetCryptoBindingInfo` at `0x18000bef1`
- `sstpcfg!GetCryptoBindingInfo` at `0x18000bef1`
- `sstpcfg!GetCryptoBindingSupportedAlgoInfo` at `0x18000beb3`
- `sstpcfg!GetCryptoBindingSupportedAlgoInfo` at `0x18000beb3`
- `sstpcfg!GetSstpServerConfig` at `0x18000be24`
- `sstpcfg!GetSstpServerConfig` at `0x18000be24`

## string_xrefs

- `0x18000bf8f`: `HttpCreateServerSession fails with error %d (%d)`
- `0x18000bfe0`: `HttpCreateUrlGroup fails with error %d (%d)`
- `0x18000c2f0`: `Unable to create ThreadpoolI/O...0x%x (%d)`

## pseudocode

```c
__int64 __fastcall InitializeSstpServer(char a1)
{
  DWORD dwErrorCode; // edi
  HTTPAPI_VERSION v3; // ebx
  HTTPAPI_VERSION v4; // ecx
  ULONG v5; // eax
  LPVOID v6; // rdx
  __int64 v7; // r9
  DWORD CryptoBindingInfo; // eax
  ULONG ServerSession; // eax
  ULONG UrlGroup; // eax
  void *v11; // rcx
  ULONG RequestQueue; // eax
  void *v13; // rcx
  ULONG v14; // eax
  void *v15; // rcx
  char *v16; // rcx
  PTP_IO ThreadpoolIo; // rax
  LPVOID v18; // rcx
  DWORD LastError; // eax
  DWORD v20; // r15d
  char v21; // bl
  unsigned int v22; // r12d
  DWORD v23; // eax
  ULONG v24; // eax
  __int16 v26; // [rsp+40h] [rbp-C0h] BYREF
  char v27; // [rsp+42h] [rbp-BEh]
  HTTPAPI_VERSION Version; // [rsp+44h] [rbp-BCh]
  __int128 PropertyInformation; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  char v31[2044]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR pFullyQualifiedUrl[264]; // [rsp+860h] [rbp+760h] BYREF

  Version = (HTTPAPI_VERSION)2;
  memset_0(pFullyQualifiedUrl, 0, 0x208u);
  v30 = 0;
  v27 = 0;
  v26 = 0;
  PropertyInformation = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"Entering %ws", L"InitializeSstpServer");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v30);
  }
  dwErrorCode = 0;
  if ( (a1 & 1) != 0 )
    SetSstpConfigFlag(2, 1);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)SstpSvcGlobals + 191, 1, 1) )
    return dwErrorCode;
  GetSstpServerConfig(&v26);
  v3 = Version;
  v4 = Version;
  *((_DWORD *)SstpSvcGlobals + 160) = 10;
  v5 = HttpInitialize(v4, 3u, 0);
  dwErrorCode = v5;
  if ( !v5 )
  {
    GetCryptoBindingSupportedAlgoInfo(0, (char *)SstpSvcGlobals + 644);
    v6 = SstpSvcGlobals;
    LOBYTE(v7) = 1;
    LOBYTE(v6) = *((_BYTE *)SstpSvcGlobals + 644);
    CryptoBindingInfo = GetCryptoBindingInfo(
                          0,
                          v6,
                          0,
                          v7,
                          0,
                          (char *)SstpSvcGlobals + 645,
                          (char *)SstpSvcGlobals + 665);
    dwErrorCode = CryptoBindingInfo;
    if ( CryptoBindingInfo )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_63;
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"GetCryptoBindingInfo failed with error %d", CryptoBindingInfo);
    }
    else
    {
      ServerSession = HttpCreateServerSession(v3, (PHTTP_SERVER_SESSION_ID)SstpSvcGlobals + 6, 0);
      dwErrorCode = ServerSession;
      if ( !ServerSession )
      {
        UrlGroup = HttpCreateUrlGroup(*((_QWORD *)SstpSvcGlobals + 6), (PHTTP_URL_GROUP_ID)SstpSvcGlobals + 7, 0);
        dwErrorCode = UrlGroup;
        if ( UrlGroup )
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString(&v30, L"HttpCreateUrlGroup fails with error %d (%d)", UrlGroup, UrlGroup);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
          }
        }
        else
        {
          GetUrlForConfig(&v26, &qword_180024068, pFullyQualifiedUrl);
          dwErrorCode = HttpAddUrlToUrlGroup(*((_QWORD *)SstpSvcGlobals + 7), pFullyQualifiedUrl, 0, 0);
          if ( dwErrorCode )
          {
            v11 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
            if ( v11 )
              RouterLogEventStringW(v11, 1u, 0x16u, 0, 0, dwErrorCode, 0);
            if ( (byte_18002E903 & 8) != 0 )
            {
              LOWORD(v30) = 0;
              FormatRRASErrorString(&v30, L"Error adding the URL to URL group (%d - %d)", dwErrorCode, dwErrorCode);
              if ( (byte_18002E903 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
            }
          }
          else
          {
            RequestQueue = HttpCreateRequestQueue(v3, 0, 0, 0, (PHANDLE)SstpSvcGlobals + 8);
            dwErrorCode = RequestQueue;
            if ( RequestQueue )
            {
              if ( (byte_18002E903 & 8) != 0 )
              {
                LOWORD(v30) = 0;
                FormatRRASErrorString(&v30, L"Error setting up the request queue (%d - %d)", RequestQueue, RequestQueue);
                if ( (byte_18002E903 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
              }
              v13 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
              if ( v13 )
                RouterLogEventStringW(v13, 1u, 0x16u, 0, 0, dwErrorCode, 0);
            }
            else
            {
              if ( (byte_18002E903 & 0x10) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasSSTPSvcTraceInfo,
                  L"Successfully setup the request queue");
              LODWORD(PropertyInformation) = PropertyInformation | 1;
              *((_QWORD *)&PropertyInformation + 1) = *((_QWORD *)SstpSvcGlobals + 8);
              v14 = HttpSetUrlGroupProperty(
                      *((_QWORD *)SstpSvcGlobals + 7),
                      HttpServerBindingProperty,
                      &PropertyInformation,
                      0x10u);
              dwErrorCode = v14;
              if ( v14 )
              {
                if ( (byte_18002E903 & 8) != 0 )
                {
                  LOWORD(v30) = 0;
                  FormatRRASErrorString(
                    &v30,
                    L"Unable to setup the binding between the UrlGroup and the request queue (%d - %d)",
                    v14,
                    v14);
                  if ( (byte_18002E903 & 8) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasSSTPSvcTraceError,
                      &v30);
                }
                v15 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
                if ( v15 )
                  RouterLogEventStringW(v15, 1u, 0x16u, 0, 0, dwErrorCode, 0);
              }
              else
              {
                v16 = (char *)SstpSvcGlobals;
                if ( *((_QWORD *)SstpSvcGlobals + 21) )
                {
                  WaitForThreadpoolIoCallbacks(*((PTP_IO *)SstpSvcGlobals + 21), 0);
                  CloseThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
                  v16 = (char *)SstpSvcGlobals;
                  *((_QWORD *)SstpSvcGlobals + 21) = 0;
                }
                ThreadpoolIo = CreateThreadpoolIo(
                                 *((HANDLE *)v16 + 8),
                                 HttpThreadPoolRequestQueueCallback,
                                 0,
                                 (PTP_CALLBACK_ENVIRON)(v16 + 80));
                v18 = SstpSvcGlobals;
                *((_QWORD *)SstpSvcGlobals + 21) = ThreadpoolIo;
                if ( ThreadpoolIo )
                {
                  v20 = 0;
                  v21 = 0;
                  v22 = 0;
                  if ( *((_DWORD *)v18 + 160) )
                  {
                    do
                    {
                      v23 = PostNewHttpRequest();
                      v18 = SstpSvcGlobals;
                      v20 = v23;
                      if ( !v23 )
                        v21 = 1;
                      ++v22;
                    }
                    while ( v22 < *((_DWORD *)SstpSvcGlobals + 160) );
                    if ( v21 )
                    {
                      *((_DWORD *)SstpSvcGlobals + 191) = 1;
                      _InterlockedExchange((volatile __int32 *)v18 + 191, 1);
                      return dwErrorCode;
                    }
                  }
                  if ( (byte_18002E903 & 8) != 0 )
                  {
                    LOWORD(v30) = 0;
                    FormatRRASErrorString(&v30, L"Unable to setup listener successfully - %d", v20);
                    if ( (byte_18002E903 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v30);
                    v18 = SstpSvcGlobals;
                  }
                  dwErrorCode = v20;
                  CloseThreadpoolIo(*((PTP_IO *)v18 + 21));
                  *((_QWORD *)SstpSvcGlobals + 21) = 0;
                }
                else
                {
                  LastError = GetLastError();
                  dwErrorCode = LastError;
                  if ( (byte_18002E903 & 8) != 0 )
                  {
                    LOWORD(v30) = 0;
                    FormatRRASErrorString(&v30, L"Unable to create ThreadpoolI/O...0x%x (%d)", LastError, LastError);
                    if ( (byte_18002E903 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v30);
                  }
                }
              }
              HttpCloseRequestQueue(*((HANDLE *)SstpSvcGlobals + 8));
              *((_QWORD *)SstpSvcGlobals + 8) = 0;
            }
          }
          HttpCloseUrlGroup(*((_QWORD *)SstpSvcGlobals + 7));
          *((_QWORD *)SstpSvcGlobals + 7) = 0;
        }
        HttpCloseServerSession(*((_QWORD *)SstpSvcGlobals + 6));
        *((_QWORD *)SstpSvcGlobals + 6) = 0;
        goto LABEL_63;
      }
      if ( (byte_18002E903 & 8) == 0 )
      {
LABEL_63:
        v24 = HttpTerminate(3u, 0);
        if ( v24 )
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString(&v30, L"HttpTerminate fails with error %d (%d)", v24, v24);
            if ( (byte_18002E903 & 8) != 0 )
              goto LABEL_66;
          }
        }
        return dwErrorCode;
      }
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"HttpCreateServerSession fails with error %d (%d)", ServerSession, ServerSession);
    }
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
    goto LABEL_63;
  }
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"HttpInitialize fails with error %d (%d)", v5, v5);
    if ( (byte_18002E903 & 8) != 0 )
LABEL_66:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x18000bd24  push    rbp
0x18000bd26  push    rbx
0x18000bd27  push    rsi
0x18000bd28  push    rdi
0x18000bd29  push    r12
0x18000bd2b  push    r13
0x18000bd2d  push    r14
0x18000bd2f  push    r15
0x18000bd31  lea     rbp, [rsp-988h]
0x18000bd39  sub     rsp, 0A88h
0x18000bd40  mov     rax, cs:__security_cookie
0x18000bd47  xor     rax, rsp
0x18000bd4a  mov     [rbp+9C0h+var_50], rax
0x18000bd51  mov     ebx, ecx
0x18000bd53  mov     r14d, 2
0x18000bd59  lea     rcx, [rbp+9C0h+pFullyQualifiedUrl]; void *
0x18000bd60  mov     dword ptr [rsp+0AC0h+Version.HttpApiMajorVersion], r14d
0x18000bd65  xor     edx, edx; Val
0x18000bd67  mov     r8d, 208h; Size
0x18000bd6d  xor     r13d, r13d
0x18000bd70  call    memset_0
0x18000bd75  xor     eax, eax
0x18000bd77  mov     [rsp+0AC0h+var_A60], r13d
0x18000bd7c  xorps   xmm0, xmm0
0x18000bd7f  mov     [rsp+0AC0h+var_A7F], ax
0x18000bd84  xor     edx, edx; Val
0x18000bd86  mov     [rsp+40h], ax
0x18000bd8b  mov     r8d, 7FCh; Size
0x18000bd91  lea     rcx, [rsp+0AC0h+var_A5C]; void *
0x18000bd96  movups  [rsp+0AC0h+PropertyInformation], xmm0
0x18000bd9b  call    memset_0
0x18000bda0  lea     r12d, [r14+0Eh]
0x18000bda4  test    cs:byte_18002E903, r12b
0x18000bdab  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bdb2  jz      short loc_18000BDEF
0x18000bdb4  lea     r8, aInitializesstp; "InitializeSstpServer"
0x18000bdbb  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000bdc1  lea     rdx, aEnteringWs; "Entering %ws"
0x18000bdc8  lea     rcx, [rsp+0AC0h+var_A60]
0x18000bdcd  call    FormatRRASErrorString
0x18000bdd2  test    cs:byte_18002E903, r12b
0x18000bdd9  jz      short loc_18000BDEF
0x18000bddb  lea     r8, [rsp+0AC0h+var_A60]
0x18000bde0  mov     rcx, r15
0x18000bde3  lea     rdx, RasSSTPSvcTraceInfo
0x18000bdea  call    McTemplateU0z_EventWriteTransfer
0x18000bdef  mov     esi, 1
0x18000bdf4  mov     edi, r13d
0x18000bdf7  test    sil, bl
0x18000bdfa  jz      short loc_18000BE06
0x18000bdfc  mov     edx, esi
0x18000bdfe  mov     ecx, r14d
0x18000be01  call    SetSstpConfigFlag
0x18000be06  mov     rcx, cs:SstpSvcGlobals
0x18000be0d  mov     eax, esi
0x18000be0f  lock cmpxchg [rcx+2FCh], esi
0x18000be17  test    eax, eax
0x18000be19  jnz     loc_18000C496
0x18000be1f  lea     rcx, [rsp+0AC0h+var_A80]
0x18000be24  call    cs:__imp_GetSstpServerConfig
0x18000be2b  nop     dword ptr [rax+rax+00h]
0x18000be30  mov     rax, cs:SstpSvcGlobals
0x18000be37  xor     r8d, r8d; pReserved
0x18000be3a  mov     ebx, dword ptr [rsp+0AC0h+Version.HttpApiMajorVersion]
0x18000be3e  mov     ecx, ebx; Version
0x18000be40  lea     edx, [r8+3]; Flags
0x18000be44  mov     dword ptr [rax+280h], 0Ah
0x18000be4e  call    cs:__imp_HttpInitialize
0x18000be55  nop     dword ptr [rax+rax+00h]
0x18000be5a  mov     edi, eax
0x18000be5c  test    eax, eax
0x18000be5e  jz      short loc_18000BEA3
0x18000be60  mov     bl, 8
0x18000be62  test    cs:byte_18002E903, bl
0x18000be68  jz      loc_18000C496
0x18000be6e  mov     r9d, eax
0x18000be71  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000be77  mov     r8d, eax
0x18000be7a  lea     rdx, aHttpinitialize; "HttpInitialize fails with error %d (%d)"
0x18000be81  lea     rcx, [rsp+0AC0h+var_A60]
0x18000be86  call    FormatRRASErrorString
0x18000be8b  test    cs:byte_18002E903, bl
0x18000be91  jz      loc_18000C496
0x18000be97  lea     rdx, RasSSTPSvcTraceError
0x18000be9e  jmp     loc_18000C489
0x18000bea3  mov     rdx, cs:SstpSvcGlobals
0x18000beaa  xor     ecx, ecx
0x18000beac  add     rdx, 284h
0x18000beb3  call    cs:__imp_GetCryptoBindingSupportedAlgoInfo
0x18000beba  nop     dword ptr [rax+rax+00h]
0x18000bebf  mov     rdx, cs:SstpSvcGlobals
0x18000bec6  mov     r9b, sil
0x18000bec9  xor     r8d, r8d
0x18000becc  lea     rcx, [rdx+285h]
0x18000bed3  lea     rax, [rdx+299h]
0x18000beda  mov     dl, [rdx+284h]
0x18000bee0  mov     qword ptr [rsp+0AC0h+dwErrorIndex], rax
0x18000bee5  mov     qword ptr [rsp+0AC0h+dwErrorCode], rcx
0x18000beea  xor     ecx, ecx
0x18000beec  mov     [rsp+0AC0h+plpszSubStringArray], r13
0x18000bef1  call    cs:__imp_GetCryptoBindingInfo
0x18000bef8  nop     dword ptr [rax+rax+00h]
0x18000befd  lea     r14, RasSSTPSvcTraceError
0x18000bf04  mov     edi, eax
0x18000bf06  test    eax, eax
0x18000bf08  jz      short loc_18000BF53
0x18000bf0a  mov     bl, 8
0x18000bf0c  test    cs:byte_18002E903, bl
0x18000bf12  jz      loc_18000C444
0x18000bf18  mov     r8d, eax
0x18000bf1b  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000bf21  lea     rdx, aGetcryptobindi; "GetCryptoBindingInfo failed with error "...
0x18000bf28  lea     rcx, [rsp+0AC0h+var_A60]
0x18000bf2d  call    FormatRRASErrorString
0x18000bf32  test    cs:byte_18002E903, bl
0x18000bf38  jz      loc_18000C444
0x18000bf3e  lea     r8, [rsp+0AC0h+var_A60]
0x18000bf43  mov     rdx, r14
0x18000bf46  mov     rcx, r15
0x18000bf49  call    McTemplateU0z_EventWriteTransfer
0x18000bf4e  jmp     loc_18000C444
0x18000bf53  mov     rdx, cs:SstpSvcGlobals
0x18000bf5a  xor     r8d, r8d; Reserved
0x18000bf5d  add     rdx, 30h ; '0'; ServerSessionId
0x18000bf61  mov     ecx, ebx; Version
0x18000bf63  call    cs:__imp_HttpCreateServerSession
0x18000bf6a  nop     dword ptr [rax+rax+00h]
0x18000bf6f  mov     edi, eax
0x18000bf71  test    eax, eax
0x18000bf73  jz      short loc_18000BFA2
0x18000bf75  mov     bl, 8
0x18000bf77  test    cs:byte_18002E903, bl
0x18000bf7d  jz      loc_18000C444
0x18000bf83  mov     r9d, eax
0x18000bf86  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000bf8c  mov     r8d, eax
0x18000bf8f  lea     rdx, aHttpcreateserv; "HttpCreateServerSession fails with erro"...
0x18000bf96  lea     rcx, [rsp+0AC0h+var_A60]
0x18000bf9b  call    FormatRRASErrorString
0x18000bfa0  jmp     short loc_18000BF32
0x18000bfa2  mov     rcx, cs:SstpSvcGlobals
0x18000bfa9  xor     r8d, r8d; Reserved
0x18000bfac  lea     rdx, [rcx+38h]; pUrlGroupId
0x18000bfb0  mov     rcx, [rcx+30h]; ServerSessionId
0x18000bfb4  call    cs:__imp_HttpCreateUrlGroup
0x18000bfbb  nop     dword ptr [rax+rax+00h]
0x18000bfc0  mov     edi, eax
0x18000bfc2  test    eax, eax
0x18000bfc4  jz      short loc_18000C012
0x18000bfc6  mov     bl, 8
0x18000bfc8  test    cs:byte_18002E903, bl
0x18000bfce  jz      loc_18000C422
0x18000bfd4  mov     r9d, eax
0x18000bfd7  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000bfdd  mov     r8d, eax
0x18000bfe0  lea     rdx, aHttpcreateurlg; "HttpCreateUrlGroup fails with error %d "...
0x18000bfe7  lea     rcx, [rsp+0AC0h+var_A60]
0x18000bfec  call    FormatRRASErrorString
0x18000bff1  test    cs:byte_18002E903, bl
0x18000bff7  jz      loc_18000C422
0x18000bffd  lea     r8, [rsp+0AC0h+var_A60]
0x18000c002  mov     rdx, r14
0x18000c005  mov     rcx, r15
0x18000c008  call    McTemplateU0z_EventWriteTransfer
0x18000c00d  jmp     loc_18000C422
0x18000c012  lea     r8, [rbp+9C0h+pFullyQualifiedUrl]
0x18000c019  lea     rdx, qword_180024068
0x18000c020  lea     rcx, [rsp+0AC0h+var_A80]
0x18000c025  call    cs:__imp_GetUrlForConfig
0x18000c02c  nop     dword ptr [rax+rax+00h]
0x18000c031  mov     rcx, cs:SstpSvcGlobals
0x18000c038  lea     rdx, [rbp+9C0h+pFullyQualifiedUrl]; pFullyQualifiedUrl
0x18000c03f  xor     r9d, r9d; Reserved
0x18000c042  xor     r8d, r8d; UrlContext
0x18000c045  mov     rcx, [rcx+38h]; UrlGroupId
0x18000c049  call    cs:__imp_HttpAddUrlToUrlGroup
0x18000c050  nop     dword ptr [rax+rax+00h]
0x18000c055  mov     edi, eax
0x18000c057  test    eax, eax
0x18000c059  mov     rax, cs:SstpSvcGlobals
0x18000c060  jz      short loc_18000C0DA
0x18000c062  mov     rcx, [rax+48h]; hLogHandle
0x18000c066  test    rcx, rcx
0x18000c069  jz      short loc_18000C08E
0x18000c06b  xor     r9d, r9d; dwSubStringCount
0x18000c06e  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000c073  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000c077  mov     edx, esi; dwEventType
0x18000c079  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000c07e  lea     r8d, [r9+16h]; dwMessageId
0x18000c082  call    cs:__imp_RouterLogEventStringW
0x18000c089  nop     dword ptr [rax+rax+00h]
0x18000c08e  mov     bl, 8
0x18000c090  test    cs:byte_18002E903, bl
0x18000c096  jz      loc_18000C400
0x18000c09c  mov     r9d, edi
0x18000c09f  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000c0a5  mov     r8d, edi
0x18000c0a8  lea     rdx, aErrorAddingThe; "Error adding the URL to URL group (%d -"...
0x18000c0af  lea     rcx, [rsp+0AC0h+var_A60]
0x18000c0b4  call    FormatRRASErrorString
0x18000c0b9  test    cs:byte_18002E903, bl
0x18000c0bf  jz      loc_18000C400
0x18000c0c5  lea     r8, [rsp+0AC0h+var_A60]
0x18000c0ca  mov     rdx, r14
0x18000c0cd  mov     rcx, r15
0x18000c0d0  call    McTemplateU0z_EventWriteTransfer
0x18000c0d5  jmp     loc_18000C400
0x18000c0da  add     rax, 40h ; '@'
0x18000c0de  xor     r9d, r9d; Flags
0x18000c0e1  xor     r8d, r8d; SecurityAttributes
0x18000c0e4  mov     [rsp+0AC0h+plpszSubStringArray], rax; RequestQueueHandle
0x18000c0e9  xor     edx, edx; Name
0x18000c0eb  mov     ecx, ebx; Version
0x18000c0ed  call    cs:__imp_HttpCreateRequestQueue
0x18000c0f4  nop     dword ptr [rax+rax+00h]
0x18000c0f9  mov     edi, eax
0x18000c0fb  test    eax, eax
0x18000c0fd  jz      short loc_18000C17A
0x18000c0ff  mov     bl, 8
0x18000c101  test    cs:byte_18002E903, bl
0x18000c107  jz      short loc_18000C13E
0x18000c109  mov     r9d, eax
0x18000c10c  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000c112  mov     r8d, eax
0x18000c115  lea     rdx, aErrorSettingUp; "Error setting up the request queue (%d "...
0x18000c11c  lea     rcx, [rsp+0AC0h+var_A60]
0x18000c121  call    FormatRRASErrorString
0x18000c126  test    cs:byte_18002E903, bl
0x18000c12c  jz      short loc_18000C13E
0x18000c12e  lea     r8, [rsp+0AC0h+var_A60]
0x18000c133  mov     rdx, r14
0x18000c136  mov     rcx, r15
0x18000c139  call    McTemplateU0z_EventWriteTransfer
0x18000c13e  mov     rax, cs:SstpSvcGlobals
0x18000c145  mov     rcx, [rax+48h]; hLogHandle
0x18000c149  test    rcx, rcx
0x18000c14c  jz      loc_18000C400
0x18000c152  xor     r9d, r9d; dwSubStringCount
0x18000c155  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000c15a  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000c15e  mov     edx, esi; dwEventType
0x18000c160  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000c165  lea     r8d, [r9+16h]; dwMessageId
0x18000c169  call    cs:__imp_RouterLogEventStringW
0x18000c170  nop     dword ptr [rax+rax+00h]
0x18000c175  jmp     loc_18000C400
0x18000c17a  test    cs:byte_18002E903, r12b
0x18000c181  jz      short loc_18000C199
0x18000c183  lea     r8, aSuccessfullySe; "Successfully setup the request queue"
0x18000c18a  mov     rcx, r15
0x18000c18d  lea     rdx, RasSSTPSvcTraceInfo
0x18000c194  call    McTemplateU0z_EventWriteTransfer
0x18000c199  mov     rcx, cs:SstpSvcGlobals
0x18000c1a0  lea     r8, [rsp+0AC0h+PropertyInformation]; PropertyInformation
0x18000c1a5  or      dword ptr [rsp+0AC0h+PropertyInformation], esi
0x18000c1a9  mov     r9d, r12d; PropertyInformationLength
0x18000c1ac  mov     edx, 7; Property
0x18000c1b1  mov     rax, [rcx+40h]
0x18000c1b5  mov     qword ptr [rsp+0AC0h+PropertyInformation+8], rax
0x18000c1ba  mov     rcx, [rcx+38h]; UrlGroupId
0x18000c1be  call    cs:__imp_HttpSetUrlGroupProperty
0x18000c1c5  nop     dword ptr [rax+rax+00h]
0x18000c1ca  mov     edi, eax
0x18000c1cc  test    eax, eax
0x18000c1ce  jz      short loc_18000C24B
0x18000c1d0  mov     bl, 8
0x18000c1d2  test    cs:byte_18002E903, bl
0x18000c1d8  jz      short loc_18000C20F
0x18000c1da  mov     r9d, eax
0x18000c1dd  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000c1e3  mov     r8d, eax
0x18000c1e6  lea     rdx, aUnableToSetupT; "Unable to setup the binding between the"...
0x18000c1ed  lea     rcx, [rsp+0AC0h+var_A60]
0x18000c1f2  call    FormatRRASErrorString
0x18000c1f7  test    cs:byte_18002E903, bl
0x18000c1fd  jz      short loc_18000C20F
0x18000c1ff  lea     r8, [rsp+0AC0h+var_A60]
0x18000c204  mov     rdx, r14
0x18000c207  mov     rcx, r15
0x18000c20a  call    McTemplateU0z_EventWriteTransfer
0x18000c20f  mov     rax, cs:SstpSvcGlobals
0x18000c216  mov     rcx, [rax+48h]; hLogHandle
0x18000c21a  test    rcx, rcx
0x18000c21d  jz      loc_18000C3DE
0x18000c223  xor     r9d, r9d; dwSubStringCount
0x18000c226  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000c22b  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000c22f  mov     edx, esi; dwEventType
0x18000c231  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000c236  lea     r8d, [r9+16h]; dwMessageId
0x18000c23a  call    cs:__imp_RouterLogEventStringW
0x18000c241  nop     dword ptr [rax+rax+00h]
0x18000c246  jmp     loc_18000C3DE
0x18000c24b  mov     rcx, cs:SstpSvcGlobals
0x18000c252  mov     rax, [rcx+0A8h]
0x18000c259  test    rax, rax
0x18000c25c  jz      short loc_18000C297
0x18000c25e  xor     edx, edx; fCancelPendingCallbacks
0x18000c260  mov     rcx, rax; pio
  ... truncated ...
```
