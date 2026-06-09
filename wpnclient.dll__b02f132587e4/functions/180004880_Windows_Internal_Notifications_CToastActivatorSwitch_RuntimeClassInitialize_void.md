# Windows::Internal::Notifications::CToastActivatorSwitch::RuntimeClassInitialize(void)

- ea: `0x180004880`
- end: `0x180004e79`
- name: `?RuntimeClassInitialize@CToastActivatorSwitch@Notifications@Internal@Windows@@QEAAJXZ`
- size: `1529`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivatorSwitch *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015030`

## callees

- `0x180004868`
- `0x180004880`
- `0x180004e80`
- `0x1800070e8`
- `0x18001459c`
- `0x1800180cc`
- `0x18001b4e0`
- `0x18001b8e0`
- `0x18001ff00`
- `0x180020d34`
- `0x180025700`
- `0x180025aa0`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004b41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004b5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004b5c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180004b98`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180004b98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a57`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004940`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004940`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800049f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800049f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e0a`

## string_xrefs

- `0x1800048d0`: `Software\Microsoft\Windows\CurrentVersion\PushNotifications\ActivationPlugins`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::Notifications::CToastActivatorSwitch::RuntimeClassInitialize(
        Windows::Internal::Notifications::CToastActivatorSwitch *this)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  LPWSTR v6; // rdi
  unsigned __int64 v7; // rcx
  WCHAR *v8; // rax
  DWORD i; // r15d
  LSTATUS v10; // eax
  unsigned int v11; // eax
  PVOID Reserved1; // rsi
  HSTRING v13; // rdi
  HKEY v14; // r14
  int v15; // r14d
  const WCHAR *v16; // rdi
  unsigned __int64 v17; // rbx
  HSTRING v18; // rbx
  HKEY v19; // rcx
  int v20; // ebx
  HKEY v21; // rbx
  HKEY v22; // rdi
  __int64 v23; // rsi
  HKEY v24; // rcx
  const char *v25; // r9
  __int64 result; // rax
  unsigned int v27; // ebx
  size_t v28; // rbx
  DWORD LastError; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-F8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-F8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-F8h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-B8h] BYREF
  HKEY v34; // [rsp+68h] [rbp-B0h] BYREF
  HKEY v35; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int8 v36; // [rsp+78h] [rbp-A0h]
  DWORD cSubKeys; // [rsp+7Ch] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+80h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-88h] BYREF
  LPWSTR lpName[2]; // [rsp+98h] [rbp-80h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-70h]
  DWORD cchName; // [rsp+B0h] [rbp-68h] BYREF
  DWORD cbData; // [rsp+B4h] [rbp-64h] BYREF
  HKEY v45; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-58h]
  HSTRING string; // [rsp+C8h] [rbp-50h] BYREF
  HSTRING_HEADER v48; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\ActivationPlugins",
         0,
         0x20019u,
         &hKey);
  try
  {
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivatorswitch.cpp",
        (const char *)v2,
        phkResult);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v3 )
    {
      v27 = wil::details::in1diag3::Return_Win32(retaddr, v4, v5, (const char *)v3, phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      result = v27;
    }
    else
    {
      ++cbMaxSubKeyLen;
      if ( cSubKeys )
      {
        std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(lpName);
        v6 = lpName[1];
        v7 = lpName[1] - lpName[0];
        if ( cbMaxSubKeyLen < v7 )
        {
          v8 = &lpName[0][cbMaxSubKeyLen];
LABEL_7:
          lpName[1] = v8;
          goto LABEL_8;
        }
        if ( cbMaxSubKeyLen > v7 )
        {
          if ( cbMaxSubKeyLen <= (unsigned __int64)((signed __int64)(v42 - (unsigned __int64)lpName[0]) >> 1) )
          {
            v28 = cbMaxSubKeyLen - v7;
            memset_0(lpName[1], 0, v28 * 2);
            v8 = &v6[v28];
            goto LABEL_7;
          }
          std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpName, cbMaxSubKeyLen);
        }
LABEL_8:
        for ( i = 0; i < cSubKeys; ++i )
        {
          *lpName[0] = 0;
          cchName = cbMaxSubKeyLen;
          v10 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
          if ( v10 == 259 )
            break;
          if ( !v10 )
          {
            v35 = 0;
            string = (HSTRING)&v35;
            v48.Reserved.Reserved1 = 0;
            v48.Reserved.Reserved2[8] = 1;
            v11 = RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, (PHKEY)&v48);
            if ( v11 )
              wil::details::in1diag3::_Throw_Win32(
                retaddr,
                (void *)0x29,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
                (const char *)v11,
                phkResultb);
            if ( v48.Reserved.Reserved2[8] )
            {
              Reserved1 = v48.Reserved.Reserved1;
              v13 = string;
              v14 = *(HKEY *)string;
              if ( *(_QWORD *)string )
              {
                LastError = GetLastError();
                RegCloseKey(v14);
                SetLastError(LastError);
              }
              *(_QWORD *)v13 = Reserved1;
            }
            *(_DWORD *)Data = 0;
            cbData = 4;
            Type = 4;
            RegQueryValueExW(v35, L"priority", 0, &Type, Data, &cbData);
            v15 = *(_DWORD *)Data;
            if ( v35 )
              RegCloseKey(v35);
            v34 = 0;
            v16 = lpName[0];
            v17 = -1;
            do
              ++v17;
            while ( lpName[0][v17] );
            if ( v17 > 0xFFFFFFFF )
            {
              LODWORD(v17) = -1;
              RaiseException(0xC000000D, 1u, 0, 0);
            }
            WindowsCreateStringReference(v16, v17, &v48, &string);
            v18 = string;
            v19 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)v19 + 16LL))(v19);
            }
            v34 = 0;
            v35 = 0;
            v20 = RoActivateInstance(v18, &v35);
            if ( v20 >= 0 )
            {
              if ( !memcmp_0(
                      &GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b,
                      &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                      0x10u) )
              {
                v34 = v35;
              }
              else
              {
                v20 = (**(__int64 (__fastcall ***)(HKEY, GUID *, HKEY *))v35)(
                        v35,
                        &GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b,
                        &v34);
                (*(void (__fastcall **)(HKEY))(*(_QWORD *)v35 + 16LL))(v35);
              }
            }
            if ( v20 >= 0 )
            {
              v21 = 0;
              v45 = 0;
              v46 = 0;
              v22 = v34;
              if ( v34 )
              {
                (*(void (__fastcall **)(HKEY))(*(_QWORD *)v34 + 8LL))(v34);
                v21 = v22;
                v45 = v22;
              }
              LODWORD(v46) = v15;
              v23 = *((_QWORD *)this + 10);
              if ( v23 == *((_QWORD *)this + 11) )
              {
                std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::_Emplace_reallocate<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord const &>(
                  (char *)this + 72,
                  *((_QWORD *)this + 10),
                  &v45);
                v21 = v45;
              }
              else
              {
                *(_QWORD *)v23 = v21;
                Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>::InternalAddRef(v23);
                *(_DWORD *)(v23 + 8) = v15;
                *((_QWORD *)this + 10) += 16LL;
              }
              if ( v21 )
              {
                v45 = 0;
                (*(void (__fastcall **)(HKEY))(*(_QWORD *)v21 + 16LL))(v21);
              }
            }
            v24 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)v24 + 16LL))(v24);
            }
          }
        }
        std::_Sort_unchecked_Windows::Internal::Notifications::CToastActivatorSwitch::ActivatorRecord____lambda_65877b2b2c69831d27d64bc64a3c3fc4___(
          *((_QWORD *)this + 9),
          *((_QWORD *)this + 10),
          (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 4,
          v36);
        if ( lpName[0] )
        {
          std::_Deallocate<16>(lpName[0], 2 * ((signed __int64)(v42 - (unsigned __int64)lpName[0]) >> 1));
          *(_OWORD *)lpName = 0;
          v42 = 0;
        }
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivatorswitch.cpp",
        (const char *)0x80070490LL,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      result = 2147943568LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x60,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivatorswitch.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x180004880  mov     [rsp+arg_8], rbx
0x180004885  mov     [rsp+arg_10], rsi
0x18000488a  push    rdi
0x18000488b  push    r12
0x18000488d  push    r13
0x18000488f  push    r14
0x180004891  push    r15
0x180004893  sub     rsp, 0F0h
0x18000489a  mov     rax, cs:__security_cookie
0x1800048a1  xor     rax, rsp
0x1800048a4  mov     [rsp+118h+var_30], rax
0x1800048ac  mov     r13, rcx
0x1800048af  xor     r12d, r12d
0x1800048b2  mov     [rsp+118h+hKey], r12
0x1800048ba  lea     rax, [rsp+118h+hKey]
0x1800048c2  mov     [rsp+118h+phkResult], rax; unsigned int
0x1800048c7  mov     r9d, 20019h; samDesired
0x1800048cd  xor     r8d, r8d; ulOptions
0x1800048d0  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800048d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048de  call    cs:__imp_RegOpenKeyExW
0x1800048e4  mov     rcx, [rsp+118h]; this
0x1800048ec  test    eax, eax
0x1800048ee  jnz     loc_180004D8B
0x1800048f4  mov     [rsp+118h+cSubKeys], r12d
0x1800048f9  mov     [rsp+118h+cbMaxSubKeyLen], r12d
0x1800048fe  mov     [rsp+118h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180004903  mov     [rsp+118h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180004908  mov     [rsp+118h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000490d  mov     [rsp+118h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180004912  mov     [rsp+118h+lpcValues], r12; lpcValues
0x180004917  mov     [rsp+118h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000491c  lea     rax, [rsp+118h+cbMaxSubKeyLen]
0x180004921  mov     [rsp+118h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180004926  lea     rax, [rsp+118h+cSubKeys]
0x18000492b  mov     [rsp+118h+phkResult], rax; int
0x180004930  xor     r9d, r9d; lpReserved
0x180004933  xor     r8d, r8d; lpcchClass
0x180004936  xor     edx, edx; lpClass
0x180004938  mov     rcx, [rsp+118h+hKey]; hKey
0x180004940  call    cs:__imp_RegQueryInfoKeyW
0x180004946  test    eax, eax
0x180004948  jnz     loc_180004D25
0x18000494e  inc     [rsp+118h+cbMaxSubKeyLen]
0x180004952  cmp     [rsp+118h+cSubKeys], r12d
0x180004957  jz      loc_180004D4E
0x18000495d  lea     rcx, [rsp+118h+lpName]
0x180004965  call    ??0?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(void)
0x18000496a  nop
0x18000496b  mov     ebx, [rsp+118h+cbMaxSubKeyLen]
0x18000496f  mov     rdx, [rsp+118h+lpName]
0x180004977  mov     rdi, [rsp+118h+lpName+8]
0x18000497f  mov     rcx, rdi
0x180004982  sub     rcx, rdx
0x180004985  sar     rcx, 1
0x180004988  cmp     rbx, rcx
0x18000498b  jnb     loc_180004DA0
0x180004991  lea     rax, [rdx+rbx*2]
0x180004995  mov     [rsp+118h+lpName+8], rax
0x18000499d  mov     r15d, r12d
0x1800049a0  mov     esi, 0FFFFFFFFh
0x1800049a5  cmp     r15d, [rsp+118h+cSubKeys]
0x1800049aa  jnb     loc_180004CB3
0x1800049b0  mov     rax, [rsp+118h+lpName]
0x1800049b8  mov     [rax], r12w
0x1800049bc  mov     eax, [rsp+118h+cbMaxSubKeyLen]
0x1800049c0  mov     [rsp+118h+cchName], eax
0x1800049c7  mov     [rsp+118h+lpcValues], r12; lpftLastWriteTime
0x1800049cc  mov     [rsp+118h+lpcbMaxClassLen], r12; lpcchClass
0x1800049d1  mov     [rsp+118h+lpcbMaxSubKeyLen], r12; lpClass
0x1800049d6  mov     [rsp+118h+phkResult], r12; lpReserved
0x1800049db  lea     r9, [rsp+118h+cchName]; lpcchName
0x1800049e3  mov     r8, [rsp+118h+lpName]; lpName
0x1800049eb  mov     edx, r15d; dwIndex
0x1800049ee  mov     rcx, [rsp+118h+hKey]; hKey
0x1800049f6  call    cs:__imp_RegEnumKeyExW
0x1800049fc  cmp     eax, 103h
0x180004a01  jz      loc_180004CB3
0x180004a07  test    eax, eax
0x180004a09  jnz     loc_180004C7C
0x180004a0f  mov     [rsp+118h+var_A8], r12
0x180004a14  lea     rax, [rsp+118h+var_A8]
0x180004a19  mov     [rsp+118h+string], rax
0x180004a21  mov     [rsp+118h+var_48], r12
0x180004a29  mov     [rsp+118h+var_40], 1
0x180004a31  lea     rax, [rsp+118h+var_48]
0x180004a39  mov     [rsp+118h+phkResult], rax; unsigned int
0x180004a3e  mov     r9d, 20019h; samDesired
0x180004a44  xor     r8d, r8d; ulOptions
0x180004a47  mov     rdx, [rsp+118h+lpName]; lpSubKey
0x180004a4f  mov     rcx, [rsp+118h+hKey]; hKey
0x180004a57  call    cs:__imp_RegOpenKeyExW
0x180004a5d  mov     rcx, [rsp+118h]; this
0x180004a65  test    eax, eax
0x180004a67  jnz     loc_180004DEA
0x180004a6d  cmp     [rsp+118h+var_40], al
0x180004a74  jz      short loc_180004A9A
0x180004a76  mov     rsi, [rsp+118h+var_48]
0x180004a7e  mov     rdi, [rsp+118h+string]
0x180004a86  mov     r14, [rdi]
0x180004a89  test    r14, r14
0x180004a8c  jnz     loc_180004DFF
0x180004a92  mov     [rdi], rsi
0x180004a95  mov     esi, 0FFFFFFFFh
0x180004a9a  mov     dword ptr [rsp+118h+Data], r12d
0x180004aa2  mov     [rsp+118h+cbData], 4
0x180004aad  mov     [rsp+118h+Type], 4
0x180004ab8  lea     rax, [rsp+118h+cbData]
0x180004ac0  mov     [rsp+118h+lpcbMaxSubKeyLen], rax; lpcbData
0x180004ac5  lea     rax, [rsp+118h+Data]
0x180004acd  mov     [rsp+118h+phkResult], rax; lpData
0x180004ad2  lea     r9, [rsp+118h+Type]; lpType
0x180004ada  xor     r8d, r8d; lpReserved
0x180004add  lea     rdx, ValueName; "priority"
0x180004ae4  mov     rcx, [rsp+118h+var_A8]; hKey
0x180004ae9  call    cs:__imp_RegQueryValueExW
0x180004aef  mov     r14d, dword ptr [rsp+118h+Data]
0x180004af7  mov     rcx, [rsp+118h+var_A8]; hKey
0x180004afc  test    rcx, rcx
0x180004aff  jz      short loc_180004B07
0x180004b01  call    cs:__imp_RegCloseKey
0x180004b07  mov     [rsp+118h+var_B0], r12
0x180004b0c  mov     rdi, [rsp+118h+lpName]
0x180004b14  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004b1b  nop     dword ptr [rax+rax+00h]
0x180004b20  inc     rbx
0x180004b23  cmp     word ptr [rdi+rbx*2], 0
0x180004b28  jnz     short loc_180004B20
0x180004b2a  cmp     rbx, rsi
0x180004b2d  jbe     short loc_180004B47
0x180004b2f  mov     ebx, esi
0x180004b31  xor     r9d, r9d; lpArguments
0x180004b34  xor     r8d, r8d; nNumberOfArguments
0x180004b37  mov     edx, 1; dwExceptionFlags
0x180004b3c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180004b41  call    cs:__imp_RaiseException
0x180004b47  lea     r9, [rsp+118h+string]; string
0x180004b4f  lea     r8, [rsp+118h+var_48]; hstringHeader
0x180004b57  mov     edx, ebx; length
0x180004b59  mov     rcx, rdi; sourceString
0x180004b5c  call    cs:__imp_WindowsCreateStringReference
0x180004b62  mov     rbx, [rsp+118h+string]
0x180004b6a  mov     rcx, [rsp+118h+var_B0]
0x180004b6f  test    rcx, rcx
0x180004b72  jz      short loc_180004B86
0x180004b74  mov     [rsp+118h+var_B0], r12
0x180004b79  mov     rax, [rcx]
0x180004b7c  mov     rax, [rax+10h]
0x180004b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b85  nop
0x180004b86  mov     [rsp+118h+var_B0], r12
0x180004b8b  mov     [rsp+118h+var_A8], r12
0x180004b90  lea     rdx, [rsp+118h+var_A8]
0x180004b95  mov     rcx, rbx
0x180004b98  call    cs:__imp_RoActivateInstance
0x180004b9e  mov     ebx, eax
0x180004ba0  test    eax, eax
0x180004ba2  js      short loc_180004BCF
0x180004ba4  mov     r8d, 10h; Size
0x180004baa  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180004bb1  lea     rcx, _GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b; Buf1
0x180004bb8  call    memcmp_0
0x180004bbd  mov     rcx, [rsp+118h+var_A8]
0x180004bc2  test    eax, eax
0x180004bc4  jnz     loc_180004C84
0x180004bca  mov     [rsp+118h+var_B0], rcx
0x180004bcf  test    ebx, ebx
0x180004bd1  js      loc_180004C60
0x180004bd7  mov     rbx, r12
0x180004bda  mov     [rsp+118h+var_60], rbx
0x180004be2  mov     [rsp+118h+var_58], r12
0x180004bea  mov     rdi, [rsp+118h+var_B0]
0x180004bef  cmp     r12, rdi
0x180004bf2  jz      short loc_180004C14
0x180004bf4  test    rdi, rdi
0x180004bf7  jz      short loc_180004C09
0x180004bf9  mov     rax, [rdi]
0x180004bfc  mov     rcx, rdi
0x180004bff  mov     rax, [rax+8]
0x180004c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c08  nop
0x180004c09  mov     rbx, rdi
0x180004c0c  mov     [rsp+118h+var_60], rbx
0x180004c14  mov     dword ptr [rsp+118h+var_58], r14d
0x180004c1c  mov     rsi, [r13+50h]
0x180004c20  cmp     rsi, [r13+58h]
0x180004c24  jz      loc_180004E1D
0x180004c2a  mov     [rsi], rbx
0x180004c2d  mov     rcx, rsi
0x180004c30  call    ?InternalAddRef@?$ComPtr@UIWpnToastActivator@Notifications@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>::InternalAddRef(void)
0x180004c35  mov     [rsi+8], r14d
0x180004c39  add     qword ptr [r13+50h], 10h
0x180004c3e  test    rbx, rbx
0x180004c41  jz      short loc_180004C5B
0x180004c43  mov     [rsp+118h+var_60], r12
0x180004c4b  mov     rax, [rbx]
0x180004c4e  mov     rcx, rbx
0x180004c51  mov     rax, [rax+10h]
0x180004c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5a  nop
0x180004c5b  mov     esi, 0FFFFFFFFh
0x180004c60  mov     rcx, [rsp+118h+var_B0]
0x180004c65  test    rcx, rcx
0x180004c68  jz      short loc_180004C7C
0x180004c6a  mov     [rsp+118h+var_B0], r12
0x180004c6f  mov     rax, [rcx]
0x180004c72  mov     rax, [rax+10h]
0x180004c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c7b  nop
0x180004c7c  inc     r15d
0x180004c7f  jmp     loc_1800049A5
0x180004c84  mov     rax, [rcx]
0x180004c87  lea     r8, [rsp+118h+var_B0]
0x180004c8c  lea     rdx, _GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b
0x180004c93  mov     rax, [rax]
0x180004c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c9b  mov     ebx, eax
0x180004c9d  mov     rcx, [rsp+118h+var_A8]
0x180004ca2  mov     rax, [rcx]
0x180004ca5  mov     rax, [rax+10h]
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  jmp     loc_180004BCF
0x180004cb3  mov     rdx, [r13+50h]
0x180004cb7  mov     rcx, [r13+48h]
0x180004cbb  mov     r8, rdx
0x180004cbe  sub     r8, rcx
0x180004cc1  sar     r8, 4
0x180004cc5  movzx   r9d, [rsp+118h+var_A0]
0x180004ccb  call    std___Sort_unchecked_Windows__Internal__Notifications__CToastActivatorSwitch__ActivatorRecord____lambda_65877b2b2c69831d27d64bc64a3c3fc4___
0x180004cd0  nop
0x180004cd1  mov     rcx, [rsp+118h+lpName]
0x180004cd9  test    rcx, rcx
0x180004cdc  jnz     loc_180004E3E
0x180004ce2  mov     rcx, [rsp+118h+hKey]; hKey
0x180004cea  test    rcx, rcx
0x180004ced  jz      short loc_180004CF6
0x180004cef  call    cs:__imp_RegCloseKey
0x180004cf5  nop
0x180004cf6  xor     eax, eax
0x180004cf8  mov     rcx, [rsp+118h+var_30]
0x180004d00  xor     rcx, rsp; StackCookie
0x180004d03  call    __security_check_cookie
0x180004d08  lea     r11, [rsp+118h+var_28]
0x180004d10  mov     rbx, [r11+38h]
0x180004d14  mov     rsi, [r11+40h]
0x180004d18  mov     rsp, r11
0x180004d1b  pop     r15
0x180004d1d  pop     r14
0x180004d1f  pop     r13
0x180004d21  pop     r12
0x180004d23  pop     rdi
0x180004d24  retn
0x180004d25  mov     rcx, [rsp+118h]; this
0x180004d2d  mov     r9d, eax; char *
0x180004d30  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004d35  mov     ebx, eax
0x180004d37  mov     rcx, [rsp+118h+hKey]; hKey
0x180004d3f  test    rcx, rcx
0x180004d42  jz      short loc_180004D4A
0x180004d44  call    cs:__imp_RegCloseKey
0x180004d4a  mov     eax, ebx
0x180004d4c  jmp     short loc_180004CF8
0x180004d4e  mov     rcx, [rsp+118h]; this
0x180004d56  mov     r9d, 80070490h; char *
0x180004d5c  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004d63  mov     edx, 33h ; '3'; void *
0x180004d68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d6d  nop
0x180004d6e  mov     rcx, [rsp+118h+hKey]; hKey
0x180004d76  test    rcx, rcx
0x180004d79  jz      short loc_180004D81
0x180004d7b  call    cs:__imp_RegCloseKey
0x180004d81  mov     eax, 80070490h
0x180004d86  jmp     loc_180004CF8
0x180004d8b  mov     r9d, eax; char *
0x180004d8e  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004d95  mov     edx, 27h ; '''; void *
0x180004d9a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180004da0  jbe     loc_18000499D
0x180004da6  mov     rax, [rsp+118h+var_70]
0x180004dae  sub     rax, rdx
0x180004db1  sar     rax, 1
0x180004db4  cmp     rbx, rax
0x180004db7  jbe     short loc_180004DCE
0x180004db9  mov     rdx, rbx
0x180004dbc  lea     rcx, [rsp+118h+lpName]
0x180004dc4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180004dc9  jmp     loc_18000499D
0x180004dce  sub     rbx, rcx
0x180004dd1  add     rbx, rbx
0x180004dd4  mov     r8, rbx; Size
0x180004dd7  xor     edx, edx; Val
0x180004dd9  mov     rcx, rdi; void *
0x180004ddc  call    memset_0
0x180004de1  lea     rax, [rbx+rdi]
0x180004de5  jmp     loc_180004995
0x180004dea  mov     r9d, eax; char *
0x180004ded  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004df4  mov     edx, 29h ; ')'; void *
0x180004df9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
  ... truncated ...
```
