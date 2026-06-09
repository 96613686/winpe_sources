# ConfigureSstpServer

- ea: `0x180002518`
- end: `0x1800029a1`
- name: `ConfigureSstpServer`
- size: `1161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009720`

## callees

- `0x180002518`
- `0x180006a20`
- `0x180007450`
- `0x18000a044`
- `0x18000a088`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180002661`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180002661`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x18000271e`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x180002828`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x18000271e`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x180002828`
- `HTTPAPI!HttpInitialize` at `0x1800025ae`
- `HTTPAPI!HttpInitialize` at `0x1800025ae`
- `HTTPAPI!HttpTerminate` at `0x180002977`
- `HTTPAPI!HttpTerminate` at `0x180002977`
- `rtutils!RouterLogEventStringW` at `0x1800025df`
- `rtutils!RouterLogEventStringW` at `0x180002771`
- `rtutils!RouterLogEventStringW` at `0x18000287b`
- `rtutils!RouterLogEventStringW` at `0x1800025df`
- `rtutils!RouterLogEventStringW` at `0x180002771`
- `rtutils!RouterLogEventStringW` at `0x18000287b`

## string_xrefs

- `0x180002627`: `Unable to initialize HTTP for server configuration: %d`
- `0x1800026c8`: `HttpDeleteServiceConfiguration fails with error %d for %ws`
- `0x1800027c6`: `HttpSetServiceConfiguration fails with error %d for %ws`
- `0x1800028b5`: `HttpSetServiceConfiguration for default URL ACL fails %d`

## pseudocode

```c
__int64 __fastcall ConfigureSstpServer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG dwErrorCode; // eax
  ULONG v8; // edi
  __int64 v9; // r8
  const wchar_t *v10; // rdx
  ULONG v11; // edi
  int v12; // r8d
  ULONG v13; // eax
  ULONG v14; // edi
  int v15; // r8d
  ULONG v16; // eax
  ULONG v17; // edi
  __int64 v18; // r8
  ULONG v19; // eax
  __int64 v20; // r8
  __int128 pConfigInformation; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  char v27[2044]; // [rsp+74h] [rbp-8Ch] BYREF
  _BYTE v28[528]; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v29[528]; // [rsp+A80h] [rbp+980h] BYREF

  v25 = a4;
  v26 = 0;
  pConfigInformation = 0;
  memset_0(v27, 0, sizeof(v27));
  GetUrlForConfig(a1, &dword_18000D51C, v29);
  GetUrlForConfig(a2, &dword_18000D51C, v28);
  dwErrorCode = HttpInitialize((HTTPAPI_VERSION)2, 2u, 0);
  v8 = dwErrorCode;
  if ( dwErrorCode )
  {
    RouterLogEventStringW(EventSource, 2u, 8u, 0, 0, dwErrorCode, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, v9, v8);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      v10 = L"Unable to initialize HTTP for server configuration: %d";
LABEL_38:
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, v10, v8);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v26);
    }
  }
  else
  {
    *((_QWORD *)&pConfigInformation + 1) = L"D:(A;;GA;;;S-1-5-80-3435701886-799518250-3791383489-3228296122-2938884314)(A;"
                                            ";GA;;;BA)(A;;GA;;;SY)";
    *(_QWORD *)&pConfigInformation = v28;
    v11 = HttpDeleteServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, v12, v11, (__int64)v28);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"HttpDeleteServiceConfiguration fails with error %d for %ws", v11, v28);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v26);
      }
    }
    *(_QWORD *)&pConfigInformation = v29;
    v13 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
    v14 = v13;
    if ( v13 && v13 != 183 )
    {
      plpszSubStringArray = (LPWSTR)pConfigInformation;
      v24 = 0;
      RouterLogEventStringW(EventSource, 2u, 9u, 1u, &plpszSubStringArray, v13, 1u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, v15, v14, (__int64)v29);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"HttpSetServiceConfiguration fails with error %d for %ws", v14, v29);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v26);
      }
    }
    *(_QWORD *)&pConfigInformation = L"https://+:443/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/";
    *((_QWORD *)&pConfigInformation + 1) = L"D:(A;;GA;;;S-1-5-80-3435701886-799518250-3791383489-3228296122-2938884314)(A;"
                                            ";GA;;;BA)(A;;GA;;;SY)";
    v16 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
    v17 = v16;
    if ( v16 && v16 != 183 )
    {
      plpszSubStringArray = (LPWSTR)pConfigInformation;
      v24 = 0;
      RouterLogEventStringW(EventSource, 2u, 0xAu, 1u, &plpszSubStringArray, v16, 1u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, v18, v17);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"HttpSetServiceConfiguration for default URL ACL fails %d", v17);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v26);
      }
    }
    v19 = PlumbCertificateToHttp(a2, a1, a3, v25);
    v8 = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, v20, v19);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        v10 = L"Certificate plumbing to HTTP failed %d";
        goto LABEL_38;
      }
    }
  }
  HttpTerminate(2u, 0);
  return v8;
}

```

