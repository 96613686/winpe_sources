# WPDLibDeleteRegistryValue

- ea: `0x1800059d0`
- end: `0x180005a41`
- name: `WPDLibDeleteRegistryValue`
- size: `113`
- prototype: `LSTATUS __fastcall(__int64, __int64, const WCHAR *, const WCHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800069d0`
- `0x18000f390`
- `0x1800106e0`

## callees

- `0x1800059d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a0b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005a23`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005a23`

## pseudocode

```c
LSTATUS __fastcall WPDLibDeleteRegistryValue(__int64 a1, __int64 a2, const WCHAR *a3, const WCHAR *a4)
{
  LSTATUS result; // eax
  LSTATUS v6; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( !a3 )
    return 87;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    v6 = RegDeleteValueW(hKey, a4);
    RegCloseKey(hKey);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800059d0  mov     [rsp+hKey], rdx
0x1800059d5  push    rbx
0x1800059d6  sub     rsp, 30h
0x1800059da  mov     [rsp+38h+hKey], 0
0x1800059e3  mov     rbx, r9
0x1800059e6  mov     rax, r8
0x1800059e9  test    r8, r8
0x1800059ec  jz      short loc_180005A3A
0x1800059ee  lea     rcx, [rsp+38h+hKey]
0x1800059f3  mov     r9d, 2001Fh; samDesired
0x1800059f9  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800059fe  xor     r8d, r8d; ulOptions
0x180005a01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005a08  mov     rdx, rax; lpSubKey
0x180005a0b  call    cs:__imp_RegOpenKeyExW
0x180005a11  test    eax, eax
0x180005a13  jz      short loc_180005A1B
0x180005a15  add     rsp, 30h
0x180005a19  pop     rbx
0x180005a1a  retn
0x180005a1b  mov     rcx, [rsp+38h+hKey]; hKey
0x180005a20  mov     rdx, rbx; lpValueName
0x180005a23  call    cs:__imp_RegDeleteValueW
0x180005a29  mov     rcx, [rsp+38h+hKey]; hKey
0x180005a2e  mov     ebx, eax
0x180005a30  call    cs:__imp_RegCloseKey
0x180005a36  mov     eax, ebx
0x180005a38  jmp     short loc_180005A15
0x180005a3a  mov     eax, 57h ; 'W'
0x180005a3f  jmp     short loc_180005A15
```
