# RegValueExists(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)

- ea: `0x18002c77c`
- end: `0x18002c84d`
- name: `?RegValueExists@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027058`

## callees

- `0x18002bee8`
- `0x18002c77c`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c828`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c828`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c806`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c806`

## pseudocode

```c
__int64 __fastcall RegValueExists(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  signed int v5; // ebx
  LSTATUS Value; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 1;
  v5 = SetRegistryType(a1, &samDesired);
  if ( v5 >= 0 )
  {
    Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( Value || (Value = RegQueryValueExW(hKey, a3, 0, 0, 0, 0)) != 0 )
    {
      v5 = (unsigned __int16)Value | 0x80070000;
      if ( Value <= 0 )
        v5 = Value;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c77c  mov     r11, rsp
0x18002c77f  mov     [r11+8], rbx
0x18002c783  mov     [r11+20h], rsi
0x18002c787  push    rdi
0x18002c788  sub     rsp, 50h
0x18002c78c  mov     rax, cs:__security_cookie
0x18002c793  xor     rax, rsp
0x18002c796  mov     [rsp+58h+var_18], rax
0x18002c79b  mov     rsi, rdx
0x18002c79e  mov     qword ptr [r11-20h], 0
0x18002c7a6  lea     rdx, [r11-28h]
0x18002c7aa  mov     [rsp+58h+samDesired], 1
0x18002c7b2  mov     rdi, r8
0x18002c7b5  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c7ba  mov     ebx, eax
0x18002c7bc  test    eax, eax
0x18002c7be  js      short loc_18002C81E
0x18002c7c0  mov     r9d, [rsp+58h+samDesired]; samDesired
0x18002c7c5  lea     rax, [rsp+58h+hKey]
0x18002c7ca  xor     r8d, r8d; ulOptions
0x18002c7cd  mov     [rsp+58h+phkResult], rax; phkResult
0x18002c7d2  mov     rdx, rsi; lpSubKey
0x18002c7d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c7dc  call    cs:__imp_RegOpenKeyExW
0x18002c7e2  test    eax, eax
0x18002c7e4  jnz     short loc_18002C810
0x18002c7e6  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c7eb  xor     r9d, r9d; lpType
0x18002c7ee  mov     [rsp+58h+lpcbData], 0; lpcbData
0x18002c7f7  xor     r8d, r8d; lpReserved
0x18002c7fa  mov     rdx, rdi; lpValueName
0x18002c7fd  mov     [rsp+58h+phkResult], 0; lpData
0x18002c806  call    cs:__imp_RegQueryValueExW
0x18002c80c  test    eax, eax
0x18002c80e  jz      short loc_18002C81E
0x18002c810  movzx   ebx, ax
0x18002c813  or      ebx, 80070000h
0x18002c819  test    eax, eax
0x18002c81b  cmovle  ebx, eax
0x18002c81e  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c823  test    rcx, rcx
0x18002c826  jz      short loc_18002C82E
0x18002c828  call    cs:__imp_RegCloseKey
0x18002c82e  mov     eax, ebx
0x18002c830  mov     rcx, [rsp+58h+var_18]
0x18002c835  xor     rcx, rsp; StackCookie
0x18002c838  call    __security_check_cookie
0x18002c83d  mov     rbx, [rsp+58h+arg_0]
0x18002c842  mov     rsi, [rsp+58h+arg_18]
0x18002c847  add     rsp, 50h
0x18002c84b  pop     rdi
0x18002c84c  retn
```
