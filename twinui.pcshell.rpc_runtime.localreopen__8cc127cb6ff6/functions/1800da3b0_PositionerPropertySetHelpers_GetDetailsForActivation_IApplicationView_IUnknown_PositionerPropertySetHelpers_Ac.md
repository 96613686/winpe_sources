# PositionerPropertySetHelpers::GetDetailsForActivation(IApplicationView *,IUnknown *,PositionerPropertySetHelpers::ActivationPropertyFlags *,PositionerPropertySetHelpers::ViewSizePreferences *)

- ea: `0x1800da3b0`
- end: `0x1800da8a3`
- name: `?GetDetailsForActivation@PositionerPropertySetHelpers@@YAJPEAUIApplicationView@@PEAUIUnknown@@PEAW4ActivationPropertyFlags@1@PEAUViewSizePreferences@1@@Z`
- size: `1267`
- prototype: `__int64 __fastcall(PositionerPropertySetHelpers *__hidden this, struct IApplicationView *, struct IUnknown *, enum PositionerPropertySetHelpers::ActivationPropertyFlags *, struct PositionerPropertySetHelpers::ViewSizePreferences *)`
- caller_count: `14`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d8dc0`
- `0x1800d9400`
- `0x1800d9f38`
- `0x180204e70`
- `0x180235b50`
- `0x1802bc540`
- `0x1803a29a0`
- `0x180525440`
- `0x1805256f0`
- `0x180527638`
- `0x180537804`
- `0x18053784c`
- `0x18054d1c0`
- `0x18054e610`

## callees

- `0x1800237c8`
- `0x180023b60`
- `0x180031c70`
- `0x180045dfc`
- `0x1800479bc`
- `0x1800519e0`
- `0x1800da3b0`
- `0x180181818`
- `0x1801b9a9c`
- `0x1802bbaf8`
- `0x1802dd470`
- `0x1802de988`
- `0x180356360`
- `0x1803a30f0`
- `0x18066a8bc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da4af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da52b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da57a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da5c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da4af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da52b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da57a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da5c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da7f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da6e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da6e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da765`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800da664`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800da664`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800da62a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800da62a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800da6ff`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800da6ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PositionerPropertySetHelpers::GetDetailsForActivation(
        PositionerPropertySetHelpers *this,
        struct IApplicationView *a2,
        struct IUnknown *a3,
        enum PositionerPropertySetHelpers::ActivationPropertyFlags *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  ViewSizePreferenceHelpers *v8; // rcx
  HRESULT v10; // eax
  int v11; // edx
  __int64 v12; // r8
  int v13; // edi
  unsigned int v14; // r8d
  unsigned __int64 v15; // rdx
  HRESULT v16; // eax
  int v17; // edx
  __int64 v18; // r8
  HRESULT v19; // eax
  int v20; // edx
  __int64 v21; // r8
  HRESULT v22; // eax
  int v23; // edx
  __int64 v24; // r8
  HWND *v25; // r9
  CallerIdentity *v26; // r12
  const char *v27; // r9
  enum APPLICATION_VIEW_SIZE_PREFERENCE *v28; // r8
  bool v29; // r15
  void *v30; // rdx
  CallerIdentity *v31; // rbx
  char *v32; // r9
  int LastError; // esi
  int ImpersonationTokenFromProcess; // eax
  int v35; // eax
  PVOID Reserved1; // rbx
  HWND v37; // rdx
  const unsigned __int16 *v38; // rdx
  int TargetViewSizePreferenceFromPropertySet; // eax
  ViewSizePreferenceHelpers *v40; // rcx
  int v41; // [rsp+20h] [rbp-60h] BYREF
  ViewSizePreferenceHelpers *v42; // [rsp+28h] [rbp-58h] BYREF
  HWND hWnd; // [rsp+30h] [rbp-50h] BYREF
  int v44; // [rsp+38h] [rbp-48h] BYREF
  DWORD dwProcessId; // [rsp+3Ch] [rbp-44h] BYREF
  int v46; // [rsp+40h] [rbp-40h] BYREF
  ViewSizePreferenceHelpers *v47; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  LODWORD(a3->lpVtbl) = 0;
  if ( a4 )
  {
    *(_QWORD *)a4 = 0;
    *((_QWORD *)a4 + 1) = 0;
  }
  if ( !a2 )
    return 0;
  v42 = 0;
  v6 = (**(__int64 (__fastcall ***)(struct IApplicationView *, GUID *, ViewSizePreferenceHelpers **))a2)(
         a2,
         &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
         &v42);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v47 = v42;
    if ( v42 )
      (*(void (__fastcall **)(ViewSizePreferenceHelpers *))(*(_QWORD *)v42 + 8LL))(v42);
    v44 = 0;
    string = 0;
    v10 = WindowsCreateStringReference(L"AAMShim.ActivateOptionsInternal", 0x1Fu, &hstringHeader, &string);
    if ( v10 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      __debugbreak();
    }
    v13 = 0;
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(&v47, string, v12, &v44) >= 0 )
      v13 = (v44 & 0x1000000) != 0;
    BYTE1(v41) = 0;
    string = 0;
    v15 = -1;
    do
      ++v15;
    while ( aShellshouldlau[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v15, v14);
      __debugbreak();
    }
    if ( (int)v15 + 1 < (unsigned int)v15 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v15, v14);
      __debugbreak();
    }
    v16 = WindowsCreateStringReference(L"ShellShouldLaunchAppMinimized", v15, &hstringHeader, &string);
    if ( v16 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
      __debugbreak();
    }
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
                &v47,
                string,
                v18,
                (char *)&v41 + 1) >= 0
      && BYTE1(v41) )
    {
      v13 = 16;
    }
    BYTE2(v41) = 0;
    string = 0;
    v19 = WindowsCreateStringReference(L"ApplicationMultiviewActivationPolicy", 0x24u, &hstringHeader, &string);
    if ( v19 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
      JUMPOUT(0x1800DA8A2LL);
    }
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
                &v47,
                string,
                v21,
                (char *)&v41 + 2) >= 0
      && BYTE2(v41) )
    {
      v13 |= 4u;
    }
    LOBYTE(v41) = 0;
    string = 0;
    v22 = WindowsCreateStringReference(L"AppActivationResponse", 0x15u, &hstringHeader, &string);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      __debugbreak();
    }
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(&v47, string, v24, &v41) < 0 )
    {
      LOBYTE(v41) = 0;
    }
    else if ( (_BYTE)v41 )
    {
      v13 |= 8u;
    }
    v46 = 0;
    hWnd = 0;
    if ( (int)ViewSizePreferenceHelpers::GetSourceViewSizePreferenceFromPropertySet(
                v42,
                (struct Windows::Foundation::Collections::IPropertySet *)&v46,
                (enum APPLICATION_VIEW_SIZE_PREFERENCE *)&hWnd,
                v25) < 0 )
      goto LABEL_62;
    dwProcessId = 0;
    v26 = (CallerIdentity *)hWnd;
    if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    {
      v29 = 0;
      if ( (int)wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x14,
                  (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window_capability.cpp",
                  v27) < 0 )
        goto LABEL_51;
      goto LABEL_50;
    }
    v31 = (CallerIdentity *)OpenProcess(0x1000u, 0, dwProcessId);
    if ( (((unsigned __int64)v31 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v29 = 0;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x44,
                    (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
                    v32);
      if ( (unsigned __int64)v31 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_48;
      goto LABEL_47;
    }
    hWnd = 0;
    ImpersonationTokenFromProcess = CallerIdentity::GetImpersonationTokenFromProcess(
                                      v31,
                                      v30,
                                      (unsigned int)&hWnd,
                                      (void **)v32);
    LastError = ImpersonationTokenFromProcess;
    if ( ImpersonationTokenFromProcess >= 0 )
    {
      HIBYTE(v41) = 0;
      v35 = CapabilityCheck(hWnd, L"shellExperience", (char *)&v41 + 3);
      if ( v35 >= 0 )
      {
        v29 = HIBYTE(v41) != 0;
        LastError = 0;
      }
      else
      {
        v29 = 0;
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0xE,
                      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
                      (const char *)(unsigned int)v35,
                      v41);
      }
      if ( (unsigned __int64)hWnd - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hWnd);
      if ( LastError >= 0 )
        goto LABEL_47;
    }
    else
    {
      v29 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
        (const char *)(unsigned int)ImpersonationTokenFromProcess,
        v41);
      if ( (unsigned __int64)hWnd - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hWnd);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
      (const char *)(unsigned int)LastError,
      v41);
LABEL_47:
    CloseHandle(v31);
LABEL_48:
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window_capability.cpp",
        (const char *)(unsigned int)LastError,
        v41);
      goto LABEL_51;
    }
