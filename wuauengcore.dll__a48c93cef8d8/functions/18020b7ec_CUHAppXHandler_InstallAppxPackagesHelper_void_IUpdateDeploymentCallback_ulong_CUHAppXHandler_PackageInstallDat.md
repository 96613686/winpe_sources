# CUHAppXHandler::InstallAppxPackagesHelper(void *,IUpdateDeploymentCallback *,ulong,CUHAppXHandler::PackageInstallData const * const *,ulong,unsigned __int64,tagUpdateDeploymentNotifyData *)

- ea: `0x18020b7ec`
- end: `0x18020bea1`
- name: `?InstallAppxPackagesHelper@CUHAppXHandler@@AEAAJPEAXPEAUIUpdateDeploymentCallback@@KPEBQEBVPackageInstallData@1@K_KPEAUtagUpdateDeploymentNotifyData@@@Z`
- size: `1717`
- prototype: `__int64 __fastcall(CUHAppXHandler *__hidden this, void *, struct IUpdateDeploymentCallback *, unsigned int, const struct CUHAppXHandler::PackageInstallData *const *, unsigned int, unsigned __int64, struct tagUpdateDeploymentNotifyData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18020bea8`

## callees

- `0x18007b8a4`
- `0x180110914`
- `0x18012b618`
- `0x1801aaab4`
- `0x180204190`
- `0x18020ad4c`
- `0x18020b7ec`
- `0x18020f7ac`
- `0x1802110f8`
- `0x1802116f4`
- `0x180211978`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18020bc21`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18020bc21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020bd5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020bd5f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18020bc5f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18020bc5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020b9e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18020b9e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020bcd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020bcd0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18020b9ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18020b9ff`

## string_xrefs

