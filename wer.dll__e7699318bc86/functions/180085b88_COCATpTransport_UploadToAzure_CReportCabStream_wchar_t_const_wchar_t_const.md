# COCATpTransport::UploadToAzure(CReportCabStream *,wchar_t const *,wchar_t const *)

- ea: `0x180085b88`
- end: `0x1800865f0`
- name: `?UploadToAzure@COCATpTransport@@IEAAJPEAVCReportCabStream@@PEB_W1@Z`
- size: `2664`
- prototype: `__int64 __fastcall(COCATpTransport *__hidden this, struct CReportCabStream *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800843d0`

## callees

- `0x180004198`
- `0x180004bb4`
- `0x180009ad4`
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
- `0x18004559c`
- `0x180045bdc`
- `0x1800489f0`
- `0x18004c774`
- `0x1800720ec`
- `0x180072d90`
- `0x180077844`
- `0x180083bdc`
- `0x1800851d4`
- `0x1800855ac`
- `0x180085b88`
- `0x18008f36c`
- `0x18008f4e4`
- `0x18008f7b8`
- `0x1800a1d70`
- `0x1800a28b4`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085e20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085e38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085e20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085e38`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085de7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085f39`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008619d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085de7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180085f39`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008619d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085d54`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085ede`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800860a9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085d54`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085ede`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800860a9`

## string_xrefs

