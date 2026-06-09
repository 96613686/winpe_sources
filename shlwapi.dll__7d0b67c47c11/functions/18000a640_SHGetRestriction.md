# SHGetRestriction

- ea: `0x18000a640`
- end: `0x18000a70b`
- name: `SHGetRestriction`
- size: `203`
- prototype: `__int64 __fastcall(LPCWSTR pszDir, LPCWSTR pszFile, LPCWSTR pszValue)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x18000a640`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000a67c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000a67c`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000a6b0`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000a6e8`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000a6b0`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000a6e8`

## pseudocode

```c
__int64 __fastcall SHGetRestriction(LPCWSTR pszDir, LPCWSTR pszFile, LPCWSTR pszValue)
{
  const WCHAR *v5; // rdx
  DWORD pcbData; // [rsp+30h] [rbp-238h] BYREF
  _DWORD pvData[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  pvData[0] = 0;
  v5 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies";
  if ( pszDir )
    v5 = pszDir;
  PathCombineW(pszDest, v5, pszFile);
  pcbData = 4;
  if ( SHGetValueW(HKEY_LOCAL_MACHINE, pszDest, pszValue, 0, pvData, &pcbData) )
  {
    pcbData = 4;
    SHGetValueW(HKEY_CURRENT_USER, pszDest, pszValue, 0, pvData, &pcbData);
  }
  return pvData[0];
}

```

## disassembly

```asm
0x18000a640  push    rbx
0x18000a642  sub     rsp, 260h
0x18000a649  mov     rax, cs:__security_cookie
0x18000a650  xor     rax, rsp
0x18000a653  mov     [rsp+268h+var_18], rax
0x18000a65b  test    rcx, rcx
0x18000a65e  mov     [rsp+268h+var_234], 0
0x18000a666  mov     rbx, r8
0x18000a669  mov     r8, rdx; pszFile
0x18000a66c  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a673  cmovnz  rdx, rcx; pszDir
0x18000a677  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18000a67c  call    cs:__imp_PathCombineW
0x18000a682  lea     rax, [rsp+268h+var_238]
0x18000a687  mov     [rsp+268h+var_238], 4
0x18000a68f  mov     [rsp+268h+pcbData], rax; pcbData
0x18000a694  lea     rdx, [rsp+268h+pszDest]; pszSubKey
0x18000a699  lea     rax, [rsp+268h+var_234]
0x18000a69e  xor     r9d, r9d; pdwType
0x18000a6a1  mov     r8, rbx; pszValue
0x18000a6a4  mov     [rsp+268h+pvData], rax; pvData
0x18000a6a9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a6b0  call    cs:__imp_SHGetValueW
0x18000a6b6  test    eax, eax
0x18000a6b8  jz      short loc_18000A6EE
0x18000a6ba  lea     rax, [rsp+268h+var_238]
0x18000a6bf  mov     [rsp+268h+var_238], 4
0x18000a6c7  mov     [rsp+268h+pcbData], rax; pcbData
0x18000a6cc  lea     rdx, [rsp+268h+pszDest]; pszSubKey
0x18000a6d1  lea     rax, [rsp+268h+var_234]
0x18000a6d6  xor     r9d, r9d; pdwType
0x18000a6d9  mov     r8, rbx; pszValue
0x18000a6dc  mov     [rsp+268h+pvData], rax; pvData
0x18000a6e1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18000a6e8  call    cs:__imp_SHGetValueW
0x18000a6ee  mov     eax, [rsp+268h+var_234]
0x18000a6f2  mov     rcx, [rsp+268h+var_18]
0x18000a6fa  xor     rcx, rsp; StackCookie
0x18000a6fd  call    __security_check_cookie
0x18000a702  add     rsp, 260h
0x18000a709  pop     rbx
0x18000a70a  retn
```
