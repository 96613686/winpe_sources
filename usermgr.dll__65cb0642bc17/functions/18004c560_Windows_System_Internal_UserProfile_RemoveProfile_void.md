# Windows::System::Internal::UserProfile::RemoveProfile(void)

- ea: `0x18004c560`
- end: `0x18004c714`
- name: `?RemoveProfile@UserProfile@Internal@System@Windows@@UEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserProfile *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000acdc`
- `0x1800179c0`
- `0x18003d38c`
- `0x18004bfa0`
- `0x18004c378`
- `0x18004c3cc`
- `0x18004c560`
- `0x18004e508`
- `0x18004e75c`
- `0x18008cb8c`
- `0x1800ce480`
- `0x1800ce554`
- `0x1800ce70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c61c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c61c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004c64b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004c64b`

## string_xrefs

- `0x18004c5d7`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004c62e`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004c65d`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004c6b4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004c701`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::UserProfile::RemoveProfile(Windows::System::Internal::UserProfile *this)
{
  char *v2; // rbx
  HSTRING v3; // r8
  int PersistedRegistryLocationAlloc; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  HSTRING v7; // rdx
  int v8; // eax
  wil *v9; // rcx
  __int64 result; // rax
  int v11; // eax
  int v12; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Windows::System::Internal::UserProfile *v15; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+18h] BYREF
  char *v18; // [rsp+68h] [rbp+20h] BYREF

  v15 = this;
  v2 = (char *)this + 144;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  try
  {
    v18 = v2;
    if ( !*((_BYTE *)this + 104) )
    {
      if ( *((_DWORD *)this + 27) == 2 )
      {
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
            (void *)0x18C,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
            (const char *)(unsigned int)PersistedRegistryLocationAlloc,
            phkResult);
        hKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
        if ( v5 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x18F,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
            (const char *)v5,
            phkResult);
        v6 = RegDeleteValueW(hKey, L"SID");
        if ( v6 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
            (const char *)v6,
            phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      }
      if ( !*((_BYTE *)this + 56) )
      {
        v7 = (HSTRING)*((_QWORD *)this + 9);
        if ( v7
          && !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                              *((Microsoft::WRL::Wrappers::Details **)this + 8),
                              v7,
                              v3) )
        {
          v8 = Windows::System::Internal::UserProfile::RemoveConnectedProfile((Windows::System::Internal::UserProfile *)((char *)this - 24));
          if ( v8 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x195,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
              (const char *)(unsigned int)v8,
              phkResult);
          goto LABEL_18;
        }
        if ( !*((_BYTE *)this + 56) )
        {
          v11 = Windows::System::Internal::UserProfile::RemoveNTProfile((Windows::System::Internal::UserProfile *)((char *)this - 24));
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x19D,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
              (const char *)(unsigned int)v11,
              phkResult);
          goto LABEL_18;
        }
      }
      Windows::System::Internal::UserProfile::RemoveAADProfile((Windows::System::Internal::UserProfile *)((char *)this - 24));
    }
LABEL_18:
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v18);
    result = 0;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v9);
    LODWORD(hKey) = v12;
    if ( (v12 == -2147024751 || v12 == -2147024864) && !*((_BYTE *)v15 + 106) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v15,
        0);
      Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(*((_DWORD *)v15 + 15), (HKEY *)&v15);
      Windows::System::Internal::Implementation::RegUtil::WriteValue<unsigned long>(0, L"Dirty", 1);
      *((_BYTE *)v15 + 106) = 1;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    }
    return (unsigned int)hKey;
  }
  return result;
}

```

## disassembly

