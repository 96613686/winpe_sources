# CClientConfigDataCacheManager::DownloadAndReloadConfig(void)

- ea: `0x1800c4f64`
- end: `0x1800c53fc`
- name: `?DownloadAndReloadConfig@CClientConfigDataCacheManager@@QEAAJXZ`
- size: `1176`
- prototype: `__int64 __fastcall(CClientConfigDataCacheManager *__hidden this)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4e54`
- `0x1800c5a90`

## callees

- `0x18000ed04`
- `0x180013448`
- `0x180014330`
- `0x1800151c4`
- `0x180015860`
- `0x180017af0`
- `0x180018f80`
- `0x180019690`
- `0x18002d36c`
- `0x180035b8c`
- `0x1800406a8`
- `0x18004dfa4`
- `0x180053670`
- `0x18005c700`
- `0x1800859c4`
- `0x180085fdc`
- `0x18008609c`
- `0x180088c64`
- `0x180088e64`
- `0x1800a3b60`
- `0x1800c4924`
- `0x1800c4954`
- `0x1800c4984`
- `0x1800c4d94`
- `0x1800c4f64`
- `0x1800c6bd4`
- `0x1800c6e84`
- `0x1800c7308`
- `0x1800c789c`
- `0x1800c7b8c`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c52fb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c52fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5284`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c52b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5284`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c52b7`

## string_xrefs

- `0x1800c50a5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c50e2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c51b4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c521d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5368`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5024`: `DownloadAndReloadConfig`
- `0x1800c51d7`: `https://go.microsoft.com/fwlink/?LinkId=859524`
- `0x1800c50b6`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0`
- `0x1800c5098`: `Unable to generate user agent string 0x%x.`
- `0x1800c535b`: `ReadFile HTTP_STATUS (0x%x).`

## pseudocode

```c
__int64 __fastcall CClientConfigDataCacheManager::DownloadAndReloadConfig(CClientConfigDataCacheManager *this)
{
  __int64 v2; // rax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  int UserAgentString; // eax
  int v8; // eax
  HRESULT File; // eax
  const wchar_t *v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int *v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+54h] [rbp-ACh] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-98h] BYREF
  LPSTREAM ppstm; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[8]; // [rsp+78h] [rbp-88h] BYREF
  int v23; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v24[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v25[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[112]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+160h] [rbp+60h] BYREF
  __int64 v28; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v29[8]; // [rsp+180h] [rbp+80h] BYREF
  int v30[4]; // [rsp+188h] [rbp+88h] BYREF
  int v31; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v32[38]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v33; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v34; // [rsp+2E0h] [rbp+1E0h]
  __int64 v35; // [rsp+2F0h] [rbp+1F0h]
  _QWORD v36[42]; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  v16 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
  ppstm = 0;
  CONFIGDATA::CONFIGDATA((CONFIGDATA *)v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v19);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v22);
  v18 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v2 = lambda_e0d9cd9a486b1910261db8a5938169cb_::_lambda_e0d9cd9a486b1910261db8a5938169cb_(
         (unsigned int)v24,
         (_DWORD)this,
         (unsigned int)v22,
         (unsigned int)&v16,
         (__int64)&v33);
  wil::scope_exit__lambda_e0d9cd9a486b1910261db8a5938169cb___(v25, v2);
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "DownloadAndReloadConfig");
  v36[0] = &MSAClientTraceTelemetry::DownloadAndReloadConfig::`vftable';
  MSAClientTraceTelemetry::DownloadAndReloadConfig::StartActivity((MSAClientTraceTelemetry::DownloadAndReloadConfig *)v36);
  ATL::CSimpleStringT<unsigned short,0>::operator=(v22, (char *)this + 520);
  v3 = CClientConfigDataCacheManager::CheckConnection(this);
  v4 = v3;
  v16 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 1652;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      (const char *)v5,
      (int)v15);
    goto LABEL_35;
  }
  UserAgentString = CClientConfigDataCacheManager::GetUserAgentString(this, v20);
  v16 = UserAgentString;
  if ( UserAgentString >= 0 )
  {
    CClientConfigDataCacheManager::CopyConfigData(this, (struct CONFIGDATA *)v26);
    HTTPRequest::Reset((CClientConfigDataCacheManager *)((char *)this + 248));
    v15 = v30;
    v8 = HTTPRequest::Open((char *)this + 248, v20, (unsigned int)v30[2], v29);
    v4 = v8;
    v16 = v8;
    if ( v8 < 0 )
    {
      v5 = (unsigned int)v8;
      v6 = 1674;
      goto LABEL_6;
    }
    v17 = 0;
    v24[0] = &ExecutionContext::`vftable';
    v24[1] = &ComFunctions::`vftable';
    v24[2] = &StringSrvPassthrough::`vftable';
    File = IsMsaEnterpriseDeviceAuthEnabled(&v17);
    v4 = File;
    v16 = File;
    if ( File < 0 )
    {
      v6 = 1678;
      goto LABEL_11;
    }
    if ( v17 == 1 )
    {
      if ( !*(_DWORD *)(v28 - 16) )
      {
LABEL_14:
        v10 = L"https://go.microsoft.com/fwlink/?LinkId=859524";
        goto LABEL_19;
      }
      v11 = &v28;
    }
    else
    {
      if ( !*(_DWORD *)(v27 - 16) )
        goto LABEL_14;
      v11 = &v27;
    }
    v10 = *(const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(v11);
LABEL_19:
    ATL::CSimpleStringT<unsigned short,0>::SetString(v19, v10);
    LODWORD(v15) = v19[0];
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0x69Eu,
      L"URL: %ls\n");
    if ( *(int *)(v32[0] - 16LL) <= 0 )
      goto LABEL_24;
    v12 = *((_QWORD *)this + 103);
    if ( !v12 )
    {
      v4 = -2147188728;
      v5 = 2147778568LL;
      v6 = 1699;
      goto LABEL_6;
    }
    File = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(*(_QWORD *)v12 + 24LL))(v12, v32, &v23);
    v4 = File;
    v16 = File;
    if ( File >= 0 )
    {
LABEL_24:
      *((_QWORD *)&v34 + 1) = GetTickCount64();
      v16 = HTTPRequest::RequestUrl((int)this + 248, (int)v19, (int)&v31, (int)&v23, &v18);
      LODWORD(v33) = GetTickCount64() - DWORD2(v34);
      HIDWORD(v33) = v18;
      v4 = v16;
      if ( v16 < 0 )
      {
        v5 = (unsigned int)v16;
        v6 = 1715;
        goto LABEL_6;
      }
      if ( v18 == 200 )
      {
        File = CreateStreamOnHGlobal(0, 1, &ppstm);
        v4 = File;
        v16 = File;
        if ( File < 0 )
        {
          v6 = 1719;
          goto LABEL_11;
        }
        File = HTTPRequest::ReadFile((char *)this + 248, v13, ppstm);
        v4 = File;
        v16 = File;
        if ( File < 0 )
        {
          v6 = 1721;
          goto LABEL_11;
        }
        File = CClientConfigDataCacheManager::SaveDownloadedData(this, ppstm);
        v4 = File;
        v16 = File;
        if ( File < 0 )
        {
          v6 = 1724;
          goto LABEL_11;
        }
      }
      else
      {
        LODWORD(v15) = v18;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          0x6C0u,
          L"ReadFile HTTP_STATUS (0x%x).",
          v15);
      }
      wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36);
      v4 = 0;
      goto LABEL_35;
    }
    v6 = 1702;
