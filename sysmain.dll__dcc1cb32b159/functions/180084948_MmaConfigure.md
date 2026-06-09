# MmaConfigure

- ea: `0x180084948`
- end: `0x180084ebe`
- name: `MmaConfigure`
- size: `1398`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a040`
- `0x18007a100`
- `0x18007a1c0`

## callees

- `0x1800382e0`
- `0x1800383e8`
- `0x180069920`
- `0x180071b0c`
- `0x180083234`
- `0x180084948`
- `0x180085bd4`
- `0x180086914`
- `0x180086cac`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x1800849ce`
- `ntdll!RtlGetVersion` at `0x1800849ce`
- `ntdll!RtlNtStatusToDosError` at `0x1800849de`
- `ntdll!RtlNtStatusToDosError` at `0x1800849de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084c21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084b0d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180084e3e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180084e3e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180084b03`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180084b03`

## string_xrefs

- `0x180084b33`: `StartedComponents`

## pseudocode

```c
__int64 __fastcall MmaConfigure(_DWORD *a1, int a2)
{
  HKEY v4; // r14
  int Version; // eax
  int v6; // esi
  unsigned int Value; // ebx
  BOOL v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  SC_HANDLE v11; // r12
  __int16 v12; // ax
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v17; // eax
  int v18; // edi
  int v19; // r8d
  int v20; // eax
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  SC_HANDLE hService[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+98h] [rbp-68h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+C0h] [rbp-40h] BYREF
  char v32; // [rsp+1DAh] [rbp+DAh]

  v22 = 0;
  v23 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v25 = 0;
  v24 = 0;
  v27 = 0;
  v4 = 0;
  v26 = 0;
  hKey = 0;
  *(_OWORD *)hService = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  v6 = 1;
  if ( Version >= 0 )
  {
    v8 = v32 == 1;
  }
  else
  {
    Value = RtlNtStatusToDosError(Version);
    v8 = 0;
    if ( Value )
      goto LABEL_94;
  }
  if ( a2 == 2 )
  {
    *a1 = 0;
    v9 = 0;
  }
  else
  {
    v9 = v8 ? -29 : 8;
  }
  if ( (v9 & *a1) != 0 )
  {
    Value = 50;
    goto LABEL_94;
  }
  v25 = 0;
  v22 = 0;
  v23 = 0;
  if ( a2 == 2 )
  {
    v10 = PfSvServiceRegistryKeyGet(&v26, 1);
    Value = v10;
    if ( v10 )
    {
      if ( v10 != 5 )
      {
        v4 = v26;
        v11 = hService[1];
        goto LABEL_24;
      }
LABEL_93:
      v4 = v26;
      goto LABEL_94;
    }
    v4 = v26;
  }
  else
  {
    Value = PfSvServiceRegistryKeyGet(&v26, 0);
    if ( Value )
      goto LABEL_93;
    v4 = v26;
    Value = PfsRegQueryValue((_DWORD)v26, (unsigned int)L"AdminEnable", 4, 4, (__int64)&v22);
    if ( (Value & 0xFFFFFFFD) != 0 )
      goto LABEL_94;
    Value = PfsRegQueryValue((_DWORD)v4, (unsigned int)L"AdminDisable", 4, 4, (__int64)&v23);
    if ( (Value & 0xFFFFFFFD) != 0 )
      goto LABEL_94;
  }
  Value = PfsServiceCtxStart(hService, L"Sysmain");
  if ( Value )
    goto LABEL_94;
  v11 = hService[1];
  if ( !QueryServiceStatus(hService[1], &ServiceStatus) )
    goto LABEL_20;
  if ( ServiceStatus.dwCurrentState != 4
    || (Value = PfsRegQueryValue((_DWORD)v4, (unsigned int)L"StartedComponents", 4, 4, (__int64)&v25)) == 0 )
  {
    if ( a2 != 2 )
    {
      v13 = v22;
      v14 = v23;
      if ( (*(_BYTE *)a1 & 0x10) != 0 )
      {
        if ( a2 )
        {
          v14 = v23 | 0x200;
          v23 |= 0x200u;
        }
        else
        {
          v13 = v22 | 0x200;
          v22 |= 0x200u;
        }
      }
      if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        if ( a2 )
        {
          v14 |= 0x100u;
          v23 = v14;
        }
        else
        {
          v13 |= 0x100u;
          v22 = v13;
        }
      }
      if ( (*(_BYTE *)a1 & 3) == 0 )
        goto LABEL_73;
      Value = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\PrefetchParameters",
                0,
                0,
                0,
                0xF003Fu,
                0,
                &hKey,
                0);
      if ( Value )
        goto LABEL_94;
LABEL_41:
      if ( (unsigned int)PfsRegQueryValue((_DWORD)hKey, (unsigned int)L"EnablePrefetcher", 4, 4, (__int64)&v24) )
      {
        v15 = 0;
        v24 = 0;
      }
      else
      {
        v15 = v24;
      }
      if ( a2 == 2 )
      {
        if ( !(unsigned int)PfsQueryFileInfo(&v27) && v27 )
        {
          if ( (v24 & 1) != 0 )
            *a1 |= 1u;
          if ( (v24 & 2) != 0 )
            *a1 |= 2u;
        }
        goto LABEL_51;
      }
      v16 = *a1 & 1;
      if ( a2 )
      {
        if ( v16 )
        {
          v15 &= ~1u;
          v24 = v15;
        }
        if ( (*(_BYTE *)a1 & 2) != 0 )
          v24 = v15 & 0xFFFFFFFD;
      }
      else
      {
        if ( v16 )
        {
          v15 |= 1u;
          v24 = v15;
        }
        if ( (*(_BYTE *)a1 & 2) != 0 )
          v24 = v15 | 2;
        Value = PfsEnableFileInfo(1);
        if ( Value )
          goto LABEL_94;
      }
      Value = PfsRegSetValue(hKey, L"EnablePrefetcher", 4, 4, &v24);
      if ( Value )
        goto LABEL_94;
      v17 = v24;
      if ( !v24 )
      {
        Value = PfsEnableFileInfo(0);
        if ( Value )
          goto LABEL_94;
        v17 = v24;
      }
      v13 = v22;
      if ( !a2 )
      {
        v13 = v22 | 3;
        v22 |= 3u;
LABEL_72:
        v14 = v23;
        goto LABEL_73;
      }
      if ( v17 )
        goto LABEL_72;
      v14 = v23 | 3;
      v23 |= 3u;
LABEL_73:
      if ( (*(_BYTE *)a1 & 8) != 0 )
      {
        if ( a2 )
        {
          v14 |= 0x2000u;
          v23 = v14;
        }
        else
        {
          v13 |= 0x2000u;
          v22 = v13;
        }
      }
      if ( v25 || (v18 = 1, !v13) )
        v18 = 0;
      if ( a2 )
      {
        v20 = ~v14;
        v22 = v20 & v13;
        v19 = v20 & v25;
      }
      else
      {
        v23 = ~v13 & v14;
        v19 = v13 | v25;
      }
      v25 = v19;
      Value = PfsRegSetValue(v4, L"AdminEnable", 4, 4, &v22);
      if ( !Value )
      {
        Value = PfsRegSetValue(v4, L"AdminDisable", 4, 4, &v23);
        if ( !Value )
        {
          if ( !v25 )
            goto LABEL_91;
          if ( ChangeServiceConfigW(v11, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
          {
            if ( v25 )
              v6 = 0;
LABEL_91:
            Value = PfsRestartService(hService, v18 | (unsigned int)v6);
            if ( Value )
              goto LABEL_94;
LABEL_54:
            Value = 0;
            goto LABEL_94;
          }
LABEL_20:
          Value = GetLastError();
          goto LABEL_94;
        }
      }
      goto LABEL_94;
    }
LABEL_24:
    v12 = v25;
    if ( (v25 & 0x200) != 0 )
      *a1 |= 0x10u;
    if ( (v12 & 0x100) != 0 )
      *a1 |= 4u;
    if ( (v12 & 1) == 0 )
      goto LABEL_52;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\PrefetchParameters",
           0,
           0xF003Fu,
           &hKey) )
    {
LABEL_51:
      v12 = v25;
LABEL_52:
      if ( (v12 & 0x2000) != 0 )
        *a1 |= 8u;
      goto LABEL_54;
    }
    goto LABEL_41;
  }
