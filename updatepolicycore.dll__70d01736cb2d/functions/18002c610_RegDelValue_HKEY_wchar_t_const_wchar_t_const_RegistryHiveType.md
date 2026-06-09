# RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)

- ea: `0x18002c610`
- end: `0x18002c6d4`
- name: `?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f6c8`

## callees

- `0x18002bee8`
- `0x18002c610`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c670`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c670`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c692`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6af`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegDelValue(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 2;
  v5 = SetRegistryType(a1, &samDesired);
  if ( v5 >= 0 )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( v6 )
    {
      v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      v7 = RegDeleteValueW(hKey, a3);
      if ( v7 )
      {
        v5 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 <= 0 )
          v5 = v7;
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c610  mov     r11, rsp
0x18002c613  mov     [r11+8], rbx
0x18002c617  mov     [r11+20h], rsi
0x18002c61b  push    rdi
0x18002c61c  sub     rsp, 50h
0x18002c620  mov     rax, cs:__security_cookie
0x18002c627  xor     rax, rsp
0x18002c62a  mov     [rsp+58h+var_18], rax
0x18002c62f  mov     rsi, rdx
0x18002c632  mov     qword ptr [r11-20h], 0
0x18002c63a  lea     rdx, [r11-28h]
0x18002c63e  mov     [rsp+58h+samDesired], 2
0x18002c646  mov     rdi, r8
0x18002c649  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c64e  mov     ebx, eax
0x18002c650  test    eax, eax
0x18002c652  js      short loc_18002C6B5
0x18002c654  mov     r9d, [rsp+58h+samDesired]; samDesired
0x18002c659  lea     rax, [rsp+58h+hKey]
0x18002c65e  xor     r8d, r8d; ulOptions
0x18002c661  mov     [rsp+58h+phkResult], rax; phkResult
0x18002c666  mov     rdx, rsi; lpSubKey
0x18002c669  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c670  call    cs:__imp_RegOpenKeyExW
0x18002c676  test    eax, eax
0x18002c678  jz      short loc_18002C68A
0x18002c67a  movzx   ebx, ax
0x18002c67d  or      ebx, 80070000h
0x18002c683  test    eax, eax
0x18002c685  cmovle  ebx, eax
0x18002c688  jmp     short loc_18002C6B5
0x18002c68a  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c68f  mov     rdx, rdi; lpValueName
0x18002c692  call    cs:__imp_RegDeleteValueW
0x18002c698  test    eax, eax
0x18002c69a  jz      short loc_18002C6AA
0x18002c69c  movzx   ebx, ax
0x18002c69f  or      ebx, 80070000h
0x18002c6a5  test    eax, eax
0x18002c6a7  cmovle  ebx, eax
0x18002c6aa  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c6af  call    cs:__imp_RegCloseKey
0x18002c6b5  mov     eax, ebx
0x18002c6b7  mov     rcx, [rsp+58h+var_18]
0x18002c6bc  xor     rcx, rsp; StackCookie
0x18002c6bf  call    __security_check_cookie
0x18002c6c4  mov     rbx, [rsp+58h+arg_0]
0x18002c6c9  mov     rsi, [rsp+58h+arg_18]
0x18002c6ce  add     rsp, 50h
0x18002c6d2  pop     rdi
0x18002c6d3  retn
```
