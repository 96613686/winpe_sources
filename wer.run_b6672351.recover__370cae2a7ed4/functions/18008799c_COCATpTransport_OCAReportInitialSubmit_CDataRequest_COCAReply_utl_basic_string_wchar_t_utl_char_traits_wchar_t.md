# COCATpTransport::OCAReportInitialSubmit(CDataRequest *,COCAReply *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)

- ea: `0x18008799c`
- end: `0x180088083`
- name: `?OCAReportInitialSubmit@COCATpTransport@@IEAAJPEAVCDataRequest@@PEAVCOCAReply@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z`
- size: `1767`
- prototype: `__int64 __usercall@<rax>(COCATpTransport *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800863ec`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000db80`
- `0x180020680`
- `0x180025444`
- `0x180025848`
- `0x18003aed8`
- `0x18003b7e0`
- `0x18003e2b4`
- `0x18003fc6c`
- `0x1800412b4`
- `0x18004761c`
- `0x18004ab74`
- `0x18004eb28`
- `0x180073e20`
- `0x18007543c`
- `0x180086b60`
- `0x180086f7c`
- `0x18008799c`
- `0x18008884c`
- `0x180088cec`
- `0x180089138`
- `0x180093454`
- `0x1800934d0`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087c34`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087e6a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087c34`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087e6a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087ba8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087dd1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087ba8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087dd1`

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
0x18008799c  mov     rax, rsp
0x18008799f  mov     [rax+20h], rbx
0x1800879a3  mov     [rax+18h], r8
0x1800879a7  mov     [rax+10h], rdx
0x1800879ab  push    rbp
0x1800879ac  push    rsi
0x1800879ad  push    rdi
0x1800879ae  push    r12
0x1800879b0  push    r13
0x1800879b2  push    r14
0x1800879b4  push    r15
0x1800879b6  lea     rbp, [rax-778h]
0x1800879bd  sub     rsp, 840h
0x1800879c4  mov     r13, r9
0x1800879c7  mov     rdi, rcx
0x1800879ca  xor     r15d, r15d
0x1800879cd  mov     [rbp+770h+var_7E8], r15
0x1800879d1  lea     rcx, [rbp+770h+var_3A0]; this
0x1800879d8  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800879dd  nop
0x1800879de  lea     rcx, [rbp+770h+var_738]; this
0x1800879e2  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x1800879e7  nop
0x1800879e8  lea     rcx, [rbp+770h+var_710]; this
0x1800879ec  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800879f1  nop
0x1800879f2  lea     rcx, [rbp+770h+var_758]; this
0x1800879f6  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x1800879fb  nop
0x1800879fc  lea     rcx, [rbp+770h+var_7B8]; void *
0x180087a00  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180087a05  nop
0x180087a06  mov     [rbp+770h+var_7E0], r15
0x180087a0a  mov     dword ptr [rbp+770h+arg_0], r15d
0x180087a11  lea     rcx, [rbp+770h+var_798]; void *
0x180087a15  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180087a1a  nop
0x180087a1b  lea     rcx, [rbp+770h+var_7D8]; void *
0x180087a1f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180087a24  nop
0x180087a25  lea     rcx, [rbp+770h+var_778]; void *
0x180087a29  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180087a2e  nop
0x180087a2f  mov     [rbp+770h+var_7F0], r15d
0x180087a33  mov     rdx, [rdi+30h]
0x180087a37  lea     r9, [rdx+0CAD0h]
0x180087a3e  mov     r8d, [rdx+0CACCh]
0x180087a45  mov     edx, [rdx+0CAC8h]
0x180087a4b  lea     rcx, [rbp+770h+var_3A0]
0x180087a52  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180087a57  mov     ebx, eax
0x180087a59  lea     r14, WPP_GLOBAL_Control
0x180087a60  test    eax, eax
0x180087a62  jns     short loc_180087A8A
0x180087a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a6b  cmp     rcx, r14
0x180087a6e  jz      loc_180087F8F
0x180087a74  test    byte ptr [rcx+1Ch], 1
0x180087a78  jz      loc_180087F8F
0x180087a7e  lea     edx, [r15+0Dh]
0x180087a82  mov     r9d, eax
0x180087a85  jmp     loc_180087FFE
0x180087a8a  mov     rdx, [rdi+30h]
0x180087a8e  lea     r9, [rdx+0CAD0h]
0x180087a95  mov     r8d, [rdx+0CACCh]
0x180087a9c  mov     edx, [rdx+0CAC8h]
0x180087aa2  lea     rcx, [rbp+770h+var_710]
0x180087aa6  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180087aab  mov     ebx, eax
0x180087aad  test    eax, eax
0x180087aaf  jns     short loc_180087AD2
0x180087ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ab8  cmp     rcx, r14
0x180087abb  jz      loc_180087F8F
0x180087ac1  test    byte ptr [rcx+1Ch], 1
0x180087ac5  jz      loc_180087F8F
0x180087acb  mov     edx, 0Eh
0x180087ad0  jmp     short loc_180087A82
0x180087ad2  mov     rcx, [r13+0]
0x180087ad6  mov     [r13+8], rcx
0x180087ada  mov     [rcx], r15w
0x180087ade  mov     rax, [rbp+770h+arg_20]
0x180087ae5  mov     [rax], r15
0x180087ae8  mov     rsi, [rbp+770h+arg_28]
0x180087aef  mov     [rsi], r15d
0x180087af2  lea     r9, [rbp+770h+var_7F0]
0x180087af6  lea     r8, [rbp+770h+var_778]
0x180087afa  lea     rdx, [rbp+770h+var_7D8]
0x180087afe  mov     rcx, rdi; this
0x180087b01  call    ?HandleAsyncStage2Prolog@COCATpTransport@@IEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAH@Z; COCATpTransport::HandleAsyncStage2Prolog(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *)
0x180087b06  mov     ebx, eax
0x180087b08  test    eax, eax
0x180087b0a  jns     short loc_180087B30
0x180087b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b13  cmp     rcx, r14
0x180087b16  jz      loc_180087F8F
0x180087b1c  test    byte ptr [rcx+1Ch], 1
0x180087b20  jz      loc_180087F8F
0x180087b26  mov     edx, 0Fh
0x180087b2b  jmp     loc_180087A82
0x180087b30  mov     rdx, [rdi+28h]
0x180087b34  lea     rcx, [rbp+770h+var_798]
0x180087b38  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180087b3d  mov     ebx, eax
0x180087b3f  test    eax, eax
0x180087b41  jns     short loc_180087B6B
0x180087b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b4a  cmp     rcx, r14
0x180087b4d  jz      loc_180087F8F
0x180087b53  mov     edx, 2
0x180087b58  test    [rcx+1Ch], dl
0x180087b5b  jz      loc_180087F8F
0x180087b61  mov     edx, 10h
0x180087b66  jmp     loc_180087A82
0x180087b6b  mov     r14d, r15d
0x180087b6e  mov     r12d, [rbp+770h+var_7F0]
0x180087b72  test    r12d, r12d
0x180087b75  jnz     loc_180087C9A
0x180087b7b  lea     rdx, [rbp+770h+var_3A0]; this
0x180087b82  mov     rcx, [rdi+30h]; struct CReport *
0x180087b86  call    ?PrepareReqUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareReqUploadRequest(CReport *,CTpRequestMessage *)
0x180087b8b  mov     ebx, eax
0x180087b8d  test    eax, eax
0x180087b8f  js      loc_180087F88
0x180087b95  mov     rax, [rdi+30h]
0x180087b99  mov     rbx, [rax+0CB58h]
0x180087ba0  test    rbx, rbx
0x180087ba3  jz      short loc_180087BB7
0x180087ba5  mov     rcx, rbx; hToken
0x180087ba8  call    cs:__imp_ImpersonateLoggedOnUser
0x180087baf  nop     dword ptr [rax+rax+00h]
0x180087bb4  mov     r14d, eax
0x180087bb7  mov     r8, [rbp+770h+var_798]
0x180087bbb  lea     r9, [rdi+0C0h]
0x180087bc2  mov     rcx, rdi
0x180087bc5  lea     rdx, [rdi+20h]
0x180087bc9  neg     rcx
0x180087bcc  sbb     r10, r10
0x180087bcf  and     r10, rdx
0x180087bd2  mov     [rsp+70h], r15d; int
0x180087bd7  mov     [rsp+870h+var_808], r15; __int64
0x180087bdc  mov     [rsp+870h+var_810], r8; __int64
0x180087be1  mov     qword ptr [rsp+870h+var_818], r15; int
0x180087be6  lea     rax, aRequestUploadM; "request-upload/minidump"
0x180087bed  mov     [rsp+870h+var_820], rax; __int64
0x180087bf2  mov     [rsp+870h+var_828], r9; __int64
0x180087bf7  mov     rax, [rdi+28h]
0x180087bfb  mov     [rsp+870h+var_830], rax; __int64
0x180087c00  mov     [rsp+870h+var_838], rbx; __int64
0x180087c05  mov     [rsp+870h+var_840], r15; int
0x180087c0a  mov     dword ptr [rsp+870h+var_848], r15d; int
0x180087c0f  mov     [rsp+870h+var_850], r10; struct ITpCallbacks *
0x180087c14  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180087c1b  lea     r8, [rbp+770h+var_738]
0x180087c1f  xor     edx, edx
0x180087c21  lea     rcx, [rbp+770h+var_3A0]; this
0x180087c28  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180087c2d  mov     ebx, eax
0x180087c2f  test    r14d, r14d
0x180087c32  jz      short loc_180087C43
0x180087c34  call    cs:__imp_RevertToSelf
0x180087c3b  nop     dword ptr [rax+rax+00h]
0x180087c40  mov     r14d, r15d
0x180087c43  test    ebx, ebx
0x180087c45  js      loc_180087F88
0x180087c4b  lea     r9, [rbp+770h+arg_0]
0x180087c52  lea     r8, [rbp+770h+var_7E0]
0x180087c56  lea     rdx, [rbp+770h+var_7B8]
0x180087c5a  lea     rcx, [rbp+770h+var_738]; this
0x180087c5e  call    ?ParseReqUploadResponse@COCATpTransport@@KAJPEAVCTpResponseMessage@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z; COCATpTransport::ParseReqUploadResponse(CTpResponseMessage *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)
0x180087c63  mov     ebx, eax
0x180087c65  test    eax, eax
0x180087c67  js      loc_180087F88
0x180087c6d  cmp     dword ptr [rbp+770h+arg_0], r15d
0x180087c74  jz      short loc_180087C86
0x180087c76  mov     dword ptr [rsi], 1
0x180087c7c  mov     ebx, 1B000Bh
0x180087c81  jmp     loc_180087F88
0x180087c86  mov     rax, [rbp+770h+var_7B0]
0x180087c8a  cmp     [rbp+770h+var_7B8], rax
0x180087c8e  jnz     short loc_180087C9A
0x180087c90  mov     ebx, 1
0x180087c95  jmp     loc_180087F88
0x180087c9a  xor     r9d, r9d; int
0x180087c9d  mov     r8, [rdi+28h]; void *
0x180087ca1  lea     rdx, [rbp+770h+var_7E8]; struct CReportCabStream **
0x180087ca5  mov     rcx, rdi; this
0x180087ca8  call    ?EventGetUploadCab@CTransport@@IEAAJPEAPEAVCReportCabStream@@PEAXH@Z; CTransport::EventGetUploadCab(CReportCabStream * *,void *,int)
0x180087cad  mov     ebx, eax
0x180087caf  test    eax, eax
0x180087cb1  jns     short loc_180087CDE
0x180087cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180087cba  lea     r14, WPP_GLOBAL_Control
0x180087cc1  cmp     rcx, r14
0x180087cc4  jz      loc_180087F8F
0x180087cca  test    byte ptr [rcx+1Ch], 1
0x180087cce  jz      loc_180087F8F
0x180087cd4  mov     edx, 11h
0x180087cd9  jmp     loc_180087A82
0x180087cde  mov     r15, [rbp+770h+var_7E8]
0x180087ce2  test    r15, r15
0x180087ce5  jnz     short loc_180087D1C
0x180087ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180087cee  lea     r14, WPP_GLOBAL_Control
0x180087cf5  cmp     rcx, r14
0x180087cf8  jz      short loc_180087D14
0x180087cfa  test    byte ptr [rcx+1Ch], 1
0x180087cfe  jz      short loc_180087D14
0x180087d00  lea     edx, [r15+12h]
0x180087d04  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180087d0b  mov     rcx, [rcx+10h]
0x180087d0f  call    WPP_SF_
0x180087d14  xor     r15d, r15d
0x180087d17  jmp     loc_180087F8F
0x180087d1c  test    r12d, r12d
0x180087d1f  jnz     short loc_180087D4E
0x180087d21  lea     rax, aCab_1; "cab"
0x180087d28  lea     rbx, aZip_0; "zip"
0x180087d2f  cmp     [r15+10h], r12d
0x180087d33  cmovz   rbx, rax
0x180087d37  mov     rax, [r15]
0x180087d3a  mov     rcx, r15
0x180087d3d  mov     rax, [rax+20h]
0x180087d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d46  mov     r9, [rbp+770h+var_7B8]
0x180087d4a  xor     ecx, ecx
0x180087d4c  jmp     short loc_180087D5A
0x180087d4e  mov     r9, [rbp+770h+var_778]; wchar_t *
0x180087d52  xor     eax, eax
0x180087d54  xor     ebx, ebx
0x180087d56  mov     rcx, [rbp+770h+var_7D8]
0x180087d5a  lea     rdx, [rbp+770h+var_710]
0x180087d5e  mov     [rsp+870h+var_830], rdx; struct CTpRequestMessage *
0x180087d63  mov     [rsp+870h+var_838], rcx; wchar_t *
0x180087d68  mov     dword ptr [rsp+870h+var_840], 1; int
0x180087d70  mov     [rsp+870h+var_848], rbx; wchar_t *
0x180087d75  mov     [rsp+870h+var_850], rax; unsigned __int64
0x180087d7a  xor     r8d, r8d; wchar_t *
0x180087d7d  lea     rdx, aMinidump_0; "minidump"
0x180087d84  mov     rcx, [rdi+30h]; struct CReport *
0x180087d88  call    ?PrepareCabUploadRequest@COCATpTransport@@KAJPEAVCReport@@PEB_W11_K1H1PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareCabUploadRequest(CReport *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,int,wchar_t const *,CTpRequestMessage *)
0x180087d8d  mov     ebx, eax
0x180087d8f  test    eax, eax
0x180087d91  js      loc_180087F85
0x180087d97  xor     ebx, ebx
0x180087d99  mov     rcx, [rdi+30h]
0x180087d9d  add     rcx, 0B660h; this
0x180087da4  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x180087da9  test    eax, eax
0x180087dab  jz      short loc_180087DBE
0x180087dad  mov     rcx, [rdi+30h]; this
0x180087db1  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180087db6  lea     edx, [rbx+2]
0x180087db9  test    eax, eax
0x180087dbb  cmovz   ebx, edx
0x180087dbe  mov     rax, [rdi+30h]
0x180087dc2  mov     rsi, [rax+0CB58h]
0x180087dc9  test    rsi, rsi
0x180087dcc  jz      short loc_180087DE0
0x180087dce  mov     rcx, rsi; hToken
0x180087dd1  call    cs:__imp_ImpersonateLoggedOnUser
0x180087dd8  nop     dword ptr [rax+rax+00h]
0x180087ddd  mov     r14d, eax
0x180087de0  mov     r8, [rbp+770h+var_798]
0x180087de4  mov     r10, [rdi+28h]
0x180087de8  mov     rax, rdi
0x180087deb  lea     rcx, [rdi+20h]
0x180087def  neg     rax
0x180087df2  sbb     r11, r11
0x180087df5  and     r11, rcx
0x180087df8  xor     edx, edx
0x180087dfa  test    r12d, r12d
0x180087dfd  cmovz   rdx, r15
0x180087e01  lea     rax, [rdi+0C0h]
0x180087e08  xor     r15d, r15d
0x180087e0b  mov     [rsp+70h], r15d; int
0x180087e10  lea     rcx, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180087e17  mov     [rsp+870h+var_808], rcx; __int64
0x180087e1c  mov     [rsp+870h+var_810], r8; __int64
0x180087e21  mov     qword ptr [rsp+870h+var_818], r15; int
0x180087e26  lea     rcx, aDataUploadMini; "data-upload/minidump"
0x180087e2d  mov     [rsp+870h+var_820], rcx; __int64
0x180087e32  mov     [rsp+870h+var_828], rax; __int64
0x180087e37  mov     [rsp+870h+var_830], r10; __int64
0x180087e3c  mov     [rsp+870h+var_838], rsi; __int64
0x180087e41  mov     [rsp+870h+var_840], r15; int
0x180087e46  mov     dword ptr [rsp+870h+var_848], ebx; int
0x180087e4a  mov     [rsp+870h+var_850], r11; struct ITpCallbacks *
0x180087e4f  lea     r9, ?tpCommandConstructors@COCATpTransport@@1QBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZB; long (*const near * const COCATpTransport::tpCommandConstructors)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *)
0x180087e56  lea     r8, [rbp+770h+var_758]
0x180087e5a  lea     rcx, [rbp+770h+var_710]; this
0x180087e5e  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180087e63  mov     ebx, eax
0x180087e65  test    r14d, r14d
0x180087e68  jz      short loc_180087E76
0x180087e6a  call    cs:__imp_RevertToSelf
0x180087e71  nop     dword ptr [rax+rax+00h]
0x180087e76  test    ebx, ebx
0x180087e78  js      loc_180087F88
0x180087e7e  mov     rdx, [rdi+30h]
  ... truncated ...
```
