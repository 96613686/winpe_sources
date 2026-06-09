# ShellExperienceHelpers::ModalWindowHelper::StartModal(HWND__ *,HWND__ *,ShellExperienceHelpers::ModalWindowHelper::StartModalFlags,IPrivilegedWindowOwnershipOperations *,IPrivilegedForegroundOperations *)

- ea: `0x18000b3d8`
- end: `0x18000b7e1`
- name: `?StartModal@ModalWindowHelper@ShellExperienceHelpers@@QEAAJPEAUHWND__@@0W4StartModalFlags@12@PEAUIPrivilegedWindowOwnershipOperations@@PEAUIPrivilegedForegroundOperations@@@Z`
- size: `1033`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009cb0`
- `0x18020e098`

## callees

- `0x180008acc`
- `0x18000b3d8`
- `0x18003c5e4`
- `0x18003c898`
- `0x1800ef768`
- `0x1800f2158`
- `0x18013d330`
- `0x18019801c`
- `0x180208d68`
- `0x18020b758`
- `0x18020ffb4`
- `0x1802100b8`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b471`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b471`
- `USER32!FlashWindow` at `0x18000b759`
- `USER32!FlashWindow` at `0x18000b759`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b45b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18000b623`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18000b623`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b6f4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b702`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b6f4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b702`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18000b796`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18000b796`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b55f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b732`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b747`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b55f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b732`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18000b747`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18000b782`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18000b782`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18000b639`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18000b73b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18000b639`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18000b73b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18000b5e1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18000b5e1`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18000b5a1`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18000b5b3`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18000b5a1`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18000b5b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellExperienceHelpers::ModalWindowHelper::StartModal(
        _QWORD *a1,
        HWND a2,
        HWND a3,
        char a4,
        __int64 a5,
        struct IPrivilegedForegroundOperations *a6)
{
  HRESULT v9; // eax
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, _QWORD *); // rbx
  _QWORD *v16; // r15
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  HWND v20; // r8
  __int64 v21; // rbx
  unsigned int UniqueContext; // eax
  __int64 v23; // rcx
  HWND v24; // r8
  HWND ForegroundWindow; // rax
  HWND v26; // rcx
  __int64 v27; // rdx
  DWORD WindowThreadProcessId; // ebx
  HWND Ancestor; // rbx
  HWND v30; // rax
  int v31; // [rsp+20h] [rbp-59h]
  HWND hwnd; // [rsp+40h] [rbp-39h] BYREF
  HWND hWnd; // [rsp+48h] [rbp-31h] BYREF
  __int64 v34; // [rsp+50h] [rbp-29h] BYREF
  struct IPrivilegedForegroundOperations *v35; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  hWnd = a2;
  hwnd = a3;
  v35 = a6;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup>::GetImpl'::`2'::impl,
    a2);
  if ( (a4 & 1) == 0 )
  {
    v34 = 0;
    string = 0;
    v9 = WindowsCreateStringReference(L"Windows.Internal.Shell.Popups.PopupClient", 0x29u, &hstringHeader, &string);
    if ( v9 < 0 )
    {
      RaiseException(v9, 1u, 0, 0);
      __debugbreak();
    }
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Shell::Popups::IPopupClientStatics>>(
            string,
            &v34);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
        (const char *)(unsigned int)v10,
        v31);
      v12 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      return (unsigned int)v11;
    }
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v34 + 56LL);
    v16 = a1 + 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 1);
    v17 = v15(v14, (unsigned int)hwnd, a1 + 1);
    v11 = v17;
    if ( v17 != -2147024891 )
    {
      if ( v17 < 0 )
      {
        v18 = 271;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
          (const char *)(unsigned int)v17,
          v31);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        return (unsigned int)v11;
      }
      hstringHeader.Reserved.Reserved1 = 0;
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*v16 + 72LL))(*v16, &hstringHeader);
      v11 = v17;
      if ( v17 < 0 )
      {
        v18 = 274;
        goto LABEL_13;
      }
      if ( *(_DWORD *)&hstringHeader.Reserved.Reserved2[4] )
        hwnd = GetAncestor((HWND)*(unsigned int *)&hstringHeader.Reserved.Reserved2[4], 2u);
      v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 56LL))(*v16);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11C,
          (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
          (const char *)(unsigned int)v19,
          v31);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  }
  if ( !(unsigned int)IsShellManagedWindow(hWnd) || (unsigned int)IsShellManagedWindow(hwnd) )
  {
    if ( a5 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, HWND, HWND))(*(_QWORD *)a5 + 24LL))(a5, hWnd, hwnd);
      if ( v11 < 0 )
      {
        v27 = 325;
        goto LABEL_31;
      }
    }
    else
    {
      v11 = ShellExperienceHelpers::SetWindowOwner(hWnd, hwnd, v20);
      if ( v11 < 0 )
      {
        v27 = 329;
        goto LABEL_31;
      }
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
    v21 = _lambda_e71153b4466264dd044f9579b1f36c18_::_lambda_e71153b4466264dd044f9579b1f36c18_(
            &hstringHeader,
            &hWnd,
            &hwnd,
            &v35);
    UniqueContext = SHTaskPoolGetUniqueContext();
    v11 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<ShellExperienceHelpers::Internal::ProxyModalWindow,ShellExperienceHelpers::Internal::IProxyModalWindow,_lambda_b61c939eac1c13c2fa01af63e4f28967_>(
            v23,
            UniqueContext,
            a1,
            v21);
    if ( v11 == -2147024891 )
    {
      SetWindowPos(hWnd, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u);
      *((_BYTE *)a1 + 41) = 1;
      goto LABEL_23;
    }
    if ( v11 < 0 )
    {
      v27 = 311;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
        (const char *)(unsigned int)v11,
        v31);
      return (unsigned int)v11;
    }
    ShellExperienceHelpers::FixRelativeZOrderingBeforeOwnership(hWnd, hwnd, v24);
  }
