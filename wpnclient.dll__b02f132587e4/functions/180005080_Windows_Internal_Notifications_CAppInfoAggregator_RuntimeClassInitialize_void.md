# Windows::Internal::Notifications::CAppInfoAggregator::RuntimeClassInitialize(void)

- ea: `0x180005080`
- end: `0x180005661`
- name: `?RuntimeClassInitialize@CAppInfoAggregator@Notifications@Internal@Windows@@QEAAJXZ`
- size: `1505`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CAppInfoAggregator *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f88`

## callees

- `0x180004868`
- `0x180004e80`
- `0x180005080`
- `0x180005670`
- `0x18001459c`
- `0x180015b48`
- `0x1800180cc`
- `0x18001b848`
- `0x18001ff00`
- `0x180020d34`
- `0x180025700`
- `0x180025aa0`
- `0x1800271c4`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000560d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000560d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005361`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000537c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000537c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800053ac`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800053ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800050de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000527b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800050de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000527b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005307`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005140`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005140`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005211`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000531f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005605`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000531f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005605`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::Notifications::CAppInfoAggregator::RuntimeClassInitialize(
        Windows::Internal::Notifications::CAppInfoAggregator *this)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  const char *v4; // r9
  LPWSTR v5; // rdi
  unsigned __int64 v6; // rcx
  WCHAR *v7; // rax
  DWORD i; // r15d
  LSTATUS v9; // eax
  unsigned int v10; // eax
  PVOID Reserved1; // rsi
  HSTRING v12; // rdi
  HKEY v13; // r14
  int v14; // r14d
  const WCHAR *v15; // rdi
  unsigned __int64 v16; // rbx
  HSTRING v17; // rbx
  void *v18; // rdx
  int v19; // ebx
  unsigned int v20; // r8d
  HKEY v21; // rdi
  HKEY v22; // rbx
  _QWORD *v23; // rbx
  __int64 v24; // rsi
  __int64 result; // rax
  HKEY v26; // rcx
  size_t v27; // rbx
  DWORD LastError; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-F8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-F8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-F8h]
  int phkResultc; // [rsp+20h] [rbp-F8h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-B8h] BYREF
  HKEY v34; // [rsp+68h] [rbp-B0h] BYREF
  unsigned __int8 v35; // [rsp+70h] [rbp-A8h]
  DWORD cSubKeys; // [rsp+74h] [rbp-A4h] BYREF
  DWORD Type; // [rsp+78h] [rbp-A0h] BYREF
  HKEY v38; // [rsp+80h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-88h] BYREF
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
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\AppInfoProviders",
         0,
         0x20019u,
         &hKey);
  try
  {
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoaggregator.cpp",
        (const char *)v2,
        phkResult);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v3 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoaggregator.cpp",
        (const char *)v3,
        phkResulta);
    ++cbMaxSubKeyLen;
    if ( !cSubKeys )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoaggregator.cpp",
        (const char *)0x80070490LL,
        phkResulta);
    std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(lpName);
    v5 = lpName[1];
    v6 = lpName[1] - lpName[0];
    if ( cbMaxSubKeyLen < v6 )
    {
      v7 = &lpName[0][cbMaxSubKeyLen];
LABEL_7:
      lpName[1] = v7;
      goto LABEL_8;
    }
    if ( cbMaxSubKeyLen > v6 )
    {
      if ( cbMaxSubKeyLen <= (unsigned __int64)((signed __int64)(v42 - (unsigned __int64)lpName[0]) >> 1) )
      {
        v27 = cbMaxSubKeyLen - v6;
        memset_0(lpName[1], 0, v27 * 2);
        v7 = &v5[v27];
        goto LABEL_7;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpName, cbMaxSubKeyLen);
    }
LABEL_8:
    for ( i = 0; i < cSubKeys; ++i )
    {
      *lpName[0] = 0;
      cchName = cbMaxSubKeyLen;
      v9 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
      if ( v9 == 259 )
        break;
      if ( !v9 && *lpName[0] )
      {
        v34 = 0;
        string = (HSTRING)&v34;
        v48.Reserved.Reserved1 = 0;
        v48.Reserved.Reserved2[8] = 1;
        v10 = RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, (PHKEY)&v48);
        if ( v10 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
            (const char *)v10,
            phkResultb);
        if ( v48.Reserved.Reserved2[8] )
        {
          Reserved1 = v48.Reserved.Reserved1;
          v12 = string;
          v13 = *(HKEY *)string;
          if ( *(_QWORD *)string )
          {
            LastError = GetLastError();
            RegCloseKey(v13);
            SetLastError(LastError);
          }
          *(_QWORD *)v12 = Reserved1;
        }
        *(_DWORD *)Data = 0;
        cbData = 4;
        Type = 4;
        RegQueryValueExW(v34, L"priority", 0, &Type, Data, &cbData);
        v14 = *(_DWORD *)Data;
        if ( v34 )
          RegCloseKey(v34);
        v38 = 0;
        v15 = lpName[0];
        v16 = -1;
        do
          ++v16;
        while ( lpName[0][v16] );
        if ( v16 > 0xFFFFFFFF )
        {
          LODWORD(v16) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(v15, v16, &v48, &string);
        v17 = string;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v38 = 0;
        v34 = 0;
        v19 = RoActivateInstance(v17, &v34);
        if ( v19 >= 0 )
        {
          if ( !memcmp_0(&GUID_535aa053_78a8_438b_a1c9_94dcad4a6a67, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
          {
            v38 = v34;
          }
          else
          {
            v19 = (**(__int64 (__fastcall ***)(HKEY, GUID *, HKEY *))v34)(
                    v34,
                    &GUID_535aa053_78a8_438b_a1c9_94dcad4a6a67,
                    &v38);
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)v34 + 16LL))(v34);
          }
        }
        if ( v19 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(retaddr, v18, v20, (const char *)(unsigned int)v19, phkResultc);
          v23 = (_QWORD *)((char *)this + 72);
        }
        else
        {
          v21 = 0;
          v45 = 0;
          v46 = 0;
          v22 = v38;
          if ( v38 )
          {
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)v38 + 8LL))(v38);
            v21 = v22;
            v45 = v22;
          }
          LODWORD(v46) = v14;
          v23 = (_QWORD *)((char *)this + 72);
          v24 = *((_QWORD *)this + 10);
          if ( v24 == *((_QWORD *)this + 11) )
          {
            std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::_Emplace_reallocate<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord const &>(
              (char *)this + 72,
              *((_QWORD *)this + 10),
              &v45);
          }
          else
          {
            *(_QWORD *)v24 = v21;
            Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>::InternalAddRef(v24);
            *(_DWORD *)(v24 + 8) = v14;
            *((_QWORD *)this + 10) += 16LL;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        }
        std::_Sort_unchecked_Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord____lambda_82f5821a7b78b5e80faf9c371f0f5534___(
          *v23,
          *((_QWORD *)this + 10),
          (__int64)(*((_QWORD *)this + 10) - *v23) >> 4,
          v35);
        v26 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)v26 + 16LL))(v26);
        }
      }
    }
    if ( lpName[0] )
    {
      std::_Deallocate<16>(lpName[0], 2 * ((signed __int64)(v42 - (unsigned __int64)lpName[0]) >> 1));
      *(_OWORD *)lpName = 0;
      v42 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5D,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoaggregator.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180005080  mov     [rsp+arg_8], rbx
0x180005085  mov     [rsp+arg_10], rsi
0x18000508a  push    rdi
0x18000508b  push    r12
0x18000508d  push    r13
0x18000508f  push    r14
0x180005091  push    r15
0x180005093  sub     rsp, 0F0h
0x18000509a  mov     rax, cs:__security_cookie
0x1800050a1  xor     rax, rsp
0x1800050a4  mov     [rsp+118h+var_30], rax
0x1800050ac  mov     r13, rcx
0x1800050af  xor     r12d, r12d
0x1800050b2  mov     [rsp+118h+hKey], r12
0x1800050ba  lea     rax, [rsp+118h+hKey]
0x1800050c2  mov     [rsp+118h+phkResult], rax; unsigned int
0x1800050c7  mov     r9d, 20019h; samDesired
0x1800050cd  xor     r8d, r8d; ulOptions
0x1800050d0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800050d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800050de  call    cs:__imp_RegOpenKeyExW
0x1800050e4  mov     rcx, [rsp+118h]; this
0x1800050ec  test    eax, eax
0x1800050ee  jnz     loc_18000555B
0x1800050f4  mov     [rsp+118h+cSubKeys], r12d
0x1800050f9  mov     [rsp+118h+cbMaxSubKeyLen], r12d
0x1800050fe  mov     [rsp+118h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180005103  mov     [rsp+118h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180005108  mov     [rsp+118h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000510d  mov     [rsp+118h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180005112  mov     [rsp+118h+lpcValues], r12; lpcValues
0x180005117  mov     [rsp+118h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000511c  lea     rax, [rsp+118h+cbMaxSubKeyLen]
0x180005121  mov     [rsp+118h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180005126  lea     rax, [rsp+118h+cSubKeys]
0x18000512b  mov     [rsp+118h+phkResult], rax; int
0x180005130  xor     r9d, r9d; lpReserved
0x180005133  xor     r8d, r8d; lpcchClass
0x180005136  xor     edx, edx; lpClass
0x180005138  mov     rcx, [rsp+118h+hKey]; hKey
0x180005140  call    cs:__imp_RegQueryInfoKeyW
0x180005146  mov     rcx, [rsp+118h]; this
0x18000514e  test    eax, eax
0x180005150  jnz     loc_18000556F
0x180005156  inc     [rsp+118h+cbMaxSubKeyLen]
0x18000515a  cmp     [rsp+118h+cSubKeys], r12d
0x18000515f  setz    al
0x180005162  mov     rcx, [rsp+118h]; this
0x18000516a  test    al, al
0x18000516c  jnz     loc_180005583
0x180005172  lea     rcx, [rsp+118h+lpName]
0x18000517a  call    ??0?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(void)
0x18000517f  nop
0x180005180  mov     ebx, [rsp+118h+cbMaxSubKeyLen]
0x180005184  mov     rdx, [rsp+118h+lpName]
0x18000518c  mov     rdi, [rsp+118h+lpName+8]
0x180005194  mov     rcx, rdi
0x180005197  sub     rcx, rdx
0x18000519a  sar     rcx, 1
0x18000519d  cmp     rbx, rcx
0x1800051a0  jnb     loc_18000559B
0x1800051a6  lea     rax, [rdx+rbx*2]
0x1800051aa  mov     [rsp+118h+lpName+8], rax
0x1800051b2  mov     r15d, r12d
0x1800051b5  mov     esi, 0FFFFFFFFh
0x1800051ba  nop     word ptr [rax+rax+00h]
0x1800051c0  cmp     r15d, [rsp+118h+cSubKeys]
0x1800051c5  jnb     loc_180005468
0x1800051cb  mov     rax, [rsp+118h+lpName]
0x1800051d3  mov     [rax], r12w
0x1800051d7  mov     eax, [rsp+118h+cbMaxSubKeyLen]
0x1800051db  mov     [rsp+118h+cchName], eax
0x1800051e2  mov     [rsp+118h+lpcValues], r12; lpftLastWriteTime
0x1800051e7  mov     [rsp+118h+lpcbMaxClassLen], r12; lpcchClass
0x1800051ec  mov     [rsp+118h+lpcbMaxSubKeyLen], r12; lpClass
0x1800051f1  mov     [rsp+118h+phkResult], r12; lpReserved
0x1800051f6  lea     r9, [rsp+118h+cchName]; lpcchName
0x1800051fe  mov     r8, [rsp+118h+lpName]; lpName
0x180005206  mov     edx, r15d; dwIndex
0x180005209  mov     rcx, [rsp+118h+hKey]; hKey
0x180005211  call    cs:__imp_RegEnumKeyExW
0x180005217  cmp     eax, 103h
0x18000521c  jz      loc_180005468
0x180005222  test    eax, eax
0x180005224  jnz     loc_180005553
0x18000522a  mov     rdx, [rsp+118h+lpName]; lpSubKey
0x180005232  cmp     [rdx], ax
0x180005235  jz      loc_180005553
0x18000523b  mov     [rsp+118h+var_B0], r12
0x180005240  lea     rax, [rsp+118h+var_B0]
0x180005245  mov     [rsp+118h+string], rax
0x18000524d  mov     [rsp+118h+var_48], r12
0x180005255  mov     [rsp+118h+var_40], 1
0x18000525d  lea     rax, [rsp+118h+var_48]
0x180005265  mov     [rsp+118h+phkResult], rax; unsigned int
0x18000526a  mov     r9d, 20019h; samDesired
0x180005270  xor     r8d, r8d; ulOptions
0x180005273  mov     rcx, [rsp+118h+hKey]; hKey
0x18000527b  call    cs:__imp_RegOpenKeyExW
0x180005281  mov     rcx, [rsp+118h]; this
0x180005289  test    eax, eax
0x18000528b  jnz     loc_1800055E5
0x180005291  cmp     [rsp+118h+var_40], al
0x180005298  jz      short loc_1800052BE
0x18000529a  mov     rsi, [rsp+118h+var_48]
0x1800052a2  mov     rdi, [rsp+118h+string]
0x1800052aa  mov     r14, [rdi]
0x1800052ad  test    r14, r14
0x1800052b0  jnz     loc_1800055FA
0x1800052b6  mov     [rdi], rsi
0x1800052b9  mov     esi, 0FFFFFFFFh
0x1800052be  mov     dword ptr [rsp+118h+Data], r12d
0x1800052c6  mov     [rsp+118h+cbData], 4
0x1800052d1  mov     [rsp+118h+Type], 4
0x1800052d9  lea     rax, [rsp+118h+cbData]
0x1800052e1  mov     [rsp+118h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800052e6  lea     rax, [rsp+118h+Data]
0x1800052ee  mov     [rsp+118h+phkResult], rax; int
0x1800052f3  lea     r9, [rsp+118h+Type]; lpType
0x1800052f8  xor     r8d, r8d; lpReserved
0x1800052fb  lea     rdx, ValueName; "priority"
0x180005302  mov     rcx, [rsp+118h+var_B0]; hKey
0x180005307  call    cs:__imp_RegQueryValueExW
0x18000530d  mov     r14d, dword ptr [rsp+118h+Data]
0x180005315  mov     rcx, [rsp+118h+var_B0]; hKey
0x18000531a  test    rcx, rcx
0x18000531d  jz      short loc_180005325
0x18000531f  call    cs:__imp_RegCloseKey
0x180005325  mov     [rsp+118h+var_98], r12
0x18000532d  mov     rdi, [rsp+118h+lpName]
0x180005335  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000533c  nop     dword ptr [rax+00h]
0x180005340  inc     rbx
0x180005343  cmp     word ptr [rdi+rbx*2], 0
0x180005348  jnz     short loc_180005340
0x18000534a  cmp     rbx, rsi
0x18000534d  jbe     short loc_180005367
0x18000534f  mov     ebx, esi
0x180005351  xor     r9d, r9d; lpArguments
0x180005354  xor     r8d, r8d; nNumberOfArguments
0x180005357  mov     edx, 1; dwExceptionFlags
0x18000535c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180005361  call    cs:__imp_RaiseException
0x180005367  lea     r9, [rsp+118h+string]; string
0x18000536f  lea     r8, [rsp+118h+var_48]; hstringHeader
0x180005377  mov     edx, ebx; length
0x180005379  mov     rcx, rdi; sourceString
0x18000537c  call    cs:__imp_WindowsCreateStringReference
0x180005382  mov     rbx, [rsp+118h+string]
0x18000538a  lea     rcx, [rsp+118h+var_98]
0x180005392  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005397  mov     [rsp+118h+var_98], r12
0x18000539f  mov     [rsp+118h+var_B0], r12
0x1800053a4  lea     rdx, [rsp+118h+var_B0]
0x1800053a9  mov     rcx, rbx
0x1800053ac  call    cs:__imp_RoActivateInstance
0x1800053b2  mov     ebx, eax
0x1800053b4  test    eax, eax
0x1800053b6  js      short loc_1800053E6
0x1800053b8  mov     r8d, 10h; Size
0x1800053be  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800053c5  lea     rcx, _GUID_535aa053_78a8_438b_a1c9_94dcad4a6a67; Buf1
0x1800053cc  call    memcmp_0
0x1800053d1  mov     rcx, [rsp+118h+var_B0]
0x1800053d6  test    eax, eax
0x1800053d8  jnz     loc_1800054BC
0x1800053de  mov     [rsp+118h+var_98], rcx
0x1800053e6  mov     rcx, [rsp+118h]; this
0x1800053ee  test    ebx, ebx
0x1800053f0  js      loc_180005618
0x1800053f6  mov     rdi, r12
0x1800053f9  mov     [rsp+118h+var_60], r12
0x180005401  mov     [rsp+118h+var_58], r12
0x180005409  mov     rbx, [rsp+118h+var_98]
0x180005411  cmp     r12, rbx
0x180005414  jz      short loc_180005436
0x180005416  test    rbx, rbx
0x180005419  jz      short loc_18000542B
0x18000541b  mov     rax, [rbx]
0x18000541e  mov     rcx, rbx
0x180005421  mov     rax, [rax+8]
0x180005425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000542a  nop
0x18000542b  mov     rdi, rbx
0x18000542e  mov     [rsp+118h+var_60], rbx
0x180005436  mov     dword ptr [rsp+118h+var_58], r14d
0x18000543e  lea     rbx, [r13+48h]
0x180005442  mov     rsi, [rbx+8]
0x180005446  cmp     rsi, [rbx+10h]
0x18000544a  jnz     loc_1800054EE
0x180005450  lea     r8, [rsp+118h+var_60]
0x180005458  mov     rdx, rsi
0x18000545b  mov     rcx, rbx
0x18000545e  call    ??$_Emplace_reallocate@AEBUAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@AEAAPEAUAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@QEAU23456@AEBU23456@@Z; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::_Emplace_reallocate<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord const &>(Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord * const,Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord const &)
0x180005463  jmp     loc_180005502
0x180005468  mov     rcx, [rsp+118h+lpName]
0x180005470  test    rcx, rcx
0x180005473  jnz     loc_180005629
0x180005479  mov     rcx, [rsp+118h+hKey]; hKey
0x180005481  test    rcx, rcx
0x180005484  jz      short loc_18000548D
0x180005486  call    cs:__imp_RegCloseKey
0x18000548c  nop
0x18000548d  xor     eax, eax
0x18000548f  mov     rcx, [rsp+118h+var_30]
0x180005497  xor     rcx, rsp; StackCookie
0x18000549a  call    __security_check_cookie
0x18000549f  lea     r11, [rsp+118h+var_28]
0x1800054a7  mov     rbx, [r11+38h]
0x1800054ab  mov     rsi, [r11+40h]
0x1800054af  mov     rsp, r11
0x1800054b2  pop     r15
0x1800054b4  pop     r14
0x1800054b6  pop     r13
0x1800054b8  pop     r12
0x1800054ba  pop     rdi
0x1800054bb  retn
0x1800054bc  mov     rax, [rcx]
0x1800054bf  lea     r8, [rsp+118h+var_98]
0x1800054c7  lea     rdx, _GUID_535aa053_78a8_438b_a1c9_94dcad4a6a67
0x1800054ce  mov     rax, [rax]
0x1800054d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d6  mov     ebx, eax
0x1800054d8  mov     rcx, [rsp+118h+var_B0]
0x1800054dd  mov     rax, [rcx]
0x1800054e0  mov     rax, [rax+10h]
0x1800054e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e9  jmp     loc_1800053E6
0x1800054ee  mov     [rsi], rdi
0x1800054f1  mov     rcx, rsi
0x1800054f4  call    ?InternalAddRef@?$ComPtr@UIWpnToastActivator@Notifications@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>::InternalAddRef(void)
0x1800054f9  mov     [rsi+8], r14d
0x1800054fd  add     qword ptr [rbx+8], 10h
0x180005502  lea     rcx, [rsp+118h+var_60]
0x18000550a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000550f  mov     esi, 0FFFFFFFFh
0x180005514  mov     rdx, [r13+50h]
0x180005518  mov     rcx, [rbx]
0x18000551b  mov     r8, rdx
0x18000551e  sub     r8, rcx
0x180005521  sar     r8, 4
0x180005525  movzx   r9d, [rsp+118h+var_A8]
0x18000552b  call    std___Sort_unchecked_Windows__Internal__Notifications__CAppInfoAggregator__AppInfoRecord____lambda_82f5821a7b78b5e80faf9c371f0f5534___
0x180005530  nop
0x180005531  mov     rcx, [rsp+118h+var_98]
0x180005539  test    rcx, rcx
0x18000553c  jz      short loc_180005553
0x18000553e  mov     [rsp+118h+var_98], r12
0x180005546  mov     rax, [rcx]
0x180005549  mov     rax, [rax+10h]
0x18000554d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005552  nop
0x180005553  inc     r15d
0x180005556  jmp     loc_1800051C0
0x18000555b  mov     r9d, eax; char *
0x18000555e  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005565  mov     edx, 23h ; '#'; void *
0x18000556a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000556f  mov     r9d, eax; char *
0x180005572  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005579  mov     edx, 2Ah ; '*'; void *
0x18000557e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180005583  mov     r9d, 80070490h; char *
0x180005589  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005590  mov     edx, 2Fh ; '/'; void *
0x180005595  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000559b  jbe     loc_1800051B2
0x1800055a1  mov     rax, [rsp+118h+var_70]
0x1800055a9  sub     rax, rdx
0x1800055ac  sar     rax, 1
0x1800055af  cmp     rbx, rax
0x1800055b2  jbe     short loc_1800055C9
0x1800055b4  mov     rdx, rbx
0x1800055b7  lea     rcx, [rsp+118h+lpName]
0x1800055bf  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800055c4  jmp     loc_1800051B2
0x1800055c9  sub     rbx, rcx
0x1800055cc  add     rbx, rbx
0x1800055cf  mov     r8, rbx; Size
0x1800055d2  xor     edx, edx; Val
0x1800055d4  mov     rcx, rdi; void *
0x1800055d7  call    memset_0
0x1800055dc  lea     rax, [rbx+rdi]
0x1800055e0  jmp     loc_1800051AA
0x1800055e5  mov     r9d, eax; char *
0x1800055e8  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800055ef  mov     edx, 29h ; ')'; void *
0x1800055f4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800055fa  call    cs:__imp_GetLastError
0x180005600  mov     ebx, eax
0x180005602  mov     rcx, r14; hKey
0x180005605  call    cs:__imp_RegCloseKey
0x18000560b  mov     ecx, ebx; dwErrCode
0x18000560d  call    cs:__imp_SetLastError
0x180005613  jmp     loc_1800052B6
0x180005618  mov     r9d, ebx; char *
0x18000561b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005620  lea     rbx, [r13+48h]
0x180005624  jmp     loc_180005514
0x180005629  mov     rdx, [rsp+118h+var_70]
  ... truncated ...
```
