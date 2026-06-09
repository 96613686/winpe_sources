# COSDownloader::AddPayloadFileToDownloadRequest(ISusHandlerNotification *,wchar_t const *,ulong,tagDSFile * *)

- ea: `0x180021730`
- end: `0x180021d89`
- name: `?AddPayloadFileToDownloadRequest@COSDownloader@@AEAAJPEAUISusHandlerNotification@@PEB_WKPEAPEAUtagDSFile@@@Z`
- size: `1625`
- prototype: `__int64 __fastcall(COSDownloader *__hidden this, struct ISusHandlerNotification *, const wchar_t *, unsigned int, struct tagDSFile **)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020290`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a4f4`
- `0x18000af44`
- `0x18000c0b4`
- `0x18000fcfc`
- `0x180010f54`
- `0x180018f18`
- `0x180019cc4`
- `0x18001a8b8`
- `0x18001cb68`
- `0x18001e948`
- `0x180021730`
- `0x180022a8c`
- `0x180022e48`
- `0x180023204`
- `0x1800232b0`
- `0x1800239b4`
- `0x180023a34`
- `0x180023f6c`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021958`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002196b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021958`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002196b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002181f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800218fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002181f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800218fd`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180021ab3`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180021ade`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180021ab3`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180021ade`

## string_xrefs

- `0x180021b50`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180021a7c`: `Connection to remote UA process failed for the update %ws during GDR. Disconnecting COM objects`
- `0x180021c8e`: `UUP handler decided to use the volume %ws for the update %ws.`
- `0x180021b92`: `UUP handler: PreDownload finished for the update %ws.`

## pseudocode

```c
__int64 __fastcall COSDownloader::AddPayloadFileToDownloadRequest(
        COSDownloader *this,
        struct ISusHandlerNotification *a2,
        const wchar_t *a3,
        unsigned int a4,
        struct tagDSFile **a5)
{
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  int v12; // eax
  _QWORD *v13; // r15
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  IUnknown *v17; // rbx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, LPUNKNOWN, IUnknown *, struct RemoteDeploymentDownloadRequest **); // rdi
  int v20; // eax
  char v21; // cl
  int v22; // esi
  HRESULT v23; // eax
  HRESULT v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  void *v28; // rcx
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned int v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v33[2]; // [rsp+68h] [rbp-98h] BYREF
  LPUNKNOWN pUnk; // [rsp+78h] [rbp-88h] BYREF
  COSDownloader *v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  _QWORD v37[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  GUID v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  _BYTE v41[112]; // [rsp+C0h] [rbp-40h] BYREF
  int v42[2]; // [rsp+130h] [rbp+30h] BYREF
  struct RemoteDeploymentDownloadRequest *v43; // [rsp+138h] [rbp+38h] BYREF
  LPUNKNOWN v44; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)v42 = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80070057LL,
      v29);
    return 2147942487LL;
  }
  v38 = 0;
  v39 = GUID_NULL;
  v40 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl)
    || (v9 = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(
               (struct _GUID *)&v38,
               (GUID *)((char *)this + 308),
               (void **)0x493E0),
        v10 = v9,
        v9 >= 0) )
  {
    v33[0] = (char *)this + 80;
    if ( this != (COSDownloader *)-80LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( *((_BYTE *)this + 16) )
    {
      v10 = -2145116152;
      goto LABEL_13;
    }
    if ( !*((_QWORD *)this + 17) )
    {
      v11 = COSDownloader::InitializeGDRRemoteDeploymentSession(this, a3, a4, a5);
      v10 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5BA,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)v11,
          v29);
LABEL_13:
        if ( this != (COSDownloader *)-80LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
        goto LABEL_63;
      }
    }
    if ( this != (COSDownloader *)-80LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v36 = 1;
    v35 = this;
    v44 = 0;
    v12 = COSDownloader::InitializeOSDeploymentInformationForGDR(this, (struct IDeploymentInformation **)&v44);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CA,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v12,
        v29);
