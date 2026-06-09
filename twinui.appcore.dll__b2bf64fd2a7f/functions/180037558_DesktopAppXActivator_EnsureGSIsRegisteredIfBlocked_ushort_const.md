# DesktopAppXActivator::EnsureGSIsRegisteredIfBlocked(ushort const *)

- ea: `0x180037558`
- end: `0x180037bee`
- name: `?EnsureGSIsRegisteredIfBlocked@DesktopAppXActivator@@AEAAXPEBG@Z`
- size: `1686`
- prototype: `void __fastcall(DesktopAppXActivator *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006f30`

## callees

- `0x180003d24`
- `0x18000876c`
- `0x180012450`
- `0x180016300`
- `0x1800223e4`
- `0x180028870`
- `0x18002ad1c`
- `0x18002b1b0`
- `0x18002e489`
- `0x180033d5c`
- `0x1800360ac`
- `0x180037558`
- `0x180038d8c`
- `0x180039fa0`
- `0x18003a1e4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003768c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003768c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800376c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800376c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037960`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800378df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037911`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800378df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037911`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x1800376d1`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x1800376d1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003771a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003771a`

## string_xrefs

- `0x180037a32`: `Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices`
- `0x180037579`: `Microsoft.GamingServices_8wekyb3d8bbwe`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall DesktopAppXActivator::EnsureGSIsRegisteredIfBlocked(
        DesktopAppXActivator *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, _QWORD, __int64 *); // rbx
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int PackageStatus; // eax
  int v13; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, _QWORD); // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  const char *v24; // r9
  HRESULT v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  unsigned int ppv; // [rsp+20h] [rbp-128h]
  int ppva; // [rsp+20h] [rbp-128h]
  int ppvb; // [rsp+20h] [rbp-128h]
  int ppvc; // [rsp+20h] [rbp-128h]
  char v34; // [rsp+60h] [rbp-E8h] BYREF
  char v35[7]; // [rsp+61h] [rbp-E7h] BYREF
  LPVOID v36; // [rsp+68h] [rbp-E0h] BYREF
  int v37; // [rsp+70h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+98h] [rbp-B0h] BYREF
  _QWORD v43[2]; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-98h] BYREF
  int v45; // [rsp+B8h] [rbp-90h] BYREF
  int v46; // [rsp+BCh] [rbp-8Ch] BYREF
  __int64 v47; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v50; // [rsp+D8h] [rbp-70h] BYREF
  _QWORD v51[2]; // [rsp+E0h] [rbp-68h] BYREF
  IID Buf1[2]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v43[0] = L"Microsoft.GamingServices_8wekyb3d8bbwe";
  try
  {
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageFamilyStatics>();
    v41 = 0;
    v2 = v48;
    v3 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 128LL);
    v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(Buf1, v43);
    v5 = v3(v2, *(_QWORD *)(v4 + 24), &v41);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v40 = 0;
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&v47);
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v47 + 216LL))(v47, v41, 1, &v40);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v44 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, 0, &v44);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    string = 0;
    v8 = v44;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v10,
        ppv);
    v37 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    PackageStatus = GetPackageStatus(StringRawBuffer, &v37);
    if ( PackageStatus )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)PackageStatus,
        ppv);
    if ( (v37 & 0x400000) != 0 )
    {
      wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(&v42);
      v36 = 0;
      v39 = 0;
      v13 = UMgrQueryUserContext(0, &v39);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B1,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          (const char *)(unsigned int)v13,
          ppv);
      v14 = v42;
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v42 + 432LL);
      v16 = v39;
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(Buf1, v43);
      v18 = v15(v14, *(_QWORD *)(v17 + 24), v16, 0);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          (const char *)(unsigned int)v18,
          3);
      v21 = Windows::Management::Deployment::WaitForDeploymentOperation((_DWORD)retaddr, (_DWORD)v36, v19, v20, 3);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BC,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          (const char *)(unsigned int)v21,
          ppva);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
      goto LABEL_24;
    }
    if ( (v37 & 0x81020) == 0 )
    {
LABEL_24:
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      v28 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v48);
      return;
    }
    Buf1[0] = *(IID *)FindAppActivationErrorHandler(v51, 2147958016LL);
    if ( memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      v36 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      if ( CoCreateInstance(Buf1, 0, 4u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v36) < 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        v25 = CoCreateInstance(Buf1, 0, 1u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v36);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CB,
            (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
            (const char *)(unsigned int)v25,
            ppvb);
      }
      v39 = 0;
      v34 = 1;
      v35[0] = 1;
      v45 = 0;
      v49 = 0;
      v46 = 0;
      v50 = 0;
      v51[0] = WindowsGetStringRawBuffer(string, 0);
      LODWORD(v42) = 3;
      LODWORD(v43[0]) = 0;
      Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(&v39);
      v26 = Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,enum ACTIVATEOPTIONSINTERNAL,enum _PackageOrigin,unsigned short const *,unsigned int &,std::nullptr_t,int,std::nullptr_t,enum ACTIVATION_PHASE,bool,bool>(
              (unsigned int)&v39,
              (unsigned int)v43,
              (unsigned int)&v42,
              (unsigned int)v51,
              (__int64)&v37,
              (__int64)&v50,
              (__int64)&v46,
              (__int64)&v49,
              (__int64)&v45,
              (__int64)v35,
              (__int64)&v34);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          (const char *)(unsigned int)v26,
          ppvc);
      v27 = (*(__int64 (__fastcall **)(LPVOID, __int64, const wchar_t *, __int64))(*(_QWORD *)v36 + 32LL))(
              v36,
              2147958016LL,
              L"Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices",
              (v39 + 8) & -(__int64)(v39 != 0));
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DE,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          (const char *)(unsigned int)v27,
          ppvc);
      Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      goto LABEL_24;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
    v22 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v48);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      v24);
  }
}

