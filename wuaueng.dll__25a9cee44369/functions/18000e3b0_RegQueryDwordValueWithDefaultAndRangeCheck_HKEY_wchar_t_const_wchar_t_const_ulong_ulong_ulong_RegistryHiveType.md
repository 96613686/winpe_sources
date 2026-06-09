# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x18000e3b0`
- end: `0x18000e45a`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const wchar_t *, REGSAM)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800064e0`

## callees

- `0x18000e23c`
- `0x18000e320`
- `0x18000e3b0`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e40b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e40b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e43d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e43d`

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
0x18000e3b0  push    rbx
0x18000e3b2  push    rsi
0x18000e3b3  push    rdi
0x18000e3b4  sub     rsp, 50h
0x18000e3b8  mov     rax, cs:__security_cookie
0x18000e3bf  xor     rax, rsp
0x18000e3c2  mov     [rsp+68h+var_28], rax
0x18000e3c7  mov     rsi, rdx
0x18000e3ca  mov     [rsp+68h+samDesired], 1
0x18000e3d2  lea     rdx, [rsp+68h+samDesired]
0x18000e3d7  mov     ebx, r9d
0x18000e3da  mov     rdi, r8
0x18000e3dd  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18000e3e2  test    eax, eax
0x18000e3e4  js      short loc_18000E443
0x18000e3e6  mov     r9d, [rsp+68h+samDesired]; samDesired
0x18000e3eb  lea     rax, [rsp+68h+hKey]
0x18000e3f0  xor     r8d, r8d; ulOptions
0x18000e3f3  mov     [rsp+68h+phkResult], rax; phkResult
0x18000e3f8  mov     rdx, rsi; lpSubKey
0x18000e3fb  mov     [rsp+68h+hKey], 0
0x18000e404  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e40b  call    cs:__imp_RegOpenKeyExW
0x18000e411  test    eax, eax
0x18000e413  jnz     short loc_18000E443
0x18000e415  mov     rcx, [rsp+68h+hKey]; HKEY
0x18000e41a  mov     [rsp+68h+samDesired], ebx
0x18000e41e  test    rcx, rcx
0x18000e421  jz      short loc_18000E438
0x18000e423  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x18000e428  mov     rdx, rdi; wchar_t *
0x18000e42b  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18000e430  test    eax, eax
0x18000e432  js      short loc_18000E438
0x18000e434  mov     ebx, [rsp+68h+samDesired]
0x18000e438  mov     rcx, [rsp+68h+hKey]; hKey
0x18000e43d  call    cs:__imp_RegCloseKey
0x18000e443  mov     eax, ebx
0x18000e445  mov     rcx, [rsp+68h+var_28]
0x18000e44a  xor     rcx, rsp; StackCookie
0x18000e44d  call    __security_check_cookie
0x18000e452  add     rsp, 50h
0x18000e456  pop     rdi
0x18000e457  pop     rsi
0x18000e458  pop     rbx
0x18000e459  retn
```
