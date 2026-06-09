# GetAppPathInfo(ushort const *,ushort *,ulong,ushort *,ulong)

- ea: `0x18002d774`
- end: `0x18002d8eb`
- name: `?GetAppPathInfo@@YAXPEBGPEAGK1K@Z`
- size: `375`
- prototype: `void __fastcall(const unsigned __int16 *, LPBYTE lpData, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002da70`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x18002d774`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d86f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d8ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d86f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d8ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d830`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d830`

## string_xrefs

- `0x18002d7d9`: `Software\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
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
0x18002d774  push    rbp
0x18002d776  push    rbx
0x18002d777  push    rsi
0x18002d778  push    rdi
0x18002d779  push    r14
0x18002d77b  lea     rbp, [rsp-1C0h]
0x18002d783  sub     rsp, 2C0h
0x18002d78a  mov     rax, cs:__security_cookie
0x18002d791  xor     rax, rsp
0x18002d794  mov     [rbp+1E0h+var_30], rax
0x18002d79b  mov     rdi, rdx
0x18002d79e  mov     [rsp+2E0h+hKey], 0
0x18002d7a7  mov     rsi, rcx
0x18002d7aa  xor     edx, edx; Val
0x18002d7ac  lea     rcx, [rsp+2E0h+SubKey]; void *
0x18002d7b1  mov     r8d, 270h; Size
0x18002d7b7  mov     rbx, r9
0x18002d7ba  call    memset_0
0x18002d7bf  test    rdi, rdi
0x18002d7c2  jz      short loc_18002D7C9
0x18002d7c4  xor     eax, eax
0x18002d7c6  mov     [rdi], ax
0x18002d7c9  test    rbx, rbx
0x18002d7cc  jz      short loc_18002D7D3
0x18002d7ce  xor     eax, eax
0x18002d7d0  mov     [rbx], ax
0x18002d7d3  mov     r14d, 138h
0x18002d7d9  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d7e0  mov     edx, r14d; unsigned __int64
0x18002d7e3  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002d7e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d7ed  lea     r8, asc_1800516CC; "\\"
0x18002d7f4  mov     edx, r14d; unsigned __int64
0x18002d7f7  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002d7fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d801  mov     r8, rsi; unsigned __int16 *
0x18002d804  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18002d809  mov     edx, r14d; unsigned __int64
0x18002d80c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d811  lea     rax, [rsp+2E0h+hKey]
0x18002d816  mov     r9d, 1; samDesired
0x18002d81c  xor     r8d, r8d; ulOptions
0x18002d81f  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18002d824  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18002d829  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d830  call    cs:__imp_RegOpenKeyExW
0x18002d837  nop     dword ptr [rax+rax+00h]
0x18002d83c  test    eax, eax
0x18002d83e  jnz     short loc_18002D8B7
0x18002d840  mov     [rsp+2E0h+Type], eax
0x18002d844  test    rdi, rdi
0x18002d847  jz      short loc_18002D87B
0x18002d849  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002d84e  lea     rax, [rsp+2E0h+cbData]
0x18002d853  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18002d858  lea     r9, [rsp+2E0h+Type]; lpType
0x18002d85d  xor     r8d, r8d; lpReserved
0x18002d860  mov     [rsp+2E0h+phkResult], rdi; lpData
0x18002d865  xor     edx, edx; lpValueName
0x18002d867  mov     [rsp+2E0h+cbData], 20Ah
0x18002d86f  call    cs:__imp_RegQueryValueExW
0x18002d876  nop     dword ptr [rax+rax+00h]
0x18002d87b  test    rbx, rbx
0x18002d87e  jz      short loc_18002D8B7
0x18002d880  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002d885  lea     rax, [rsp+2E0h+cbData]
0x18002d88a  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18002d88f  lea     r9, [rsp+2E0h+Type]; lpType
0x18002d894  xor     r8d, r8d; lpReserved
0x18002d897  mov     [rsp+2E0h+phkResult], rbx; lpData
0x18002d89c  lea     rdx, Name; "Path"
0x18002d8a3  mov     [rsp+2E0h+cbData], 800h
0x18002d8ab  call    cs:__imp_RegQueryValueExW
0x18002d8b2  nop     dword ptr [rax+rax+00h]
0x18002d8b7  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18002d8bc  test    rcx, rcx
0x18002d8bf  jz      short loc_18002D8CD
0x18002d8c1  call    cs:__imp_RegCloseKey
0x18002d8c8  nop     dword ptr [rax+rax+00h]
0x18002d8cd  mov     rcx, [rbp+1E0h+var_30]
0x18002d8d4  xor     rcx, rsp; StackCookie
0x18002d8d7  call    __security_check_cookie
0x18002d8dc  add     rsp, 2C0h
0x18002d8e3  pop     r14
0x18002d8e5  pop     rdi
0x18002d8e6  pop     rsi
0x18002d8e7  pop     rbx
0x18002d8e8  pop     rbp
0x18002d8e9  retn
```
