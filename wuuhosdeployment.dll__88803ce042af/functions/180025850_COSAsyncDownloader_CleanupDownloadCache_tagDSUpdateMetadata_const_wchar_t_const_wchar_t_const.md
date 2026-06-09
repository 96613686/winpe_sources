# COSAsyncDownloader::CleanupDownloadCache(tagDSUpdateMetadata const *,wchar_t const *,wchar_t const *)

- ea: `0x180025850`
- end: `0x180025bd0`
- name: `?CleanupDownloadCache@COSAsyncDownloader@@UEAAJPEBUtagDSUpdateMetadata@@PEB_W1@Z`
- size: `896`
- prototype: `__int64 __fastcall(COSAsyncDownloader *this, const struct tagDSUpdateMetadata *, const wchar_t *, struct tagDSFile ***)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a4f4`
- `0x180018f18`
- `0x18001952c`
- `0x180019cc4`
- `0x180019e00`
- `0x18001a8b8`
- `0x18001d604`
- `0x180025850`
- `0x180042630`
- `0x180042a24`
- `0x180049260`
- `0x1800492e0`

## string_xrefs

- `0x1800258a8`: `CleanupDownloadCache - cleanup UUP update %ws with the session data %ws in the sandbox %ws.`
- `0x180025ac9`: `CleanupDownloadCache: CDeploymentSessionWrapper Initialize failed.`

## pseudocode

