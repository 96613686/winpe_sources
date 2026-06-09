# WsSaveGlobalMappingToRegistry

- ea: `0x18002ea70`
- end: `0x18002eafe`
- name: `WsSaveGlobalMappingToRegistry`
- size: `142`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001710`

## callees

- `0x18002e7a8`
- `0x18002ea70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eacb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eaeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eaeb`

## pseudocode

```c
__int64 __fastcall WsSaveGlobalMappingToRegistry(__int64 a1)
{
  unsigned int v2; // ebx
  DWORD v4; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v4 = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &v4);
  if ( !v2 )
  {
    v2 = SaveConnectionInfoToRegistry(hKey, a1);
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x18002ea70  mov     r11, rsp
0x18002ea73  mov     [r11+8], rbx
0x18002ea77  push    rdi
0x18002ea78  sub     rsp, 50h
0x18002ea7c  lea     rax, [r11+10h]
0x18002ea80  mov     qword ptr [r11+18h], 0
0x18002ea88  mov     [r11-18h], rax
0x18002ea8c  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18002ea93  lea     rax, [r11+18h]
0x18002ea97  mov     [rsp+58h+arg_8], 0
0x18002ea9f  mov     [r11-20h], rax
0x18002eaa3  mov     rdi, rcx
0x18002eaa6  mov     qword ptr [r11-28h], 0
0x18002eaae  xor     r9d, r9d; lpClass
0x18002eab1  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18002eab9  xor     r8d, r8d; Reserved
0x18002eabc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002eac3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002eacb  call    cs:__imp_RegCreateKeyExW
0x18002ead1  mov     ebx, eax
0x18002ead3  test    eax, eax
0x18002ead5  jnz     short loc_18002EAF1
0x18002ead7  mov     rcx, [rsp+58h+hKey]
0x18002eadc  mov     rdx, rdi
0x18002eadf  call    SaveConnectionInfoToRegistry
0x18002eae4  mov     rcx, [rsp+58h+hKey]; hKey
0x18002eae9  mov     ebx, eax
0x18002eaeb  call    cs:__imp_RegCloseKey
0x18002eaf1  mov     eax, ebx
0x18002eaf3  mov     rbx, [rsp+58h+arg_0]
0x18002eaf8  add     rsp, 50h
0x18002eafc  pop     rdi
0x18002eafd  retn
```