LABEL_94:
  if ( v4 )
    RegCloseKey(v4);
  if ( hKey )
    RegCloseKey(hKey);
  PfsServiceCtxCleanup(hService);
  return Value;
}

```

## disassembly

```asm
0x180084948  push    rbp
0x18008494a  push    rbx
0x18008494b  push    rsi
0x18008494c  push    rdi
0x18008494d  push    r12
0x18008494f  push    r13
0x180084951  push    r14
0x180084953  push    r15
0x180084955  lea     rbp, [rsp-0F8h]
0x18008495d  sub     rsp, 1F8h
0x180084964  mov     rax, cs:__security_cookie
0x18008496b  xor     rax, rsp
0x18008496e  mov     [rbp+130h+var_50], rax
0x180084975  xor     r13d, r13d
0x180084978  xorps   xmm0, xmm0
0x18008497b  mov     r15d, edx
0x18008497e  mov     [rsp+230h+var_1D0], r13d
0x180084983  mov     rdi, rcx
0x180084986  mov     [rsp+230h+var_1CC], r13d
0x18008498b  movups  xmmword ptr [rbp+130h+ServiceStatus.dwServiceType], xmm0
0x18008498f  xor     edx, edx; Val
0x180084991  mov     [rsp+230h+var_1C4], r13d
0x180084996  mov     r8d, 118h; Size
0x18008499c  mov     [rsp+230h+var_1C8], r13d
0x1800849a1  lea     rcx, [rbp+130h+VersionInformation.dwMajorVersion]; void *
0x1800849a5  mov     [rsp+230h+var_1B8], r13d
0x1800849aa  movups  xmmword ptr [rbp+130h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800849ae  mov     r14d, r13d
0x1800849b1  mov     [rsp+230h+var_1C0], r13
0x1800849b6  mov     [rbp+130h+hKey], r13
0x1800849ba  movups  xmmword ptr [rbp+130h+hService], xmm0
0x1800849be  call    memset_0
0x1800849c3  lea     rcx, [rbp+130h+VersionInformation]; lpVersionInformation
0x1800849c7  mov     [rbp+130h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800849ce  call    cs:__imp_RtlGetVersion
0x1800849d4  lea     esi, [r13+1]
0x1800849d8  test    eax, eax
0x1800849da  jns     short loc_1800849F2
0x1800849dc  mov     ecx, eax; Status
0x1800849de  call    cs:__imp_RtlNtStatusToDosError
0x1800849e4  mov     ebx, eax
0x1800849e6  mov     eax, r13d
0x1800849e9  test    ebx, ebx
0x1800849eb  jz      short loc_1800849FF
0x1800849ed  jmp     loc_180084E73
0x1800849f2  cmp     [rbp+130h+var_56], sil
0x1800849f9  mov     eax, r13d
0x1800849fc  setz    al
0x1800849ff  cmp     r15d, 2
0x180084a03  jnz     short loc_180084A0D
0x180084a05  mov     [rdi], r13d
0x180084a08  mov     eax, r13d
0x180084a0b  jmp     short loc_180084A17
0x180084a0d  neg     eax
0x180084a0f  sbb     eax, eax
0x180084a11  and     eax, 0FFFFFFDBh
0x180084a14  add     eax, 8
0x180084a17  test    [rdi], eax
0x180084a19  jz      short loc_180084A25
0x180084a1b  mov     ebx, 32h ; '2'
0x180084a20  jmp     loc_180084E73
0x180084a25  mov     [rsp+230h+var_1C4], r13d
0x180084a2a  mov     r12d, 4
0x180084a30  mov     [rsp+230h+var_1D0], r13d
0x180084a35  lea     rcx, [rsp+230h+var_1C0]
0x180084a3a  mov     [rsp+230h+var_1CC], r13d
0x180084a3f  cmp     r15d, 2
0x180084a43  jnz     short loc_180084A70
0x180084a45  mov     edx, esi
0x180084a47  call    PfSvServiceRegistryKeyGet
0x180084a4c  mov     ebx, eax
0x180084a4e  test    eax, eax
0x180084a50  jz      short loc_180084A69
0x180084a52  cmp     eax, 5
0x180084a55  jz      loc_180084E6E
0x180084a5b  mov     r14, [rsp+230h+var_1C0]
0x180084a60  mov     r12, [rbp+130h+hService+8]
0x180084a64  jmp     loc_180084B52
0x180084a69  mov     r14, [rsp+230h+var_1C0]
0x180084a6e  jmp     short loc_180084ADE
0x180084a70  xor     edx, edx
0x180084a72  call    PfSvServiceRegistryKeyGet
0x180084a77  mov     ebx, eax
0x180084a79  test    eax, eax
0x180084a7b  jnz     loc_180084E6E
0x180084a81  mov     r14, [rsp+230h+var_1C0]
0x180084a86  lea     rax, [rsp+230h+var_1D0]
0x180084a8b  mov     rcx, r14
0x180084a8e  mov     [rsp+230h+phkResult], rax
0x180084a93  mov     r9d, r12d
0x180084a96  lea     rdx, aAdminenable; "AdminEnable"
0x180084a9d  mov     r8d, r12d
0x180084aa0  call    PfsRegQueryValue
0x180084aa5  mov     ebx, eax
0x180084aa7  test    eax, 0FFFFFFFDh
0x180084aac  jnz     loc_180084E73
0x180084ab2  lea     rax, [rsp+230h+var_1CC]
0x180084ab7  mov     r9d, r12d
0x180084aba  mov     r8d, r12d
0x180084abd  mov     [rsp+230h+phkResult], rax
0x180084ac2  lea     rdx, aAdmindisable; "AdminDisable"
0x180084ac9  mov     rcx, r14
0x180084acc  call    PfsRegQueryValue
0x180084ad1  mov     ebx, eax
0x180084ad3  test    eax, 0FFFFFFFDh
0x180084ad8  jnz     loc_180084E73
0x180084ade  lea     rdx, ServiceName; "Sysmain"
0x180084ae5  lea     rcx, [rbp+130h+hService]
0x180084ae9  call    PfsServiceCtxStart
0x180084aee  mov     ebx, eax
0x180084af0  test    eax, eax
0x180084af2  jnz     loc_180084E73
0x180084af8  mov     r12, [rbp+130h+hService+8]
0x180084afc  lea     rdx, [rbp+130h+ServiceStatus]; lpServiceStatus
0x180084b00  mov     rcx, r12; hService
0x180084b03  call    cs:__imp_QueryServiceStatus
0x180084b09  test    eax, eax
0x180084b0b  jnz     short loc_180084B1A
0x180084b0d  call    cs:__imp_GetLastError
0x180084b13  mov     ebx, eax
0x180084b15  jmp     loc_180084E73
0x180084b1a  cmp     [rbp+130h+ServiceStatus.dwCurrentState], 4
0x180084b1e  jnz     short loc_180084B4C
0x180084b20  mov     r9d, 4
0x180084b26  lea     rax, [rsp+230h+var_1C4]
0x180084b2b  mov     r8d, r9d
0x180084b2e  mov     [rsp+230h+phkResult], rax
0x180084b33  lea     rdx, aStartedcompone; "StartedComponents"
0x180084b3a  mov     rcx, r14
0x180084b3d  call    PfsRegQueryValue
0x180084b42  mov     ebx, eax
0x180084b44  test    eax, eax
0x180084b46  jnz     loc_180084E73
0x180084b4c  cmp     r15d, 2
0x180084b50  jnz     short loc_180084BA4
0x180084b52  mov     eax, [rsp+230h+var_1C4]
0x180084b56  bt      eax, 9
0x180084b5a  jnb     short loc_180084B5F
0x180084b5c  or      dword ptr [rdi], 10h
0x180084b5f  bt      eax, 8
0x180084b63  jnb     short loc_180084B68
0x180084b65  or      dword ptr [rdi], 4
0x180084b68  test    sil, al
0x180084b6b  jz      loc_180084C99
0x180084b71  lea     rax, [rbp+130h+hKey]
0x180084b75  mov     r9d, 0F003Fh; samDesired
0x180084b7b  xor     r8d, r8d; ulOptions
0x180084b7e  mov     [rsp+230h+phkResult], rax; phkResult
0x180084b83  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Ses"...
0x180084b8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084b91  call    cs:__imp_RegOpenKeyExW
0x180084b97  test    eax, eax
0x180084b99  jnz     loc_180084C95
0x180084b9f  jmp     loc_180084C31
0x180084ba4  test    byte ptr [rdi], 10h
0x180084ba7  mov     ecx, [rsp+230h+var_1D0]
0x180084bab  mov     eax, [rsp+230h+var_1CC]
0x180084baf  jz      short loc_180084BC8
0x180084bb1  test    r15d, r15d
0x180084bb4  jnz     short loc_180084BC0
0x180084bb6  bts     ecx, 9
0x180084bba  mov     [rsp+230h+var_1D0], ecx
0x180084bbe  jmp     short loc_180084BC8
0x180084bc0  bts     eax, 9
0x180084bc4  mov     [rsp+230h+var_1CC], eax
0x180084bc8  test    byte ptr [rdi], 4
0x180084bcb  jz      short loc_180084BE4
0x180084bcd  test    r15d, r15d
0x180084bd0  jnz     short loc_180084BDC
0x180084bd2  bts     ecx, 8
0x180084bd6  mov     [rsp+230h+var_1D0], ecx
0x180084bda  jmp     short loc_180084BE4
0x180084bdc  bts     eax, 8
0x180084be0  mov     [rsp+230h+var_1CC], eax
0x180084be4  test    byte ptr [rdi], 3
0x180084be7  jz      loc_180084D51
0x180084bed  mov     [rsp+230h+lpdwDisposition], r13; lpdwDisposition
0x180084bf2  lea     rax, [rbp+130h+hKey]
0x180084bf6  mov     [rsp+230h+var_1F8], rax; phkResult
0x180084bfb  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Ses"...
0x180084c02  mov     [rsp+230h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180084c07  xor     r9d, r9d; lpClass
0x180084c0a  mov     [rsp+230h+samDesired], 0F003Fh; samDesired
0x180084c12  xor     r8d, r8d; Reserved
0x180084c15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084c1c  mov     dword ptr [rsp+230h+phkResult], r13d; dwOptions
0x180084c21  call    cs:__imp_RegCreateKeyExW
0x180084c27  mov     ebx, eax
0x180084c29  test    eax, eax
0x180084c2b  jnz     loc_180084E73
0x180084c31  mov     rcx, [rbp+130h+hKey]
0x180084c35  lea     rax, [rsp+230h+var_1C8]
0x180084c3a  mov     ebx, 4
0x180084c3f  mov     [rsp+230h+phkResult], rax
0x180084c44  mov     r9d, ebx
0x180084c47  lea     rdx, aEnableprefetch; "EnablePrefetcher"
0x180084c4e  mov     r8d, ebx
0x180084c51  call    PfsRegQueryValue
0x180084c56  test    eax, eax
0x180084c58  jz      short loc_180084C63
0x180084c5a  mov     eax, r13d
0x180084c5d  mov     [rsp+230h+var_1C8], eax
0x180084c61  jmp     short loc_180084C67
0x180084c63  mov     eax, [rsp+230h+var_1C8]
0x180084c67  cmp     r15d, 2
0x180084c6b  jnz     short loc_180084CAA
0x180084c6d  lea     rcx, [rsp+230h+var_1B8]
0x180084c72  call    PfsQueryFileInfo
0x180084c77  test    eax, eax
0x180084c79  jnz     short loc_180084C95
0x180084c7b  cmp     [rsp+230h+var_1B8], r13d
0x180084c80  jz      short loc_180084C95
0x180084c82  test    byte ptr [rsp+230h+var_1C8], sil
0x180084c87  jz      short loc_180084C8B
0x180084c89  or      [rdi], esi
0x180084c8b  test    byte ptr [rsp+230h+var_1C8], 2
0x180084c90  jz      short loc_180084C95
0x180084c92  or      dword ptr [rdi], 2
0x180084c95  mov     eax, [rsp+230h+var_1C4]
0x180084c99  bt      eax, 0Dh
0x180084c9d  jnb     short loc_180084CA2
0x180084c9f  or      dword ptr [rdi], 8
0x180084ca2  mov     ebx, r13d
0x180084ca5  jmp     loc_180084E73
0x180084caa  mov     ecx, [rdi]
0x180084cac  and     ecx, esi
0x180084cae  test    r15d, r15d
0x180084cb1  jnz     short loc_180084CDF
0x180084cb3  test    ecx, ecx
0x180084cb5  jz      short loc_180084CBD
0x180084cb7  or      eax, esi
0x180084cb9  mov     [rsp+230h+var_1C8], eax
0x180084cbd  test    byte ptr [rdi], 2
0x180084cc0  jz      short loc_180084CC9
0x180084cc2  or      eax, 2
0x180084cc5  mov     [rsp+230h+var_1C8], eax
0x180084cc9  mov     ecx, esi
0x180084ccb  call    PfsEnableFileInfo
0x180084cd0  mov     ebx, eax
0x180084cd2  test    eax, eax
0x180084cd4  jnz     loc_180084E73
0x180084cda  lea     ebx, [rax+4]
0x180084cdd  jmp     short loc_180084CF6
0x180084cdf  test    ecx, ecx
0x180084ce1  jz      short loc_180084CEA
0x180084ce3  and     eax, 0FFFFFFFEh
0x180084ce6  mov     [rsp+230h+var_1C8], eax
0x180084cea  test    byte ptr [rdi], 2
0x180084ced  jz      short loc_180084CF6
0x180084cef  and     eax, 0FFFFFFFDh
0x180084cf2  mov     [rsp+230h+var_1C8], eax
0x180084cf6  mov     rcx, [rbp+130h+hKey]
0x180084cfa  lea     rax, [rsp+230h+var_1C8]
0x180084cff  mov     r9d, ebx
0x180084d02  mov     [rsp+230h+phkResult], rax
0x180084d07  mov     r8d, ebx
0x180084d0a  lea     rdx, aEnableprefetch; "EnablePrefetcher"
0x180084d11  call    PfsRegSetValue
0x180084d16  mov     ebx, eax
0x180084d18  test    eax, eax
0x180084d1a  jnz     loc_180084E73
0x180084d20  mov     eax, [rsp+230h+var_1C8]
0x180084d24  test    eax, eax
0x180084d26  jnz     short loc_180084D3D
0x180084d28  xor     ecx, ecx
0x180084d2a  call    PfsEnableFileInfo
0x180084d2f  mov     ebx, eax
0x180084d31  test    eax, eax
0x180084d33  jnz     loc_180084E73
0x180084d39  mov     eax, [rsp+230h+var_1C8]
0x180084d3d  mov     ecx, [rsp+230h+var_1D0]
0x180084d41  test    r15d, r15d
0x180084d44  jnz     short loc_180084D65
0x180084d46  or      ecx, 3
0x180084d49  mov     [rsp+230h+var_1D0], ecx
0x180084d4d  mov     eax, [rsp+230h+var_1CC]
0x180084d51  test    byte ptr [rdi], 8
0x180084d54  jz      short loc_180084D7E
0x180084d56  test    r15d, r15d
0x180084d59  jnz     short loc_180084D76
0x180084d5b  bts     ecx, 0Dh
0x180084d5f  mov     [rsp+230h+var_1D0], ecx
0x180084d63  jmp     short loc_180084D7E
0x180084d65  test    eax, eax
0x180084d67  jnz     short loc_180084D4D
0x180084d69  mov     eax, [rsp+230h+var_1CC]
0x180084d6d  or      eax, 3
0x180084d70  mov     [rsp+230h+var_1CC], eax
0x180084d74  jmp     short loc_180084D51
0x180084d76  bts     eax, 0Dh
0x180084d7a  mov     [rsp+230h+var_1CC], eax
0x180084d7e  mov     r8d, [rsp+230h+var_1C4]
0x180084d83  test    r8d, r8d
0x180084d86  jnz     short loc_180084D8E
0x180084d88  mov     edi, esi
0x180084d8a  test    ecx, ecx
0x180084d8c  jnz     short loc_180084D91
0x180084d8e  mov     edi, r13d
0x180084d91  test    r15d, r15d
0x180084d94  jnz     short loc_180084DA5
  ... truncated ...
```