LABEL_60:
      if ( v44 )
      {
        ((void (__fastcall *)(LPUNKNOWN))v44->lpVtbl->Release)(v44);
        v44 = 0;
      }
      wil::details::lambda_call__lambda_1a3bc59f89afd235294e47090ed20a57___::_lambda_call__lambda_1a3bc59f89afd235294e47090ed20a57___(&v35);
      goto LABEL_63;
    }
    v33[0] = (char *)this + 536;
    if ( this != (COSDownloader *)-536LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    v13 = (_QWORD *)((char *)this + 584);
    v14 = *((_QWORD *)this + 73);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *v13 = 0;
    }
    v15 = Microsoft::WRL::Details::MakeAndInitialize<OSDownloader::CancelObject,OSDownloader::ICancelObject,>((char *)this + 584);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v15,
        v29);
      if ( this != (COSDownloader *)-536LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
      goto LABEL_60;
    }
    if ( this != (COSDownloader *)-536LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    v37[1] = 1;
    v37[0] = this;
    pUnk = 0;
    *(_QWORD *)v32 = *v13;
    v33[0] = *((_QWORD *)this + 44);
    v16 = Microsoft::WRL::Details::MakeAndInitialize<COSGDRProgress,COSGDRProgress,_GUID &,tagDSGlobalUpdateId &,wchar_t *,ISusHandlerNotification * &,OSDownloader::ICancelObject *,enum tagDownloadType &>(
            (unsigned int)&pUnk,
            (int)this + 292,
            (int)this + 308,
            (unsigned int)v33,
            (__int64)v42,
            (__int64)v32,
            (__int64)this + 472);
    v10 = v16;
    v17 = pUnk;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DD,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v16,
        v30);
LABEL_57:
      if ( v17 )
        ((void (__fastcall *)(IUnknown *))v17->lpVtbl->Release)(v17);
      wil::details::lambda_call__lambda_0e0097209a740d5e4491a9fb467518cc___::_lambda_call__lambda_0e0097209a740d5e4491a9fb467518cc___(v37);
      goto LABEL_60;
    }
    *(_WORD *)((char *)this + 17) = 257;
    v33[0] = this;
    v33[1] = 1;
    v43 = 0;
    v18 = *((_QWORD *)this + 17);
    v19 = *(__int64 (__fastcall **)(__int64, LPUNKNOWN, IUnknown *, struct RemoteDeploymentDownloadRequest **))(*(_QWORD *)v18 + 24LL);
    WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(&v43);
    v20 = v19(v18, v44, v17, &v43);
    v22 = v20;
    if ( v20 == -2147418110 || v20 == -2147023170 )
    {
      Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v41, (COSDownloader *)((char *)this + 308));
      v30 = v22;
      WUTrace(0, 0, 4096, 3);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl'::`2'::impl) )
      {
        v23 = CoDisconnectObject(v17, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x601,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)(unsigned int)v23,
            v22);
        v24 = CoDisconnectObject(v44, 0);
        v21 = (char)retaddr;
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x602,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)(unsigned int)v24,
            v30);
      }
    }
    if ( v22 < 0 )
    {
      if ( v22 != -2145116152 && (unsigned int)(v22 + 2147024894) > 1 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x609,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)v22,
          v30);
      v10 = v22;
      goto LABEL_56;
    }
    if ( (unsigned int)AreTestKeysAllowed(v21)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v25,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"PreDownloadTestEnabled",
                         0)
      && *((_DWORD *)this + 118) == 1 )
    {
      *(_DWORD *)(*((_QWORD *)this + 32) + 48LL) = 0;
      *(_QWORD *)(*((_QWORD *)this + 32) + 40LL) = 0;
      Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v41, (COSDownloader *)((char *)this + 308));
      WUTrace(0, 0, 4096, 4);
