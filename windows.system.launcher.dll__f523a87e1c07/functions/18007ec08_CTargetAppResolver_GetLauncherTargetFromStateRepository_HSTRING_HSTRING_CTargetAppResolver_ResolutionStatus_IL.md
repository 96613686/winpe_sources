# CTargetAppResolver::GetLauncherTargetFromStateRepository(HSTRING__ *,HSTRING__ *,CTargetAppResolver::ResolutionStatus *,ILauncherTarget * *)

- ea: `0x18007ec08`
- end: `0x18007f25f`
- name: `?GetLauncherTargetFromStateRepository@CTargetAppResolver@@AEAAJPEAUHSTRING__@@0PEAW4ResolutionStatus@1@PEAPEAUILauncherTarget@@@Z`
- size: `1623`
- prototype: `__int64 __usercall@<rax>(CTargetAppResolver *__hidden this@<rcx>, HSTRING string@<rdx>, HSTRING@<r8>, enum CTargetAppResolver::ResolutionStatus *@<r9>, struct ILauncherTarget **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a91c0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001b8d0`
- `0x180027314`
- `0x18003d318`
- `0x180049cdc`
- `0x180077f08`
- `0x18007ec08`
- `0x18007f268`
- `0x18008a030`
- `0x18008d1c0`
- `0x18009ad54`
- `0x1800a745c`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x18007effc`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18007effc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007ef6f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007ef6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ecb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ef51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007efe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ecb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ef51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007efe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ec6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ec98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ee09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ef94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f22d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ec6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ec98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ee09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ef94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f1e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall CTargetAppResolver::GetLauncherTargetFromStateRepository(
        HSTRING *this,
        HSTRING string,
        HSTRING a3,
        enum CTargetAppResolver::ResolutionStatus *a4,
        struct ILauncherTarget **a5)
{
  int v9; // r14d
  __int64 ExtensionOrSchemeForUri; // rdi
  char v11; // di
  const WCHAR *StringRawBuffer; // rax
  int v13; // eax
  struct Windows::Foundation::IUriRuntimeClass *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  int ExtensionInfoFromStateRepositoryForAppUriHandler; // eax
  struct Windows::System::Internal::Launch::IExtensionInfo *v17; // rbx
  int ExtensionInfoFromStateRepository; // eax
  __int64 (__fastcall *v19)(struct Windows::System::Internal::Launch::IExtensionInfo *, HSTRING *); // rdi
  int v20; // eax
  int v21; // eax
  struct ILauncherTarget *v22; // rax
  HSTRING v23; // rcx
  const WCHAR *v24; // rax
  struct Windows::Foundation::IUriRuntimeClass *v25; // rdi
  __int64 (__fastcall *v26)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v27; // eax
  const WCHAR *v28; // rax
  HRESULT v29; // eax
  void *v30; // rdi
  __int64 (__fastcall *v31)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v32; // eax
  void *v33; // rcx
  __int64 v34; // rbx
  int (__fastcall *v35)(__int64, __int64, _QWORD, LPVOID *); // rdi
  int v36; // eax
  struct ILauncherTarget *v37; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-118h]
  int bIgnoreCasea; // [rsp+20h] [rbp-118h]
  LPVOID pv; // [rsp+40h] [rbp-F8h] BYREF
  struct Windows::System::Internal::Launch::IExtensionInfo *v42; // [rsp+48h] [rbp-F0h] BYREF
  HSTRING v43; // [rsp+50h] [rbp-E8h] BYREF
  HSTRING stringa; // [rsp+58h] [rbp-E0h]
  int v45[2]; // [rsp+60h] [rbp-D8h] BYREF
  void *ppv; // [rsp+68h] [rbp-D0h] BYREF
  HSTRING v47; // [rsp+70h] [rbp-C8h] BYREF
  int v48[2]; // [rsp+78h] [rbp-C0h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v49; // [rsp+80h] [rbp-B8h] BYREF
  struct Windows::System::Internal::Launch::IExtensionInfo *v50; // [rsp+88h] [rbp-B0h] BYREF
  _DWORD *v51; // [rsp+90h] [rbp-A8h] BYREF
  HSTRING v52; // [rsp+98h] [rbp-A0h]
  HSTRING v53; // [rsp+A0h] [rbp-98h]
  HSTRING v54; // [rsp+A8h] [rbp-90h] BYREF
  HSTRING v55; // [rsp+B0h] [rbp-88h] BYREF
  _DWORD v56[2]; // [rsp+B8h] [rbp-80h] BYREF
  HSTRING v57; // [rsp+C0h] [rbp-78h]
  HSTRING v58; // [rsp+C8h] [rbp-70h]
  HSTRING_HEADER v59; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  stringa = 0;
  *a5 = 0;
  *(_DWORD *)a4 = 0;
  v9 = 4;
  LODWORD(pv) = 4;
  ExtensionOrSchemeForUri = CTargetAppResolver::GetExtensionOrSchemeForUri(&v51);
  WindowsDeleteString(stringa);
  stringa = 0;
  stringa = *(HSTRING *)(ExtensionOrSchemeForUri + 8);
  *(_QWORD *)(ExtensionOrSchemeForUri + 8) = 0;
  v11 = *(_BYTE *)ExtensionOrSchemeForUri;
  WindowsDeleteString(v52);
  v42 = 0;
  v49 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v13 = TryCreateRuntimeUri(StringRawBuffer, &v49);
  v15 = retaddr;
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
  if ( v11 || *((_BYTE *)this + 144) || !LauncherMiscHelpers::IsHttpUrl(v49, v14) )
  {
    v17 = v42;
  }
  else
  {
    ExtensionInfoFromStateRepositoryForAppUriHandler = CTargetAppResolver::GetExtensionInfoFromStateRepositoryForAppUriHandler(
                                                         (CTargetAppResolver *)this,
                                                         string,
                                                         a3,
                                                         (enum CTargetAppResolver::ResolutionStatus *)&pv,
                                                         &v42);
    v15 = retaddr;
    if ( ExtensionInfoFromStateRepositoryForAppUriHandler < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
        (const char *)(unsigned int)ExtensionInfoFromStateRepositoryForAppUriHandler,
        bIgnoreCase);
    v17 = v42;
    v9 = (int)pv;
    if ( !v42 && (_DWORD)pv != 3 )
      goto LABEL_14;
    *((_DWORD *)this + 37) = 3;
  }
  if ( v17 )
    goto LABEL_17;
  if ( v9 == 3 )
    goto LABEL_23;
LABEL_14:
  ExtensionInfoFromStateRepository = CTargetAppResolver::GetExtensionInfoFromStateRepository(
                                       (CTargetAppResolver *)this,
                                       v11,
                                       stringa,
                                       a3,
                                       (enum CTargetAppResolver::ResolutionStatus *)&pv,
                                       &v42);
  if ( ExtensionInfoFromStateRepository < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
      (const char *)(unsigned int)ExtensionInfoFromStateRepository,
      bIgnoreCase);
  v15 = (wil::details::in1diag3 *)((unsigned int)(v11 != 0) + 1);
  *((_DWORD *)this + 37) = (_DWORD)v15;
  v9 = (int)pv;
  v17 = v42;
LABEL_17:
  if ( v17 )
  {
    v43 = 0;
    v19 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Launch::IExtensionInfo *, HSTRING *))(*(_QWORD *)v17 + 48LL);
    WindowsDeleteString(0);
    v43 = 0;
    v20 = v19(v17, &v43);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    HIDWORD(v51) = 0;
    LODWORD(v51) = *((_DWORD *)this + 11);
    v52 = this[6];
    v53 = this[7];
    pv = 0;
    v47 = (HSTRING)v42;
    ppv = v43;
    *(_QWORD *)v45 = this[9];
    v50 = (struct Windows::System::Internal::Launch::IExtensionInfo *)this[8];
    *(_QWORD *)v48 = &v51;
    v21 = Microsoft::WRL::Details::MakeAndInitialize<CModernTarget,ILauncherTarget,LAUNCH_PARAMETERS *,IUnknown *,Windows::Storage::Search::IStorageFileQueryResult *,HSTRING__ *,Windows::System::Internal::Launch::IExtensionInfo *,enum Windows::System::Private::PendingLaunchType &>(
            &pv,
            v48,
            &v50,
            v45);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
        (const char *)(unsigned int)v21,
        (int)&ppv);
    v22 = (struct ILauncherTarget *)pv;
    pv = 0;
    *a5 = v22;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    v23 = v43;
LABEL_42:
    WindowsDeleteString(v23);
    goto LABEL_43;
  }
LABEL_23:
  if ( (unsigned __int8)IsShellExecuteExWPresent(v15) )
  {
    if ( !v11 && !v42 )
    {
      v24 = WindowsGetStringRawBuffer(stringa, 0);
      if ( CompareStringOrdinal(v24, -1, L"ms-settings", -1, 1) == 2 )
      {
        v47 = 0;
        v25 = v49;
        v26 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v49 + 48LL);
        WindowsDeleteString(0);
        v47 = 0;
        v27 = v26(v25, &v47);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
            (const char *)(unsigned int)v27,
            bIgnoreCasea);
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v28 = WindowsGetStringRawBuffer(v47, 0);
        v29 = SHCreateItemFromParsingName(v28, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF5,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
            (const char *)(unsigned int)v29,
            bIgnoreCasea);
        *(_QWORD *)v45 = 0;
        v30 = ppv;
        v31 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v45);
        v32 = v31(v30, 0, &BHID_AssociationArray, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
            (const char *)(unsigned int)v32,
            (int)v45);
        v33 = 0;
        pv = 0;
        v34 = *(_QWORD *)v45;
        if ( *(_QWORD *)v45 )
        {
          v35 = *(int (__fastcall **)(__int64, __int64, _QWORD, LPVOID *))(**(_QWORD **)v45 + 24LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pv,
            0);
          if ( v35(v34, 458757, 0, &pv) >= 0 )
          {
            v9 = 1;
            v56[1] = 0;
            v56[0] = *((_DWORD *)this + 11);
            v57 = this[6];
            v58 = this[7];
            v43 = 0;
            v50 = v42;
            *(_QWORD *)v48 = pv;
            *(_QWORD *)v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v59, (const WCHAR **)v48)[1].Reserved.Reserved1;
            v54 = this[9];
            v55 = this[8];
            v51 = v56;
            v36 = Microsoft::WRL::Details::MakeAndInitialize<CModernTarget,ILauncherTarget,LAUNCH_PARAMETERS *,IUnknown *,Windows::Storage::Search::IStorageFileQueryResult *,HSTRING__ *,Windows::System::Internal::Launch::IExtensionInfo *,enum Windows::System::Private::PendingLaunchType &>(
                    &v43,
                    &v51,
                    &v55,
                    &v54);
            if ( v36 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xFF,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\targetappresolver.cpp",
                (const char *)(unsigned int)v36,
                (int)v48);
            v37 = (struct ILauncherTarget *)v43;
            v43 = 0;
            *a5 = v37;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          }
          v33 = pv;
        }
        if ( v33 )
          CoTaskMemFree(v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v23 = v47;
        goto LABEL_42;
      }
    }
  }
LABEL_43:
  *(_DWORD *)a4 = v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  WindowsDeleteString(stringa);
  return 0;
}

```

