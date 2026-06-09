# CTargetAppResolver::GetExtensionInfoFromStateRepositoryForAppUriHandler(HSTRING__ *,HSTRING__ *,CTargetAppResolver::ResolutionStatus *,Windows::System::Internal::Launch::IExtensionInfo * *)

- ea: `0x1800a745c`
- end: `0x1800a77fa`
- name: `?GetExtensionInfoFromStateRepositoryForAppUriHandler@CTargetAppResolver@@AEAAJPEAUHSTRING__@@0PEAW4ResolutionStatus@1@PEAPEAUIExtensionInfo@Launch@Internal@System@Windows@@@Z`
- size: `926`
- prototype: `__int64 __usercall@<rax>(CTargetAppResolver *__hidden this@<rcx>, HSTRING@<rdx>, HSTRING@<r8>, enum CTargetAppResolver::ResolutionStatus *@<r9>, struct Windows::System::Internal::Launch::IExtensionInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ec08`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180024990`
- `0x180027d80`
- `0x18003d764`
- `0x18007537c`
- `0x1800a6940`
- `0x1800a6ab8`
- `0x1800a745c`
- `0x1800a7bb0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a752e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a752e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a75ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a75ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a75d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a75d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a754f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a77da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a754f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a77da`

## string_xrefs

- `0x1800a7519`: `EnableAppUriUserDefaults`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTargetAppResolver::GetExtensionInfoFromStateRepositoryForAppUriHandler(
        CTargetAppResolver *this,
        HSTRING a2,
        HSTRING a3,
        enum CTargetAppResolver::ResolutionStatus *a4,
        struct Windows::System::Internal::Launch::IExtensionInfo **string)
{
  struct Windows::System::Internal::Launch::IExtensionInfo **v9; // r15
  const struct _GUID *v10; // rcx
  int QueryAssociationBrokerService; // eax
  int v12; // ebx
  __int64 v13; // rdx
  void *v14; // rdi
  __int64 (__fastcall *v15)(void *, HSTRING, _QWORD, struct Windows::System::Internal::Launch::IExtensionInfo ***); // rbx
  _QWORD *v16; // rax
  const WCHAR *StringRawBuffer; // rax
  void **v18; // r8
  int StateRepositoryQueryHelper; // eax
  int v20; // eax
  __int64 v21; // rdx
  struct Windows::System::Internal::Launch::IExtensionInfo *v22; // rdx
  void *v23; // rdi
  __int64 (__fastcall *v24)(void *, HSTRING, HSTRING, _QWORD); // rbx
  _QWORD *OriginatingPackageFamilyName; // rax
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  int ResolvedTarget; // eax
  int pdwType; // [rsp+20h] [rbp-50h]
  int pdwTypea; // [rsp+20h] [rbp-50h]
  int pdwTypeb; // [rsp+20h] [rbp-50h]
  int *pdwTypec; // [rsp+20h] [rbp-50h]
  int v35[2]; // [rsp+40h] [rbp-30h] BYREF
  struct Windows::System::Internal::Launch::IExtensionInfo *v36; // [rsp+48h] [rbp-28h] BYREF
  void *v37; // [rsp+50h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+58h] [rbp-18h] BYREF
  HSTRING v39[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  HSTRING v41; // [rsp+C0h] [rbp+50h] BYREF
  HSTRING pcbData; // [rsp+C8h] [rbp+58h] BYREF

  v41 = a3;
  *(_DWORD *)a4 = 0;
  v9 = string;
  *string = 0;
  newString = 0;
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  QueryAssociationBrokerService = GetQueryAssociationBrokerService(v10, &v37);
  v12 = QueryAssociationBrokerService;
  if ( QueryAssociationBrokerService >= 0 )
  {
    if ( a3 )
    {
      QueryAssociationBrokerService = Microsoft::WRL::Wrappers::HString::Set(&newString, &v41);
      v12 = QueryAssociationBrokerService;
      if ( QueryAssociationBrokerService < 0 )
      {
        v13 = 338;
        goto LABEL_6;
      }
LABEL_27:
      if ( !*(_DWORD *)a4 || *(_DWORD *)a4 == 3 )
      {
        *(_QWORD *)v35 = 0;
        v23 = v37;
        v24 = *(__int64 (__fastcall **)(void *, HSTRING, HSTRING, _QWORD))(*(_QWORD *)v37 + 72LL);
        OriginatingPackageFamilyName = (_QWORD *)CallerInformation::GetOriginatingPackageFamilyName(
                                                   (char *)this + 96,
                                                   v39);
        pdwTypec = v35;
        v12 = v24(v23, a2, newString, *OriginatingPackageFamilyName);
        WindowsDeleteString(v39[0]);
        if ( v12 < 0 )
        {
          v26 = (unsigned int)v12;
          v27 = 373;
LABEL_31:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
            (const char *)v26,
            (int)pdwTypec);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
          goto LABEL_39;
        }
        v28 = CTargetAppResolver::AppendToLaunchProviders(this, *(_QWORD *)v35);
        v12 = v28;
        if ( v28 < 0 )
        {
          v26 = (unsigned int)v28;
          v27 = 374;
          goto LABEL_31;
        }
        if ( !*(_DWORD *)a4 )
        {
          ResolvedTarget = CTargetAppResolver::GetResolvedTarget(this, (__int64)v9);
          v12 = ResolvedTarget;
          if ( ResolvedTarget < 0 )
          {
            v26 = (unsigned int)ResolvedTarget;
            v27 = 378;
            goto LABEL_31;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
      }
LABEL_38:
      v12 = 0;
      goto LABEL_39;
    }
    LODWORD(string) = 0;
    LODWORD(pcbData) = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsSystemLauncherTestHooks",
      L"EnableAppUriUserDefaults",
      0x18u,
      0,
      &string,
      (LPDWORD)&pcbData);
    if ( (_DWORD)string == 1 )
      goto LABEL_27;
    string = 0;
    v14 = v37;
    v15 = *(__int64 (__fastcall **)(void *, HSTRING, _QWORD, struct Windows::System::Internal::Launch::IExtensionInfo ***))(*(_QWORD *)v37 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = (_QWORD *)CallerInformation::GetOriginatingPackageFamilyName((char *)this + 96, &pcbData);
    v12 = v15(v14, a2, *v16, &string);
    WindowsDeleteString(pcbData);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
        (const char *)(unsigned int)v12,
        pdwTypea);
LABEL_10:
      WindowsDeleteString((HSTRING)string);
      string = 0;
      goto LABEL_39;
    }
    if ( !string )
    {
      WindowsDeleteString(0);
      string = 0;
      goto LABEL_38;
    }
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"Undecided", -1, 0) == 2 )
    {
      if ( CTargetAppResolver::CanSystemShowDisambiguationUI(this) )
        *(_DWORD *)a4 = 3;
    }
    else
    {
      pcbData = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pcbData);
      StateRepositoryQueryHelper = LauncherMiscHelpers::GetStateRepositoryQueryHelper(
                                     (LauncherMiscHelpers *)&GUID_dca3c552_9d75_54a4_b78b_5c7fbfd8504b,
                                     (const struct _GUID *)&pcbData,
                                     v18);
      v12 = StateRepositoryQueryHelper;
      if ( StateRepositoryQueryHelper < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
          (const char *)(unsigned int)StateRepositoryQueryHelper,
          pdwTypeb);
LABEL_16:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pcbData);
        goto LABEL_10;
      }
      v36 = 0;
      v20 = (*(__int64 (__fastcall **)(HSTRING, struct Windows::System::Internal::Launch::IExtensionInfo **, HSTRING, struct Windows::System::Internal::Launch::IExtensionInfo **))(*(_QWORD *)pcbData + 64LL))(
              pcbData,
              string,
              a2,
              &v36);
      v12 = v20;
      if ( v20 < 0 )
      {
        v21 = 353;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
          (const char *)(unsigned int)v20,
          pdwTypeb);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        goto LABEL_16;
      }
      v22 = v36;
      if ( v36 )
      {
        *(_DWORD *)a4 = 1;
        v36 = 0;
        *v9 = v22;
        v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 104LL))(*((_QWORD *)this + 19));
        v12 = v20;
        if ( v20 < 0 )
        {
          v21 = 359;
          goto LABEL_19;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pcbData);
    }
    WindowsDeleteString((HSTRING)string);
    goto LABEL_27;
  }
  v13 = 334;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
    (const char *)(unsigned int)QueryAssociationBrokerService,
    pdwType);
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  WindowsDeleteString(newString);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a745c  mov     [rsp-38h+arg_0], rbx
0x1800a7461  mov     [rsp-38h+arg_10], r8
0x1800a7466  push    rbp
0x1800a7467  push    rsi
0x1800a7468  push    rdi
0x1800a7469  push    r12
0x1800a746b  push    r13
0x1800a746d  push    r14
0x1800a746f  push    r15
0x1800a7471  mov     rbp, rsp
0x1800a7474  sub     rsp, 70h
0x1800a7478  mov     rsi, r9
0x1800a747b  mov     rdi, r8
0x1800a747e  mov     r12, rdx
0x1800a7481  mov     r14, rcx
0x1800a7484  xor     r13d, r13d
0x1800a7487  mov     [r9], r13d
0x1800a748a  mov     r15, [rbp+string]
0x1800a748e  mov     [r15], r13
0x1800a7491  mov     [rbp+newString], r13
0x1800a7495  mov     [rbp+var_20], r13
0x1800a7499  lea     rcx, [rbp+var_20]
0x1800a749d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a74a2  lea     rdx, [rbp+var_20]; void **
0x1800a74a6  call    ?GetQueryAssociationBrokerService@@YAJAEBU_GUID@@PEAPEAX@Z; GetQueryAssociationBrokerService(_GUID const &,void * *)
0x1800a74ab  mov     ebx, eax
0x1800a74ad  test    eax, eax
0x1800a74af  jns     short loc_1800A74B8
0x1800a74b1  mov     edx, 14Eh
0x1800a74b6  jmp     short loc_1800A74D9
0x1800a74b8  test    rdi, rdi
0x1800a74bb  jz      short loc_1800A74F1
0x1800a74bd  lea     rdx, [rbp+arg_10]; HSTRING *
0x1800a74c1  lea     rcx, [rbp+newString]; newString
0x1800a74c5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800a74ca  mov     ebx, eax
0x1800a74cc  test    eax, eax
0x1800a74ce  jns     loc_1800A76F6
0x1800a74d4  mov     edx, 152h; void *
0x1800a74d9  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x1800a74e0  mov     r9d, eax; char *
0x1800a74e3  mov     rcx, [rbp+38h]; this
0x1800a74e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a74ec  jmp     loc_1800A77CC
0x1800a74f1  mov     dword ptr [rbp+string], r13d
0x1800a74f5  mov     dword ptr [rbp+arg_18], 4
0x1800a74fc  lea     rax, [rbp+arg_18]
0x1800a7500  mov     [rsp+70h+pcbData], rax; pcbData
0x1800a7505  lea     rax, [rbp+string]
0x1800a7509  mov     [rsp+70h+pvData], rax; pvData
0x1800a750e  mov     [rsp+70h+pdwType], r13; int
0x1800a7513  mov     r9d, 18h; dwFlags
0x1800a7519  lea     r8, aEnableappurius; "EnableAppUriUserDefaults"
0x1800a7520  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a7527  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800a752e  call    cs:__imp_RegGetValueW
0x1800a7534  cmp     dword ptr [rbp+string], 1
0x1800a7538  jz      loc_1800A76F6
0x1800a753e  mov     [rbp+string], r13
0x1800a7542  mov     rdi, [rbp+var_20]
0x1800a7546  mov     rax, [rdi]
0x1800a7549  mov     rbx, [rax+68h]
0x1800a754d  xor     ecx, ecx; string
0x1800a754f  call    cs:__imp_WindowsDeleteString
0x1800a7555  mov     [rbp+string], r13
0x1800a7559  lea     rcx, [r14+60h]
0x1800a755d  lea     rdx, [rbp+arg_18]
0x1800a7561  call    ?GetOriginatingPackageFamilyName@CallerInformation@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; CallerInformation::GetOriginatingPackageFamilyName(void)
0x1800a7566  nop
0x1800a7567  lea     r9, [rbp+string]
0x1800a756b  mov     r8, [rax]
0x1800a756e  mov     rdx, r12
0x1800a7571  mov     rcx, rdi
0x1800a7574  mov     rax, rbx
0x1800a7577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a757c  mov     ebx, eax
0x1800a757e  mov     rcx, [rbp+arg_18]; string
0x1800a7582  call    cs:__imp_WindowsDeleteString
0x1800a7588  test    ebx, ebx
0x1800a758a  jns     short loc_1800A75B8
0x1800a758c  mov     rcx, [rbp+38h]; this
0x1800a7590  mov     r9d, ebx; char *
0x1800a7593  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x1800a759a  mov     edx, 157h; void *
0x1800a759f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a75a4  nop
0x1800a75a5  mov     rcx, [rbp+string]; string
0x1800a75a9  call    cs:__imp_WindowsDeleteString
0x1800a75af  mov     [rbp+string], r13
0x1800a75b3  jmp     loc_1800A77CC
0x1800a75b8  mov     rcx, [rbp+string]; string
0x1800a75bc  test    rcx, rcx
0x1800a75bf  jnz     short loc_1800A75D0
0x1800a75c1  call    cs:__imp_WindowsDeleteString
0x1800a75c7  mov     [rbp+string], r13
0x1800a75cb  jmp     loc_1800A77C9
0x1800a75d0  xor     edx, edx; length
0x1800a75d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a75d8  mov     dword ptr [rsp+70h+pdwType], r13d; int
0x1800a75dd  or      edx, 0FFFFFFFFh; cchCount1
0x1800a75e0  mov     r9d, edx; cchCount2
0x1800a75e3  lea     r8, aUndecided; "Undecided"
0x1800a75ea  mov     rcx, rax; lpString1
0x1800a75ed  call    cs:__imp_CompareStringOrdinal
0x1800a75f3  cmp     eax, 2
0x1800a75f6  jz      loc_1800A76DA
0x1800a75fc  mov     [rbp+arg_18], r13
0x1800a7600  lea     rcx, [rbp+arg_18]
0x1800a7604  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7609  lea     rdx, [rbp+arg_18]; struct _GUID *
0x1800a760d  lea     rcx, _GUID_dca3c552_9d75_54a4_b78b_5c7fbfd8504b; this
0x1800a7614  call    ?GetStateRepositoryQueryHelper@LauncherMiscHelpers@@YAJAEBU_GUID@@PEAPEAX@Z; LauncherMiscHelpers::GetStateRepositoryQueryHelper(_GUID const &,void * *)
0x1800a7619  mov     ebx, eax
0x1800a761b  test    eax, eax
0x1800a761d  jns     short loc_1800A7646
0x1800a761f  mov     rcx, [rbp+38h]; this
0x1800a7623  mov     r9d, eax; char *
0x1800a7626  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x1800a762d  mov     edx, 15Fh; void *
0x1800a7632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7637  nop
0x1800a7638  lea     rcx, [rbp+arg_18]
0x1800a763c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7641  jmp     loc_1800A75A5
0x1800a7646  mov     [rbp+var_28], r13
0x1800a764a  mov     rcx, [rbp+arg_18]
0x1800a764e  mov     rax, [rcx]
0x1800a7651  lea     r9, [rbp+var_28]
0x1800a7655  mov     r8, r12
0x1800a7658  mov     rdx, [rbp+string]
0x1800a765c  mov     rax, [rax+40h]
0x1800a7660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7665  mov     ebx, eax
0x1800a7667  test    eax, eax
0x1800a7669  jns     short loc_1800A768F
0x1800a766b  mov     edx, 161h; void *
0x1800a7670  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x1800a7677  mov     r9d, eax; char *
0x1800a767a  mov     rcx, [rbp+38h]; this
0x1800a767e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7683  nop
0x1800a7684  lea     rcx, [rbp+var_28]
0x1800a7688  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a768d  jmp     short loc_1800A7638
0x1800a768f  mov     rdx, [rbp+var_28]
0x1800a7693  test    rdx, rdx
0x1800a7696  jz      short loc_1800A76C5
0x1800a7698  mov     dword ptr [rsi], 1
0x1800a769e  mov     [rbp+var_28], r13
0x1800a76a2  mov     [r15], rdx
0x1800a76a5  mov     rcx, [r14+98h]
0x1800a76ac  mov     rax, [rcx]
0x1800a76af  mov     rax, [rax+68h]
0x1800a76b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a76b8  mov     ebx, eax
0x1800a76ba  test    eax, eax
0x1800a76bc  jns     short loc_1800A76C5
0x1800a76be  mov     edx, 167h
0x1800a76c3  jmp     short loc_1800A7670
0x1800a76c5  lea     rcx, [rbp+var_28]
0x1800a76c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a76ce  nop
0x1800a76cf  lea     rcx, [rbp+arg_18]
0x1800a76d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a76d8  jmp     short loc_1800A76EC
0x1800a76da  mov     rcx, r14; this
0x1800a76dd  call    ?CanSystemShowDisambiguationUI@CTargetAppResolver@@AEAA_NXZ; CTargetAppResolver::CanSystemShowDisambiguationUI(void)
0x1800a76e2  test    al, al
0x1800a76e4  jz      short loc_1800A76EC
0x1800a76e6  mov     dword ptr [rsi], 3
0x1800a76ec  mov     rcx, [rbp+string]; string
0x1800a76f0  call    cs:__imp_WindowsDeleteString
0x1800a76f6  cmp     [rsi], r13d
0x1800a76f9  jz      short loc_1800A7704
0x1800a76fb  cmp     dword ptr [rsi], 3
0x1800a76fe  jnz     loc_1800A77C9
0x1800a7704  mov     qword ptr [rbp+var_30], r13
0x1800a7708  mov     rdi, [rbp+var_20]
0x1800a770c  mov     rax, [rdi]
0x1800a770f  mov     rbx, [rax+48h]
0x1800a7713  lea     rcx, [r14+60h]
0x1800a7717  lea     rdx, [rbp+var_10]
0x1800a771b  call    ?GetOriginatingPackageFamilyName@CallerInformation@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; CallerInformation::GetOriginatingPackageFamilyName(void)
0x1800a7720  nop
0x1800a7721  lea     rcx, [rbp+var_30]
0x1800a7725  mov     [rsp+70h+pdwType], rcx; int
0x1800a772a  mov     r9, [rax]
0x1800a772d  mov     r8, [rbp+newString]
0x1800a7731  mov     rdx, r12
0x1800a7734  mov     rcx, rdi
0x1800a7737  mov     rax, rbx
0x1800a773a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a773f  mov     ebx, eax
0x1800a7741  mov     rcx, [rbp+var_10]; string
0x1800a7745  call    cs:__imp_WindowsDeleteString
0x1800a774b  test    ebx, ebx
0x1800a774d  jns     short loc_1800A7773
0x1800a774f  mov     r9d, ebx; char *
0x1800a7752  mov     edx, 175h; void *
0x1800a7757  mov     rcx, [rbp+38h]; this
0x1800a775b  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x1800a7762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7767  nop
0x1800a7768  lea     rcx, [rbp+var_30]
0x1800a776c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7771  jmp     short loc_1800A77CC
0x1800a7773  mov     rdx, qword ptr [rbp+var_30]
0x1800a7777  mov     rcx, r14
0x1800a777a  call    ?AppendToLaunchProviders@CTargetAppResolver@@AEAAJPEAU?$IVectorView@PEAVExtensionInfo@Launch@Internal@System@Windows@@@Collections@Foundation@Windows@@@Z; CTargetAppResolver::AppendToLaunchProviders(Windows::Foundation::Collections::IVectorView<Windows::System::Internal::Launch::ExtensionInfo *> *)
0x1800a777f  mov     ebx, eax
0x1800a7781  test    eax, eax
0x1800a7783  jns     short loc_1800A778F
0x1800a7785  mov     r9d, eax
0x1800a7788  mov     edx, 176h
0x1800a778d  jmp     short loc_1800A7757
0x1800a778f  cmp     [rsi], r13d
0x1800a7792  jnz     short loc_1800A77C0
0x1800a7794  cmp     [rbp+newString], r13
0x1800a7798  setnz   r8b
0x1800a779c  mov     [rsp+70h+pdwType], r15; __int64
0x1800a77a1  mov     r9, rsi
0x1800a77a4  mov     rdx, qword ptr [rbp+var_30]
0x1800a77a8  mov     rcx, r14; this
0x1800a77ab  call    ?GetResolvedTarget@CTargetAppResolver@@AEAAJPEAU?$IVectorView@PEAVExtensionInfo@Launch@Internal@System@Windows@@@Collections@Foundation@Windows@@_NPEAW4ResolutionStatus@1@PEAPEAUIExtensionInfo@Launch@Internal@System@5@@Z; CTargetAppResolver::GetResolvedTarget(Windows::Foundation::Collections::IVectorView<Windows::System::Internal::Launch::ExtensionInfo *> *,bool,CTargetAppResolver::ResolutionStatus *,Windows::System::Internal::Launch::IExtensionInfo * *)
0x1800a77b0  mov     ebx, eax
0x1800a77b2  test    eax, eax
0x1800a77b4  jns     short loc_1800A77C0
0x1800a77b6  mov     r9d, eax
0x1800a77b9  mov     edx, 17Ah
0x1800a77be  jmp     short loc_1800A7757
0x1800a77c0  lea     rcx, [rbp+var_30]
0x1800a77c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a77c9  mov     ebx, r13d
0x1800a77cc  lea     rcx, [rbp+var_20]
0x1800a77d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a77d5  nop
0x1800a77d6  mov     rcx, [rbp+newString]; string
0x1800a77da  call    cs:__imp_WindowsDeleteString
0x1800a77e0  mov     eax, ebx
0x1800a77e2  mov     rbx, [rsp+70h+arg_0]
0x1800a77ea  add     rsp, 70h
0x1800a77ee  pop     r15
0x1800a77f0  pop     r14
0x1800a77f2  pop     r13
0x1800a77f4  pop     r12
0x1800a77f6  pop     rdi
0x1800a77f7  pop     rsi
0x1800a77f8  pop     rbp
0x1800a77f9  retn
```
