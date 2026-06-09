# CWatsonTpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *,CDataRequest const *)

- ea: `0x180088ef8`
- end: `0x1800899b9`
- name: `?UploadToAzure@CWatsonTpTransport@@AEAAJPEAVCReportCabStream@@PEB_W1PEBVCDataRequest@@@Z`
- size: `2753`
- prototype: `__int64 __fastcall(CWatsonTpTransport *this, struct CReportCabStream *, const wchar_t *, const wchar_t *, const struct CDataRequest *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024998`

## callees

- `0x180004198`
- `0x180009ad4`
- `0x18000bfbc`
- `0x18000c390`
- `0x18000dad0`
- `0x18001fe24`
- `0x18002556c`
- `0x18002c220`
- `0x1800303dc`
- `0x180039d00`
- `0x180039e60`
- `0x18003c24c`
- `0x18003df8c`
- `0x18003f364`
- `0x180045bdc`
- `0x1800489f0`
- `0x180048ee4`
- `0x18004c774`
- `0x180050db0`
- `0x1800720ec`
- `0x180072d90`
- `0x180087084`
- `0x1800875c4`
- `0x180088638`
- `0x180088a78`
- `0x180088ef8`
- `0x18008f36c`
- `0x18008f4e4`
- `0x1800a1d70`
- `0x1800a28b4`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800891e7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008984e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800891e7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008984e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800891b2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800892c9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089612`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800891b2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800892c9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089612`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089129`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089274`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008951d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089129`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089274`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008951d`

## string_xrefs

- `0x180089469`: `uploadcompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWatsonTpTransport::UploadToAzure(
        CWatsonTpTransport *this,
        struct CReportCabStream *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const struct CDataRequest *a5)
{
  struct IWerByteStream *v6; // r14
  unsigned int v8; // esi
  unsigned int v9; // r12d
  BOOL v10; // r15d
  struct CResponse *v11; // r13
  int v12; // eax
  int BlockIdFromString; // ebx
  int v14; // eax
  _WORD *v15; // rcx
  const wchar_t *v16; // rax
  wchar_t *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // r14
  __int64 v21; // rax
  const wchar_t **v22; // r12
  const wchar_t *v23; // rdx
  int v24; // eax
  wchar_t *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  int v28; // eax
  const wchar_t *v29; // rsi
  wchar_t *v30; // rbx
  __int64 v31; // rax
  int v32; // eax
  int v33; // esi
  struct ITpCallbacks *v34; // r13
  __int64 v35; // r8
  CTransport *v36; // rcx
  wchar_t *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r9
  __int64 v40; // rax
  int v41; // eax
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  wchar_t *v46; // [rsp+80h] [rbp-80h]
  BOOL v47; // [rsp+88h] [rbp-78h]
  unsigned int v48; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int DwordData; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v50; // [rsp+94h] [rbp-6Ch] BYREF
  _QWORD v51[2]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v52[8]; // [rsp+A8h] [rbp-58h] BYREF
  struct ITpCallbacks *v53; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h] BYREF
  struct IWerByteStream *v55; // [rsp+C8h] [rbp-38h]
  struct CDataRequest *v56; // [rsp+D0h] [rbp-30h] BYREF
  struct CResponse *v57; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v58; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v59[2]; // [rsp+E8h] [rbp-18h] BYREF
  _WORD v60[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v61[8]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  _BYTE v64[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v65[848]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v66[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v67[848]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v68; // [rsp+810h] [rbp+710h] BYREF
  int v69; // [rsp+818h] [rbp+718h]
  int v70; // [rsp+81Ch] [rbp+71Ch]

  v54 = (__int64)a4;
  v6 = a2;
  v55 = a2;
  v56 = a5;
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v66);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v61);
  v8 = 0;
  v9 = 0;
  v48 = 0;
  v10 = 0;
  v47 = 0;
  v50 = 0;
  v46 = 0;
  v11 = (struct CResponse *)(*((_QWORD *)this + 6) + 8LL);
  v57 = v11;
  v59[0] = v60;
  v59[1] = v60;
  v60[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v59, a3);
  DwordData = CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 6) + 51472LL));
  v68 = 257698037880000LL;
  v69 = 30000;
  v70 = 60000;
  while ( 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, ++v8);
    CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v64);
    CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v51);
    v12 = CTpRequestMessage::SetCommercialInfo(
            v64,
            *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
            *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
            *((_QWORD *)this + 6) + 51920LL);
    BlockIdFromString = v12;
    if ( v12 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_109;
      v38 = 21;
LABEL_107:
      v39 = (unsigned int)v12;
      goto LABEL_108;
    }
    v14 = OsInformation::Copy((OsInformation *)v65, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
    BlockIdFromString = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
          (unsigned int)v14);
      goto LABEL_109;
    }
    v15 = *(_WORD **)(*((_QWORD *)this + 6) + 6568LL);
    if ( !v15 || (v16 = L"renewsas", !*v15) )
      v16 = L"getdestination";
    v46 = (wchar_t *)v16;
    v17 = L"zip";
    if ( !*((_DWORD *)v6 + 4) )
      v17 = (wchar_t *)L"cab";
    v18 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, 0);
    v12 = CWatsonTpTransport::PrepareResumableUploadRequest(
            *((struct CReport **)this + 6),
            v11,
            v59[0],
            v18,
            v17,
            v46,
            0,
            (struct CTpRequestMessage *)v64);
    BlockIdFromString = v12;
    if ( v12 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v38 = 23;
        goto LABEL_107;
      }
