# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x14001074c`
- end: `0x1400107f6`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `170`
- prototype: `unsigned int __high(HKEY, const wchar_t *, const wchar_t *, unsigned int, unsigned int, unsigned int, enum RegistryHiveType)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400080bc`

## callees

- `0x1400105d8`
- `0x1400106bc`
- `0x14001074c`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400107d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400107d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400107a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400107a7`

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
0x14001074c  push    rbx
0x14001074e  push    rsi
0x14001074f  push    rdi
0x140010750  sub     rsp, 50h
0x140010754  mov     rax, cs:__security_cookie
0x14001075b  xor     rax, rsp
0x14001075e  mov     [rsp+68h+var_28], rax
0x140010763  mov     rsi, rdx
0x140010766  mov     [rsp+68h+samDesired], 1
0x14001076e  lea     rdx, [rsp+68h+samDesired]
0x140010773  mov     ebx, r9d
0x140010776  mov     rdi, r8
0x140010779  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x14001077e  test    eax, eax
0x140010780  js      short loc_1400107DF
0x140010782  mov     r9d, [rsp+68h+samDesired]; samDesired
0x140010787  lea     rax, [rsp+68h+hKey]
0x14001078c  xor     r8d, r8d; ulOptions
0x14001078f  mov     [rsp+68h+phkResult], rax; phkResult
0x140010794  mov     rdx, rsi; lpSubKey
0x140010797  mov     [rsp+68h+hKey], 0
0x1400107a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400107a7  call    cs:__imp_RegOpenKeyExW
0x1400107ad  test    eax, eax
0x1400107af  jnz     short loc_1400107DF
0x1400107b1  mov     rcx, [rsp+68h+hKey]; HKEY
0x1400107b6  mov     [rsp+68h+samDesired], ebx
0x1400107ba  test    rcx, rcx
0x1400107bd  jz      short loc_1400107D4
0x1400107bf  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x1400107c4  mov     rdx, rdi; wchar_t *
0x1400107c7  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1400107cc  test    eax, eax
0x1400107ce  js      short loc_1400107D4
0x1400107d0  mov     ebx, [rsp+68h+samDesired]
0x1400107d4  mov     rcx, [rsp+68h+hKey]; hKey
0x1400107d9  call    cs:__imp_RegCloseKey
0x1400107df  mov     eax, ebx
0x1400107e1  mov     rcx, [rsp+68h+var_28]
0x1400107e6  xor     rcx, rsp; StackCookie
0x1400107e9  call    __security_check_cookie
0x1400107ee  add     rsp, 50h
0x1400107f2  pop     rdi
0x1400107f3  pop     rsi
0x1400107f4  pop     rbx
0x1400107f5  retn
```
