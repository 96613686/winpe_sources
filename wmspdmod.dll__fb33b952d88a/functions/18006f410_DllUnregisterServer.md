# DllUnregisterServer

- ea: `0x18006f410`
- end: `0x18006f48e`
- name: `DllUnregisterServer`
- size: `126`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001330`
- `0x18006f410`
- `0x1800826c0`

## import_xrefs

- `msdmo!DMOUnregister` at `0x18006f463`
- `msdmo!DMOUnregister` at `0x18006f463`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f447`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f447`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  HRESULT v1; // ebx
  HRESULT result; // eax
  WCHAR SubKey[80]; // [rsp+20h] [rbp-B8h] BYREF

  v1 = sub_1800826C0(v0);
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
0x18006f410  push    rbx
0x18006f412  sub     rsp, 0D0h
0x18006f419  mov     rax, cs:__security_cookie
0x18006f420  xor     rax, rsp
0x18006f423  mov     [rsp+0D8h+var_18], rax
0x18006f42b  lea     rdx, [rsp+0D8h+SubKey]
0x18006f430  call    sub_1800826C0
0x18006f435  mov     ebx, eax
0x18006f437  test    eax, eax
0x18006f439  js      short loc_18006F455
0x18006f43b  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18006f440  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006f447  call    cs:RegDeleteTreeW
0x18006f44e  nop     dword ptr [rax+rax+00h]
0x18006f453  mov     ebx, eax
0x18006f455  lea     rdx, guidCategory; guidCategory
0x18006f45c  lea     rcx, clsidDMO; clsidDMO
0x18006f463  call    cs:DMOUnregister
0x18006f46a  nop     dword ptr [rax+rax+00h]
0x18006f46f  test    ebx, ebx
0x18006f471  cmovs   eax, ebx
0x18006f474  mov     rcx, [rsp+0D8h+var_18]
0x18006f47c  xor     rcx, rsp; StackCookie
0x18006f47f  call    __security_check_cookie
0x18006f484  add     rsp, 0D0h
0x18006f48b  pop     rbx
0x18006f48c  retn
```
