# Windows::System::Internal::Implementation::UserProfileManager::CreateProfileWithNameAndType(HSTRING__ *,uint,uchar,uint *)

- ea: `0x1800c21d0`
- end: `0x1800c2795`
- name: `?CreateProfileWithNameAndType@UserProfileManager@Implementation@Internal@System@Windows@@UEAAJPEAUHSTRING__@@IEPEAI@Z`
- size: `1477`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::Implementation::UserProfileManager *__hidden this@<rcx>, HSTRING@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, unsigned int *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000392c`
- `0x180003ab8`
- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x180014e7c`
- `0x180018d14`
- `0x180025cd4`
- `0x180025cf4`
- `0x1800346b8`
- `0x180039b08`
- `0x18003d38c`
- `0x18004bfa0`
- `0x18004c378`
- `0x18004c3cc`
- `0x18004e508`
- `0x18004e75c`
- `0x180063504`
- `0x18006371c`
- `0x180063748`
- `0x1800687f8`
- `0x1800c21d0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c22c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c22c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c221d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c243f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c221d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c243f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800c2295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800c2295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2573`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2531`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2531`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c24e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c24e5`
- `ntdll!RtlIsMultiSessionSku` at `0x1800c2311`
- `ntdll!RtlIsMultiSessionSku` at `0x1800c2311`

## string_xrefs

- `0x1800c2696`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c26ac`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c26c6`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c26dd`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c26f4`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c270b`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c271f`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c2732`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c2746`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c2759`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c276e`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c2782`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::Implementation::UserProfileManager::CreateProfileWithNameAndType(
        Windows::System::Internal::Implementation::UserProfileManager *this,
        HSTRING a2,
        unsigned int a3,
        unsigned __int8 a4,
        unsigned int *a5)
{
  unsigned __int8 v5; // di
  const struct _tlgProvider_t *v9; // rax
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  unsigned int *v13; // r15
  char v14; // al
  unsigned int v15; // r13d
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  char *StringRawBuffer; // rax
  __int64 v22; // rbx
  const char *v23; // r9
  int PersistedRegistryLocationAlloc; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  _DWORD *v27; // rax
  const struct _tlgProvider_t *v28; // rbx
  int v29; // r8d
  int v30; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v32; // rax
  int v33; // ebx
  wil *v34; // rcx
  int v35; // r8d
  int v36; // r9d
  Windows::System::Internal::UserProfile *dwOptions; // [rsp+20h] [rbp-C8h]
  int dwOptionsa; // [rsp+20h] [rbp-C8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-C8h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-C8h]
  _BYTE v41[4]; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v42; // [rsp+54h] [rbp-94h] BYREF
  HSTRING string; // [rsp+58h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-88h] BYREF
  BYTE *v45; // [rsp+68h] [rbp-80h] BYREF
  PCWSTR v46; // [rsp+70h] [rbp-78h] BYREF
  HKEY v47; // [rsp+78h] [rbp-70h] BYREF
  BYTE *lpData[2]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v49; // [rsp+90h] [rbp-58h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-50h] BYREF
  _BYTE v51[72]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  HSTRING v53; // [rsp+F8h] [rbp+10h] BYREF
  unsigned int v54; // [rsp+100h] [rbp+18h] BYREF
  unsigned __int8 v55; // [rsp+108h] [rbp+20h] BYREF

  v55 = a4;
  v54 = a3;
  v53 = a2;
  v5 = a4;
  v9 = UserMgrUserModelTelemetry::Provider();
  v10 = (int)v9;
  if ( *(_DWORD *)v9 > 5u )
  {
    v41[0] = v5;
    v42 = a3;
    lpData[0] = (BYTE *)WindowsGetStringRawBuffer(a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v10,
      (unsigned int)byte_18012C639,
      v11,
      v12,
      (__int64)lpData,
      (__int64)&v42,
      (__int64)v41);
  }
  v42 = 0;
  v47 = 0;
  v45 = 0;
  v49 = 0;
  try
  {
    if ( !IsFullTrustOrHasSignInCapabilityInSingleSessionOrAdminInMultiSession() )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80070005LL,
        (int)dwOptions);
    if ( WindowsIsStringEmpty(a2) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80A20E01LL,
        (int)dwOptions);
    v13 = a5;
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80004003LL,
        (int)dwOptions);
    *a5 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v46 = (PCWSTR)((char *)this + 64);
    Windows::System::Internal::Implementation::UserProfileManager::FindConsoleUserByEmailAddress(this, a2, &v42);
    if ( v42 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80A20E02LL,
        (int)dwOptions);
    if ( (unsigned int)(*((_DWORD *)this + 30) + 1) > 0xFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80A20101LL,
        (int)dwOptions);
    if ( (unsigned __int8)RtlIsMultiSessionSku(retaddr) || (v14 = 1, *((_QWORD *)this + 14) < 0x40u) )
      v14 = 0;
    if ( v14 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)0x80A2010ALL,
        (int)dwOptions);
    v15 = *((_DWORD *)this + 30);
    v42 = v15;
    *((_DWORD *)this + 30) = v15 + 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v47,
      0);
    Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(v15, &v47);
    lpData[0] = (BYTE *)v47;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    v16 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserProfile,Windows::System::Internal::IUserProfile,unsigned int &,HKEY__ *,HSTRING__ * &,bool,unsigned int &,unsigned char &>(
            &v45,
            &v42,
            (HKEY *)lpData,
            &v53,
            dwOptions,
            &v54,
            &v55);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v16,
        dwOptionsa);
    if ( a3 == 2 )
    {
      string = 0;
      v17 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v45,
              (__int64)&v49);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v17,
          dwOptionsa);
      v18 = v49;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v20 = v19(v18, &string);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v20,
          dwOptionsa);
      StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
      v22 = -1;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        lpData,
        StringRawBuffer,
        0xFFFFFFFFFFFFFFFFuLL,
        v23);
      lpSubKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &lpSubKey,
        0);
      PersistedRegistryLocationAlloc = Windows::System::Internal::Implementation::RegUtil::GetPersistedRegistryLocationAlloc(
                                         L"ResourceAccount",
                                         L"SOFTWARE\\Microsoft\\Policies\\AppRestrictions\\Resource\\Data",
                                         (unsigned __int16 **)&lpSubKey);
      if ( PersistedRegistryLocationAlloc < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)PersistedRegistryLocationAlloc,
          dwOptionsa);
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v25 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      if ( v25 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)v25,
          dwOptionsb);
      do
        ++v22;
      while ( *(_WORD *)&lpData[0][2 * v22] );
      v26 = RegSetValueExW(hKey, L"SID", 0, 1u, lpData[0], 2 * v22 + 2);
      if ( v26 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)v26,
          dwOptionsc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(lpData);
      WindowsDeleteString(string);
      v5 = v55;
    }
    lpData[0] = v45;
    v27 = std::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>(
            &lpSubKey,
            &v42,
            lpData);
    std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>>,0>>::insert(
      (char *)this + 104,
      lpData,
      v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v51);
    *v13 = v15;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v46);
    v28 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v28 > 5u )
    {
      v42 = 0;
      LODWORD(hKey) = *v13;
      v41[0] = v5;
      LODWORD(string) = a3;
      v46 = WindowsGetStringRawBuffer(a2, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v28,
        (unsigned int)&unk_18012C5C8,
        v29,
        v30,
        (__int64)&v46,
        (__int64)&string,
        (__int64)v41,
        (__int64)&hKey,
        (__int64)&v42);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
    result = 0;
  }
  catch ( ... )
  {
    v32 = UserMgrUserModelTelemetry::Provider();
    v33 = (int)v32;
    v34 = (wil *)*(unsigned int *)v32;
    if ( (unsigned int)v34 > 5 )
    {
      LODWORD(string) = wil::ResultFromCaughtException(v34);
      v41[0] = v55;
      LODWORD(hKey) = v54;
      v46 = WindowsGetStringRawBuffer(v53, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v33,
        (unsigned int)&dword_18012C54C,
        v35,
        v36,
        (__int64)&v46,
        (__int64)&hKey,
        (__int64)v41,
        (__int64)&string);
    }
    return (unsigned int)wil::ResultFromCaughtException(v34);
  }
  return result;
}