LABEL_23:
  if ( (a4 & 8) != 0 )
    goto LABEL_43;
  ForegroundWindow = GetForegroundWindow();
  if ( (a4 & 2) == 0 )
  {
    v26 = hwnd;
    if ( ForegroundWindow != hwnd && (ForegroundWindow || (a4 & 4) == 0) )
    {
LABEL_44:
      Ancestor = GetAncestor(v26, 3u);
      v30 = GetForegroundWindow();
      if ( Ancestor != GetAncestor(v30, 3u) )
        FlashWindow(Ancestor, 1);
      goto LABEL_46;
    }
    goto LABEL_42;
  }
  if ( !ForegroundWindow )
  {
    if ( (a4 & 4) != 0 )
      goto LABEL_42;
LABEL_43:
    v26 = hwnd;
    goto LABEL_44;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(ForegroundWindow, 0);
  if ( WindowThreadProcessId != GetWindowThreadProcessId(hwnd, 0) )
    goto LABEL_43;
LABEL_42:
  if ( !ShellExperienceHelpers::ModalWindowHelper::SetForegroundWindowWithPrivilegedOperation(
          (ShellExperienceHelpers::ModalWindowHelper *)v26,
          v35,
          hWnd) )
    goto LABEL_43;
LABEL_46:
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 32LL))(*a1);
  SetPropW(hwnd, L"ModalExperienceWindowProp", hWnd);
  *((_BYTE *)a1 + 40) = 0;
  if ( (a4 & 8) == 0 )
    *((_BYTE *)a1 + 40) = !EnableWindow(hwnd, 0);
  a1[2] = hWnd;
  a1[4] = hwnd;
  a1[3] = a3;
  return 0;
}