- `0x180085ffe`: `uploadcompleted`

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
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
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
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v47)
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
                          0,
                          (CTpResponseMessage *)v42,
                          0,
                          v46,
                          v10,
                          0,
                          (__int64)v18,
                          *((void **)this + 5),
                          (COCATpTransport *)((char *)this + 192),
                          v41,
                          0,
                          (wchar_t *)v58,
                          (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
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
      (__int64)v23,
      v51,
      (v28 - v51) >> 3);
    BlockIdFromString = CTpTransport::DoExchange(
                          (struct CTpRequestMessage *)v54,
                          0,
                          (CTpResponseMessage *)v50,
                          0,
                          v27,
                          v10,
                          0,
                          (__int64)v18,
                          *((void **)this + 5),
                          (COCATpTransport *)((char *)this + 192),
                          (wchar_t *)L"uploadcompleted",
                          0,
                          (wchar_t *)v58,
                          (struct WINHTTP_TIMEOUTS *)&httpTimeoutsLongerReceiveTimeout,
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v42);
  if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 0x400000000000LL) )
  {
    LODWORD(v56) = BlockIdFromString;
    v55 = *((_DWORD *)this + 88);
    v46 = (struct ITpCallbacks *)L"OCA";
    v45 = v42[0];
    v44 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v37,
      (__int64)&dword_1800C92AC,
      v38,
      v39,
      (__int64)&v44,
      (const size_t **)&v41,
      (const size_t **)&v45,
      (const size_t **)&v46,
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
0x180085b88  mov     rax, rsp
0x180085b8b  mov     [rax+20h], r9
0x180085b8f  mov     [rax+18h], r8
0x180085b93  mov     [rax+10h], rdx
0x180085b97  push    rbp
0x180085b98  push    rbx
0x180085b99  push    rsi
0x180085b9a  push    rdi
0x180085b9b  push    r12
0x180085b9d  push    r13
0x180085b9f  push    r14
0x180085ba1  push    r15
0x180085ba3  lea     rbp, [rax-738h]
0x180085baa  sub     rsp, 7F8h
0x180085bb1  mov     r14, rdx
0x180085bb4  mov     rdi, rcx
0x180085bb7  lea     rcx, [rbp+730h+var_3B0]; this
0x180085bbe  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180085bc3  nop
0x180085bc4  lea     rcx, [rbp+730h+var_748]; this
0x180085bc8  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180085bcd  nop
0x180085bce  xor     ebx, ebx
0x180085bd0  mov     r15d, ebx
0x180085bd3  mov     [rbp+730h+arg_0], ebx
0x180085bd9  mov     [rbp+730h+var_7B0], ebx
0x180085bdc  mov     rcx, [rdi+30h]
0x180085be0  lea     rsi, [rcx+8]
0x180085be4  add     rcx, 0C910h; this
0x180085beb  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180085bf0  mov     dword ptr [rbp+730h+var_780], eax
0x180085bf3  mov     r13d, ebx
0x180085bf6  lea     rax, [rbp+730h+var_758]
0x180085bfa  mov     [rbp+730h+var_768], rax
0x180085bfe  lea     rax, [rbp+730h+var_758]
0x180085c02  mov     [rbp+730h+var_760], rax
0x180085c06  mov     [rbp+730h+var_758], bx
0x180085c0a  mov     rdx, [rsi]
0x180085c0d  lea     rcx, [rbp+730h+var_768]
0x180085c11  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180085c16  lea     rdx, WPP_GLOBAL_Control
0x180085c1d  test    al, al
0x180085c1f  jnz     short loc_180085C4C
0x180085c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180085c28  cmp     rcx, rdx
0x180085c2b  jz      short loc_180085C4C
0x180085c2d  test    byte ptr [rcx+1Ch], 2
0x180085c31  jz      short loc_180085C4C
0x180085c33  lea     edx, [rbx+4Bh]
0x180085c36  mov     r9d, 8007000Eh
0x180085c3c  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085c43  mov     rcx, [rcx+10h]
0x180085c47  call    WPP_SF_d
0x180085c4c  mov     r12d, ebx
0x180085c4f  mov     rcx, [rdi+30h]
0x180085c53  add     rcx, 0B660h; this
0x180085c5a  call    ?IsUploadOnFreeNetworksOnly@CSettings@@QEBAHXZ; CSettings::IsUploadOnFreeNetworksOnly(void)
0x180085c5f  test    eax, eax
0x180085c61  jz      short loc_180085C77
0x180085c63  mov     rcx, [rdi+30h]; this
0x180085c67  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180085c6c  test    eax, eax
0x180085c6e  mov     eax, 2
0x180085c73  cmovz   r12d, eax
0x180085c77  lea     rbx, aZip_0; "zip"
0x180085c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180085c85  lea     rax, WPP_GLOBAL_Control
0x180085c8c  cmp     rcx, rax
0x180085c8f  jz      short loc_180085CB2
0x180085c91  test    byte ptr [rcx+1Ch], 4
0x180085c95  jz      short loc_180085CB2
0x180085c97  inc     r13d
0x180085c9a  mov     edx, 4Ch ; 'L'
0x180085c9f  mov     r9d, r13d
0x180085ca2  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085ca9  mov     rcx, [rcx+10h]
0x180085cad  call    WPP_SF_d
0x180085cb2  lea     rcx, [rbp+730h+var_720]; this
0x180085cb6  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180085cbb  nop
0x180085cbc  lea     rcx, [rbp+730h+var_7A0]; this
0x180085cc0  call    ??0CTpResponseMessage@@QEAA@XZ; CTpResponseMessage::CTpResponseMessage(void)
0x180085cc5  nop
0x180085cc6  mov     rax, [rdi+30h]
0x180085cca  mov     rcx, [rax+19A8h]
0x180085cd1  xor     edx, edx
0x180085cd3  test    rcx, rcx
0x180085cd6  jz      short loc_180085CE4
0x180085cd8  cmp     [rcx], dx
0x180085cdb  lea     rax, aRenewsas; "renewsas"
0x180085ce2  jnz     short loc_180085CEB
0x180085ce4  lea     rax, aGetdestination; "getdestination"
0x180085ceb  mov     [rbp+730h+var_7A8], rax
0x180085cef  cmp     [r14+10h], edx
0x180085cf3  lea     rax, aCab_1; "cab"
0x180085cfa  cmovz   rbx, rax
0x180085cfe  mov     rax, [r14]
0x180085d01  mov     rcx, r14
0x180085d04  mov     rax, [rax+20h]
0x180085d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d0d  lea     rcx, [rbp+730h+var_720]
0x180085d11  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x180085d16  mov     rcx, [rbp+730h+var_7A8]
0x180085d1a  mov     [rsp+830h+var_810], rcx; wchar_t *
0x180085d1f  mov     r9, rbx; wchar_t *
0x180085d22  mov     r8, rax; unsigned __int64
0x180085d25  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180085d2c  mov     rcx, rdi; this
0x180085d2f  call    ?PrepareResumableUploadRequest@COCATpTransport@@IEAAJPEB_W_K00PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareResumableUploadRequest(wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CTpRequestMessage *)
0x180085d34  mov     ebx, eax
0x180085d36  xor     r9d, r9d
0x180085d39  test    eax, eax
0x180085d3b  js      loc_18008647A
0x180085d41  mov     rax, [rdi+30h]
0x180085d45  mov     r14, [rax+0CB58h]
0x180085d4c  test    r14, r14
0x180085d4f  jz      short loc_180085D66
0x180085d51  mov     rcx, r14; hToken
0x180085d54  call    cs:__imp_ImpersonateLoggedOnUser
0x180085d5a  mov     r15d, eax
0x180085d5d  mov     [rbp+730h+arg_0], eax
0x180085d63  xor     r9d, r9d
0x180085d66  lea     r8, [rdi+0C0h]
0x180085d6d  mov     rcx, rdi
0x180085d70  lea     rdx, [rdi+20h]
0x180085d74  neg     rcx
0x180085d77  sbb     rcx, rcx
0x180085d7a  and     rcx, rdx
0x180085d7d  mov     [rbp+730h+var_770], rcx
0x180085d81  mov     [rsp+70h], r9d; int
0x180085d86  lea     rax, ?httpTimeoutsLongerReceiveTimeout@@3UWINHTTP_TIMEOUTS@@A; WINHTTP_TIMEOUTS httpTimeoutsLongerReceiveTimeout
0x180085d8d  mov     [rsp+830h+var_7C8], rax; __int64
0x180085d92  mov     rax, [rbp+730h+arg_18]
0x180085d99  mov     [rsp+830h+var_7D0], rax; __int64
0x180085d9e  mov     qword ptr [rsp+830h+var_7D8], r9; int
0x180085da3  mov     rax, [rbp+730h+var_7A8]
0x180085da7  mov     [rsp+830h+var_7E0], rax; __int64
0x180085dac  mov     [rsp+830h+var_7E8], r8; __int64
0x180085db1  mov     rax, [rdi+28h]
0x180085db5  mov     [rsp+830h+var_7F0], rax; __int64
0x180085dba  mov     [rsp+830h+var_7F8], r14; __int64
0x180085dbf  mov     [rsp+830h+var_800], r9; int
0x180085dc4  mov     dword ptr [rsp+830h+var_808], r12d; int
0x180085dc9  mov     [rsp+830h+var_810], rcx; struct ITpCallbacks *
0x180085dce  xor     r9d, r9d
0x180085dd1  lea     r8, [rbp+730h+var_7A0]
0x180085dd5  xor     edx, edx
0x180085dd7  lea     rcx, [rbp+730h+var_720]; this
0x180085ddb  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180085de0  mov     ebx, eax
0x180085de2  test    r15d, r15d
0x180085de5  jz      short loc_180085DF8
0x180085de7  call    cs:__imp_RevertToSelf
0x180085ded  xor     eax, eax
0x180085def  mov     r15d, eax
0x180085df2  mov     [rbp+730h+arg_0], eax
0x180085df8  test    ebx, ebx
0x180085dfa  js      loc_180086457
0x180085e00  lea     rdx, [rbp+730h+var_7A0]; struct CTpResponseMessage *
0x180085e04  mov     rcx, rdi; this
0x180085e07  call    ?ParseResumableUploadResponse@COCATpTransport@@IEAAJPEAVCTpResponseMessage@@@Z; COCATpTransport::ParseResumableUploadResponse(CTpResponseMessage *)
0x180085e0c  mov     ebx, eax
0x180085e0e  test    eax, eax
0x180085e10  js      loc_180086437
0x180085e16  lea     rdx, aRejectedByRule; "REJECTED_BY_RULE"
0x180085e1d  mov     rcx, [rsi]
0x180085e20  call    cs:__imp__o__wcsicmp
0x180085e26  test    eax, eax
0x180085e28  jz      loc_180086364
0x180085e2e  lea     rdx, aInvalidRequest; "INVALID_REQUEST"
0x180085e35  mov     rcx, [rsi]
0x180085e38  call    cs:__imp__o__wcsicmp
0x180085e3e  test    eax, eax
0x180085e40  jz      loc_180086314
0x180085e46  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180085e4d  mov     rcx, rdi; this
0x180085e50  call    ?SaveResumeState@COCATpTransport@@IEAAJPEB_W@Z; COCATpTransport::SaveResumeState(wchar_t const *)
0x180085e55  mov     ebx, eax
0x180085e57  test    eax, eax
0x180085e59  js      loc_1800862E9
0x180085e5f  lea     rcx, [rdi+38h]; this
0x180085e63  mov     rdx, [rdi+30h]; struct CReport *
0x180085e67  call    ?SaveToReport@COCAReply@@QEAAJPEAVCReport@@@Z; COCAReply::SaveToReport(CReport *)
0x180085e6c  mov     ebx, eax
0x180085e6e  xor     eax, eax
0x180085e70  test    ebx, ebx
0x180085e72  js      loc_1800862AE
0x180085e78  mov     rdx, [rsi+1A0h]; wchar_t *
0x180085e7f  test    rdx, rdx
0x180085e82  jz      loc_18008627A
0x180085e88  cmp     [rdx], ax
0x180085e8b  jz      loc_18008627A
0x180085e91  mov     rcx, [rdi+30h]; this
0x180085e95  call    ?SetCabUrl@CReport@@QEAAJPEB_W@Z; CReport::SetCabUrl(wchar_t const *)
0x180085e9a  mov     ebx, eax
0x180085e9c  test    eax, eax
0x180085e9e  js      loc_18008624F
0x180085ea4  mov     rcx, [rdi+30h]
0x180085ea8  mov     rax, [rsi+200h]
0x180085eaf  mov     [rcx+19A0h], rax
0x180085eb6  lea     rdx, [rbp+730h+var_7B0]; unsigned int *
0x180085eba  mov     rcx, [rsi+208h]; wchar_t *
0x180085ec1  call    ?GetBlockIdFromString@CTpAzureStorageTransport@@SAJPEB_WAEAK@Z; CTpAzureStorageTransport::GetBlockIdFromString(wchar_t const *,ulong &)
0x180085ec6  mov     ebx, eax
0x180085ec8  xor     eax, eax
0x180085eca  test    ebx, ebx
0x180085ecc  js      loc_180086221
0x180085ed2  mov     [rbp+730h+var_778], rax
0x180085ed6  test    r14, r14
0x180085ed9  jz      short loc_180085EED
0x180085edb  mov     rcx, r14; hToken
0x180085ede  call    cs:__imp_ImpersonateLoggedOnUser
0x180085ee4  mov     r15d, eax
0x180085ee7  mov     [rbp+730h+arg_0], eax
0x180085eed  mov     r9, [rdi+30h]
0x180085ef1  mov     rax, [rbp+730h+var_770]
0x180085ef5  mov     [rsp+830h+var_7F8], rax; struct ITpCallbacks *
0x180085efa  lea     rax, [rbp+730h+var_778]
0x180085efe  mov     [rsp+830h+var_800], rax; unsigned __int64 *
0x180085f03  lea     rax, [rbp+730h+var_7B0]
0x180085f07  mov     [rsp+830h+var_808], rax; unsigned int *
0x180085f0c  mov     rax, [rdi+28h]
0x180085f10  mov     [rsp+830h+var_810], rax; void *
0x180085f15  mov     r9, [r9+19A0h]; unsigned __int64
0x180085f1c  mov     r8, [rbp+730h+arg_8]; struct IWerByteStream *
0x180085f23  mov     edx, r12d; unsigned int
0x180085f26  mov     rcx, [rsi+1A0h]; pwszUrl
0x180085f2d  call    ?UploadFileToAzureUsingSAS@CTpAzureStorageTransport@@SAJPEB_WKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z; CTpAzureStorageTransport::UploadFileToAzureUsingSAS(wchar_t const *,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)
0x180085f32  mov     ebx, eax
0x180085f34  test    r15d, r15d
0x180085f37  jz      short loc_180085F49
0x180085f39  call    cs:__imp_RevertToSelf
0x180085f3f  xor     r15d, r15d
0x180085f42  mov     [rbp+730h+arg_0], r15d
0x180085f49  mov     rcx, [rdi+30h]
0x180085f4d  mov     eax, [rbp+730h+var_7B0]
0x180085f50  mov     [rcx+1998h], eax
0x180085f56  mov     rcx, [rdi+30h]
0x180085f5a  mov     rax, [rbp+730h+var_778]
0x180085f5e  add     [rcx+19A0h], rax
0x180085f65  mov     edx, ebx; int
0x180085f67  mov     rcx, rdi; this
0x180085f6a  call    ?LogAzureExchangeEvent@COCATpTransport@@IEBAXJ@Z; COCATpTransport::LogAzureExchangeEvent(long)
0x180085f6f  test    ebx, ebx
0x180085f71  jns     short loc_180085FB2
0x180085f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180085f7a  lea     rax, WPP_GLOBAL_Control
0x180085f81  cmp     rcx, rax
0x180085f84  jz      short loc_180085FA4
0x180085f86  test    byte ptr [rcx+1Ch], 1
0x180085f8a  jz      short loc_180085FA4
0x180085f8c  mov     edx, 58h ; 'X'
0x180085f91  mov     r9d, ebx
0x180085f94  lea     r8, WPP_e978319962c6324aa7974808bc8c2b8c_Traceguids
0x180085f9b  mov     rcx, [rcx+10h]
0x180085f9f  call    WPP_SF_d
0x180085fa4  cmp     ebx, 80190193h
0x180085faa  jnz     short loc_180085FDF
0x180085fac  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180085fb0  jnb     short loc_180085FDF
0x180085fb2  lea     rcx, [rbp+730h+var_7A0]; this
0x180085fb6  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180085fbb  nop
0x180085fbc  lea     rcx, [rbp+730h+var_720]; this
0x180085fc0  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180085fc5  cmp     ebx, 80190193h
0x180085fcb  jnz     short loc_180085FFE
0x180085fcd  cmp     r13d, dword ptr [rbp+730h+var_780]
0x180085fd1  jnb     short loc_180085FFE
0x180085fd3  mov     r14, [rbp+730h+arg_8]
0x180085fda  jmp     loc_180085C77
0x180085fdf  lea     rcx, [rbp+730h+var_7A0]; this
0x180085fe3  call    ??1CTpResponseMessage@@UEAA@XZ; CTpResponseMessage::~CTpResponseMessage(void)
0x180085fe8  nop
0x180085fe9  lea     rcx, [rbp+730h+var_720]; this
0x180085fed  call    ??1CTpRequestMessage@@UEAA@XZ; CTpRequestMessage::~CTpRequestMessage(void)
0x180085ff2  lea     rsi, WPP_GLOBAL_Control
0x180085ff9  jmp     loc_1800864BF
0x180085ffe  lea     r13, aUploadcomplete; "uploadcompleted"
0x180086005  mov     [rbp+730h+var_7A8], r13
0x180086009  mov     rcx, [rbp+730h+arg_8]
0x180086010  cmp     dword ptr [rcx+10h], 0
0x180086014  lea     rbx, aZip_0; "zip"
0x18008601b  lea     rax, aCab_1; "cab"
0x180086022  cmovz   rbx, rax
0x180086026  mov     rax, [rcx]
0x180086029  mov     rax, [rax+20h]
0x18008602d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086032  lea     rcx, [rbp+730h+var_3B0]
0x180086039  mov     [rsp+830h+var_808], rcx; struct CTpRequestMessage *
0x18008603e  mov     [rsp+830h+var_810], r13; wchar_t *
0x180086043  mov     r9, rbx; wchar_t *
0x180086046  mov     r8, rax; unsigned __int64
0x180086049  mov     rdx, [rbp+730h+arg_10]; wchar_t *
0x180086050  mov     rcx, rdi; this
0x180086053  call    ?PrepareResumableUploadRequest@COCATpTransport@@IEAAJPEB_W_K00PEAVCTpRequestMessage@@@Z; COCATpTransport::PrepareResumableUploadRequest(wchar_t const *,unsigned __int64,wchar_t const *,wchar_t const *,CTpRequestMessage *)
0x180086058  mov     ebx, eax
0x18008605a  test    eax, eax
0x18008605c  jns     short loc_18008609C
0x18008605e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
