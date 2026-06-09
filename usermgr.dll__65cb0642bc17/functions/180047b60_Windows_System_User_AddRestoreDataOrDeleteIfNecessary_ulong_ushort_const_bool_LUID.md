# Windows::System::User::AddRestoreDataOrDeleteIfNecessary(ulong,ushort const *,bool,_LUID *)

- ea: `0x180047b60`
- end: `0x180047ee6`
- name: `?AddRestoreDataOrDeleteIfNecessary@User@System@Windows@@AEAAKKPEBG_NPEAU_LUID@@@Z`
- size: `902`
- prototype: `unsigned int(Windows::System::User *__hidden this, unsigned int, const unsigned __int16 *, bool, struct _LUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a3c0`
- `0x18004a240`

## callees

- `0x18000acdc`
- `0x180012890`
- `0x180015250`
- `0x180039c78`
- `0x18003d38c`
- `0x180047b60`
- `0x18004e508`
- `0x18004e58c`
- `0x18004e75c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180047bc8`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180047d93`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180047bc8`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180047d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047dd4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047dd4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047e2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047e2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047d63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047d63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047ccb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047d18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047ccb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047d18`
- `ntdll!RtlIsMultiSessionSku` at `0x180047bb1`
- `ntdll!RtlIsMultiSessionSku` at `0x180047bb1`

## string_xrefs

- `0x180047e3e`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047e56`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047e6b`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047e7d`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047e95`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047eaa`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047ebf`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x180047ed4`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::User::AddRestoreDataOrDeleteIfNecessary(
        Windows::System::User *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        char a4,
        struct _LUID *a5)
{
  const char *v8; // r9
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  const struct _tlgProvider_t *v14; // rax
  const char *v15; // r9
  unsigned int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  unsigned int v18; // eax
  int phkResult; // [rsp+20h] [rbp-51h]
  unsigned int phkResulta; // [rsp+20h] [rbp-51h]
  unsigned int phkResultb; // [rsp+20h] [rbp-51h]
  unsigned int phkResultc; // [rsp+20h] [rbp-51h]
  unsigned int phkResultd; // [rsp+20h] [rbp-51h]
  struct _LUID Luid; // [rsp+50h] [rbp-21h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-11h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-Dh] BYREF
  unsigned __int64 pvData; // [rsp+68h] [rbp-9h] BYREF
  HKEY v29; // [rsp+70h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+7h] BYREF
  WCHAR SubKey[12]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  hKey = 0;
  v29 = 0;
  hkey = 0;
  Luid = 0;
  pvData = 0;
  pcbData = 0;
  dwDisposition = 0;
  if ( !(unsigned __int8)RtlIsMultiSessionSku(this) )
  {
    if ( !a4 )
      goto LABEL_6;
    if ( !AllocateLocallyUniqueId(&Luid) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2DA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        v8);
    goto LABEL_4;
  }
  if ( a5 )
    *a5 = 0;
  v10 = StringCchPrintfW(SubKey, 0xAu, L"%d", a2);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
      (const char *)(unsigned int)v10,
      phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\VolatileUserMgrKey",
          0,
          0x2001Fu,
          &hKey);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
      (const char *)v11,
      phkResulta);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v29,
    0);
  v12 = RegCreateKeyExW(hKey, SubKey, 0, 0, 1u, 0xF003Fu, 0, &v29, &dwDisposition);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
      (const char *)v12,
      phkResultb);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v13 = RegCreateKeyExW(v29, a3, 0, 0, 1u, 0xF003Fu, 0, &hkey, &dwDisposition);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x308,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
      (const char *)v13,
      phkResultc);
  if ( a4 )
  {
    pcbData = 8;
    if ( RegGetValueW(hkey, 0, L"contextLuid", 0x20000040u, 0, &pvData, &pcbData) )
    {
      v14 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v14 > 2u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v14,
          qword_18012B480,
          0);
      if ( !AllocateLocallyUniqueId(&Luid) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x31C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          v15);
      pvData = Luid.LowPart | (unsigned __int64)((__int64)Luid.HighPart << 32);
      v16 = RegSetValueExW(hkey, L"contextLuid", 0, 0xBu, (const BYTE *)&pvData, 8u);
      if ( v16 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x325,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)v16,
          phkResultd);
    }
    else
    {
      v17 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v17 > 2u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v17,
          &unk_18012B450,
          0);
      Luid = (struct _LUID)pvData;
    }
