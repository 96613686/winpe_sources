# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x18000fcfc`
- end: `0x18000fda6`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006600`
- `0x180012344`
- `0x180021730`
- `0x180021d90`
- `0x180026964`
- `0x180028ea8`
- `0x18002f6ac`
- `0x18003543c`
- `0x18003583c`

## callees

- `0x18000fac4`
- `0x18000fc6c`
- `0x18000fcfc`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd57`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValueWithDefaultAndRangeCheck(int a1, const WCHAR *a2, const wchar_t *a3, REGSAM a4)
{
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  REGSAM samDesired; // [rsp+38h] [rbp-30h] BYREF

  samDesired = 1;
  if ( (int)SetRegistryType(a1, &samDesired) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey) )
    {
      samDesired = a4;
      if ( hKey && RegQueryDwordValue(hKey, a3, &samDesired) >= 0 )
        a4 = samDesired;
      RegCloseKey(hKey);
    }
  }
  return a4;
}

```

## disassembly

```asm
0x18000fcfc  push    rbx
0x18000fcfe  push    rsi
0x18000fcff  push    rdi
0x18000fd00  sub     rsp, 50h
0x18000fd04  mov     rax, cs:__security_cookie
0x18000fd0b  xor     rax, rsp
0x18000fd0e  mov     [rsp+68h+var_28], rax
0x18000fd13  mov     rsi, rdx
0x18000fd16  mov     [rsp+68h+samDesired], 1
0x18000fd1e  lea     rdx, [rsp+68h+samDesired]
0x18000fd23  mov     ebx, r9d
0x18000fd26  mov     rdi, r8
0x18000fd29  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18000fd2e  test    eax, eax
0x18000fd30  js      short loc_18000FD8F
0x18000fd32  mov     r9d, [rsp+68h+samDesired]; samDesired
0x18000fd37  lea     rax, [rsp+68h+hKey]
0x18000fd3c  xor     r8d, r8d; ulOptions
0x18000fd3f  mov     [rsp+68h+phkResult], rax; phkResult
0x18000fd44  mov     rdx, rsi; lpSubKey
0x18000fd47  mov     [rsp+68h+hKey], 0
0x18000fd50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fd57  call    cs:__imp_RegOpenKeyExW
0x18000fd5d  test    eax, eax
0x18000fd5f  jnz     short loc_18000FD8F
0x18000fd61  mov     rcx, [rsp+68h+hKey]; HKEY
0x18000fd66  mov     [rsp+68h+samDesired], ebx
0x18000fd6a  test    rcx, rcx
0x18000fd6d  jz      short loc_18000FD84
0x18000fd6f  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x18000fd74  mov     rdx, rdi; wchar_t *
0x18000fd77  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18000fd7c  test    eax, eax
0x18000fd7e  js      short loc_18000FD84
0x18000fd80  mov     ebx, [rsp+68h+samDesired]
0x18000fd84  mov     rcx, [rsp+68h+hKey]; hKey
0x18000fd89  call    cs:__imp_RegCloseKey
0x18000fd8f  mov     eax, ebx
0x18000fd91  mov     rcx, [rsp+68h+var_28]
0x18000fd96  xor     rcx, rsp; StackCookie
0x18000fd99  call    __security_check_cookie
0x18000fd9e  add     rsp, 50h
0x18000fda2  pop     rdi
0x18000fda3  pop     rsi
0x18000fda4  pop     rbx
0x18000fda5  retn
```
