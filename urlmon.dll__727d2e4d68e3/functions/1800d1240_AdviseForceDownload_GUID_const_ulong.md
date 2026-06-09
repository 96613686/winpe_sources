# AdviseForceDownload(_GUID * const,ulong)

- ea: `0x1800d1240`
- end: `0x1800d1579`
- name: `?AdviseForceDownload@@YAHQEAU_GUID@@K@Z`
- size: `825`
- prototype: `__int64 __fastcall(struct _GUID *const, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bc0d0`

## callees

- `0x18002fee0`
- `0x18007bcc8`
- `0x18007c108`
- `0x180096c28`
- `0x1800a5678`
- `0x1800d1240`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d132f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1360`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d13b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1406`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1432`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1496`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d14de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d132f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1360`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d13b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1406`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1432`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d1496`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d14de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d13d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d14ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d13d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d14ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1539`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800d12e0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800d12e0`

## string_xrefs

- `0x1800d1321`: `CLSID`

## pseudocode

```c
__int64 __fastcall AdviseForceDownload(struct _GUID *const a1, char a2)
{
  unsigned int v3; // ebx
  CHAR *v4; // rdi
  const IID *v5; // r8
  int v6; // r9d
  LSTATUS v7; // eax
  HKEY v8; // rcx
  LPCSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v12; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[320]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 1;
  v4 = 0;
  hKey = 0;
  lpSubKey = 0;
  phkResult = 0;
  lpsz = 0;
  CLocalComponentInfo::CLocalComponentInfo((CLocalComponentInfo *)v15);
  if ( v6 )
    goto LABEL_29;
  if ( StringFromCLSID(v5, &lpsz) >= 0 )
  {
    if ( (int)Unicode2Ansi(lpsz, (CHAR **)&lpSubKey) < 0 )
    {
      v4 = (CHAR *)lpSubKey;
      goto LABEL_21;
    }
    v7 = RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey);
    v4 = (CHAR *)lpSubKey;
    if ( !v7 && !RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    {
      if ( (int)CheckInstalledVersionHint(phkResult, (struct CLocalComponentInfo *)v15, 0, 0) >= 0 )
      {
LABEL_7:
        v3 = 0;
        goto LABEL_21;
      }
      v12 = 0;
      if ( !RegOpenKeyExA(phkResult, "AppID", 0, 0x20019u, &v12) )
      {
        v8 = v12;
        v3 = 0;
LABEL_10:
        RegCloseKey(v8);
        goto LABEL_21;
      }
      lpSubKey = 0;
      if ( RegOpenKeyExA(phkResult, "InProcServer32", 0, 0x20019u, (PHKEY)&lpSubKey) )
      {
        if ( !RegOpenKeyExA(phkResult, "LocalServer32", 0, 0x20019u, (PHKEY)&lpSubKey) )
        {
          RegCloseKey((HKEY)lpSubKey);
          if ( (a2 & 4) == 0 )
            goto LABEL_7;
        }
      }
      else
      {
        RegCloseKey((HKEY)lpSubKey);
      }
    }
    v12 = 0;
    if ( !RegOpenKeyExA(
            HKEY_CURRENT_USER,
            "Software\\Microsoft\\Code Store Database\\Distribution Units",
            0,
            0x20019u,
            &v12) )
      RegCloseKey(v12);
    lpSubKey = 0;
    if ( RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\Code Store Database\\Distribution Units",
           0,
           0x20019u,
           (PHKEY)&lpSubKey) )
    {
      goto LABEL_21;
    }
    v8 = (HKEY)lpSubKey;
    goto LABEL_10;
  }
LABEL_21:
  if ( lpsz )
    operator delete(lpsz);
  if ( v4 )
    operator delete(v4);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_29:
  CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v15);
  return v3;
}

```

## disassembly

