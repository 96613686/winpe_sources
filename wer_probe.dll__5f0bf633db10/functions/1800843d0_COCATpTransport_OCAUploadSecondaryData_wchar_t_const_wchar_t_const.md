# COCATpTransport::OCAUploadSecondaryData(wchar_t const *,wchar_t const *)

- ea: `0x1800843d0`
- end: `0x1800848d4`
- name: `?OCAUploadSecondaryData@COCATpTransport@@IEAAJPEB_W0@Z`
- size: `1284`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008278c`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000dad0`
- `0x180016514`
- `0x18001fe24`
- `0x18002556c`
- `0x1800293ac`
- `0x180039d00`
- `0x18003bed8`
- `0x18003bf14`
- `0x18003c24c`
- `0x18003df8c`
- `0x180045854`
- `0x1800489f0`
- `0x180049a60`
- `0x18004ae6c`
- `0x18004c774`
- `0x18004cdec`
- `0x1800720ec`
- `0x1800843d0`
- `0x180084b64`
- `0x180085b88`
- `0x18008f3ec`
- `0x18008f420`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084476`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084476`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084766`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084766`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800846de`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800846de`

## string_xrefs

- `0x1800847c8`: `TpToken`
- `0x1800847b9`: `TpTokenExp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall COCATpTransport::OCAUploadSecondaryData(COCATpTransport *this, wchar_t *a2, wchar_t *a3)
{
  void **v5; // r12
  int v6; // edi
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct CReportCabStream *v10; // r15
  void *v11; // rbx
  unsigned __int64 v12; // rax
  int DeviceTicketHeader; // eax
  const wchar_t *v14; // rbx
  unsigned __int64 v15; // rax
  const wchar_t *v16; // r8
  CReport **v17; // r14
  BOOL v18; // r13d
  int v19; // ebx
  __int64 v20; // rdi
  int v21; // eax
  wchar_t *v22; // rcx
  __int64 v23; // rdx
  bool v25; // [rsp+28h] [rbp-D8h]
  void *v26; // [rsp+80h] [rbp-80h] BYREF
  int v27; // [rsp+88h] [rbp-78h]
  struct CReportCabStream *v28[2]; // [rsp+8Ch] [rbp-74h]
  int v29; // [rsp+9Ch] [rbp-64h]
  __int64 v30[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v31[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v34[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v35[56]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v36[928]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v37; // [rsp+510h] [rbp+410h] BYREF
  wchar_t *v38; // [rsp+520h] [rbp+420h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+528h] [rbp+428h] BYREF

  v38 = a3;
  CReportCab::CReportCab((CReportCab *)v35);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v36);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v33);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
  v30[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v31);
  SystemTimeAsFileTime = 0;
  v5 = (void **)((char *)this + 40);
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v27 = 7;
  v26 = (void *)*((_QWORD *)this + 5);
  CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v26);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *((_QWORD *)this + 49) <= *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    v6 = 1;
    goto LABEL_47;
  }
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  v27 = 10;
  v26 = *v5;
  v7 = CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v26);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)v7);
    goto LABEL_47;
  }
  v10 = *(struct CReportCabStream **)((char *)v28 + 4);
  if ( !*(struct CReportCabStream **)((char *)v28 + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  *((_DWORD *)this + 84) = 1;
  v11 = *v5;
  v12 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v10 + 32LL))(v10);
  CTransport::EventUploadStart(this, v12, v11);
  DeviceTicketHeader = CTransport::GetDeviceTicketHeader(v31, *v5);
  v6 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)DeviceTicketHeader);
    goto LABEL_47;
  }
  if ( UtilRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting",
         L"EnableZip",
         1u,
         0,
         v25) )
  {
    v21 = COCATpTransport::UploadToAzure(this, v10, a2, v31[0]);
    v6 = v21;
    if ( v21 >= 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_47;
      v23 = 27;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)v21);
        v22 = WPP_GLOBAL_Control;
      }
      if ( !*((_DWORD *)this + 88) )
        goto LABEL_20;
      if ( v22 == (wchar_t *)&WPP_GLOBAL_Control || (v22[14] & 4) == 0 )
        goto LABEL_47;
      v23 = 26;
    }
    WPP_SF_(*((_QWORD *)v22 + 2), v23, &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
LABEL_20:
  v14 = L"zip";
  if ( !*((_DWORD *)v10 + 4) )
    v14 = L"cab";
  v15 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v10 + 32LL))(v10);
  v30[1] = (__int64)this + 56;
  v16 = 0;
  if ( *((_QWORD *)this + 11) != *((_QWORD *)this + 12) )
    v16 = (const wchar_t *)*((_QWORD *)this + 11);
  v17 = (CReport **)((char *)this + 48);
  v6 = COCATpTransport::PrepareCabUploadRequest(
         *((struct CReport **)this + 6),
         a2,
         v16,
         v38,
         v15,
         v14,
         0,
         0,
         (struct CTpRequestMessage *)v36);
  if ( v6 >= 0 )
  {
    v18 = 0;
    v19 = 0;
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CReport *)((char *)*v17 + 46688))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*v17) )
    {
      v19 = 2;
    }
    v20 = *((_QWORD *)*v17 + 6507);
    if ( v20 )
      v18 = ImpersonateLoggedOnUser(*((HANDLE *)*v17 + 6507));
    v6 = CTpTransport::DoExchange(
           (struct CTpRequestMessage *)v36,
           v10,
           (CTpResponseMessage *)v33,
           (__int64)&COCATpTransport::tpCommandConstructors,
           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           v19,
           0,
           v20,
           *v5,
           (COCATpTransport *)((char *)this + 192),
           (wchar_t *)L"data-upload/secondary",
           0,
           v31[0],
           (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
           0);
    if ( v18 )
      RevertToSelf();
    if ( v6 >= 0 )
    {
      v6 = COCATpTransport::ParseCabUploadResponse(
             (CTpResponseMessage *)v33,
             (CReport *)((char *)*v17 + 8),
             (__int64)v34,
             (__int64)v30,
             (__int64)&v37,
             0);
      if ( v6 >= 0 )
      {
        CReport::RemoveStateParamByKey(*v17, L"TpTokenExp");
        CReport::RemoveStateParamByKey(*v17, L"TpToken");
        v6 = 0;
      }
    }
  }
LABEL_47:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
  utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(v32);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v33);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v36);
  CReportCab::~CReportCab((CReportCab *)v35);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800843d0  mov     [rsp-8+arg_8], rbx
0x1800843d5  mov     [rsp-8+arg_10], r8
0x1800843da  push    rbp
0x1800843db  push    rsi
0x1800843dc  push    rdi
0x1800843dd  push    r12
0x1800843df  push    r13
0x1800843e1  push    r14
0x1800843e3  push    r15
0x1800843e5  lea     rbp, [rsp-3D0h]
0x1800843ed  sub     rsp, 4D0h
0x1800843f4  mov     r13, rdx
0x1800843f7  mov     rsi, rcx
0x1800843fa  lea     rcx, [rbp+400h+var_3D8]; this
0x1800843fe  call    ??0CReportCab@@QEAA@XZ; CReportCab::CReportCab(void)
0x180084403  nop
0x180084404  lea     rcx, [rbp+400h+var_3A0]; this
0x180084408  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x18008440d  nop
0x18008440e  lea     rcx, [rbp+400h+var_418]; this
0x180084412  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180084417  nop
0x180084418  lea     rcx, [rbp+400h+var_430]
0x18008441c  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180084421  nop
0x180084422  lea     rcx, [rbp+400h+var_3F8]; void *
0x180084426  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008442b  nop
0x18008442c  xor     r14d, r14d
0x18008442f  mov     [rbp+400h+var_460], r14
0x180084433  lea     rcx, [rbp+400h+var_450]; void *
0x180084437  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008443c  nop
0x18008443d  mov     qword ptr [rbp+400h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180084444  lea     r12, [rsi+28h]
0x180084448  xorps   xmm0, xmm0
0x18008444b  movdqu  xmmword ptr [rbp+400h+var_474], xmm0
0x180084450  mov     [rbp+400h+var_464], r14d
0x180084454  mov     [rbp+400h+var_478], 7
0x18008445b  mov     rax, [r12]
0x18008445f  mov     [rbp+400h+var_480], rax
0x180084463  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x180084467  mov     rcx, rsi; this
0x18008446a  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x18008446f  lea     rcx, [rbp+400h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180084476  call    cs:__imp_GetSystemTimeAsFileTime
0x18008447c  mov     ecx, [rbp+400h+SystemTimeAsFileTime.dwHighDateTime]
0x180084482  shl     rcx, 20h
0x180084486  mov     eax, [rbp+400h+SystemTimeAsFileTime.dwLowDateTime]
0x18008448c  or      rcx, rax
0x18008448f  cmp     [rsi+188h], rcx
0x180084496  ja      short loc_1800844D2
0x180084498  lea     rbx, WPP_GLOBAL_Control
0x18008449f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844a6  cmp     rcx, rbx
0x1800844a9  jz      short loc_1800844C8
0x1800844ab  lea     edx, [r14+2]
0x1800844af  test    [rcx+1Ch], dl
0x1800844b2  jz      short loc_1800844C8
0x1800844b4  lea     edx, [r14+16h]
0x1800844b8  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800844bf  mov     rcx, [rcx+10h]
0x1800844c3  call    WPP_SF_
0x1800844c8  mov     edi, 1
0x1800844cd  jmp     loc_18008487C
0x1800844d2  mov     [rbp+400h+var_474], r14
0x1800844d6  mov     [rbp+400h+var_474+8], r14
0x1800844da  mov     [rbp+400h+var_464], r14d
0x1800844de  mov     [rbp+400h+var_478], 0Ah
0x1800844e5  mov     rax, [r12]
0x1800844e9  mov     [rbp+400h+var_480], rax
0x1800844ed  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x1800844f1  mov     rcx, rsi; this
0x1800844f4  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x1800844f9  mov     edi, eax
0x1800844fb  test    eax, eax
0x1800844fd  jns     short loc_18008453D
0x1800844ff  lea     rbx, WPP_GLOBAL_Control
0x180084506  mov     rcx, cs:WPP_GLOBAL_Control
0x18008450d  cmp     rcx, rbx
0x180084510  jz      loc_18008487C
0x180084516  test    byte ptr [rcx+1Ch], 1
0x18008451a  jz      loc_18008487C
0x180084520  mov     edx, 17h
0x180084525  mov     r9d, eax
0x180084528  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008452f  mov     rcx, [rcx+10h]
0x180084533  call    WPP_SF_d
0x180084538  jmp     loc_18008487C
0x18008453d  mov     r15, [rbp+400h+var_474+4]
0x180084541  test    r15, r15
0x180084544  jnz     short loc_18008454B
0x180084546  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008454b  mov     dword ptr [rsi+150h], 1
0x180084555  mov     rbx, [r12]
0x180084559  mov     rax, [r15]
0x18008455c  mov     rcx, r15
0x18008455f  mov     rax, [rax+20h]
0x180084563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084568  mov     r8, rbx; void *
0x18008456b  mov     rdx, rax; unsigned __int64
0x18008456e  mov     rcx, rsi; this
0x180084571  call    ?EventUploadStart@CTransport@@IEAAJ_KPEAX@Z; CTransport::EventUploadStart(unsigned __int64,void *)
0x180084576  mov     rdx, [r12]
0x18008457a  lea     rcx, [rbp+400h+var_450]
0x18008457e  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180084583  mov     edi, eax
0x180084585  test    eax, eax
0x180084587  jns     short loc_1800845CB
0x180084589  lea     rbx, WPP_GLOBAL_Control
0x180084590  mov     rcx, cs:WPP_GLOBAL_Control
0x180084597  cmp     rcx, rbx
0x18008459a  jz      loc_18008487C
0x1800845a0  mov     edx, 2
0x1800845a5  test    [rcx+1Ch], dl
0x1800845a8  jz      loc_18008487C
0x1800845ae  mov     edx, 18h
0x1800845b3  mov     r9d, eax
0x1800845b6  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800845bd  mov     rcx, [rcx+10h]
0x1800845c1  call    WPP_SF_d
0x1800845c6  jmp     loc_18008487C
0x1800845cb  mov     [rsp+500h+var_4E0], r14; bool *
0x1800845d0  mov     r9d, 1; unsigned int
0x1800845d6  lea     r8, aEnablezip; "EnableZip"
0x1800845dd  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\Windows E"...
0x1800845e4  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800845eb  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800845f0  test    eax, eax
0x1800845f2  jnz     loc_1800847DE
0x1800845f8  lea     rbx, WPP_GLOBAL_Control
0x1800845ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180084606  cmp     rcx, rbx
0x180084609  jz      short loc_180084624
0x18008460b  test    byte ptr [rcx+1Ch], 4
0x18008460f  jz      short loc_180084624
0x180084611  lea     edx, [rax+49h]
0x180084614  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008461b  mov     rcx, [rcx+10h]
0x18008461f  call    WPP_SF_
0x180084624  lea     rax, aCab_1; "cab"
0x18008462b  lea     rbx, aZip_0; "zip"
0x180084632  cmp     [r15+10h], r14d
0x180084636  cmovz   rbx, rax
0x18008463a  mov     rax, [r15]
0x18008463d  mov     rcx, r15
0x180084640  mov     rax, [rax+20h]
0x180084644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084649  lea     rdx, [rsi+38h]
0x18008464d  mov     [rbp+400h+var_458], rdx
0x180084651  mov     rcx, [rdx+20h]
0x180084655  mov     r8, r14
0x180084658  cmp     rcx, [rdx+28h]
0x18008465c  cmovnz  r8, rcx; wchar_t *
0x180084660  lea     r14, [rsi+30h]
0x180084664  lea     rcx, [rbp+400h+var_3A0]
0x180084668  mov     [rsp+500h+var_4C0], rcx; struct CTpRequestMessage *
0x18008466d  mov     [rsp+500h+var_4C8], 0; wchar_t *
0x180084676  mov     dword ptr [rsp+500h+var_4D0], 0; int
0x18008467e  mov     [rsp+500h+var_4D8], rbx; wchar_t *
0x180084683  mov     [rsp+500h+var_4E0], rax; unsigned __int64
0x180084688  mov     r9, [rbp+400h+arg_10]; wchar_t *
0x18008468f  mov     rdx, r13; wchar_t *
0x180084692  mov     rcx, [r14]; struct CReport *
0x180084695  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x18008469a  mov     edi, eax
0x18008469c  test    eax, eax
0x18008469e  js      loc_18008487C
0x1800846a4  xor     r13d, r13d
0x1800846a7  xor     ebx, ebx
0x1800846a9  mov     rcx, [r14]
0x1800846ac  add     rcx, 0B660h; this
0x1800846b3  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x1800846b8  test    eax, eax
0x1800846ba  jz      short loc_1800846CC
0x1800846bc  mov     rcx, [r14]; this
0x1800846bf  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x1800846c4  lea     edx, [rbx+2]
0x1800846c7  test    eax, eax
0x1800846c9  cmovz   ebx, edx
0x1800846cc  mov     rax, [r14]
0x1800846cf  mov     rdi, [rax+0CB58h]
0x1800846d6  test    rdi, rdi
0x1800846d9  jz      short loc_1800846E7
0x1800846db  mov     rcx, rdi; hToken
0x1800846de  call    cs:__imp_ImpersonateLoggedOnUser
0x1800846e4  mov     r13d, eax
0x1800846e7  mov     r8, [rbp+400h+var_450]
0x1800846eb  lea     r9, [rsi+0C0h]
0x1800846f2  lea     rcx, [rsi+20h]
0x1800846f6  neg     rsi
0x1800846f9  sbb     r10, r10
0x1800846fc  and     r10, rcx
0x1800846ff  xor     esi, esi
0x180084701  mov     [rsp+500h+var_490], esi; int
0x180084705  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x18008470c  mov     [rsp+500h+var_498], rax; __int64
0x180084711  mov     [rsp+500h+var_4A0], r8; __int64
0x180084716  mov     qword ptr [rsp+500h+var_4A8], rsi; int
0x18008471b  lea     rax, aDataUploadSeco; "data-upload/secondary"
0x180084722  mov     [rsp+500h+var_4B0], rax; __int64
0x180084727  mov     [rsp+500h+var_4B8], r9; __int64
0x18008472c  mov     rax, [r12]
0x180084730  mov     [rsp+500h+var_4C0], rax; __int64
0x180084735  mov     [rsp+500h+var_4C8], rdi; __int64
0x18008473a  mov     [rsp+500h+var_4D0], rsi; int
0x18008473f  mov     dword ptr [rsp+500h+var_4D8], ebx; int
0x180084743  mov     [rsp+500h+var_4E0], r10; struct ITpCallbacks *
0x180084748  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x18008474f  lea     r8, [rbp+400h+var_418]
0x180084753  mov     rdx, r15
0x180084756  lea     rcx, [rbp+400h+var_3A0]; this
0x18008475a  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x18008475f  mov     edi, eax
0x180084761  test    r13d, r13d
0x180084764  jz      short loc_18008476C
0x180084766  call    cs:__imp_RevertToSelf
0x18008476c  test    edi, edi
0x18008476e  js      loc_18008487C
0x180084774  mov     rdx, [r14]
0x180084777  add     rdx, 8; CResponse *
0x18008477b  mov     [rsp+500h+var_4C8], rsi; __int64
0x180084780  lea     rax, [rbp+400h+arg_0]
0x180084787  mov     [rsp+500h+var_4D0], rax; __int64
0x18008478c  lea     rax, [rbp+400h+var_460]
0x180084790  mov     [rsp+500h+var_4D8], rax; __int64
0x180084795  lea     rax, [rbp+400h+var_3F8]
0x180084799  mov     [rsp+500h+var_4E0], rax; __int64
0x18008479e  lea     r9, [rbp+400h+var_430]
0x1800847a2  mov     r8, [rbp+400h+var_458]
0x1800847a6  lea     rcx, [rbp+400h+var_418]; this
0x1800847aa  call    ?ParseCabUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAVCResponse@@PEAVCOCAReply@@PEAVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH4@Z; COCATpTransport::ParseCabUploadResponse(CTpResponseMessage *,CResponse *,COCAReply *,CDataRequest *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800847af  mov     edi, eax
0x1800847b1  test    eax, eax
0x1800847b3  js      loc_18008487C
0x1800847b9  lea     rdx, aTptokenexp; "TpTokenExp"
0x1800847c0  mov     rcx, [r14]; this
0x1800847c3  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x1800847c8  lea     rdx, aTptoken; "TpToken"
0x1800847cf  mov     rcx, [r14]; this
0x1800847d2  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x1800847d7  mov     edi, esi
0x1800847d9  jmp     loc_18008487C
0x1800847de  mov     r9, [rbp+400h+var_450]; wchar_t *
0x1800847e2  mov     r8, r13; wchar_t *
0x1800847e5  mov     rdx, r15; struct CReportCabStream *
0x1800847e8  mov     rcx, rsi; this
0x1800847eb  call    ?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z; COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)
0x1800847f0  mov     edi, eax
0x1800847f2  test    eax, eax
0x1800847f4  jns     short loc_18008484D
0x1800847f6  lea     rbx, WPP_GLOBAL_Control
0x1800847fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180084804  cmp     rcx, rbx
0x180084807  jz      short loc_18008482E
0x180084809  test    byte ptr [rcx+1Ch], 1
0x18008480d  jz      short loc_18008482E
0x18008480f  mov     edx, 19h
0x180084814  mov     r9d, eax
0x180084817  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008481e  mov     rcx, [rcx+10h]
0x180084822  call    WPP_SF_d
0x180084827  mov     rcx, cs:WPP_GLOBAL_Control
0x18008482e  cmp     [rsi+160h], r14d
0x180084835  jz      loc_180084624
0x18008483b  cmp     rcx, rbx
0x18008483e  jz      short loc_18008487C
0x180084840  test    byte ptr [rcx+1Ch], 4
0x180084844  jz      short loc_18008487C
0x180084846  mov     edx, 1Ah
0x18008484b  jmp     short loc_18008486B
0x18008484d  lea     rbx, WPP_GLOBAL_Control
0x180084854  mov     rcx, cs:WPP_GLOBAL_Control
0x18008485b  cmp     rcx, rbx
0x18008485e  jz      short loc_18008487C
0x180084860  test    byte ptr [rcx+1Ch], 4
0x180084864  jz      short loc_18008487C
0x180084866  mov     edx, 1Bh
0x18008486b  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180084872  mov     rcx, [rcx+10h]
0x180084876  call    WPP_SF_
0x18008487b  nop
0x18008487c  lea     rcx, [rbp+400h+var_450]; void *
0x180084880  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180084885  nop
0x180084886  lea     rcx, [rbp+400h+var_3F8]; void *
0x18008488a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008488f  nop
0x180084890  lea     rcx, [rbp+400h+var_430]
0x180084894  call    ?_Uninit@?$vector@VRequestToken@@V?$allocator@VRequestToken@@@utl@@@utl@@AEAAXXZ; utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(void)
0x180084899  nop
0x18008489a  lea     rcx, [rbp+400h+var_418]; this
0x18008489e  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x1800848a3  nop
0x1800848a4  lea     rcx, [rbp+400h+var_3A0]; this
0x1800848a8  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x1800848ad  nop
0x1800848ae  lea     rcx, [rbp+400h+var_3D8]; this
0x1800848b2  call    ??1CReportCab@@QEAA@XZ; CReportCab::~CReportCab(void)
0x1800848b7  mov     eax, edi
  ... truncated ...
```