LABEL_109:
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v51);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v64);
      goto LABEL_110;
    }
    if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
      && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
    {
      v9 |= 2u;
      v48 = v9;
    }
    v19 = *((_QWORD *)this + 6);
    v20 = *(void **)(v19 + 52056);
    if ( v20 )
    {
      v10 = ImpersonateLoggedOnUser(*(HANDLE *)(v19 + 52056));
      v47 = v10;
    }
    v53 = (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v64,
                          v53,
                          v9,
                          0,
                          (__int64)v20,
                          *((_QWORD *)this + 5),
                          (__int64)this + 80,
                          (__int64)v46,
                          0,
                          v54,
                          (__int64)&v68,
                          0);
    if ( v10 )
    {
      RevertToSelf();
      v10 = 0;
      v47 = 0;
    }
    if ( BlockIdFromString < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_109;
      v38 = 24;
      goto LABEL_82;
    }
    v12 = CWatsonTpTransport::ParseResumableUploadResponse((struct CTpResponseMessage *)v51, v11, 0);
    BlockIdFromString = v12;
    if ( v12 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v38 = 25;
        goto LABEL_107;
      }
      goto LABEL_109;
    }
    v21 = _wtoi64(*((const wchar_t **)v11 + 60));
    v22 = (const wchar_t **)((char *)v11 + 448);
    BlockIdFromString = CWatsonTpTransport::SaveResumeState(this, (char *)v11 + 448, v21);
    if ( BlockIdFromString < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_109;
      v38 = 26;
      goto LABEL_82;
    }
    v23 = (const wchar_t *)*((_QWORD *)v11 + 52);
    if ( !v23 || !*v23 )
    {
      BlockIdFromString = -2147024883;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_109;
      v38 = 27;
      goto LABEL_82;
    }
    v12 = CReport::SetCabUrl(*((CReport **)this + 6), v23);
    BlockIdFromString = v12;
    if ( v12 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v38 = 28;
        goto LABEL_107;
      }
      goto LABEL_109;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) = *((_QWORD *)v11 + 64);
    BlockIdFromString = CTpAzureStorageTransport::GetBlockIdFromString(*((const wchar_t **)v11 + 65), &v50);
    if ( BlockIdFromString < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_109;
      v38 = 29;
LABEL_82:
      v39 = (unsigned int)BlockIdFromString;
LABEL_108:
      WPP_SF_d(*((_QWORD *)v37 + 2), v38, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v39);
      goto LABEL_109;
    }
    v58 = 0;
    if ( v20 )
    {
      v10 = ImpersonateLoggedOnUser(v20);
      v47 = v10;
    }
    BlockIdFromString = CTpAzureStorageTransport::UploadFileToAzureUsingSAS(
                          *((LPCWSTR *)v11 + 52),
                          v48,
                          v55,
                          *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL),
                          *((void **)this + 5),
                          &v50,
                          &v58,
                          v53);
    if ( v10 )
    {
      RevertToSelf();
      v10 = 0;
      v47 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 6) + 6552LL) = v50;
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) += v58;
    CWatsonTpTransport::LogAzureExchangeEvent(this, BlockIdFromString);
    if ( BlockIdFromString < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
          (unsigned int)BlockIdFromString);
      if ( BlockIdFromString != -2145844845 || v8 >= DwordData )
        goto LABEL_109;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
        v59,
        *v22,
        (__int64)(*((_QWORD *)v11 + 57) - (_QWORD)*v22) >> 1);
    }
    CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v51);
    CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v64);
    if ( BlockIdFromString != -2145844845 || v8 >= DwordData )
      break;
    v9 = v48;
    v6 = v55;
  }
  v24 = CTpRequestMessage::SetCommercialInfo(
          v66,
          *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
          *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
          *((_QWORD *)this + 6) + 51920LL);
  BlockIdFromString = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_110;
    v26 = 31;
