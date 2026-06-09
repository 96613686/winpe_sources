# COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)

- ea: `0x1800898d8`
- end: `0x18008a371`
- name: `?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z`
- size: `2713`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, struct CReportCabStream *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008808c`

## callees

- `0x1800041d0`
- `0x180004c64`
- `0x18000ad98`
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
- `0x180047364`
- `0x1800479ac`
- `0x18004ab74`
- `0x18004eb28`
- `0x18007543c`
- `0x180076130`
- `0x18007ad94`
- `0x18008787c`
- `0x180088f0c`
- `0x1800892f8`
- `0x1800898d8`
- `0x18009341c`
- `0x180093594`
- `0x18009388c`
- `0x1800a68c0`
- `0x1800a7454`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180089b7c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180089b9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180089b7c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180089b9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089b3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089ca7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089f17`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089b3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089ca7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180089f17`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089aa4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089c46`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089e1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089aa4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089c46`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180089e1d`

## string_xrefs

- `0x180089d72`: `uploadcompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall COCATpTransport::UploadToAzure(
        COCATpTransport *this,
        struct CReportCabStream *a2,
        wchar_t *a3,
        const wchar_t *a4)
{
  struct IWerByteStream *v4; // r14
  BOOL v6; // r15d
  __int64 v7; // rcx
  CResponse *v8; // rsi
  unsigned int v9; // r13d
  int v10; // r12d
  const wchar_t *v11; // rbx
  _WORD *v12; // rcx
  wchar_t *v13; // rax
  unsigned __int64 v14; // rax
  int v15; // eax
  int BlockIdFromString; // ebx
  __int64 v17; // rax
  void *v18; // r14
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rbx
  unsigned __int64 v21; // rax
  int v22; // eax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // esi
  struct ITpCallbacks *v27; // r15
  __int64 v28; // r8
  CTransport *v29; // rcx
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  int v33; // eax
  wchar_t *v34; // rcx
  int v36; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v41; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v42[2]; // [rsp+98h] [rbp-70h] BYREF
  _WORD v43[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+C0h] [rbp-48h] BYREF
  struct ITpCallbacks *v46; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *v47; // [rsp+D0h] [rbp-38h] BYREF
  wchar_t *v48; // [rsp+D8h] [rbp-30h]
  _WORD v49[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v50[8]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-10h]
  __int64 v52; // [rsp+100h] [rbp-8h]
  _BYTE v53[880]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v54[944]; // [rsp+488h] [rbp+380h] BYREF
  int v55; // [rsp+848h] [rbp+740h] BYREF
  struct IWerByteStream *v56; // [rsp+850h] [rbp+748h] BYREF
  wchar_t *v57; // [rsp+858h] [rbp+750h]
  __int64 v58; // [rsp+860h] [rbp+758h]

  v58 = (__int64)a4;
  v57 = a3;
  v56 = a2;
  v4 = a2;
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v54);
  CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v50);
  v6 = 0;
  v55 = 0;
  v40 = 0;
  v7 = *((_QWORD *)this + 6);
  v8 = (CResponse *)(v7 + 8);
  LODWORD(v44) = CRegSetting::GetDwordData((CRegSetting *)(v7 + 51472));
  v9 = 0;
  v47 = v49;
  v48 = v49;
  v49[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &v47,
                           *(void **)v8)
    && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 2147942414LL);
  }
  v10 = 0;
  if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
    && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
  {
    v10 = 2;
  }
  while ( 1 )
  {
    v11 = L"zip";
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, ++v9);
    CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v53);
    CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v42);
    v12 = *(_WORD **)(*((_QWORD *)this + 6) + 6568LL);
    if ( !v12 || (v13 = L"renewsas", !*v12) )
      v13 = L"getdestination";
    v41 = v13;
    if ( !*((_DWORD *)v4 + 4) )
      v11 = L"cab";
    v14 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 0);
    v15 = COCATpTransport::PrepareResumableUploadRequest(this, v57, v14, v11, v41, (struct CTpRequestMessage *)v53);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 77;
      goto LABEL_116;
    }
    v17 = *((_QWORD *)this + 6);
    v18 = *(void **)(v17 + 52056);
    if ( v18 )
    {
      v6 = ImpersonateLoggedOnUser(*(HANDLE *)(v17 + 52056));
      v55 = v6;
    }
    v46 = (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v53,
                          v46,
                          v10,
                          0,
                          (__int64)v18,
                          *((_QWORD *)this + 5),
                          (__int64)this + 192,
                          (__int64)v41,
                          0,
                          v58,
                          (__int64)&httpTimeoutsLongerReceiveTimeout,
                          0);
    if ( v6 )
    {
      RevertToSelf();
      v6 = 0;
      v55 = 0;
    }
    if ( BlockIdFromString < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 78;
      goto LABEL_78;
    }
    v15 = COCATpTransport::ParseResumableUploadResponse(this, (struct CTpResponseMessage *)v42);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 79;
LABEL_116:
      v32 = (unsigned int)v15;
LABEL_117:
      WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v32);
LABEL_118:
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_119;
    }
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v8, L"REJECTED_BY_RULE") )
    {
      if ( v47 != v48 )
      {
        v33 = CResponse::SetBucketId(v8, v47);
        if ( v33 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
            goto LABEL_101;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
            (unsigned int)v33);
        }
      }
      v34 = WPP_GLOBAL_Control;
LABEL_101:
      BlockIdFromString = 1769483;
      if ( v34 != (wchar_t *)&WPP_GLOBAL_Control && (v34[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v34 + 2), 81, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 1769483);
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_105;
    }
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v8, L"INVALID_REQUEST") )
    {
      BlockIdFromString = -2147024883;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, 2147942413LL);
      CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
      CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
      goto LABEL_120;
    }
    v15 = COCATpTransport::SaveResumeState(this, v57);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 83;
        goto LABEL_116;
      }
      goto LABEL_118;
    }
    BlockIdFromString = COCAReply::SaveToReport((COCATpTransport *)((char *)this + 56), *((struct CReport **)this + 6));
    if ( BlockIdFromString < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids);
      goto LABEL_118;
    }
    v19 = (const wchar_t *)*((_QWORD *)v8 + 52);
    if ( !v19 || !*v19 )
    {
      v32 = 2147942413LL;
      BlockIdFromString = -2147024883;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 85;
        goto LABEL_117;
      }
      goto LABEL_118;
    }
    v15 = CReport::SetCabUrl(*((CReport **)this + 6), v19);
    BlockIdFromString = v15;
    if ( v15 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 86;
        goto LABEL_116;
      }
      goto LABEL_118;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) = *((_QWORD *)v8 + 64);
    BlockIdFromString = CTpAzureStorageTransport::GetBlockIdFromString(*((const wchar_t **)v8 + 65), &v40);
    if ( BlockIdFromString < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_118;
      v31 = 87;
LABEL_78:
      v32 = (unsigned int)BlockIdFromString;
      goto LABEL_117;
    }
    v45 = 0;
    if ( v18 )
    {
      v6 = ImpersonateLoggedOnUser(v18);
      v55 = v6;
    }
    BlockIdFromString = CTpAzureStorageTransport::UploadFileToAzureUsingSAS(
                          *((LPCWSTR *)v8 + 52),
                          v10,
                          v56,
                          *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL),
                          *((void **)this + 5),
                          &v40,
                          &v45,
                          v46);
    if ( v6 )
    {
      RevertToSelf();
      v6 = 0;
      v55 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 6) + 6552LL) = v40;
    *(_QWORD *)(*((_QWORD *)this + 6) + 6560LL) += v45;
    COCATpTransport::LogAzureExchangeEvent(this, BlockIdFromString);
    if ( BlockIdFromString < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)BlockIdFromString);
      if ( BlockIdFromString != -2145844845 || v9 >= (unsigned int)v44 )
      {
        CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
        CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
        goto LABEL_119;
      }
    }
    CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v42);
    CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v53);
    if ( BlockIdFromString != -2145844845 || v9 >= (unsigned int)v44 )
      break;
    v4 = v56;
  }
  v41 = (wchar_t *)L"uploadcompleted";
  v20 = L"zip";
  if ( !*((_DWORD *)v56 + 4) )
    v20 = L"cab";
  v21 = (*(__int64 (**)(void))(*(_QWORD *)v56 + 32LL))();
  v22 = COCATpTransport::PrepareResumableUploadRequest(
          this,
          v57,
          v21,
          v20,
          L"uploadcompleted",
          (struct CTpRequestMessage *)v54);
  BlockIdFromString = v22;
  if ( v22 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_119;
    v24 = 89;
LABEL_52:
    v25 = (unsigned int)v22;
    goto LABEL_53;
  }
  v26 = 3;
  if ( v18 )
    v55 = ImpersonateLoggedOnUser(v18);
  v27 = v46;
  while ( 2 )
  {
    --v26;
    v28 = v52;
    v52 = v51;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CTpResponseSection,utl::default_delete<CTpResponseSection>>>>(
      v23,
      v51,
      (v28 - v51) >> 3);
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v54,
                          v27,
                          v10,
                          0,
                          (__int64)v18,
                          *((_QWORD *)this + 5),
                          (__int64)this + 192,
                          (__int64)L"uploadcompleted",
                          0,
                          v58,
                          (__int64)&httpTimeoutsLongerReceiveTimeout,
                          0);
    if ( BlockIdFromString >= 0 )
    {
LABEL_61:
      v29 = (CTransport *)WPP_GLOBAL_Control;
    }
    else
    {
      v29 = (CTransport *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
          (unsigned int)(3 - v26),
          BlockIdFromString);
        goto LABEL_61;
      }
    }
    if ( (unsigned int)CTransport::ShouldRetryExchange(v29, BlockIdFromString) && v26 )
      continue;
    break;
  }
  if ( v55 )
  {
    RevertToSelf();
    v23 = WPP_GLOBAL_Control;
  }
  if ( BlockIdFromString < 0 )
  {
    if ( v23 != (wchar_t *)&WPP_GLOBAL_Control && (v23[14] & 1) != 0 )
    {
      v24 = 91;
      v25 = (unsigned int)BlockIdFromString;
LABEL_53:
      WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids, v25);
    }
    goto LABEL_119;
  }
  v22 = COCATpTransport::ParseResumableUploadResponse(this, (struct CTpResponseMessage *)v50);
  BlockIdFromString = v22;
  if ( v22 >= 0 )
  {
    CTransport::EventCabUploadComplete(this, v22);
    goto LABEL_119;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v24 = 92;
    goto LABEL_52;
  }
LABEL_119:
  if ( BlockIdFromString >= 0 )
  {
LABEL_105:
    CReport::SetCabUrl(*((CReport **)this + 6), 0);
    goto LABEL_106;
  }
LABEL_120:
  v36 = COCATpTransport::SaveResumeState(this, v57);
  if ( v36 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids,
      (unsigned int)v36);
  v42[0] = v43;
  v42[1] = v43;
  v43[0] = 0;
  if ( (int)CReport::GetUniqueIdentifier(*((_QWORD *)this + 6), v42) < 0 )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      v42,
      L"{00000000-0000-0000-0000-000000000000}");
  if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 0x400000000000LL) )
  {
    LODWORD(v56) = BlockIdFromString;
    v55 = *((_DWORD *)this + 88);
    v46 = (struct ITpCallbacks *)L"OCA";
    v45 = v42[0];
    v44 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)&dword_1800CE35C,
      v38,
      v39,
      (__int64)&v44,
      (__int64)&v41,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v55,
      (__int64)&v56);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
LABEL_106:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v47);
  CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v50);
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v54);
  return (unsigned int)BlockIdFromString;
}

```

