# CWatsonTpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *,CDataRequest const *)

- ea: `0x18008cd48`
- end: `0x18008d83a`
- name: `?UploadToAzure@CWatsonTpTransport@@AEAAJPEAVCReportCabStream@@PEB_W1PEBVCDataRequest@@@Z`
- size: `2802`
- prototype: `__int64 __usercall@<rax>(CWatsonTpTransport *__hidden this@<rcx>, struct CReportCabStream *@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, const struct CDataRequest *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024840`

## callees

- `0x1800041d0`
- `0x18000ad98`
- `0x18000d40c`
- `0x18000da00`
- `0x18000db80`
- `0x180020680`
- `0x180025444`
- `0x18002dc4c`
- `0x180031cd0`
- `0x18003b7e0`
- `0x18003ba58`
- `0x18003e2b4`
- `0x18003fc6c`
- `0x1800412b4`
- `0x1800479ac`
- `0x18004ab74`
- `0x18004af98`
- `0x18004eb28`
- `0x180053300`
- `0x18007543c`
- `0x180076130`
- `0x18008ae48`
- `0x18008b3c8`
- `0x18008c458`
- `0x18008c8a4`
- `0x18008cd48`
- `0x18009341c`
- `0x180093594`
- `0x1800a68c0`
- `0x1800a7454`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008d043`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008d6c8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008d043`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18008d6c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d008`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d131`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d486`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d008`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d131`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008d486`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008cf79`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008d0d6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008d38b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008cf79`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008d0d6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008d38b`

## string_xrefs

- `0x18008d2d7`: `uploadcompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWatsonTpTransport::UploadToAzure(
        CWatsonTpTransport *this,
        struct CReportCabStream *a2,
        wchar_t *a3,
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
  const wchar_t *v17; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // r14
  __int64 v21; // rax
  void **v22; // r12
  const wchar_t *v23; // rdx
  int v24; // eax
  wchar_t *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  int v28; // eax
  const wchar_t *v29; // rsi
  const wchar_t *v30; // rbx
  unsigned __int64 v31; // rax
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
      v17 = L"cab";
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
    v22 = (void **)((char *)v11 + 448);
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
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v59, *v22);
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
    v30 = L"cab";
  v31 = (*(__int64 (**)(void))(*(_QWORD *)v55 + 32LL))();
  v32 = CWatsonTpTransport::PrepareResumableUploadRequest(
          *((struct CReport **)this + 6),
          v11,
          (const wchar_t *)*v22,
          v31,
          v30,
          L"uploadcompleted",
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
    if ( (int)CReport::GetUniqueIdentifier(*((_QWORD *)this + 6), v51) < 0 )
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
        v51,
        L"{00000000-0000-0000-0000-000000000000}");
    if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 0x400000000000LL) )
    {
      DwordData = BlockIdFromString;
      v48 = 0;
      v57 = (struct CResponse *)L"Watson";
      v56 = (struct CDataRequest *)v51[0];
      v54 = (__int64)v29;
      v53 = (struct ITpCallbacks *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v42,
        (unsigned int)&word_1800CE6D6,
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
0x18008cd48  push    rbp
0x18008cd4a  push    rbx
0x18008cd4b  push    rsi
0x18008cd4c  push    rdi
0x18008cd4d  push    r12
0x18008cd4f  push    r13
0x18008cd51  push    r14
0x18008cd53  push    r15
0x18008cd55  lea     rbp, [rsp-738h]
0x18008cd5d  sub     rsp, 838h
0x18008cd64  mov     rax, cs:__security_cookie
0x18008cd6b  xor     rax, rsp
0x18008cd6e  mov     [rbp+770h+var_50], rax
0x18008cd75  mov     [rbp+770h+var_7B0], r9
0x18008cd79  mov     rbx, r8
0x18008cd7c  mov     r14, rdx
0x18008cd7f  mov     [rbp+770h+var_7A8], rdx
0x18008cd83  mov     rdi, rcx
0x18008cd86  mov     rax, [rbp+770h+arg_20]
0x18008cd8d  mov     [rbp+770h+var_7A0], rax
0x18008cd91  lea     rcx, [rbp+770h+var_3D0]; this
0x18008cd98  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x18008cd9d  nop
0x18008cd9e  lea     rcx, [rbp+770h+var_768]; this
0x18008cda2  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x18008cda7  nop
0x18008cda8  xor     esi, esi
0x18008cdaa  mov     r12d, esi
0x18008cdad  mov     [rbp+770h+var_7E4], esi
0x18008cdb0  mov     r15d, esi
0x18008cdb3  mov     [rbp+770h+var_7E8], esi
0x18008cdb6  mov     [rbp+770h+var_7DC], esi
0x18008cdb9  mov     [rbp+770h+var_7F0], rsi
0x18008cdbd  mov     r13, [rdi+30h]
0x18008cdc1  add     r13, 8
0x18008cdc5  mov     [rbp+770h+var_798], r13
0x18008cdc9  lea     rax, [rbp+770h+var_778]
0x18008cdcd  mov     [rbp+770h+var_788], rax
0x18008cdd1  lea     rax, [rbp+770h+var_778]
0x18008cdd5  mov     [rbp+770h+var_780], rax
0x18008cdd9  mov     [rbp+770h+var_778], si
0x18008cddd  mov     rdx, rbx
0x18008cde0  lea     rcx, [rbp+770h+var_788]
0x18008cde4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18008cde9  mov     rcx, [rdi+30h]
0x18008cded  add     rcx, 0C910h; this
0x18008cdf4  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18008cdf9  mov     [rbp+770h+var_7E0], eax
0x18008cdfc  mov     dword ptr [rbp+770h+var_60], 1D4C0h
0x18008ce06  mov     eax, 0EA60h
0x18008ce0b  mov     dword ptr [rbp+770h+var_60+4], eax
0x18008ce11  mov     [rbp+770h+var_58], 7530h
0x18008ce1b  mov     [rbp+770h+var_54], eax
0x18008ce21  lea     rax, WPP_GLOBAL_Control
0x18008ce28  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce2f  cmp     rcx, rax
0x18008ce32  jz      short loc_18008CE54
0x18008ce34  test    byte ptr [rcx+1Ch], 4
0x18008ce38  jz      short loc_18008CE54
0x18008ce3a  inc     esi
0x18008ce3c  mov     edx, 14h
0x18008ce41  mov     r9d, esi
0x18008ce44  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x18008ce4b  mov     rcx, [rcx+10h]
0x18008ce4f  call    WPP_SF_d
0x18008ce54  lea     rcx, [rbp+770h+var_740]; this
0x18008ce58  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x18008ce5d  nop
0x18008ce5e  lea     rcx, [rbp+770h+var_7D8]; this
0x18008ce62  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x18008ce67  nop
0x18008ce68  mov     rdx, [rdi+30h]
0x18008ce6c  lea     r9, [rdx+0CAD0h]
0x18008ce73  mov     r8d, [rdx+0CACCh]
0x18008ce7a  mov     edx, [rdx+0CAC8h]
0x18008ce80  lea     rcx, [rbp+770h+var_740]
0x18008ce84  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x18008ce89  mov     ebx, eax
0x18008ce8b  test    eax, eax
0x18008ce8d  js      loc_18008D670
0x18008ce93  mov     rdx, [rdi+30h]
0x18008ce97  add     rdx, 1790h; struct OsInformation *
0x18008ce9e  lea     rcx, [rbp+770h+var_720]; this
0x18008cea2  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x18008cea7  mov     ebx, eax
0x18008cea9  xor     edx, edx
0x18008ceab  test    eax, eax
0x18008cead  js      loc_18008D63D
0x18008ceb3  mov     rax, [rdi+30h]
0x18008ceb7  mov     rcx, [rax+19A8h]
0x18008cebe  test    rcx, rcx
0x18008cec1  jz      short loc_18008CECF
0x18008cec3  cmp     [rcx], dx
0x18008cec6  lea     rax, aRenewsas; "renewsas"
0x18008cecd  jnz     short loc_18008CED6
0x18008cecf  lea     rax, aGetdestination; "getdestination"
0x18008ced6  mov     [rbp+770h+var_7F0], rax
0x18008ceda  lea     rbx, aZip_0; "zip"
0x18008cee1  cmp     [r14+10h], edx
0x18008cee5  lea     rax, aCab_1; "cab"
0x18008ceec  cmovz   rbx, rax
0x18008cef0  mov     rax, [r14]
0x18008cef3  mov     rcx, r14
0x18008cef6  mov     rax, [rax+20h]
0x18008cefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ceff  lea     rcx, [rbp+770h+var_740]
0x18008cf03  mov     [rsp+870h+var_838], rcx; struct CTpRequestMessage *
0x18008cf08  xor     r14d, r14d
0x18008cf0b  mov     [rsp+870h+var_840], r14; struct CDataRequest *
0x18008cf10  mov     rcx, [rbp+770h+var_7F0]
0x18008cf14  mov     [rsp+870h+var_848], rcx; wchar_t *
0x18008cf19  mov     [rsp+870h+var_850], rbx; wchar_t *
0x18008cf1e  mov     r9, rax; unsigned __int64
0x18008cf21  mov     r8, [rbp+770h+var_788]; wchar_t *
0x18008cf25  mov     rdx, r13; struct CResponse *
0x18008cf28  mov     rcx, [rdi+30h]; this
0x18008cf2c  call    ?PrepareResumableUploadRequest@CWatsonTpTransport@@CAJPEAVCReport@@PEAVCResponse@@PEB_W_K22PEBVCDataRequest@@PEAVCTpRequestMessage@@@Z; CWatsonTpTransport::PrepareResumableUploadRequest(CReport *,CResponse *,wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CDataRequest const *,CTpRequestMessage *)
0x18008cf31  mov     ebx, eax
0x18008cf33  test    eax, eax
0x18008cf35  js      loc_18008D61D
0x18008cf3b  mov     rcx, [rdi+30h]
0x18008cf3f  add     rcx, 0B660h; this
0x18008cf46  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x18008cf4b  xor     ebx, ebx
0x18008cf4d  test    eax, eax
0x18008cf4f  jz      short loc_18008CF66
0x18008cf51  mov     rcx, [rdi+30h]; this
0x18008cf55  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x18008cf5a  test    eax, eax
0x18008cf5c  jnz     short loc_18008CF66
0x18008cf5e  or      r12d, 2
0x18008cf62  mov     [rbp+770h+var_7E4], r12d
0x18008cf66  mov     rax, [rdi+30h]
0x18008cf6a  mov     r14, [rax+0CB58h]
0x18008cf71  test    r14, r14
0x18008cf74  jz      short loc_18008CF8B
0x18008cf76  mov     rcx, r14; hToken
0x18008cf79  call    cs:__imp_ImpersonateLoggedOnUser
0x18008cf80  nop     dword ptr [rax+rax+00h]
0x18008cf85  mov     r15d, eax
0x18008cf88  mov     [rbp+770h+var_7E8], eax
0x18008cf8b  lea     rax, [rdi+50h]
0x18008cf8f  mov     rcx, rdi
0x18008cf92  lea     rdx, [rdi+20h]
0x18008cf96  neg     rcx
0x18008cf99  sbb     rcx, rcx
0x18008cf9c  and     rcx, rdx
0x18008cf9f  mov     [rbp+770h+var_7B8], rcx
0x18008cfa3  mov     [rsp+870h+var_800], ebx; int
0x18008cfa7  lea     rdx, [rbp+770h+var_60]
0x18008cfae  mov     [rsp+870h+var_808], rdx; __int64
0x18008cfb3  mov     rdx, [rbp+770h+var_7B0]
0x18008cfb7  mov     [rsp+870h+var_810], rdx; __int64
0x18008cfbc  mov     qword ptr [rsp+870h+var_818], rbx; int
0x18008cfc1  mov     rdx, [rbp+770h+var_7F0]
0x18008cfc5  mov     [rsp+870h+var_820], rdx; __int64
0x18008cfca  mov     [rsp+870h+var_828], rax; __int64
0x18008cfcf  mov     rax, [rdi+28h]
0x18008cfd3  mov     [rsp+870h+var_830], rax; __int64
0x18008cfd8  mov     [rsp+870h+var_838], r14; __int64
0x18008cfdd  mov     [rsp+870h+var_840], rbx; int
0x18008cfe2  mov     dword ptr [rsp+870h+var_848], r12d; int
0x18008cfe7  mov     [rsp+870h+var_850], rcx; struct ITpCallbacks *
0x18008cfec  xor     r9d, r9d
0x18008cfef  lea     r8, [rbp+770h+var_7D8]
0x18008cff3  xor     edx, edx
0x18008cff5  lea     rcx, [rbp+770h+var_740]; this
0x18008cff9  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x18008cffe  mov     ebx, eax
0x18008d000  xor     r12d, r12d
0x18008d003  test    r15d, r15d
0x18008d006  jz      short loc_18008D01B
0x18008d008  call    cs:__imp_RevertToSelf
0x18008d00f  nop     dword ptr [rax+rax+00h]
0x18008d014  mov     r15d, r12d
0x18008d017  mov     [rbp+770h+var_7E8], r12d
0x18008d01b  test    ebx, ebx
0x18008d01d  js      loc_18008D5F2
0x18008d023  xor     r8d, r8d; int
0x18008d026  mov     rdx, r13; struct CResponse *
0x18008d029  lea     rcx, [rbp+770h+var_7D8]; struct CTpResponseMessage *
0x18008d02d  call    ?ParseResumableUploadResponse@CWatsonTpTransport@@CAJPEAVCTpResponseMessage@@PEAVCResponse@@H@Z; CWatsonTpTransport::ParseResumableUploadResponse(CTpResponseMessage *,CResponse *,int)
0x18008d032  mov     ebx, eax
0x18008d034  test    eax, eax
0x18008d036  js      loc_18008D5C7
0x18008d03c  mov     rcx, [r13+1E0h]; String
0x18008d043  call    cs:__imp__wtoi64
0x18008d04a  nop     dword ptr [rax+rax+00h]
0x18008d04f  lea     r12, [r13+1C0h]
0x18008d056  mov     r8, rax
0x18008d059  mov     rdx, r12
0x18008d05c  mov     rcx, rdi
0x18008d05f  call    ?SaveResumeState@CWatsonTpTransport@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_K@Z; CWatsonTpTransport::SaveResumeState(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64)
0x18008d064  mov     ebx, eax
0x18008d066  xor     eax, eax
0x18008d068  test    ebx, ebx
0x18008d06a  js      loc_18008D59C
0x18008d070  mov     rdx, [r13+1A0h]; wchar_t *
0x18008d077  test    rdx, rdx
0x18008d07a  jz      loc_18008D56F
0x18008d080  cmp     [rdx], ax
0x18008d083  jz      loc_18008D56F
0x18008d089  mov     rcx, [rdi+30h]; this
0x18008d08d  call    ?SetCabUrl@CReport@@QEAAJPEB_W@Z; CReport::SetCabUrl(wchar_t const *)
0x18008d092  mov     ebx, eax
0x18008d094  test    eax, eax
0x18008d096  js      loc_18008D544
0x18008d09c  mov     rcx, [rdi+30h]
0x18008d0a0  mov     rax, [r13+200h]
0x18008d0a7  mov     [rcx+19A0h], rax
0x18008d0ae  lea     rdx, [rbp+770h+var_7DC]; unsigned int *
0x18008d0b2  mov     rcx, [r13+208h]; wchar_t *
0x18008d0b9  call    ?GetBlockIdFromString@CTpAzureStorageTransport@@SAJPEB_WAEAK@Z; CTpAzureStorageTransport::GetBlockIdFromString(wchar_t const *,ulong &)
0x18008d0be  mov     ebx, eax
0x18008d0c0  xor     eax, eax
0x18008d0c2  test    ebx, ebx
0x18008d0c4  js      loc_18008D516
0x18008d0ca  mov     [rbp+770h+var_790], rax
0x18008d0ce  test    r14, r14
0x18008d0d1  jz      short loc_18008D0E8
0x18008d0d3  mov     rcx, r14; hToken
0x18008d0d6  call    cs:__imp_ImpersonateLoggedOnUser
0x18008d0dd  nop     dword ptr [rax+rax+00h]
0x18008d0e2  mov     r15d, eax
0x18008d0e5  mov     [rbp+770h+var_7E8], eax
0x18008d0e8  mov     r9, [rdi+30h]
0x18008d0ec  mov     rax, [rbp+770h+var_7B8]
0x18008d0f0  mov     [rsp+870h+var_838], rax; struct ITpCallbacks *
0x18008d0f5  lea     rax, [rbp+770h+var_790]
0x18008d0f9  mov     [rsp+870h+var_840], rax; unsigned __int64 *
0x18008d0fe  lea     rax, [rbp+770h+var_7DC]
0x18008d102  mov     [rsp+870h+var_848], rax; unsigned int *
0x18008d107  mov     rax, [rdi+28h]
0x18008d10b  mov     [rsp+870h+var_850], rax; void *
0x18008d110  mov     r9, [r9+19A0h]; unsigned __int64
0x18008d117  mov     r8, [rbp+770h+var_7A8]; struct IWerByteStream *
0x18008d11b  mov     edx, [rbp+770h+var_7E4]; unsigned int
0x18008d11e  mov     rcx, [r13+1A0h]; pwszUrl
0x18008d125  call    ?UploadFileToAzureUsingSAS@CTpAzureStorageTransport@@SAJPEB_WKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z; CTpAzureStorageTransport::UploadFileToAzureUsingSAS(wchar_t const *,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)
0x18008d12a  mov     ebx, eax
0x18008d12c  test    r15d, r15d
0x18008d12f  jz      short loc_18008D144
0x18008d131  call    cs:__imp_RevertToSelf
0x18008d138  nop     dword ptr [rax+rax+00h]
0x18008d13d  xor     r15d, r15d
0x18008d140  mov     [rbp+770h+var_7E8], r15d
0x18008d144  mov     rcx, [rdi+30h]
0x18008d148  mov     eax, [rbp+770h+var_7DC]
0x18008d14b  mov     [rcx+1998h], eax
0x18008d151  mov     rcx, [rdi+30h]
0x18008d155  mov     rax, [rbp+770h+var_790]
0x18008d159  add     [rcx+19A0h], rax
0x18008d160  mov     edx, ebx; int
0x18008d162  mov     rcx, rdi; this
0x18008d165  call    ?LogAzureExchangeEvent@CWatsonTpTransport@@AEBAXJ@Z; CWatsonTpTransport::LogAzureExchangeEvent(long)
0x18008d16a  test    ebx, ebx
0x18008d16c  jns     short loc_18008D1C8
0x18008d16e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d175  lea     rax, WPP_GLOBAL_Control
0x18008d17c  cmp     rcx, rax
0x18008d17f  jz      short loc_18008D19F
0x18008d181  test    byte ptr [rcx+1Ch], 1
0x18008d185  jz      short loc_18008D19F
0x18008d187  mov     edx, 1Eh
0x18008d18c  mov     r9d, ebx
0x18008d18f  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x18008d196  mov     rcx, [rcx+10h]
0x18008d19a  call    WPP_SF_d
0x18008d19f  cmp     ebx, 80190193h
0x18008d1a5  jnz     short loc_18008D1F5
0x18008d1a7  cmp     esi, [rbp+770h+var_7E0]
0x18008d1aa  jnb     short loc_18008D1F5
0x18008d1ac  mov     r8, [r13+1C8h]
0x18008d1b3  sub     r8, [r12]
0x18008d1b7  sar     r8, 1
0x18008d1ba  mov     rdx, [r12]
0x18008d1be  lea     rcx, [rbp+770h+var_788]
0x18008d1c2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18008d1c7  nop
0x18008d1c8  lea     rcx, [rbp+770h+var_7D8]; this
0x18008d1cc  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x18008d1d1  nop
0x18008d1d2  lea     rcx, [rbp+770h+var_740]; this
0x18008d1d6  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008d1db  cmp     ebx, 80190193h
0x18008d1e1  jnz     short loc_18008D214
0x18008d1e3  cmp     esi, [rbp+770h+var_7E0]
0x18008d1e6  jnb     short loc_18008D214
0x18008d1e8  mov     r12d, [rbp+770h+var_7E4]
0x18008d1ec  mov     r14, [rbp+770h+var_7A8]
0x18008d1f0  jmp     loc_18008CE21
0x18008d1f5  lea     rcx, [rbp+770h+var_7D8]; this
0x18008d1f9  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x18008d1fe  nop
0x18008d1ff  lea     rcx, [rbp+770h+var_740]; this
0x18008d203  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x18008d208  lea     r14, WPP_GLOBAL_Control
0x18008d20f  jmp     loc_18008D6B5
0x18008d214  mov     rdx, [rdi+30h]
0x18008d218  lea     r9, [rdx+0CAD0h]
  ... truncated ...
```
