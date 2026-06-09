# WwanRegRemoveProfile(ushort const *,ushort const *,int)

- ea: `0x1800a3480`
- end: `0x1800a3552`
- name: `?WwanRegRemoveProfile@@YAKPEBG0H@Z`
- size: `210`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18009f9f0`
- `0x1800a1148`
- `0x1800a3e84`
- `0x1800a4478`
- `0x1800a4af8`
- `0x1800a4e14`

## callees

- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a3398`
- `0x1800a3480`
- `0x1800a3c94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3516`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3516`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a34d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a34d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a34fa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a34fa`

## string_xrefs

- `0x1800a3495`: `WwanRegRemoveProfile`
- `0x1800a3528`: `WwanRegRemoveProfile`
- `0x1800a3534`: `WwanRegRemoveProfile`

## pseudocode

```c
__int64 __fastcall WwanRegRemoveProfile(LPCWSTR lpSubKey, LPCWSTR a2, int a3)
{
  HKEY v6; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  WwanLog::Enter("WwanRegRemoveProfile");
  v6 = qword_180152870;
  hKey = 0;
  if ( a3 )
    v6 = ::hKey;
  if ( !RegOpenKeyExW(v6, lpSubKey, 0, 0x2001Fu, &hKey) )
  {
    remMultiSzVal(hKey, L"ProfileList");
    RegDeleteTreeW(hKey, a2);
    if ( a3 )
      WwanRegRemoveDMConfigEmptyKey(lpSubKey, hKey);
    RegCloseKey(hKey);
  }
  WwanLog::Verbose("WwanRegRemoveProfile", 0, L"errCode (0x%8x)", 0);
  WwanLog::Exit("WwanRegRemoveProfile");
  return 0;
}

```

## disassembly

```asm
0x1800a3480  mov     [rsp+arg_8], rbx
0x1800a3485  mov     [rsp+arg_10], rsi
0x1800a348a  push    rdi
0x1800a348b  sub     rsp, 30h
0x1800a348f  mov     rdi, rcx
0x1800a3492  mov     esi, r8d
0x1800a3495  lea     rcx, aWwanregremovep_0; "WwanRegRemoveProfile"
0x1800a349c  mov     rbx, rdx
0x1800a349f  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a34a4  mov     rcx, cs:qword_180152870
0x1800a34ab  lea     rax, [rsp+38h+hKey]
0x1800a34b0  test    esi, esi
0x1800a34b2  mov     [rsp+38h+hKey], 0
0x1800a34bb  mov     r9d, 2001Fh; samDesired
0x1800a34c1  mov     [rsp+38h+phkResult], rax; phkResult
0x1800a34c6  cmovnz  rcx, cs:hKey; hKey
0x1800a34ce  mov     rdx, rdi; lpSubKey
0x1800a34d1  xor     r8d, r8d; ulOptions
0x1800a34d4  call    cs:__imp_RegOpenKeyExW
0x1800a34da  test    eax, eax
0x1800a34dc  jnz     short loc_1800A351C
0x1800a34de  mov     rcx, [rsp+38h+hKey]; hKey
0x1800a34e3  lea     rdx, aProfilelist; "ProfileList"
0x1800a34ea  mov     r8, rbx
0x1800a34ed  call    _remMultiSzVal
0x1800a34f2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800a34f7  mov     rdx, rbx; lpSubKey
0x1800a34fa  call    cs:__imp_RegDeleteTreeW
0x1800a3500  test    esi, esi
0x1800a3502  jz      short loc_1800A3511
0x1800a3504  mov     rdx, [rsp+38h+hKey]; hKey
0x1800a3509  mov     rcx, rdi; lpSubKey
0x1800a350c  call    ?WwanRegRemoveDMConfigEmptyKey@@YAXPEBGPEAUHKEY__@@@Z; WwanRegRemoveDMConfigEmptyKey(ushort const *,HKEY__ *)
0x1800a3511  mov     rcx, [rsp+38h+hKey]; hKey
0x1800a3516  call    cs:__imp_RegCloseKey
0x1800a351c  xor     r9d, r9d
0x1800a351f  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x1800a3526  xor     edx, edx; struct _GUID *
0x1800a3528  lea     rcx, aWwanregremovep_0; "WwanRegRemoveProfile"
0x1800a352f  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a3534  lea     rcx, aWwanregremovep_0; "WwanRegRemoveProfile"
0x1800a353b  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a3540  mov     rbx, [rsp+38h+arg_8]
0x1800a3545  xor     eax, eax
0x1800a3547  mov     rsi, [rsp+38h+arg_10]
0x1800a354c  add     rsp, 30h
0x1800a3550  pop     rdi
0x1800a3551  retn
```