LABEL_55:
      v10 = 0;
      goto LABEL_56;
    }
    v32[0] = 0;
    v26 = AddFileToDownloadRequest(
            *((_DWORD *)this + 98),
            *((const struct tagDSFile *const *)this + 50),
            *((_DWORD *)this + 104),
            *((const struct tagDSFile *const *)this + 53),
            *((_DWORD *)this + 110),
            *((const struct tagDSFile *const *)this + 56),
            *((_DWORD *)this + 117),
            v43,
            *((struct ISusFileRequestList **)this + 34),
            *((struct ISusFileRequestList **)this + 54),
            v32);
    v10 = v26;
    if ( v26 >= 0 )
    {
      *(_DWORD *)(*((_QWORD *)this + 32) + 48LL) = *((_DWORD *)v43 + 2);
      *(_QWORD *)(*((_QWORD *)this + 32) + 40LL) = *((_QWORD *)v43 + 2);
      if ( !*(_QWORD *)v43 )
        goto LABEL_54;
      Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v41, (COSDownloader *)((char *)this + 308));
      v31 = 0;
      WUTrace(0, 0, 4096, 4);
      v28 = (void *)*((_QWORD *)this + 33);
      if ( v28 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v28);
        *((_QWORD *)this + 33) = 0;
      }
      v26 = DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)v43, (char *)this + 264);
      v10 = v26;
      if ( v26 >= 0 )
      {
LABEL_54:
        LOBYTE(v36) = v32[0] == 0;
        goto LABEL_55;
      }
      v27 = 1593;
    }
    else
    {
      v27 = 1577;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)(unsigned int)v26,
      v31);
LABEL_56:
    WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(&v43);
    *((_BYTE *)this + 17) = 0;
    goto LABEL_57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5AC,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
    (const char *)(unsigned int)v9,
    v29);
LABEL_63:
  OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v38);
  return v10;
}

