# UmpopRegistryGetPowerRequestOverrideMask

- ea: `0x180002f7c`
- end: `0x180003062`
- name: `UmpopRegistryGetPowerRequestOverrideMask`
- size: `230`
- prototype: `char __fastcall(wchar_t *Str, LPCWSTR lpSubKey, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004170`

## callees

- `0x180002f7c`
- `0x180016e24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002fd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ff7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002fd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003042`

## pseudocode

```c
char __fastcall UmpopRegistryGetPowerRequestOverrideMask(wchar_t *Str, LPCWSTR lpSubKey, _DWORD *a3)
{
  char matched; // di
  HKEY v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+48h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  matched = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Power\\PowerRequestOverride",
          0,
          1u,
          &hKey)
    && !RegOpenKeyExW(hKey, lpSubKey, 0, 3u, &phkResult) )
  {
    matched = UmpopRegistryMatchPowerRequestOverride(phkResult, Str);
    if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(phkResult);
      phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
  }
  v7 = hKey;
  *a3 = 0;
  if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v7);
  return matched;
}

```

## disassembly

```asm
0x180002f7c  mov     [rsp-28h+arg_0], rbx
0x180002f81  mov     [rsp-28h+arg_8], rsi
0x180002f86  push    rbp
0x180002f87  push    rdi
0x180002f88  push    r12
0x180002f8a  push    r14
0x180002f8c  push    r15
0x180002f8e  mov     rbp, rsp
0x180002f91  sub     rsp, 40h
0x180002f95  or      r12, 0FFFFFFFFFFFFFFFFh
0x180002f99  mov     [rbp+arg_10], 0
0x180002fa0  mov     rsi, r8
0x180002fa3  mov     [rbp+hKey], r12
0x180002fa7  mov     r14, rdx
0x180002faa  mov     [rbp+arg_18], r12
0x180002fae  mov     r15, rcx
0x180002fb1  lea     rax, [rbp+hKey]
0x180002fb5  lea     r9d, [r12+2]; samDesired
0x180002fba  mov     [rsp+40h+phkResult], rax; phkResult
0x180002fbf  xor     r8d, r8d; ulOptions
0x180002fc2  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Pow"...
0x180002fc9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002fd0  xor     dil, dil
0x180002fd3  xor     ebx, ebx
0x180002fd5  call    cs:__imp_RegOpenKeyExW
0x180002fdb  test    eax, eax
0x180002fdd  jnz     short loc_180003032
0x180002fdf  mov     rcx, [rbp+hKey]; hKey
0x180002fe3  lea     rax, [rbp+arg_18]
0x180002fe7  lea     r9d, [r12+4]; samDesired
0x180002fec  mov     [rsp+40h+phkResult], rax; phkResult
0x180002ff1  xor     r8d, r8d; ulOptions
0x180002ff4  mov     rdx, r14; lpSubKey
0x180002ff7  call    cs:__imp_RegOpenKeyExW
0x180002ffd  test    eax, eax
0x180002fff  jnz     short loc_180003032
0x180003001  mov     rcx, [rbp+arg_18]; hKey
0x180003005  lea     r8, [rbp+arg_10]
0x180003009  mov     rdx, r15; Str
0x18000300c  call    UmpopRegistryMatchPowerRequestOverride
0x180003011  mov     rcx, [rbp+arg_18]; hKey
0x180003015  test    al, al
0x180003017  mov     dil, al
0x18000301a  cmovnz  ebx, [rbp+arg_10]
0x18000301e  lea     rdx, [rcx-1]
0x180003022  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180003026  ja      short loc_180003032
0x180003028  call    cs:__imp_RegCloseKey
0x18000302e  mov     [rbp+arg_18], r12
0x180003032  mov     rcx, [rbp+hKey]; hKey
0x180003036  mov     [rsi], ebx
0x180003038  lea     rax, [rcx-1]
0x18000303c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003040  ja      short loc_180003048
0x180003042  call    cs:__imp_RegCloseKey
0x180003048  mov     rbx, [rsp+40h+arg_0]
0x18000304d  mov     al, dil
0x180003050  mov     rsi, [rsp+40h+arg_8]
0x180003055  add     rsp, 40h
0x180003059  pop     r15
0x18000305b  pop     r14
0x18000305d  pop     r12
0x18000305f  pop     rdi
0x180003060  pop     rbp
0x180003061  retn
```