```

## disassembly

```asm
0x1800c21d0  mov     [rsp+arg_18], r9b
0x1800c21d5  mov     [rsp+arg_10], r8d
0x1800c21da  mov     [rsp+arg_8], rdx
0x1800c21df  push    rbx
0x1800c21e0  push    rsi
0x1800c21e1  push    rdi
0x1800c21e2  push    r12
0x1800c21e4  push    r13
0x1800c21e6  push    r14
0x1800c21e8  push    r15
0x1800c21ea  sub     rsp, 0B0h
0x1800c21f1  mov     dil, r9b
0x1800c21f4  mov     r12d, r8d
0x1800c21f7  mov     r14, rdx
0x1800c21fa  mov     rsi, rcx
0x1800c21fd  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800c2202  mov     rbx, rax
0x1800c2205  mov     r10d, [rax]
0x1800c2208  cmp     r10d, 5
0x1800c220c  jbe     short loc_1800C225B
0x1800c220e  mov     [rsp+0E8h+var_98], dil
0x1800c2213  mov     [rsp+0E8h+var_94], r12d
0x1800c2218  xor     edx, edx; length
0x1800c221a  mov     rcx, r14; string
0x1800c221d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2223  mov     [rsp+0E8h+lpData], rax
0x1800c222b  lea     rax, [rsp+0E8h+var_98]
0x1800c2230  mov     [rsp+0E8h+lpSecurityAttributes], rax
0x1800c2235  lea     rax, [rsp+0E8h+var_94]
0x1800c223a  mov     qword ptr [rsp+0E8h+samDesired], rax
0x1800c223f  lea     rax, [rsp+0E8h+lpData]
0x1800c2247  mov     qword ptr [rsp+0E8h+dwOptions], rax; int
0x1800c224c  lea     rdx, byte_18012C639
0x1800c2253  mov     rcx, rbx
0x1800c2256  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800c225b  xor     r13d, r13d
0x1800c225e  mov     [rsp+0E8h+var_94], r13d
0x1800c2263  mov     [rsp+0E8h+var_70], r13
0x1800c2268  mov     [rsp+0E8h+var_80], r13
0x1800c226d  mov     [rsp+0E8h+var_58], r13
0x1800c2275  call    ?IsFullTrustOrHasSignInCapabilityInSingleSessionOrAdminInMultiSession@@YA_NXZ; IsFullTrustOrHasSignInCapabilityInSingleSessionOrAdminInMultiSession(void)
0x1800c227a  mov     rcx, [rsp+0E8h]; this
0x1800c2282  test    al, al
0x1800c2284  jz      loc_1800C2690
0x1800c228a  mov     rbx, [rsp+0E8h]
0x1800c2292  mov     rcx, r14; string
0x1800c2295  call    cs:__imp_WindowsIsStringEmpty
0x1800c229b  test    eax, eax
0x1800c229d  jnz     loc_1800C26A6
0x1800c22a3  mov     rcx, [rsp+0E8h]; this
0x1800c22ab  mov     r15, [rsp+0E8h+arg_20]
0x1800c22b3  test    r15, r15
0x1800c22b6  jz      loc_1800C26C0
0x1800c22bc  mov     [r15], r13d
0x1800c22bf  lea     rbx, [rsi+40h]
0x1800c22c3  mov     rcx, rbx; lpCriticalSection
0x1800c22c6  call    cs:__imp_EnterCriticalSection
0x1800c22cc  mov     [rsp+0E8h+var_78], rbx
0x1800c22d1  lea     r8, [rsp+0E8h+var_94]; unsigned int *
0x1800c22d6  mov     rdx, r14; HSTRING
0x1800c22d9  mov     rcx, rsi; this
0x1800c22dc  call    ?FindConsoleUserByEmailAddress@UserProfileManager@Implementation@Internal@System@Windows@@AEAAJPEAUHSTRING__@@PEAI@Z; Windows::System::Internal::Implementation::UserProfileManager::FindConsoleUserByEmailAddress(HSTRING__ *,uint *)
0x1800c22e1  cmp     [rsp+0E8h+var_94], r13d
0x1800c22e6  setnz   al
0x1800c22e9  mov     rcx, [rsp+0E8h]; this
0x1800c22f1  test    al, al
0x1800c22f3  jnz     loc_1800C26D7
0x1800c22f9  mov     rcx, [rsp+0E8h]; this
0x1800c2301  mov     eax, [rsi+78h]
0x1800c2304  inc     eax
0x1800c2306  cmp     eax, 0FFFFFh
0x1800c230b  ja      loc_1800C26EE
0x1800c2311  call    cs:__imp_RtlIsMultiSessionSku
0x1800c2317  test    al, al
0x1800c2319  jnz     short loc_1800C2324
0x1800c231b  cmp     qword ptr [rsi+70h], 40h ; '@'
0x1800c2320  mov     al, 1
0x1800c2322  jnb     short loc_1800C2327
0x1800c2324  mov     al, r13b
0x1800c2327  mov     rcx, [rsp+0E8h]; this
0x1800c232f  test    al, al
0x1800c2331  jnz     loc_1800C2705
0x1800c2337  mov     r13d, [rsi+78h]
0x1800c233b  mov     [rsp+0E8h+var_94], r13d
0x1800c2340  lea     eax, [r13+1]
0x1800c2344  mov     [rsi+78h], eax
0x1800c2347  xor     edx, edx
0x1800c2349  lea     rcx, [rsp+0E8h+var_70]
0x1800c234e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c2353  lea     rdx, [rsp+0E8h+var_70]; HKEY *
0x1800c2358  mov     ecx, r13d; Value
0x1800c235b  call    ?CreateUserKey@UserProfileManager@Implementation@Internal@System@Windows@@SAJIPEAPEAUHKEY__@@@Z; Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(uint,HKEY__ * *)
0x1800c2360  mov     rax, [rsp+0E8h+var_70]
0x1800c2365  mov     [rsp+0E8h+lpData], rax
0x1800c236d  lea     rcx, [rsp+0E8h+var_80]
0x1800c2372  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2377  lea     rax, [rsp+0E8h+arg_18]
0x1800c237f  mov     [rsp+0E8h+lpSecurityAttributes], rax
0x1800c2384  lea     rax, [rsp+0E8h+arg_10]
0x1800c238c  mov     qword ptr [rsp+0E8h+samDesired], rax
0x1800c2391  lea     r9, [rsp+0E8h+arg_8]
0x1800c2399  lea     r8, [rsp+0E8h+lpData]
0x1800c23a1  lea     rdx, [rsp+0E8h+var_94]
0x1800c23a6  lea     rcx, [rsp+0E8h+var_80]
0x1800c23ab  call    ??$MakeAndInitialize@VUserProfile@Internal@System@Windows@@UIUserProfile@234@AEAIPEAUHKEY__@@AEAPEAUHSTRING__@@_NAEAIAEAE@Details@WRL@Microsoft@@YAJPEAPEAUIUserProfile@Internal@System@Windows@@AEAI$$QEAPEAUHKEY__@@AEAPEAUHSTRING__@@$$QEA_N1AEAE@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserProfile,Windows::System::Internal::IUserProfile,uint &,HKEY__ *,HSTRING__ * &,bool,uint &,uchar &>(Windows::System::Internal::IUserProfile * *,uint &,HKEY__ * &&,HSTRING__ * &,bool &&,uint &,uchar &)
0x1800c23b0  mov     rcx, [rsp+0E8h]; this
0x1800c23b8  xor     ebx, ebx
0x1800c23ba  test    eax, eax
0x1800c23bc  js      loc_1800C271C
0x1800c23c2  cmp     r12d, 2
0x1800c23c6  jnz     loc_1800C2581
0x1800c23cc  mov     [rsp+0E8h+string], rbx
0x1800c23d1  lea     rdx, [rsp+0E8h+var_58]
0x1800c23d9  lea     rcx, [rsp+0E8h+var_80]
0x1800c23de  call    ??$As@UIUserProfile2@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfile2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile2>>)
0x1800c23e3  mov     rcx, [rsp+0E8h]; this
0x1800c23eb  test    eax, eax
0x1800c23ed  js      loc_1800C272F
0x1800c23f3  mov     rdi, [rsp+0E8h+var_58]
0x1800c23fb  mov     rax, [rdi]
0x1800c23fe  mov     rbx, [rax+38h]
0x1800c2402  mov     rcx, [rsp+0E8h+string]; string
0x1800c2407  call    cs:__imp_WindowsDeleteString
0x1800c240d  mov     [rsp+0E8h+string], 0
0x1800c2416  lea     rdx, [rsp+0E8h+string]
0x1800c241b  mov     rcx, rdi
0x1800c241e  mov     rax, rbx
0x1800c2421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2426  mov     rcx, [rsp+0E8h]; this
0x1800c242e  xor     edi, edi
0x1800c2430  test    eax, eax
0x1800c2432  js      loc_1800C2743
0x1800c2438  xor     edx, edx; length
0x1800c243a  mov     rcx, [rsp+0E8h+string]; string
0x1800c243f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2445  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c2449  mov     r8, rbx
0x1800c244c  mov     rdx, rax
0x1800c244f  lea     rcx, [rsp+0E8h+lpData]
0x1800c2457  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800c245c  nop
0x1800c245d  mov     [rsp+0E8h+lpSubKey], rdi
0x1800c2465  xor     edx, edx
0x1800c2467  lea     rcx, [rsp+0E8h+lpSubKey]
0x1800c246f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800c2474  lea     r8, [rsp+0E8h+lpSubKey]; unsigned __int16 **
0x1800c247c  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Policies\\AppRestr"...
0x1800c2483  lea     rcx, aResourceaccoun_4; "ResourceAccount"
0x1800c248a  call    ?GetPersistedRegistryLocationAlloc@RegUtil@Implementation@Internal@System@Windows@@SAJPEBG0PEAPEAG@Z; Windows::System::Internal::Implementation::RegUtil::GetPersistedRegistryLocationAlloc(ushort const *,ushort const *,ushort * *)
0x1800c248f  mov     rcx, [rsp+0E8h]; this
0x1800c2497  test    eax, eax
0x1800c2499  js      loc_1800C2756
0x1800c249f  mov     [rsp+0E8h+hKey], rdi
0x1800c24a4  xor     edx, edx
0x1800c24a6  lea     rcx, [rsp+0E8h+hKey]
0x1800c24ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c24b0  mov     [rsp+0E8h+lpdwDisposition], rdi; lpdwDisposition
0x1800c24b5  lea     rax, [rsp+0E8h+hKey]
0x1800c24ba  mov     [rsp+0E8h+phkResult], rax; phkResult
0x1800c24bf  mov     [rsp+0E8h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800c24c4  mov     [rsp+0E8h+samDesired], 20006h; samDesired
0x1800c24cc  mov     [rsp+0E8h+dwOptions], edi; unsigned int
0x1800c24d0  xor     r9d, r9d; lpClass
0x1800c24d3  xor     r8d, r8d; Reserved
0x1800c24d6  mov     rdx, [rsp+0E8h+lpSubKey]; lpSubKey
0x1800c24de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c24e5  call    cs:__imp_RegCreateKeyExW
0x1800c24eb  mov     rcx, [rsp+0E8h]; this
0x1800c24f3  test    eax, eax
0x1800c24f5  jnz     loc_1800C276B
0x1800c24fb  mov     rax, [rsp+0E8h+lpData]
0x1800c2503  inc     rbx
0x1800c2506  cmp     [rax+rbx*2], di
0x1800c250a  jnz     short loc_1800C2503
0x1800c250c  lea     edx, ds:2[rbx*2]
0x1800c2513  mov     [rsp+0E8h+samDesired], edx; cbData
0x1800c2517  mov     qword ptr [rsp+0E8h+dwOptions], rax; unsigned int
0x1800c251c  mov     r9d, 1; dwType
0x1800c2522  xor     r8d, r8d; Reserved
0x1800c2525  lea     rdx, aSid_4; "SID"
0x1800c252c  mov     rcx, [rsp+0E8h+hKey]; hKey
0x1800c2531  call    cs:__imp_RegSetValueExW
0x1800c2537  mov     rcx, [rsp+0E8h]; this
0x1800c253f  test    eax, eax
0x1800c2541  jnz     loc_1800C277F
0x1800c2547  lea     rcx, [rsp+0E8h+hKey]
0x1800c254c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c2551  nop
0x1800c2552  lea     rcx, [rsp+0E8h+lpSubKey]
0x1800c255a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c255f  nop
0x1800c2560  lea     rcx, [rsp+0E8h+lpData]
0x1800c2568  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c256d  nop
0x1800c256e  mov     rcx, [rsp+0E8h+string]; string
0x1800c2573  call    cs:__imp_WindowsDeleteString
0x1800c2579  mov     dil, [rsp+0E8h+arg_18]
0x1800c2581  mov     rax, [rsp+0E8h+var_80]
0x1800c2586  mov     [rsp+0E8h+lpData], rax
0x1800c258e  lea     r8, [rsp+0E8h+lpData]
0x1800c2596  lea     rdx, [rsp+0E8h+var_94]
0x1800c259b  lea     rcx, [rsp+0E8h+lpSubKey]
0x1800c25a3  call    ??$?0AEAIPEAUIUserProfile@Internal@System@Windows@@@?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@QEAA@AEAI$$QEAPEAUIUserProfile@Internal@System@Windows@@PEAPEAX@Z; std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>(uint &,Windows::System::Internal::IUserProfile * &&,void * *)
0x1800c25a8  nop
0x1800c25a9  lea     rcx, [rsi+68h]
0x1800c25ad  mov     r8, rax
0x1800c25b0  lea     rdx, [rsp+0E8h+lpData]
0x1800c25b8  call    ?insert@?$_Tree@V?$_Tmap_traits@IV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>>,0>>::insert(std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>> &&)
0x1800c25bd  nop
0x1800c25be  lea     rcx, [rsp+0E8h+var_48]
0x1800c25c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c25cb  mov     [r15], r13d
0x1800c25ce  lea     rcx, [rsp+0E8h+var_78]
0x1800c25d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800c25d8  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800c25dd  mov     rbx, rax
0x1800c25e0  mov     ecx, [rax]
0x1800c25e2  cmp     ecx, 5
0x1800c25e5  jbe     short loc_1800C2652
0x1800c25e7  mov     [rsp+0E8h+var_94], 0
0x1800c25ef  mov     ecx, [r15]
0x1800c25f2  mov     dword ptr [rsp+0E8h+hKey], ecx
0x1800c25f6  mov     [rsp+0E8h+var_98], dil
0x1800c25fb  mov     dword ptr [rsp+0E8h+string], r12d
0x1800c2600  xor     edx, edx; length
0x1800c2602  mov     rcx, r14; string
0x1800c2605  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c260b  mov     [rsp+0E8h+var_78], rax
0x1800c2610  lea     rax, [rsp+0E8h+var_94]
0x1800c2615  mov     [rsp+0E8h+lpdwDisposition], rax
0x1800c261a  lea     rax, [rsp+0E8h+hKey]
0x1800c261f  mov     [rsp+0E8h+phkResult], rax
0x1800c2624  lea     rax, [rsp+0E8h+var_98]
0x1800c2629  mov     [rsp+0E8h+lpSecurityAttributes], rax
0x1800c262e  lea     rax, [rsp+0E8h+string]
0x1800c2633  mov     qword ptr [rsp+0E8h+samDesired], rax
0x1800c2638  lea     rax, [rsp+0E8h+var_78]
0x1800c263d  mov     qword ptr [rsp+0E8h+dwOptions], rax
0x1800c2642  lea     rdx, unk_18012C5C8
0x1800c2649  mov     rcx, rbx
0x1800c264c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c2651  nop
0x1800c2652  lea     rcx, [rsp+0E8h+var_58]
0x1800c265a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c265f  nop
0x1800c2660  lea     rcx, [rsp+0E8h+var_80]
0x1800c2665  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c266a  nop
0x1800c266b  lea     rcx, [rsp+0E8h+var_70]
0x1800c2670  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c2675  xor     eax, eax
0x1800c2677  jmp     short loc_1800C267D
0x1800c2679  mov     eax, dword ptr [rsp+0E8h+string]
0x1800c267d  add     rsp, 0B0h
0x1800c2684  pop     r15
0x1800c2686  pop     r14
0x1800c2688  pop     r13
0x1800c268a  pop     r12
0x1800c268c  pop     rdi
0x1800c268d  pop     rsi
0x1800c268e  pop     rbx
0x1800c268f  retn
0x1800c2690  mov     r9d, 80070005h; char *
0x1800c2696  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c269d  lea     edx, [r13+64h]; void *
0x1800c26a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c26a6  mov     r9d, 80A20E01h; char *
0x1800c26ac  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c26b3  mov     edx, 65h ; 'e'; void *
0x1800c26b8  mov     rcx, rbx; this
0x1800c26bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c26c0  mov     r9d, 80004003h; char *
0x1800c26c6  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c26cd  lea     edx, [r15+66h]; void *
0x1800c26d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c26d7  mov     r9d, 80A20E02h; char *
0x1800c26dd  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c26e4  mov     edx, 6Eh ; 'n'; void *
0x1800c26e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c26ee  mov     r9d, 80A20101h; char *
0x1800c26f4  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c26fb  mov     edx, 70h ; 'p'; void *
0x1800c2700  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c2705  mov     r9d, 80A2010Ah; char *
0x1800c270b  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c2712  mov     edx, 73h ; 's'; void *
0x1800c2717  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c271c  mov     r9d, eax; char *
0x1800c271f  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c2726  lea     edx, [rbx+78h]; void *
0x1800c2729  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c272f  mov     r9d, eax; char *
0x1800c2732  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c2739  lea     edx, [r12+7Ch]; void *
0x1800c273e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c2743  mov     r9d, eax; char *
0x1800c2746  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c274d  lea     edx, [rdi+7Fh]; void *
0x1800c2750  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c2756  mov     r9d, eax; char *
  ... truncated ...
```