```asm
0x18004c560  mov     [rsp+arg_0], rcx
0x18004c565  push    rbx
0x18004c566  push    rdi
0x18004c567  sub     rsp, 38h
0x18004c56b  mov     rdi, rcx
0x18004c56e  lea     rbx, [rcx+90h]
0x18004c575  mov     rcx, rbx; lpCriticalSection
0x18004c578  call    cs:__imp_EnterCriticalSection
0x18004c57e  mov     [rsp+48h+arg_18], rbx
0x18004c583  lea     rbx, [rdi-18h]
0x18004c587  cmp     byte ptr [rbx+80h], 0
0x18004c58e  jnz     loc_18004C6D4
0x18004c594  cmp     dword ptr [rdi+6Ch], 2
0x18004c598  jnz     loc_18004C684
0x18004c59e  mov     [rsp+48h+lpSubKey], 0
0x18004c5a7  xor     edx, edx
0x18004c5a9  lea     rcx, [rsp+48h+lpSubKey]
0x18004c5ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004c5b3  lea     r8, [rsp+48h+lpSubKey]; unsigned __int16 **
0x18004c5b8  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Policies\\AppRestr"...
0x18004c5bf  lea     rcx, aResourceaccoun_3; "ResourceAccount"
0x18004c5c6  call    ?GetPersistedRegistryLocationAlloc@RegUtil@Implementation@Internal@System@Windows@@SAJPEBG0PEAPEAG@Z; Windows::System::Internal::Implementation::RegUtil::GetPersistedRegistryLocationAlloc(ushort const *,ushort const *,ushort * *)
0x18004c5cb  mov     rcx, [rsp+48h]; this
0x18004c5d0  test    eax, eax
0x18004c5d2  jns     short loc_18004C5E8
0x18004c5d4  mov     r9d, eax; char *
0x18004c5d7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c5de  mov     edx, 18Ch; void *
0x18004c5e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c5e8  mov     [rsp+48h+hKey], 0
0x18004c5f1  xor     edx, edx
0x18004c5f3  lea     rcx, [rsp+48h+hKey]
0x18004c5f8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c5fd  lea     rax, [rsp+48h+hKey]
0x18004c602  mov     qword ptr [rsp+48h+phkResult], rax; int
0x18004c607  mov     r9d, 20006h; samDesired
0x18004c60d  xor     r8d, r8d; ulOptions
0x18004c610  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x18004c615  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c61c  call    cs:__imp_RegOpenKeyExW
0x18004c622  mov     rcx, [rsp+48h]; this
0x18004c627  test    eax, eax
0x18004c629  jz      short loc_18004C63F
0x18004c62b  mov     r9d, eax; char *
0x18004c62e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c635  mov     edx, 18Fh; void *
0x18004c63a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004c63f  lea     rdx, aSid_1; "SID"
0x18004c646  mov     rcx, [rsp+48h+hKey]; hKey
0x18004c64b  call    cs:__imp_RegDeleteValueW
0x18004c651  mov     rcx, [rsp+48h]; this
0x18004c656  test    eax, eax
0x18004c658  jz      short loc_18004C66F
0x18004c65a  mov     r9d, eax; char *
0x18004c65d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c664  mov     edx, 190h; void *
0x18004c669  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004c66f  lea     rcx, [rsp+48h+hKey]
0x18004c674  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004c679  nop
0x18004c67a  lea     rcx, [rsp+48h+lpSubKey]
0x18004c67f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c684  cmp     byte ptr [rdi+38h], 0
0x18004c688  jnz     short loc_18004C6CB
0x18004c68a  mov     rdx, [rdi+48h]; HSTRING
0x18004c68e  test    rdx, rdx
0x18004c691  jz      short loc_18004C6C5
0x18004c693  mov     rcx, [rdi+40h]; this
0x18004c697  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18004c69c  test    eax, eax
0x18004c69e  jnz     short loc_18004C6C5
0x18004c6a0  mov     rcx, rbx; this
0x18004c6a3  call    ?RemoveConnectedProfile@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::RemoveConnectedProfile(void)
0x18004c6a8  mov     rcx, [rsp+48h]; this
0x18004c6ad  test    eax, eax
0x18004c6af  jns     short loc_18004C6D4
0x18004c6b1  mov     r9d, eax; char *
0x18004c6b4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c6bb  mov     edx, 195h; void *
0x18004c6c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c6c5  cmp     byte ptr [rdi+38h], 0
0x18004c6c9  jz      short loc_18004C6ED
0x18004c6cb  mov     rcx, rbx; this
0x18004c6ce  call    ?RemoveAADProfile@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::RemoveAADProfile(void)
0x18004c6d3  nop
0x18004c6d4  lea     rcx, [rsp+48h+arg_18]; this
0x18004c6d9  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x18004c6de  xor     eax, eax
0x18004c6e0  jmp     short loc_18004C6E6
0x18004c6e2  mov     eax, dword ptr [rsp+48h+hKey]
0x18004c6e6  add     rsp, 38h
0x18004c6ea  pop     rdi
0x18004c6eb  pop     rbx
0x18004c6ec  retn
0x18004c6ed  mov     rcx, rbx; this
0x18004c6f0  call    ?RemoveNTProfile@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::RemoveNTProfile(void)
0x18004c6f5  mov     rcx, [rsp+48h]; this
0x18004c6fa  test    eax, eax
0x18004c6fc  jns     short loc_18004C6D4
0x18004c6fe  mov     r9d, eax; char *
0x18004c701  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c708  mov     edx, 19Dh; void *
0x18004c70d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