```

## disassembly

```asm
0x180021730  push    rbp
0x180021732  push    rbx
0x180021733  push    rsi
0x180021734  push    rdi
0x180021735  push    r12
0x180021737  push    r13
0x180021739  push    r14
0x18002173b  push    r15
0x18002173d  lea     rbp, [rsp-58h]
0x180021742  sub     rsp, 158h
0x180021749  mov     rax, cs:__security_cookie
0x180021750  xor     rax, rsp
0x180021753  mov     [rbp+90h+var_48], rax
0x180021757  mov     r12d, r9d
0x18002175a  mov     r15, r8
0x18002175d  mov     r14, rcx
0x180021760  mov     qword ptr [rbp+90h+var_60], rdx
0x180021764  mov     r13, [rbp+90h+arg_20]
0x18002176b  test    rdx, rdx
0x18002176e  jnz     short loc_180021797
0x180021770  mov     rcx, [rbp+98h]; this
0x180021777  mov     ebx, 80070057h
0x18002177c  mov     r9d, ebx; char *
0x18002177f  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021786  mov     edx, 5A6h; void *
0x18002178b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021790  mov     eax, ebx
0x180021792  jmp     loc_180021D69
0x180021797  xorps   xmm0, xmm0
0x18002179a  movups  xmmword ptr [rbp+90h+var_F0.Data1], xmm0
0x18002179e  movups  [rbp+90h+var_E0], xmm0
0x1800217a2  mov     qword ptr [rbp+90h+var_F0.Data1], 0
0x1800217aa  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800217b1  movdqu  xmmword ptr [rbp+90h+var_F0.Data4], xmm1
0x1800217b6  mov     qword ptr [rbp+90h+var_E0+8], 0
0x1800217be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x1800217c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x1800217ca  test    al, al
0x1800217cc  jz      short loc_18002180A
0x1800217ce  lea     rdx, [r14+134h]; rguid
0x1800217d5  mov     r8d, 493E0h; void **
0x1800217db  lea     rcx, [rbp+90h+var_F0]; this
0x1800217df  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJAEBU_GUID@@K@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(_GUID const &,ulong)
0x1800217e4  mov     edi, eax
0x1800217e6  test    eax, eax
0x1800217e8  jns     short loc_18002180A
0x1800217ea  mov     rcx, [rbp+98h]; this
0x1800217f1  mov     r9d, eax; char *
0x1800217f4  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800217fb  mov     edx, 5ACh; void *
0x180021800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021805  jmp     loc_180021D5E
0x18002180a  lea     rbx, [r14+50h]
0x18002180e  mov     qword ptr [rsp+190h+var_128], rbx
0x180021813  lea     rsi, [rbx+8]
0x180021817  test    rbx, rbx
0x18002181a  jz      short loc_180021826
0x18002181c  mov     rcx, rsi; lpCriticalSection
0x18002181f  call    cs:__imp_EnterCriticalSection
0x180021825  nop
0x180021826  cmp     byte ptr [r14+10h], 0
0x18002182b  jz      short loc_180021834
0x18002182d  mov     edi, 80242008h
0x180021832  jmp     short loc_180021874
0x180021834  cmp     qword ptr [r14+88h], 0
0x18002183c  jnz     short loc_18002188B
0x18002183e  mov     r9, r13; struct tagDSFile **
0x180021841  mov     r8d, r12d; unsigned int
0x180021844  mov     rdx, r15; wchar_t *
0x180021847  mov     rcx, r14; this
0x18002184a  call    ?InitializeGDRRemoteDeploymentSession@COSDownloader@@AEAAJPEB_WKPEAPEAUtagDSFile@@@Z; COSDownloader::InitializeGDRRemoteDeploymentSession(wchar_t const *,ulong,tagDSFile * *)
0x18002184f  mov     edi, eax
0x180021851  xor     r13d, r13d
0x180021854  test    eax, eax
0x180021856  jns     short loc_18002188E
0x180021858  mov     rcx, [rbp+98h]; this
0x18002185f  mov     r9d, eax; char *
0x180021862  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021869  mov     edx, 5BAh; void *
0x18002186e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021873  nop
0x180021874  test    rbx, rbx
0x180021877  jz      loc_180021D5E
0x18002187d  mov     rcx, rsi; lpCriticalSection
0x180021880  call    cs:__imp_LeaveCriticalSection
0x180021886  jmp     loc_180021D5E
0x18002188b  xor     r13d, r13d
0x18002188e  test    rbx, rbx
0x180021891  jz      short loc_18002189C
0x180021893  mov     rcx, rsi; lpCriticalSection
0x180021896  call    cs:__imp_LeaveCriticalSection
0x18002189c  xorps   xmm0, xmm0
0x18002189f  movups  [rbp+90h+var_110], xmm0
0x1800218a3  mov     qword ptr [rbp+90h+var_110], r14
0x1800218a7  mov     eax, 1
0x1800218ac  mov     byte ptr [rbp+90h+var_110+8], al
0x1800218af  mov     [rbp+90h+var_50], r13
0x1800218b3  lea     rdx, [rbp+90h+var_50]; struct IDeploymentInformation **
0x1800218b7  mov     rcx, r14; this
0x1800218ba  call    ?InitializeOSDeploymentInformationForGDR@COSDownloader@@AEAAJPEAPEAUIDeploymentInformation@@@Z; COSDownloader::InitializeOSDeploymentInformationForGDR(IDeploymentInformation * *)
0x1800218bf  mov     edi, eax
0x1800218c1  test    eax, eax
0x1800218c3  jns     short loc_1800218E5
0x1800218c5  mov     rcx, [rbp+98h]; this
0x1800218cc  mov     r9d, eax; char *
0x1800218cf  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800218d6  mov     edx, 5CAh; void *
0x1800218db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800218e0  jmp     loc_180021D3B
0x1800218e5  lea     rbx, [r14+218h]
0x1800218ec  mov     qword ptr [rsp+190h+var_128], rbx
0x1800218f1  lea     rsi, [rbx+8]
0x1800218f5  test    rbx, rbx
0x1800218f8  jz      short loc_180021904
0x1800218fa  mov     rcx, rsi; lpCriticalSection
0x1800218fd  call    cs:__imp_EnterCriticalSection
0x180021903  nop
0x180021904  lea     r15, [r14+248h]
0x18002190b  mov     rcx, [r15]
0x18002190e  test    rcx, rcx
0x180021911  jz      short loc_180021922
0x180021913  mov     rax, [rcx]
0x180021916  mov     rax, [rax+10h]
0x18002191a  call    _guard_dispatch_icall
0x18002191f  mov     [r15], r13
0x180021922  mov     rcx, r15
0x180021925  call    ??$MakeAndInitialize@VCancelObject@OSDownloader@@UICancelObject@2@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICancelObject@OSDownloader@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDownloader::CancelObject,OSDownloader::ICancelObject,>(OSDownloader::ICancelObject * *)
0x18002192a  mov     edi, eax
0x18002192c  test    eax, eax
0x18002192e  jns     short loc_180021963
0x180021930  mov     rcx, [rbp+98h]; this
0x180021937  mov     r9d, eax; char *
0x18002193a  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021941  mov     edx, 5CEh; void *
0x180021946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002194b  nop
0x18002194c  test    rbx, rbx
0x18002194f  jz      loc_180021D3B
0x180021955  mov     rcx, rsi; lpCriticalSection
0x180021958  call    cs:__imp_LeaveCriticalSection
0x18002195e  jmp     loc_180021D3B
0x180021963  test    rbx, rbx
0x180021966  jz      short loc_180021971
0x180021968  mov     rcx, rsi; lpCriticalSection
0x18002196b  call    cs:__imp_LeaveCriticalSection
0x180021971  xorps   xmm0, xmm0
0x180021974  movups  [rbp+90h+var_100], xmm0
0x180021978  mov     qword ptr [rbp+90h+var_100], r14
0x18002197c  mov     esi, 1
0x180021981  mov     byte ptr [rbp+90h+var_100+8], sil
0x180021985  mov     [rsp+190h+pUnk], r13
0x18002198a  mov     rax, [r15]
0x18002198d  mov     qword ptr [rsp+190h+var_130], rax
0x180021992  mov     rax, [r14+160h]
0x180021999  mov     qword ptr [rsp+190h+var_128], rax
0x18002199e  lea     r15, [r14+134h]
0x1800219a5  lea     r12, [r14+1D8h]
0x1800219ac  lea     rdx, [r14+124h]
0x1800219b3  mov     qword ptr [rsp+190h+var_160], r12
0x1800219b8  lea     rax, [rsp+190h+var_130]
0x1800219bd  mov     [rsp+190h+var_168], rax
0x1800219c2  lea     rax, [rbp+90h+var_60]
0x1800219c6  mov     qword ptr [rsp+190h+var_170], rax; int
0x1800219cb  lea     r9, [rsp+190h+var_128]
0x1800219d0  mov     r8, r15
0x1800219d3  lea     rcx, [rsp+190h+pUnk]
0x1800219d8  call    ??$MakeAndInitialize@VCOSGDRProgress@@V1@AEAU_GUID@@AEAUtagDSGlobalUpdateId@@PEA_WAEAPEAUISusHandlerNotification@@PEAUICancelObject@OSDownloader@@AEAW4tagDownloadType@@@Details@WRL@Microsoft@@YAJPEAPEAVCOSGDRProgress@@AEAU_GUID@@AEAUtagDSGlobalUpdateId@@$$QEAPEA_WAEAPEAUISusHandlerNotification@@$$QEAPEAUICancelObject@OSDownloader@@AEAW4tagDownloadType@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COSGDRProgress,COSGDRProgress,_GUID &,tagDSGlobalUpdateId &,wchar_t *,ISusHandlerNotification * &,OSDownloader::ICancelObject *,tagDownloadType &>(COSGDRProgress * *,_GUID &,tagDSGlobalUpdateId &,wchar_t * &&,ISusHandlerNotification * &,OSDownloader::ICancelObject * &&,tagDownloadType &)
0x1800219dd  mov     edi, eax
0x1800219df  mov     rbx, [rsp+190h+pUnk]
0x1800219e4  test    eax, eax
0x1800219e6  jns     short loc_180021A08
0x1800219e8  mov     rcx, [rbp+98h]; this
0x1800219ef  mov     r9d, eax; char *
0x1800219f2  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800219f9  mov     edx, 5DDh; void *
0x1800219fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a03  jmp     loc_180021D1C
0x180021a08  mov     word ptr [r14+11h], 101h
0x180021a0f  xorps   xmm0, xmm0
0x180021a12  movups  [rsp+190h+var_128], xmm0
0x180021a17  mov     qword ptr [rsp+190h+var_128], r14
0x180021a1c  mov     byte ptr [rsp+190h+var_128+8], sil
0x180021a21  mov     [rbp+90h+var_58], r13
0x180021a25  mov     rsi, [r14+88h]
0x180021a2c  mov     rax, [rsi]
0x180021a2f  mov     rdi, [rax+18h]
0x180021a33  lea     rcx, [rbp+90h+var_58]
0x180021a37  call    ?InternalRelease@?$XPtrBase@URemoteDeploymentDownloadRequest@@URemoteDeploymentRequestPolicy@OSDeploymentRemote@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(void)
0x180021a3c  lea     r9, [rbp+90h+var_58]
0x180021a40  mov     r8, rbx
0x180021a43  mov     rdx, [rbp+90h+var_50]
0x180021a47  mov     rcx, rsi
0x180021a4a  mov     rax, rdi
0x180021a4d  call    _guard_dispatch_icall
0x180021a52  mov     esi, eax
0x180021a54  mov     edi, 1000h
0x180021a59  cmp     eax, 80010002h
0x180021a5e  jz      short loc_180021A6B
0x180021a60  cmp     eax, 800706BEh
0x180021a65  jnz     loc_180021B03
0x180021a6b  mov     rdx, r15; struct tagDSGlobalUpdateId *
0x180021a6e  lea     rcx, [rbp+90h+var_D0]; this
0x180021a72  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180021a77  mov     qword ptr [rsp+190h+var_160], rax
0x180021a7c  lea     rax, aConnectionToRe; "Connection to remote UA process failed "...
0x180021a83  mov     [rsp+190h+var_168], rax
0x180021a88  mov     [rsp+190h+var_170], esi; int
0x180021a8c  mov     r9d, 3
0x180021a92  mov     r8d, edi
0x180021a95  xor     edx, edx
0x180021a97  xor     ecx, ecx
0x180021a99  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180021a9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x180021aa5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x180021aaa  test    al, al
0x180021aac  jnz     short loc_180021B03
0x180021aae  xor     edx, edx; dwReserved
0x180021ab0  mov     rcx, rbx; pUnk
0x180021ab3  call    cs:__imp_CoDisconnectObject
0x180021ab9  mov     rcx, [rbp+98h]; this
0x180021ac0  test    eax, eax
0x180021ac2  jns     short loc_180021AD8
0x180021ac4  mov     r9d, eax; char *
0x180021ac7  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021ace  mov     edx, 601h; void *
0x180021ad3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021ad8  xor     edx, edx; dwReserved
0x180021ada  mov     rcx, [rbp+90h+var_50]; pUnk
0x180021ade  call    cs:__imp_CoDisconnectObject
0x180021ae4  mov     rcx, [rbp+98h]; this
0x180021aeb  test    eax, eax
0x180021aed  jns     short loc_180021B03
0x180021aef  mov     r9d, eax; char *
0x180021af2  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021af9  mov     edx, 602h; void *
0x180021afe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021b03  test    esi, esi
0x180021b05  jns     short loc_180021B3D
0x180021b07  mov     edi, 80242008h
0x180021b0c  cmp     esi, edi
0x180021b0e  jz      short loc_180021B36
0x180021b10  lea     eax, [rsi+7FF8FFFEh]
0x180021b16  cmp     eax, 1
0x180021b19  jbe     short loc_180021B36
0x180021b1b  mov     rcx, [rbp+98h]; this
0x180021b22  mov     r9d, esi; char *
0x180021b25  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180021b2c  mov     edx, 609h; void *
0x180021b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b36  mov     edi, esi
0x180021b38  jmp     loc_180021D0E
0x180021b3d  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180021b42  test    eax, eax
0x180021b44  jz      short loc_180021BB8
0x180021b46  xor     r9d, r9d
0x180021b49  lea     r8, aPredownloadtes; "PreDownloadTestEnabled"
0x180021b50  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021b57  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x180021b5c  mov     esi, 1
0x180021b61  test    eax, eax
0x180021b63  jz      short loc_180021BBD
0x180021b65  cmp     [r12], esi
0x180021b69  jnz     short loc_180021BBD
0x180021b6b  mov     rax, [r14+100h]
0x180021b72  mov     [rax+30h], r13d
0x180021b76  mov     rax, [r14+100h]
0x180021b7d  mov     [rax+28h], r13
0x180021b81  mov     rdx, r15; struct tagDSGlobalUpdateId *
0x180021b84  lea     rcx, [rbp+90h+var_D0]; this
0x180021b88  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180021b8d  mov     qword ptr [rsp+190h+var_160], rax
0x180021b92  lea     rax, aUupHandlerPred; "UUP handler: PreDownload finished for t"...
0x180021b99  mov     [rsp+190h+var_168], rax
0x180021b9e  mov     qword ptr [rsp+190h+var_170], r13
0x180021ba3  lea     r9d, [rsi+3]
0x180021ba7  mov     r8d, edi
0x180021baa  xor     edx, edx
0x180021bac  xor     ecx, ecx
0x180021bae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180021bb3  jmp     loc_180021D0B
0x180021bb8  mov     esi, 1
0x180021bbd  mov     [rsp+190h+var_130], r13d
0x180021bc2  mov     rcx, [rbp+90h+var_58]
0x180021bc6  lea     rax, [rsp+190h+var_130]
0x180021bcb  mov     [rsp+190h+var_140], rax; unsigned int *
0x180021bd0  mov     rax, [r14+1B0h]
0x180021bd7  mov     [rsp+190h+var_148], rax; struct ISusFileRequestList *
0x180021bdc  mov     rax, [r14+110h]
0x180021be3  mov     [rsp+190h+var_150], rax; struct ISusFileRequestList *
0x180021be8  mov     [rsp+190h+var_158], rcx; struct RemoteDeploymentDownloadRequest *
0x180021bed  mov     eax, [r14+1D4h]
0x180021bf4  mov     [rsp+190h+var_160], eax; unsigned int
0x180021bf8  mov     rax, [r14+1C0h]
0x180021bff  mov     [rsp+190h+var_168], rax; struct tagDSFile *
0x180021c04  mov     eax, [r14+1B8h]
0x180021c0b  mov     [rsp+190h+var_170], eax; unsigned int
0x180021c0f  mov     r9, [r14+1A8h]; struct tagDSFile *
0x180021c16  mov     r8d, [r14+1A0h]; unsigned int
0x180021c1d  mov     rdx, [r14+190h]; struct tagDSFile *
0x180021c24  mov     ecx, [r14+188h]; unsigned int
  ... truncated ...
```
