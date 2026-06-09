# SHSetValueW

- ea: `0x180046530`
- end: `0x180046601`
- name: `SHSetValueW`
- size: `209`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue, DWORD dwType, LPCVOID pvData, DWORD cbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180070bc0`

## callees

- `0x180046530`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800465eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800465eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800465b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800465b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046588`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046588`

## pseudocode

```c
LSTATUS __stdcall SHSetValueW(
        HKEY hkey,
        LPCWSTR pszSubKey,
        LPCWSTR pszValue,
        DWORD dwType,
        LPCVOID pvData,
        DWORD cbData)
{
  HKEY v8; // rdi
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-48h] BYREF

  hKey = 0;
  v8 = hkey;
  if ( pszSubKey && *pszSubKey )
  {
    v9 = RegCreateKeyExW(hkey, pszSubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    hkey = hKey;
  }
  else
  {
    hKey = hkey;
  }
  v9 = RegSetValueExW(hkey, pszValue, 0, dwType, (const BYTE *)pvData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180046530  push    rbx
0x180046532  push    rbp
0x180046533  push    rsi
0x180046534  push    rdi
0x180046535  push    r14
0x180046537  push    r15
0x180046539  sub     rsp, 68h
0x18004653d  mov     rax, cs:__security_cookie
0x180046544  xor     rax, rsp
0x180046547  mov     [rsp+98h+var_40], rax
0x18004654c  mov     r14, [rsp+98h+pvData]
0x180046554  xor     r15d, r15d
0x180046557  mov     [rsp+98h+hKey], r15
0x18004655c  mov     ebp, r9d
0x18004655f  mov     rsi, r8
0x180046562  mov     rdi, rcx
0x180046565  test    rdx, rdx
0x180046568  jnz     short loc_1800465BE
0x18004656a  mov     [rsp+98h+hKey], rcx
0x18004656f  mov     eax, [rsp+98h+cbData]
0x180046576  mov     r9d, ebp; dwType
0x180046579  mov     [rsp+98h+samDesired], eax; cbData
0x18004657d  xor     r8d, r8d; Reserved
0x180046580  mov     rdx, rsi; lpValueName
0x180046583  mov     [rsp+98h+lpData], r14; lpData
0x180046588  call    cs:__imp_RegSetValueExW
0x18004658e  mov     rcx, [rsp+98h+hKey]; hKey
0x180046593  mov     ebx, eax
0x180046595  cmp     rcx, rdi
0x180046598  jnz     short loc_1800465B6
0x18004659a  mov     eax, ebx
0x18004659c  mov     rcx, [rsp+98h+var_40]
0x1800465a1  xor     rcx, rsp; StackCookie
0x1800465a4  call    __security_check_cookie
0x1800465a9  add     rsp, 68h
0x1800465ad  pop     r15
0x1800465af  pop     r14
0x1800465b1  pop     rdi
0x1800465b2  pop     rsi
0x1800465b3  pop     rbp
0x1800465b4  pop     rbx
0x1800465b5  retn
0x1800465b6  call    cs:__imp_RegCloseKey
0x1800465bc  jmp     short loc_18004659A
0x1800465be  cmp     [rdx], r15w
0x1800465c2  jz      short loc_18004656A
0x1800465c4  mov     [rsp+98h+lpdwDisposition], r15; lpdwDisposition
0x1800465c9  lea     rax, [rsp+98h+hKey]
0x1800465ce  mov     [rsp+98h+phkResult], rax; phkResult
0x1800465d3  xor     r9d, r9d; lpClass
0x1800465d6  mov     [rsp+98h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800465db  xor     r8d, r8d; Reserved
0x1800465de  mov     [rsp+98h+samDesired], 2; samDesired
0x1800465e6  mov     dword ptr [rsp+98h+lpData], r15d; dwOptions
0x1800465eb  call    cs:__imp_RegCreateKeyExW
0x1800465f1  mov     ebx, eax
0x1800465f3  test    eax, eax
0x1800465f5  jnz     short loc_18004659A
0x1800465f7  mov     rcx, [rsp+98h+hKey]
0x1800465fc  jmp     loc_18004656F
```