- `0x18020b9db`: `Windows.Foundation.Handles.Internal.TokenHandle`
- `0x18020b91f`: `Failed to create deployment operation`
- `0x18020bc29`: `AppX Install: Begin Wait`
- `0x18020bd96`: `AppX Install: Event Fired: TimeOut`
- `0x18020bb64`: `AppX Install: Event Fired: Cancel`
- `0x18020b894`: `Cannot install legacy XAP without applicability data.`
- `0x18020bc6f`: `AppX Install: Event Fired: Cancel+Disconnect`
- `0x18020bdc3`: `AppX Install: Event Fired: Complete`
- `0x18020bd7d`: `AppX Install: Wait Failed`
- `0x18020bd32`: `AppX Install: Wait Unexpected: Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CUHAppXHandler::InstallAppxPackagesHelper(
        CUHAppXHandler *this,
        void *a2,
        struct IUpdateDeploymentCallback *a3,
        unsigned int a4,
        const struct CUHAppXHandler::PackageInstallData **a5,
        unsigned int a6,
        unsigned __int64 a7,
        struct tagUpdateDeploymentNotifyData *a8)
{
  __int64 v8; // r13
  __int64 v10; // rax
  signed int PackageFamilyNamesFromPackageData; // ebx
  CAppxDeploymentOperation *v12; // rdi
  const wchar_t *v13; // rax
  const struct CUHAppXHandler::PackageInstallData *v14; // rsi
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  __int64 v18; // rax
  DWORD v19; // r15d
  void *v20; // rcx
  const struct CUHAppXHandler::PackageInstallData *const *v21; // r15
  struct IUpdateDeploymentCallback *v22; // rdi
  const struct CUHAppXHandler::PackageInstallData *v23; // rax
  DWORD v24; // eax
  __int64 v25; // rcx
  signed int LastError; // eax
  char IsEnabled; // al
  int v29; // ecx
  int v30; // eax
  bool v31; // zf
  struct CAppxDeploymentOperation **v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-B8h]
  CAppxDeploymentOperation *v35; // [rsp+50h] [rbp-B0h] BYREF
  CUHAppXHandler *v36; // [rsp+58h] [rbp-A8h]
  struct IUpdateDeploymentCallback *v37; // [rsp+60h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v41; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v42; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v43[56]; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handles[2]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v45; // [rsp+1A0h] [rbp+A0h]

  v8 = a4;
  v34 = a4;
  v37 = a3;
  v36 = this;
  v35 = 0;
  *(_OWORD *)Handles = 0;
  v45 = 0;
  v33 = 0;
  v42 = 0;
  if ( a4 != 1 || (v10 = *((_QWORD *)*a5 + 3), *(_DWORD *)v10 != 3) || *(_QWORD *)(v10 + 8) )
  {
    PackageFamilyNamesFromPackageData = CUHAppXHandler::GetPackageFamilyNamesFromPackageData(a5, a4, &v33);
    if ( PackageFamilyNamesFromPackageData < 0 )
    {
      WUTrace(0, 0, 4096, 1, PackageFamilyNamesFromPackageData, L"GetPackageFamilyNamesFromPackageData");
      goto LABEL_46;
    }
LABEL_7:
    memset(a8, 0, 0xD8u);
    *(_DWORD *)a8 = 2;
    PackageFamilyNamesFromPackageData = CAppxDeploymentOperation::CreateInstance(0, 0, 0, 0, 0, 0, &v35);
    v12 = v35;
    if ( PackageFamilyNamesFromPackageData >= 0 )
    {
      v14 = *a5;
      if ( a7 )
      {
        PackageFamilyNamesFromPackageData = CAppxDeploymentOperation::RegisterPackagesAsync(
                                              (_DWORD)v35,
                                              v33,
                                              (_DWORD)v42,
                                              (int)v14 + 48,
                                              a6,
                                              a7,
                                              0);
      }
      else
      {
        v41 = 0;
        string = 0;
        v15 = WindowsCreateStringReference(
                L"Windows.Foundation.Handles.Internal.TokenHandle",
                0x2Fu,
                &hstringHeader,
                &string);
        if ( v15 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
          JUMPOUT(0x18020BEA0LL);
        }
        PackageFamilyNamesFromPackageData = RoGetActivationFactory(
                                              string,
                                              &GUID_9ca65f02_bdc8_47ab_a06b_61bd5b619bdb,
                                              &v41);
        if ( PackageFamilyNamesFromPackageData < 0 )
        {
          if ( v41 )
            (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
          goto LABEL_44;
        }
        v40 = 0;
        v18 = *v41;
        v40 = 0;
        PackageFamilyNamesFromPackageData = (*(__int64 (__fastcall **)(__int64 *, void *, GUID *, __int64 *))(v18 + 56))(
                                              v41,
                                              a2,
                                              &GUID_28f61b65_979a_4ebc_882a_6006ebcbd52e,
                                              &v40);
        if ( PackageFamilyNamesFromPackageData < 0 )
        {
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          if ( v41 )
            (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
          goto LABEL_44;
        }
        PackageFamilyNamesFromPackageData = CAppxDeploymentOperation::RegisterPackagesAsync(
                                              (_DWORD)v12,
                                              v33,
                                              (_DWORD)v42,
                                              (int)v14 + 48,
                                              a6,
                                              0,
                                              v40);
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        if ( v41 )
          (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
      }
      if ( PackageFamilyNamesFromPackageData >= 0 )
      {
        Handles[0] = *((HANDLE *)v36 + 25);
        Handles[1] = *((HANDLE *)v12 + 5);
        *(_QWORD *)&v45 = *((_QWORD *)v12 + 6);
        *((_QWORD *)&v45 + 1) = *((_QWORD *)v36 + 24);
        v19 = 4;
        LODWORD(v40) = 4;
        while ( 1 )
        {
          WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Begin Wait");
          v24 = WaitForMultipleObjects(v19, Handles, 0, 0xFFFFFFFF);
          if ( !v24 )
          {
            WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Event Fired: Cancel+Disconnect");
            CAppxDeploymentOperation::Cancel(v12);
            *((_DWORD *)a8 + 2) = 2;
            *((_DWORD *)a8 + 9) = -2145116152;
            *((_DWORD *)a8 + 8) = 0;
            goto LABEL_44;
          }
          if ( v24 == 1 )
            break;
          if ( v24 == 2 )
          {
            memset(&v43[1], 0, 0xD4u);
            v43[0] = 1;
            v43[6] = *((_DWORD *)v12 + 38);
            v43[7] = 100;
            if ( (_DWORD)v8 )
            {
              v21 = a5;
              v22 = v37;
              do
              {
                v23 = *v21;
                *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)*v21;
                *(_DWORD *)&hstringHeader.Reserved.Reserved2[16] = *((_DWORD *)v23 + 4);
                (*(void (__fastcall **)(struct IUpdateDeploymentCallback *, HSTRING_HEADER *, _DWORD *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                  v22,
                  &hstringHeader,
                  v43,
                  0);
                ++v21;
                --v8;
              }
              while ( v8 );
              v12 = v35;
              v8 = v34;
              v19 = v40;
            }
            v20 = (void *)*((_QWORD *)v12 + 6);
          }
          else
          {
            if ( v24 != 3 )
            {
              if ( v24 == 258 )
              {
                WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Event Fired: TimeOut");
                PackageFamilyNamesFromPackageData = -2145124319;
              }
              else if ( v24 == -1 )
              {
                LastError = GetLastError();
                PackageFamilyNamesFromPackageData = (unsigned __int16)LastError | 0x80070000;
                if ( LastError <= 0 )
                  PackageFamilyNamesFromPackageData = LastError;
                if ( PackageFamilyNamesFromPackageData >= 0 )
                  PackageFamilyNamesFromPackageData = -2147418113;
                WUTrace(0, 0, 4096, 5, PackageFamilyNamesFromPackageData, L"AppX Install: Wait Failed");
              }
              else
              {
                LODWORD(v32) = v24;
                WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Wait Unexpected: Error %d", v32);
                PackageFamilyNamesFromPackageData = -2145112065;
              }
              goto LABEL_44;
            }
            WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Event Fired: Cancel");
            CAppxDeploymentOperation::Cancel(v12);
            LODWORD(v40) = --v19;
            v20 = (void *)*((_QWORD *)v36 + 24);
          }
          ResetEvent(v20);
        }
        WUTrace(0, 0, 4096, 5, 0, L"AppX Install: Event Fired: Complete");
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ReportExtendedHResultFromAppX_56053304>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ReportExtendedHResultFromAppX_56053304>::GetImpl'::`2'::impl);
        v29 = *((_DWORD *)v12 + 34);
        if ( IsEnabled )
        {
          *((_DWORD *)a8 + 9) = v29;
          *((_DWORD *)a8 + 10) = *((_DWORD *)v12 + 35);
        }
        else
        {
          if ( v29 < 0 )
          {
            v30 = *((_DWORD *)v12 + 35);
            if ( v30 < 0 && v30 != -2147467260 )
              v29 = *((_DWORD *)v12 + 35);
          }
          *((_DWORD *)a8 + 9) = v29;
        }
        if ( v29 >= 0 )
        {
          *((_DWORD *)a8 + 2) = 1;
        }
        else
        {
          *((_DWORD *)a8 + 2) = 0;
          *((_DWORD *)a8 + 8) = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ReportExtendedHResultFromAppX_56053304>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ReportExtendedHResultFromAppX_56053304>::GetImpl'::`2'::impl) )
          {
            if ( *((int *)a8 + 10) >= 0 )
              goto LABEL_44;
            v31 = *((_WORD *)a8 + 20) == 32;
          }
          else
          {
            if ( *((int *)a8 + 9) >= 0 )
              goto LABEL_44;
            v31 = *((_WORD *)a8 + 18) == 32;
          }
          if ( v31 )
            DuplicateString<wchar_t const *,wchar_t *>(*((_QWORD *)v12 + 18), (char *)a8 + 128);
        }
        goto LABEL_44;
      }
      v13 = L"RegisterPackagesAsync";
    }
    else
    {
      v13 = L"Failed to create deployment operation";
    }
    WUTrace(0, 0, 4096, 1, PackageFamilyNamesFromPackageData, v13);
