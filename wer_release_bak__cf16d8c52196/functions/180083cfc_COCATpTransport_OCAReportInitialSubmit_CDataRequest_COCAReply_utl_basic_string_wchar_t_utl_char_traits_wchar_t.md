# COCATpTransport::OCAReportInitialSubmit(CDataRequest *,COCAReply *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)

- ea: `0x180083cfc`
- end: `0x1800843ca`
- name: `?OCAReportInitialSubmit@COCATpTransport@@IEAAJPEAVCDataRequest@@PEAVCOCAReply@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z`
- size: `1742`
- prototype: `__int64 __usercall@<rax>(COCATpTransport *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008278c`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000dad0`
- `0x18001fe24`
- `0x18002556c`
- `0x180026498`
- `0x180038ce4`
- `0x180039d00`
- `0x18003c24c`
- `0x18003df8c`
- `0x18003f364`
- `0x180045854`
- `0x1800489f0`
- `0x18004c774`
- `0x180070af4`
- `0x1800720ec`
- `0x180082f00`
- `0x18008331c`
- `0x180083cfc`
- `0x180084b64`
- `0x180084fc8`
- `0x1800853ec`
- `0x18008f3a4`
- `0x18008f420`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180083f8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800841b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180083f8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800841b8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180083f08`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180084125`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180083f08`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180084125`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall COCATpTransport::OCAReportInitialSubmit(
        COCATpTransport *this,
        CDataRequest *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        _DWORD *a6)
{
  int DeviceTicketHeader; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  const wchar_t *v13; // rcx
  _DWORD *v14; // rsi
  BOOL v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rbx
  struct IWerByteStream *v18; // r15
  const wchar_t *v19; // rbx
  unsigned __int64 v20; // rax
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rsi
  unsigned __int64 *v24; // rsi
  CDataRequest *v25; // r14
  int v26; // eax
  unsigned int i; // r9d
  CReport *v28; // rcx
  int v29; // r9d
  struct CReportCabStream *v31[2]; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *v32[4]; // [rsp+A0h] [rbp-68h] BYREF
  const wchar_t *v33[4]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v34[4]; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t *v35[4]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v36[32]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v37[40]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v38[880]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v39[928]; // [rsp+4D8h] [rbp+3D0h] BYREF
  struct CReportFile *v40; // [rsp+888h] [rbp+780h] BYREF
  CDataRequest *v41; // [rsp+890h] [rbp+788h]
  __int64 v42; // [rsp+898h] [rbp+790h]

  v42 = a3;
  v41 = a2;
  v31[0] = 0;
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v39);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v37);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v38);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v36);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v33);
  v31[1] = 0;
  LODWORD(v40) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  DeviceTicketHeader = CTpRequestMessage::SetCommercialInfo(
                         v39,
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
                         *((_QWORD *)this + 6) + 51920LL);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 13;
LABEL_5:
    v12 = (unsigned int)DeviceTicketHeader;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v12);
    goto LABEL_60;
  }
  DeviceTicketHeader = CTpRequestMessage::SetCommercialInfo(
                         v38,
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
                         *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
                         *((_QWORD *)this + 6) + 51920LL);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 14;
    goto LABEL_5;
  }
  v13 = *(const wchar_t **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v13 = 0;
  *a5 = 0;
  v14 = a6;
  *a6 = 0;
  DeviceTicketHeader = COCATpTransport::HandleAsyncStage2Prolog(this);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 15;
    goto LABEL_5;
  }
  DeviceTicketHeader = CTransport::GetDeviceTicketHeader(v34, *((_QWORD *)this + 5));
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      goto LABEL_60;
    v11 = 16;
    goto LABEL_5;
  }
  v15 = 0;
  v9 = COCATpTransport::PrepareReqUploadRequest(*((struct CReport **)this + 6), (struct CTpRequestMessage *)v39);
  if ( v9 < 0 )
    goto LABEL_60;
  v16 = *((_QWORD *)this + 6);
  v17 = *(_QWORD *)(v16 + 52056);
  if ( v17 )
    v15 = ImpersonateLoggedOnUser(*(HANDLE *)(v16 + 52056));
  v9 = CTpTransport::DoExchange(
         (struct CTpRequestMessage *)v39,
         0,
         (CTpResponseMessage *)v37,
         (__int64)&COCATpTransport::tpCommandConstructors,
         (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
         0,
         0,
         v17,
         *((void **)this + 5),
         (COCATpTransport *)((char *)this + 192),
         (wchar_t *)L"request-upload/minidump",
         0,
         (wchar_t *)v34[0],
         0,
         0);
  if ( v15 )
  {
    RevertToSelf();
    v15 = 0;
  }
  if ( v9 < 0 )
    goto LABEL_60;
  v9 = COCATpTransport::ParseReqUploadResponse((CTpResponseMessage *)v37);
  if ( v9 < 0 )
    goto LABEL_60;
  if ( (_DWORD)v40 )
  {
    *v14 = 1;
    v9 = 1769483;
    goto LABEL_60;
  }
  if ( v33[0] == v33[1] )
  {
    v9 = 1;
    goto LABEL_60;
  }
  DeviceTicketHeader = CTransport::EventGetUploadCab(this, v31, *((void **)this + 5), 0);
  v9 = DeviceTicketHeader;
  if ( DeviceTicketHeader < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v11 = 17;
    goto LABEL_5;
  }
  v18 = v31[0];
  if ( !v31[0] )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(LODWORD(v31[0]) + 18),
        WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
    goto LABEL_60;
  }
  v19 = L"zip";
  if ( !*((_DWORD *)v31[0] + 4) )
    v19 = L"cab";
  v20 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v31[0] + 32LL))(v31[0]);
  v9 = COCATpTransport::PrepareCabUploadRequest(
         *((struct CReport **)this + 6),
         L"minidump",
         0,
         v33[0],
         v20,
         v19,
         1,
         0,
         (struct CTpRequestMessage *)v38);
  if ( v9 >= 0 )
  {
    v21 = 0;
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
    {
      v21 = 2;
    }
    v22 = *((_QWORD *)this + 6);
    v23 = *(_QWORD *)(v22 + 52056);
    if ( v23 )
      v15 = ImpersonateLoggedOnUser(*(HANDLE *)(v22 + 52056));
    v9 = CTpTransport::DoExchange(
           (struct CTpRequestMessage *)v38,
           v18,
           (CTpResponseMessage *)v36,
           (__int64)&COCATpTransport::tpCommandConstructors,
           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           v21,
           0,
           v23,
           *((void **)this + 5),
           (COCATpTransport *)((char *)this + 192),
           (wchar_t *)L"data-upload/minidump",
           0,
           (wchar_t *)v34[0],
           (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
           0);
    if ( v15 )
      RevertToSelf();
    if ( v9 >= 0 )
    {
      v24 = a5;
      v25 = v41;
      v9 = COCATpTransport::ParseCabUploadResponse(
             (CTpResponseMessage *)v36,
             (CResponse *)(*((_QWORD *)this + 6) + 8LL),
             a4,
             (__int64)a5,
             (__int64)&v40,
             (__int64)v32);
      if ( v9 >= 0 )
      {
        CDataRequest::ReadRegistryValues(
          v25,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug\\DataRequest");
        DeviceTicketHeader = COCATpTransport::HandleAsyncStage2Epilog(this, v32[0], *(const wchar_t **)a4, *v24, 0);
        v9 = DeviceTicketHeader;
        if ( DeviceTicketHeader != 1769476 )
        {
          if ( DeviceTicketHeader >= 0 )
          {
            v26 = CReport::AddStateParam(*((CReport **)this + 6), L"Transport.DoneStage1", L"1");
            if ( v26 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
                (unsigned int)v26);
            v9 = 0;
            goto LABEL_60;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_60;
          v11 = 19;
          goto LABEL_5;
        }
      }
    }
  }
LABEL_60:
  if ( v9 < 0 || v9 == 1769476 )
  {
    for ( i = 0; ; i = v29 + 1 )
    {
      v28 = (CReport *)*((_QWORD *)this + 6);
      if ( i >= (unsigned int)((__int64)(*((_QWORD *)v28 + 728) - *((_QWORD *)v28 + 727)) >> 3) )
        break;
      v40 = 0;
      if ( (int)CReport::GetFileByIndex(v28, i, &v40) < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 21;
          v12 = (unsigned int)v9;
          goto LABEL_69;
        }
        goto LABEL_60;
      }
      *((_DWORD *)v40 + 1) &= ~0x80000u;
    }
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v36);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v38);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v37);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180083cfc  mov     rax, rsp
0x180083cff  mov     [rax+20h], rbx
0x180083d03  mov     [rax+18h], r8
0x180083d07  mov     [rax+10h], rdx
0x180083d0b  push    rbp
0x180083d0c  push    rsi
0x180083d0d  push    rdi
0x180083d0e  push    r12
0x180083d10  push    r13
0x180083d12  push    r14
0x180083d14  push    r15
0x180083d16  lea     rbp, [rax-778h]
0x180083d1d  sub     rsp, 840h
0x180083d24  mov     r13, r9
0x180083d27  mov     rdi, rcx
0x180083d2a  xor     r15d, r15d
0x180083d2d  mov     [rbp+770h+var_7E8], r15
0x180083d31  lea     rcx, [rbp+770h+var_3A0]; this
0x180083d38  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180083d3d  nop
0x180083d3e  lea     rcx, [rbp+770h+var_738]; this
0x180083d42  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180083d47  nop
0x180083d48  lea     rcx, [rbp+770h+var_710]; this
0x180083d4c  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180083d51  nop
0x180083d52  lea     rcx, [rbp+770h+var_758]; this
0x180083d56  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180083d5b  nop
0x180083d5c  lea     rcx, [rbp+770h+var_7B8]; void *
0x180083d60  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d65  nop
0x180083d66  mov     [rbp+770h+var_7E0], r15
0x180083d6a  mov     dword ptr [rbp+770h+arg_0], r15d
0x180083d71  lea     rcx, [rbp+770h+var_798]; void *
0x180083d75  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d7a  nop
0x180083d7b  lea     rcx, [rbp+770h+var_7D8]; void *
0x180083d7f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d84  nop
0x180083d85  lea     rcx, [rbp+770h+var_778]; void *
0x180083d89  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180083d8e  nop
0x180083d8f  mov     [rbp+770h+var_7F0], r15d
0x180083d93  mov     rdx, [rdi+30h]
0x180083d97  lea     r9, [rdx+0CAD0h]
0x180083d9e  mov     r8d, [rdx+0CACCh]
0x180083da5  mov     edx, [rdx+0CAC8h]
0x180083dab  lea     rcx, [rbp+770h+var_3A0]
0x180083db2  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180083db7  mov     ebx, eax
0x180083db9  lea     r14, WPP_GLOBAL_Control
0x180083dc0  test    eax, eax
0x180083dc2  jns     short loc_180083DEA
0x180083dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180083dcb  cmp     rcx, r14
0x180083dce  jz      loc_1800842D7
0x180083dd4  test    byte ptr [rcx+1Ch], 1
0x180083dd8  jz      loc_1800842D7
0x180083dde  lea     edx, [r15+0Dh]
0x180083de2  mov     r9d, eax
0x180083de5  jmp     loc_180084346
0x180083dea  mov     rdx, [rdi+30h]
0x180083dee  lea     r9, [rdx+0CAD0h]
0x180083df5  mov     r8d, [rdx+0CACCh]
0x180083dfc  mov     edx, [rdx+0CAC8h]
0x180083e02  lea     rcx, [rbp+770h+var_710]
0x180083e06  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180083e0b  mov     ebx, eax
0x180083e0d  test    eax, eax
0x180083e0f  jns     short loc_180083E32
0x180083e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e18  cmp     rcx, r14
0x180083e1b  jz      loc_1800842D7
0x180083e21  test    byte ptr [rcx+1Ch], 1
0x180083e25  jz      loc_1800842D7
0x180083e2b  mov     edx, 0Eh
0x180083e30  jmp     short loc_180083DE2
0x180083e32  mov     rcx, [r13+0]
0x180083e36  mov     [r13+8], rcx
0x180083e3a  mov     [rcx], r15w
0x180083e3e  mov     rax, [rbp+770h+arg_20]
0x180083e45  mov     [rax], r15
0x180083e48  mov     rsi, [rbp+770h+arg_28]
0x180083e4f  mov     [rsi], r15d
0x180083e52  lea     r9, [rbp+770h+var_7F0]
0x180083e56  lea     r8, [rbp+770h+var_778]
0x180083e5a  lea     rdx, [rbp+770h+var_7D8]
0x180083e5e  mov     rcx, rdi; this
0x180083e61  call    ?HandleAsyncStage2Prolog@COCATpTransport@@IEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAH@Z; COCATpTransport::HandleAsyncStage2Prolog(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *)
0x180083e66  mov     ebx, eax
0x180083e68  test    eax, eax
0x180083e6a  jns     short loc_180083E90
0x180083e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e73  cmp     rcx, r14
0x180083e76  jz      loc_1800842D7
0x180083e7c  test    byte ptr [rcx+1Ch], 1
0x180083e80  jz      loc_1800842D7
0x180083e86  mov     edx, 0Fh
0x180083e8b  jmp     loc_180083DE2
0x180083e90  mov     rdx, [rdi+28h]
0x180083e94  lea     rcx, [rbp+770h+var_798]
0x180083e98  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180083e9d  mov     ebx, eax
0x180083e9f  test    eax, eax
0x180083ea1  jns     short loc_180083ECB
0x180083ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180083eaa  cmp     rcx, r14
0x180083ead  jz      loc_1800842D7
0x180083eb3  mov     edx, 2
0x180083eb8  test    [rcx+1Ch], dl
0x180083ebb  jz      loc_1800842D7
0x180083ec1  mov     edx, 10h
0x180083ec6  jmp     loc_180083DE2
0x180083ecb  mov     r14d, r15d
0x180083ece  mov     r12d, [rbp+770h+var_7F0]
0x180083ed2  test    r12d, r12d
0x180083ed5  jnz     loc_180083FEE
0x180083edb  lea     rdx, [rbp+770h+var_3A0]; this
0x180083ee2  mov     rcx, [rdi+30h]; struct CReport *
0x180083ee6  call    ?PrepareReqUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareReqUploadRequest(CReport *,CTpRequestMessage *)
0x180083eeb  mov     ebx, eax
0x180083eed  test    eax, eax
0x180083eef  js      loc_1800842D0
0x180083ef5  mov     rax, [rdi+30h]
0x180083ef9  mov     rbx, [rax+0CB58h]
0x180083f00  test    rbx, rbx
0x180083f03  jz      short loc_180083F11
0x180083f05  mov     rcx, rbx; hToken
0x180083f08  call    cs:__imp_ImpersonateLoggedOnUser
0x180083f0e  mov     r14d, eax
0x180083f11  mov     r8, [rbp+770h+var_798]
0x180083f15  lea     r9, [rdi+0C0h]
0x180083f1c  mov     rcx, rdi
0x180083f1f  lea     rdx, [rdi+20h]
0x180083f23  neg     rcx
0x180083f26  sbb     r10, r10
0x180083f29  and     r10, rdx
0x180083f2c  mov     [rsp+70h], r15d; int
0x180083f31  mov     [rsp+870h+var_808], r15; __int64
0x180083f36  mov     [rsp+870h+var_810], r8; __int64
0x180083f3b  mov     qword ptr [rsp+870h+var_818], r15; int
0x180083f40  lea     rax, aRequestUploadM; "request-upload/minidump"
0x180083f47  mov     [rsp+870h+var_820], rax; __int64
0x180083f4c  mov     [rsp+870h+var_828], r9; __int64
0x180083f51  mov     rax, [rdi+28h]
0x180083f55  mov     [rsp+870h+var_830], rax; __int64
0x180083f5a  mov     [rsp+870h+var_838], rbx; __int64
0x180083f5f  mov     [rsp+870h+var_840], r15; int
0x180083f64  mov     dword ptr [rsp+870h+var_848], r15d; int
0x180083f69  mov     [rsp+870h+var_850], r10; struct ITpCallbacks *
0x180083f6e  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180083f75  lea     r8, [rbp+770h+var_738]
0x180083f79  xor     edx, edx
0x180083f7b  lea     rcx, [rbp+770h+var_3A0]; this
0x180083f82  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180083f87  mov     ebx, eax
0x180083f89  test    r14d, r14d
0x180083f8c  jz      short loc_180083F97
0x180083f8e  call    cs:__imp_RevertToSelf
0x180083f94  mov     r14d, r15d
0x180083f97  test    ebx, ebx
0x180083f99  js      loc_1800842D0
0x180083f9f  lea     r9, [rbp+770h+arg_0]
0x180083fa6  lea     r8, [rbp+770h+var_7E0]
0x180083faa  lea     rdx, [rbp+770h+var_7B8]
0x180083fae  lea     rcx, [rbp+770h+var_738]; this
0x180083fb2  call    ?ParseReqUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z; COCATpTransport::ParseReqUploadResponse(CTpResponseMessage *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)
0x180083fb7  mov     ebx, eax
0x180083fb9  test    eax, eax
0x180083fbb  js      loc_1800842D0
0x180083fc1  cmp     dword ptr [rbp+770h+arg_0], r15d
0x180083fc8  jz      short loc_180083FDA
0x180083fca  mov     dword ptr [rsi], 1
0x180083fd0  mov     ebx, 1B000Bh
0x180083fd5  jmp     loc_1800842D0
0x180083fda  mov     rax, [rbp+770h+var_7B0]
0x180083fde  cmp     [rbp+770h+var_7B8], rax
0x180083fe2  jnz     short loc_180083FEE
0x180083fe4  mov     ebx, 1
0x180083fe9  jmp     loc_1800842D0
0x180083fee  xor     r9d, r9d; int
0x180083ff1  mov     r8, [rdi+28h]; void *
0x180083ff5  lea     rdx, [rbp+770h+var_7E8]; struct CReportCabStream **
0x180083ff9  mov     rcx, rdi; this
0x180083ffc  call    ?EventGetUploadCab@CTransport@@IEAAJPEAPEAVCReportCabStream@@PEAXH@Z; CTransport::EventGetUploadCab(CReportCabStream * *,void *,int)
0x180084001  mov     ebx, eax
0x180084003  test    eax, eax
0x180084005  jns     short loc_180084032
0x180084007  mov     rcx, cs:WPP_GLOBAL_Control
0x18008400e  lea     r14, WPP_GLOBAL_Control
0x180084015  cmp     rcx, r14
0x180084018  jz      loc_1800842D7
0x18008401e  test    byte ptr [rcx+1Ch], 1
0x180084022  jz      loc_1800842D7
0x180084028  mov     edx, 11h
0x18008402d  jmp     loc_180083DE2
0x180084032  mov     r15, [rbp+770h+var_7E8]
0x180084036  test    r15, r15
0x180084039  jnz     short loc_180084070
0x18008403b  mov     rcx, cs:WPP_GLOBAL_Control
0x180084042  lea     r14, WPP_GLOBAL_Control
0x180084049  cmp     rcx, r14
0x18008404c  jz      short loc_180084068
0x18008404e  test    byte ptr [rcx+1Ch], 1
0x180084052  jz      short loc_180084068
0x180084054  lea     edx, [r15+12h]
0x180084058  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x18008405f  mov     rcx, [rcx+10h]
0x180084063  call    WPP_SF_
0x180084068  xor     r15d, r15d
0x18008406b  jmp     loc_1800842D7
0x180084070  test    r12d, r12d
0x180084073  jnz     short loc_1800840A2
0x180084075  lea     rax, aCab_1; "cab"
0x18008407c  lea     rbx, aZip_0; "zip"
0x180084083  cmp     [r15+10h], r12d
0x180084087  cmovz   rbx, rax
0x18008408b  mov     rax, [r15]
0x18008408e  mov     rcx, r15
0x180084091  mov     rax, [rax+20h]
0x180084095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008409a  mov     r9, [rbp+770h+var_7B8]
0x18008409e  xor     ecx, ecx
0x1800840a0  jmp     short loc_1800840AE
0x1800840a2  mov     r9, [rbp+770h+var_778]; wchar_t *
0x1800840a6  xor     eax, eax
0x1800840a8  xor     ebx, ebx
0x1800840aa  mov     rcx, [rbp+770h+var_7D8]
0x1800840ae  lea     rdx, [rbp+770h+var_710]
0x1800840b2  mov     [rsp+870h+var_830], rdx; struct CTpRequestMessage *
0x1800840b7  mov     [rsp+870h+var_838], rcx; wchar_t *
0x1800840bc  mov     dword ptr [rsp+870h+var_840], 1; int
0x1800840c4  mov     [rsp+870h+var_848], rbx; wchar_t *
0x1800840c9  mov     [rsp+870h+var_850], rax; unsigned __int64
0x1800840ce  xor     r8d, r8d; wchar_t *
0x1800840d1  lea     rdx, aMinidump_0; "minidump"
0x1800840d8  mov     rcx, [rdi+30h]; struct CReport *
0x1800840dc  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x1800840e1  mov     ebx, eax
0x1800840e3  test    eax, eax
0x1800840e5  js      loc_1800842CD
0x1800840eb  xor     ebx, ebx
0x1800840ed  mov     rcx, [rdi+30h]
0x1800840f1  add     rcx, 0B660h; this
0x1800840f8  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x1800840fd  test    eax, eax
0x1800840ff  jz      short loc_180084112
0x180084101  mov     rcx, [rdi+30h]; this
0x180084105  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x18008410a  lea     edx, [rbx+2]
0x18008410d  test    eax, eax
0x18008410f  cmovz   ebx, edx
0x180084112  mov     rax, [rdi+30h]
0x180084116  mov     rsi, [rax+0CB58h]
0x18008411d  test    rsi, rsi
0x180084120  jz      short loc_18008412E
0x180084122  mov     rcx, rsi; hToken
0x180084125  call    cs:__imp_ImpersonateLoggedOnUser
0x18008412b  mov     r14d, eax
0x18008412e  mov     r8, [rbp+770h+var_798]
0x180084132  mov     r10, [rdi+28h]
0x180084136  mov     rax, rdi
0x180084139  lea     rcx, [rdi+20h]
0x18008413d  neg     rax
0x180084140  sbb     r11, r11
0x180084143  and     r11, rcx
0x180084146  xor     edx, edx
0x180084148  test    r12d, r12d
0x18008414b  cmovz   rdx, r15
0x18008414f  lea     rax, [rdi+0C0h]
0x180084156  xor     r15d, r15d
0x180084159  mov     [rsp+70h], r15d; int
0x18008415e  lea     rcx, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180084165  mov     [rsp+870h+var_808], rcx; __int64
0x18008416a  mov     [rsp+870h+var_810], r8; __int64
0x18008416f  mov     qword ptr [rsp+870h+var_818], r15; int
0x180084174  lea     rcx, aDataUploadMini; "data-upload/minidump"
0x18008417b  mov     [rsp+870h+var_820], rcx; __int64
0x180084180  mov     [rsp+870h+var_828], rax; __int64
0x180084185  mov     [rsp+870h+var_830], r10; __int64
0x18008418a  mov     [rsp+870h+var_838], rsi; __int64
0x18008418f  mov     [rsp+870h+var_840], r15; int
0x180084194  mov     dword ptr [rsp+870h+var_848], ebx; int
0x180084198  mov     [rsp+870h+var_850], r11; struct ITpCallbacks *
0x18008419d  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x1800841a4  lea     r8, [rbp+770h+var_758]
0x1800841a8  lea     rcx, [rbp+770h+var_710]; this
0x1800841ac  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x1800841b1  mov     ebx, eax
0x1800841b3  test    r14d, r14d
0x1800841b6  jz      short loc_1800841BE
0x1800841b8  call    cs:__imp_RevertToSelf
0x1800841be  test    ebx, ebx
0x1800841c0  js      loc_1800842D0
0x1800841c6  mov     rdx, [rdi+30h]
0x1800841ca  add     rdx, 8; CResponse *
0x1800841ce  lea     rax, [rbp+770h+var_7D8]
0x1800841d2  mov     [rsp+870h+var_838], rax; __int64
0x1800841d7  lea     rax, [rbp+770h+arg_0]
  ... truncated ...
```
