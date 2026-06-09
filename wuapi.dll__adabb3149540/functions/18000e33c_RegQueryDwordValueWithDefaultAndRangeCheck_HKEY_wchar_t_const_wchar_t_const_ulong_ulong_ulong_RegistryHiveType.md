# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x18000e33c`
- end: `0x18000e3e6`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `170`
- prototype: `unsigned int __high(HKEY, const wchar_t *, const wchar_t *, unsigned int, unsigned int, unsigned int, enum RegistryHiveType)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007d00`

## callees

- `0x18000e1c8`
- `0x18000e2ac`
- `0x18000e33c`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e397`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e397`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e3c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e3c9`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValueWithDefaultAndRangeCheck(
        __int64 a1,
        const WCHAR *a2,
        const wchar_t *a3,
        REGSAM a4)
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
0x18000e33c  push    rbx
0x18000e33e  push    rsi
0x18000e33f  push    rdi
0x18000e340  sub     rsp, 50h
0x18000e344  mov     rax, cs:__security_cookie
0x18000e34b  xor     rax, rsp
0x18000e34e  mov     [rsp+68h+var_28], rax
0x18000e353  mov     rsi, rdx
0x18000e356  mov     [rsp+68h+samDesired], 1
0x18000e35e  lea     rdx, [rsp+68h+samDesired]
0x18000e363  mov     ebx, r9d
0x18000e366  mov     rdi, r8
0x18000e369  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18000e36e  test    eax, eax
0x18000e370  js      short loc_18000E3CF
0x18000e372  mov     r9d, [rsp+68h+samDesired]; samDesired
0x18000e377  lea     rax, [rsp+68h+hKey]
0x18000e37c  xor     r8d, r8d; ulOptions
0x18000e37f  mov     [rsp+68h+phkResult], rax; phkResult
0x18000e384  mov     rdx, rsi; lpSubKey
0x18000e387  mov     [rsp+68h+hKey], 0
0x18000e390  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e397  call    cs:__imp_RegOpenKeyExW
0x18000e39d  test    eax, eax
0x18000e39f  jnz     short loc_18000E3CF
0x18000e3a1  mov     rcx, [rsp+68h+hKey]; HKEY
0x18000e3a6  mov     [rsp+68h+samDesired], ebx
0x18000e3aa  test    rcx, rcx
0x18000e3ad  jz      short loc_18000E3C4
0x18000e3af  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x18000e3b4  mov     rdx, rdi; wchar_t *
0x18000e3b7  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18000e3bc  test    eax, eax
0x18000e3be  js      short loc_18000E3C4
0x18000e3c0  mov     ebx, [rsp+68h+samDesired]
0x18000e3c4  mov     rcx, [rsp+68h+hKey]; hKey
0x18000e3c9  call    cs:__imp_RegCloseKey
0x18000e3cf  mov     eax, ebx
0x18000e3d1  mov     rcx, [rsp+68h+var_28]
0x18000e3d6  xor     rcx, rsp; StackCookie
0x18000e3d9  call    __security_check_cookie
0x18000e3de  add     rsp, 50h
0x18000e3e2  pop     rdi
0x18000e3e3  pop     rsi
0x18000e3e4  pop     rbx
0x18000e3e5  retn
```
