# AdviseForceDownload(_GUID * const,ulong)

- ea: `0x1800c89e8`
- end: `0x1800c8ccc`
- name: `?AdviseForceDownload@@YAHQEAU_GUID@@K@Z`
- size: `740`
- prototype: `__int64 __fastcall(struct _GUID *const, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b4640`

## callees

- `0x180030880`
- `0x1800763a8`
- `0x18007679c`
- `0x180090b64`
- `0x18009e830`
- `0x1800c89e8`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8afc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8b4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8b90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8bb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8c08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8c44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8afc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8b4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8b90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8bb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8c08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c8c44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8b60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8bdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8b60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8bdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c93`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c8a88`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c8a88`

## string_xrefs

- `0x1800c8ac3`: `CLSID`

## pseudocode

```c
__int64 __fastcall AdviseForceDownload(struct _GUID *const a1, char a2)
{
  unsigned int v3; // ebx
  const IID *v4; // r8
  int v5; // r9d
  HKEY v6; // rcx
  LPCSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v10; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[320]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 1;
  hKey = 0;
  lpSubKey = 0;
  phkResult = 0;
  lpsz = 0;
  CLocalComponentInfo::CLocalComponentInfo((CLocalComponentInfo *)v13);
  if ( v5 )
    goto LABEL_26;
  if ( StringFromCLSID(v4, &lpsz) >= 0 && (int)Unicode2Ansi(lpsz) >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey)
      && !RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    {
      if ( (int)CheckInstalledVersionHint(phkResult, (struct CLocalComponentInfo *)v13, 0, 0) >= 0 )
      {
LABEL_7:
        v3 = 0;
        goto LABEL_20;
      }
      v10 = 0;
      if ( !RegOpenKeyExA(phkResult, "AppID", 0, 0x20019u, &v10) )
      {
        v6 = v10;
        v3 = 0;
LABEL_10:
        RegCloseKey(v6);
        goto LABEL_20;
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
    v10 = 0;
    if ( !RegOpenKeyExA(
            HKEY_CURRENT_USER,
            "Software\\Microsoft\\Code Store Database\\Distribution Units",
            0,
            0x20019u,
            &v10) )
      RegCloseKey(v10);
    lpSubKey = 0;
    if ( RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\Code Store Database\\Distribution Units",
           0,
           0x20019u,
           (PHKEY)&lpSubKey) )
    {
      goto LABEL_20;
    }
    v6 = (HKEY)lpSubKey;
    goto LABEL_10;
  }
LABEL_20:
  if ( lpsz )
    operator delete(lpsz);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_26:
  CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v13);
  return v3;
}