LABEL_4:
    if ( a5 )
      *a5 = Luid;
    goto LABEL_6;
  }
  v18 = RegDeleteValueW(hkey, L"contextLuid");
  if ( v18 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x338,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
      (const char *)v18,
      phkResultc);
LABEL_6:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180047b60  mov     [rsp-8+arg_0], rbx
0x180047b65  push    rbp
0x180047b66  push    rsi
0x180047b67  push    rdi
0x180047b68  push    r14
0x180047b6a  push    r15
0x180047b6c  lea     rbp, [rsp-2Fh]
0x180047b71  sub     rsp, 0A0h
0x180047b78  mov     rax, cs:__security_cookie
0x180047b7f  xor     rax, rsp
0x180047b82  mov     [rbp+4Fh+var_28], rax
0x180047b86  mov     dil, r9b
0x180047b89  mov     r14, r8
0x180047b8c  mov     esi, edx
0x180047b8e  mov     rbx, [rbp+4Fh+arg_20]
0x180047b92  xor     r15d, r15d
0x180047b95  mov     [rbp+4Fh+hKey], r15
0x180047b99  mov     [rbp+4Fh+var_50], r15
0x180047b9d  mov     [rbp+4Fh+hkey], r15
0x180047ba1  mov     qword ptr [rbp+4Fh+Luid.LowPart], r15
0x180047ba5  mov     [rbp+4Fh+pvData], r15
0x180047ba9  mov     [rbp+4Fh+pcbData], r15d
0x180047bad  mov     [rbp+4Fh+dwDisposition], r15d
0x180047bb1  call    cs:__imp_RtlIsMultiSessionSku
0x180047bb7  test    al, al
0x180047bb9  jnz     short loc_180047C21
0x180047bbb  test    dil, dil
0x180047bbe  jz      short loc_180047BDF
0x180047bc0  mov     rdi, [rbp+57h]
0x180047bc4  lea     rcx, [rbp+4Fh+Luid]; Luid
0x180047bc8  call    cs:__imp_AllocateLocallyUniqueId
0x180047bce  test    eax, eax
0x180047bd0  jz      loc_180047E7D
0x180047bd6  test    rbx, rbx
0x180047bd9  jnz     loc_180047E18
0x180047bdf  lea     rcx, [rbp+4Fh+hkey]
0x180047be3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180047be8  nop
0x180047be9  lea     rcx, [rbp+4Fh+var_50]
0x180047bed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180047bf2  nop
0x180047bf3  lea     rcx, [rbp+4Fh+hKey]
0x180047bf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180047bfc  xor     eax, eax
0x180047bfe  mov     rcx, [rbp+4Fh+var_28]
0x180047c02  xor     rcx, rsp; StackCookie
0x180047c05  call    __security_check_cookie
0x180047c0a  mov     rbx, [rsp+0C0h+arg_0]
0x180047c12  add     rsp, 0A0h
0x180047c19  pop     r15
0x180047c1b  pop     r14
0x180047c1d  pop     rdi
0x180047c1e  pop     rsi
0x180047c1f  pop     rbp
0x180047c20  retn
0x180047c21  test    rbx, rbx
0x180047c24  jz      short loc_180047C29
0x180047c26  mov     [rbx], r15
0x180047c29  mov     r9d, esi
0x180047c2c  lea     r8, aD; "%d"
0x180047c33  mov     edx, 0Ah; unsigned __int64
0x180047c38  lea     rcx, [rbp+4Fh+SubKey]; unsigned __int16 *
0x180047c3c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047c41  mov     rcx, [rbp+57h]; this
0x180047c45  test    eax, eax
0x180047c47  js      loc_180047E92
0x180047c4d  xor     edx, edx
0x180047c4f  lea     rcx, [rbp+4Fh+hKey]
0x180047c53  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180047c58  lea     rax, [rbp+4Fh+hKey]
0x180047c5c  mov     [rsp+0C0h+phkResult], rax; unsigned int
0x180047c61  mov     r9d, 2001Fh; samDesired
0x180047c67  xor     r8d, r8d; ulOptions
0x180047c6a  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x180047c71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047c78  call    cs:__imp_RegOpenKeyExW
0x180047c7e  mov     rcx, [rbp+57h]; this
0x180047c82  test    eax, eax
0x180047c84  jnz     loc_180047EA7
0x180047c8a  xor     edx, edx
0x180047c8c  lea     rcx, [rbp+4Fh+var_50]
0x180047c90  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180047c95  lea     rax, [rbp+4Fh+dwDisposition]
0x180047c99  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180047c9e  lea     rax, [rbp+4Fh+var_50]
0x180047ca2  mov     [rsp+0C0h+var_88], rax; phkResult
0x180047ca7  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180047cac  mov     esi, 0F003Fh
0x180047cb1  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180047cb5  mov     dword ptr [rsp+0C0h+phkResult], 1; unsigned int
0x180047cbd  xor     r9d, r9d; lpClass
0x180047cc0  xor     r8d, r8d; Reserved
0x180047cc3  lea     rdx, [rbp+4Fh+SubKey]; lpSubKey
0x180047cc7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180047ccb  call    cs:__imp_RegCreateKeyExW
0x180047cd1  mov     rcx, [rbp+57h]; this
0x180047cd5  test    eax, eax
0x180047cd7  jnz     loc_180047EBC
0x180047cdd  xor     edx, edx
0x180047cdf  lea     rcx, [rbp+4Fh+hkey]
0x180047ce3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180047ce8  lea     rax, [rbp+4Fh+dwDisposition]
0x180047cec  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180047cf1  lea     rax, [rbp+4Fh+hkey]
0x180047cf5  mov     [rsp+0C0h+var_88], rax; phkResult
0x180047cfa  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180047cff  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180047d03  mov     dword ptr [rsp+0C0h+phkResult], 1; unsigned int
0x180047d0b  xor     r9d, r9d; lpClass
0x180047d0e  xor     r8d, r8d; Reserved
0x180047d11  mov     rdx, r14; lpSubKey
0x180047d14  mov     rcx, [rbp+4Fh+var_50]; hKey
0x180047d18  call    cs:__imp_RegCreateKeyExW
0x180047d1e  mov     rcx, [rbp+57h]; this
0x180047d22  test    eax, eax
0x180047d24  jnz     loc_180047ED1
0x180047d2a  mov     rcx, [rbp+4Fh+hkey]; hKey
0x180047d2e  test    dil, dil
0x180047d31  jz      loc_180047E24
0x180047d37  lea     esi, [rax+8]
0x180047d3a  mov     [rbp+4Fh+pcbData], esi
0x180047d3d  lea     rax, [rbp+4Fh+pcbData]
0x180047d41  mov     [rsp+0C0h+lpSecurityAttributes], rax; pcbData
0x180047d46  lea     rax, [rbp+4Fh+pvData]
0x180047d4a  mov     qword ptr [rsp+0C0h+samDesired], rax; pvData
0x180047d4f  mov     [rsp+0C0h+phkResult], r15; pdwType
0x180047d54  mov     r9d, 20000040h; dwFlags
0x180047d5a  lea     r8, aContextluid; "contextLuid"
0x180047d61  xor     edx, edx; lpSubKey
0x180047d63  call    cs:__imp_RegGetValueW
0x180047d69  test    eax, eax
0x180047d6b  jz      short loc_180047DE7
0x180047d6d  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180047d72  mov     ecx, [rax]
0x180047d74  cmp     ecx, 2
0x180047d77  jbe     short loc_180047D8B
0x180047d79  xor     r8d, r8d
0x180047d7c  lea     rdx, qword_18012B480
0x180047d83  mov     rcx, rax
0x180047d86  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180047d8b  mov     rdi, [rbp+57h]
0x180047d8f  lea     rcx, [rbp+4Fh+Luid]; Luid
0x180047d93  call    cs:__imp_AllocateLocallyUniqueId
0x180047d99  test    eax, eax
0x180047d9b  jz      loc_180047E3E
0x180047da1  movsxd  rcx, [rbp+4Fh+Luid.HighPart]
0x180047da5  shl     rcx, 20h
0x180047da9  mov     eax, [rbp+4Fh+Luid.LowPart]
0x180047dac  or      rcx, rax
0x180047daf  mov     [rbp+4Fh+pvData], rcx
0x180047db3  mov     [rsp+0C0h+samDesired], esi; cbData
0x180047db7  lea     rax, [rbp+4Fh+pvData]
0x180047dbb  mov     [rsp+0C0h+phkResult], rax; unsigned int
0x180047dc0  mov     r9d, 0Bh; dwType
0x180047dc6  xor     r8d, r8d; Reserved
0x180047dc9  lea     rdx, aContextluid; "contextLuid"
0x180047dd0  mov     rcx, [rbp+4Fh+hkey]; hKey
0x180047dd4  call    cs:__imp_RegSetValueExW
0x180047dda  mov     rcx, [rbp+57h]; this
0x180047dde  test    eax, eax
0x180047de0  jnz     short loc_180047E53
0x180047de2  jmp     loc_180047BD6
0x180047de7  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180047dec  mov     ecx, [rax]
0x180047dee  cmp     ecx, 2
0x180047df1  jbe     short loc_180047E05
0x180047df3  xor     r8d, r8d
0x180047df6  lea     rdx, unk_18012B450
0x180047dfd  mov     rcx, rax
0x180047e00  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180047e05  mov     rax, [rbp+4Fh+pvData]
0x180047e09  mov     [rbp+4Fh+Luid.LowPart], eax
0x180047e0c  shr     rax, 20h
0x180047e10  mov     [rbp+4Fh+Luid.HighPart], eax
0x180047e13  jmp     loc_180047BD6
0x180047e18  mov     rax, qword ptr [rbp+4Fh+Luid.LowPart]
0x180047e1c  mov     [rbx], rax
0x180047e1f  jmp     loc_180047BDF
0x180047e24  lea     rdx, aContextluid; "contextLuid"
0x180047e2b  call    cs:__imp_RegDeleteValueW
0x180047e31  mov     rcx, [rbp+57h]; this
0x180047e35  test    eax, eax
0x180047e37  jnz     short loc_180047E68
0x180047e39  jmp     loc_180047BDF
0x180047e3e  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047e45  mov     edx, 31Ch; void *
0x180047e4a  mov     rcx, rdi; this
0x180047e4d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180047e53  mov     r9d, eax; char *
0x180047e56  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047e5d  mov     edx, 325h; void *
0x180047e62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180047e68  mov     r9d, eax; char *
0x180047e6b  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047e72  mov     edx, 338h; void *
0x180047e77  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180047e7d  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047e84  mov     edx, 2DAh; void *
0x180047e89  mov     rcx, rdi; this
0x180047e8c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180047e92  mov     r9d, eax; char *
0x180047e95  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047e9c  mov     edx, 2E9h; void *
0x180047ea1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047ea7  mov     r9d, eax; char *
0x180047eaa  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047eb1  mov     edx, 2F1h; void *
0x180047eb6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180047ebc  mov     r9d, eax; char *
0x180047ebf  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047ec6  mov     edx, 2FDh; void *
0x180047ecb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180047ed1  mov     r9d, eax; char *
0x180047ed4  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\umstartup\\userm"...
0x180047edb  mov     edx, 308h; void *
0x180047ee0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