```asm
0x1800d1240  mov     [rsp-8+arg_8], rbx
0x1800d1245  mov     [rsp-8+arg_10], rsi
0x1800d124a  push    rbp
0x1800d124b  push    rdi
0x1800d124c  push    r15
0x1800d124e  lea     rbp, [rsp-0B0h]
0x1800d1256  sub     rsp, 1B0h
0x1800d125d  mov     rax, cs:__security_cookie
0x1800d1264  xor     rax, rsp
0x1800d1267  mov     [rbp+0C0h+var_20], rax
0x1800d126e  mov     esi, edx
0x1800d1270  mov     r8, rcx
0x1800d1273  mov     ebx, 1
0x1800d1278  test    rcx, rcx
0x1800d127b  jz      short loc_1800D12A0
0x1800d127d  mov     rax, [rcx]
0x1800d1280  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800d1287  jnz     short loc_1800D1294
0x1800d1289  mov     rax, [rcx+8]
0x1800d128d  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800d1294  xor     r9d, r9d
0x1800d1297  test    rax, rax
0x1800d129a  setz    r9b
0x1800d129e  jmp     short loc_1800D12A3
0x1800d12a0  mov     r9d, ebx
0x1800d12a3  xor     edi, edi
0x1800d12a5  mov     [rsp+1C0h+hKey], 0
0x1800d12ae  lea     rcx, [rsp+1C0h+var_160]; this
0x1800d12b3  mov     [rsp+1C0h+lpSubKey], rdi
0x1800d12b8  mov     [rsp+1C0h+var_188], 0
0x1800d12c1  mov     [rsp+1C0h+lpsz], 0
0x1800d12ca  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x1800d12cf  test    r9d, r9d
0x1800d12d2  jnz     loc_1800D1545
0x1800d12d8  lea     rdx, [rsp+1C0h+lpsz]; lplpsz
0x1800d12dd  mov     rcx, r8; rclsid
0x1800d12e0  call    cs:__imp_StringFromCLSID
0x1800d12e7  nop     dword ptr [rax+rax+00h]
0x1800d12ec  test    eax, eax
0x1800d12ee  js      loc_1800D14FD
0x1800d12f4  mov     rcx, [rsp+1C0h+lpsz]; lpWideCharStr
0x1800d12f9  lea     rdx, [rsp+1C0h+lpSubKey]
0x1800d12fe  call    Unicode2Ansi
0x1800d1303  test    eax, eax
0x1800d1305  js      loc_1800D14F8
0x1800d130b  lea     rax, [rsp+1C0h+hKey]
0x1800d1310  mov     r15d, 20019h
0x1800d1316  mov     r9d, r15d; samDesired
0x1800d1319  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d131e  xor     r8d, r8d; ulOptions
0x1800d1321  lea     rdx, aClsid_3; "CLSID"
0x1800d1328  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800d132f  call    cs:__imp_RegOpenKeyExA
0x1800d1336  nop     dword ptr [rax+rax+00h]
0x1800d133b  mov     rdi, [rsp+1C0h+lpSubKey]
0x1800d1340  test    eax, eax
0x1800d1342  jnz     loc_1800D146F
0x1800d1348  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d134d  lea     rax, [rsp+1C0h+var_188]
0x1800d1352  mov     r9d, r15d; samDesired
0x1800d1355  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d135a  xor     r8d, r8d; ulOptions
0x1800d135d  mov     rdx, rdi; lpSubKey
0x1800d1360  call    cs:__imp_RegOpenKeyExA
0x1800d1367  nop     dword ptr [rax+rax+00h]
0x1800d136c  test    eax, eax
0x1800d136e  jnz     loc_1800D146F
0x1800d1374  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800d1379  lea     rdx, [rsp+1C0h+var_160]; struct CLocalComponentInfo *
0x1800d137e  xor     r9d, r9d; unsigned int
0x1800d1381  xor     r8d, r8d; unsigned int
0x1800d1384  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x1800d1389  test    eax, eax
0x1800d138b  js      short loc_1800D1394
0x1800d138d  xor     ebx, ebx
0x1800d138f  jmp     loc_1800D14FD
0x1800d1394  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800d1399  lea     rax, [rsp+1C0h+var_180]
0x1800d139e  mov     r9d, r15d; samDesired
0x1800d13a1  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d13a6  xor     r8d, r8d; ulOptions
0x1800d13a9  mov     [rsp+1C0h+var_180], 0
0x1800d13b2  lea     rdx, aAppid; "AppID"
0x1800d13b9  call    cs:__imp_RegOpenKeyExA
0x1800d13c0  nop     dword ptr [rax+rax+00h]
0x1800d13c5  test    eax, eax
0x1800d13c7  jnz     short loc_1800D13E1
0x1800d13c9  mov     rcx, [rsp+1C0h+var_180]; hKey
0x1800d13ce  xor     ebx, ebx
0x1800d13d0  call    cs:__imp_RegCloseKey
0x1800d13d7  nop     dword ptr [rax+rax+00h]
0x1800d13dc  jmp     loc_1800D14FD
0x1800d13e1  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800d13e6  lea     rax, [rsp+1C0h+lpSubKey]
0x1800d13eb  mov     r9d, r15d; samDesired
0x1800d13ee  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d13f3  xor     r8d, r8d; ulOptions
0x1800d13f6  mov     [rsp+1C0h+lpSubKey], 0
0x1800d13ff  lea     rdx, aInprocserver32_0; "InProcServer32"
0x1800d1406  call    cs:__imp_RegOpenKeyExA
0x1800d140d  nop     dword ptr [rax+rax+00h]
0x1800d1412  test    eax, eax
0x1800d1414  jz      short loc_1800D145E
0x1800d1416  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800d141b  lea     rax, [rsp+1C0h+lpSubKey]
0x1800d1420  mov     r9d, r15d; samDesired
0x1800d1423  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d1428  xor     r8d, r8d; ulOptions
0x1800d142b  lea     rdx, aLocalserver32_0; "LocalServer32"
0x1800d1432  call    cs:__imp_RegOpenKeyExA
0x1800d1439  nop     dword ptr [rax+rax+00h]
0x1800d143e  test    eax, eax
0x1800d1440  jnz     short loc_1800D146F
0x1800d1442  mov     rcx, [rsp+1C0h+lpSubKey]; hKey
0x1800d1447  call    cs:__imp_RegCloseKey
0x1800d144e  nop     dword ptr [rax+rax+00h]
0x1800d1453  test    sil, 4
0x1800d1457  jnz     short loc_1800D146F
0x1800d1459  jmp     loc_1800D138D
0x1800d145e  mov     rcx, [rsp+1C0h+lpSubKey]; hKey
0x1800d1463  call    cs:__imp_RegCloseKey
0x1800d146a  nop     dword ptr [rax+rax+00h]
0x1800d146f  lea     rax, [rsp+1C0h+var_180]
0x1800d1474  mov     [rsp+1C0h+var_180], 0
0x1800d147d  mov     r9d, r15d; samDesired
0x1800d1480  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d1485  xor     r8d, r8d; ulOptions
0x1800d1488  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800d148f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d1496  call    cs:__imp_RegOpenKeyExA
0x1800d149d  nop     dword ptr [rax+rax+00h]
0x1800d14a2  test    eax, eax
0x1800d14a4  jnz     short loc_1800D14B7
0x1800d14a6  mov     rcx, [rsp+1C0h+var_180]; hKey
0x1800d14ab  call    cs:__imp_RegCloseKey
0x1800d14b2  nop     dword ptr [rax+rax+00h]
0x1800d14b7  lea     rax, [rsp+1C0h+lpSubKey]
0x1800d14bc  mov     [rsp+1C0h+lpSubKey], 0
0x1800d14c5  mov     r9d, r15d; samDesired
0x1800d14c8  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800d14cd  xor     r8d, r8d; ulOptions
0x1800d14d0  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800d14d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d14de  call    cs:__imp_RegOpenKeyExA
0x1800d14e5  nop     dword ptr [rax+rax+00h]
0x1800d14ea  test    eax, eax
0x1800d14ec  jnz     short loc_1800D14FD
0x1800d14ee  mov     rcx, [rsp+1C0h+lpSubKey]
0x1800d14f3  jmp     loc_1800D13D0
0x1800d14f8  mov     rdi, [rsp+1C0h+lpSubKey]
0x1800d14fd  mov     rcx, [rsp+1C0h+lpsz]; void *
0x1800d1502  test    rcx, rcx
0x1800d1505  jz      short loc_1800D150C
0x1800d1507  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d150c  test    rdi, rdi
0x1800d150f  jz      short loc_1800D1519
0x1800d1511  mov     rcx, rdi; void *
0x1800d1514  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d1519  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800d151e  test    rcx, rcx
0x1800d1521  jz      short loc_1800D152F
0x1800d1523  call    cs:__imp_RegCloseKey
0x1800d152a  nop     dword ptr [rax+rax+00h]
0x1800d152f  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800d1534  test    rcx, rcx
0x1800d1537  jz      short loc_1800D1545
0x1800d1539  call    cs:__imp_RegCloseKey
0x1800d1540  nop     dword ptr [rax+rax+00h]
0x1800d1545  lea     rcx, [rsp+1C0h+var_160]; this
0x1800d154a  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x1800d154f  mov     eax, ebx
0x1800d1551  mov     rcx, [rbp+0C0h+var_20]
0x1800d1558  xor     rcx, rsp; StackCookie
0x1800d155b  call    __security_check_cookie
0x1800d1560  lea     r11, [rsp+1C0h+var_10]
0x1800d1568  mov     rbx, [r11+28h]
0x1800d156c  mov     rsi, [r11+30h]
0x1800d1570  mov     rsp, r11
0x1800d1573  pop     r15
0x1800d1575  pop     rdi
0x1800d1576  pop     rbp
0x1800d1577  retn
```