## disassembly

```asm
0x18007ec08  push    rbx
0x18007ec0a  push    rsi
0x18007ec0b  push    rdi
0x18007ec0c  push    r12
0x18007ec0e  push    r13
0x18007ec10  push    r14
0x18007ec12  push    r15
0x18007ec14  sub     rsp, 100h
0x18007ec1b  mov     rax, cs:__security_cookie
0x18007ec22  xor     rax, rsp
0x18007ec25  mov     [rsp+138h+var_48], rax
0x18007ec2d  mov     r13, r9
0x18007ec30  mov     r15, r8
0x18007ec33  mov     rbx, rdx
0x18007ec36  mov     rsi, rcx
0x18007ec39  mov     r12, [rsp+138h+arg_20]
0x18007ec41  xor     eax, eax
0x18007ec43  mov     [rsp+138h+string], rax
0x18007ec48  mov     [r12], rax
0x18007ec4c  mov     [r9], eax
0x18007ec4f  lea     r14d, [rax+4]
0x18007ec53  mov     dword ptr [rsp+138h+pv], r14d
0x18007ec58  lea     rcx, [rsp+138h+var_A8]
0x18007ec60  call    ?GetExtensionOrSchemeForUri@CTargetAppResolver@@SA?AV?$tuple@VHString@Wrappers@WRL@Microsoft@@_N@std@@PEAUHSTRING__@@@Z; CTargetAppResolver::GetExtensionOrSchemeForUri(HSTRING__ *)
0x18007ec65  mov     rdi, rax
0x18007ec68  mov     rcx, [rsp+138h+string]; string
0x18007ec6d  call    cs:__imp_WindowsDeleteString
0x18007ec73  mov     [rsp+138h+string], 0
0x18007ec7c  mov     rcx, [rdi+8]
0x18007ec80  mov     [rsp+138h+string], rcx
0x18007ec85  mov     qword ptr [rdi+8], 0
0x18007ec8d  mov     dil, [rdi]
0x18007ec90  mov     rcx, [rsp+138h+var_A0]; string
0x18007ec98  call    cs:__imp_WindowsDeleteString
0x18007ec9e  mov     [rsp+138h+var_F0], 0
0x18007eca7  mov     [rsp+138h+var_B8], 0
0x18007ecb3  xor     edx, edx; length
0x18007ecb5  mov     rcx, rbx; string
0x18007ecb8  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ecbe  lea     rdx, [rsp+138h+var_B8]; struct Windows::Foundation::IUriRuntimeClass **
0x18007ecc6  mov     rcx, rax; sourceString
0x18007ecc9  call    ?TryCreateRuntimeUri@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; TryCreateRuntimeUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)
0x18007ecce  mov     rcx, [rsp+138h]; this
0x18007ecd6  test    eax, eax
0x18007ecd8  jns     short loc_18007ECEE
0x18007ecda  mov     r9d, eax; char *
0x18007ecdd  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007ece4  mov     edx, 0CDh; void *
0x18007ece9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ecee  test    dil, dil
0x18007ecf1  jnz     short loc_18007ED6B
0x18007ecf3  cmp     [rsi+90h], dil
0x18007ecfa  jnz     short loc_18007ED6B
0x18007ecfc  mov     rcx, [rsp+138h+var_B8]; this
0x18007ed04  call    ?IsHttpUrl@LauncherMiscHelpers@@YA_NPEAUIUriRuntimeClass@Foundation@Windows@@@Z; LauncherMiscHelpers::IsHttpUrl(Windows::Foundation::IUriRuntimeClass *)
0x18007ed09  test    al, al
0x18007ed0b  jz      short loc_18007ED6B
0x18007ed0d  lea     rax, [rsp+138h+var_F0]
0x18007ed12  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x18007ed17  lea     r9, [rsp+138h+pv]; enum CTargetAppResolver::ResolutionStatus *
0x18007ed1c  mov     r8, r15; HSTRING
0x18007ed1f  mov     rdx, rbx; HSTRING
0x18007ed22  mov     rcx, rsi; this
0x18007ed25  call    ?GetExtensionInfoFromStateRepositoryForAppUriHandler@CTargetAppResolver@@AEAAJPEAUHSTRING__@@0PEAW4ResolutionStatus@1@PEAPEAUIExtensionInfo@Launch@Internal@System@Windows@@@Z; CTargetAppResolver::GetExtensionInfoFromStateRepositoryForAppUriHandler(HSTRING__ *,HSTRING__ *,CTargetAppResolver::ResolutionStatus *,Windows::System::Internal::Launch::IExtensionInfo * *)
0x18007ed2a  mov     rcx, [rsp+138h]; this
0x18007ed32  test    eax, eax
0x18007ed34  jns     short loc_18007ED4A
0x18007ed36  mov     r9d, eax; char *
0x18007ed39  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007ed40  mov     edx, 0D1h; void *
0x18007ed45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ed4a  mov     rbx, [rsp+138h+var_F0]
0x18007ed4f  mov     r14d, dword ptr [rsp+138h+pv]
0x18007ed54  test    rbx, rbx
0x18007ed57  jnz     short loc_18007ED5F
0x18007ed59  cmp     r14d, 3
0x18007ed5d  jnz     short loc_18007ED88
0x18007ed5f  mov     dword ptr [rsi+94h], 3
0x18007ed69  jmp     short loc_18007ED70
0x18007ed6b  mov     rbx, [rsp+138h+var_F0]
0x18007ed70  test    rbx, rbx
0x18007ed73  jz      short loc_18007ED7E
0x18007ed75  lea     r15, [rsi+94h]
0x18007ed7c  jmp     short loc_18007EDEE
0x18007ed7e  cmp     r14d, 3
0x18007ed82  jz      loc_18007EF26
0x18007ed88  lea     rax, [rsp+138h+var_F0]
0x18007ed8d  mov     [rsp+138h+var_110], rax; struct Windows::System::Internal::Launch::IExtensionInfo **
0x18007ed92  lea     rax, [rsp+138h+pv]
0x18007ed97  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x18007ed9c  mov     r9, r15; HSTRING
0x18007ed9f  mov     r8, [rsp+138h+string]; HSTRING
0x18007eda4  mov     dl, dil; bool
0x18007eda7  mov     rcx, rsi; this
0x18007edaa  call    ?GetExtensionInfoFromStateRepository@CTargetAppResolver@@AEAAJ_NPEAUHSTRING__@@1PEAW4ResolutionStatus@1@PEAPEAUIExtensionInfo@Launch@Internal@System@Windows@@@Z; CTargetAppResolver::GetExtensionInfoFromStateRepository(bool,HSTRING__ *,HSTRING__ *,CTargetAppResolver::ResolutionStatus *,Windows::System::Internal::Launch::IExtensionInfo * *)
0x18007edaf  mov     rcx, [rsp+138h]; this
0x18007edb7  test    eax, eax
0x18007edb9  jns     short loc_18007EDCF
0x18007edbb  mov     r9d, eax; char *
0x18007edbe  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007edc5  mov     edx, 0DBh; void *
0x18007edca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007edcf  lea     r15, [rsi+94h]
0x18007edd6  mov     al, dil
0x18007edd9  neg     al
0x18007eddb  sbb     ecx, ecx
0x18007eddd  neg     ecx
0x18007eddf  inc     ecx
0x18007ede1  mov     [r15], ecx
0x18007ede4  mov     r14d, dword ptr [rsp+138h+pv]
0x18007ede9  mov     rbx, [rsp+138h+var_F0]
0x18007edee  test    rbx, rbx
0x18007edf1  jz      loc_18007EF26
0x18007edf7  mov     [rsp+138h+var_E8], 0
0x18007ee00  mov     rax, [rbx]
0x18007ee03  mov     rdi, [rax+30h]
0x18007ee07  xor     ecx, ecx; string
0x18007ee09  call    cs:__imp_WindowsDeleteString
0x18007ee0f  mov     [rsp+138h+var_E8], 0
0x18007ee18  lea     rdx, [rsp+138h+var_E8]
0x18007ee1d  mov     rcx, rbx
0x18007ee20  mov     rax, rdi
0x18007ee23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee28  mov     rcx, [rsp+138h]; this
0x18007ee30  xor     ebx, ebx
0x18007ee32  test    eax, eax
0x18007ee34  jns     short loc_18007EE4A
0x18007ee36  mov     r9d, eax; char *
0x18007ee39  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007ee40  mov     edx, 0E6h; void *
0x18007ee45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ee4a  mov     dword ptr [rsp+138h+var_A8+4], ebx
0x18007ee51  mov     eax, [rsi+2Ch]
0x18007ee54  mov     dword ptr [rsp+138h+var_A8], eax
0x18007ee5b  mov     rax, [rsi+30h]
0x18007ee5f  mov     [rsp+138h+var_A0], rax
0x18007ee67  mov     rax, [rsi+38h]
0x18007ee6b  mov     [rsp+138h+var_98], rax
0x18007ee73  mov     [rsp+138h+pv], rbx
0x18007ee78  mov     rax, [rsp+138h+var_F0]
0x18007ee7d  mov     [rsp+138h+var_C8], rax
0x18007ee82  mov     rax, [rsp+138h+var_E8]
0x18007ee87  mov     [rsp+138h+ppv], rax
0x18007ee8c  mov     rax, [rsi+48h]
0x18007ee90  mov     qword ptr [rsp+138h+var_D8], rax
0x18007ee95  mov     rax, [rsi+40h]
0x18007ee99  mov     [rsp+138h+var_B0], rax
0x18007eea1  lea     rax, [rsp+138h+var_A8]
0x18007eea9  mov     qword ptr [rsp+138h+var_C0], rax
0x18007eeae  mov     [rsp+138h+var_108], r15
0x18007eeb3  lea     rax, [rsp+138h+var_C8]
0x18007eeb8  mov     [rsp+138h+var_110], rax
0x18007eebd  lea     rax, [rsp+138h+ppv]
0x18007eec2  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x18007eec7  lea     r9, [rsp+138h+var_D8]
0x18007eecc  lea     r8, [rsp+138h+var_B0]
0x18007eed4  lea     rdx, [rsp+138h+var_C0]
0x18007eed9  lea     rcx, [rsp+138h+pv]
0x18007eede  call    ??$MakeAndInitialize@VCModernTarget@@UILauncherTarget@@PEAULAUNCH_PARAMETERS@@PEAUIUnknown@@PEAUIStorageFileQueryResult@Search@Storage@Windows@@PEAUHSTRING__@@PEAUIExtensionInfo@Launch@Internal@System@8@AEAW4PendingLaunchType@Private@System@8@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UILauncherTarget@@@WRL@Microsoft@@@012@$$QEAPEAULAUNCH_PARAMETERS@@$$QEAPEAUIUnknown@@$$QEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@$$QEAPEAUHSTRING__@@$$QEAPEAUIExtensionInfo@Launch@Internal@System@9@AEAW4PendingLaunchType@Private@System@9@@Z; Microsoft::WRL::Details::MakeAndInitialize<CModernTarget,ILauncherTarget,LAUNCH_PARAMETERS *,IUnknown *,Windows::Storage::Search::IStorageFileQueryResult *,HSTRING__ *,Windows::System::Internal::Launch::IExtensionInfo *,Windows::System::Private::PendingLaunchType &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILauncherTarget>>,LAUNCH_PARAMETERS * &&,IUnknown * &&,Windows::Storage::Search::IStorageFileQueryResult * &&,HSTRING__ * &&,Windows::System::Internal::Launch::IExtensionInfo * &&,Windows::System::Private::PendingLaunchType &)
0x18007eee3  mov     rcx, [rsp+138h]; this
0x18007eeeb  test    eax, eax
0x18007eeed  jns     short loc_18007EF03
0x18007eeef  mov     r9d, eax; char *
0x18007eef2  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007eef9  mov     edx, 0E9h; void *
0x18007eefe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ef03  mov     rax, [rsp+138h+pv]
0x18007ef08  mov     [rsp+138h+pv], rbx
0x18007ef0d  mov     [r12], rax
0x18007ef11  lea     rcx, [rsp+138h+pv]
0x18007ef16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ef1b  nop
0x18007ef1c  mov     rcx, [rsp+138h+var_E8]
0x18007ef21  jmp     loc_18007F205
0x18007ef26  call    IsShellExecuteExWPresent
0x18007ef2b  xor     r15d, r15d
0x18007ef2e  test    al, al
0x18007ef30  jz      loc_18007F20B
0x18007ef36  test    dil, dil
0x18007ef39  jnz     loc_18007F20B
0x18007ef3f  cmp     [rsp+138h+var_F0], r15
0x18007ef44  jnz     loc_18007F20B
0x18007ef4a  xor     edx, edx; length
0x18007ef4c  mov     rcx, [rsp+138h+string]; string
0x18007ef51  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ef57  mov     [rsp+138h+bIgnoreCase], 1; int
0x18007ef5f  or      edx, 0FFFFFFFFh; cchCount1
0x18007ef62  mov     r9d, edx; cchCount2
0x18007ef65  lea     r8, aMsSettings; "ms-settings"
0x18007ef6c  mov     rcx, rax; lpString1
0x18007ef6f  call    cs:__imp_CompareStringOrdinal
0x18007ef75  cmp     eax, 2
0x18007ef78  jnz     loc_18007F20B
0x18007ef7e  mov     [rsp+138h+var_C8], r15
0x18007ef83  mov     rdi, [rsp+138h+var_B8]
0x18007ef8b  mov     rax, [rdi]
0x18007ef8e  mov     rbx, [rax+30h]
0x18007ef92  xor     ecx, ecx; string
0x18007ef94  call    cs:__imp_WindowsDeleteString
0x18007ef9a  mov     [rsp+138h+var_C8], r15
0x18007ef9f  lea     rdx, [rsp+138h+var_C8]
0x18007efa4  mov     rcx, rdi
0x18007efa7  mov     rax, rbx
0x18007efaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007efaf  mov     rcx, [rsp+138h]; this
0x18007efb7  test    eax, eax
0x18007efb9  jns     short loc_18007EFCF
0x18007efbb  mov     r9d, eax; char *
0x18007efbe  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007efc5  mov     edx, 0F3h; void *
0x18007efca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007efcf  mov     [rsp+138h+ppv], r15
0x18007efd4  lea     rcx, [rsp+138h+ppv]
0x18007efd9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007efde  xor     edx, edx; length
0x18007efe0  mov     rcx, [rsp+138h+var_C8]; string
0x18007efe5  call    cs:__imp_WindowsGetStringRawBuffer
0x18007efeb  lea     r9, [rsp+138h+ppv]; ppv
0x18007eff0  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18007eff7  xor     edx, edx; pbc
0x18007eff9  mov     rcx, rax; pszPath
0x18007effc  call    cs:__imp_SHCreateItemFromParsingName
0x18007f002  mov     rcx, [rsp+138h]; this
0x18007f00a  test    eax, eax
0x18007f00c  jns     short loc_18007F022
0x18007f00e  mov     r9d, eax; char *
0x18007f011  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007f018  mov     edx, 0F5h; void *
0x18007f01d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007f022  mov     qword ptr [rsp+138h+var_D8], r15
0x18007f027  mov     rdi, [rsp+138h+ppv]
0x18007f02c  mov     rax, [rdi]
0x18007f02f  mov     rbx, [rax+18h]
0x18007f033  lea     rcx, [rsp+138h+var_D8]
0x18007f038  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f03d  lea     rax, [rsp+138h+var_D8]
0x18007f042  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x18007f047  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x18007f04e  lea     r8, BHID_AssociationArray
0x18007f055  xor     edx, edx
0x18007f057  mov     rcx, rdi
0x18007f05a  mov     rax, rbx
0x18007f05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f062  mov     rcx, [rsp+138h]; this
0x18007f06a  test    eax, eax
0x18007f06c  jns     short loc_18007F082
0x18007f06e  mov     r9d, eax; char *
0x18007f071  lea     r8, aOnecoreuapShel_35; "onecoreuap\\shell\\windows.system.launc"...
0x18007f078  mov     edx, 0F7h; void *
0x18007f07d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007f082  mov     rcx, r15
0x18007f085  mov     [rsp+138h+pv], rcx
0x18007f08a  mov     rbx, qword ptr [rsp+138h+var_D8]
0x18007f08f  test    rbx, rbx
0x18007f092  jz      loc_18007F1DE
0x18007f098  mov     rax, [rbx]
0x18007f09b  mov     rdi, [rax+18h]
0x18007f09f  xor     edx, edx
0x18007f0a1  lea     rcx, [rsp+138h+pv]
0x18007f0a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007f0ab  lea     r9, [rsp+138h+pv]
0x18007f0b0  xor     r8d, r8d
0x18007f0b3  mov     edx, 70005h
0x18007f0b8  mov     rcx, rbx
0x18007f0bb  mov     rax, rdi
0x18007f0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0c3  test    eax, eax
0x18007f0c5  js      loc_18007F1D9
0x18007f0cb  mov     r14d, 1
0x18007f0d1  mov     [rsp+138h+var_7C], r15d
0x18007f0d9  mov     eax, [rsi+2Ch]
0x18007f0dc  mov     [rsp+138h+var_80], eax
0x18007f0e3  mov     rax, [rsi+30h]
0x18007f0e7  mov     [rsp+138h+var_78], rax
0x18007f0ef  mov     rax, [rsi+38h]
0x18007f0f3  mov     [rsp+138h+var_70], rax
0x18007f0fb  mov     [rsp+138h+var_E8], r15
0x18007f100  mov     rax, [rsp+138h+var_F0]
0x18007f105  mov     [rsp+138h+var_B0], rax
0x18007f10d  mov     rax, [rsp+138h+pv]
0x18007f112  mov     qword ptr [rsp+138h+var_C0], rax
0x18007f117  lea     rdx, [rsp+138h+var_C0]
0x18007f11c  lea     rcx, [rsp+138h+var_68]
0x18007f124  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18007f129  nop
0x18007f12a  mov     rax, [rax+18h]
0x18007f12e  mov     qword ptr [rsp+138h+var_C0], rax
0x18007f133  mov     rax, [rsi+48h]
0x18007f137  mov     [rsp+138h+var_90], rax
0x18007f13f  mov     rax, [rsi+40h]
0x18007f143  mov     [rsp+138h+var_88], rax
0x18007f14b  lea     rax, [rsp+138h+var_80]
0x18007f153  mov     [rsp+138h+var_A8], rax
0x18007f15b  lea     rax, [rsi+94h]
0x18007f162  mov     [rsp+138h+var_108], rax
0x18007f167  lea     rax, [rsp+138h+var_B0]
0x18007f16f  mov     [rsp+138h+var_110], rax
0x18007f174  lea     rax, [rsp+138h+var_C0]
0x18007f179  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x18007f17e  lea     r9, [rsp+138h+var_90]
  ... truncated ...
```
