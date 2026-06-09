# GetAppPathInfo(ushort const *,ushort *,ulong,ushort *,ulong)

- ea: `0x18002ba40`
- end: `0x18002bb9e`
- name: `?GetAppPathInfo@@YAXPEBGPEAGK1K@Z`
- size: `350`
- prototype: `void __fastcall(const unsigned __int16 *, LPBYTE lpData, __int64, BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bd00`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x18002ba40`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bafc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bafc`

## string_xrefs

- `0x18002baa5`: `Software\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetAppPathInfo(const unsigned __int16 *a1, LPBYTE lpData, __int64 a3, BYTE *a4)
{
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[312]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  if ( lpData )
    *(_WORD *)lpData = 0;
  if ( a4 )
    *(_WORD *)a4 = 0;
  StringCchCopyW(SubKey, 0x138u, L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths");
  StringCchCatW(SubKey, 0x138u, L"\\");
  StringCchCatW(SubKey, 0x138u, a1);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    Type = 0;
    if ( lpData )
    {
      cbData = 522;
      RegQueryValueExW(hKey, 0, 0, &Type, lpData, &cbData);
    }
    if ( a4 )
    {
      cbData = 2048;
      RegQueryValueExW(hKey, L"Path", 0, &Type, a4, &cbData);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18002ba40  push    rbp
0x18002ba42  push    rbx
0x18002ba43  push    rsi
0x18002ba44  push    rdi
0x18002ba45  push    r14
0x18002ba47  lea     rbp, [rsp-1C0h]
0x18002ba4f  sub     rsp, 2C0h
0x18002ba56  mov     rax, cs:__security_cookie
0x18002ba5d  xor     rax, rsp
0x18002ba60  mov     [rbp+1E0h+var_30], rax
0x18002ba67  mov     rdi, rdx
0x18002ba6a  mov     [rsp+2E0h+hKey], 0
0x18002ba73  mov     rsi, rcx
0x18002ba76  xor     edx, edx; Val
0x18002ba78  lea     rcx, [rsp+2E0h+SubKey]; void *
0x18002ba7d  mov     r8d, 270h; Size
0x18002ba83  mov     rbx, r9
0x18002ba86  call    memset_0
0x18002ba8b  test    rdi, rdi
0x18002ba8e  jz      short loc_18002BA95
0x18002ba90  xor     eax, eax
0x18002ba92  mov     [rdi], ax
0x18002ba95  test    rbx, rbx
0x18002ba98  jz      short loc_18002BA9F
0x18002ba9a  xor     eax, eax
0x18002ba9c  mov     [rbx], ax
0x18002ba9f  mov     r14d, 138h
0x18002baa5  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002baac  mov     edx, r14d; unsigned __int64
0x18002baaf  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002bab4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bab9  lea     r8, asc_18004F6BC; "\\"
0x18002bac0  mov     edx, r14d; unsigned __int64
0x18002bac3  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002bac8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002bacd  mov     r8, rsi; unsigned __int16 *
0x18002bad0  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002bad5  mov     edx, r14d; unsigned __int64
0x18002bad8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002badd  lea     rax, [rsp+2E0h+hKey]
0x18002bae2  mov     r9d, 1; samDesired
0x18002bae8  xor     r8d, r8d; ulOptions
0x18002baeb  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18002baf0  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18002baf5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bafc  call    cs:__imp_RegOpenKeyExW
0x18002bb02  test    eax, eax
0x18002bb04  jnz     short loc_18002BB71
0x18002bb06  mov     [rsp+2E0h+Type], eax
0x18002bb0a  test    rdi, rdi
0x18002bb0d  jz      short loc_18002BB3B
0x18002bb0f  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002bb14  lea     rax, [rsp+2E0h+cbData]
0x18002bb19  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18002bb1e  lea     r9, [rsp+2E0h+Type]; lpType
0x18002bb23  xor     r8d, r8d; lpReserved
0x18002bb26  mov     [rsp+2E0h+phkResult], rdi; lpData
0x18002bb2b  xor     edx, edx; lpValueName
0x18002bb2d  mov     [rsp+2E0h+cbData], 20Ah
0x18002bb35  call    cs:__imp_RegQueryValueExW
0x18002bb3b  test    rbx, rbx
0x18002bb3e  jz      short loc_18002BB71
0x18002bb40  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002bb45  lea     rax, [rsp+2E0h+cbData]
0x18002bb4a  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18002bb4f  lea     r9, [rsp+2E0h+Type]; lpType
0x18002bb54  xor     r8d, r8d; lpReserved
0x18002bb57  mov     [rsp+2E0h+phkResult], rbx; lpData
0x18002bb5c  lea     rdx, Name; "Path"
0x18002bb63  mov     [rsp+2E0h+cbData], 800h
0x18002bb6b  call    cs:__imp_RegQueryValueExW
0x18002bb71  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002bb76  test    rcx, rcx
0x18002bb79  jz      short loc_18002BB81
0x18002bb7b  call    cs:__imp_RegCloseKey
0x18002bb81  mov     rcx, [rbp+1E0h+var_30]
0x18002bb88  xor     rcx, rsp; StackCookie
0x18002bb8b  call    __security_check_cookie
0x18002bb90  add     rsp, 2C0h
0x18002bb97  pop     r14
0x18002bb99  pop     rdi
0x18002bb9a  pop     rsi
0x18002bb9b  pop     rbx
0x18002bb9c  pop     rbp
0x18002bb9d  retn
```