```

## disassembly

```asm
0x180037558  mov     r11, rsp
0x18003755b  push    rbx
0x18003755c  push    rsi
0x18003755d  push    rdi
0x18003755e  push    r14
0x180037560  sub     rsp, 128h
0x180037567  mov     rax, cs:__security_cookie
0x18003756e  xor     rax, rsp
0x180037571  mov     [rsp+148h+var_38], rax
0x180037579  lea     rax, aMicrosoftGamin; "Microsoft.GamingServices_8wekyb3d8bbwe"
0x180037580  mov     [r11-0A8h], rax
0x180037587  lea     rcx, [r11-80h]
0x18003758b  call    ??$GetActivationFactory@UIPackageFamilyStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageFamilyStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageFamilyStatics>(ushort const *)
0x180037590  nop
0x180037591  xor     r14d, r14d
0x180037594  mov     [rsp+148h+var_B8], r14
0x18003759c  mov     rdi, [rsp+148h+var_80]
0x1800375a4  mov     rax, [rdi]
0x1800375a7  mov     rbx, [rax+80h]
0x1800375ae  lea     rdx, [rsp+148h+var_A8]
0x1800375b6  lea     rcx, [rsp+148h+Buf1]
0x1800375be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800375c3  nop
0x1800375c4  lea     r8, [rsp+148h+var_B8]
0x1800375cc  mov     rdx, [rax+18h]
0x1800375d0  mov     rcx, rdi
0x1800375d3  mov     rax, rbx
0x1800375d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375db  mov     rcx, [rsp+148h]; this
0x1800375e3  test    eax, eax
0x1800375e5  js      loc_180037B08
0x1800375eb  mov     [rsp+148h+var_C0], r14
0x1800375f3  lea     rcx, [rsp+148h+var_88]
0x1800375fb  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x180037600  nop
0x180037601  mov     rcx, [rsp+148h+var_88]
0x180037609  mov     rax, [rcx]
0x18003760c  lea     r9, [rsp+148h+var_C0]
0x180037614  mov     esi, 1
0x180037619  mov     r8d, esi
0x18003761c  mov     rdx, [rsp+148h+var_B8]
0x180037624  mov     rax, [rax+0D8h]
0x18003762b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037630  mov     rcx, [rsp+148h]; this
0x180037638  test    eax, eax
0x18003763a  js      loc_180037B1D
0x180037640  mov     [rsp+148h+var_98], r14
0x180037648  mov     rcx, [rsp+148h+var_C0]
0x180037650  mov     rax, [rcx]
0x180037653  lea     r8, [rsp+148h+var_98]
0x18003765b  xor     edx, edx
0x18003765d  mov     rax, [rax+30h]
0x180037661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037666  mov     rcx, [rsp+148h]; this
0x18003766e  test    eax, eax
0x180037670  js      loc_180037B32
0x180037676  mov     [rsp+148h+string], r14
0x18003767b  mov     rdi, [rsp+148h+var_98]
0x180037683  mov     rax, [rdi]
0x180037686  mov     rbx, [rax+70h]
0x18003768a  xor     ecx, ecx; string
0x18003768c  call    cs:__imp_WindowsDeleteString
0x180037692  mov     [rsp+148h+string], r14
0x180037697  lea     rdx, [rsp+148h+string]
0x18003769c  mov     rcx, rdi
0x18003769f  mov     rax, rbx
0x1800376a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376a7  mov     rcx, [rsp+148h]; this
0x1800376af  test    eax, eax
0x1800376b1  js      loc_180037B47
0x1800376b7  mov     [rsp+148h+var_D8], r14d
0x1800376bc  xor     edx, edx; length
0x1800376be  mov     rcx, [rsp+148h+string]; string
0x1800376c3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800376c9  lea     rdx, [rsp+148h+var_D8]
0x1800376ce  mov     rcx, rax
0x1800376d1  call    cs:__imp_GetPackageStatus
0x1800376d7  mov     rcx, [rsp+148h]; this
0x1800376df  test    eax, eax
0x1800376e1  jnz     loc_180037B5B
0x1800376e7  test    [rsp+148h+var_D8], 400000h
0x1800376ef  jz      loc_1800377DF
0x1800376f5  lea     rcx, [rsp+148h+var_B0]
0x1800376fd  call    ??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(ushort const *)
0x180037702  nop
0x180037703  mov     [rsp+148h+var_E0], r14
0x180037708  mov     [rsp+148h+var_C8], r14
0x180037710  lea     rdx, [rsp+148h+var_C8]
0x180037718  xor     ecx, ecx
0x18003771a  call    cs:__imp_UMgrQueryUserContext
0x180037720  mov     rcx, [rsp+148h]; this
0x180037728  test    eax, eax
0x18003772a  js      loc_180037B70
0x180037730  mov     rsi, [rsp+148h+var_B0]
0x180037738  mov     rax, [rsi]
0x18003773b  mov     rdi, [rax+1B0h]
0x180037742  mov     rbx, [rsp+148h+var_C8]
0x18003774a  lea     rdx, [rsp+148h+var_A8]
0x180037752  lea     rcx, [rsp+148h+Buf1]
0x18003775a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003775f  nop
0x180037760  lea     rcx, [rsp+148h+var_E0]
0x180037765  mov     [rsp+148h+var_120], rcx
0x18003776a  mov     dword ptr [rsp+148h+ppv], 3; int
0x180037772  xor     r9d, r9d
0x180037775  mov     r8, rbx
0x180037778  mov     rdx, [rax+18h]
0x18003777c  mov     rcx, rsi
0x18003777f  mov     rax, rdi
0x180037782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037787  mov     rcx, [rsp+148h]; this
0x18003778f  test    eax, eax
0x180037791  js      loc_180037B85
0x180037797  mov     rdx, [rsp+148h+var_E0]
0x18003779c  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x1800377a1  mov     rcx, [rsp+148h]; this
0x1800377a9  test    eax, eax
0x1800377ab  js      loc_180037B9A
0x1800377b1  mov     rcx, [rsp+148h+var_E0]
0x1800377b6  test    rcx, rcx
0x1800377b9  jz      short loc_1800377CD
0x1800377bb  mov     [rsp+148h+var_E0], r14
0x1800377c0  mov     rax, [rcx]
0x1800377c3  mov     rax, [rax+10h]
0x1800377c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377cc  nop
0x1800377cd  lea     rcx, [rsp+148h+var_B0]
0x1800377d5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800377da  jmp     loc_180037A6D
0x1800377df  test    [rsp+148h+var_D8], 81020h
0x1800377e7  jz      loc_180037A6D
0x1800377ed  mov     ebx, 80073D00h
0x1800377f2  mov     edx, ebx
0x1800377f4  lea     rcx, [rsp+148h+var_68]
0x1800377fc  call    FindAppActivationErrorHandler
0x180037801  movups  xmm0, xmmword ptr [rax]
0x180037804  movdqu  [rsp+148h+Buf1], xmm0
0x18003780d  mov     r8d, 10h; Size
0x180037813  lea     rdx, GUID_NULL; Buf2
0x18003781a  lea     rcx, [rsp+148h+Buf1]; Buf1
0x180037822  call    memcmp_0
0x180037827  test    eax, eax
0x180037829  jnz     loc_1800378B1
0x18003782f  mov     rcx, [rsp+148h+string]; string
0x180037834  call    cs:__imp_WindowsDeleteString
0x18003783a  mov     [rsp+148h+string], r14
0x18003783f  lea     rcx, [rsp+148h+var_98]
0x180037847  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003784c  nop
0x18003784d  lea     rcx, [rsp+148h+var_88]
0x180037855  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18003785a  nop
0x18003785b  mov     rcx, [rsp+148h+var_C0]
0x180037863  test    rcx, rcx
0x180037866  jz      short loc_18003787D
0x180037868  mov     [rsp+148h+var_C0], r14
0x180037870  mov     rax, [rcx]
0x180037873  mov     rax, [rax+10h]
0x180037877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003787c  nop
0x18003787d  mov     rcx, [rsp+148h+var_B8]
0x180037885  test    rcx, rcx
0x180037888  jz      short loc_18003789F
0x18003788a  mov     [rsp+148h+var_B8], r14
0x180037892  mov     rax, [rcx]
0x180037895  mov     rax, [rax+10h]
0x180037899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003789e  nop
0x18003789f  lea     rcx, [rsp+148h+var_80]
0x1800378a7  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800378ac  jmp     loc_180037AEB
0x1800378b1  mov     [rsp+148h+var_E0], r14
0x1800378b6  lea     rcx, [rsp+148h+var_E0]
0x1800378bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800378c0  lea     rax, [rsp+148h+var_E0]
0x1800378c5  mov     [rsp+148h+ppv], rax; ppv
0x1800378ca  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800378d1  xor     edx, edx; pUnkOuter
0x1800378d3  lea     r8d, [rdx+4]; dwClsContext
0x1800378d7  lea     rcx, [rsp+148h+Buf1]; rclsid
0x1800378df  call    cs:__imp_CoCreateInstance
0x1800378e5  test    eax, eax
0x1800378e7  jns     short loc_180037927
0x1800378e9  lea     rcx, [rsp+148h+var_E0]
0x1800378ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800378f3  lea     rax, [rsp+148h+var_E0]
0x1800378f8  mov     [rsp+148h+ppv], rax; int
0x1800378fd  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x180037904  mov     r8d, esi; dwClsContext
0x180037907  xor     edx, edx; pUnkOuter
0x180037909  lea     rcx, [rsp+148h+Buf1]; rclsid
0x180037911  call    cs:__imp_CoCreateInstance
0x180037917  mov     rcx, [rsp+148h]; this
0x18003791f  test    eax, eax
0x180037921  js      loc_180037BAF
0x180037927  mov     [rsp+148h+var_C8], r14
0x18003792f  mov     [rsp+148h+var_E8], sil
0x180037934  mov     [rsp+148h+var_E7], sil
0x180037939  mov     [rsp+148h+var_90], r14d
0x180037941  mov     [rsp+148h+var_78], r14
0x180037949  mov     [rsp+148h+var_8C], r14d
0x180037951  mov     [rsp+148h+var_70], r14
0x180037959  xor     edx, edx; length
0x18003795b  mov     rcx, [rsp+148h+string]; string
0x180037960  call    cs:__imp_WindowsGetStringRawBuffer
0x180037966  mov     [rsp+148h+var_68], rax
0x18003796e  mov     dword ptr [rsp+148h+var_B0], 3
0x180037979  mov     [rsp+148h+var_A8], r14d
0x180037981  lea     rcx, [rsp+148h+var_C8]
0x180037989  call    ?InternalRelease@?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(void)
0x18003798e  lea     rax, [rsp+148h+var_E8]
0x180037993  mov     [rsp+148h+var_F8], rax
0x180037998  lea     rax, [rsp+148h+var_E7]
0x18003799d  mov     [rsp+148h+var_100], rax
0x1800379a2  lea     rax, [rsp+148h+var_90]
0x1800379aa  mov     [rsp+148h+var_108], rax
0x1800379af  lea     rax, [rsp+148h+var_78]
0x1800379b7  mov     [rsp+148h+var_110], rax
0x1800379bc  lea     rax, [rsp+148h+var_8C]
0x1800379c4  mov     [rsp+148h+var_118], rax
0x1800379c9  lea     rax, [rsp+148h+var_70]
0x1800379d1  mov     [rsp+148h+var_120], rax
0x1800379d6  lea     rax, [rsp+148h+var_D8]
0x1800379db  mov     [rsp+148h+ppv], rax; int
0x1800379e0  lea     r9, [rsp+148h+var_68]
0x1800379e8  lea     r8, [rsp+148h+var_B0]
0x1800379f0  lea     rdx, [rsp+148h+var_A8]
0x1800379f8  lea     rcx, [rsp+148h+var_C8]
0x180037a00  call    ??$MakeAndInitialize@VAppActivationRemediationInfo@@V1@W4ACTIVATEOPTIONSINTERNAL@@W4_PackageOrigin@@PEBGAEAI$$TH$$TW4ACTIVATION_PHASE@@_N_N@Details@WRL@Microsoft@@YAJPEAPEAVAppActivationRemediationInfo@@$$QEAW4ACTIVATEOPTIONSINTERNAL@@$$QEAW4_PackageOrigin@@$$QEAPEBGAEAI$$QEA$$T$$QEAH5$$QEAW4ACTIVATION_PHASE@@$$QEA_N8@Z
0x180037a05  mov     rcx, [rsp+148h]; this
0x180037a0d  test    eax, eax
0x180037a0f  js      loc_180037BC4
0x180037a15  mov     rcx, [rsp+148h+var_E0]
0x180037a1a  mov     r8, [rsp+148h+var_C8]
0x180037a22  mov     r10, [rcx]
0x180037a25  lea     rax, [r8+8]
0x180037a29  neg     r8
0x180037a2c  sbb     r9, r9
0x180037a2f  and     r9, rax
0x180037a32  lea     r8, aMicrosoftGamin_0; "Microsoft.GamingServices_8wekyb3d8bbwe!"...
0x180037a39  mov     edx, ebx
0x180037a3b  mov     rax, [r10+20h]
0x180037a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a44  mov     rcx, [rsp+148h]; this
0x180037a4c  test    eax, eax
0x180037a4e  js      loc_180037BD8
0x180037a54  lea     rcx, [rsp+148h+var_C8]
0x180037a5c  call    ?InternalRelease@?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(void)
0x180037a61  nop
0x180037a62  lea     rcx, [rsp+148h+var_E0]
0x180037a67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037a6c  nop
0x180037a6d  mov     rcx, [rsp+148h+string]; string
0x180037a72  call    cs:__imp_WindowsDeleteString
0x180037a78  mov     [rsp+148h+string], r14
0x180037a7d  lea     rcx, [rsp+148h+var_98]
0x180037a85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037a8a  nop
0x180037a8b  lea     rcx, [rsp+148h+var_88]
0x180037a93  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180037a98  nop
0x180037a99  mov     rcx, [rsp+148h+var_C0]
0x180037aa1  test    rcx, rcx
0x180037aa4  jz      short loc_180037ABB
0x180037aa6  mov     [rsp+148h+var_C0], r14
0x180037aae  mov     rax, [rcx]
0x180037ab1  mov     rax, [rax+10h]
0x180037ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aba  nop
0x180037abb  mov     rcx, [rsp+148h+var_B8]
0x180037ac3  test    rcx, rcx
0x180037ac6  jz      short loc_180037ADD
0x180037ac8  mov     [rsp+148h+var_B8], r14
0x180037ad0  mov     rax, [rcx]
0x180037ad3  mov     rax, [rax+10h]
0x180037ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037adc  nop
0x180037add  lea     rcx, [rsp+148h+var_80]
0x180037ae5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180037aea  nop
0x180037aeb  mov     rcx, [rsp+148h+var_38]
0x180037af3  xor     rcx, rsp; StackCookie
0x180037af6  call    __security_check_cookie
0x180037afb  add     rsp, 128h
0x180037b02  pop     r14
0x180037b04  pop     rdi
0x180037b05  pop     rsi
0x180037b06  pop     rbx
0x180037b07  retn
0x180037b08  mov     r9d, eax; char *
0x180037b0b  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180037b12  mov     edx, 19Ch; void *
0x180037b17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037b1d  mov     r9d, eax; char *
0x180037b20  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180037b27  mov     edx, 1A0h; void *
0x180037b2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037b32  mov     r9d, eax; char *
0x180037b35  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180037b3c  mov     edx, 1A2h; void *
  ... truncated ...
```
