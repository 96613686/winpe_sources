# COCATpTransport::OCAUploadSecondaryData(wchar_t const *,wchar_t const *)

- ea: `0x18008808c`
- end: `0x1800885a3`
- name: `?OCAUploadSecondaryData@COCATpTransport@@IEAAJPEB_W0@Z`
- size: `1303`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800863ec`

## callees

- `0x180004c64`
- `0x180005be8`
- `0x18000cf50`
- `0x18000db80`
- `0x180019f74`
- `0x180020680`
- `0x180025444`
- `0x18002a0f4`
- `0x18003b7e0`
- `0x18003de60`
- `0x18003de9c`
- `0x18003e2b4`
- `0x18003fc6c`
- `0x18004761c`
- `0x18004ab74`
- `0x18004bc20`
- `0x18004cff4`
- `0x18004eb28`
- `0x18004f1cc`
- `0x18007543c`
- `0x18008808c`
- `0x18008884c`
- `0x1800898d8`
- `0x18009349c`
- `0x1800934d0`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180088132`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180088132`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008842e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008842e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800883a0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800883a0`

## string_xrefs

- `0x180088496`: `TpToken`
- `0x180088487`: `TpTokenExp`

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
  __int64 v10; // r8
  struct CReportCabStream *v11; // r15
  void *v12; // rbx
  unsigned __int64 v13; // rax
  int DeviceTicketHeader; // eax
  const wchar_t *v15; // rbx
  unsigned __int64 v16; // rax
  const wchar_t *v17; // r8
  CReport **v18; // r14
  BOOL v19; // r13d
  int v20; // ebx
  __int64 v21; // rdi
  int v22; // eax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  bool v26; // [rsp+28h] [rbp-D8h]
  void *v27; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+88h] [rbp-78h]
  struct CReportCabStream *v29[2]; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+9Ch] [rbp-64h]
  __int64 v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v35[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v36[56]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v37[928]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v38; // [rsp+510h] [rbp+410h] BYREF
  wchar_t *v39; // [rsp+520h] [rbp+420h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+528h] [rbp+428h] BYREF

  v39 = a3;
  CReportCab::CReportCab((CReportCab *)v36);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v37);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v34);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v33);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v31[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
  SystemTimeAsFileTime = 0;
  v5 = (void **)((char *)this + 40);
  *(_OWORD *)v29 = 0;
  v30 = 0;
  v28 = 7;
  v27 = (void *)*((_QWORD *)this + 5);
  CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v27);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *((_QWORD *)this + 49) <= *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    v6 = 1;
    goto LABEL_47;
  }
  v29[0] = 0;
  v29[1] = 0;
  v30 = 0;
  v28 = 10;
  v27 = *v5;
  v7 = CTransport::DoCallback(this, (struct TRANSPORT_CALLBACK_PARAM *)&v27);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)v7);
    goto LABEL_47;
  }
  v11 = *(struct CReportCabStream **)((char *)v29 + 4);
  if ( !*(struct CReportCabStream **)((char *)v29 + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10);
  *((_DWORD *)this + 84) = 1;
  v12 = *v5;
  v13 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v11 + 32LL))(v11);
  CTransport::EventUploadStart(this, v13, v12);
  DeviceTicketHeader = CTransport::GetDeviceTicketHeader(v32, *v5);
  v6 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
        (unsigned int)DeviceTicketHeader);
    goto LABEL_47;
  }
  if ( UtilRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting",
         L"EnableZip",
         1u,
         0,
         v26) )
  {
    v22 = COCATpTransport::UploadToAzure(this, v11, a2, v32[0]);
    v6 = v22;
    if ( v22 >= 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_47;
      v24 = 27;
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)v22);
        v23 = WPP_GLOBAL_Control;
      }
      if ( !*((_DWORD *)this + 88) )
        goto LABEL_20;
      if ( v23 == (wchar_t *)&WPP_GLOBAL_Control || (v23[14] & 4) == 0 )
        goto LABEL_47;
      v24 = 26;
    }
    WPP_SF_(*((_QWORD *)v23 + 2), v24, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
LABEL_20:
  v15 = L"zip";
  if ( !*((_DWORD *)v11 + 4) )
    v15 = L"cab";
  v16 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v11 + 32LL))(v11);
  v31[1] = (__int64)this + 56;
  v17 = 0;
  if ( *((_QWORD *)this + 11) != *((_QWORD *)this + 12) )
    v17 = (const wchar_t *)*((_QWORD *)this + 11);
  v18 = (CReport **)((char *)this + 48);
  v6 = COCATpTransport::PrepareCabUploadRequest(
         *((struct CReport **)this + 6),
         a2,
         v17,
         v39,
         v16,
         v15,
         0,
         0,
         (struct CTpRequestMessage *)v37);
  if ( v6 >= 0 )
  {
    v19 = 0;
    v20 = 0;
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CReport *)((char *)*v18 + 46688))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*v18) )
    {
      v20 = 2;
    }
    v21 = *((_QWORD *)*v18 + 6507);
    if ( v21 )
      v19 = ImpersonateLoggedOnUser(*((HANDLE *)*v18 + 6507));
    v6 = CTpTransport::DoExchange(
           (struct CTpRequestMessage *)v37,
           v11,
           (CTpResponseMessage *)v34,
           (__int64)&COCATpTransport::tpCommandConstructors,
           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           v20,
           0,
           v21,
           *v5,
           (COCATpTransport *)((char *)this + 192),
           (wchar_t *)L"data-upload/secondary",
           0,
           v32[0],
           (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
           0);
    if ( v19 )
      RevertToSelf();
    if ( v6 >= 0 )
    {
      v6 = COCATpTransport::ParseCabUploadResponse(
             (CTpResponseMessage *)v34,
             (CReport *)((char *)*v18 + 8),
             (__int64)v35,
             (__int64)v31,
             (__int64)&v38,
             0);
      if ( v6 >= 0 )
      {
        CReport::RemoveStateParamByKey(*v18, L"TpTokenExp");
        CReport::RemoveStateParamByKey(*v18, L"TpToken");
        v6 = 0;
      }
    }
  }
