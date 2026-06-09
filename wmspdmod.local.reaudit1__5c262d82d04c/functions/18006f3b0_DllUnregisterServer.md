# DllUnregisterServer

- ea: `0x18006f3b0`
- end: `0x18006f42e`
- name: `DllUnregisterServer`
- size: `126`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001330`
- `0x18006f3b0`
- `0x180082660`

## import_xrefs

- `msdmo!DMOUnregister` at `0x18006f403`
- `msdmo!DMOUnregister` at `0x18006f403`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f3e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f3e7`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  HRESULT v1; // ebx
  HRESULT result; // eax
  WCHAR SubKey[80]; // [rsp+20h] [rbp-B8h] BYREF

  v1 = sub_180082660(v0);
  if ( v1 >= 0 )
    v1 = RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
  result = DMOUnregister(&clsidDMO, &guidCategory);
  if ( v1 < 0 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x18006f3b0  push    rbx
0x18006f3b2  sub     rsp, 0D0h
0x18006f3b9  mov     rax, cs:__security_cookie
0x18006f3c0  xor     rax, rsp
0x18006f3c3  mov     [rsp+0D8h+var_18], rax
0x18006f3cb  lea     rdx, [rsp+0D8h+SubKey]
0x18006f3d0  call    sub_180082660
0x18006f3d5  mov     ebx, eax
0x18006f3d7  test    eax, eax
0x18006f3d9  js      short loc_18006F3F5
0x18006f3db  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18006f3e0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006f3e7  call    cs:RegDeleteTreeW
0x18006f3ee  nop     dword ptr [rax+rax+00h]
0x18006f3f3  mov     ebx, eax
0x18006f3f5  lea     rdx, guidCategory; guidCategory
0x18006f3fc  lea     rcx, clsidDMO; clsidDMO
0x18006f403  call    cs:DMOUnregister
0x18006f40a  nop     dword ptr [rax+rax+00h]
0x18006f40f  test    ebx, ebx
0x18006f411  cmovs   eax, ebx
0x18006f414  mov     rcx, [rsp+0D8h+var_18]
0x18006f41c  xor     rcx, rsp; StackCookie
0x18006f41f  call    __security_check_cookie
0x18006f424  add     rsp, 0D0h
0x18006f42b  pop     rbx
0x18006f42c  retn
```
