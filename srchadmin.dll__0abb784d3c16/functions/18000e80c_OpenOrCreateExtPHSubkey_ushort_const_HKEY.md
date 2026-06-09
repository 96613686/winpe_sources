# OpenOrCreateExtPHSubkey(ushort const *,HKEY__ * *)

- ea: `0x18000e80c`
- end: `0x18000e8d0`
- name: `?OpenOrCreateExtPHSubkey@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e938`

## callees

- `0x18000e80c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e862`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e8a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e862`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e8a3`

## pseudocode

```c
__int64 __fastcall OpenOrCreateExtPHSubkey(LPCWSTR lpSubKey, PHKEY phkResult)
{
  LSTATUS Key; // ebx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  *phkResult = 0;
  hKey = 0;
  Key = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( !Key )
  {
    Key = RegCreateKeyExW(hKey, L"PersistentHandler", 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    RegCloseKey(hKey);
  }
  if ( Key > 0 )
    return (unsigned __int16)Key | 0x80070000;
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18000e80c  mov     r11, rsp
0x18000e80f  mov     [r11+8], rbx
0x18000e813  push    rdi
0x18000e814  sub     rsp, 50h
0x18000e818  mov     qword ptr [r11-18h], 0
0x18000e820  lea     rax, [r11+10h]
0x18000e824  mov     [r11-20h], rax
0x18000e828  mov     rdi, rdx
0x18000e82b  mov     qword ptr [r11-28h], 0
0x18000e833  xor     r9d, r9d; lpClass
0x18000e836  mov     qword ptr [rdx], 0
0x18000e83d  xor     r8d, r8d; Reserved
0x18000e840  mov     rdx, rcx; lpSubKey
0x18000e843  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000e84b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e852  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000e85a  mov     qword ptr [r11+10h], 0
0x18000e862  call    cs:__imp_RegCreateKeyExW
0x18000e868  mov     ebx, eax
0x18000e86a  test    eax, eax
0x18000e86c  jnz     short loc_18000E8B6
0x18000e86e  mov     rcx, [rsp+58h+hKey]; hKey
0x18000e873  lea     rdx, aPersistenthand; "PersistentHandler"
0x18000e87a  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000e883  xor     r9d, r9d; lpClass
0x18000e886  mov     [rsp+58h+phkResult], rdi; phkResult
0x18000e88b  xor     r8d, r8d; Reserved
0x18000e88e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000e897  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000e89f  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18000e8a3  call    cs:__imp_RegCreateKeyExW
0x18000e8a9  mov     rcx, [rsp+58h+hKey]; hKey
0x18000e8ae  mov     ebx, eax
0x18000e8b0  call    cs:__imp_RegCloseKey
0x18000e8b6  test    ebx, ebx
0x18000e8b8  jle     short loc_18000E8C3
0x18000e8ba  movzx   ebx, bx
0x18000e8bd  or      ebx, 80070000h
0x18000e8c3  mov     eax, ebx
0x18000e8c5  mov     rbx, [rsp+58h+arg_0]
0x18000e8ca  add     rsp, 50h
0x18000e8ce  pop     rdi
0x18000e8cf  retn
```
