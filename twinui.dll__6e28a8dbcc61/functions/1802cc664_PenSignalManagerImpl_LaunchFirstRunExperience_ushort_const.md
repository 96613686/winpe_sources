# PenSignalManagerImpl::LaunchFirstRunExperience(ushort const *)

- ea: `0x1802cc664`
- end: `0x1802cca83`
- name: `?LaunchFirstRunExperience@PenSignalManagerImpl@@AEAAJPEBG@Z`
- size: `1055`
- prototype: `__int64 __fastcall(PenSignalManagerImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802cd510`

## callees

- `0x180008acc`
- `0x18000c350`
- `0x180026d94`
- `0x18003c5e4`
- `0x180052980`
- `0x1800a706c`
- `0x180107e10`
- `0x18013d330`
- `0x1801f6864`
- `0x180207bcc`
- `0x1802cb9fc`
- `0x1802cbaac`
- `0x1802cbae8`
- `0x1802cc0c0`
- `0x1802cc664`
- `0x1802cca8c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc7fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc8f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cca39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc7fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cc8f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cca39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc8e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc9dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc8e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cc9dc`

## string_xrefs

- `0x1802cc69e`: `PenDetachFREComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PenSignalManagerImpl::LaunchFirstRunExperience(
        PenSignalManagerImpl *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  PenSignalManagerImpl *v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  PenSignalManagerImpl *v28; // rcx
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v32; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v37[4]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  _BYTE v40[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( IsUserOOBEOrCredentialReset() )
    return 0;
  v3 = SHRegSetBOOL(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PenWorkspace",
         L"PenDetachFREComplete",
         1);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)v4,
      (int)string);
    return v4;
  }
  v35 = 0;
  v36 = 0;
  v34 = 0;
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.Launcher", 0x18u, 0x17u);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(v39, &v36);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 178;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
    goto LABEL_38;
  }
  v7 = v36;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v40, off_1803E2388);
  v5 = v8(v7, *(_QWORD *)(v9 + 24), &v34);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 179;
    goto LABEL_9;
  }
  v5 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(
         v34,
         &v35);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 180;
    goto LABEL_9;
  }
  v32 = 0;
  string = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v32);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 186;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
    goto LABEL_15;
  }
  if ( !v32 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51575997>::GetImpl'::`2'::impl) )
    {
      v10 = PenSignalManagerImpl::LaunchUri(v12, L"ms-get-started://redirect?id=penfre", 0);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 192;
        goto LABEL_14;
      }
    }
LABEL_36:
    WindowsDeleteString(string);
    v4 = 0;
    goto LABEL_37;
  }
  v13 = 0;
  while ( 1 )
  {
    v33 = 0;
    v14 = v35;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v16 = v15(v14, v13, &v33);
    v4 = v16;
    if ( v16 < 0 )
    {
      v19 = 201;
      goto LABEL_29;
    }
    v17 = v33;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v18(v17, &string);
    v4 = v16;
    if ( v16 < 0 )
    {
      v19 = 202;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
        (const char *)(unsigned int)v16,
        (int)string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      goto LABEL_15;
    }
    if ( WindowsGetStringRawBuffer(string, 0) )
      break;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    if ( ++v13 >= v32 )
      goto LABEL_25;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
LABEL_25:
  if ( !WindowsGetStringRawBuffer(string, 0) )
  {
    WindowsDeleteString(string);
    v4 = -2147418113;
    goto LABEL_37;
  }
  v20 = std::wstring::wstring(v40, L"undocked");
  v21 = std::wstring::wstring(v43, L"source=");
  v22 = std::wstring::wstring(v42, L"://?");
  v24 = std::operator+<unsigned short>(v41, v23, v22);
  std::wstring::wstring(&hstringHeader, v25, v24, v21);
  std::wstring::wstring(v37, v26, &hstringHeader, v20);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(v43);
  std::wstring::_Tidy_deallocate(v40);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v29 = (const unsigned __int16 *)v37;
  if ( v37[3] > (unsigned __int16 *)7 )
    v29 = v37[0];
  v30 = PenSignalManagerImpl::LaunchUri(v28, v29, StringRawBuffer);
  v4 = v30;
  if ( v30 >= 0 )
  {
    std::wstring::_Tidy_deallocate(v37);
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE0,
    (unsigned int)"shell\\twinui\\pensignalmanager\\lib\\pensignalmanagerimpl.cpp",
    (const char *)(unsigned int)v30,
    (int)string);
  std::wstring::_Tidy_deallocate(v37);
LABEL_15:
  WindowsDeleteString(string);
LABEL_37:
  string = 0;
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return v4;
}

