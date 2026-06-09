# CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)

- ea: `0x18000a24c`
- end: `0x18000a466`
- name: `?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z`
- size: `538`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000a490`
- `0x18001c190`
- `0x1800bc720`

## callees

- `0x18000a24c`
- `0x18000a46c`
- `0x18000af00`
- `0x18000da00`
- `0x18001c020`
- `0x180037140`
- `0x18003729c`
- `0x180054130`
- `0x1800c09d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a371`

## string_xrefs

- `0x18000a2bd`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a336`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a388`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a3da`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a3b8`: `LoggedOnUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 **a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  BYTE *v10; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  HKEY v15; // [rsp+38h] [rbp-38h] BYREF
  BYTE *v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  WCHAR SubKey[8]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  *(_QWORD *)this = 0;
  hKey = 0;
  v15 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         9u,
         &v15);
  if ( !v3 )
  {
    v5 = StringCchPrintfW(SubKey, 8u, L"%d", NtCurrentPeb()->SessionId);
    v4 = v5;
    if ( v5 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v6 = RegOpenKeyExW(v15, SubKey, 0, 1u, &hKey);
      if ( v6 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x64,
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
               (const char *)v6,
               phkResulta);
      }
      else
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
               &v16,
               hKey,
               L"LoggedOnUserSID");
        v4 = v7;
        if ( v7 >= 0 )
        {
          v10 = v16;
          if ( v16 )
          {
            v16 = 0;
            v18 = 0;
            v17 = 0;
            *(_QWORD *)this = v10;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
            v4 = 0;
            goto LABEL_14;
          }
          v4 = -2147024882;
          v8 = 2147942414LL;
          v9 = 104;
        }
        else
        {
          v8 = (unsigned int)v7;
          v9 = 103;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
          (const char *)v8,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)v5,
        phkResult);
    }
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    return v4;
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x60,
         (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
         (const char *)v3,
         phkResult);
  if ( v15 )
    RegCloseKey(v15);
  return v4;
}