```

## disassembly

```asm
0x18000b3d8  mov     [rsp-8+arg_18], rbx
0x18000b3dd  push    rbp
0x18000b3de  push    rsi
0x18000b3df  push    rdi
0x18000b3e0  push    r12
0x18000b3e2  push    r13
0x18000b3e4  push    r14
0x18000b3e6  push    r15
0x18000b3e8  lea     rbp, [rsp-17h]
0x18000b3ed  sub     rsp, 90h
0x18000b3f4  mov     rax, cs:__security_cookie
0x18000b3fb  xor     rax, rsp
0x18000b3fe  mov     [rbp+47h+var_40], rax
0x18000b402  mov     r14d, r9d
0x18000b405  mov     r13, r8
0x18000b408  mov     rsi, rcx
0x18000b40b  mov     [rbp+47h+hWnd], rdx
0x18000b40f  mov     [rbp+47h+hwnd], r8
0x18000b413  mov     r12, [rbp+47h+arg_20]
0x18000b417  mov     rax, [rbp+47h+arg_28]
0x18000b41b  mov     [rbp+47h+var_68], rax
0x18000b41f  mov     dl, 1
0x18000b421  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@details@3@XZ@4V453@A
0x18000b428  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z
0x18000b42d  test    r14b, 1
0x18000b431  jnz     loc_18000B59D
0x18000b437  mov     [rbp+47h+var_70], 0
0x18000b43f  mov     [rbp+47h+string], 0
0x18000b447  lea     r9, [rbp+47h+string]; string
0x18000b44b  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18000b44f  mov     edx, 29h ; ')'; length
0x18000b454  lea     rcx, ?RuntimeClass_Windows_Internal_Shell_Popups_PopupClient@@3QBGB
0x18000b45b  call    cs:__imp_WindowsCreateStringReference
0x18000b461  test    eax, eax
0x18000b463  jns     short loc_18000B478
0x18000b465  xor     r9d, r9d; lpArguments
0x18000b468  xor     r8d, r8d; nNumberOfArguments
0x18000b46b  lea     edx, [r9+1]; dwExceptionFlags
0x18000b46f  mov     ecx, eax; dwExceptionCode
0x18000b471  call    cs:__imp_RaiseException
0x18000b477  int     3; Trap to Debugger
0x18000b478  lea     rdx, [rbp+47h+var_70]
0x18000b47c  mov     rcx, [rbp+47h+string]
0x18000b480  call    ??$GetActivationFactory@V?$ComPtr@UIPopupClientStatics@Popups@Shell@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupClientStatics@Popups@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z
0x18000b485  mov     ebx, eax
0x18000b487  test    eax, eax
0x18000b489  jns     short loc_18000B4C9
0x18000b48b  mov     rcx, [rbp+4Fh]; this
0x18000b48f  mov     r9d, eax; char *
0x18000b492  lea     r8, aShellTwinuiExp_12
0x18000b499  mov     edx, 108h; void *
0x18000b49e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18000b4a3  nop
0x18000b4a4  mov     rcx, [rbp+47h+var_70]
0x18000b4a8  test    rcx, rcx
0x18000b4ab  jz      short loc_18000B4C2
0x18000b4ad  mov     [rbp+47h+var_70], 0
0x18000b4b5  mov     rax, [rcx]
0x18000b4b8  mov     rax, [rax+10h]
0x18000b4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4c1  nop
0x18000b4c2  mov     eax, ebx
0x18000b4c4  jmp     loc_18000B7BA
0x18000b4c9  mov     rdi, [rbp+47h+var_70]
0x18000b4cd  mov     rax, [rdi]
0x18000b4d0  mov     rbx, [rax+38h]
0x18000b4d4  lea     r15, [rsi+8]
0x18000b4d8  mov     rcx, r15
0x18000b4db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18000b4e0  mov     r8, r15
0x18000b4e3  mov     edx, dword ptr [rbp+47h+hwnd]
0x18000b4e6  mov     rcx, rdi
0x18000b4e9  mov     rax, rbx
0x18000b4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f1  mov     ebx, eax
0x18000b4f3  cmp     eax, 80070005h
0x18000b4f8  jz      loc_18000B594
0x18000b4fe  test    eax, eax
0x18000b500  jns     short loc_18000B509
0x18000b502  mov     edx, 10Fh
0x18000b507  jmp     short loc_18000B530
0x18000b509  xor     eax, eax
0x18000b50b  mov     qword ptr [rbp+47h+hstringHeader.Reserved], rax
0x18000b50f  mov     dword ptr [rbp+47h+hstringHeader.Reserved+8], eax
0x18000b512  mov     rcx, [r15]
0x18000b515  mov     rax, [rcx]
0x18000b518  lea     rdx, [rbp+47h+hstringHeader]
0x18000b51c  mov     rax, [rax+48h]
0x18000b520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b525  mov     ebx, eax
0x18000b527  test    eax, eax
0x18000b529  jns     short loc_18000B551
0x18000b52b  mov     edx, 112h; void *
0x18000b530  mov     r9d, eax; char *
0x18000b533  lea     r8, aShellTwinuiExp_12
0x18000b53a  mov     rcx, [rbp+4Fh]; this
0x18000b53e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18000b543  lea     rcx, [rbp+47h+var_70]
0x18000b547  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18000b54c  jmp     loc_18000B4C2
0x18000b551  mov     eax, dword ptr [rbp+47h+hstringHeader.Reserved+4]
0x18000b554  test    eax, eax
0x18000b556  jz      short loc_18000B569
0x18000b558  mov     ecx, eax; hwnd
0x18000b55a  mov     edx, 2; gaFlags
0x18000b55f  call    cs:__imp_GetAncestor
0x18000b565  mov     [rbp+47h+hwnd], rax
0x18000b569  mov     rcx, [r15]
0x18000b56c  mov     rax, [rcx]
0x18000b56f  mov     rax, [rax+38h]
0x18000b573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b578  test    eax, eax
0x18000b57a  jns     short loc_18000B594
0x18000b57c  mov     rcx, [rbp+4Fh]; this
0x18000b580  mov     r9d, eax; char *
0x18000b583  lea     r8, aShellTwinuiExp_12
0x18000b58a  mov     edx, 11Ch; void *
0x18000b58f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18000b594  lea     rcx, [rbp+47h+var_70]
0x18000b598  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18000b59d  mov     rcx, [rbp+47h+hWnd]
0x18000b5a1  call    cs:__imp_IsShellManagedWindow
0x18000b5a7  test    eax, eax
0x18000b5a9  jz      loc_18000B69E
0x18000b5af  mov     rcx, [rbp+47h+hwnd]
0x18000b5b3  call    cs:__imp_IsShellManagedWindow
0x18000b5b9  test    eax, eax
0x18000b5bb  jnz     loc_18000B69E
0x18000b5c1  mov     rcx, rsi
0x18000b5c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18000b5c9  lea     r9, [rbp+47h+var_68]
0x18000b5cd  lea     r8, [rbp+47h+hwnd]
0x18000b5d1  lea     rdx, [rbp+47h+hWnd]
0x18000b5d5  lea     rcx, [rbp+47h+hstringHeader]
0x18000b5d9  call    ??0_lambda_e71153b4466264dd044f9579b1f36c18_@@QEAA@PEAV?$SimpleVectorView@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@V?$Vector@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2785@U?$VectorOptions@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@$00$00$0A@@2785@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2785@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAPEAUIContactActionControlItem@2Contacts@ApplicationModel@5@@Z
0x18000b5de  mov     rbx, rax
0x18000b5e1  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18000b5e7  mov     r9, rbx
0x18000b5ea  mov     r8, rsi
0x18000b5ed  mov     edx, eax
0x18000b5ef  call    ??$_MakeAndInitializeOnSTAThread@VProxyModalWindow@Internal@ShellExperienceHelpers@@UIProxyModalWindow@23@V_lambda_b61c939eac1c13c2fa01af63e4f28967_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIProxyModalWindow@1ShellExperienceHelpers@@AEBV_lambda_b61c939eac1c13c2fa01af63e4f28967_@@@Z
0x18000b5f4  mov     ebx, eax
0x18000b5f6  cmp     eax, 80070005h
0x18000b5fb  jnz     short loc_18000B66E
0x18000b5fd  mov     [rsp+0C0h+uFlags], 13h; uFlags
0x18000b605  mov     [rsp+0C0h+cy], 0; cy
0x18000b60d  mov     [rsp+0C0h+var_A0], 0; cx
0x18000b615  xor     r9d, r9d; Y
0x18000b618  xor     r8d, r8d; X
0x18000b61b  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18000b61f  mov     rcx, [rbp+47h+hWnd]; hWnd
0x18000b623  call    cs:__imp_SetWindowPos
0x18000b629  mov     byte ptr [rsi+29h], 1
0x18000b62d  mov     edi, r14d
0x18000b630  and     edi, 8
0x18000b633  jnz     loc_18000B725
0x18000b639  call    cs:__imp_GetForegroundWindow
0x18000b63f  test    r14b, 2
0x18000b643  jnz     loc_18000B6EA
0x18000b649  mov     rcx, [rbp+47h+hwnd]
0x18000b64d  cmp     rax, rcx
0x18000b650  jz      loc_18000B714
0x18000b656  test    rax, rax
0x18000b659  jnz     loc_18000B729
0x18000b65f  test    r14b, 4
0x18000b663  jz      loc_18000B729
0x18000b669  jmp     loc_18000B714
0x18000b66e  test    ebx, ebx
0x18000b670  jns     short loc_18000B68F
0x18000b672  mov     edx, 137h; void *
0x18000b677  mov     rcx, [rbp+4Fh]; this
0x18000b67b  mov     r9d, ebx; char *
0x18000b67e  lea     r8, aShellTwinuiExp_12
0x18000b685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18000b68a  jmp     loc_18000B4C2
0x18000b68f  mov     rdx, [rbp+47h+hwnd]; hWnd
0x18000b693  mov     rcx, [rbp+47h+hWnd]; hWndInsertAfter
0x18000b697  call    ?FixRelativeZOrderingBeforeOwnership@ShellExperienceHelpers@@YAXPEAUHWND__@@0@Z
0x18000b69c  jmp     short loc_18000B62D
0x18000b69e  test    r12, r12
0x18000b6a1  jz      short loc_18000B6CC
0x18000b6a3  mov     rax, [r12]
0x18000b6a7  mov     r8, [rbp+47h+hwnd]
0x18000b6ab  mov     rdx, [rbp+47h+hWnd]
0x18000b6af  mov     rcx, r12
0x18000b6b2  mov     rax, [rax+18h]
0x18000b6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6bb  mov     ebx, eax
0x18000b6bd  test    eax, eax
0x18000b6bf  jns     loc_18000B62D
0x18000b6c5  mov     edx, 145h
0x18000b6ca  jmp     short loc_18000B677
0x18000b6cc  mov     rdx, [rbp+47h+hwnd]; hWndInsertAfter
0x18000b6d0  mov     rcx, [rbp+47h+hWnd]; hWnd
0x18000b6d4  call    ?SetWindowOwner@ShellExperienceHelpers@@YAJPEAUHWND__@@0@Z
0x18000b6d9  mov     ebx, eax
0x18000b6db  test    eax, eax
0x18000b6dd  jns     loc_18000B62D
0x18000b6e3  mov     edx, 149h
0x18000b6e8  jmp     short loc_18000B677
0x18000b6ea  test    rax, rax
0x18000b6ed  jz      short loc_18000B70E
0x18000b6ef  xor     edx, edx; lpdwProcessId
0x18000b6f1  mov     rcx, rax; hWnd
0x18000b6f4  call    cs:__imp_GetWindowThreadProcessId
0x18000b6fa  mov     ebx, eax
0x18000b6fc  xor     edx, edx; lpdwProcessId
0x18000b6fe  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18000b702  call    cs:__imp_GetWindowThreadProcessId
0x18000b708  cmp     ebx, eax
0x18000b70a  jz      short loc_18000B714
0x18000b70c  jmp     short loc_18000B725
0x18000b70e  test    r14b, 4
0x18000b712  jz      short loc_18000B725
0x18000b714  mov     r8, [rbp+47h+hWnd]; HWND
0x18000b718  mov     rdx, [rbp+47h+var_68]; struct IPrivilegedForegroundOperations *
0x18000b71c  call    ?SetForegroundWindowWithPrivilegedOperation@ModalWindowHelper@ShellExperienceHelpers@@AEAA_NPEAUIPrivilegedForegroundOperations@@PEAUHWND__@@@Z
0x18000b721  test    al, al
0x18000b723  jnz     short loc_18000B75F
0x18000b725  mov     rcx, [rbp+47h+hwnd]; hwnd
0x18000b729  mov     r14d, 3
0x18000b72f  mov     edx, r14d; gaFlags
0x18000b732  call    cs:__imp_GetAncestor
0x18000b738  mov     rbx, rax
0x18000b73b  call    cs:__imp_GetForegroundWindow
0x18000b741  mov     rcx, rax; hwnd
0x18000b744  mov     edx, r14d; gaFlags
0x18000b747  call    cs:__imp_GetAncestor
0x18000b74d  cmp     rbx, rax
0x18000b750  jz      short loc_18000B75F
0x18000b752  lea     edx, [r14-2]; bInvert
0x18000b756  mov     rcx, rbx; hWnd
0x18000b759  call    cs:__imp_FlashWindow
0x18000b75f  mov     rcx, [rsi]
0x18000b762  test    rcx, rcx
0x18000b765  jz      short loc_18000B773
0x18000b767  mov     rax, [rcx]
0x18000b76a  mov     rax, [rax+20h]
0x18000b76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b773  mov     r8, [rbp+47h+hWnd]; hData
0x18000b777  lea     rdx, String
0x18000b77e  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18000b782  call    cs:__imp_SetPropW
0x18000b788  mov     byte ptr [rsi+28h], 0
0x18000b78c  test    edi, edi
0x18000b78e  jnz     short loc_18000B7A4
0x18000b790  xor     edx, edx; bEnable
0x18000b792  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18000b796  call    cs:__imp_EnableWindow
0x18000b79c  test    eax, eax
0x18000b79e  setz    al
0x18000b7a1  mov     [rsi+28h], al
0x18000b7a4  mov     rax, [rbp+47h+hWnd]
0x18000b7a8  mov     [rsi+10h], rax
0x18000b7ac  mov     rax, [rbp+47h+hwnd]
0x18000b7b0  mov     [rsi+20h], rax
0x18000b7b4  mov     [rsi+18h], r13
0x18000b7b8  xor     eax, eax
0x18000b7ba  mov     rcx, [rbp+47h+var_40]
0x18000b7be  xor     rcx, rsp; StackCookie
0x18000b7c1  call    __security_check_cookie
0x18000b7c6  mov     rbx, [rsp+0C0h+arg_18]
0x18000b7ce  add     rsp, 90h
0x18000b7d5  pop     r15
0x18000b7d7  pop     r14
0x18000b7d9  pop     r13
0x18000b7db  pop     r12
0x18000b7dd  pop     rdi
0x18000b7de  pop     rsi
0x18000b7df  pop     rbp
0x18000b7e0  retn
```