## disassembly

```asm
0x180002518  push    rbp
0x18000251a  push    rbx
0x18000251b  push    rdi
0x18000251c  push    r12
0x18000251e  push    r13
0x180002520  push    r14
0x180002522  push    r15
0x180002524  lea     rbp, [rsp-0BA0h]
0x18000252c  sub     rsp, 0CA0h
0x180002533  mov     rax, cs:__security_cookie
0x18000253a  xor     rax, rsp
0x18000253d  mov     [rbp+0BD0h+var_40], rax
0x180002544  mov     r13, r8
0x180002547  mov     [rsp+0CD0h+var_C68], r9
0x18000254c  mov     r12, rdx
0x18000254f  mov     r15, rcx
0x180002552  xorps   xmm0, xmm0
0x180002555  lea     rcx, [rsp+0CD0h+var_C5C]; void *
0x18000255a  xor     eax, eax
0x18000255c  mov     ebx, 2
0x180002561  xor     edx, edx; Val
0x180002563  mov     [rsp+0CD0h+var_C90], ebx
0x180002567  mov     r8d, 7FCh; Size
0x18000256d  mov     [rsp+0CD0h+var_C60], eax
0x180002571  movups  [rsp+0CD0h+pConfigInformation], xmm0
0x180002576  call    memset_0
0x18000257b  lea     r8, [rbp+0BD0h+var_250]
0x180002582  mov     rcx, r15
0x180002585  lea     rdx, dword_18000D51C
0x18000258c  call    GetUrlForConfig
0x180002591  lea     r8, [rbp+0BD0h+var_460]
0x180002598  mov     rcx, r12
0x18000259b  lea     rdx, dword_18000D51C
0x1800025a2  call    GetUrlForConfig
0x1800025a7  xor     r8d, r8d; pReserved
0x1800025aa  mov     edx, ebx; Flags
0x1800025ac  mov     ecx, ebx; Version
0x1800025ae  call    cs:__imp_HttpInitialize
0x1800025b4  mov     edi, eax
0x1800025b6  mov     edx, ebx; ConfigId
0x1800025b8  test    eax, eax
0x1800025ba  jz      short loc_180002633
0x1800025bc  mov     rcx, cs:EventSource; hLogHandle
0x1800025c3  lea     r8d, [rbx+6]; dwMessageId
0x1800025c7  mov     [rsp+0CD0h+dwErrorIndex], 0; dwErrorIndex
0x1800025cf  xor     r9d, r9d; dwSubStringCount
0x1800025d2  mov     [rsp+0CD0h+dwErrorCode], eax; dwErrorCode
0x1800025d6  mov     [rsp+0CD0h+plpszSubStringArray], 0; plpszSubStringArray
0x1800025df  call    cs:__imp_RouterLogEventStringW
0x1800025e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025ec  lea     r14, WPP_GLOBAL_Control
0x1800025f3  cmp     rcx, r14
0x1800025f6  jz      short loc_180002619
0x1800025f8  test    byte ptr [rcx+1Ch], 40h
0x1800025fc  jz      short loc_180002619
0x1800025fe  mov     ebx, 1
0x180002603  cmp     [rcx+19h], bl
0x180002606  jb      short loc_180002619
0x180002608  mov     rcx, [rcx+10h]
0x18000260c  mov     edx, 85h
0x180002611  mov     r9d, edi
0x180002614  call    WPP_SF_d
0x180002619  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180002621  jz      loc_180002972
0x180002627  lea     rdx, aUnableToInitia; "Unable to initialize HTTP for server co"...
0x18000262e  jmp     loc_18000293F
0x180002633  lea     rax, aDAGaS158034357; "D:(A;;GA;;;S-1-5-80-3435701886-79951825"...
0x18000263a  mov     [rsp+0CD0h+plpszSubStringArray], 0; pOverlapped
0x180002643  mov     qword ptr [rsp+0CD0h+pConfigInformation+8], rax
0x180002648  lea     r8, [rsp+0CD0h+pConfigInformation]; pConfigInformation
0x18000264d  lea     rax, [rbp+0BD0h+var_460]
0x180002654  mov     r9d, 10h; ConfigInformationLength
0x18000265a  xor     ecx, ecx; ServiceHandle
0x18000265c  mov     qword ptr [rsp+0CD0h+pConfigInformation], rax
0x180002661  call    cs:__imp_HttpDeleteServiceConfiguration
0x180002667  lea     r14, WPP_GLOBAL_Control
0x18000266e  mov     ebx, 1
0x180002673  mov     edi, eax
0x180002675  test    eax, eax
0x180002677  jz      short loc_1800026F8
0x180002679  mov     rcx, cs:WPP_GLOBAL_Control
0x180002680  cmp     rcx, r14
0x180002683  jz      short loc_1800026AD
0x180002685  test    byte ptr [rcx+1Ch], 40h
0x180002689  jz      short loc_1800026AD
0x18000268b  cmp     [rcx+19h], bl
0x18000268e  jb      short loc_1800026AD
0x180002690  mov     rcx, [rcx+10h]
0x180002694  lea     rax, [rbp+0BD0h+var_460]
0x18000269b  mov     edx, 86h
0x1800026a0  mov     [rsp+0CD0h+plpszSubStringArray], rax
0x1800026a5  mov     r9d, edi
0x1800026a8  call    WPP_SF_DS
0x1800026ad  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800026b5  jz      short loc_1800026F8
0x1800026b7  xor     eax, eax
0x1800026b9  lea     r9, [rbp+0BD0h+var_460]
0x1800026c0  mov     r8d, edi
0x1800026c3  mov     word ptr [rsp+0CD0h+var_C60], ax
0x1800026c8  lea     rdx, aHttpdeleteserv_0; "HttpDeleteServiceConfiguration fails wi"...
0x1800026cf  lea     rcx, [rsp+0CD0h+var_C60]
0x1800026d4  call    FormatRRASErrorString
0x1800026d9  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800026e0  lea     r8, [rsp+0CD0h+var_C60]
0x1800026e5  mov     rcx, cs:gSstpCfgEtwContext
0x1800026ec  mov     rax, cs:gSstpCfgTemplateFunc
0x1800026f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f8  mov     r9d, 10h; ConfigInformationLength
0x1800026fe  mov     [rsp+0CD0h+plpszSubStringArray], 0; pOverlapped
0x180002707  lea     rax, [rbp+0BD0h+var_250]
0x18000270e  xor     ecx, ecx; ServiceHandle
0x180002710  lea     r8, [rsp+0CD0h+pConfigInformation]; pConfigInformation
0x180002715  mov     qword ptr [rsp+0CD0h+pConfigInformation], rax
0x18000271a  lea     edx, [r9-0Eh]; ConfigId
0x18000271e  call    cs:__imp_HttpSetServiceConfiguration
0x180002724  mov     edi, eax
0x180002726  test    eax, eax
0x180002728  jz      loc_1800027F6
0x18000272e  cmp     eax, 0B7h
0x180002733  jz      loc_1800027F6
0x180002739  mov     rcx, qword ptr [rsp+0CD0h+pConfigInformation]
0x18000273e  mov     edx, 2; dwEventType
0x180002743  mov     [rsp+0CD0h+dwErrorIndex], ebx; dwErrorIndex
0x180002747  mov     r9d, ebx; dwSubStringCount
0x18000274a  mov     [rsp+0CD0h+dwErrorCode], eax; dwErrorCode
0x18000274e  lea     rax, [rsp+0CD0h+var_C78]
0x180002753  mov     [rsp+0CD0h+var_C78], rcx
0x180002758  mov     rcx, cs:EventSource; hLogHandle
0x18000275f  lea     r8d, [rdx+7]; dwMessageId
0x180002763  mov     [rsp+0CD0h+var_C70], 0
0x18000276c  mov     [rsp+0CD0h+plpszSubStringArray], rax; plpszSubStringArray
0x180002771  call    cs:__imp_RouterLogEventStringW
0x180002777  mov     rcx, cs:WPP_GLOBAL_Control
0x18000277e  cmp     rcx, r14
0x180002781  jz      short loc_1800027AB
0x180002783  test    byte ptr [rcx+1Ch], 40h
0x180002787  jz      short loc_1800027AB
0x180002789  cmp     [rcx+19h], bl
0x18000278c  jb      short loc_1800027AB
0x18000278e  mov     rcx, [rcx+10h]
0x180002792  lea     rax, [rbp+0BD0h+var_250]
0x180002799  mov     edx, 87h
0x18000279e  mov     [rsp+0CD0h+plpszSubStringArray], rax
0x1800027a3  mov     r9d, edi
0x1800027a6  call    WPP_SF_DS
0x1800027ab  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800027b3  jz      short loc_1800027F6
0x1800027b5  xor     eax, eax
0x1800027b7  lea     r9, [rbp+0BD0h+var_250]
0x1800027be  mov     r8d, edi
0x1800027c1  mov     word ptr [rsp+0CD0h+var_C60], ax
0x1800027c6  lea     rdx, aHttpsetservice_2; "HttpSetServiceConfiguration fails with "...
0x1800027cd  lea     rcx, [rsp+0CD0h+var_C60]
0x1800027d2  call    FormatRRASErrorString
0x1800027d7  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800027de  lea     r8, [rsp+0CD0h+var_C60]
0x1800027e3  mov     rcx, cs:gSstpCfgEtwContext
0x1800027ea  mov     rax, cs:gSstpCfgTemplateFunc
0x1800027f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f6  mov     r9d, 10h; ConfigInformationLength
0x1800027fc  mov     [rsp+0CD0h+plpszSubStringArray], 0; pOverlapped
0x180002805  lea     rax, aHttps443SraBa1; "https://+:443/sra_{BA195980-CD49-458b-9"...
0x18000280c  xor     ecx, ecx; ServiceHandle
0x18000280e  mov     qword ptr [rsp+0CD0h+pConfigInformation], rax
0x180002813  lea     r8, [rsp+0CD0h+pConfigInformation]; pConfigInformation
0x180002818  lea     rax, aDAGaS158034357; "D:(A;;GA;;;S-1-5-80-3435701886-79951825"...
0x18000281f  lea     edx, [r9-0Eh]; ConfigId
0x180002823  mov     qword ptr [rsp+0CD0h+pConfigInformation+8], rax
0x180002828  call    cs:__imp_HttpSetServiceConfiguration
0x18000282e  mov     edi, eax
0x180002830  test    eax, eax
0x180002832  jz      loc_1800028ED
0x180002838  cmp     eax, 0B7h
0x18000283d  jz      loc_1800028ED
0x180002843  mov     rcx, qword ptr [rsp+0CD0h+pConfigInformation]
0x180002848  mov     edx, 2; dwEventType
0x18000284d  mov     [rsp+0CD0h+dwErrorIndex], ebx; dwErrorIndex
0x180002851  mov     r9d, ebx; dwSubStringCount
0x180002854  mov     [rsp+0CD0h+dwErrorCode], eax; dwErrorCode
0x180002858  lea     rax, [rsp+0CD0h+var_C78]
0x18000285d  mov     [rsp+0CD0h+var_C78], rcx
0x180002862  mov     rcx, cs:EventSource; hLogHandle
0x180002869  lea     r8d, [rdx+8]; dwMessageId
0x18000286d  mov     [rsp+0CD0h+var_C70], 0
0x180002876  mov     [rsp+0CD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18000287b  call    cs:__imp_RouterLogEventStringW
0x180002881  mov     rcx, cs:WPP_GLOBAL_Control
0x180002888  cmp     rcx, r14
0x18000288b  jz      short loc_1800028A9
0x18000288d  test    byte ptr [rcx+1Ch], 40h
0x180002891  jz      short loc_1800028A9
0x180002893  cmp     [rcx+19h], bl
0x180002896  jb      short loc_1800028A9
0x180002898  mov     rcx, [rcx+10h]
0x18000289c  mov     edx, 88h
0x1800028a1  mov     r9d, edi
0x1800028a4  call    WPP_SF_d
0x1800028a9  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800028b1  jz      short loc_1800028ED
0x1800028b3  xor     eax, eax
0x1800028b5  lea     rdx, aHttpsetservice_0; "HttpSetServiceConfiguration for default"...
0x1800028bc  mov     r8d, edi
0x1800028bf  mov     word ptr [rsp+0CD0h+var_C60], ax
0x1800028c4  lea     rcx, [rsp+0CD0h+var_C60]
0x1800028c9  call    FormatRRASErrorString
0x1800028ce  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800028d5  lea     r8, [rsp+0CD0h+var_C60]
0x1800028da  mov     rcx, cs:gSstpCfgEtwContext
0x1800028e1  mov     rax, cs:gSstpCfgTemplateFunc
0x1800028e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ed  mov     r9, [rsp+0CD0h+var_C68]
0x1800028f2  mov     r8, r13
0x1800028f5  mov     rdx, r15
0x1800028f8  mov     rcx, r12
0x1800028fb  call    PlumbCertificateToHttp
0x180002900  mov     edi, eax
0x180002902  test    eax, eax
0x180002904  jz      short loc_180002972
0x180002906  mov     rcx, cs:WPP_GLOBAL_Control
0x18000290d  cmp     rcx, r14
0x180002910  jz      short loc_18000292E
0x180002912  test    byte ptr [rcx+1Ch], 40h
0x180002916  jz      short loc_18000292E
0x180002918  cmp     [rcx+19h], bl
0x18000291b  jb      short loc_18000292E
0x18000291d  mov     rcx, [rcx+10h]
0x180002921  mov     edx, 89h
0x180002926  mov     r9d, eax
0x180002929  call    WPP_SF_d
0x18000292e  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180002936  jz      short loc_180002972
0x180002938  lea     rdx, aCertificatePlu; "Certificate plumbing to HTTP failed %d"
0x18000293f  xor     eax, eax
0x180002941  lea     rcx, [rsp+0CD0h+var_C60]
0x180002946  mov     r8d, edi
0x180002949  mov     word ptr [rsp+0CD0h+var_C60], ax
0x18000294e  call    FormatRRASErrorString
0x180002953  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000295a  lea     r8, [rsp+0CD0h+var_C60]
0x18000295f  mov     rcx, cs:gSstpCfgEtwContext
0x180002966  mov     rax, cs:gSstpCfgTemplateFunc
0x18000296d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002972  xor     edx, edx; pReserved
0x180002974  lea     ecx, [rdx+2]; Flags
0x180002977  call    cs:__imp_HttpTerminate
0x18000297d  mov     eax, edi
0x18000297f  mov     rcx, [rbp+0BD0h+var_40]
0x180002986  xor     rcx, rsp; StackCookie
0x180002989  call    __security_check_cookie
0x18000298e  add     rsp, 0CA0h
0x180002995  pop     r15
0x180002997  pop     r14
0x180002999  pop     r13
0x18000299b  pop     r12
0x18000299d  pop     rdi
0x18000299e  pop     rbx
0x18000299f  pop     rbp
0x1800029a0  retn
```