```

## disassembly

```asm
0x1802cc664  push    rbp
0x1802cc666  push    rbx
0x1802cc667  push    rsi
0x1802cc668  push    rdi
0x1802cc669  push    r14
0x1802cc66b  lea     rbp, [rsp-20h]
0x1802cc670  sub     rsp, 120h
0x1802cc677  mov     rax, cs:__security_cookie
0x1802cc67e  xor     rax, rsp
0x1802cc681  mov     [rbp+40h+var_30], rax
0x1802cc685  xor     r14d, r14d
0x1802cc688  call    ?IsUserOOBEOrCredentialReset@@YA_NXZ; IsUserOOBEOrCredentialReset(void)
0x1802cc68d  test    al, al
0x1802cc68f  jz      short loc_1802CC698
0x1802cc691  xor     eax, eax
0x1802cc693  jmp     loc_1802CCA69
0x1802cc698  mov     r9d, 1; int
0x1802cc69e  lea     r8, aPendetachfreco; "PenDetachFREComplete"
0x1802cc6a5  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1802cc6ac  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1802cc6b3  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1802cc6b8  mov     ebx, eax
0x1802cc6ba  test    eax, eax
0x1802cc6bc  jns     short loc_1802CC6F3
0x1802cc6be  mov     rcx, [rbp+48h]; this
0x1802cc6c2  mov     r9d, eax; char *
0x1802cc6c5  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cc6cc  mov     edx, 4Ch ; 'L'; void *
0x1802cc6d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cc6d6  mov     rcx, [rbp+48h]; this
0x1802cc6da  mov     r9d, ebx; char *
0x1802cc6dd  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cc6e4  mov     edx, 0ABh; void *
0x1802cc6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cc6ee  jmp     loc_1802CCA67
0x1802cc6f3  mov     [rsp+140h+var_100], r14
0x1802cc6f8  mov     [rsp+140h+var_F8], r14
0x1802cc6fd  mov     [rsp+140h+var_108], r14
0x1802cc702  mov     [rbp+40h+var_B8], r14
0x1802cc706  mov     r9d, 17h; unsigned int
0x1802cc70c  lea     r8d, [r9+1]; unsigned int
0x1802cc710  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1802cc717  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x1802cc71c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802cc721  lea     rdx, [rsp+140h+var_F8]
0x1802cc726  mov     rcx, [rbp+40h+var_B8]
0x1802cc72a  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>)
0x1802cc72f  mov     ebx, eax
0x1802cc731  test    eax, eax
0x1802cc733  jns     short loc_1802CC73C
0x1802cc735  mov     edx, 0B2h
0x1802cc73a  jmp     short loc_1802CC782
0x1802cc73c  mov     rdi, [rsp+140h+var_F8]
0x1802cc741  mov     rax, [rdi]
0x1802cc744  mov     rbx, [rax+68h]
0x1802cc748  lea     rcx, [rsp+140h+var_108]
0x1802cc74d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cc752  lea     rdx, off_1803E2388; "first-run-pen-experience"
0x1802cc759  lea     rcx, [rbp+40h+var_B0]
0x1802cc75d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802cc762  nop
0x1802cc763  lea     r8, [rsp+140h+var_108]
0x1802cc768  mov     rdx, [rax+18h]
0x1802cc76c  mov     rcx, rdi
0x1802cc76f  mov     rax, rbx
0x1802cc772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cc777  mov     ebx, eax
0x1802cc779  test    eax, eax
0x1802cc77b  jns     short loc_1802CC79A
0x1802cc77d  mov     edx, 0B3h; void *
0x1802cc782  mov     rcx, [rbp+48h]; this
0x1802cc786  mov     r9d, eax; char *
0x1802cc789  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cc790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cc795  jmp     loc_1802CCA47
0x1802cc79a  lea     rdx, [rsp+140h+var_100]
0x1802cc79f  mov     rcx, [rsp+140h+var_108]
0x1802cc7a4  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@12@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> * *,tagCOWAIT_FLAGS,void *)
0x1802cc7a9  mov     ebx, eax
0x1802cc7ab  test    eax, eax
0x1802cc7ad  jns     short loc_1802CC7B6
0x1802cc7af  mov     edx, 0B4h
0x1802cc7b4  jmp     short loc_1802CC782
0x1802cc7b6  mov     [rsp+140h+var_118], r14d
0x1802cc7bb  mov     [rsp+140h+string], r14; int
0x1802cc7c0  mov     rcx, [rsp+140h+var_100]
0x1802cc7c5  mov     rax, [rcx]
0x1802cc7c8  lea     rdx, [rsp+140h+var_118]
0x1802cc7cd  mov     rax, [rax+38h]
0x1802cc7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cc7d6  mov     ebx, eax
0x1802cc7d8  test    eax, eax
0x1802cc7da  jns     short loc_1802CC805
0x1802cc7dc  mov     edx, 0BAh; void *
0x1802cc7e1  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cc7e8  mov     r9d, eax; char *
0x1802cc7eb  mov     rcx, [rbp+48h]; this
0x1802cc7ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cc7f4  nop
0x1802cc7f5  mov     rcx, [rsp+140h+string]; string
0x1802cc7fa  call    cs:__imp_WindowsDeleteString
0x1802cc800  jmp     loc_1802CCA42
0x1802cc805  mov     eax, [rsp+140h+var_118]
0x1802cc809  test    eax, eax
0x1802cc80b  jnz     short loc_1802CC841
0x1802cc80d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51575997@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51575997@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997> `wil::Feature<__WilFeatureTraits_Feature_51575997>::GetImpl(void)'::`2'::impl
0x1802cc814  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51575997@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51575997>::__private_IsEnabled(void)
0x1802cc819  test    al, al
0x1802cc81b  jnz     loc_1802CCA34
0x1802cc821  xor     r8d, r8d; unsigned __int16 *
0x1802cc824  lea     rdx, aMsGetStartedRe; "ms-get-started://redirect?id=penfre"
0x1802cc82b  call    ?LaunchUri@PenSignalManagerImpl@@AEAAJPEBG0@Z; PenSignalManagerImpl::LaunchUri(ushort const *,ushort const *)
0x1802cc830  mov     ebx, eax
0x1802cc832  test    eax, eax
0x1802cc834  jns     loc_1802CCA34
0x1802cc83a  mov     edx, 0C0h
0x1802cc83f  jmp     short loc_1802CC7E1
0x1802cc841  mov     esi, r14d
0x1802cc844  test    eax, eax
0x1802cc846  jz      loc_1802CC8DE
0x1802cc84c  mov     [rsp+140h+var_110], r14
0x1802cc851  mov     rdi, [rsp+140h+var_100]
0x1802cc856  mov     rax, [rdi]
0x1802cc859  mov     rbx, [rax+30h]
0x1802cc85d  lea     rcx, [rsp+140h+var_110]
0x1802cc862  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cc867  lea     r8, [rsp+140h+var_110]
0x1802cc86c  mov     edx, esi
0x1802cc86e  mov     rcx, rdi
0x1802cc871  mov     rax, rbx
0x1802cc874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cc879  mov     ebx, eax
0x1802cc87b  test    eax, eax
0x1802cc87d  js      loc_1802CC934
0x1802cc883  mov     rdi, [rsp+140h+var_110]
0x1802cc888  mov     rax, [rdi]
0x1802cc88b  mov     rbx, [rax+48h]
0x1802cc88f  mov     rcx, [rsp+140h+string]; string
0x1802cc894  call    cs:__imp_WindowsDeleteString
0x1802cc89a  mov     [rsp+140h+string], r14; int
0x1802cc89f  lea     rdx, [rsp+140h+string]
0x1802cc8a4  mov     rcx, rdi
0x1802cc8a7  mov     rax, rbx
0x1802cc8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cc8af  mov     ebx, eax
0x1802cc8b1  test    eax, eax
0x1802cc8b3  js      short loc_1802CC90C
0x1802cc8b5  xor     edx, edx; length
0x1802cc8b7  mov     rcx, [rsp+140h+string]; string
0x1802cc8bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1802cc8c2  nop
0x1802cc8c3  lea     rcx, [rsp+140h+var_110]
0x1802cc8c8  test    rax, rax
0x1802cc8cb  jnz     short loc_1802CC905
0x1802cc8cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cc8d2  inc     esi
0x1802cc8d4  cmp     esi, [rsp+140h+var_118]
0x1802cc8d8  jb      loc_1802CC84C
0x1802cc8de  xor     edx, edx; length
0x1802cc8e0  mov     rcx, [rsp+140h+string]; string
0x1802cc8e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1802cc8eb  test    rax, rax
0x1802cc8ee  jnz     short loc_1802CC93B
0x1802cc8f0  mov     rcx, [rsp+140h+string]; string
0x1802cc8f5  call    cs:__imp_WindowsDeleteString
0x1802cc8fb  mov     ebx, 8000FFFFh
0x1802cc900  jmp     loc_1802CCA42
0x1802cc905  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cc90a  jmp     short loc_1802CC8DE
0x1802cc90c  mov     edx, 0CAh; void *
0x1802cc911  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cc918  mov     r9d, eax; char *
0x1802cc91b  mov     rcx, [rbp+48h]; this
0x1802cc91f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cc924  nop
0x1802cc925  lea     rcx, [rsp+140h+var_110]
0x1802cc92a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cc92f  jmp     loc_1802CC7F5
0x1802cc934  mov     edx, 0C9h
0x1802cc939  jmp     short loc_1802CC911
0x1802cc93b  lea     rdx, aUndocked; "undocked"
0x1802cc942  lea     rcx, [rbp+40h+var_B0]
0x1802cc946  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802cc94b  mov     rdi, rax
0x1802cc94e  lea     rdx, aSource; "source="
0x1802cc955  lea     rcx, [rbp+40h+var_50]
0x1802cc959  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802cc95e  mov     rbx, rax
0x1802cc961  lea     rdx, asc_1804213B8; "://?"
0x1802cc968  lea     rcx, [rbp+40h+var_70]
0x1802cc96c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802cc971  nop
0x1802cc972  mov     r8, rax
0x1802cc975  lea     rcx, [rbp+40h+var_90]
0x1802cc979  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1802cc97e  nop
0x1802cc97f  mov     r9, rbx
0x1802cc982  mov     r8, rax
0x1802cc985  lea     rcx, [rsp+140h+hstringHeader]
0x1802cc98a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1802cc98f  nop
0x1802cc990  mov     r9, rdi
0x1802cc993  lea     r8, [rsp+140h+hstringHeader]
0x1802cc998  lea     rcx, [rsp+140h+var_F0]
0x1802cc99d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1802cc9a2  nop
0x1802cc9a3  lea     rcx, [rsp+140h+hstringHeader]
0x1802cc9a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cc9ad  nop
0x1802cc9ae  lea     rcx, [rbp+40h+var_90]
0x1802cc9b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cc9b7  nop
0x1802cc9b8  lea     rcx, [rbp+40h+var_70]
0x1802cc9bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cc9c1  nop
0x1802cc9c2  lea     rcx, [rbp+40h+var_50]
0x1802cc9c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cc9cb  nop
0x1802cc9cc  lea     rcx, [rbp+40h+var_B0]
0x1802cc9d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cc9d5  xor     edx, edx; length
0x1802cc9d7  mov     rcx, [rsp+140h+string]; string
0x1802cc9dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1802cc9e2  lea     rdx, [rsp+140h+var_F0]
0x1802cc9e7  cmp     [rsp+140h+var_D8], 7
0x1802cc9ed  cmova   rdx, [rsp+140h+var_F0]; unsigned __int16 *
0x1802cc9f3  mov     r8, rax; unsigned __int16 *
0x1802cc9f6  call    ?LaunchUri@PenSignalManagerImpl@@AEAAJPEBG0@Z; PenSignalManagerImpl::LaunchUri(ushort const *,ushort const *)
0x1802cc9fb  mov     ebx, eax
0x1802cc9fd  test    eax, eax
0x1802cc9ff  jns     short loc_1802CCA29
0x1802cca01  mov     rcx, [rbp+48h]; this
0x1802cca05  mov     r9d, eax; char *
0x1802cca08  lea     r8, aShellTwinuiPen_1; "shell\\twinui\\pensignalmanager\\lib\\p"...
0x1802cca0f  mov     edx, 0E0h; void *
0x1802cca14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cca19  nop
0x1802cca1a  lea     rcx, [rsp+140h+var_F0]
0x1802cca1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cca24  jmp     loc_1802CC7F5
0x1802cca29  lea     rcx, [rsp+140h+var_F0]
0x1802cca2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cca33  nop
0x1802cca34  mov     rcx, [rsp+140h+string]; string
0x1802cca39  call    cs:__imp_WindowsDeleteString
0x1802cca3f  mov     ebx, r14d
0x1802cca42  mov     [rsp+140h+string], r14
0x1802cca47  lea     rcx, [rsp+140h+var_108]
0x1802cca4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cca51  nop
0x1802cca52  lea     rcx, [rsp+140h+var_F8]
0x1802cca57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cca5c  nop
0x1802cca5d  lea     rcx, [rsp+140h+var_100]
0x1802cca62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802cca67  mov     eax, ebx
0x1802cca69  mov     rcx, [rbp+40h+var_30]
0x1802cca6d  xor     rcx, rsp; StackCookie
0x1802cca70  call    __security_check_cookie
0x1802cca75  add     rsp, 120h
0x1802cca7c  pop     r14
0x1802cca7e  pop     rdi
0x1802cca7f  pop     rsi
0x1802cca80  pop     rbx
0x1802cca81  pop     rbp
0x1802cca82  retn
```
