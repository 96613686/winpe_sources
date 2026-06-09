# COSDownloader::AddPayloadFileToDownloadRequest_Legacy(ISusHandlerNotification *,wchar_t const *,ulong,tagDSFile * *,OSDownloadProgress *)

- ea: `0x180021d90`
- end: `0x18002284a`
- name: `?AddPayloadFileToDownloadRequest_Legacy@COSDownloader@@AEAAJPEAUISusHandlerNotification@@PEB_WKPEAPEAUtagDSFile@@PEAUOSDownloadProgress@@@Z`
- size: `2746`
- prototype: `__int64 __fastcall(COSDownloader *this, struct ISusHandlerNotification *, const wchar_t *, int, struct tagDSFile **, struct OSDownloadProgress *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180020290`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a4f4`
- `0x18000af44`
- `0x18000fcfc`
- `0x180010f54`
- `0x180018f18`
- `0x180019cc4`
- `0x18001a8b8`
- `0x18001ee5c`
- `0x180020e94`
- `0x180021d90`
- `0x1800232b0`
- `0x180023404`
- `0x180023548`
- `0x180023c1c`
- `0x180042630`
- `0x180042a24`
- `0x180049260`
- `0x1800492e0`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002208c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002208c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022781`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002210c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002210c`

## string_xrefs

- `0x1800224ed`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1800223a4`: `UpdatePriority`
- `0x1800227cd`: `UUP handler decided to use the volume %ws for the update %ws.`
- `0x18002252f`: `UUP handler: PreDownload finished for the update %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COSDownloader::AddPayloadFileToDownloadRequest_Legacy(
        COSDownloader *this,
        struct ISusHandlerNotification *a2,
        const wchar_t *a3,
        int a4,
        struct tagDSFile **a5,
        struct OSDownloadProgress *a6)
{
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r12
  GUID *v10; // r14
  int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 DownloadProperties; // rax
  _QWORD *v16; // r13
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, LPVOID *); // rbx
  HRESULT v21; // eax
  int v22; // ecx
  _DWORD *v23; // r13
  int v24; // eax
  char *v25; // rbx
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  const struct std::nothrow_t *v28; // rdx
  int v29; // eax
  int v30; // eax
  _BOOL8 v31; // rbx
  __int64 (__fastcall *v32)(__int64, struct IDeploymentDownloadRequest **); // rbx
  int v33; // eax
  bool v34; // cl
  unsigned int v35; // ebx
  __int64 v36; // rcx
  struct OSDownloadProgress *v37; // rbx
  int v39; // eax
  __int64 v40; // rdx
  struct OSDownloadProgress *v41; // rbx
  struct IDeploymentDownloadRequest *v42; // rbx
  int (__fastcall *v43)(struct IDeploymentDownloadRequest *, LPVOID *); // r14
  void *v44; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  int v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *v51; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  struct OSDownloadProgress *v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h]
  IID rclsid; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h] BYREF
  GUID v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  LPVOID *v60; // [rsp+C0h] [rbp-40h]
  LPVOID *p_pv; // [rsp+C8h] [rbp-38h]
  COSDownloader *v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  char *v65; // [rsp+E8h] [rbp-18h]
  _BYTE v66[40]; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v67; // [rsp+118h] [rbp+18h] BYREF
  struct tagDSFile **v68; // [rsp+120h] [rbp+20h] BYREF
  int v69[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v70[14]; // [rsp+130h] [rbp+30h] BYREF
  LPVOID v71; // [rsp+1A0h] [rbp+A0h] BYREF
  struct IDeploymentDownloadRequest *v72; // [rsp+1A8h] [rbp+A8h] BYREF
  LPVOID pv; // [rsp+1B0h] [rbp+B0h] BYREF
  LPVOID v74; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v75; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v76[112]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *(_QWORD *)v69 = a2;
  v67 = a3;
  v48 = a4;
  v68 = a5;
  v53 = a6;
  pv = 0;
  v7 = 0;
  v49 = 0;
  v64 = 0;
  v8 = 0;
  v52 = 0;
  v72 = 0;
  v74 = 0;
  v71 = 0;
  v9 = 0;
  v55 = 0;
  v10 = (GUID *)((char *)this + 308);
  Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v76, (COSDownloader *)((char *)this + 308));
  v57 = 0;
  v58 = GUID_NULL;
  v59 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl) )
  {
    v11 = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire((struct _GUID *)&v57, v10, (void **)0x493E0);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v11,
        ppv);
      goto LABEL_65;
    }
  }
  v63 = 1;
  v60 = &v71;
  p_pv = &pv;
  v62 = this;
  if ( !a6 )
  {
    v12 = -2147467261;
    v13 = 2147500035LL;
    v14 = 1642;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)v13,
      ppv);
    goto LABEL_62;
  }
  memset(v70, 0, sizeof(v70));
  v70[1] = v76;
  v70[4] = *((_QWORD *)this + 48);
  v70[0] = *((_QWORD *)this + 44);
  v70[2] = *((_QWORD *)this + 45);
  v70[3] = *((_QWORD *)this + 46);
  v70[7] = *((_QWORD *)this + 47);
  DownloadProperties = COSDownloader::GetDownloadProperties(this, v66);
  *(_OWORD *)((char *)&v70[8] + 4) = *(_OWORD *)DownloadProperties;
  *(_OWORD *)((char *)&v70[10] + 4) = *(_OWORD *)(DownloadProperties + 16);
  HIDWORD(v70[12]) = *(_DWORD *)(DownloadProperties + 32);
  LODWORD(v70[13]) = *((_DWORD *)this + 118) == 1;
  v65 = (char *)this + 80;
  if ( this != (COSDownloader *)-80LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_BYTE *)this + 16) )
  {
    v12 = -2145116152;
    goto LABEL_15;
  }
  v16 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 16) )
  {
    v12 = -2145124343;
    v17 = 2149842953LL;
    v18 = 1665;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)v17,
      ppv);
LABEL_15:
    if ( this != (COSDownloader *)-80LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    goto LABEL_62;
  }
  v51 = v70;
  rclsid = (IID)xmmword_1800766B8;
  v54 = *((_QWORD *)this + 43);
  *(_QWORD *)v50 = *((_QWORD *)this + 35);
  v19 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t *,wchar_t const * &,wchar_t *,unsigned long &,tagDSFile * * &,_GUID,unsigned long const &,tagOptionalSessionInfo6 *>(
          (int)this + 128,
          (unsigned int)v50,
          (unsigned int)&v67,
          (unsigned int)&v54,
          (__int64)&v48,
          (__int64)&v68,
          (__int64)&rclsid);
  v12 = v19;
  if ( v19 < 0 )
  {
    v17 = (unsigned int)v19;
    v18 = 1692;
    goto LABEL_14;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
  v9 = *v16;
  v55 = *v16;
  if ( this != (COSDownloader *)-80LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v20 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v9 + 24LL);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v21 = v20(v9, &pv);
  v12 = v21;
  if ( v21 < 0 )
  {
    v14 = 1699;
LABEL_42:
    v13 = (unsigned int)v21;
    goto LABEL_43;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  rclsid = (IID)xmmword_1800766B8;
  v21 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_c8264914_c0d2_48da_a5cd_f47d74fda7f6, &v71);
  v12 = v21;
  if ( v21 < 0 )
  {
    v14 = 1704;
    goto LABEL_42;
  }
  v22 = *((_DWORD *)this + 104);
  v23 = (_DWORD *)((char *)this + 392);
  if ( v22 )
  {
    v48 = *v23 + v22;
    v51 = 0;
    WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile>>::ReleaseAndAllocArray(
      &v51,
      (unsigned int)v48);
    v25 = (char *)v51;
    memmove(v51, *((const void **)this + 50), 248LL * (unsigned int)*v23);
    memmove(&v25[248 * *v23], *((const void **)this + 53), 248LL * *((unsigned int *)this + 104));
    *(_QWORD *)v50 = v25;
    v26 = Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,unsigned long &,unsigned long const &,tagDSFile * const &>(
            (unsigned int)&v49,
            (int)this + 288,
            (int)this + 336,
            (unsigned int)&v48,
            (__int64)v50);
    v12 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C0,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v26,
        ppv);
      if ( v25 )
        operator delete(v25, v28);
      goto LABEL_30;
    }
    if ( v25 )
      operator delete(v25, v27);
LABEL_36:
    v7 = v49;
    v21 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v71 + 24LL))(v71, pv, v49);
    v12 = v21;
    if ( v21 < 0 )
    {
      v14 = 1731;
      goto LABEL_42;
    }
    *((_BYTE *)this + 17) = 1;
    *(_QWORD *)v50 = this;
    v67 = (const wchar_t *)*((_QWORD *)this + 44);
    v29 = Microsoft::WRL::Details::MakeAndInitialize<COSGDRProgress,COSGDRProgress,_GUID &,tagDSGlobalUpdateId &,wchar_t *,ISusHandlerNotification * &,OSDownloader::ICancelObject *,enum tagDownloadType &>(
            (unsigned int)&v52,
            (int)this + 292,
            (int)this + 308,
            (unsigned int)&v67,
            (__int64)v69,
            (__int64)v50,
            (__int64)this + 472);
    v12 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CD,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v29,
        ppv);
      v8 = v52;
      goto LABEL_62;
    }
    v8 = v52;
    v21 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v71 + 32LL))(v71, pv, v52);
    v12 = v21;
    if ( v21 < 0 )
    {
      v14 = 1743;
      goto LABEL_42;
    }
    v75 = 0;
    v30 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
            v9,
            &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
            &v75);
    if ( v30 < 0
      || !v75
      || (v31 = *((_DWORD *)this + 115) == 1,
          ppva = 0,
          WUTrace(0, 0, 4096, 5),
          v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _BOOL8))(*(_QWORD *)v75 + 168LL))(
                  v75,
                  0,
                  L"UpdatePriority",
                  v31),
          v30 < 0) )
    {
      ppva = v30;
      WUTrace(0, 0, 4096, 5);
    }
    *((_BYTE *)this + 18) = 1;
    v32 = *(__int64 (__fastcall **)(__int64, struct IDeploymentDownloadRequest **))(*(_QWORD *)v9 + 32LL);
    if ( v72 )
    {
      (*(void (__fastcall **)(struct IDeploymentDownloadRequest *))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    v33 = v32(v9, &v72);
    v35 = v33;
    if ( v33 < 0 )
    {
      if ( v33 != -2145116152 && (unsigned int)(v33 + 2147024894) > 1 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6FB,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)v33,
          ppva);
      v12 = v35;
      goto LABEL_60;
    }
    if ( (unsigned int)AreTestKeysAllowed(v34)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v36,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"PreDownloadTestEnabled",
                         0)
      && *((_DWORD *)this + 118) == 1 )
    {
      v37 = v53;
      *((_DWORD *)v53 + 12) = 0;
      *((_QWORD *)v37 + 5) = 0;
      WUTrace(0, 0, 4096, 4);
LABEL_59:
      v12 = 0;
      goto LABEL_60;
    }
    v39 = AddFileToDownloadRequest(
            *((_DWORD *)this + 98),
            *((const struct tagDSFile *const *)this + 50),
            *((struct ISusFileRequestList **)this + 34),
            *((_DWORD *)this + 104),
            *((const struct tagDSFile *const *)this + 53),
            *((struct ISusFileRequestList **)this + 54),
            *((_DWORD *)this + 110),
            *((const struct tagDSFile *const *)this + 56),
            v72,
            *((_DWORD *)this + 117));
    v12 = v39;
    if ( v39 >= 0 )
    {
      v41 = v53;
      v39 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64))(*(_QWORD *)v72 + 32LL))(
              v72,
              (__int64)v53 + 48);
      v12 = v39;
      if ( v39 >= 0 )
      {
        if ( (*(int (__fastcall **)(struct IDeploymentDownloadRequest *, __int64))(*(_QWORD *)v72 + 56LL))(
               v72,
               (__int64)v41 + 40) < 0 )
          *((_QWORD *)v41 + 5) = 0;
        v42 = v72;
        v43 = *(int (__fastcall **)(struct IDeploymentDownloadRequest *, LPVOID *))(*(_QWORD *)v72 + 24LL);
        if ( v74 )
        {
          CoTaskMemFree(v74);
          v74 = 0;
        }
        if ( v43(v42, &v74) < 0 || !v74 )
          goto LABEL_59;
        ppvb = 0;
        WUTrace(0, 0, 4096, 4);
        v44 = (void *)*((_QWORD *)this + 33);
        if ( v44 )
        {
          CSusBaseAllocTag<942762101>::operator delete(v44);
          *((_QWORD *)this + 33) = 0;
        }
        v39 = DuplicateString<wchar_t *,wchar_t *>(v74, (char *)this + 264);
        v12 = v39;
        if ( v39 >= 0 )
          goto LABEL_59;
        v40 = 1837;
      }
      else
      {
        v40 = 1819;
      }
    }
    else
    {
      v40 = 1817;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)(unsigned int)v39,
      ppvb);
LABEL_60:
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    goto LABEL_62;
  }
  v24 = Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,unsigned long &,unsigned long const &,tagDSFile * const &>(
          (unsigned int)&v49,
          (int)this + 288,
          (int)this + 336,
          (int)this + 392,
          (__int64)this + 400);
  v12 = v24;
  if ( v24 >= 0 )
    goto LABEL_36;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6B0,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
    (const char *)(unsigned int)v24,
    ppv);
LABEL_30:
  v7 = v49;
LABEL_62:
  if ( v71 )
  {
    (*(void (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v71 + 40LL))(v71, pv);
    (*(void (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v71 + 48LL))(v71, pv);
  }
  *((_BYTE *)this + 17) = 0;
LABEL_65:
  OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v57);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v71 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v74 )
  {
    CoTaskMemFree(v74);
    v74 = 0;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(struct IDeploymentDownloadRequest *))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( pv )
    CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x180021d90  push    rbp
0x180021d92  push    rbx
0x180021d93  push    rsi
0x180021d94  push    rdi
0x180021d95  push    r12
0x180021d97  push    r13
0x180021d99  push    r14
0x180021d9b  push    r15
0x180021d9d  lea     rbp, [rsp-158h]
0x180021da5  sub     rsp, 258h
0x180021dac  mov     rax, cs:__security_cookie
0x180021db3  xor     rax, rsp
0x180021db6  mov     [rbp+190h+var_50], rax
0x180021dbd  mov     r15, rcx
0x180021dc0  mov     qword ptr [rbp+190h+var_168], rdx
0x180021dc4  mov     [rbp+190h+var_178], r8
0x180021dc8  mov     [rsp+290h+var_240], r9d
0x180021dcd  mov     rax, [rbp+190h+arg_20]
0x180021dd4  mov     [rbp+190h+var_170], rax
0x180021dd8  mov     rbx, [rbp+190h+arg_28]
0x180021ddf  mov     [rsp+290h+var_218], rbx
0x180021de4  mov     [rbp+190h+pv], 0
0x180021def  xor     edi, edi
0x180021df1  mov     [rsp+290h+var_238], rdi
0x180021df6  mov     [rbp+190h+var_1B0], rdi
0x180021dfa  xor     esi, esi
0x180021dfc  mov     [rsp+290h+var_220], rsi
0x180021e01  mov     [rbp+190h+var_E8], rsi
0x180021e08  mov     [rbp+190h+var_D8], rsi
0x180021e0f  mov     [rbp+190h+var_F0], rsi
0x180021e16  xor     r12d, r12d
0x180021e19  mov     [rbp+190h+var_208], r12
0x180021e1d  lea     r14, [rcx+134h]
0x180021e24  mov     rdx, r14; struct tagDSGlobalUpdateId *
0x180021e27  lea     rcx, [rbp+190h+var_C0]; this
0x180021e2e  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180021e33  xorps   xmm0, xmm0
0x180021e36  movups  xmmword ptr [rbp+190h+var_1F0.Data1], xmm0
0x180021e3a  movups  [rbp+190h+var_1E0], xmm0
0x180021e3e  mov     qword ptr [rbp+190h+var_1F0.Data1], r12
0x180021e42  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180021e49  movdqu  xmmword ptr [rbp+190h+var_1F0.Data4], xmm1
0x180021e4e  mov     qword ptr [rbp+190h+var_1E0+8], r12
0x180021e52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x180021e59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x180021e5e  test    al, al
0x180021e60  jz      short loc_180021E9B
0x180021e62  mov     r8d, 493E0h; void **
0x180021e68  mov     rdx, r14; rguid
0x180021e6b  lea     rcx, [rbp+190h+var_1F0]; this
0x180021e6f  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJAEBU_GUID@@K@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(_GUID const &,ulong)
0x180021e74  mov     r14d, eax
0x180021e77  test    eax, eax
0x180021e79  jns     short loc_180021E9B
0x180021e7b  mov     rcx, [rbp+198h]; this
0x180021e82  mov     r9d, eax; char *
0x180021e85  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021e8c  mov     edx, 65Ah; void *
0x180021e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e96  jmp     loc_1800225BA
0x180021e9b  xorps   xmm0, xmm0
0x180021e9e  movups  [rbp+190h+var_1D0], xmm0
0x180021ea2  movups  [rbp+190h+var_1C0], xmm0
0x180021ea6  lea     rax, [rbp+190h+var_F0]
0x180021ead  mov     qword ptr [rbp+190h+var_1D0], rax
0x180021eb1  lea     rax, [rbp+190h+pv]
0x180021eb8  mov     qword ptr [rbp+190h+var_1D0+8], rax
0x180021ebc  mov     qword ptr [rbp+190h+var_1C0], r15
0x180021ec0  mov     byte ptr [rbp+190h+var_1C0+8], 1
0x180021ec4  test    rbx, rbx
0x180021ec7  jnz     short loc_180021EDC
0x180021ec9  mov     r14d, 80004003h
0x180021ecf  mov     r9d, r14d
0x180021ed2  mov     edx, 66Ah
0x180021ed7  jmp     loc_18002233C
0x180021edc  xor     edx, edx; Val
0x180021ede  lea     r8d, [rdx+70h]; Size
0x180021ee2  lea     rcx, [rbp+190h+var_160]; void *
0x180021ee6  call    memset
0x180021eeb  lea     rax, [rbp+190h+var_C0]
0x180021ef2  mov     [rbp+190h+var_158], rax
0x180021ef6  mov     rax, [r15+180h]
0x180021efd  mov     [rbp+190h+var_140], rax
0x180021f01  mov     rax, [r15+160h]
0x180021f08  mov     [rbp+190h+var_160], rax
0x180021f0c  mov     rax, [r15+168h]
0x180021f13  mov     [rbp+190h+var_150], rax
0x180021f17  mov     rax, [r15+170h]
0x180021f1e  mov     [rbp+190h+var_148], rax
0x180021f22  mov     rax, [r15+178h]
0x180021f29  mov     [rbp+190h+var_128], rax
0x180021f2d  lea     rdx, [rbp+190h+var_1A0]
0x180021f31  mov     rcx, r15
0x180021f34  call    ?GetDownloadProperties@COSDownloader@@QEAA?BUtagSessionDownloadProperties@@XZ; COSDownloader::GetDownloadProperties(void)
0x180021f39  movups  xmm0, xmmword ptr [rax]
0x180021f3c  movups  [rbp+190h+var_11C], xmm0
0x180021f40  movups  xmm1, xmmword ptr [rax+10h]
0x180021f44  movups  [rbp+190h+var_10C], xmm1
0x180021f4b  mov     eax, [rax+20h]
0x180021f4e  mov     [rbp+190h+var_FC], eax
0x180021f54  xor     eax, eax
0x180021f56  cmp     dword ptr [r15+1D8h], 1
0x180021f5e  setz    al
0x180021f61  mov     [rbp+190h+var_F8], eax
0x180021f67  lea     rbx, [r15+50h]
0x180021f6b  mov     [rbp+190h+var_1A8], rbx
0x180021f6f  test    rbx, rbx
0x180021f72  jz      short loc_180021F7F
0x180021f74  lea     rcx, [rbx+8]; lpCriticalSection
0x180021f78  call    cs:__imp_EnterCriticalSection
0x180021f7e  nop
0x180021f7f  cmp     byte ptr [r15+10h], 0
0x180021f84  jz      short loc_180021F91
0x180021f86  mov     r14d, 80242008h
0x180021f8c  jmp     loc_180022039
0x180021f91  lea     r13, [r15+80h]
0x180021f98  cmp     qword ptr [r13+0], 0
0x180021f9d  jz      short loc_180021FAF
0x180021f9f  mov     r14d, 80240009h
0x180021fa5  mov     r9d, r14d
0x180021fa8  mov     edx, 681h
0x180021fad  jmp     short loc_180022025
0x180021faf  lea     rax, [rbp+190h+var_160]
0x180021fb3  mov     [rsp+290h+var_228], rax
0x180021fb8  movups  xmm0, cs:xmmword_1800766B8
0x180021fbf  movdqu  xmmword ptr [rbp+190h+rclsid.Data1], xmm0
0x180021fc4  mov     rax, [r15+158h]
0x180021fcb  mov     [rbp+190h+var_210], rax
0x180021fcf  mov     rax, [r15+118h]
0x180021fd6  mov     qword ptr [rsp+290h+var_230], rax
0x180021fdb  lea     rax, [rsp+290h+var_228]
0x180021fe0  mov     [rsp+290h+var_250], rax
0x180021fe5  lea     rax, [rbp+190h+rclsid]
0x180021fe9  mov     qword ptr [rsp+290h+var_260], rax
0x180021fee  lea     rax, [rbp+190h+var_170]
0x180021ff2  mov     [rsp+290h+var_268], rax
0x180021ff7  lea     rax, [rsp+290h+var_240]
0x180021ffc  mov     [rsp+290h+ppv], rax; int
0x180022001  lea     r9, [rbp+190h+var_210]
0x180022005  lea     r8, [rbp+190h+var_178]
0x180022009  lea     rdx, [rsp+290h+var_230]
0x18002200e  mov     rcx, r13
0x180022011  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@UIDeploymentSession@@PEA_WAEAPEB_WPEA_WAEAKAEAPEAPEAUtagDSFile@@U_GUID@@AEBKPEAUtagOptionalSessionInfo6@@@Details@WRL@Microsoft@@YAJPEAPEAUIDeploymentSession@@$$QEAPEA_WAEAPEB_W1AEAKAEAPEAPEAUtagDSFile@@$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo6@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t *,wchar_t const * &,wchar_t *,ulong &,tagDSFile * * &,_GUID,ulong const &,tagOptionalSessionInfo6 *>(IDeploymentSession * *,wchar_t * &&,wchar_t const * &,wchar_t * &&,ulong &,tagDSFile * * &,_GUID &&,ulong const &,tagOptionalSessionInfo6 * &&)
0x180022016  mov     r14d, eax
0x180022019  test    eax, eax
0x18002201b  jns     short loc_180022051
0x18002201d  mov     r9d, eax; char *
0x180022020  mov     edx, 69Ch; void *
0x180022025  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002202c  mov     rcx, [rbp+198h]; this
0x180022033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022038  nop
0x180022039  test    rbx, rbx
0x18002203c  jz      loc_18002257C
0x180022042  lea     rcx, [rbx+8]; lpCriticalSection
0x180022046  call    cs:__imp_LeaveCriticalSection
0x18002204c  jmp     loc_18002257C
0x180022051  mov     rcx, [r13+0]
0x180022055  mov     rax, [rcx]
0x180022058  mov     rax, [rax+8]
0x18002205c  call    _guard_dispatch_icall
0x180022061  mov     r12, [r13+0]
0x180022065  mov     [rbp+190h+var_208], r12
0x180022069  test    rbx, rbx
0x18002206c  jz      short loc_180022078
0x18002206e  lea     rcx, [rbx+8]; lpCriticalSection
0x180022072  call    cs:__imp_LeaveCriticalSection
0x180022078  mov     rax, [r12]
0x18002207c  mov     rbx, [rax+18h]
0x180022080  mov     rcx, [rbp+190h+pv]; pv
0x180022087  test    rcx, rcx
0x18002208a  jz      short loc_18002209D
0x18002208c  call    cs:__imp_CoTaskMemFree
0x180022092  mov     [rbp+190h+pv], 0
0x18002209d  lea     rdx, [rbp+190h+pv]
0x1800220a4  mov     rcx, r12
0x1800220a7  mov     rax, rbx
0x1800220aa  call    _guard_dispatch_icall
0x1800220af  mov     r14d, eax
0x1800220b2  test    eax, eax
0x1800220b4  jns     short loc_1800220C0
0x1800220b6  mov     edx, 6A3h
0x1800220bb  jmp     loc_180022339
0x1800220c0  mov     rcx, [rbp+190h+var_F0]
0x1800220c7  test    rcx, rcx
0x1800220ca  jz      short loc_1800220E3
0x1800220cc  mov     rax, [rcx]
0x1800220cf  mov     rax, [rax+10h]
0x1800220d3  call    _guard_dispatch_icall
0x1800220d8  mov     [rbp+190h+var_F0], 0
0x1800220e3  movups  xmm0, cs:xmmword_1800766B8
0x1800220ea  movdqu  xmmword ptr [rbp+190h+rclsid.Data1], xmm0
0x1800220ef  lea     rax, [rbp+190h+var_F0]
0x1800220f6  mov     [rsp+290h+ppv], rax; ppv
0x1800220fb  lea     r9, _GUID_c8264914_c0d2_48da_a5cd_f47d74fda7f6; riid
0x180022102  xor     edx, edx; pUnkOuter
0x180022104  lea     r8d, [rdx+17h]; dwClsContext
0x180022108  lea     rcx, [rbp+190h+rclsid]; rclsid
0x18002210c  call    cs:__imp_CoCreateInstance
0x180022112  mov     r14d, eax
0x180022115  test    eax, eax
0x180022117  jns     short loc_180022123
0x180022119  mov     edx, 6A8h
0x18002211e  jmp     loc_180022339
0x180022123  mov     ecx, [r15+1A0h]
0x18002212a  lea     r13, [r15+188h]
0x180022131  lea     rdi, [r15+150h]
0x180022138  lea     r14, [r15+120h]
0x18002213f  lea     rbx, [r15+190h]
0x180022146  test    ecx, ecx
0x180022148  jnz     short loc_180022192
0x18002214a  mov     [rsp+290h+ppv], rbx; int
0x18002214f  mov     r9, r13
0x180022152  mov     r8, rdi
0x180022155  mov     rdx, r14
0x180022158  lea     rcx, [rsp+290h+var_238]
0x18002215d  call    ??$MakeAndInitialize@VCUHOSDeploymentInformation@@V1@_NAEAKAEBKAEBQEAUtagDSFile@@@Details@WRL@Microsoft@@YAJPEAPEAVCUHOSDeploymentInformation@@$$QEA_NAEAKAEBKAEBQEAUtagDSFile@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,ulong &,ulong const &,tagDSFile * const &>(CUHOSDeploymentInformation * *,bool &&,ulong &,ulong const &,tagDSFile * const &)
0x180022162  mov     r14d, eax
0x180022165  test    eax, eax
0x180022167  jns     loc_18002225C
0x18002216d  mov     rcx, [rbp+198h]; this
0x180022174  mov     r9d, eax; char *
0x180022177  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002217e  mov     edx, 6B0h; void *
0x180022183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022188  mov     rdi, [rsp+290h+var_238]
0x18002218d  jmp     loc_18002257C
0x180022192  add     ecx, [r13+0]
0x180022196  mov     [rsp+290h+var_240], ecx
0x18002219a  mov     [rsp+290h+var_228], 0
0x1800221a3  mov     edx, ecx
0x1800221a5  lea     rcx, [rsp+290h+var_228]
0x1800221aa  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@UtagDSFile@@U?$STArrayZeroAllocPolicy@UtagDSFile@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile>>::ReleaseAndAllocArray(unsigned __int64)
0x1800221af  mov     eax, [r13+0]
0x1800221b3  imul    r8, rax, 0F8h; Size
0x1800221ba  mov     rdx, [rbx]; Src
0x1800221bd  mov     rbx, [rsp+290h+var_228]
0x1800221c2  mov     rcx, rbx; void *
0x1800221c5  call    memmove
0x1800221ca  mov     eax, [r15+1A0h]
0x1800221d1  imul    r8, rax, 0F8h; Size
0x1800221d8  mov     eax, [r13+0]
0x1800221dc  imul    rcx, rax, 0F8h
0x1800221e3  add     rcx, rbx; void *
0x1800221e6  mov     rdx, [r15+1A8h]; Src
0x1800221ed  call    memmove
0x1800221f2  mov     qword ptr [rsp+290h+var_230], rbx
0x1800221f7  lea     rax, [rsp+290h+var_230]
0x1800221fc  mov     [rsp+290h+ppv], rax; int
0x180022201  lea     r9, [rsp+290h+var_240]
0x180022206  mov     r8, rdi
0x180022209  mov     rdx, r14
0x18002220c  lea     rcx, [rsp+290h+var_238]
0x180022211  call    ??$MakeAndInitialize@VCUHOSDeploymentInformation@@V1@_NAEAKAEBKAEBQEAUtagDSFile@@@Details@WRL@Microsoft@@YAJPEAPEAVCUHOSDeploymentInformation@@$$QEA_NAEAKAEBKAEBQEAUtagDSFile@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,ulong &,ulong const &,tagDSFile * const &>(CUHOSDeploymentInformation * *,bool &&,ulong &,ulong const &,tagDSFile * const &)
0x180022216  mov     r14d, eax
0x180022219  test    eax, eax
0x18002221b  jns     short loc_18002224F
0x18002221d  mov     rcx, [rbp+198h]; this
0x180022224  mov     r9d, eax; char *
0x180022227  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002222e  mov     edx, 6C0h; void *
0x180022233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022238  nop
0x180022239  test    rbx, rbx
0x18002223c  jz      loc_180022188
0x180022242  mov     rcx, rbx; void *
0x180022245  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002224a  jmp     loc_180022188
0x18002224f  test    rbx, rbx
0x180022252  jz      short loc_18002225C
0x180022254  mov     rcx, rbx; void *
0x180022257  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002225c  mov     rcx, [rbp+190h+var_F0]
0x180022263  mov     rax, [rcx]
0x180022266  mov     rdi, [rsp+290h+var_238]
0x18002226b  mov     r8, rdi
0x18002226e  mov     rdx, [rbp+190h+pv]
0x180022275  mov     rax, [rax+18h]
0x180022279  call    _guard_dispatch_icall
0x18002227e  mov     r14d, eax
0x180022281  test    eax, eax
0x180022283  jns     short loc_18002228F
0x180022285  mov     edx, 6C3h
0x18002228a  jmp     loc_180022339
0x18002228f  mov     byte ptr [r15+11h], 1
0x180022294  mov     qword ptr [rsp+290h+var_230], r15
0x180022299  mov     rax, [r15+160h]
0x1800222a0  mov     [rbp+190h+var_178], rax
0x1800222a4  lea     rdx, [r15+124h]
0x1800222ab  lea     rax, [r15+1D8h]
0x1800222b2  mov     qword ptr [rsp+290h+var_260], rax
0x1800222b7  lea     rax, [rsp+290h+var_230]
0x1800222bc  mov     [rsp+290h+var_268], rax
0x1800222c1  lea     rax, [rbp+190h+var_168]
0x1800222c5  mov     [rsp+290h+ppv], rax; int
0x1800222ca  lea     r9, [rbp+190h+var_178]
0x1800222ce  lea     r8, [r15+134h]
0x1800222d5  lea     rcx, [rsp+290h+var_220]
0x1800222da  call    ??$MakeAndInitialize@VCOSGDRProgress@@V1@AEAU_GUID@@AEAUtagDSGlobalUpdateId@@PEA_WAEAPEAUISusHandlerNotification@@PEAUICancelObject@OSDownloader@@AEAW4tagDownloadType@@@Details@WRL@Microsoft@@YAJPEAPEAVCOSGDRProgress@@AEAU_GUID@@AEAUtagDSGlobalUpdateId@@$$QEAPEA_WAEAPEAUISusHandlerNotification@@$$QEAPEAUICancelObject@OSDownloader@@AEAW4tagDownloadType@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COSGDRProgress,COSGDRProgress,_GUID &,tagDSGlobalUpdateId &,wchar_t *,ISusHandlerNotification * &,OSDownloader::ICancelObject *,tagDownloadType &>(COSGDRProgress * *,_GUID &,tagDSGlobalUpdateId &,wchar_t * &&,ISusHandlerNotification * &,OSDownloader::ICancelObject * &&,tagDownloadType &)
0x1800222df  mov     r14d, eax
  ... truncated ...
```