```

## disassembly

```asm
0x18000a24c  mov     [rsp-8+arg_8], rbx
0x18000a251  mov     [rsp-8+arg_10], rdi
0x18000a256  push    rbp
0x18000a257  mov     rbp, rsp
0x18000a25a  sub     rsp, 70h
0x18000a25e  mov     rax, cs:__security_cookie
0x18000a265  xor     rax, rsp
0x18000a268  mov     [rbp+var_8], rax
0x18000a26c  mov     rdi, rcx
0x18000a26f  mov     qword ptr [rcx], 0
0x18000a276  mov     [rbp+hKey], 0
0x18000a27e  mov     [rbp+var_38], 0
0x18000a286  lea     rax, [rbp+var_38]
0x18000a28a  mov     qword ptr [rsp+70h+phkResult], rax; int
0x18000a28f  mov     r9d, 9; samDesired
0x18000a295  xor     r8d, r8d; ulOptions
0x18000a298  lea     rdx, ?c_sessionDataKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a29f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a2a6  call    cs:__imp_RegOpenKeyExW
0x18000a2ad  nop     dword ptr [rax+rax+00h]
0x18000a2b2  test    eax, eax
0x18000a2b4  jz      short loc_18000A304
0x18000a2b6  mov     rcx, [rbp+8]; this
0x18000a2ba  mov     r9d, eax; char *
0x18000a2bd  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a2c4  mov     edx, 60h ; '`'; void *
0x18000a2c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a2ce  mov     ebx, eax
0x18000a2d0  mov     rcx, [rbp+hKey]; hKey
0x18000a2d4  test    rcx, rcx
0x18000a2d7  jz      short loc_18000A2E6
0x18000a2d9  call    cs:__imp_RegCloseKey
0x18000a2e0  nop     dword ptr [rax+rax+00h]
0x18000a2e5  nop
0x18000a2e6  mov     rcx, [rbp+var_38]; hKey
0x18000a2ea  test    rcx, rcx
0x18000a2ed  jz      loc_18000A445
0x18000a2f3  call    cs:__imp_RegCloseKey
0x18000a2fa  nop     dword ptr [rax+rax+00h]
0x18000a2ff  jmp     loc_18000A445
0x18000a304  mov     r9, gs:60h
0x18000a30d  mov     r9d, [r9+2C0h]
0x18000a314  lea     r8, aD; "%d"
0x18000a31b  mov     edx, 8; unsigned __int64
0x18000a320  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x18000a324  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a329  mov     ebx, eax
0x18000a32b  test    eax, eax
0x18000a32d  jns     short loc_18000A34C
0x18000a32f  mov     rcx, [rbp+8]; this
0x18000a333  mov     r9d, eax; char *
0x18000a336  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a33d  mov     edx, 63h ; 'c'; void *
0x18000a342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a347  jmp     loc_18000A432
0x18000a34c  xor     edx, edx
0x18000a34e  lea     rcx, [rbp+hKey]
0x18000a352  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a357  lea     rax, [rbp+hKey]
0x18000a35b  mov     qword ptr [rsp+70h+phkResult], rax; int
0x18000a360  mov     r9d, 1; samDesired
0x18000a366  xor     r8d, r8d; ulOptions
0x18000a369  lea     rdx, [rbp+SubKey]; lpSubKey
0x18000a36d  mov     rcx, [rbp+var_38]; hKey
0x18000a371  call    cs:__imp_RegOpenKeyExW
0x18000a378  nop     dword ptr [rax+rax+00h]
0x18000a37d  test    eax, eax
0x18000a37f  jz      short loc_18000A3A0
0x18000a381  mov     rcx, [rbp+8]; this
0x18000a385  mov     r9d, eax; char *
0x18000a388  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a38f  mov     edx, 64h ; 'd'; void *
0x18000a394  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a399  mov     ebx, eax
0x18000a39b  jmp     loc_18000A432
0x18000a3a0  mov     [rbp+var_30], 0
0x18000a3a8  mov     [rbp+var_28], 0
0x18000a3b0  mov     [rbp+var_20], 0
0x18000a3b8  lea     r8, ?c_loggedOnUserSid@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LoggedOnUserSID"
0x18000a3bf  mov     rdx, [rbp+hKey]
0x18000a3c3  lea     rcx, [rbp+var_30]
0x18000a3c7  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18000a3cc  mov     ebx, eax
0x18000a3ce  test    eax, eax
0x18000a3d0  jns     short loc_18000A3F6
0x18000a3d2  mov     r9d, eax; char *
0x18000a3d5  mov     edx, 67h ; 'g'; void *
0x18000a3da  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a3e1  mov     rcx, [rbp+8]; this
0x18000a3e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3ea  nop
0x18000a3eb  lea     rcx, [rbp+var_30]
0x18000a3ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a3f4  jmp     short loc_18000A432
0x18000a3f6  mov     rax, [rbp+var_30]
0x18000a3fa  test    rax, rax
0x18000a3fd  jnz     short loc_18000A40C
0x18000a3ff  mov     ebx, 8007000Eh
0x18000a404  mov     r9d, ebx
0x18000a407  lea     edx, [rax+68h]
0x18000a40a  jmp     short loc_18000A3DA
0x18000a40c  mov     [rbp+var_30], 0
0x18000a414  mov     [rbp+var_20], 0
0x18000a41c  mov     [rbp+var_28], 0
0x18000a424  mov     [rdi], rax
0x18000a427  lea     rcx, [rbp+var_30]
0x18000a42b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a430  xor     ebx, ebx
0x18000a432  lea     rcx, [rbp+hKey]
0x18000a436  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a43b  nop
0x18000a43c  lea     rcx, [rbp+var_38]
0x18000a440  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a445  mov     eax, ebx
0x18000a447  mov     rcx, [rbp+var_8]
0x18000a44b  xor     rcx, rsp; StackCookie
0x18000a44e  call    __security_check_cookie
0x18000a453  lea     r11, [rsp+70h+var_s0]
0x18000a458  mov     rbx, [r11+18h]
0x18000a45c  mov     rdi, [r11+20h]
0x18000a460  mov     rsp, r11
0x18000a463  pop     rbp
0x18000a464  retn
```