LABEL_11:
    v5 = (unsigned int)File;
    goto LABEL_6;
  }
  LODWORD(v15) = UserAgentString;
  TracePrintW(
    3u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    0x679u,
    L"Unable to generate user agent string 0x%x.");
  ATL::CSimpleStringT<char,0>::SetString(v20, "Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0");
  v4 = v16;
  if ( v16 < 0 )
  {
    v5 = (unsigned int)v16;
    v6 = 1659;
    goto LABEL_6;
  }
LABEL_35:
  MSAClientTraceTelemetry::DownloadAndReloadConfig::~DownloadAndReloadConfig((MSAClientTraceTelemetry::DownloadAndReloadConfig *)v36);
  wil::details::lambda_call__lambda_9a9fadcf22f2423b96ce814514c36e41___::_lambda_call__lambda_9a9fadcf22f2423b96ce814514c36e41___(v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v22);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v19);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
  CONFIGDATA::~CONFIGDATA((CONFIGDATA *)v26);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppstm);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v23);
  return v4;
}

```

## disassembly

```asm
0x1800c4f64  push    rbp
0x1800c4f66  push    rbx
0x1800c4f67  push    rsi
0x1800c4f68  push    r14
0x1800c4f6a  lea     rbp, [rsp-368h]
0x1800c4f72  sub     rsp, 468h
0x1800c4f79  mov     rax, cs:__security_cookie
0x1800c4f80  xor     rax, rsp
0x1800c4f83  mov     [rbp+380h+var_30], rax
0x1800c4f8a  mov     rsi, rcx
0x1800c4f8d  mov     dword ptr [rsp+480h+var_430], 0
0x1800c4f95  lea     rcx, [rbp+380h+var_400]
0x1800c4f99  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c4f9e  nop
0x1800c4f9f  mov     [rsp+480h+ppstm], 0
0x1800c4fa8  lea     rcx, [rbp+380h+var_3B0]; this
0x1800c4fac  call    ??0CONFIGDATA@@QEAA@XZ; CONFIGDATA::CONFIGDATA(void)
0x1800c4fb1  nop
0x1800c4fb2  lea     rcx, [rsp+480h+var_418]
0x1800c4fb7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c4fbc  nop
0x1800c4fbd  lea     rcx, [rsp+480h+var_420]
0x1800c4fc2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c4fc7  nop
0x1800c4fc8  lea     rcx, [rsp+480h+var_408]
0x1800c4fcd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c4fd2  nop
0x1800c4fd3  mov     [rsp+480h+var_428], 0
0x1800c4fdb  xorps   xmm0, xmm0
0x1800c4fde  xor     eax, eax
0x1800c4fe0  movups  [rbp+380h+var_1B0], xmm0
0x1800c4fe7  movups  [rbp+380h+var_1A0], xmm0
0x1800c4fee  mov     [rbp+380h+var_190], rax
0x1800c4ff5  lea     rax, [rbp+380h+var_1B0]
0x1800c4ffc  mov     [rsp+480h+var_460], rax
0x1800c5001  lea     r9, [rsp+480h+var_430]
0x1800c5006  lea     r8, [rsp+480h+var_408]
0x1800c500b  mov     rdx, rsi
0x1800c500e  lea     rcx, [rbp+380h+var_3F8]
0x1800c5012  call    _lambda_e0d9cd9a486b1910261db8a5938169cb____lambda_e0d9cd9a486b1910261db8a5938169cb_
0x1800c5017  mov     rdx, rax
0x1800c501a  lea     rcx, [rbp+380h+var_3D8]
0x1800c501e  call    wil__scope_exit__lambda_e0d9cd9a486b1910261db8a5938169cb___
0x1800c5023  nop
0x1800c5024  lea     rdx, aDownloadandrel; "DownloadAndReloadConfig"
0x1800c502b  lea     rcx, [rbp+380h+var_180]
0x1800c5032  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c5037  lea     rax, ??_7DownloadAndReloadConfig@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::DownloadAndReloadConfig::`vftable'
0x1800c503e  mov     [rbp+380h+var_180], rax
0x1800c5045  lea     rcx, [rbp+380h+var_180]; this
0x1800c504c  call    ?StartActivity@DownloadAndReloadConfig@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::DownloadAndReloadConfig::StartActivity(void)
0x1800c5051  nop
0x1800c5052  lea     rdx, [rsi+208h]
0x1800c5059  lea     rcx, [rsp+480h+var_408]
0x1800c505e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c5063  mov     rcx, rsi; this
0x1800c5066  call    ?CheckConnection@CClientConfigDataCacheManager@@QEAAJXZ; CClientConfigDataCacheManager::CheckConnection(void)
0x1800c506b  mov     ebx, eax
0x1800c506d  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5071  test    eax, eax
0x1800c5073  jns     short loc_1800C507F
0x1800c5075  mov     r9d, eax
0x1800c5078  mov     edx, 674h
0x1800c507d  jmp     short loc_1800C50DB
0x1800c507f  lea     rdx, [rsp+480h+var_418]
0x1800c5084  mov     rcx, rsi
0x1800c5087  call    ?GetUserAgentString@CClientConfigDataCacheManager@@QEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CClientConfigDataCacheManager::GetUserAgentString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800c508c  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5090  test    eax, eax
0x1800c5092  jns     short loc_1800C50F3
0x1800c5094  mov     dword ptr [rsp+480h+var_460], eax; int
0x1800c5098  lea     r9, aUnableToGenera; "Unable to generate user agent string 0x"...
0x1800c509f  mov     r8d, 679h; unsigned int
0x1800c50a5  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c50ac  mov     ecx, 3; unsigned __int8
0x1800c50b1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c50b6  lea     rdx, aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x1800c50bd  lea     rcx, [rsp+480h+var_418]
0x1800c50c2  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x1800c50c7  mov     ebx, dword ptr [rsp+480h+var_430]
0x1800c50cb  test    ebx, ebx
0x1800c50cd  jns     loc_1800C5388
0x1800c50d3  mov     r9d, ebx; char *
0x1800c50d6  mov     edx, 67Bh; void *
0x1800c50db  mov     rcx, [rbp+388h]; this
0x1800c50e2  lea     r8, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c50e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c50ee  jmp     loc_1800C5388
0x1800c50f3  lea     rdx, [rbp+380h+var_3B0]; struct CONFIGDATA *
0x1800c50f7  mov     rcx, rsi; this
0x1800c50fa  call    ?CopyConfigData@CClientConfigDataCacheManager@@QEAAXAEAUCONFIGDATA@@@Z; CClientConfigDataCacheManager::CopyConfigData(CONFIGDATA &)
0x1800c50ff  lea     r14, [rsi+0F8h]
0x1800c5106  mov     rcx, r14; this
0x1800c5109  call    ?Reset@HTTPRequest@@QEAAXXZ; HTTPRequest::Reset(void)
0x1800c510e  mov     eax, [rbp+380h+var_338]
0x1800c5111  mov     [rsp+480h+var_440], eax
0x1800c5115  mov     eax, [rbp+380h+var_334]
0x1800c5118  mov     [rsp+480h+var_448], eax
0x1800c511c  mov     eax, [rbp+380h+var_33C]
0x1800c511f  mov     [rsp+480h+var_450], eax
0x1800c5123  mov     eax, [rbp+380h+var_340]
0x1800c5126  mov     [rsp+480h+var_458], eax
0x1800c512a  lea     rax, [rbp+380h+var_2F8]
0x1800c5131  mov     [rsp+480h+var_460], rax; int
0x1800c5136  lea     r9, [rbp+380h+var_300]
0x1800c513d  mov     r8d, [rbp+380h+var_2F0]
0x1800c5144  lea     rdx, [rsp+480h+var_418]
0x1800c5149  mov     rcx, r14
0x1800c514c  call    ?Open@HTTPRequest@@QEAAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@K00KKKK@Z; HTTPRequest::Open(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ulong,ulong,ulong,ulong)
0x1800c5151  mov     ebx, eax
0x1800c5153  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5157  test    eax, eax
0x1800c5159  jns     short loc_1800C5168
0x1800c515b  mov     r9d, eax
0x1800c515e  mov     edx, 68Ah
0x1800c5163  jmp     loc_1800C50DB
0x1800c5168  mov     dword ptr [rsp+480h+var_430+4], 0
0x1800c5170  lea     rax, ??_7ExecutionContext@@6B@; const ExecutionContext::`vftable'
0x1800c5177  mov     [rbp+380h+var_3F8], rax
0x1800c517b  lea     rax, ??_7ComFunctions@@6B@; const ComFunctions::`vftable'
0x1800c5182  mov     [rbp+380h+var_3F0], rax
0x1800c5186  lea     rax, ??_7StringSrvPassthrough@@6B@; const StringSrvPassthrough::`vftable'
0x1800c518d  mov     [rbp+380h+var_3E8], rax
0x1800c5191  lea     rcx, [rsp+480h+var_430+4]; int *
0x1800c5196  call    ?IsMsaEnterpriseDeviceAuthEnabled@@YAJPEAH@Z; IsMsaEnterpriseDeviceAuthEnabled(int *)
0x1800c519b  mov     ebx, eax
0x1800c519d  mov     dword ptr [rsp+480h+var_430], eax
0x1800c51a1  test    eax, eax
0x1800c51a3  jns     short loc_1800C51C6
0x1800c51a5  mov     edx, 68Eh; void *
0x1800c51aa  mov     r9d, eax; char *
0x1800c51ad  mov     rcx, [rbp+388h]; this
0x1800c51b4  lea     r8, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c51bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c51c0  nop
0x1800c51c1  jmp     loc_1800C5388
0x1800c51c6  cmp     dword ptr [rsp+480h+var_430+4], 1
0x1800c51cb  jnz     short loc_1800C51E6
0x1800c51cd  mov     rax, [rbp+380h+var_318]
0x1800c51d1  cmp     dword ptr [rax-10h], 0
0x1800c51d5  jnz     short loc_1800C51E0
0x1800c51d7  lea     rdx, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x1800c51de  jmp     short loc_1800C51FC
0x1800c51e0  lea     rcx, [rbp+380h+var_318]
0x1800c51e4  jmp     short loc_1800C51F4
0x1800c51e6  mov     rax, [rbp+380h+var_320]
0x1800c51ea  cmp     dword ptr [rax-10h], 0
0x1800c51ee  jz      short loc_1800C51D7
0x1800c51f0  lea     rcx, [rbp+380h+var_320]
0x1800c51f4  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1800c51f9  mov     rdx, [rax]
0x1800c51fc  lea     rcx, [rsp+480h+var_420]
0x1800c5201  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800c5206  mov     rax, qword ptr [rsp+480h+var_420]
0x1800c520b  mov     [rsp+480h+var_460], rax
0x1800c5210  lea     r9, aUrlLs; "URL: %ls\n"
0x1800c5217  mov     r8d, 69Eh; unsigned int
0x1800c521d  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5224  mov     ecx, 5; unsigned __int8
0x1800c5229  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c522e  mov     rax, [rbp+380h+var_2E0]
0x1800c5235  cmp     dword ptr [rax-10h], 0
0x1800c5239  jle     short loc_1800C5284
0x1800c523b  mov     rcx, [rsi+338h]
0x1800c5242  test    rcx, rcx
0x1800c5245  jnz     short loc_1800C5259
0x1800c5247  mov     ebx, 80048008h
0x1800c524c  mov     r9d, ebx
0x1800c524f  mov     edx, 6A3h
0x1800c5254  jmp     loc_1800C51AD
0x1800c5259  mov     rax, [rcx]
0x1800c525c  lea     r8, [rbp+380h+var_400]
0x1800c5260  lea     rdx, [rbp+380h+var_2E0]
0x1800c5267  mov     rax, [rax+18h]
0x1800c526b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5270  mov     ebx, eax
0x1800c5272  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5276  test    eax, eax
0x1800c5278  jns     short loc_1800C5284
0x1800c527a  mov     edx, 6A6h
0x1800c527f  jmp     loc_1800C51AA
0x1800c5284  call    cs:__imp_GetTickCount64
0x1800c528a  mov     qword ptr [rbp+380h+var_1A0+8], rax
0x1800c5291  lea     rax, [rsp+480h+var_428]
0x1800c5296  mov     [rsp+480h+var_460], rax; LPVOID
0x1800c529b  lea     r9, [rbp+380h+var_400]; int
0x1800c529f  lea     r8, [rbp+380h+var_2E8]; int
0x1800c52a6  lea     rdx, [rsp+480h+var_420]; int
0x1800c52ab  mov     rcx, r14; int
0x1800c52ae  call    ?RequestUrl@HTTPRequest@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1AEAK@Z; HTTPRequest::RequestUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x1800c52b3  mov     dword ptr [rsp+480h+var_430], eax
0x1800c52b7  call    cs:__imp_GetTickCount64
0x1800c52bd  sub     eax, dword ptr [rbp+380h+var_1A0+8]
0x1800c52c3  mov     dword ptr [rbp+380h+var_1B0], eax
0x1800c52c9  mov     eax, [rsp+480h+var_428]
0x1800c52cd  mov     dword ptr [rbp+380h+var_1B0+0Ch], eax
0x1800c52d3  mov     ebx, dword ptr [rsp+480h+var_430]
0x1800c52d7  test    ebx, ebx
0x1800c52d9  jns     short loc_1800C52E8
0x1800c52db  mov     r9d, ebx
0x1800c52de  mov     edx, 6B3h
0x1800c52e3  jmp     loc_1800C51AD
0x1800c52e8  cmp     eax, 0C8h
0x1800c52ed  jnz     short loc_1800C5357
0x1800c52ef  lea     r8, [rsp+480h+ppstm]; ppstm
0x1800c52f4  mov     edx, 1; fDeleteOnRelease
0x1800c52f9  xor     ecx, ecx; hGlobal
0x1800c52fb  call    cs:__imp_CreateStreamOnHGlobal
0x1800c5301  mov     ebx, eax
0x1800c5303  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5307  test    eax, eax
0x1800c5309  jns     short loc_1800C5315
0x1800c530b  mov     edx, 6B7h
0x1800c5310  jmp     loc_1800C51AA
0x1800c5315  mov     r8, [rsp+480h+ppstm]
0x1800c531a  mov     rcx, r14
0x1800c531d  call    ?ReadFile@HTTPRequest@@QEAAJPEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAUIStream@@@Z; HTTPRequest::ReadFile(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *,IStream *)
0x1800c5322  mov     ebx, eax
0x1800c5324  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5328  test    eax, eax
0x1800c532a  jns     short loc_1800C5336
0x1800c532c  mov     edx, 6B9h
0x1800c5331  jmp     loc_1800C51AA
0x1800c5336  mov     rdx, [rsp+480h+ppstm]; struct IStream *
0x1800c533b  mov     rcx, rsi; this
0x1800c533e  call    ?SaveDownloadedData@CClientConfigDataCacheManager@@AEAAJPEAUIStream@@@Z; CClientConfigDataCacheManager::SaveDownloadedData(IStream *)
0x1800c5343  mov     ebx, eax
0x1800c5345  mov     dword ptr [rsp+480h+var_430], eax
0x1800c5349  test    eax, eax
0x1800c534b  jns     short loc_1800C5379
0x1800c534d  mov     edx, 6BCh
0x1800c5352  jmp     loc_1800C51AA
0x1800c5357  mov     dword ptr [rsp+480h+var_460], eax
0x1800c535b  lea     r9, aReadfileHttpSt; "ReadFile HTTP_STATUS (0x%x)."
0x1800c5362  mov     r8d, 6C0h; unsigned int
0x1800c5368  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c536f  mov     ecx, 2; unsigned __int8
0x1800c5374  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5379  lea     rcx, [rbp+380h+var_180]
0x1800c5380  call    ?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800c5385  nop
0x1800c5386  xor     ebx, ebx
0x1800c5388  lea     rcx, [rbp+380h+var_180]; this
0x1800c538f  call    ??1DownloadAndReloadConfig@MSAClientTraceTelemetry@@QEAA@XZ; MSAClientTraceTelemetry::DownloadAndReloadConfig::~DownloadAndReloadConfig(void)
0x1800c5394  nop
0x1800c5395  lea     rcx, [rbp+380h+var_3D8]
0x1800c5399  call    wil__details__lambda_call__lambda_9a9fadcf22f2423b96ce814514c36e41______lambda_call__lambda_9a9fadcf22f2423b96ce814514c36e41___
0x1800c539e  nop
0x1800c539f  lea     rcx, [rsp+480h+var_408]
0x1800c53a4  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c53a9  nop
0x1800c53aa  lea     rcx, [rsp+480h+var_420]
0x1800c53af  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c53b4  nop
0x1800c53b5  lea     rcx, [rsp+480h+var_418]
0x1800c53ba  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c53bf  nop
0x1800c53c0  lea     rcx, [rbp+380h+var_3B0]; this
0x1800c53c4  call    ??1CONFIGDATA@@QEAA@XZ; CONFIGDATA::~CONFIGDATA(void)
0x1800c53c9  nop
0x1800c53ca  lea     rcx, [rsp+480h+ppstm]
0x1800c53cf  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800c53d4  nop
0x1800c53d5  lea     rcx, [rbp+380h+var_400]
0x1800c53d9  call    ??1?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800c53de  mov     eax, ebx
0x1800c53e0  mov     rcx, [rbp+380h+var_30]
0x1800c53e7  xor     rcx, rsp; StackCookie
0x1800c53ea  call    __security_check_cookie
0x1800c53ef  add     rsp, 468h
0x1800c53f6  pop     r14
0x1800c53f8  pop     rsi
0x1800c53f9  pop     rbx
0x1800c53fa  pop     rbp
0x1800c53fb  retn
```