LABEL_46:
    v27 = (unsigned int)v24;
    goto LABEL_47;
  }
  v28 = OsInformation::Copy((OsInformation *)v67, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
  BlockIdFromString = v28;
  if ( v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v28);
    goto LABEL_110;
  }
  v29 = L"uploadcompleted";
  v46 = (wchar_t *)L"uploadcompleted";
  v30 = L"zip";
  if ( !*((_DWORD *)v55 + 4) )
    v30 = (wchar_t *)L"cab";
  v31 = (*(__int64 (**)(void))(*(_QWORD *)v55 + 32LL))();
  v32 = CWatsonTpTransport::PrepareResumableUploadRequest(
          *((struct CReport **)this + 6),
          v11,
          *v22,
          v31,
          v30,
          (wchar_t *)L"uploadcompleted",
          v56,
          (struct CTpRequestMessage *)v66);
  BlockIdFromString = v32;
  if ( v32 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v32);
    goto LABEL_111;
  }
  v33 = 3;
  if ( v20 )
    v47 = ImpersonateLoggedOnUser(v20);
  v34 = v53;
  while ( 2 )
  {
    --v33;
    v35 = v63;
    v63 = v62;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CTpResponseSection,utl::default_delete<CTpResponseSection>>>>(
      v25,
      v62,
      (v35 - v62) >> 3);
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v66,
                          v34,
                          v48,
                          0,
                          (__int64)v20,
                          *((_QWORD *)this + 5),
                          (__int64)this + 80,
                          (__int64)L"uploadcompleted",
                          0,
                          v54,
                          (__int64)&v68,
                          0);
    if ( BlockIdFromString >= 0 )
    {
LABEL_65:
      v36 = (CTransport *)WPP_GLOBAL_Control;
    }
    else
    {
      v36 = (CTransport *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
          (unsigned int)(3 - v33),
          BlockIdFromString);
        goto LABEL_65;
      }
    }
    if ( (unsigned int)CTransport::ShouldRetryExchange(v36, BlockIdFromString) && v33 )
      continue;
    break;
  }
  v11 = v57;
  if ( v47 )
  {
    RevertToSelf();
    v25 = WPP_GLOBAL_Control;
  }
  if ( BlockIdFromString < 0 )
  {
    if ( v25 != (wchar_t *)&WPP_GLOBAL_Control && (v25[14] & 1) != 0 )
    {
      v26 = 35;
      v27 = (unsigned int)BlockIdFromString;
LABEL_47:
      WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v27);
    }
    goto LABEL_110;
  }
  v24 = CWatsonTpTransport::ParseResumableUploadResponse((struct CTpResponseMessage *)v61, v11, 1);
  BlockIdFromString = v24;
  if ( v24 >= 0 )
  {
    CTransport::EventCabUploadComplete(this, v24);
    goto LABEL_110;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v26 = 36;
    goto LABEL_46;
  }
