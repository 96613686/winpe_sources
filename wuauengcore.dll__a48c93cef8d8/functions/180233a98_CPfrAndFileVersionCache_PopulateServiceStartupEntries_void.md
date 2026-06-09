# CPfrAndFileVersionCache::PopulateServiceStartupEntries(void)

- ea: `0x180233a98`
- end: `0x180233ee8`
- name: `?PopulateServiceStartupEntries@CPfrAndFileVersionCache@@AEAAJXZ`
- size: `1104`
- prototype: `__int64 __fastcall(CPfrAndFileVersionCache *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180234820`

## callees

- `0x18003a6c4`
- `0x180113a10`
- `0x180113ae8`
- `0x18012d780`
- `0x1802335cc`
- `0x180233a98`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233cf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233e1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233cf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233e1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233eb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233b1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233d4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233b1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180233d4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233c54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233cb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233de1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233c54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233cb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180233de1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180233bad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180233e77`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180233bad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180233e77`

## string_xrefs

- `0x180233d7a`: `CacheFile`
- `0x180233dda`: `CacheFile`
- `0x180233b0c`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Setup\ServiceStartup\`
- `0x180233b54`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Setup\ServiceStartup\`

## pseudocode

```c
__int64 __fastcall CPfrAndFileVersionCache::PopulateServiceStartupEntries(CPfrAndFileVersionCache *this)
{
  char *v1; // rdi
  signed int v2; // ebx
  DWORD v3; // r13d
  LSTATUS v4; // eax
  __int64 v5; // rax
  DWORD v6; // r15d
  WCHAR *v7; // r12
  BYTE *v8; // r14
  LSTATUS v9; // eax
  LSTATUS v10; // ecx
  DWORD v11; // eax
  LSTATUS v12; // eax
  REGSAM samDesired[2]; // [rsp+48h] [rbp-C0h] BYREF
  CPfrAndFileVersionCache *v15; // [rsp+50h] [rbp-B8h]
  DWORD cbData[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+70h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-94h] BYREF
  WCHAR SubKey[264]; // [rsp+78h] [rbp-90h] BYREF

  v1 = 0;
  v15 = this;
  hKey = 0;
  memset(SubKey, 0, 522);
  v2 = 0;
  v3 = 0;
  cchName = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Setup\\ServiceStartup\\",
         0,
         8u,
         &hKey);
  if ( v4 == 2 )
    goto LABEL_52;
  if ( !v4 )
  {
    StringCchCopyExW(
      SubKey,
      0x105u,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Setup\\ServiceStartup\\",
      0,
      0,
      0x100u);
    v5 = -1;
    do
      ++v5;
    while ( SubKey[v5] );
    v6 = 261 - v5;
    cchName = 261 - v5;
    v7 = &SubKey[(unsigned int)v5];
    v4 = RegEnumKeyExW(hKey, 0, v7, &cchName, 0, 0, 0, 0);
    if ( v4 == 259 )
      goto LABEL_52;
    while ( 1 )
    {
      if ( v4 )
      {
        v2 = (unsigned __int16)v4 | 0x80070000;
        goto LABEL_50;
      }
      Type = 0;
      phkResult = 0;
      cbData[0] = 0;
      v8 = 0;
      samDesired[0] = 1;
      v2 = SetRegistryType(1, samDesired);
      if ( v2 >= 0 )
      {
        v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, samDesired[0], &phkResult);
        if ( v9 )
          goto LABEL_10;
        v10 = RegQueryValueExW(phkResult, L"TargetFile", 0, &Type, 0, cbData);
        if ( v10 || (v11 = cbData[0]) == 0 )
        {
          v2 = (unsigned __int16)v10 | 0x80070000;
          if ( v10 <= 0 )
            v2 = v10;
          goto LABEL_23;
        }
        if ( Type == 1 )
        {
          cbData[0] += 2;
          v8 = (BYTE *)SusAlloc(v11 + 2);
          if ( v8 )
          {
            v9 = RegQueryValueExW(phkResult, L"TargetFile", 0, &Type, v8, cbData);
            if ( !v9 )
            {
              *(_WORD *)&v8[cbData[0] & 0xFFFFFFFE] = 0;
              goto LABEL_25;
            }
LABEL_10:
            v2 = (unsigned __int16)v9 | 0x80070000;
            if ( v9 <= 0 )
              v2 = v9;
LABEL_23:
            if ( v2 >= 0 )
              goto LABEL_25;
            goto LABEL_24;
          }
          v2 = -2147024882;
        }
        else
        {
          v2 = -2147024883;
        }
      }
LABEL_24:
      SusFree(v8);
      v8 = 0;
LABEL_25:
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v2 < 0 )
        goto LABEL_52;
      Type = 0;
      phkResult = 0;
      cbData[0] = 0;
      samDesired[0] = 1;
      v2 = SetRegistryType(1, samDesired);
      if ( v2 < 0 )
        goto LABEL_41;
      v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, samDesired[0], &phkResult);
      if ( !v12 )
      {
        v12 = RegQueryValueExW(phkResult, L"CacheFile", 0, &Type, 0, cbData);
        if ( !v12 )
        {
          if ( cbData[0] )
          {
            if ( Type != 1 )
            {
              v2 = -2147024883;
LABEL_41:
              SusFree(v1);
              v1 = 0;
              goto LABEL_42;
            }
            cbData[0] += 2;
            v1 = (char *)SusAlloc(cbData[0]);
            if ( !v1 )
            {
              v2 = -2147024882;
              goto LABEL_41;
            }
            v12 = RegQueryValueExW(phkResult, L"CacheFile", 0, &Type, (LPBYTE)v1, cbData);
            if ( !v12 )
            {
              *(_WORD *)&v1[cbData[0] & 0xFFFFFFFE] = 0;
              goto LABEL_42;
            }
          }
        }
      }
      v2 = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        v2 = v12;
      if ( v2 < 0 )
        goto LABEL_41;