LABEL_44:
    if ( v12 )
    {
      CAppxDeploymentOperation::UnbindFromDeploymentRequest(v12);
      (*(void (__fastcall **)(CAppxDeploymentOperation *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_46;
  }
  v41 = *(__int64 **)(v10 + 48);
  if ( !v41 )
  {
    WUTrace(0, 0, 4096, 1, 0, L"Cannot install legacy XAP without applicability data.");
    PackageFamilyNamesFromPackageData = -2147024809;
    goto LABEL_46;
  }
  PackageFamilyNamesFromPackageData = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&v42);
  if ( PackageFamilyNamesFromPackageData >= 0 )
    goto LABEL_7;
LABEL_46:
  WindowsDeleteString(v42);
  v42 = 0;
  v25 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return (unsigned int)PackageFamilyNamesFromPackageData;
}

```

## disassembly

```asm
0x18020b7ec  mov     [rsp-8+arg_18], rbx
0x18020b7f1  push    rbp
0x18020b7f2  push    rsi
0x18020b7f3  push    rdi
0x18020b7f4  push    r12
0x18020b7f6  push    r13
0x18020b7f8  push    r14
0x18020b7fa  push    r15
0x18020b7fc  lea     rbp, [rsp-0C0h]
0x18020b804  sub     rsp, 1C0h
0x18020b80b  mov     rax, cs:__security_cookie
0x18020b812  xor     rax, rsp
0x18020b815  mov     [rbp+0F0h+var_40], rax
0x18020b81c  mov     r13d, r9d
0x18020b81f  mov     [rsp+1F0h+var_1A8], r13d
0x18020b824  mov     [rsp+1F0h+var_190], r8
0x18020b829  mov     r15, rdx
0x18020b82c  mov     [rsp+1F0h+var_198], rcx
0x18020b831  mov     r14, [rbp+0F0h+arg_38]
0x18020b838  mov     r12, [rbp+0F0h+arg_20]
0x18020b83f  xor     edi, edi
0x18020b841  mov     [rsp+1F0h+var_1A0], rdi
0x18020b846  xorps   xmm0, xmm0
0x18020b849  movups  xmmword ptr [rbp+0F0h+Handles], xmm0
0x18020b850  movups  [rbp+0F0h+var_50], xmm0
0x18020b857  mov     [rsp+1F0h+var_1B0], rdi
0x18020b85c  mov     [rbp+0F0h+var_150], rdi
0x18020b860  lea     esi, [rdi+1]
0x18020b863  cmp     r9d, esi
0x18020b866  jnz     loc_18020B944
0x18020b86c  mov     rax, [r12]
0x18020b870  mov     rax, [rax+18h]
0x18020b874  cmp     dword ptr [rax], 3
0x18020b877  jnz     loc_18020B944
0x18020b87d  cmp     [rax+8], rdi
0x18020b881  jnz     loc_18020B944
0x18020b887  mov     rax, [rax+30h]
0x18020b88b  mov     [rbp+0F0h+var_158], rax
0x18020b88f  test    rax, rax
0x18020b892  jnz     short loc_18020B8C1
0x18020b894  lea     rax, aCannotInstallL; "Cannot install legacy XAP without appli"...
0x18020b89b  mov     [rsp+1F0h+var_1C8], rax
0x18020b8a0  mov     [rsp+1F0h+var_1D0], rdi
0x18020b8a5  mov     r9d, esi
0x18020b8a8  xor     edx, edx
0x18020b8aa  xor     ecx, ecx
0x18020b8ac  mov     r8d, 1000h
0x18020b8b2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020b8b7  mov     ebx, 80070057h
0x18020b8bc  jmp     loc_18020BCCC
0x18020b8c1  lea     rdx, [rbp+0F0h+var_158]
0x18020b8c5  lea     rcx, [rbp+0F0h+var_150]; string
0x18020b8c9  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18020b8ce  mov     ebx, eax
0x18020b8d0  test    eax, eax
0x18020b8d2  js      loc_18020BCCC
0x18020b8d8  xor     edx, edx; Val
0x18020b8da  mov     r8d, 0D8h; Size
0x18020b8e0  mov     rcx, r14; void *
0x18020b8e3  call    memset
0x18020b8e8  mov     dword ptr [r14], 2
0x18020b8ef  lea     rax, [rsp+1F0h+var_1A0]
0x18020b8f4  mov     [rsp+1F0h+var_1C0], rax; struct CAppxDeploymentOperation **
0x18020b8f9  mov     [rsp+1F0h+var_1C8], rdi; wchar_t *
0x18020b8fe  mov     [rsp+1F0h+var_1D0], rdi; struct tagDSGlobalUpdateId *
0x18020b903  xor     r9d, r9d; struct _GUID *
0x18020b906  xor     r8d, r8d; struct ISusHandlerNotification *
0x18020b909  xor     edx, edx; void *
0x18020b90b  xor     ecx, ecx; bool
0x18020b90d  call    ?CreateInstance@CAppxDeploymentOperation@@SAJ_NPEAXPEAUISusHandlerNotification@@PEBU_GUID@@PEBUtagDSGlobalUpdateId@@PEB_WPEAPEAV1@@Z; CAppxDeploymentOperation::CreateInstance(bool,void *,ISusHandlerNotification *,_GUID const *,tagDSGlobalUpdateId const *,wchar_t const *,CAppxDeploymentOperation * *)
0x18020b912  mov     ebx, eax
0x18020b914  mov     rdi, [rsp+1F0h+var_1A0]
0x18020b919  xor     ecx, ecx
0x18020b91b  test    eax, eax
0x18020b91d  jns     short loc_18020B985
0x18020b91f  lea     rax, aFailedToCreate_0; "Failed to create deployment operation"
0x18020b926  mov     r9d, esi
0x18020b929  xor     edx, edx
0x18020b92b  mov     r8d, 1000h
0x18020b931  mov     [rsp+1F0h+var_1C8], rax
0x18020b936  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x18020b93a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020b93f  jmp     loc_18020BCAE
0x18020b944  lea     r8, [rsp+1F0h+var_1B0]
0x18020b949  mov     edx, r13d
0x18020b94c  mov     rcx, r12
0x18020b94f  call    ?GetPackageFamilyNamesFromPackageData@CUHAppXHandler@@CAJPEBQEBVPackageInstallData@1@KPEAPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@ABI@@@Z; CUHAppXHandler::GetPackageFamilyNamesFromPackageData(CUHAppXHandler::PackageInstallData const * const *,ulong,ABI::Windows::Foundation::Collections::IIterable<HSTRING__ *> * *)
0x18020b954  mov     ebx, eax
0x18020b956  test    eax, eax
0x18020b958  jns     loc_18020B8D8
0x18020b95e  lea     rax, aGetpackagefami; "GetPackageFamilyNamesFromPackageData"
0x18020b965  mov     [rsp+1F0h+var_1C8], rax
0x18020b96a  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x18020b96e  mov     r9d, esi
0x18020b971  xor     edx, edx
0x18020b973  xor     ecx, ecx
0x18020b975  mov     r8d, 1000h
0x18020b97b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020b980  jmp     loc_18020BCCC
0x18020b985  mov     rsi, [r12]
0x18020b989  mov     rax, [rbp+0F0h+arg_30]
0x18020b990  test    rax, rax
0x18020b993  jz      short loc_18020B9C5
0x18020b995  mov     [rsp+1F0h+var_1C0], rcx
0x18020b99a  mov     [rsp+1F0h+var_1C8], rax
0x18020b99f  mov     eax, [rbp+0F0h+arg_28]
0x18020b9a5  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18020b9a9  lea     r9, [rsi+30h]
0x18020b9ad  mov     r8, [rbp+0F0h+var_150]
0x18020b9b1  mov     rdx, [rsp+1F0h+var_1B0]
0x18020b9b6  mov     rcx, rdi
0x18020b9b9  call    ?RegisterPackagesAsync@CAppxDeploymentOperation@@QEAAJPEBU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@ABI@@QEAUHSTRING__@@PEBDK_KPEAUITokenHandle@Internal@Handles@456@@Z; CAppxDeploymentOperation::RegisterPackagesAsync(ABI::Windows::Foundation::Collections::IIterable<HSTRING__ *> const *,HSTRING__ * const,char const *,ulong,unsigned __int64,ABI::Windows::Foundation::Handles::Internal::ITokenHandle *)
0x18020b9be  mov     ebx, eax
0x18020b9c0  jmp     loc_18020BAEA
0x18020b9c5  mov     [rbp+0F0h+var_158], rcx
0x18020b9c9  mov     [rbp+0F0h+string], rcx
0x18020b9cd  lea     r9, [rbp+0F0h+string]; string
0x18020b9d1  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x18020b9d6  mov     edx, 2Fh ; '/'; length
0x18020b9db  lea     rcx, ?RuntimeClass_Windows_Foundation_Handles_Internal_TokenHandle@@3QB_WB; "Windows.Foundation.Handles.Internal.Tok"...
0x18020b9e2  call    cs:__imp_WindowsCreateStringReference
0x18020b9e8  test    eax, eax
0x18020b9ea  js      loc_18020BE99
0x18020b9f0  lea     r8, [rbp+0F0h+var_158]
0x18020b9f4  lea     rdx, _GUID_9ca65f02_bdc8_47ab_a06b_61bd5b619bdb
0x18020b9fb  mov     rcx, [rbp+0F0h+string]
0x18020b9ff  call    cs:__imp_RoGetActivationFactory
0x18020ba05  mov     ebx, eax
0x18020ba07  test    eax, eax
0x18020ba09  jns     short loc_18020BA26
0x18020ba0b  mov     rcx, [rbp+0F0h+var_158]
0x18020ba0f  test    rcx, rcx
0x18020ba12  jz      short loc_18020BA21
0x18020ba14  mov     rax, [rcx]
0x18020ba17  mov     rax, [rax+10h]
0x18020ba1b  call    _guard_dispatch_icall
0x18020ba20  nop
0x18020ba21  jmp     loc_18020BCAE
0x18020ba26  mov     [rbp+0F0h+var_160], 0
0x18020ba2e  mov     rcx, [rbp+0F0h+var_158]
0x18020ba32  mov     rax, [rcx]
0x18020ba35  mov     [rbp+0F0h+var_160], 0
0x18020ba3d  lea     r9, [rbp+0F0h+var_160]
0x18020ba41  lea     r8, _GUID_28f61b65_979a_4ebc_882a_6006ebcbd52e
0x18020ba48  mov     rdx, r15
0x18020ba4b  mov     rax, [rax+38h]
0x18020ba4f  call    _guard_dispatch_icall
0x18020ba54  mov     ebx, eax
0x18020ba56  test    eax, eax
0x18020ba58  jns     short loc_18020BA8B
0x18020ba5a  mov     rcx, [rbp+0F0h+var_160]
0x18020ba5e  test    rcx, rcx
0x18020ba61  jz      short loc_18020BA70
0x18020ba63  mov     rax, [rcx]
0x18020ba66  mov     rax, [rax+10h]
0x18020ba6a  call    _guard_dispatch_icall
0x18020ba6f  nop
0x18020ba70  mov     rcx, [rbp+0F0h+var_158]
0x18020ba74  test    rcx, rcx
0x18020ba77  jz      short loc_18020BA86
0x18020ba79  mov     rax, [rcx]
0x18020ba7c  mov     rax, [rax+10h]
0x18020ba80  call    _guard_dispatch_icall
0x18020ba85  nop
0x18020ba86  jmp     loc_18020BCAE
0x18020ba8b  mov     rax, [rbp+0F0h+var_160]
0x18020ba8f  mov     [rsp+1F0h+var_1C0], rax
0x18020ba94  mov     [rsp+1F0h+var_1C8], 0
0x18020ba9d  mov     eax, [rbp+0F0h+arg_28]
0x18020baa3  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18020baa7  lea     r9, [rsi+30h]
0x18020baab  mov     r8, [rbp+0F0h+var_150]
0x18020baaf  mov     rdx, [rsp+1F0h+var_1B0]
0x18020bab4  mov     rcx, rdi
0x18020bab7  call    ?RegisterPackagesAsync@CAppxDeploymentOperation@@QEAAJPEBU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@ABI@@QEAUHSTRING__@@PEBDK_KPEAUITokenHandle@Internal@Handles@456@@Z; CAppxDeploymentOperation::RegisterPackagesAsync(ABI::Windows::Foundation::Collections::IIterable<HSTRING__ *> const *,HSTRING__ * const,char const *,ulong,unsigned __int64,ABI::Windows::Foundation::Handles::Internal::ITokenHandle *)
0x18020babc  mov     ebx, eax
0x18020babe  mov     rcx, [rbp+0F0h+var_160]
0x18020bac2  test    rcx, rcx
0x18020bac5  jz      short loc_18020BAD4
0x18020bac7  mov     rax, [rcx]
0x18020baca  mov     rax, [rax+10h]
0x18020bace  call    _guard_dispatch_icall
0x18020bad3  nop
0x18020bad4  mov     rcx, [rbp+0F0h+var_158]
0x18020bad8  test    rcx, rcx
0x18020badb  jz      short loc_18020BAEA
0x18020badd  mov     rax, [rcx]
0x18020bae0  mov     rax, [rax+10h]
0x18020bae4  call    _guard_dispatch_icall
0x18020bae9  nop
0x18020baea  xor     edx, edx
0x18020baec  test    ebx, ebx
0x18020baee  jns     short loc_18020BB02
0x18020baf0  lea     rax, aRegisterpackag_0; "RegisterPackagesAsync"
0x18020baf7  xor     ecx, ecx
0x18020baf9  lea     r9d, [rdx+1]
0x18020bafd  jmp     loc_18020B92B
0x18020bb02  mov     rcx, [rsp+1F0h+var_198]
0x18020bb07  mov     rax, [rcx+0C8h]
0x18020bb0e  mov     [rbp+0F0h+Handles], rax
0x18020bb15  mov     rax, [rdi+28h]
0x18020bb19  mov     [rbp+0F0h+Handles+8], rax
0x18020bb20  mov     rax, [rdi+30h]
0x18020bb24  mov     qword ptr [rbp+0F0h+var_50], rax
0x18020bb2b  mov     rax, [rcx+0C0h]
0x18020bb32  mov     qword ptr [rbp+0F0h+var_50+8], rax
0x18020bb39  mov     r15d, 4
0x18020bb3f  mov     dword ptr [rbp+0F0h+var_160], r15d
0x18020bb43  mov     esi, 1000h
0x18020bb48  jmp     loc_18020BC29
0x18020bb4d  cmp     eax, 1
0x18020bb50  jz      loc_18020BDC3
0x18020bb56  cmp     eax, 2
0x18020bb59  jz      short loc_18020BBA4
0x18020bb5b  cmp     eax, 3
0x18020bb5e  jnz     loc_18020BD22
0x18020bb64  lea     rax, aAppxInstallEve_1; "AppX Install: Event Fired: Cancel"
0x18020bb6b  mov     [rsp+1F0h+var_1C8], rax
0x18020bb70  mov     [rsp+1F0h+var_1D0], rcx
0x18020bb75  mov     r9d, 5
0x18020bb7b  mov     r8d, esi
0x18020bb7e  xor     edx, edx
0x18020bb80  xor     ecx, ecx
0x18020bb82  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020bb87  mov     rcx, rdi; this
0x18020bb8a  call    ?Cancel@CAppxDeploymentOperation@@QEAAJXZ; CAppxDeploymentOperation::Cancel(void)
0x18020bb8f  dec     r15d
0x18020bb92  mov     dword ptr [rbp+0F0h+var_160], r15d
0x18020bb96  mov     rax, [rsp+1F0h+var_198]
0x18020bb9b  mov     rcx, [rax+0C0h]
0x18020bba2  jmp     short loc_18020BC21
0x18020bba4  xor     edx, edx; Val
0x18020bba6  mov     r8d, 0D4h; Size
0x18020bbac  lea     rcx, [rbp+0F0h+var_13C]; void *
0x18020bbb0  call    memset
0x18020bbb5  mov     [rbp+0F0h+var_140], 1
0x18020bbbc  mov     eax, [rdi+98h]
0x18020bbc2  mov     [rbp+0F0h+var_128], eax
0x18020bbc5  mov     [rbp+0F0h+var_124], 64h ; 'd'
0x18020bbcc  test    r13d, r13d
0x18020bbcf  jz      short loc_18020BC1D
0x18020bbd1  mov     r15, r12
0x18020bbd4  mov     rdi, [rsp+1F0h+var_190]
0x18020bbd9  mov     rax, [r15]
0x18020bbdc  movups  xmm0, xmmword ptr [rax]
0x18020bbdf  movaps  xmmword ptr [rsp+1F0h+hstringHeader.Reserved], xmm0
0x18020bbe4  mov     eax, [rax+10h]
0x18020bbe7  mov     dword ptr [rbp+0F0h+hstringHeader.Reserved+10h], eax
0x18020bbea  mov     rax, [rdi]
0x18020bbed  xor     r9d, r9d
0x18020bbf0  lea     r8, [rbp+0F0h+var_140]
0x18020bbf4  lea     rdx, [rsp+1F0h+hstringHeader]
0x18020bbf9  mov     rcx, rdi
0x18020bbfc  mov     rax, [rax+18h]
0x18020bc00  call    _guard_dispatch_icall
0x18020bc05  lea     r15, [r15+8]
0x18020bc09  sub     r13, 1
0x18020bc0d  jnz     short loc_18020BBD9
0x18020bc0f  mov     rdi, [rsp+1F0h+var_1A0]
0x18020bc14  mov     r13d, [rsp+1F0h+var_1A8]
0x18020bc19  mov     r15d, dword ptr [rbp+0F0h+var_160]
0x18020bc1d  mov     rcx, [rdi+30h]; hEvent
0x18020bc21  call    cs:__imp_ResetEvent
0x18020bc27  xor     edx, edx
0x18020bc29  lea     rax, aAppxInstallBeg; "AppX Install: Begin Wait"
0x18020bc30  mov     [rsp+1F0h+var_1C8], rax
0x18020bc35  mov     [rsp+1F0h+var_1D0], 0
0x18020bc3e  mov     r9d, 5
0x18020bc44  mov     r8d, esi
0x18020bc47  xor     ecx, ecx
0x18020bc49  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020bc4e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18020bc52  xor     r8d, r8d; bWaitAll
0x18020bc55  lea     rdx, [rbp+0F0h+Handles]; lpHandles
0x18020bc5c  mov     ecx, r15d; nCount
0x18020bc5f  call    cs:__imp_WaitForMultipleObjects
0x18020bc65  xor     ecx, ecx
0x18020bc67  test    eax, eax
0x18020bc69  jnz     loc_18020BB4D
0x18020bc6f  lea     rax, aAppxInstallEve; "AppX Install: Event Fired: Cancel+Disco"...
0x18020bc76  mov     [rsp+1F0h+var_1C8], rax
0x18020bc7b  mov     [rsp+1F0h+var_1D0], rcx
0x18020bc80  lea     r9d, [rcx+5]
0x18020bc84  mov     r8d, esi
0x18020bc87  xor     edx, edx
0x18020bc89  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020bc8e  mov     rcx, rdi; this
0x18020bc91  call    ?Cancel@CAppxDeploymentOperation@@QEAAJXZ; CAppxDeploymentOperation::Cancel(void)
0x18020bc96  mov     dword ptr [r14+8], 2
0x18020bc9e  mov     dword ptr [r14+24h], 80242008h
0x18020bca6  mov     dword ptr [r14+20h], 0
0x18020bcae  test    rdi, rdi
0x18020bcb1  jz      short loc_18020BCCA
0x18020bcb3  mov     rcx, rdi; this
0x18020bcb6  call    ?UnbindFromDeploymentRequest@CAppxDeploymentOperation@@QEAAJXZ; CAppxDeploymentOperation::UnbindFromDeploymentRequest(void)
0x18020bcbb  mov     rax, [rdi]
0x18020bcbe  mov     rcx, rdi
0x18020bcc1  mov     rax, [rax+10h]
0x18020bcc5  call    _guard_dispatch_icall
0x18020bcca  xor     edi, edi
  ... truncated ...
```