LABEL_47:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(v33);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v34);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v37);
  CReportCab::~CReportCab((CReportCab *)v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008808c  mov     [rsp-8+arg_8], rbx
0x180088091  mov     [rsp-8+arg_10], r8
0x180088096  push    rbp
0x180088097  push    rsi
0x180088098  push    rdi
0x180088099  push    r12
0x18008809b  push    r13
0x18008809d  push    r14
0x18008809f  push    r15
0x1800880a1  lea     rbp, [rsp-3D0h]
0x1800880a9  sub     rsp, 4D0h
0x1800880b0  mov     r13, rdx
0x1800880b3  mov     rsi, rcx
0x1800880b6  lea     rcx, [rbp+400h+var_3D8]; this
0x1800880ba  call    ??0CReportCab@@QEAA@XZ; CReportCab::CReportCab(void)
0x1800880bf  nop
0x1800880c0  lea     rcx, [rbp+400h+var_3A0]; this
0x1800880c4  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800880c9  nop
0x1800880ca  lea     rcx, [rbp+400h+var_418]; this
0x1800880ce  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x1800880d3  nop
0x1800880d4  lea     rcx, [rbp+400h+var_430]
0x1800880d8  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800880dd  nop
0x1800880de  lea     rcx, [rbp+400h+var_3F8]; void *
0x1800880e2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800880e7  nop
0x1800880e8  xor     r14d, r14d
0x1800880eb  mov     [rbp+400h+var_460], r14
0x1800880ef  lea     rcx, [rbp+400h+var_450]; void *
0x1800880f3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800880f8  nop
0x1800880f9  mov     qword ptr [rbp+400h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180088100  lea     r12, [rsi+28h]
0x180088104  xorps   xmm0, xmm0
0x180088107  movdqu  xmmword ptr [rbp+400h+var_474], xmm0
0x18008810c  mov     [rbp+400h+var_464], r14d
0x180088110  mov     [rbp+400h+var_478], 7
0x180088117  mov     rax, [r12]
0x18008811b  mov     [rbp+400h+var_480], rax
0x18008811f  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x180088123  mov     rcx, rsi; this
0x180088126  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x18008812b  lea     rcx, [rbp+400h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180088132  call    cs:__imp_GetSystemTimeAsFileTime
0x180088139  nop     dword ptr [rax+rax+00h]
0x18008813e  mov     ecx, [rbp+400h+SystemTimeAsFileTime.dwHighDateTime]
0x180088144  shl     rcx, 20h
0x180088148  mov     eax, [rbp+400h+SystemTimeAsFileTime.dwLowDateTime]
0x18008814e  or      rcx, rax
0x180088151  cmp     [rsi+188h], rcx
0x180088158  ja      short loc_180088194
0x18008815a  lea     rbx, WPP_GLOBAL_Control
0x180088161  mov     rcx, cs:WPP_GLOBAL_Control
0x180088168  cmp     rcx, rbx
0x18008816b  jz      short loc_18008818A
0x18008816d  lea     edx, [r14+2]
0x180088171  test    [rcx+1Ch], dl
0x180088174  jz      short loc_18008818A
0x180088176  lea     edx, [r14+16h]
0x18008817a  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180088181  mov     rcx, [rcx+10h]
0x180088185  call    WPP_SF_
0x18008818a  mov     edi, 1
0x18008818f  jmp     loc_18008854A
0x180088194  mov     [rbp+400h+var_474], r14
0x180088198  mov     [rbp+400h+var_474+8], r14
0x18008819c  mov     [rbp+400h+var_464], r14d
0x1800881a0  mov     [rbp+400h+var_478], 0Ah
0x1800881a7  mov     rax, [r12]
0x1800881ab  mov     [rbp+400h+var_480], rax
0x1800881af  lea     rdx, [rbp+400h+var_480]; struct TRANSPORT_CALLBACK_PARAM *
0x1800881b3  mov     rcx, rsi; this
0x1800881b6  call    ?DoCallback@CTransport@@IEAAJPEAUTRANSPORT_CALLBACK_PARAM@@@Z; CTransport::DoCallback(TRANSPORT_CALLBACK_PARAM *)
0x1800881bb  mov     edi, eax
0x1800881bd  test    eax, eax
0x1800881bf  jns     short loc_1800881FF
0x1800881c1  lea     rbx, WPP_GLOBAL_Control
0x1800881c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800881cf  cmp     rcx, rbx
0x1800881d2  jz      loc_18008854A
0x1800881d8  test    byte ptr [rcx+1Ch], 1
0x1800881dc  jz      loc_18008854A
0x1800881e2  mov     edx, 17h
0x1800881e7  mov     r9d, eax
0x1800881ea  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800881f1  mov     rcx, [rcx+10h]
0x1800881f5  call    WPP_SF_d
0x1800881fa  jmp     loc_18008854A
0x1800881ff  mov     r15, [rbp+400h+var_474+4]
0x180088203  test    r15, r15
0x180088206  jnz     short loc_18008820D
0x180088208  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008820d  mov     dword ptr [rsi+150h], 1
0x180088217  mov     rbx, [r12]
0x18008821b  mov     rax, [r15]
0x18008821e  mov     rcx, r15
0x180088221  mov     rax, [rax+20h]
0x180088225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008822a  mov     r8, rbx; void *
0x18008822d  mov     rdx, rax; unsigned __int64
0x180088230  mov     rcx, rsi; this
0x180088233  call    ?EventUploadStart@CTransport@@IEAAJ_KPEAX@Z; CTransport::EventUploadStart(unsigned __int64,void *)
0x180088238  mov     rdx, [r12]
0x18008823c  lea     rcx, [rbp+400h+var_450]
0x180088240  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180088245  mov     edi, eax
0x180088247  test    eax, eax
0x180088249  jns     short loc_18008828D
0x18008824b  lea     rbx, WPP_GLOBAL_Control
0x180088252  mov     rcx, cs:WPP_GLOBAL_Control
0x180088259  cmp     rcx, rbx
0x18008825c  jz      loc_18008854A
0x180088262  mov     edx, 2
0x180088267  test    [rcx+1Ch], dl
0x18008826a  jz      loc_18008854A
0x180088270  mov     edx, 18h
0x180088275  mov     r9d, eax
0x180088278  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008827f  mov     rcx, [rcx+10h]
0x180088283  call    WPP_SF_d
0x180088288  jmp     loc_18008854A
0x18008828d  mov     [rsp+500h+var_4E0], r14; bool *
0x180088292  mov     r9d, 1; unsigned int
0x180088298  lea     r8, aEnablezip; "EnableZip"
0x18008829f  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x1800882a6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800882ad  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800882b2  test    eax, eax
0x1800882b4  jnz     loc_1800884AC
0x1800882ba  lea     rbx, WPP_GLOBAL_Control
0x1800882c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800882c8  cmp     rcx, rbx
0x1800882cb  jz      short loc_1800882E6
0x1800882cd  test    byte ptr [rcx+1Ch], 4
0x1800882d1  jz      short loc_1800882E6
0x1800882d3  lea     edx, [rax+49h]
0x1800882d6  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800882dd  mov     rcx, [rcx+10h]
0x1800882e1  call    WPP_SF_
0x1800882e6  lea     rax, aCab_1; "cab"
0x1800882ed  lea     rbx, aZip_0; "zip"
0x1800882f4  cmp     [r15+10h], r14d
0x1800882f8  cmovz   rbx, rax
0x1800882fc  mov     rax, [r15]
0x1800882ff  mov     rcx, r15
0x180088302  mov     rax, [rax+20h]
0x180088306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008830b  lea     rdx, [rsi+38h]
0x18008830f  mov     [rbp+400h+var_458], rdx
0x180088313  mov     rcx, [rdx+20h]
0x180088317  mov     r8, r14
0x18008831a  cmp     rcx, [rdx+28h]
0x18008831e  cmovnz  r8, rcx; wchar_t *
0x180088322  lea     r14, [rsi+30h]
0x180088326  lea     rcx, [rbp+400h+var_3A0]
0x18008832a  mov     [rsp+500h+var_4C0], rcx; struct CTpRequestMessage *
0x18008832f  mov     [rsp+500h+var_4C8], 0; wchar_t *
0x180088338  mov     dword ptr [rsp+500h+var_4D0], 0; int
0x180088340  mov     [rsp+500h+var_4D8], rbx; wchar_t *
0x180088345  mov     [rsp+500h+var_4E0], rax; unsigned __int64
0x18008834a  mov     r9, [rbp+400h+arg_10]; wchar_t *
0x180088351  mov     rdx, r13; wchar_t *
0x180088354  mov     rcx, [r14]; struct CReport *
0x180088357  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x18008835c  mov     edi, eax
0x18008835e  test    eax, eax
0x180088360  js      loc_18008854A
0x180088366  xor     r13d, r13d
0x180088369  xor     ebx, ebx
0x18008836b  mov     rcx, [r14]
0x18008836e  add     rcx, 0B660h; this
0x180088375  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x18008837a  test    eax, eax
0x18008837c  jz      short loc_18008838E
0x18008837e  mov     rcx, [r14]; this
0x180088381  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180088386  lea     edx, [rbx+2]
0x180088389  test    eax, eax
0x18008838b  cmovz   ebx, edx
0x18008838e  mov     rax, [r14]
0x180088391  mov     rdi, [rax+0CB58h]
0x180088398  test    rdi, rdi
0x18008839b  jz      short loc_1800883AF
0x18008839d  mov     rcx, rdi; hToken
0x1800883a0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800883a7  nop     dword ptr [rax+rax+00h]
0x1800883ac  mov     r13d, eax
0x1800883af  mov     r8, [rbp+400h+var_450]
0x1800883b3  lea     r9, [rsi+0C0h]
0x1800883ba  lea     rcx, [rsi+20h]
0x1800883be  neg     rsi
0x1800883c1  sbb     r10, r10
0x1800883c4  and     r10, rcx
0x1800883c7  xor     esi, esi
0x1800883c9  mov     [rsp+500h+var_490], esi; int
0x1800883cd  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x1800883d4  mov     [rsp+500h+var_498], rax; __int64
0x1800883d9  mov     [rsp+500h+var_4A0], r8; __int64
0x1800883de  mov     qword ptr [rsp+500h+var_4A8], rsi; int
0x1800883e3  lea     rax, aDataUploadSeco; "data-upload/secondary"
0x1800883ea  mov     [rsp+500h+var_4B0], rax; __int64
0x1800883ef  mov     [rsp+500h+var_4B8], r9; __int64
0x1800883f4  mov     rax, [r12]
0x1800883f8  mov     [rsp+500h+var_4C0], rax; __int64
0x1800883fd  mov     [rsp+500h+var_4C8], rdi; __int64
0x180088402  mov     [rsp+500h+var_4D0], rsi; int
0x180088407  mov     dword ptr [rsp+500h+var_4D8], ebx; int
0x18008840b  mov     [rsp+500h+var_4E0], r10; struct ITpCallbacks *
0x180088410  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180088417  lea     r8, [rbp+400h+var_418]
0x18008841b  mov     rdx, r15
0x18008841e  lea     rcx, [rbp+400h+var_3A0]; this
0x180088422  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180088427  mov     edi, eax
0x180088429  test    r13d, r13d
0x18008842c  jz      short loc_18008843A
0x18008842e  call    cs:__imp_RevertToSelf
0x180088435  nop     dword ptr [rax+rax+00h]
0x18008843a  test    edi, edi
0x18008843c  js      loc_18008854A
0x180088442  mov     rdx, [r14]
0x180088445  add     rdx, 8; CResponse *
0x180088449  mov     [rsp+500h+var_4C8], rsi; __int64
0x18008844e  lea     rax, [rbp+400h+arg_0]
0x180088455  mov     [rsp+500h+var_4D0], rax; __int64
0x18008845a  lea     rax, [rbp+400h+var_460]
0x18008845e  mov     [rsp+500h+var_4D8], rax; __int64
0x180088463  lea     rax, [rbp+400h+var_3F8]
0x180088467  mov     [rsp+500h+var_4E0], rax; __int64
0x18008846c  lea     r9, [rbp+400h+var_430]
0x180088470  mov     r8, [rbp+400h+var_458]
0x180088474  lea     rcx, [rbp+400h+var_418]; this
0x180088478  call    ?ParseCabUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAVCResponse@@PEAVCOCAReply@@PEAVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH4@Z; COCATpTransport::ParseCabUploadResponse(CTpResponseMessage *,CResponse *,COCAReply *,CDataRequest *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008847d  mov     edi, eax
0x18008847f  test    eax, eax
0x180088481  js      loc_18008854A
0x180088487  lea     rdx, aTptokenexp; "TpTokenExp"
0x18008848e  mov     rcx, [r14]; this
0x180088491  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x180088496  lea     rdx, aTptoken; "TpToken"
0x18008849d  mov     rcx, [r14]; this
0x1800884a0  call    ?RemoveStateParamByKey@CReport@@QEAAJPEB_W@Z; CReport::RemoveStateParamByKey(wchar_t const *)
0x1800884a5  mov     edi, esi
0x1800884a7  jmp     loc_18008854A
0x1800884ac  mov     r9, [rbp+400h+var_450]; wchar_t *
0x1800884b0  mov     r8, r13; wchar_t *
0x1800884b3  mov     rdx, r15; struct CReportCabStream *
0x1800884b6  mov     rcx, rsi; this
0x1800884b9  call    ?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z; COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)
0x1800884be  mov     edi, eax
0x1800884c0  test    eax, eax
0x1800884c2  jns     short loc_18008851B
0x1800884c4  lea     rbx, WPP_GLOBAL_Control
0x1800884cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800884d2  cmp     rcx, rbx
0x1800884d5  jz      short loc_1800884FC
0x1800884d7  test    byte ptr [rcx+1Ch], 1
0x1800884db  jz      short loc_1800884FC
0x1800884dd  mov     edx, 19h
0x1800884e2  mov     r9d, eax
0x1800884e5  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800884ec  mov     rcx, [rcx+10h]
0x1800884f0  call    WPP_SF_d
0x1800884f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800884fc  cmp     [rsi+160h], r14d
0x180088503  jz      loc_1800882E6
0x180088509  cmp     rcx, rbx
0x18008850c  jz      short loc_18008854A
0x18008850e  test    byte ptr [rcx+1Ch], 4
0x180088512  jz      short loc_18008854A
0x180088514  mov     edx, 1Ah
0x180088519  jmp     short loc_180088539
0x18008851b  lea     rbx, WPP_GLOBAL_Control
0x180088522  mov     rcx, cs:WPP_GLOBAL_Control
0x180088529  cmp     rcx, rbx
0x18008852c  jz      short loc_18008854A
0x18008852e  test    byte ptr [rcx+1Ch], 4
0x180088532  jz      short loc_18008854A
0x180088534  mov     edx, 1Bh
0x180088539  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180088540  mov     rcx, [rcx+10h]
0x180088544  call    WPP_SF_
0x180088549  nop
0x18008854a  lea     rcx, [rbp+400h+var_450]; void *
0x18008854e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180088553  nop
0x180088554  lea     rcx, [rbp+400h+var_3F8]; void *
0x180088558  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008855d  nop
0x18008855e  lea     rcx, [rbp+400h+var_430]
0x180088562  call    ?_Uninit@?$vector@VRequestToken@@V?$allocator@VRequestToken@@@utl@@@utl@@AEAAXXZ; utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(void)
0x180088567  nop
0x180088568  lea     rcx, [rbp+400h+var_418]; this
0x18008856c  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180088571  nop
0x180088572  lea     rcx, [rbp+400h+var_3A0]; this
0x180088576  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008857b  nop
  ... truncated ...
```