## disassembly

```asm
0x1800898d8  mov     rax, rsp
0x1800898db  mov     [rax+20h], r9
0x1800898df  mov     [rax+18h], r8
0x1800898e3  mov     [rax+10h], rdx
0x1800898e7  push    rbp
0x1800898e8  push    rbx
0x1800898e9  push    rsi
0x1800898ea  push    rdi
0x1800898eb  push    r12
0x1800898ed  push    r13
0x1800898ef  push    r14
0x1800898f1  push    r15
0x1800898f3  lea     rbp, [rax-738h]
0x1800898fa  sub     rsp, 7F8h
0x180089901  mov     r14, rdx
0x180089904  mov     rdi, rcx
0x180089907  lea     rcx, [rbp+730h+var_3B0]; this
0x18008990e  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180089913  nop
0x180089914  lea     rcx, [rbp+730h+var_748]; this
0x180089918  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x18008991d  nop
0x18008991e  xor     ebx, ebx
0x180089920  mov     r15d, ebx
0x180089923  mov     [rbp+730h+arg_0], ebx
0x180089929  mov     [rbp+730h+var_7B0], ebx
0x18008992c  mov     rcx, [rdi+30h]
0x180089930  lea     rsi, [rcx+8]
0x180089934  add     rcx, 0C910h; this
0x18008993b  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180089940  mov     dword ptr [rbp+730h+var_780], eax
0x180089943  mov     r13d, ebx
0x180089946  lea     rax, [rbp+730h+var_758]
0x18008994a  mov     [rbp+730h+var_768], rax
0x18008994e  lea     rax, [rbp+730h+var_758]
0x180089952  mov     [rbp+730h+var_760], rax
0x180089956  mov     [rbp+730h+var_758], bx
0x18008995a  mov     rdx, [rsi]
0x18008995d  lea     rcx, [rbp+730h+var_768]
0x180089961  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180089966  lea     rdx, WPP_GLOBAL_Control
0x18008996d  test    al, al
0x18008996f  jnz     short loc_18008999C
0x180089971  mov     rcx, cs:WPP_GLOBAL_Control
0x180089978  cmp     rcx, rdx
0x18008997b  jz      short loc_18008999C
0x18008997d  test    byte ptr [rcx+1Ch], 2
0x180089981  jz      short loc_18008999C
0x180089983  lea     edx, [rbx+4Bh]
0x180089986  mov     r9d, 8007000Eh
0x18008998c  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180089993  mov     rcx, [rcx+10h]
0x180089997  call    WPP_SF_d
0x18008999c  mov     r12d, ebx
0x18008999f  mov     rcx, [rdi+30h]
0x1800899a3  add     rcx, 0B660h; this
0x1800899aa  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x1800899af  test    eax, eax
0x1800899b1  jz      short loc_1800899C7
0x1800899b3  mov     rcx, [rdi+30h]; this
0x1800899b7  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x1800899bc  test    eax, eax
0x1800899be  mov     eax, 2
0x1800899c3  cmovz   r12d, eax
0x1800899c7  lea     rbx, aZip_0; "zip"
0x1800899ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800899d5  lea     rax, WPP_GLOBAL_Control
0x1800899dc  cmp     rcx, rax
0x1800899df  jz      short loc_180089A02
0x1800899e1  test    byte ptr [rcx+1Ch], 4
0x1800899e5  jz      short loc_180089A02
0x1800899e7  inc     r13d
0x1800899ea  mov     edx, 4Ch ; 'L'
0x1800899ef  mov     r9d, r13d
0x1800899f2  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x1800899f9  mov     rcx, [rcx+10h]
0x1800899fd  call    WPP_SF_d
0x180089a02  lea     rcx, [rbp+730h+var_720]; this
0x180089a06  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180089a0b  nop
0x180089a0c  lea     rcx, [rbp+730h+var_7A0]; this
0x180089a10  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180089a15  nop
0x180089a16  mov     rax, [rdi+30h]
0x180089a1a  mov     rcx, [rax+19A8h]
0x180089a21  xor     edx, edx
0x180089a23  test    rcx, rcx
0x180089a26  jz      short loc_180089A34
0x180089a28  cmp     [rcx], dx
0x180089a2b  lea     rax, aRenewsas; "renewsas"
0x180089a32  jnz     short loc_180089A3B
0x180089a34  lea     rax, aGetdestination; "getdestination"
0x180089a3b  mov     [rbp+730h+var_7A8], rax
0x180089a3f  cmp     [r14+10h], edx
0x180089a43  lea     rax, aCab_1; "cab"
0x180089a4a  cmovz   rbx, rax
0x180089a4e  mov     rax, [r14]
0x180089a51  mov     rcx, r14
0x180089a54  mov     rax, [rax+20h]
0x180089a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a5d  lea     rcx, [rbp+730h+var_720]
0x180089a61  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x180089a66  mov     rcx, [rbp+730h+var_7A8]
0x180089a6a  mov     [rsp+830h+var_810], rcx; wchar_t *
0x180089a6f  mov     r9, rbx; wchar_t *
0x180089a72  mov     r8, rax; unsigned __int64
0x180089a75  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180089a7c  mov     rcx, rdi; this
0x180089a7f  call    ?PrepareResumableUploadRequest@COCATpTransport@@IEAAJPEB_W_K00PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareResumableUploadRequest(wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CTpRequestMessage *)
0x180089a84  mov     ebx, eax
0x180089a86  xor     r9d, r9d
0x180089a89  test    eax, eax
0x180089a8b  js      loc_18008A1FB
0x180089a91  mov     rax, [rdi+30h]
0x180089a95  mov     r14, [rax+0CB58h]
0x180089a9c  test    r14, r14
0x180089a9f  jz      short loc_180089ABC
0x180089aa1  mov     rcx, r14; hToken
0x180089aa4  call    cs:__imp_ImpersonateLoggedOnUser
0x180089aab  nop     dword ptr [rax+rax+00h]
0x180089ab0  mov     r15d, eax
0x180089ab3  mov     [rbp+730h+arg_0], eax
0x180089ab9  xor     r9d, r9d
0x180089abc  lea     r8, [rdi+0C0h]
0x180089ac3  mov     rcx, rdi
0x180089ac6  lea     rdx, [rdi+20h]
0x180089aca  neg     rcx
0x180089acd  sbb     rcx, rcx
0x180089ad0  and     rcx, rdx
0x180089ad3  mov     [rbp+730h+var_770], rcx
0x180089ad7  mov     [rsp+70h], r9d; int
0x180089adc  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180089ae3  mov     [rsp+830h+var_7C8], rax; __int64
0x180089ae8  mov     rax, [rbp+730h+arg_18]
0x180089aef  mov     [rsp+830h+var_7D0], rax; __int64
0x180089af4  mov     qword ptr [rsp+830h+var_7D8], r9; int
0x180089af9  mov     rax, [rbp+730h+var_7A8]
0x180089afd  mov     [rsp+830h+var_7E0], rax; __int64
0x180089b02  mov     [rsp+830h+var_7E8], r8; __int64
0x180089b07  mov     rax, [rdi+28h]
0x180089b0b  mov     [rsp+830h+var_7F0], rax; __int64
0x180089b10  mov     [rsp+830h+var_7F8], r14; __int64
0x180089b15  mov     [rsp+830h+var_800], r9; int
0x180089b1a  mov     dword ptr [rsp+830h+var_808], r12d; int
0x180089b1f  mov     [rsp+830h+var_810], rcx; struct ITpCallbacks *
0x180089b24  xor     r9d, r9d
0x180089b27  lea     r8, [rbp+730h+var_7A0]
0x180089b2b  xor     edx, edx
0x180089b2d  lea     rcx, [rbp+730h+var_720]; this
0x180089b31  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180089b36  mov     ebx, eax
0x180089b38  test    r15d, r15d
0x180089b3b  jz      short loc_180089B54
0x180089b3d  call    cs:__imp_RevertToSelf
0x180089b44  nop     dword ptr [rax+rax+00h]
0x180089b49  xor     eax, eax
0x180089b4b  mov     r15d, eax
0x180089b4e  mov     [rbp+730h+arg_0], eax
0x180089b54  test    ebx, ebx
0x180089b56  js      loc_18008A1D8
0x180089b5c  lea     rdx, [rbp+730h+var_7A0]; struct CTpResponseMessage *
0x180089b60  mov     rcx, rdi; this
0x180089b63  call    ?ParseResumableUploadResponse@COCATpTransport@@IEAAJPEAVCTpResponseMessage@@@Z; COCATpTransport::ParseResumableUploadResponse(CTpResponseMessage *)
0x180089b68  mov     ebx, eax
0x180089b6a  test    eax, eax
0x180089b6c  js      loc_18008A1B8
0x180089b72  lea     rdx, aRejectedByRule; "REJECTED_BY_RULE"
0x180089b79  mov     rcx, [rsi]
0x180089b7c  call    cs:__imp__o__wcsicmp
0x180089b83  nop     dword ptr [rax+rax+00h]
0x180089b88  test    eax, eax
0x180089b8a  jz      loc_18008A0E4
0x180089b90  lea     rdx, aInvalidRequest; "INVALID_REQUEST"
0x180089b97  mov     rcx, [rsi]
0x180089b9a  call    cs:__imp__o__wcsicmp
0x180089ba1  nop     dword ptr [rax+rax+00h]
0x180089ba6  test    eax, eax
0x180089ba8  jz      loc_18008A094
0x180089bae  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180089bb5  mov     rcx, rdi; this
0x180089bb8  call    ?SaveResumeState@COCATpTransport@@IEAAJPEB_W@Z; COCATpTransport::SaveResumeState(wchar_t const *)
0x180089bbd  mov     ebx, eax
0x180089bbf  test    eax, eax
0x180089bc1  js      loc_18008A069
0x180089bc7  lea     rcx, [rdi+38h]; this
0x180089bcb  mov     rdx, [rdi+30h]; struct CReport *
0x180089bcf  call    ?SaveToReport@COCAReply@@QEAAJPEAVCReport@@@Z; COCAReply::SaveToReport(CReport *)
0x180089bd4  mov     ebx, eax
0x180089bd6  xor     eax, eax
0x180089bd8  test    ebx, ebx
0x180089bda  js      loc_18008A02E
0x180089be0  mov     rdx, [rsi+1A0h]; wchar_t *
0x180089be7  test    rdx, rdx
0x180089bea  jz      loc_180089FFA
0x180089bf0  cmp     [rdx], ax
0x180089bf3  jz      loc_180089FFA
0x180089bf9  mov     rcx, [rdi+30h]; this
0x180089bfd  call    ?SetCabUrl@CReport@@QEAAJPEB_W@Z; CReport::SetCabUrl(wchar_t const *)
0x180089c02  mov     ebx, eax
0x180089c04  test    eax, eax
0x180089c06  js      loc_180089FCF
0x180089c0c  mov     rcx, [rdi+30h]
0x180089c10  mov     rax, [rsi+200h]
0x180089c17  mov     [rcx+19A0h], rax
0x180089c1e  lea     rdx, [rbp+730h+var_7B0]; unsigned int *
0x180089c22  mov     rcx, [rsi+208h]; wchar_t *
0x180089c29  call    ?GetBlockIdFromString@CTpAzureStorageTransport@@SAJPEB_WAEAK@Z; CTpAzureStorageTransport::GetBlockIdFromString(wchar_t const *,ulong &)
0x180089c2e  mov     ebx, eax
0x180089c30  xor     eax, eax
0x180089c32  test    ebx, ebx
0x180089c34  js      loc_180089FA1
0x180089c3a  mov     [rbp+730h+var_778], rax
0x180089c3e  test    r14, r14
0x180089c41  jz      short loc_180089C5B
0x180089c43  mov     rcx, r14; hToken
0x180089c46  call    cs:__imp_ImpersonateLoggedOnUser
0x180089c4d  nop     dword ptr [rax+rax+00h]
0x180089c52  mov     r15d, eax
0x180089c55  mov     [rbp+730h+arg_0], eax
0x180089c5b  mov     r9, [rdi+30h]
0x180089c5f  mov     rax, [rbp+730h+var_770]
0x180089c63  mov     [rsp+830h+var_7F8], rax; struct ITpCallbacks *
0x180089c68  lea     rax, [rbp+730h+var_778]
0x180089c6c  mov     [rsp+830h+var_800], rax; unsigned __int64 *
0x180089c71  lea     rax, [rbp+730h+var_7B0]
0x180089c75  mov     [rsp+830h+var_808], rax; unsigned int *
0x180089c7a  mov     rax, [rdi+28h]
0x180089c7e  mov     [rsp+830h+var_810], rax; void *
0x180089c83  mov     r9, [r9+19A0h]; unsigned __int64
0x180089c8a  mov     r8, [rbp+730h+arg_8]; struct IWerByteStream *
0x180089c91  mov     edx, r12d; unsigned int
0x180089c94  mov     rcx, [rsi+1A0h]; pwszUrl
0x180089c9b  call    ?UploadFileToAzureUsingSAS@CTpAzureStorageTransport@@SAJPEB_WKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z; CTpAzureStorageTransport::UploadFileToAzureUsingSAS(wchar_t const *,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)
0x180089ca0  mov     ebx, eax
0x180089ca2  test    r15d, r15d
0x180089ca5  jz      short loc_180089CBD
0x180089ca7  call    cs:__imp_RevertToSelf
0x180089cae  nop     dword ptr [rax+rax+00h]
0x180089cb3  xor     r15d, r15d
0x180089cb6  mov     [rbp+730h+arg_0], r15d
0x180089cbd  mov     rcx, [rdi+30h]
0x180089cc1  mov     eax, [rbp+730h+var_7B0]
0x180089cc4  mov     [rcx+1998h], eax
0x180089cca  mov     rcx, [rdi+30h]
0x180089cce  mov     rax, [rbp+730h+var_778]
0x180089cd2  add     [rcx+19A0h], rax
0x180089cd9  mov     edx, ebx; int
0x180089cdb  mov     rcx, rdi; this
0x180089cde  call    ?LogAzureExchangeEvent@COCATpTransport@@IEBAXJ@Z; COCATpTransport::LogAzureExchangeEvent(long)
0x180089ce3  test    ebx, ebx
0x180089ce5  jns     short loc_180089D26
0x180089ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180089cee  lea     rax, WPP_GLOBAL_Control
0x180089cf5  cmp     rcx, rax
0x180089cf8  jz      short loc_180089D18
0x180089cfa  test    byte ptr [rcx+1Ch], 1
0x180089cfe  jz      short loc_180089D18
0x180089d00  mov     edx, 58h ; 'X'
0x180089d05  mov     r9d, ebx
0x180089d08  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180089d0f  mov     rcx, [rcx+10h]
0x180089d13  call    WPP_SF_d
0x180089d18  cmp     ebx, 80190193h
0x180089d1e  jnz     short loc_180089D53
0x180089d20  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180089d24  jnb     short loc_180089D53
0x180089d26  lea     rcx, [rbp+730h+var_7A0]; this
0x180089d2a  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180089d2f  nop
0x180089d30  lea     rcx, [rbp+730h+var_720]; this
0x180089d34  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180089d39  cmp     ebx, 80190193h
0x180089d3f  jnz     short loc_180089D72
0x180089d41  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180089d45  jnb     short loc_180089D72
0x180089d47  mov     r14, [rbp+730h+arg_8]
0x180089d4e  jmp     loc_1800899C7
0x180089d53  lea     rcx, [rbp+730h+var_7A0]; this
0x180089d57  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180089d5c  nop
0x180089d5d  lea     rcx, [rbp+730h+var_720]; this
0x180089d61  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180089d66  lea     rsi, WPP_GLOBAL_Control
0x180089d6d  jmp     loc_18008A240
0x180089d72  lea     r13, aUploadcomplete; "uploadcompleted"
0x180089d79  mov     [rbp+730h+var_7A8], r13
0x180089d7d  mov     rcx, [rbp+730h+arg_8]
0x180089d84  cmp     dword ptr [rcx+10h], 0
0x180089d88  lea     rbx, aZip_0; "zip"
0x180089d8f  lea     rax, aCab_1; "cab"
0x180089d96  cmovz   rbx, rax
0x180089d9a  mov     rax, [rcx]
0x180089d9d  mov     rax, [rax+20h]
0x180089da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089da6  lea     rcx, [rbp+730h+var_3B0]
0x180089dad  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x180089db2  mov     [rsp+830h+var_810], r13; wchar_t *
0x180089db7  mov     r9, rbx; wchar_t *
0x180089dba  mov     r8, rax; unsigned __int64
0x180089dbd  mov     rdx, [rbp+730h+arg_10]; wchar_t *
  ... truncated ...
```