LABEL_110:
  v29 = v46;
LABEL_111:
  if ( BlockIdFromString >= 0 )
  {
    CReport::SetCabUrl(*((CReport **)this + 6), 0);
  }
  else
  {
    v40 = _wtoi64(*((const wchar_t **)v11 + 60));
    v41 = CWatsonTpTransport::SaveResumeState(this, (char *)v11 + 448, v40);
    if ( v41 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v41);
    v51[0] = v52;
    v51[1] = v52;
    v52[0] = 0;
    if ( (int)CReport::GetUniqueIdentifier(*((CReport **)this + 6), (__int64)v51) < 0 )
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
        v51,
        L"{00000000-0000-0000-0000-000000000000}");
    if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 0x400000000000LL) )
    {
      DwordData = BlockIdFromString;
      v48 = 0;
      v57 = (struct CResponse *)L"Watson";
      v56 = (struct CDataRequest *)v51[0];
      v54 = (__int64)v29;
      v53 = (struct ITpCallbacks *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v42,
        (unsigned int)&word_1800C9626,
        v43,
        v44,
        (__int64)&v53,
        (__int64)&v54,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v48,
        (__int64)&DwordData);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v51);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v59);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v61);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v66);
  return (unsigned int)BlockIdFromString;
}

```

## disassembly

```asm
0x180088ef8  push    rbp
0x180088efa  push    rbx
0x180088efb  push    rsi
0x180088efc  push    rdi
0x180088efd  push    r12
0x180088eff  push    r13
0x180088f01  push    r14
0x180088f03  push    r15
0x180088f05  lea     rbp, [rsp-738h]
0x180088f0d  sub     rsp, 838h
0x180088f14  mov     rax, cs:__security_cookie
0x180088f1b  xor     rax, rsp
0x180088f1e  mov     [rbp+770h+var_50], rax
0x180088f25  mov     [rbp+770h+var_7B0], r9
0x180088f29  mov     rbx, r8
0x180088f2c  mov     r14, rdx
0x180088f2f  mov     [rbp+770h+var_7A8], rdx
0x180088f33  mov     rdi, rcx
0x180088f36  mov     rax, [rbp+770h+arg_20]
0x180088f3d  mov     [rbp+770h+var_7A0], rax
0x180088f41  lea     rcx, [rbp+770h+var_3D0]; this
0x180088f48  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180088f4d  nop
0x180088f4e  lea     rcx, [rbp+770h+var_768]; this
0x180088f52  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180088f57  nop
0x180088f58  xor     esi, esi
0x180088f5a  mov     r12d, esi
0x180088f5d  mov     [rbp+770h+var_7E4], esi
0x180088f60  mov     r15d, esi
0x180088f63  mov     [rbp+770h+var_7E8], esi
0x180088f66  mov     [rbp+770h+var_7DC], esi
0x180088f69  mov     [rbp+770h+var_7F0], rsi
0x180088f6d  mov     r13, [rdi+30h]
0x180088f71  add     r13, 8
0x180088f75  mov     [rbp+770h+var_798], r13
0x180088f79  lea     rax, [rbp+770h+var_778]
0x180088f7d  mov     [rbp+770h+var_788], rax
0x180088f81  lea     rax, [rbp+770h+var_778]
0x180088f85  mov     [rbp+770h+var_780], rax
0x180088f89  mov     [rbp+770h+var_778], si
0x180088f8d  mov     rdx, rbx
0x180088f90  lea     rcx, [rbp+770h+var_788]
0x180088f94  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180088f99  mov     rcx, [rdi+30h]
0x180088f9d  add     rcx, 0C910h; this
0x180088fa4  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180088fa9  mov     [rbp+770h+var_7E0], eax
0x180088fac  mov     dword ptr [rbp+770h+var_60], 1D4C0h
0x180088fb6  mov     eax, 0EA60h
0x180088fbb  mov     dword ptr [rbp+770h+var_60+4], eax
0x180088fc1  mov     [rbp+770h+var_58], 7530h
0x180088fcb  mov     [rbp+770h+var_54], eax
0x180088fd1  lea     rax, WPP_GLOBAL_Control
0x180088fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180088fdf  cmp     rcx, rax
0x180088fe2  jz      short loc_180089004
0x180088fe4  test    byte ptr [rcx+1Ch], 4
0x180088fe8  jz      short loc_180089004
0x180088fea  inc     esi
0x180088fec  mov     edx, 14h
0x180088ff1  mov     r9d, esi
0x180088ff4  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180088ffb  mov     rcx, [rcx+10h]
0x180088fff  call    WPP_SF_d
0x180089004  lea     rcx, [rbp+770h+var_740]; this
0x180089008  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x18008900d  nop
0x18008900e  lea     rcx, [rbp+770h+var_7D8]; this
0x180089012  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180089017  nop
0x180089018  mov     rdx, [rdi+30h]
0x18008901c  lea     r9, [rdx+0CAD0h]
0x180089023  mov     r8d, [rdx+0CACCh]
0x18008902a  mov     edx, [rdx+0CAC8h]
0x180089030  lea     rcx, [rbp+770h+var_740]
0x180089034  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180089039  mov     ebx, eax
0x18008903b  test    eax, eax
0x18008903d  js      loc_1800897F6
0x180089043  mov     rdx, [rdi+30h]
0x180089047  add     rdx, 1790h; struct OsInformation *
0x18008904e  lea     rcx, [rbp+770h+var_720]; this
0x180089052  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x180089057  mov     ebx, eax
0x180089059  xor     edx, edx
0x18008905b  test    eax, eax
0x18008905d  js      loc_1800897C3
0x180089063  mov     rax, [rdi+30h]
0x180089067  mov     rcx, [rax+19A8h]
0x18008906e  test    rcx, rcx
0x180089071  jz      short loc_18008907F
0x180089073  cmp     [rcx], dx
0x180089076  lea     rax, aRenewsas; "renewsas"
0x18008907d  jnz     short loc_180089086
0x18008907f  lea     rax, aGetdestination; "getdestination"
0x180089086  mov     [rbp+770h+var_7F0], rax
0x18008908a  lea     rbx, aZip_0; "zip"
0x180089091  cmp     [r14+10h], edx
0x180089095  lea     rax, aCab_1; "cab"
0x18008909c  cmovz   rbx, rax
0x1800890a0  mov     rax, [r14]
0x1800890a3  mov     rcx, r14
0x1800890a6  mov     rax, [rax+20h]
0x1800890aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890af  lea     rcx, [rbp+770h+var_740]
0x1800890b3  mov     [rsp+870h+var_838], rcx; struct CTpRequestMessage *
0x1800890b8  xor     r14d, r14d
0x1800890bb  mov     [rsp+870h+var_840], r14; struct CDataRequest *
0x1800890c0  mov     rcx, [rbp+770h+var_7F0]
0x1800890c4  mov     [rsp+870h+var_848], rcx; wchar_t *
0x1800890c9  mov     [rsp+870h+var_850], rbx; wchar_t *
0x1800890ce  mov     r9, rax; unsigned __int64
0x1800890d1  mov     r8, [rbp+770h+var_788]; wchar_t *
0x1800890d5  mov     rdx, r13; struct CResponse *
0x1800890d8  mov     rcx, [rdi+30h]; struct CReport *
0x1800890dc  call    ?PrepareResumableUploadRequest@CWatsonTpTransport@@CAJPEAVCReport@@PEAVCResponse@@PEB_W_K22PEBVCDataRequest@@PEAVCTpRequestMessage@@@Z; CWatsonTpTransport::PrepareResumableUploadRequest(CReport *,CResponse *,wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CDataRequest const *,CTpRequestMessage *)
0x1800890e1  mov     ebx, eax
0x1800890e3  test    eax, eax
0x1800890e5  js      loc_1800897A3
0x1800890eb  mov     rcx, [rdi+30h]
0x1800890ef  add     rcx, 0B660h; this
0x1800890f6  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x1800890fb  xor     ebx, ebx
0x1800890fd  test    eax, eax
0x1800890ff  jz      short loc_180089116
0x180089101  mov     rcx, [rdi+30h]; this
0x180089105  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x18008910a  test    eax, eax
0x18008910c  jnz     short loc_180089116
0x18008910e  or      r12d, 2
0x180089112  mov     [rbp+770h+var_7E4], r12d
0x180089116  mov     rax, [rdi+30h]
0x18008911a  mov     r14, [rax+0CB58h]
0x180089121  test    r14, r14
0x180089124  jz      short loc_180089135
0x180089126  mov     rcx, r14; hToken
0x180089129  call    cs:__imp_ImpersonateLoggedOnUser
0x18008912f  mov     r15d, eax
0x180089132  mov     [rbp+770h+var_7E8], eax
0x180089135  lea     rax, [rdi+50h]
0x180089139  mov     rcx, rdi
0x18008913c  lea     rdx, [rdi+20h]
0x180089140  neg     rcx
0x180089143  sbb     rcx, rcx
0x180089146  and     rcx, rdx
0x180089149  mov     [rbp+770h+var_7B8], rcx
0x18008914d  mov     [rsp+870h+var_800], ebx; int
0x180089151  lea     rdx, [rbp+770h+var_60]
0x180089158  mov     [rsp+870h+var_808], rdx; __int64
0x18008915d  mov     rdx, [rbp+770h+var_7B0]
0x180089161  mov     [rsp+870h+var_810], rdx; __int64
0x180089166  mov     qword ptr [rsp+870h+var_818], rbx; int
0x18008916b  mov     rdx, [rbp+770h+var_7F0]
0x18008916f  mov     [rsp+870h+var_820], rdx; __int64
0x180089174  mov     [rsp+870h+var_828], rax; __int64
0x180089179  mov     rax, [rdi+28h]
0x18008917d  mov     [rsp+870h+var_830], rax; __int64
0x180089182  mov     [rsp+870h+var_838], r14; __int64
0x180089187  mov     [rsp+870h+var_840], rbx; int
0x18008918c  mov     dword ptr [rsp+870h+var_848], r12d; int
0x180089191  mov     [rsp+870h+var_850], rcx; struct ITpCallbacks *
0x180089196  xor     r9d, r9d
0x180089199  lea     r8, [rbp+770h+var_7D8]
0x18008919d  xor     edx, edx
0x18008919f  lea     rcx, [rbp+770h+var_740]; this
0x1800891a3  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x1800891a8  mov     ebx, eax
0x1800891aa  xor     r12d, r12d
0x1800891ad  test    r15d, r15d
0x1800891b0  jz      short loc_1800891BF
0x1800891b2  call    cs:__imp_RevertToSelf
0x1800891b8  mov     r15d, r12d
0x1800891bb  mov     [rbp+770h+var_7E8], r12d
0x1800891bf  test    ebx, ebx
0x1800891c1  js      loc_180089778
0x1800891c7  xor     r8d, r8d; int
0x1800891ca  mov     rdx, r13; struct CResponse *
0x1800891cd  lea     rcx, [rbp+770h+var_7D8]; struct CTpResponseMessage *
0x1800891d1  call    ?ParseResumableUploadResponse@CWatsonTpTransport@@CAJPEAVCTpResponseMessage@@PEAVCResponse@@H@Z; CWatsonTpTransport::ParseResumableUploadResponse(CTpResponseMessage *,CResponse *,int)
0x1800891d6  mov     ebx, eax
0x1800891d8  test    eax, eax
0x1800891da  js      loc_18008974D
0x1800891e0  mov     rcx, [r13+1E0h]; String
0x1800891e7  call    cs:__imp__wtoi64
0x1800891ed  lea     r12, [r13+1C0h]
0x1800891f4  mov     r8, rax
0x1800891f7  mov     rdx, r12
0x1800891fa  mov     rcx, rdi
0x1800891fd  call    ?SaveResumeState@CWatsonTpTransport@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_K@Z; CWatsonTpTransport::SaveResumeState(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64)
0x180089202  mov     ebx, eax
0x180089204  xor     eax, eax
0x180089206  test    ebx, ebx
0x180089208  js      loc_180089722
0x18008920e  mov     rdx, [r13+1A0h]; wchar_t *
0x180089215  test    rdx, rdx
0x180089218  jz      loc_1800896F5
0x18008921e  cmp     [rdx], ax
0x180089221  jz      loc_1800896F5
0x180089227  mov     rcx, [rdi+30h]; this
0x18008922b  call    ?SetCabUrl@CReport@@QEAAJPEB_W@Z; CReport::SetCabUrl(wchar_t const *)
0x180089230  mov     ebx, eax
0x180089232  test    eax, eax
0x180089234  js      loc_1800896CA
0x18008923a  mov     rcx, [rdi+30h]
0x18008923e  mov     rax, [r13+200h]
0x180089245  mov     [rcx+19A0h], rax
0x18008924c  lea     rdx, [rbp+770h+var_7DC]; unsigned int *
0x180089250  mov     rcx, [r13+208h]; wchar_t *
0x180089257  call    ?GetBlockIdFromString@CTpAzureStorageTransport@@SAJPEB_WAEAK@Z; CTpAzureStorageTransport::GetBlockIdFromString(wchar_t const *,ulong &)
0x18008925c  mov     ebx, eax
0x18008925e  xor     eax, eax
0x180089260  test    ebx, ebx
0x180089262  js      loc_18008969C
0x180089268  mov     [rbp+770h+var_790], rax
0x18008926c  test    r14, r14
0x18008926f  jz      short loc_180089280
0x180089271  mov     rcx, r14; hToken
0x180089274  call    cs:__imp_ImpersonateLoggedOnUser
0x18008927a  mov     r15d, eax
0x18008927d  mov     [rbp+770h+var_7E8], eax
0x180089280  mov     r9, [rdi+30h]
0x180089284  mov     rax, [rbp+770h+var_7B8]
0x180089288  mov     [rsp+870h+var_838], rax; struct ITpCallbacks *
0x18008928d  lea     rax, [rbp+770h+var_790]
0x180089291  mov     [rsp+870h+var_840], rax; unsigned __int64 *
0x180089296  lea     rax, [rbp+770h+var_7DC]
0x18008929a  mov     [rsp+870h+var_848], rax; unsigned int *
0x18008929f  mov     rax, [rdi+28h]
0x1800892a3  mov     [rsp+870h+var_850], rax; void *
0x1800892a8  mov     r9, [r9+19A0h]; unsigned __int64
0x1800892af  mov     r8, [rbp+770h+var_7A8]; struct IWerByteStream *
0x1800892b3  mov     edx, [rbp+770h+var_7E4]; unsigned int
0x1800892b6  mov     rcx, [r13+1A0h]; pwszUrl
0x1800892bd  call    ?UploadFileToAzureUsingSAS@CTpAzureStorageTransport@@SAJPEB_WKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z; CTpAzureStorageTransport::UploadFileToAzureUsingSAS(wchar_t const *,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)
0x1800892c2  mov     ebx, eax
0x1800892c4  test    r15d, r15d
0x1800892c7  jz      short loc_1800892D6
0x1800892c9  call    cs:__imp_RevertToSelf
0x1800892cf  xor     r15d, r15d
0x1800892d2  mov     [rbp+770h+var_7E8], r15d
0x1800892d6  mov     rcx, [rdi+30h]
0x1800892da  mov     eax, [rbp+770h+var_7DC]
0x1800892dd  mov     [rcx+1998h], eax
0x1800892e3  mov     rcx, [rdi+30h]
0x1800892e7  mov     rax, [rbp+770h+var_790]
0x1800892eb  add     [rcx+19A0h], rax
0x1800892f2  mov     edx, ebx; int
0x1800892f4  mov     rcx, rdi; this
0x1800892f7  call    ?LogAzureExchangeEvent@CWatsonTpTransport@@AEBAXJ@Z; CWatsonTpTransport::LogAzureExchangeEvent(long)
0x1800892fc  test    ebx, ebx
0x1800892fe  jns     short loc_18008935A
0x180089300  mov     rcx, cs:WPP_GLOBAL_Control
0x180089307  lea     rax, WPP_GLOBAL_Control
0x18008930e  cmp     rcx, rax
0x180089311  jz      short loc_180089331
0x180089313  test    byte ptr [rcx+1Ch], 1
0x180089317  jz      short loc_180089331
0x180089319  mov     edx, 1Eh
0x18008931e  mov     r9d, ebx
0x180089321  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180089328  mov     rcx, [rcx+10h]
0x18008932c  call    WPP_SF_d
0x180089331  cmp     ebx, 80190193h
0x180089337  jnz     short loc_180089387
0x180089339  cmp     esi, [rbp+770h+var_7E0]
0x18008933c  jnb     short loc_180089387
0x18008933e  mov     r8, [r13+1C8h]
0x180089345  sub     r8, [r12]
0x180089349  sar     r8, 1
0x18008934c  mov     rdx, [r12]
0x180089350  lea     rcx, [rbp+770h+var_788]
0x180089354  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180089359  nop
0x18008935a  lea     rcx, [rbp+770h+var_7D8]; this
0x18008935e  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180089363  nop
0x180089364  lea     rcx, [rbp+770h+var_740]; this
0x180089368  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008936d  cmp     ebx, 80190193h
0x180089373  jnz     short loc_1800893A6
0x180089375  cmp     esi, [rbp+770h+var_7E0]
0x180089378  jnb     short loc_1800893A6
0x18008937a  mov     r12d, [rbp+770h+var_7E4]
0x18008937e  mov     r14, [rbp+770h+var_7A8]
0x180089382  jmp     loc_180088FD1
0x180089387  lea     rcx, [rbp+770h+var_7D8]; this
0x18008938b  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180089390  nop
0x180089391  lea     rcx, [rbp+770h+var_740]; this
0x180089395  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008939a  lea     r14, WPP_GLOBAL_Control
0x1800893a1  jmp     loc_18008983B
0x1800893a6  mov     rdx, [rdi+30h]
0x1800893aa  lea     r9, [rdx+0CAD0h]
0x1800893b1  mov     r8d, [rdx+0CACCh]
0x1800893b8  mov     edx, [rdx+0CAC8h]
0x1800893be  lea     rcx, [rbp+770h+var_3D0]
0x1800893c5  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800893ca  mov     ebx, eax
  ... truncated ...
```