```c
__int64 __fastcall COSAsyncDownloader::CleanupDownloadCache(
        COSAsyncDownloader *this,
        const struct tagDSUpdateMetadata *a2,
        const wchar_t *a3,
        struct tagDSFile ***a4)
{
  const struct tagDSGlobalUpdateId *v6; // rsi
  int FilesPerPatchType; // eax
  wchar_t **v8; // r8
  int v9; // edi
  const struct std::nothrow_t *v10; // rdx
  int v11; // eax
  void *v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+38h] [rbp-C8h]
  void *lpMem; // [rsp+50h] [rbp-B0h] BYREF
  struct tagDSFile *v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  void *v25; // [rsp+68h] [rbp-98h] BYREF
  void *v26; // [rsp+70h] [rbp-90h] BYREF
  void *v27; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[112]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v32; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v33[14]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v34; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v32 = a3;
  v6 = (const struct tagDSUpdateMetadata *)((char *)a2 + 4);
  Trace::UpdateIdToString::UpdateIdToString(
    (Trace::UpdateIdToString *)v31,
    (const struct tagDSUpdateMetadata *)((char *)a2 + 4));
  WUTrace(0, 0, 4096, 4);
  v24 = 0;
  LODWORD(v23) = 0;
  v25 = 0;
  LODWORD(lpMem) = 0;
  v26 = 0;
  FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                        (OSDeploymentHelper *)*((unsigned int *)a2 + 116),
                        *((_QWORD *)a2 + 59),
                        (struct tagDSFile *const)&v24,
                        &v23,
                        (unsigned int *)&v25,
                        (struct tagDSFile ***)&lpMem,
                        (unsigned int *)&v26,
                        a4);
  v9 = FilesPerPatchType;
  if ( FilesPerPatchType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)(unsigned int)FilesPerPatchType,
      v19);
    goto LABEL_25;
  }
  lpMem = 0;
  v11 = OSDeploymentHelper::ParseHandlerXml(
          (const struct tagDSUpdateMetadata *)((char *)a2 + 544),
          (const struct tagDSDataBlob *)&lpMem,
          v8);
  v9 = v11;
  v12 = lpMem;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)(unsigned int)v11,
      v19);
    goto LABEL_23;
  }
  memset(v28, 0, sizeof(v28));
  v29 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl)
    || (v13 = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire((struct _GUID *)v28, (GUID *)v6, (void **)0x493E0),
        v9 = v13,
        v13 >= 0) )
  {
    v34 = 0;
    memset(&v33[2], 0, 0x58u);
    v33[1] = Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v31, v6);
    v33[0] = a4;
    lpMem = v33;
    v30 = xmmword_1800766B8;
    v27 = v12;
    v14 = v24;
    if ( v24 )
      v14 = *(_QWORD *)(v24 + 72);
    v24 = v14;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v9 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t const * &,wchar_t * const,wchar_t *,unsigned long &,WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>> &,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
           (unsigned int)&v34,
           (unsigned int)&v32,
           (unsigned int)&v24,
           (unsigned int)&v27,
           (__int64)&v23,
           (__int64)&v25,
           (__int64)&v30,
           v21,
           (__int64)&lpMem);
    if ( (unsigned int)(v9 + 2147024894) <= 1 )
    {
      WUTrace(0, 0, 4096, 4);
    }
    else
    {
      if ( v9 < 0 )
      {
        v20 = v9;
        WUTrace(0, 0, 4096, 3);
        v15 = (unsigned int)v9;
        v16 = 652;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
          (const char *)v15,
          v20);
        goto LABEL_20;
      }
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 56LL))(v34);
      v9 = v17;
      if ( v17 < 0 )
      {
        v15 = (unsigned int)v17;
        v16 = 655;
        goto LABEL_17;
      }
    }
    v9 = 0;
LABEL_20:
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x268,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
    (const char *)(unsigned int)v13,
    v19);
LABEL_22:
  OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)v28);
LABEL_23:
  if ( v12 )
    CSusBaseAllocTag<942762101>::operator delete(v12);
LABEL_25:
  if ( v26 )
    operator delete(v26, v10);
  if ( v25 )
    operator delete(v25, v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025850  mov     [rsp-8+arg_0], rbx
0x180025855  push    rbp
0x180025856  push    rsi
0x180025857  push    rdi
0x180025858  push    r14
0x18002585a  push    r15
0x18002585c  lea     rbp, [rsp-0B0h]
0x180025864  sub     rsp, 1B0h
0x18002586b  mov     rax, cs:__security_cookie
0x180025872  xor     rax, rsp
0x180025875  mov     [rbp+0D0h+var_28], rax
0x18002587c  mov     r15, r9
0x18002587f  mov     rbx, r8
0x180025882  mov     r14, rdx
0x180025885  mov     [rbp+0D0h+var_B0], rbx
0x180025889  lea     rsi, [rdx+4]
0x18002588d  mov     rdx, rsi; struct tagDSGlobalUpdateId *
0x180025890  lea     rcx, [rbp+0D0h+var_120]; this
0x180025894  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180025899  mov     [rsp+1D0h+var_190], rbx
0x18002589e  mov     [rsp+1D0h+var_198], r15; struct tagDSFile ***
0x1800258a3  mov     [rsp+1D0h+var_1A0], rax
0x1800258a8  lea     rax, aCleanupdownloa; "CleanupDownloadCache - cleanup UUP upda"...
0x1800258af  mov     [rsp+1D0h+var_1A8], rax
0x1800258b4  mov     [rsp+1D0h+var_1B0], 0
0x1800258bd  xor     edx, edx
0x1800258bf  xor     ecx, ecx
0x1800258c1  lea     r9d, [rdx+4]
0x1800258c5  mov     r8d, 1000h
0x1800258cb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800258d0  mov     [rsp+1D0h+var_170], 0
0x1800258d9  mov     dword ptr [rsp+1D0h+var_178], 0
0x1800258e1  mov     [rsp+1D0h+var_168], 0
0x1800258ea  mov     dword ptr [rsp+1D0h+lpMem], 0
0x1800258f2  mov     [rsp+1D0h+var_160], 0
0x1800258fb  lea     rax, [rsp+1D0h+var_160]
0x180025900  mov     [rsp+1D0h+var_1A0], rax; unsigned int *
0x180025905  lea     rax, [rsp+1D0h+lpMem]
0x18002590a  mov     [rsp+1D0h+var_1A8], rax; struct tagDSFile ***
0x18002590f  lea     rax, [rsp+1D0h+var_168]
0x180025914  mov     [rsp+1D0h+var_1B0], rax; int
0x180025919  lea     r9, [rsp+1D0h+var_178]; struct tagDSFile **
0x18002591e  lea     r8, [rsp+1D0h+var_170]; struct tagDSFile *
0x180025923  mov     rdx, [r14+1D8h]; unsigned int
0x18002592a  mov     ecx, [r14+1D0h]; this
0x180025931  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x180025936  mov     edi, eax
0x180025938  test    eax, eax
0x18002593a  jns     short loc_18002595C
0x18002593c  mov     rcx, [rbp+0D8h]; this
0x180025943  mov     r9d, eax; char *
0x180025946  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002594d  mov     edx, 25Fh; void *
0x180025952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025957  jmp     loc_180025B8A
0x18002595c  mov     [rsp+1D0h+lpMem], 0
0x180025965  lea     rcx, [r14+220h]; this
0x18002596c  lea     rdx, [rsp+1D0h+lpMem]; struct tagDSDataBlob *
0x180025971  call    ?ParseHandlerXml@OSDeploymentHelper@@YAJAEBUtagDSDataBlob@@PEAPEA_W@Z; OSDeploymentHelper::ParseHandlerXml(tagDSDataBlob const &,wchar_t * *)
0x180025976  mov     edi, eax
0x180025978  mov     rbx, [rsp+1D0h+lpMem]
0x18002597d  test    eax, eax
0x18002597f  jns     short loc_1800259A1
0x180025981  mov     rcx, [rbp+0D8h]; this
0x180025988  mov     r9d, eax; char *
0x18002598b  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180025992  mov     edx, 262h; void *
0x180025997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002599c  jmp     loc_180025B7D
0x1800259a1  mov     qword ptr [rbp+0D0h+var_150], 0
0x1800259a9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800259b0  movdqu  xmmword ptr [rbp+0D0h+var_150+8], xmm0
0x1800259b5  mov     [rbp+0D0h+var_138], 0
0x1800259bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x1800259c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x1800259c9  test    al, al
0x1800259cb  jz      short loc_180025A05
0x1800259cd  mov     r8d, 493E0h; void **
0x1800259d3  mov     rdx, rsi; rguid
0x1800259d6  lea     rcx, [rbp+0D0h+var_150]; this
0x1800259da  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJAEBU_GUID@@K@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(_GUID const &,ulong)
0x1800259df  mov     edi, eax
0x1800259e1  test    eax, eax
0x1800259e3  jns     short loc_180025A05
0x1800259e5  mov     rcx, [rbp+0D8h]; this
0x1800259ec  mov     r9d, eax; char *
0x1800259ef  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800259f6  mov     edx, 268h; void *
0x1800259fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025a00  jmp     loc_180025B74
0x180025a05  mov     [rbp+0D0h+var_30], 0
0x180025a10  xor     edx, edx; Val
0x180025a12  lea     r8d, [rdx+58h]; Size
0x180025a16  lea     rcx, [rbp+0D0h+var_90]; void *
0x180025a1a  call    memset
0x180025a1f  mov     rdx, rsi; struct tagDSGlobalUpdateId *
0x180025a22  lea     rcx, [rbp+0D0h+var_120]; this
0x180025a26  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180025a2b  mov     [rbp+0D0h+var_98], rax
0x180025a2f  mov     [rbp+0D0h+var_A0], r15
0x180025a33  lea     rax, [rbp+0D0h+var_A0]
0x180025a37  mov     [rsp+1D0h+lpMem], rax
0x180025a3c  movups  xmm0, cs:xmmword_1800766B8
0x180025a43  movdqu  [rbp+0D0h+var_130], xmm0
0x180025a48  mov     [rsp+1D0h+var_158], rbx
0x180025a4d  mov     rax, [rsp+1D0h+var_170]
0x180025a52  test    rax, rax
0x180025a55  jz      short loc_180025A5B
0x180025a57  mov     rax, [rax+48h]
0x180025a5b  mov     [rsp+1D0h+var_170], rax
0x180025a60  mov     rcx, [rbp+0D0h+var_30]
0x180025a67  test    rcx, rcx
0x180025a6a  jz      short loc_180025A78
0x180025a6c  mov     rax, [rcx]
0x180025a6f  mov     rax, [rax+10h]
0x180025a73  call    _guard_dispatch_icall
0x180025a78  lea     rax, [rsp+1D0h+lpMem]
0x180025a7d  mov     [rsp+1D0h+var_190], rax
0x180025a82  lea     rax, [rbp+0D0h+var_130]
0x180025a86  mov     [rsp+1D0h+var_1A0], rax
0x180025a8b  lea     rax, [rsp+1D0h+var_168]
0x180025a90  mov     [rsp+1D0h+var_1A8], rax
0x180025a95  lea     rax, [rsp+1D0h+var_178]
0x180025a9a  mov     [rsp+1D0h+var_1B0], rax; int
0x180025a9f  lea     r9, [rsp+1D0h+var_158]
0x180025aa4  lea     r8, [rsp+1D0h+var_170]
0x180025aa9  lea     rdx, [rbp+0D0h+var_B0]
0x180025aad  lea     rcx, [rbp+0D0h+var_30]
0x180025ab4  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@UIDeploymentSession@@AEAPEB_WQEA_WPEA_WAEAKAEAV?$XPtrBaseWithArrayAllocation@PEAUtagDSFile@@U?$STArrayZeroAllocPolicy@PEAUtagDSFile@@@Policies@WuSmartPtr@@@WuSmartPtr@@U_GUID@@AEBKPEAUtagOptionalSessionInfo5@@@Details@WRL@Microsoft@@YAJPEAPEAUIDeploymentSession@@AEAPEB_W$$QEBQEA_W$$QEAPEA_WAEAKAEAV?$XPtrBaseWithArrayAllocation@PEAUtagDSFile@@U?$STArrayZeroAllocPolicy@PEAUtagDSFile@@@Policies@WuSmartPtr@@@WuSmartPtr@@$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo5@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t const * &,wchar_t * const,wchar_t *,ulong &,WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>> &,_GUID,ulong const &,tagOptionalSessionInfo5 *>(IDeploymentSession * *,wchar_t const * &,wchar_t * const &&,wchar_t * &&,ulong &,WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>> &,_GUID &&,ulong const &,tagOptionalSessionInfo5 * &&)
0x180025ab9  mov     edi, eax
0x180025abb  add     eax, 7FF8FFFEh
0x180025ac0  cmp     eax, 1
0x180025ac3  jbe     short loc_180025B2C
0x180025ac5  test    edi, edi
0x180025ac7  jns     short loc_180025AF6
0x180025ac9  lea     rax, aCleanupdownloa_0; "CleanupDownloadCache: CDeploymentSessio"...
0x180025ad0  mov     [rsp+1D0h+var_1A8], rax
0x180025ad5  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180025ad9  xor     edx, edx
0x180025adb  xor     ecx, ecx
0x180025add  lea     r9d, [rdx+3]
0x180025ae1  mov     r8d, 1000h
0x180025ae7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180025aec  mov     r9d, edi
0x180025aef  mov     edx, 28Ch
0x180025af4  jmp     short loc_180025B17
0x180025af6  mov     rcx, [rbp+0D0h+var_30]
0x180025afd  mov     rax, [rcx]
0x180025b00  mov     rax, [rax+38h]
0x180025b04  call    _guard_dispatch_icall
0x180025b09  mov     edi, eax
0x180025b0b  test    eax, eax
0x180025b0d  jns     short loc_180025B4F
0x180025b0f  mov     r9d, eax; char *
0x180025b12  mov     edx, 28Fh; void *
0x180025b17  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180025b1e  mov     rcx, [rbp+0D8h]; this
0x180025b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b2a  jmp     short loc_180025B51
0x180025b2c  lea     rax, aCdeploymentses; "CDeploymentSessionWrapper Initialize fa"...
0x180025b33  mov     [rsp+1D0h+var_1A8], rax
0x180025b38  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180025b3c  xor     edx, edx
0x180025b3e  xor     ecx, ecx
0x180025b40  lea     r9d, [rdx+4]
0x180025b44  mov     r8d, 1000h
0x180025b4a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180025b4f  xor     edi, edi
0x180025b51  mov     rcx, [rbp+0D0h+var_30]
0x180025b58  test    rcx, rcx
0x180025b5b  jz      short loc_180025B74
0x180025b5d  mov     rax, [rcx]
0x180025b60  mov     rax, [rax+10h]
0x180025b64  call    _guard_dispatch_icall
0x180025b69  mov     [rbp+0D0h+var_30], 0
0x180025b74  lea     rcx, [rbp+0D0h+var_150]; this
0x180025b78  call    ??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ; OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)
0x180025b7d  test    rbx, rbx
0x180025b80  jz      short loc_180025B8A
0x180025b82  mov     rcx, rbx; lpMem
0x180025b85  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180025b8a  mov     rcx, [rsp+1D0h+var_160]; void *
0x180025b8f  test    rcx, rcx
0x180025b92  jz      short loc_180025B99
0x180025b94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025b99  mov     rcx, [rsp+1D0h+var_168]; void *
0x180025b9e  test    rcx, rcx
0x180025ba1  jz      short loc_180025BA8
0x180025ba3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025ba8  mov     eax, edi
0x180025baa  mov     rcx, [rbp+0D0h+var_28]
0x180025bb1  xor     rcx, rsp; StackCookie
0x180025bb4  call    __security_check_cookie
0x180025bb9  mov     rbx, [rsp+1D0h+arg_0]
0x180025bc1  add     rsp, 1B0h
0x180025bc8  pop     r15
0x180025bca  pop     r14
0x180025bcc  pop     rdi
0x180025bcd  pop     rsi
0x180025bce  pop     rbp
0x180025bcf  retn
```