LABEL_42:
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v2 < 0
        || (v2 = CPfrAndFileVersionCache::DoBinaryInsertionSort(v15, (wchar_t *)v8, (wchar_t *)v1, 0, 0), v2 < 0) )
      {
        SusFree(v8);
        SusFree(v1);
        goto LABEL_52;
      }
      ++v3;
      v1 = 0;
      cchName = v6;
      v4 = RegEnumKeyExW(hKey, v3, v7, &cchName, 0, 0, 0, 0);
      if ( v4 == 259 )
        goto LABEL_52;
    }
  }
  v2 = (unsigned __int16)v4 | 0x80070000;
LABEL_50:
  if ( v4 <= 0 )
    v2 = v4;
LABEL_52:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180233a98  mov     rax, rsp
0x180233a9b  mov     [rax+10h], rbx
0x180233a9f  mov     [rax+18h], rsi
0x180233aa3  mov     [rax+20h], rdi
0x180233aa7  push    rbp
0x180233aa8  push    r12
0x180233aaa  push    r13
0x180233aac  push    r14
0x180233aae  push    r15
0x180233ab0  lea     rbp, [rax-1B8h]
0x180233ab7  sub     rsp, 290h
0x180233abe  mov     rax, cs:__security_cookie
0x180233ac5  xor     rax, rsp
0x180233ac8  mov     [rbp+1B0h+var_30], rax
0x180233acf  xor     edi, edi
0x180233ad1  mov     [rsp+2B0h+var_268], rcx
0x180233ad6  lea     rcx, [rsp+2B0h+var_23E]; void *
0x180233adb  mov     [rsp+2B0h+hKey], rdi
0x180233ae0  xor     edx, edx; Val
0x180233ae2  mov     [rsp+2B0h+SubKey], di
0x180233ae7  mov     r8d, 208h; Size
0x180233aed  mov     ebx, edi
0x180233aef  mov     r13d, edi
0x180233af2  call    memset
0x180233af7  lea     rax, [rsp+2B0h+hKey]
0x180233afc  mov     [rsp+2B0h+cchName], edi
0x180233b00  lea     r9d, [rdi+8]; samDesired
0x180233b04  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180233b09  xor     r8d, r8d; ulOptions
0x180233b0c  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180233b13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180233b1a  call    cs:__imp_RegOpenKeyExW
0x180233b20  cmp     eax, 2
0x180233b23  jz      loc_180233EA6
0x180233b29  test    eax, eax
0x180233b2b  jz      short loc_180233B3B
0x180233b2d  movzx   ebx, ax
0x180233b30  or      ebx, 80070000h
0x180233b36  jmp     loc_180233EA1
0x180233b3b  mov     r15d, 105h
0x180233b41  mov     dword ptr [rsp+2B0h+lpClass], 100h; unsigned int
0x180233b49  mov     edx, r15d; unsigned __int64
0x180233b4c  mov     [rsp+2B0h+phkResult], rdi; unsigned __int64 *
0x180233b51  xor     r9d, r9d; wchar_t **
0x180233b54  lea     r8, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180233b5b  lea     rcx, [rsp+2B0h+SubKey]; wchar_t *
0x180233b60  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180233b65  lea     rcx, [rsp+2B0h+SubKey]
0x180233b6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180233b6e  inc     rax
0x180233b71  cmp     [rcx+rax*2], di
0x180233b75  jnz     short loc_180233B6E
0x180233b77  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180233b7c  lea     r12, [rsp+2B0h+SubKey]
0x180233b81  sub     r15d, eax
0x180233b84  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180233b89  mov     eax, eax
0x180233b8b  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180233b90  mov     [rsp+2B0h+lpcchClass], rdi; lpcchClass
0x180233b95  xor     edx, edx; dwIndex
0x180233b97  mov     [rsp+2B0h+lpClass], rdi; lpClass
0x180233b9c  mov     [rsp+2B0h+cchName], r15d
0x180233ba1  lea     r12, [r12+rax*2]
0x180233ba5  mov     [rsp+2B0h+phkResult], rdi; lpReserved
0x180233baa  mov     r8, r12; lpName
0x180233bad  call    cs:__imp_RegEnumKeyExW
0x180233bb3  cmp     eax, 103h
0x180233bb8  jz      loc_180233EA6
0x180233bbe  mov     esi, 80070000h
0x180233bc3  test    eax, eax
0x180233bc5  jnz     loc_180233E9C
0x180233bcb  lea     rdx, [rsp+2B0h+samDesired]
0x180233bd0  mov     [rsp+2B0h+Type], edi
0x180233bd4  lea     ecx, [rax+1]
0x180233bd7  mov     [rsp+2B0h+var_258], rdi
0x180233bdc  mov     [rsp+2B0h+cbData], edi
0x180233be0  mov     r14, rdi
0x180233be3  mov     [rsp+2B0h+samDesired], 1
0x180233beb  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180233bf0  mov     ebx, eax
0x180233bf2  test    eax, eax
0x180233bf4  js      loc_180233CE1
0x180233bfa  mov     r9d, [rsp+2B0h+samDesired]; samDesired
0x180233bff  lea     rax, [rsp+2B0h+var_258]
0x180233c04  xor     r8d, r8d; ulOptions
0x180233c07  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180233c0c  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180233c11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180233c18  call    cs:__imp_RegOpenKeyExW
0x180233c1e  test    eax, eax
0x180233c20  jz      short loc_180233C31
0x180233c22  movzx   ebx, ax
0x180233c25  or      ebx, esi
0x180233c27  test    eax, eax
0x180233c29  cmovle  ebx, eax
0x180233c2c  jmp     loc_180233CDD
0x180233c31  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233c36  lea     rax, [rsp+2B0h+cbData]
0x180233c3b  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x180233c40  lea     r9, [rsp+2B0h+Type]; lpType
0x180233c45  xor     r8d, r8d; lpReserved
0x180233c48  mov     [rsp+2B0h+phkResult], rdi; lpData
0x180233c4d  lea     rdx, aTargetfile; "TargetFile"
0x180233c54  call    cs:__imp_RegQueryValueExW
0x180233c5a  mov     ecx, eax
0x180233c5c  test    eax, eax
0x180233c5e  jnz     short loc_180233CD3
0x180233c60  mov     eax, [rsp+2B0h+cbData]
0x180233c64  test    eax, eax
0x180233c66  jz      short loc_180233CD3
0x180233c68  cmp     [rsp+2B0h+Type], 1
0x180233c6d  jz      short loc_180233C76
0x180233c6f  mov     ebx, 8007000Dh
0x180233c74  jmp     short loc_180233CE1
0x180233c76  add     eax, 2
0x180233c79  mov     ecx, eax; unsigned __int64
0x180233c7b  mov     [rsp+2B0h+cbData], eax
0x180233c7f  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x180233c84  mov     r14, rax
0x180233c87  test    rax, rax
0x180233c8a  jnz     short loc_180233C93
0x180233c8c  mov     ebx, 8007000Eh
0x180233c91  jmp     short loc_180233CE1
0x180233c93  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233c98  lea     rax, [rsp+2B0h+cbData]
0x180233c9d  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x180233ca2  lea     r9, [rsp+2B0h+Type]; lpType
0x180233ca7  xor     r8d, r8d; lpReserved
0x180233caa  mov     [rsp+2B0h+phkResult], r14; lpData
0x180233caf  lea     rdx, aTargetfile; "TargetFile"
0x180233cb6  call    cs:__imp_RegQueryValueExW
0x180233cbc  test    eax, eax
0x180233cbe  jnz     loc_180233C22
0x180233cc4  mov     eax, [rsp+2B0h+cbData]
0x180233cc8  and     rax, 0FFFFFFFFFFFFFFFEh
0x180233ccc  mov     [rax+r14], di
0x180233cd1  jmp     short loc_180233CEC
0x180233cd3  movzx   ebx, cx
0x180233cd6  or      ebx, esi
0x180233cd8  test    ecx, ecx
0x180233cda  cmovle  ebx, ecx
0x180233cdd  test    ebx, ebx
0x180233cdf  jns     short loc_180233CEC
0x180233ce1  mov     rcx, r14; lpMem
0x180233ce4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180233ce9  mov     r14, rdi
0x180233cec  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233cf1  test    rcx, rcx
0x180233cf4  jz      short loc_180233CFC
0x180233cf6  call    cs:__imp_RegCloseKey
0x180233cfc  test    ebx, ebx
0x180233cfe  js      loc_180233EA6
0x180233d04  mov     eax, 1
0x180233d09  mov     [rsp+2B0h+Type], edi
0x180233d0d  mov     ecx, eax
0x180233d0f  mov     [rsp+2B0h+var_258], rdi
0x180233d14  lea     rdx, [rsp+2B0h+samDesired]
0x180233d19  mov     [rsp+2B0h+cbData], edi
0x180233d1d  mov     [rsp+2B0h+samDesired], eax
0x180233d21  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180233d26  mov     ebx, eax
0x180233d28  test    eax, eax
0x180233d2a  js      loc_180233E09
0x180233d30  mov     r9d, [rsp+2B0h+samDesired]; samDesired
0x180233d35  lea     rax, [rsp+2B0h+var_258]
0x180233d3a  xor     r8d, r8d; ulOptions
0x180233d3d  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180233d42  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180233d47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180233d4e  call    cs:__imp_RegOpenKeyExW
0x180233d54  xor     edx, edx
0x180233d56  test    eax, eax
0x180233d58  jnz     loc_180233DFB
0x180233d5e  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233d63  lea     rax, [rsp+2B0h+cbData]
0x180233d68  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x180233d6d  lea     r9, [rsp+2B0h+Type]; lpType
0x180233d72  mov     [rsp+2B0h+phkResult], rdx; lpData
0x180233d77  xor     r8d, r8d; lpReserved
0x180233d7a  lea     rdx, aCachefile; "CacheFile"
0x180233d81  call    cs:__imp_RegQueryValueExW
0x180233d87  xor     edx, edx
0x180233d89  test    eax, eax
0x180233d8b  jnz     short loc_180233DFB
0x180233d8d  mov     ecx, [rsp+2B0h+cbData]
0x180233d91  test    ecx, ecx
0x180233d93  jz      short loc_180233DFB
0x180233d95  cmp     [rsp+2B0h+Type], 1
0x180233d9a  jz      short loc_180233DA3
0x180233d9c  mov     ebx, 8007000Dh
0x180233da1  jmp     short loc_180233E09
0x180233da3  add     ecx, 2; unsigned __int64
0x180233da6  mov     [rsp+2B0h+cbData], ecx
0x180233daa  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x180233daf  mov     rdi, rax
0x180233db2  test    rax, rax
0x180233db5  jnz     short loc_180233DBE
0x180233db7  mov     ebx, 8007000Eh
0x180233dbc  jmp     short loc_180233E09
0x180233dbe  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233dc3  lea     rax, [rsp+2B0h+cbData]
0x180233dc8  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x180233dcd  lea     r9, [rsp+2B0h+Type]; lpType
0x180233dd2  xor     r8d, r8d; lpReserved
0x180233dd5  mov     [rsp+2B0h+phkResult], rdi; lpData
0x180233dda  lea     rdx, aCachefile; "CacheFile"
0x180233de1  call    cs:__imp_RegQueryValueExW
0x180233de7  xor     edx, edx
0x180233de9  test    eax, eax
0x180233deb  jnz     short loc_180233DFB
0x180233ded  mov     eax, [rsp+2B0h+cbData]
0x180233df1  and     rax, 0FFFFFFFFFFFFFFFEh
0x180233df5  mov     [rax+rdi], dx
0x180233df9  jmp     short loc_180233E15
0x180233dfb  movzx   ebx, ax
0x180233dfe  or      ebx, esi
0x180233e00  test    eax, eax
0x180233e02  cmovle  ebx, eax
0x180233e05  test    ebx, ebx
0x180233e07  jns     short loc_180233E15
0x180233e09  mov     rcx, rdi; lpMem
0x180233e0c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180233e11  xor     edx, edx
0x180233e13  mov     edi, edx
0x180233e15  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180233e1a  test    rcx, rcx
0x180233e1d  jz      short loc_180233E27
0x180233e1f  call    cs:__imp_RegCloseKey
0x180233e25  xor     edx, edx
0x180233e27  test    ebx, ebx
0x180233e29  js      short loc_180233E8A
0x180233e2b  mov     rcx, [rsp+2B0h+var_268]; this
0x180233e30  xor     r9d, r9d; int
0x180233e33  mov     [rsp+2B0h+phkResult], rdx; struct PfrAndFileVersionRecord **
0x180233e38  mov     r8, rdi; wchar_t *
0x180233e3b  mov     rdx, r14; wchar_t *
0x180233e3e  call    ?DoBinaryInsertionSort@CPfrAndFileVersionCache@@AEAAJPEA_W0HPEAPEBUPfrAndFileVersionRecord@@@Z; CPfrAndFileVersionCache::DoBinaryInsertionSort(wchar_t *,wchar_t *,int,PfrAndFileVersionRecord const * *)
0x180233e43  mov     ebx, eax
0x180233e45  test    eax, eax
0x180233e47  js      short loc_180233E8A
0x180233e49  inc     r13d
0x180233e4c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180233e51  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180233e56  xor     edi, edi
0x180233e58  mov     [rsp+2B0h+cchName], r15d
0x180233e5d  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180233e62  mov     r8, r12; lpName
0x180233e65  mov     [rsp+2B0h+lpcchClass], rdi; lpcchClass
0x180233e6a  mov     edx, r13d; dwIndex
0x180233e6d  mov     [rsp+2B0h+lpClass], rdi; lpClass
0x180233e72  mov     [rsp+2B0h+phkResult], rdi; lpReserved
0x180233e77  call    cs:__imp_RegEnumKeyExW
0x180233e7d  cmp     eax, 103h
0x180233e82  jnz     loc_180233BC3
0x180233e88  jmp     short loc_180233EA6
0x180233e8a  mov     rcx, r14; lpMem
0x180233e8d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180233e92  mov     rcx, rdi; lpMem
0x180233e95  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180233e9a  jmp     short loc_180233EA6
0x180233e9c  movzx   ebx, ax
0x180233e9f  or      ebx, esi
0x180233ea1  test    eax, eax
0x180233ea3  cmovle  ebx, eax
0x180233ea6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180233eab  test    rcx, rcx
0x180233eae  jz      short loc_180233EB6
0x180233eb0  call    cs:__imp_RegCloseKey
0x180233eb6  mov     eax, ebx
0x180233eb8  mov     rcx, [rbp+1B0h+var_30]
0x180233ebf  xor     rcx, rsp; StackCookie
0x180233ec2  call    __security_check_cookie
0x180233ec7  lea     r11, [rsp+2B0h+var_20]
0x180233ecf  mov     rbx, [r11+38h]
0x180233ed3  mov     rsi, [r11+40h]
0x180233ed7  mov     rdi, [r11+48h]
0x180233edb  mov     rsp, r11
0x180233ede  pop     r15
0x180233ee0  pop     r14
0x180233ee2  pop     r13
0x180233ee4  pop     r12
0x180233ee6  pop     rbp
0x180233ee7  retn
```