LABEL_50:
    if ( v29 )
    {
LABEL_59:
      if ( a4 )
      {
        *(_QWORD *)a4 = v26;
        *((_DWORD *)a4 + 2) = v46;
        TargetViewSizePreferenceFromPropertySet = ViewSizePreferenceHelpers::GetTargetViewSizePreferenceFromPropertySet(
                                                    v42,
                                                    (enum PositionerPropertySetHelpers::ActivationPropertyFlags *)((char *)a4 + 12),
                                                    v28);
        if ( TargetViewSizePreferenceFromPropertySet < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9D,
            (unsigned int)"desktop\\internal\\shell\\inc\\private\\PositionerPropertySetHelpers.h",
            (const char *)(unsigned int)TargetViewSizePreferenceFromPropertySet,
            v41);
      }
LABEL_62:
      LODWORD(a3->lpVtbl) = v13;
      if ( v47 )
        (*(void (__fastcall **)(ViewSizePreferenceHelpers *))(*(_QWORD *)v47 + 16LL))(v47);
      v40 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(ViewSizePreferenceHelpers *))(*(_QWORD *)v40 + 16LL))(v40);
      }
      return 0;
    }
LABEL_51:
    Reserved1 = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    if ( !(_BYTE)v41 )
    {
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
      if ( (int)CallerIdentity::GetImmersiveAppIdFromWindow(v26, (HWND)&hstringHeader, (unsigned __int16 **)v28) < 0
        || (int)CallerIdentity::ApiPolicyChecker::IsComponentUiHostWindowForeground(v26, v37) >= 0 )
      {
        Reserved1 = hstringHeader.Reserved.Reserved1;
      }
      else
      {
        Reserved1 = hstringHeader.Reserved.Reserved1;
        if ( (int)CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(
                    (struct IUnknown *)hstringHeader.Reserved.Reserved1,
                    v38) < 0 )
          v13 |= 2u;
      }
    }
    if ( Reserved1 )
      CoTaskMemFree(Reserved1);
    goto LABEL_59;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x46,
    (unsigned int)"desktop\\internal\\shell\\inc\\private\\PositionerPropertySetHelpers.h",
    (const char *)(unsigned int)v6,
    v41);
  v8 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(ViewSizePreferenceHelpers *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x1800da3b0  mov     [rsp-38h+arg_0], rbx
0x1800da3b5  push    rbp
0x1800da3b6  push    rsi
0x1800da3b7  push    rdi
0x1800da3b8  push    r12
0x1800da3ba  push    r13
0x1800da3bc  push    r14
0x1800da3be  push    r15
0x1800da3c0  mov     rbp, rsp
0x1800da3c3  sub     rsp, 80h
0x1800da3ca  mov     rax, cs:__security_cookie
0x1800da3d1  xor     rax, rsp
0x1800da3d4  mov     [rbp+var_10], rax
0x1800da3d8  mov     r14, r9
0x1800da3db  mov     r13, r8
0x1800da3de  mov     r10, rdx
0x1800da3e1  xor     esi, esi
0x1800da3e3  mov     [r8], esi
0x1800da3e6  test    r9, r9
0x1800da3e9  jz      short loc_1800DA3F2
0x1800da3eb  mov     [r9], rsi
0x1800da3ee  mov     [r9+8], rsi
0x1800da3f2  test    r10, r10
0x1800da3f5  jz      loc_1800DA866
0x1800da3fb  mov     [rbp+var_58], rsi
0x1800da3ff  mov     rax, [rdx]
0x1800da402  lea     r8, [rbp+var_58]
0x1800da406  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800da40d  mov     rcx, r10
0x1800da410  mov     rax, [rax]
0x1800da413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da418  mov     ebx, eax
0x1800da41a  test    eax, eax
0x1800da41c  jns     short loc_1800DA47A
0x1800da41e  mov     rcx, [rbp+38h]; this
0x1800da422  mov     r9d, eax; char *
0x1800da425  lea     r8, aDesktopInterna_24; "desktop\\internal\\shell\\inc\\private"...
0x1800da42c  mov     edx, 46h ; 'F'; void *
0x1800da431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da436  nop
0x1800da437  mov     rcx, [rbp+var_58]
0x1800da43b  test    rcx, rcx
0x1800da43e  jz      short loc_1800DA451
0x1800da440  mov     [rbp+var_58], rsi
0x1800da444  mov     rax, [rcx]
0x1800da447  mov     rax, [rax+10h]
0x1800da44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da450  nop
0x1800da451  mov     eax, ebx
0x1800da453  mov     rcx, [rbp+var_10]
0x1800da457  xor     rcx, rsp; StackCookie
0x1800da45a  call    __security_check_cookie
0x1800da45f  mov     rbx, [rsp+80h+arg_0]
0x1800da467  add     rsp, 80h
0x1800da46e  pop     r15
0x1800da470  pop     r14
0x1800da472  pop     r13
0x1800da474  pop     r12
0x1800da476  pop     rdi
0x1800da477  pop     rsi
0x1800da478  pop     rbp
0x1800da479  retn
0x1800da47a  mov     rcx, [rbp+var_58]
0x1800da47e  mov     [rbp+var_38], rcx
0x1800da482  test    rcx, rcx
0x1800da485  jz      short loc_1800DA494
0x1800da487  mov     rax, [rcx]
0x1800da48a  mov     rax, [rax+8]
0x1800da48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da493  nop
0x1800da494  mov     [rbp+var_48], esi
0x1800da497  mov     [rbp+string], rsi
0x1800da49b  lea     r9, [rbp+string]; string
0x1800da49f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800da4a3  mov     edx, 1Fh; length
0x1800da4a8  lea     rcx, aAamshimActivat; "AAMShim.ActivateOptionsInternal"
0x1800da4af  call    cs:__imp_WindowsCreateStringReference
0x1800da4b5  test    eax, eax
0x1800da4b7  js      loc_1800DA880
0x1800da4bd  mov     edi, esi
0x1800da4bf  lea     r9, [rbp+var_48]
0x1800da4c3  mov     rdx, [rbp+string]
0x1800da4c7  lea     rcx, [rbp+var_38]
0x1800da4cb  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x1800da4d0  nop
0x1800da4d1  shr     eax, 1Fh
0x1800da4d4  xor     al, 1
0x1800da4d6  jz      short loc_1800DA4E7
0x1800da4d8  test    [rbp+var_48], 1000000h
0x1800da4df  mov     eax, 1
0x1800da4e4  cmovnz  edi, eax
0x1800da4e7  mov     [rbp+var_5F], 0
0x1800da4eb  mov     [rbp+string], rsi
0x1800da4ef  mov     rcx, cs:off_1807500F8; sourceString
0x1800da4f6  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800da4fd  nop     dword ptr [rax]
0x1800da500  inc     rdx; int
0x1800da503  cmp     word ptr [rcx+rdx*2], 0
0x1800da508  jnz     short loc_1800DA500
0x1800da50a  mov     eax, 0FFFFFFFFh
0x1800da50f  cmp     rdx, rax
0x1800da512  ja      loc_1800DA875
0x1800da518  lea     eax, [rdx+1]
0x1800da51b  cmp     eax, edx
0x1800da51d  jb      loc_1800DA888
0x1800da523  lea     r9, [rbp+string]; string
0x1800da527  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800da52b  call    cs:__imp_WindowsCreateStringReference
0x1800da531  test    eax, eax
0x1800da533  js      loc_1800DA893
0x1800da539  lea     r9, [rbp+var_5F]
0x1800da53d  mov     rdx, [rbp+string]
0x1800da541  lea     rcx, [rbp+var_38]
0x1800da545  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x1800da54a  nop
0x1800da54b  shr     eax, 1Fh
0x1800da54e  xor     al, 1
0x1800da550  jz      short loc_1800DA55E
0x1800da552  mov     eax, 10h
0x1800da557  cmp     [rbp+var_5F], 0
0x1800da55b  cmovnz  edi, eax
0x1800da55e  mov     [rbp+var_5E], 0
0x1800da562  mov     [rbp+string], rsi
0x1800da566  lea     r9, [rbp+string]; string
0x1800da56a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800da56e  mov     edx, 24h ; '$'; length
0x1800da573  lea     rcx, aApplicationmul; "ApplicationMultiviewActivationPolicy"
0x1800da57a  call    cs:__imp_WindowsCreateStringReference
0x1800da580  test    eax, eax
0x1800da582  js      loc_1800DA89B
0x1800da588  lea     r9, [rbp+var_5E]
0x1800da58c  mov     rdx, [rbp+string]
0x1800da590  lea     rcx, [rbp+var_38]
0x1800da594  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x1800da599  nop
0x1800da59a  shr     eax, 1Fh
0x1800da59d  xor     al, 1
0x1800da59f  jz      short loc_1800DA5AA
0x1800da5a1  cmp     [rbp+var_5E], 0
0x1800da5a5  jz      short loc_1800DA5AA
0x1800da5a7  or      edi, 4
0x1800da5aa  mov     [rbp+var_60], 0
0x1800da5ae  mov     [rbp+string], rsi
0x1800da5b2  lea     r9, [rbp+string]; string
0x1800da5b6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800da5ba  mov     edx, 15h; length
0x1800da5bf  lea     rcx, aAppactivationr; "AppActivationResponse"
0x1800da5c6  call    cs:__imp_WindowsCreateStringReference
0x1800da5cc  test    eax, eax
0x1800da5ce  js      loc_1800DA86D
0x1800da5d4  lea     r9, [rbp+var_60]
0x1800da5d8  mov     rdx, [rbp+string]
0x1800da5dc  lea     rcx, [rbp+var_38]
0x1800da5e0  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x1800da5e5  nop
0x1800da5e6  shr     eax, 1Fh
0x1800da5e9  xor     al, 1
0x1800da5eb  jz      short loc_1800DA5F8
0x1800da5ed  cmp     [rbp+var_60], 0
0x1800da5f1  jz      short loc_1800DA5FC
0x1800da5f3  or      edi, 8
0x1800da5f6  jmp     short loc_1800DA5FC
0x1800da5f8  mov     [rbp+var_60], 0
0x1800da5fc  mov     [rbp+var_40], esi
0x1800da5ff  mov     [rbp+hWnd], rsi
0x1800da603  lea     r8, [rbp+hWnd]; enum APPLICATION_VIEW_SIZE_PREFERENCE *
0x1800da607  lea     rdx, [rbp+var_40]; struct Windows::Foundation::Collections::IPropertySet *
0x1800da60b  mov     rcx, [rbp+var_58]; this
0x1800da60f  call    ?GetSourceViewSizePreferenceFromPropertySet@ViewSizePreferenceHelpers@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAW4APPLICATION_VIEW_SIZE_PREFERENCE@@PEAPEAUHWND__@@@Z; ViewSizePreferenceHelpers::GetSourceViewSizePreferenceFromPropertySet(Windows::Foundation::Collections::IPropertySet *,APPLICATION_VIEW_SIZE_PREFERENCE *,HWND__ * *)
0x1800da614  test    eax, eax
0x1800da616  js      loc_1800DA832
0x1800da61c  mov     [rbp+dwProcessId], esi
0x1800da61f  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800da623  mov     r12, [rbp+hWnd]
0x1800da627  mov     rcx, r12; hWnd
0x1800da62a  call    cs:__imp_GetWindowThreadProcessId
0x1800da630  test    eax, eax
0x1800da632  jnz     short loc_1800DA659
0x1800da634  mov     rcx, [rbp+38h]; this
0x1800da638  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da63f  mov     edx, 14h; void *
0x1800da644  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800da649  xor     r15b, r15b
0x1800da64c  test    eax, eax
0x1800da64e  js      loc_1800DA792
0x1800da654  jmp     loc_1800DA78D
0x1800da659  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1800da65d  xor     edx, edx; bInheritHandle
0x1800da65f  mov     ecx, 1000h; dwDesiredAccess
0x1800da664  call    cs:__imp_OpenProcess
0x1800da66a  mov     rbx, rax
0x1800da66d  inc     rax
0x1800da670  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800da676  jnz     short loc_1800DA6A5
0x1800da678  xor     r15b, r15b
0x1800da67b  mov     rcx, [rbp+38h]; this
0x1800da67f  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da686  mov     edx, 44h ; 'D'; void *
0x1800da68b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800da690  mov     esi, eax
0x1800da692  lea     rax, [rbx-1]
0x1800da696  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800da69a  ja      loc_1800DA76B
0x1800da6a0  jmp     loc_1800DA762
0x1800da6a5  mov     [rbp+hWnd], rsi
0x1800da6a9  lea     r8, [rbp+hWnd]; unsigned int
0x1800da6ad  mov     rcx, rbx; this
0x1800da6b0  call    ?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z; CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)
0x1800da6b5  mov     esi, eax
0x1800da6b7  test    eax, eax
0x1800da6b9  jns     short loc_1800DA6EC
0x1800da6bb  xor     r15b, r15b
0x1800da6be  mov     rcx, [rbp+38h]; this
0x1800da6c2  mov     r9d, eax; char *
0x1800da6c5  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da6cc  mov     edx, 19h; void *
0x1800da6d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da6d6  mov     rcx, [rbp+hWnd]; hObject
0x1800da6da  lea     rax, [rcx-1]
0x1800da6de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800da6e2  ja      short loc_1800DA74A
0x1800da6e4  call    cs:__imp_CloseHandle
0x1800da6ea  jmp     short loc_1800DA74A
0x1800da6ec  mov     [rbp+var_5D], 0
0x1800da6f0  lea     r8, [rbp+var_5D]
0x1800da6f4  lea     rdx, aShellexperienc_0; "shellExperience"
0x1800da6fb  mov     rcx, [rbp+hWnd]
0x1800da6ff  call    cs:__imp_CapabilityCheck
0x1800da705  test    eax, eax
0x1800da707  jns     short loc_1800DA728
0x1800da709  xor     r15b, r15b
0x1800da70c  mov     rcx, [rbp+38h]; this
0x1800da710  mov     r9d, eax; char *
0x1800da713  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da71a  mov     edx, 0Eh; void *
0x1800da71f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800da724  mov     esi, eax
0x1800da726  jmp     short loc_1800DA732
0x1800da728  cmp     [rbp+var_5D], 0
0x1800da72c  setnz   r15b
0x1800da730  xor     esi, esi
0x1800da732  mov     rcx, [rbp+hWnd]; hObject
0x1800da736  lea     rax, [rcx-1]
0x1800da73a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800da73e  ja      short loc_1800DA746
0x1800da740  call    cs:__imp_CloseHandle
0x1800da746  test    esi, esi
0x1800da748  jns     short loc_1800DA762
0x1800da74a  mov     rcx, [rbp+38h]; this
0x1800da74e  mov     r9d, esi; char *
0x1800da751  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da758  mov     edx, 45h ; 'E'; void *
0x1800da75d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da762  mov     rcx, rbx; hObject
0x1800da765  call    cs:__imp_CloseHandle
0x1800da76b  test    esi, esi
0x1800da76d  jns     short loc_1800DA78B
0x1800da76f  mov     rcx, [rbp+38h]; this
0x1800da773  mov     r9d, esi; char *
0x1800da776  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800da77d  mov     edx, 16h; void *
0x1800da782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da787  xor     esi, esi
0x1800da789  jmp     short loc_1800DA792
0x1800da78b  xor     esi, esi
0x1800da78d  test    r15b, r15b
0x1800da790  jnz     short loc_1800DA7FA
0x1800da792  mov     rbx, rsi
0x1800da795  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800da799  mov     qword ptr [rbp+hstringHeader.Reserved+8], rsi
0x1800da79d  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rsi
0x1800da7a1  cmp     [rbp+var_60], 0
0x1800da7a5  jnz     short loc_1800DA7EC
0x1800da7a7  mov     qword ptr [rbp+hstringHeader.Reserved+8], 0FFFFFFFFFFFFFFFFh
0x1800da7af  mov     qword ptr [rbp+hstringHeader.Reserved+10h], 0FFFFFFFFFFFFFFFFh
0x1800da7b7  lea     rdx, [rbp+hstringHeader]; HWND
0x1800da7bb  mov     rcx, r12; this
0x1800da7be  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x1800da7c3  test    eax, eax
0x1800da7c5  js      short loc_1800DA7E8
0x1800da7c7  mov     rcx, r12; this
0x1800da7ca  call    ?IsComponentUiHostWindowForeground@ApiPolicyChecker@CallerIdentity@@YAJPEAUHWND__@@@Z; CallerIdentity::ApiPolicyChecker::IsComponentUiHostWindowForeground(HWND__ *)
0x1800da7cf  test    eax, eax
0x1800da7d1  jns     short loc_1800DA7E8
0x1800da7d3  mov     rbx, qword ptr [rbp+hstringHeader.Reserved]
0x1800da7d7  mov     rcx, rbx; this
0x1800da7da  call    ?ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground@ApiPolicyChecker@CallerIdentity@@YAJPEBG@Z; CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(ushort const *)
0x1800da7df  test    eax, eax
0x1800da7e1  jns     short loc_1800DA7EC
0x1800da7e3  or      edi, 2
0x1800da7e6  jmp     short loc_1800DA7EC
0x1800da7e8  mov     rbx, qword ptr [rbp+hstringHeader.Reserved]
0x1800da7ec  test    rbx, rbx
0x1800da7ef  jz      short loc_1800DA7FA
0x1800da7f1  mov     rcx, rbx; pv
0x1800da7f4  call    cs:__imp_CoTaskMemFree
0x1800da7fa  test    r14, r14
0x1800da7fd  jz      short loc_1800DA832
0x1800da7ff  mov     [r14], r12
0x1800da802  mov     eax, [rbp+var_40]
  ... truncated ...
```