```

## disassembly

```asm
0x1800c89e8  mov     [rsp-8+arg_8], rbx
0x1800c89ed  mov     [rsp-8+arg_10], rsi
0x1800c89f2  push    rbp
0x1800c89f3  push    rdi
0x1800c89f4  push    r15
0x1800c89f6  lea     rbp, [rsp-0B0h]
0x1800c89fe  sub     rsp, 1B0h
0x1800c8a05  mov     rax, cs:__security_cookie
0x1800c8a0c  xor     rax, rsp
0x1800c8a0f  mov     [rbp+0C0h+var_20], rax
0x1800c8a16  mov     esi, edx
0x1800c8a18  mov     r8, rcx
0x1800c8a1b  mov     ebx, 1
0x1800c8a20  test    rcx, rcx
0x1800c8a23  jz      short loc_1800C8A48
0x1800c8a25  mov     rax, [rcx]
0x1800c8a28  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800c8a2f  jnz     short loc_1800C8A3C
0x1800c8a31  mov     rax, [rcx+8]
0x1800c8a35  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800c8a3c  xor     r9d, r9d
0x1800c8a3f  test    rax, rax
0x1800c8a42  setz    r9b
0x1800c8a46  jmp     short loc_1800C8A4B
0x1800c8a48  mov     r9d, ebx
0x1800c8a4b  xor     edi, edi
0x1800c8a4d  mov     [rsp+1C0h+hKey], 0
0x1800c8a56  lea     rcx, [rsp+1C0h+var_160]; this
0x1800c8a5b  mov     [rsp+1C0h+lpSubKey], rdi
0x1800c8a60  mov     [rsp+1C0h+var_188], 0
0x1800c8a69  mov     [rsp+1C0h+lpsz], 0
0x1800c8a72  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x1800c8a77  test    r9d, r9d
0x1800c8a7a  jnz     loc_1800C8C99
0x1800c8a80  lea     rdx, [rsp+1C0h+lpsz]; lplpsz
0x1800c8a85  mov     rcx, r8; rclsid
0x1800c8a88  call    cs:__imp_StringFromCLSID
0x1800c8a8e  test    eax, eax
0x1800c8a90  js      loc_1800C8C5D
0x1800c8a96  mov     rcx, [rsp+1C0h+lpsz]; lpWideCharStr
0x1800c8a9b  lea     rdx, [rsp+1C0h+lpSubKey]
0x1800c8aa0  call    Unicode2Ansi
0x1800c8aa5  test    eax, eax
0x1800c8aa7  js      loc_1800C8C58
0x1800c8aad  lea     rax, [rsp+1C0h+hKey]
0x1800c8ab2  mov     r15d, 20019h
0x1800c8ab8  mov     r9d, r15d; samDesired
0x1800c8abb  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8ac0  xor     r8d, r8d; ulOptions
0x1800c8ac3  lea     rdx, aClsid_3; "CLSID"
0x1800c8aca  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800c8ad1  call    cs:__imp_RegOpenKeyExA
0x1800c8ad7  mov     rdi, [rsp+1C0h+lpSubKey]
0x1800c8adc  test    eax, eax
0x1800c8ade  jnz     loc_1800C8BE1
0x1800c8ae4  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c8ae9  lea     rax, [rsp+1C0h+var_188]
0x1800c8aee  mov     r9d, r15d; samDesired
0x1800c8af1  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8af6  xor     r8d, r8d; ulOptions
0x1800c8af9  mov     rdx, rdi; lpSubKey
0x1800c8afc  call    cs:__imp_RegOpenKeyExA
0x1800c8b02  test    eax, eax
0x1800c8b04  jnz     loc_1800C8BE1
0x1800c8b0a  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c8b0f  lea     rdx, [rsp+1C0h+var_160]; struct CLocalComponentInfo *
0x1800c8b14  xor     r9d, r9d; unsigned int
0x1800c8b17  xor     r8d, r8d; unsigned int
0x1800c8b1a  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x1800c8b1f  test    eax, eax
0x1800c8b21  js      short loc_1800C8B2A
0x1800c8b23  xor     ebx, ebx
0x1800c8b25  jmp     loc_1800C8C5D
0x1800c8b2a  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c8b2f  lea     rax, [rsp+1C0h+var_180]
0x1800c8b34  mov     r9d, r15d; samDesired
0x1800c8b37  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8b3c  xor     r8d, r8d; ulOptions
0x1800c8b3f  mov     [rsp+1C0h+var_180], 0
0x1800c8b48  lea     rdx, aAppid; "AppID"
0x1800c8b4f  call    cs:__imp_RegOpenKeyExA
0x1800c8b55  test    eax, eax
0x1800c8b57  jnz     short loc_1800C8B6B
0x1800c8b59  mov     rcx, [rsp+1C0h+var_180]; hKey
0x1800c8b5e  xor     ebx, ebx
0x1800c8b60  call    cs:__imp_RegCloseKey
0x1800c8b66  jmp     loc_1800C8C5D
0x1800c8b6b  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c8b70  lea     rax, [rsp+1C0h+lpSubKey]
0x1800c8b75  mov     r9d, r15d; samDesired
0x1800c8b78  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8b7d  xor     r8d, r8d; ulOptions
0x1800c8b80  mov     [rsp+1C0h+lpSubKey], 0
0x1800c8b89  lea     rdx, aInprocserver32_0; "InProcServer32"
0x1800c8b90  call    cs:__imp_RegOpenKeyExA
0x1800c8b96  test    eax, eax
0x1800c8b98  jz      short loc_1800C8BD6
0x1800c8b9a  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c8b9f  lea     rax, [rsp+1C0h+lpSubKey]
0x1800c8ba4  mov     r9d, r15d; samDesired
0x1800c8ba7  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8bac  xor     r8d, r8d; ulOptions
0x1800c8baf  lea     rdx, aLocalserver32_0; "LocalServer32"
0x1800c8bb6  call    cs:__imp_RegOpenKeyExA
0x1800c8bbc  test    eax, eax
0x1800c8bbe  jnz     short loc_1800C8BE1
0x1800c8bc0  mov     rcx, [rsp+1C0h+lpSubKey]; hKey
0x1800c8bc5  call    cs:__imp_RegCloseKey
0x1800c8bcb  test    sil, 4
0x1800c8bcf  jnz     short loc_1800C8BE1
0x1800c8bd1  jmp     loc_1800C8B23
0x1800c8bd6  mov     rcx, [rsp+1C0h+lpSubKey]; hKey
0x1800c8bdb  call    cs:__imp_RegCloseKey
0x1800c8be1  lea     rax, [rsp+1C0h+var_180]
0x1800c8be6  mov     [rsp+1C0h+var_180], 0
0x1800c8bef  mov     r9d, r15d; samDesired
0x1800c8bf2  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8bf7  xor     r8d, r8d; ulOptions
0x1800c8bfa  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800c8c01  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c8c08  call    cs:__imp_RegOpenKeyExA
0x1800c8c0e  test    eax, eax
0x1800c8c10  jnz     short loc_1800C8C1D
0x1800c8c12  mov     rcx, [rsp+1C0h+var_180]; hKey
0x1800c8c17  call    cs:__imp_RegCloseKey
0x1800c8c1d  lea     rax, [rsp+1C0h+lpSubKey]
0x1800c8c22  mov     [rsp+1C0h+lpSubKey], 0
0x1800c8c2b  mov     r9d, r15d; samDesired
0x1800c8c2e  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c8c33  xor     r8d, r8d; ulOptions
0x1800c8c36  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800c8c3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c8c44  call    cs:__imp_RegOpenKeyExA
0x1800c8c4a  test    eax, eax
0x1800c8c4c  jnz     short loc_1800C8C5D
0x1800c8c4e  mov     rcx, [rsp+1C0h+lpSubKey]
0x1800c8c53  jmp     loc_1800C8B60
0x1800c8c58  mov     rdi, [rsp+1C0h+lpSubKey]
0x1800c8c5d  mov     rcx, [rsp+1C0h+lpsz]; void *
0x1800c8c62  test    rcx, rcx
0x1800c8c65  jz      short loc_1800C8C6C
0x1800c8c67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c8c6c  test    rdi, rdi
0x1800c8c6f  jz      short loc_1800C8C79
0x1800c8c71  mov     rcx, rdi; void *
0x1800c8c74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c8c79  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c8c7e  test    rcx, rcx
0x1800c8c81  jz      short loc_1800C8C89
0x1800c8c83  call    cs:__imp_RegCloseKey
0x1800c8c89  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c8c8e  test    rcx, rcx
0x1800c8c91  jz      short loc_1800C8C99
0x1800c8c93  call    cs:__imp_RegCloseKey
0x1800c8c99  lea     rcx, [rsp+1C0h+var_160]; this
0x1800c8c9e  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x1800c8ca3  mov     eax, ebx
0x1800c8ca5  mov     rcx, [rbp+0C0h+var_20]
0x1800c8cac  xor     rcx, rsp; StackCookie
0x1800c8caf  call    __security_check_cookie
0x1800c8cb4  lea     r11, [rsp+1C0h+var_10]
0x1800c8cbc  mov     rbx, [r11+28h]
0x1800c8cc0  mov     rsi, [r11+30h]
0x1800c8cc4  mov     rsp, r11
0x1800c8cc7  pop     r15
0x1800c8cc9  pop     rdi
0x1800c8cca  pop     rbp
0x1800c8ccb  retn
```
