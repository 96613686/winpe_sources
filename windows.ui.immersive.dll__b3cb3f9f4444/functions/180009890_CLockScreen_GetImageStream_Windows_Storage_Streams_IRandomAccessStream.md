# CLockScreen::GetImageStream(Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180009890`
- end: `0x180009f3b`
- name: `?GetImageStream@CLockScreen@@UEAAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `1707`
- prototype: `__int64 __fastcall(CLockScreen *__hidden this, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009890`
- `0x18000a490`
- `0x18000af00`
- `0x18000b3b0`
- `0x18000b700`
- `0x18000c1b8`
- `0x18000da90`
- `0x180026440`
- `0x1800343ec`
- `0x180034d38`
- `0x180035c94`
- `0x18003729c`
- `0x18003c324`
- `0x18003cd00`
- `0x18003fd78`
- `0x18003fe3c`
- `0x18003ff34`
- `0x180042a08`
- `0x180042b10`
- `0x1800464f8`
- `0x180046c00`
- `0x180048c30`
- `0x18004ab6c`
- `0x18004ca2c`
- `0x180054130`
- `0x1800b1c70`
- `0x1800b5dac`
- `0x1800b8fb4`
- `0x1800c0768`
- `0x1800dce10`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dda`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800099c2`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009ac6`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009c19`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800099c2`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009ac6`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009c19`
- `SHELL32!__imp_ILFree` at `0x180009d64`
- `SHELL32!__imp_ILFree` at `0x180009d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009daa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009daa`

## string_xrefs

- `0x180009bbf`: `LandscapeAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CLockScreen::GetImageStream(void **this, struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  bool v4; // dl
  int updated; // ebx
  int v6; // eax
  char v7; // si
  unsigned __int16 *v8; // rbx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  int Stream; // eax
  __int64 v14; // rdx
  PCWSTR v15; // rbx
  int v16; // eax
  int v17; // r9d
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  unsigned __int16 v22; // r14
  HANDLE v23; // rdi
  const struct _GUID *v24; // rdx
  int v25; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v26; // rax
  int v27; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v28; // rax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned int *v32; // [rsp+28h] [rbp-D8h]
  struct Windows::Storage::Streams::IRandomAccessStream *v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v34; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  void *v39; // [rsp+60h] [rbp-A0h] BYREF
  void *v40; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hMutex; // [rsp+70h] [rbp-90h] BYREF
  char v42; // [rsp+78h] [rbp-88h]
  _BYTE v43[1624]; // [rsp+80h] [rbp-80h] BYREF
  LPITEMIDLIST pidl; // [rsp+6D8h] [rbp+5D8h]
  LPVOID v45; // [rsp+6E0h] [rbp+5E0h]
  _BYTE v46[1664]; // [rsp+700h] [rbp+600h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+DC8h] [rbp+CC8h]

  if ( CLockScreen::s_IsSystemProcess() )
  {
    updated = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1419,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)0x8000FFFFLL,
      v30);
    return (unsigned int)updated;
  }
  CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(
    (CLockScreenHistory::CSynchronizedOperation *)&hMutex,
    v4);
  *a2 = 0;
  if ( CLockScreen::_s_IsAppContainerProcess() )
  {
    v6 = CheckCallerCapabilityAndReportError(WinCapabilityPicturesLibrarySid, 0x9805u);
    updated = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141F,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v6,
        v30);
LABEL_70:
      CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)&hMutex);
      return (unsigned int)updated;
    }
  }
  v34 = 0;
  v7 = 0;
  v33 = 0;
  if ( CLockScreen::_s_IsSpecificLockScreenLogonImageForced(&v34) )
  {
    v8 = v34;
    if ( !v34 )
    {
      updated = -2147467261;
      v9 = 2147500035LL;
      v10 = 5161;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)v9,
        v30);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v34);
      goto LABEL_70;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v11 = CreateRandomAccessStreamOnFile(v8, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v33);
    updated = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v10 = 5162;
      goto LABEL_9;
    }
LABEL_61:
    v39 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v25 = CloneToInMemoryStream(v33, v24, &v39);
    updated = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1453,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v25,
        v30);
LABEL_63:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_10;
    }
    v26 = (struct Windows::Storage::Streams::IRandomAccessStream *)v39;
    if ( v7 )
    {
      pv = 0;
      v40 = v39;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      v27 = Microsoft::WRL::Details::MakeAndInitialize<CCreativeInMemoryStream,Windows::Storage::Streams::IRandomAccessStream,Windows::Storage::Streams::IRandomAccessStream *>(
              &pv,
              &v40);
      updated = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145C,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v27,
          v30);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        goto LABEL_63;
      }
      v28 = (struct Windows::Storage::Streams::IRandomAccessStream *)pv;
      pv = 0;
      *a2 = v28;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    }
    else
    {
      v39 = 0;
      *a2 = v26;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v34);
    updated = 0;
    goto LABEL_70;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  if ( CLockScreen::_s_IsSpotlightEnabled(0) )
  {
    pszPath = 0;
    v36 = 0;
    v37 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v36 = -1;
    v37 = -1;
    v12 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(0, 0, (DWORD *)&pszPath, 0, 0);
    if ( v12 >= 0 )
    {
      v15 = pszPath;
      if ( pszPath && *pszPath )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        v16 = CreateRandomAccessStreamOnFile(v15, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v33);
        updated = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1432,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)v16,
            v30);
          goto LABEL_23;
        }
        v7 = 1;
        goto LABEL_30;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x142F,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v12,
        v30);
    }
    CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v46);
    Stream = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 15));
    updated = Stream;
    if ( Stream < 0 )
    {
      v14 = 5176;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Stream,
        v30);
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v46);
      goto LABEL_23;
    }
    Stream = CLockScreenHistory::_InitAndEnsureGPEntry(
               (CLockScreenHistory *)(this + 15),
               (struct CLockScreenHistory::CLockScreenHistoryEntry *)v46,
               0x5Au);
    updated = Stream;
    if ( Stream < 0 )
    {
      v14 = 5177;
      goto LABEL_18;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Stream = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
               (CLockScreenHistory::CLockScreenHistoryEntry *)v46,
               &v33);
    updated = Stream;
    if ( Stream < 0 )
    {
      v14 = 5178;
      goto LABEL_18;
    }
    v7 = 1;
    CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v46);
LABEL_30:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    goto LABEL_61;
  }
  if ( CLockScreen::_s_IsSpotlight() && !CLockScreen::_s_IsSpotlightExpired() )
  {
    pszPath = 0;
    v36 = 0;
    v37 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v36 = -1;
    v37 = -1;
    v18 = SHRegAllocData(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
            L"LandscapeAssetPath",
            v17,
            (void **)&pszPath,
            v32);
    updated = v18;
    if ( v18 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v18 = CreateRandomAccessStreamOnFile(pszPath, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v33);
      updated = v18;
      if ( v18 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
        v7 = 1;
        goto LABEL_61;
      }
      v19 = 5187;
    }
    else
    {
      v19 = 5186;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)v18,
      v30);
LABEL_23:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    goto LABEL_10;
  }
  CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v43);
  v20 = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 15));
  updated = v20;
  if ( v20 < 0 )
  {
    v21 = 5193;
    goto LABEL_41;
  }
  pv = 0;
  if ( (int)CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(this[15], 1, (unsigned __int16 **)&pv) < 0 )
  {
    v22 = String2[0];
  }
  else
  {
    v22 = *(_WORD *)pv;
    CoTaskMemFree(pv);
  }
  updated = CLockScreenHistory::CLockScreenHistoryEntry::Init((CLockScreenHistory::CLockScreenHistoryEntry *)v43, v22);
  if ( updated >= 0 && v22 == 80 )
  {
    pszPath = 0;
    v36 = 0;
    v37 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v36 = -1;
    v37 = -1;
    updated = LockScreenPathFromPolicy((unsigned __int16 **)&pszPath);
    if ( updated >= 0 )
      updated = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(this + 15), pszPath);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  }
  if ( updated >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v20 = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
            (CLockScreenHistory::CLockScreenHistoryEntry *)v43,
            &v33);
    updated = v20;
    if ( v20 >= 0 )
    {
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v43);
      goto LABEL_61;
    }
    v21 = 5197;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)v20,
      v30);
    CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v43);
    goto LABEL_10;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x685,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)(unsigned int)updated,
    v30);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x144C,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)(unsigned int)updated,
    v31);
  ILFree(pidl);
  CoTaskMemFree(v45);
  if ( v34 )
    CoTaskMemFree(v34);
  v23 = hMutex;
  if ( hMutex )
  {
    if ( v42 )
      ReleaseMutex(hMutex);
    CloseHandle(v23);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180009890  mov     [rsp-8+arg_10], rbx
0x180009895  push    rbp
0x180009896  push    rsi
0x180009897  push    rdi
0x180009898  push    r12
0x18000989a  push    r13
0x18000989c  push    r14
0x18000989e  push    r15
0x1800098a0  lea     rbp, [rsp-0C90h]
0x1800098a8  sub     rsp, 0D90h
0x1800098af  mov     rax, cs:__security_cookie
0x1800098b6  xor     rax, rsp
0x1800098b9  mov     [rbp+0CC0h+var_40], rax
0x1800098c0  mov     r12, rdx
0x1800098c3  mov     r15, rcx
0x1800098c6  call    ?s_IsSystemProcess@CLockScreen@@SA_NXZ; CLockScreen::s_IsSystemProcess(void)
0x1800098cb  xor     r13d, r13d
0x1800098ce  test    al, al
0x1800098d0  jz      short loc_1800098F7
0x1800098d2  mov     rcx, [rbp+0CC8h]; this
0x1800098d9  mov     ebx, 8000FFFFh
0x1800098de  mov     r9d, ebx; char *
0x1800098e1  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800098e8  mov     edx, 1419h; void *
0x1800098ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098f2  jmp     loc_180009F0E
0x1800098f7  lea     rcx, [rsp+0DC0h+hMutex]; this
0x1800098fc  call    ??0CSynchronizedOperation@CLockScreenHistory@@QEAA@_N@Z; CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(bool)
0x180009901  nop
0x180009902  mov     [r12], r13
0x180009906  call    ?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ; CLockScreen::_s_IsAppContainerProcess(void)
0x18000990b  test    al, al
0x18000990d  jz      short loc_180009944
0x18000990f  mov     edx, 9805h; unsigned int
0x180009914  mov     ecx, 58h ; 'X'; enum WELL_KNOWN_SID_TYPE
0x180009919  call    ?CheckCallerCapabilityAndReportError@@YAJW4WELL_KNOWN_SID_TYPE@@IZZ; CheckCallerCapabilityAndReportError(WELL_KNOWN_SID_TYPE,uint,...)
0x18000991e  mov     ebx, eax
0x180009920  test    eax, eax
0x180009922  jns     short loc_180009944
0x180009924  mov     rcx, [rbp+0CC8h]; this
0x18000992b  mov     r9d, eax; char *
0x18000992e  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180009935  mov     edx, 141Fh; void *
0x18000993a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000993f  jmp     loc_180009F04
0x180009944  mov     [rsp+0DC0h+var_D88], r13
0x180009949  lea     rcx, [rsp+0DC0h+var_D88]; unsigned __int16 **
0x18000994e  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x180009953  mov     sil, r13b
0x180009956  mov     [rsp+0DC0h+var_D90], r13
0x18000995b  lea     rdi, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180009962  test    al, al
0x180009964  jz      short loc_1800099E2
0x180009966  mov     rbx, [rsp+0DC0h+var_D88]
0x18000996b  test    rbx, rbx
0x18000996e  jnz     short loc_1800099A7
0x180009970  mov     ebx, 80004003h
0x180009975  mov     r9d, ebx; char *
0x180009978  mov     edx, 1429h; void *
0x18000997d  mov     r8, rdi; unsigned int
0x180009980  mov     rcx, [rbp+0CC8h]; this
0x180009987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000998c  nop
0x18000998d  lea     rcx, [rsp+0DC0h+var_D90]
0x180009992  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009997  nop
0x180009998  lea     rcx, [rsp+0DC0h+var_D88]
0x18000999d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800099a2  jmp     loc_180009F04
0x1800099a7  lea     rcx, [rsp+0DC0h+var_D90]
0x1800099ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800099b1  lea     r9, [rsp+0DC0h+var_D90]
0x1800099b6  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800099bd  xor     edx, edx
0x1800099bf  mov     rcx, rbx
0x1800099c2  call    cs:__imp_CreateRandomAccessStreamOnFile
0x1800099c9  nop     dword ptr [rax+rax+00h]
0x1800099ce  mov     ebx, eax
0x1800099d0  test    eax, eax
0x1800099d2  jns     loc_180009E1D
0x1800099d8  mov     r9d, eax
0x1800099db  mov     edx, 142Ah
0x1800099e0  jmp     short loc_18000997D
0x1800099e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x1800099e9  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800099ee  xor     ecx, ecx; this
0x1800099f0  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x1800099f5  test    al, al
0x1800099f7  jz      loc_180009B74
0x1800099fd  mov     [rsp+0DC0h+pszPath], r13
0x180009a02  mov     [rsp+0DC0h+var_D78], r13
0x180009a07  mov     [rsp+0DC0h+var_D70], r13
0x180009a0c  lea     rcx, [rsp+0DC0h+pszPath]
0x180009a11  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009a16  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a1a  mov     [rsp+0DC0h+var_D78], rax
0x180009a1f  mov     [rsp+0DC0h+var_D70], rax
0x180009a24  mov     [rsp+0DC0h+var_DA0], r13; int
0x180009a29  xor     r9d, r9d; unsigned __int16 **
0x180009a2c  lea     r8, [rsp+0DC0h+pszPath]; unsigned __int16 **
0x180009a31  xor     edx, edx; unsigned __int16 *
0x180009a33  xor     ecx, ecx; this
0x180009a35  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180009a3a  mov     rcx, [rbp+0CC8h]; this
0x180009a41  test    eax, eax
0x180009a43  jns     short loc_180009A9B
0x180009a45  mov     r9d, eax; char *
0x180009a48  mov     r8, rdi; unsigned int
0x180009a4b  mov     edx, 142Fh; void *
0x180009a50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009a55  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009a5c  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x180009a61  nop
0x180009a62  lea     rcx, [r15+78h]; this
0x180009a66  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180009a6b  mov     ebx, eax
0x180009a6d  test    eax, eax
0x180009a6f  jns     loc_180009B04
0x180009a75  mov     edx, 1438h; void *
0x180009a7a  mov     rcx, [rbp+0CC8h]; this
0x180009a81  mov     r9d, eax; char *
0x180009a84  mov     r8, rdi; unsigned int
0x180009a87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a8c  nop
0x180009a8d  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009a94  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180009a99  jmp     short loc_180009AF0
0x180009a9b  mov     rbx, [rsp+0DC0h+pszPath]
0x180009aa0  test    rbx, rbx
0x180009aa3  jz      short loc_180009A55
0x180009aa5  cmp     [rbx], r13w
0x180009aa9  jz      short loc_180009A55
0x180009aab  lea     rcx, [rsp+0DC0h+var_D90]
0x180009ab0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009ab5  lea     r9, [rsp+0DC0h+var_D90]
0x180009aba  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180009ac1  xor     edx, edx
0x180009ac3  mov     rcx, rbx
0x180009ac6  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180009acd  nop     dword ptr [rax+rax+00h]
0x180009ad2  mov     ebx, eax
0x180009ad4  test    eax, eax
0x180009ad6  jns     short loc_180009AFF
0x180009ad8  mov     rcx, [rbp+0CC8h]; this
0x180009adf  mov     r9d, eax; char *
0x180009ae2  mov     r8, rdi; unsigned int
0x180009ae5  mov     edx, 1432h; void *
0x180009aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009aef  nop
0x180009af0  lea     rcx, [rsp+0DC0h+pszPath]
0x180009af5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009afa  jmp     loc_18000998D
0x180009aff  mov     sil, 1
0x180009b02  jmp     short loc_180009B65
0x180009b04  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x180009b0a  lea     rdx, [rbp+0CC0h+var_6C0]; struct CLockScreenHistory::CLockScreenHistoryEntry *
0x180009b11  lea     rcx, [r15+78h]; this
0x180009b15  call    ?_InitAndEnsureGPEntry@CLockScreenHistory@@IEAAJPEAVCLockScreenHistoryEntry@1@G@Z; CLockScreenHistory::_InitAndEnsureGPEntry(CLockScreenHistory::CLockScreenHistoryEntry *,ushort)
0x180009b1a  mov     ebx, eax
0x180009b1c  test    eax, eax
0x180009b1e  jns     short loc_180009B2A
0x180009b20  mov     edx, 1439h
0x180009b25  jmp     loc_180009A7A
0x180009b2a  lea     rcx, [rsp+0DC0h+var_D90]
0x180009b2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009b34  lea     rdx, [rsp+0DC0h+var_D90]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180009b39  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009b40  call    ?GetStream@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetStream(Windows::Storage::Streams::IRandomAccessStream * *)
0x180009b45  mov     ebx, eax
0x180009b47  test    eax, eax
0x180009b49  jns     short loc_180009B55
0x180009b4b  mov     edx, 143Ah
0x180009b50  jmp     loc_180009A7A
0x180009b55  mov     sil, 1
0x180009b58  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009b5f  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180009b64  nop
0x180009b65  lea     rcx, [rsp+0DC0h+pszPath]
0x180009b6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009b6f  jmp     loc_180009E1D
0x180009b74  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x180009b79  test    al, al
0x180009b7b  jz      loc_180009C44
0x180009b81  call    ?_s_IsSpotlightExpired@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlightExpired(void)
0x180009b86  test    al, al
0x180009b88  jnz     loc_180009C44
0x180009b8e  mov     [rsp+0DC0h+pszPath], r13
0x180009b93  mov     [rsp+0DC0h+var_D78], r13
0x180009b98  mov     [rsp+0DC0h+var_D70], r13
0x180009b9d  lea     rcx, [rsp+0DC0h+pszPath]
0x180009ba2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009ba7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009bab  mov     [rsp+0DC0h+var_D78], rax
0x180009bb0  mov     [rsp+0DC0h+var_D70], rax
0x180009bb5  lea     rax, [rsp+0DC0h+pszPath]
0x180009bba  mov     [rsp+0DC0h+var_DA0], rax; int
0x180009bbf  lea     r8, ?c_landscapeAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LandscapeAssetPath"
0x180009bc6  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009bcd  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180009bd4  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180009bd9  mov     ebx, eax
0x180009bdb  test    eax, eax
0x180009bdd  jns     short loc_180009BFC
0x180009bdf  mov     edx, 1442h; void *
0x180009be4  mov     r8, rdi; unsigned int
0x180009be7  mov     r9d, eax; char *
0x180009bea  mov     rcx, [rbp+0CC8h]; this
0x180009bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bf6  nop
0x180009bf7  jmp     loc_180009AF0
0x180009bfc  lea     rcx, [rsp+0DC0h+var_D90]
0x180009c01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009c06  lea     r9, [rsp+0DC0h+var_D90]
0x180009c0b  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180009c12  xor     edx, edx
0x180009c14  mov     rcx, [rsp+0DC0h+pszPath]
0x180009c19  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180009c20  nop     dword ptr [rax+rax+00h]
0x180009c25  mov     ebx, eax
0x180009c27  test    eax, eax
0x180009c29  jns     short loc_180009C32
0x180009c2b  mov     edx, 1443h
0x180009c30  jmp     short loc_180009BE4
0x180009c32  lea     rcx, [rsp+0DC0h+pszPath]
0x180009c37  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009c3c  mov     sil, 1
0x180009c3f  jmp     loc_180009E1D
0x180009c44  lea     rcx, [rbp+0CC0h+var_D40]; this
0x180009c48  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x180009c4d  nop
0x180009c4e  lea     rcx, [r15+78h]; this
0x180009c52  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180009c57  mov     ebx, eax
0x180009c59  test    eax, eax
0x180009c5b  jns     short loc_180009C83
0x180009c5d  mov     edx, 1449h; void *
0x180009c62  mov     r8, rdi; unsigned int
0x180009c65  mov     r9d, eax; char *
0x180009c68  mov     rcx, [rbp+0CC8h]; this
0x180009c6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c74  nop
0x180009c75  lea     rcx, [rbp+0CC0h+var_D40]; this
0x180009c79  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180009c7e  jmp     loc_18000998D
0x180009c83  mov     [rsp+0DC0h+pv], r13
0x180009c88  lea     r8, [rsp+0DC0h+pv]; unsigned __int16 **
0x180009c8d  mov     dl, 1; bool
0x180009c8f  mov     rcx, [r15+78h]; void *
0x180009c93  call    ?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z; CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)
0x180009c98  test    eax, eax
0x180009c9a  js      short loc_180009CB3
0x180009c9c  mov     rcx, [rsp+0DC0h+pv]; pv
0x180009ca1  movzx   r14d, word ptr [rcx]
0x180009ca5  call    cs:__imp_CoTaskMemFree
0x180009cac  nop     dword ptr [rax+rax+00h]
0x180009cb1  jmp     short loc_180009CBB
0x180009cb3  movzx   r14d, word ptr cs:String2; "ZYXWVU"
0x180009cbb  movzx   edx, r14w; unsigned __int16
0x180009cbf  lea     rcx, [rbp+0CC0h+var_D40]; this
0x180009cc3  call    ?Init@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJG@Z; CLockScreenHistory::CLockScreenHistoryEntry::Init(ushort)
0x180009cc8  mov     ebx, eax
0x180009cca  test    eax, eax
0x180009ccc  js      short loc_180009D26
0x180009cce  cmp     r14w, 50h ; 'P'
0x180009cd3  jnz     short loc_180009D26
0x180009cd5  mov     [rsp+0DC0h+pszPath], r13
0x180009cda  mov     [rsp+0DC0h+var_D78], r13
0x180009cdf  mov     [rsp+0DC0h+var_D70], r13
0x180009ce4  lea     rcx, [rsp+0DC0h+pszPath]
0x180009ce9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009cee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009cf2  mov     [rsp+0DC0h+var_D78], rax
0x180009cf7  mov     [rsp+0DC0h+var_D70], rax
0x180009cfc  lea     rcx, [rsp+0DC0h+pszPath]; unsigned __int16 **
0x180009d01  call    ?LockScreenPathFromPolicy@@YAJPEAPEAG@Z; LockScreenPathFromPolicy(ushort * *)
0x180009d06  mov     ebx, eax
0x180009d08  test    eax, eax
0x180009d0a  js      short loc_180009D1C
0x180009d0c  mov     rdx, [rsp+0DC0h+pszPath]; pszPath
0x180009d11  lea     rcx, [r15+78h]; this
0x180009d15  call    ?_InitOrUpdateGPImages@CLockScreenHistory@@IEAAJPEBG@Z; CLockScreenHistory::_InitOrUpdateGPImages(ushort const *)
0x180009d1a  mov     ebx, eax
0x180009d1c  lea     rcx, [rsp+0DC0h+pszPath]
0x180009d21  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009d26  mov     rcx, [rbp+0CC8h]; this
0x180009d2d  test    ebx, ebx
0x180009d2f  jns     loc_180009DEC
0x180009d35  mov     r9d, ebx; char *
0x180009d38  mov     r8, rdi; unsigned int
0x180009d3b  mov     edx, 685h; void *
0x180009d40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009d45  mov     rcx, [rbp+0CC8h]; this
0x180009d4c  mov     r9d, ebx; char *
0x180009d4f  mov     r8, rdi; unsigned int
0x180009d52  mov     edx, 144Ch; void *
0x180009d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d5c  nop
0x180009d5d  mov     rcx, [rbp+0CC0h+pidl]; pidl
0x180009d64  call    cs:__imp_ILFree
0x180009d6b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
