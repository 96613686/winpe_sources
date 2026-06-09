# GetHKCUClassesCLSID(void *,HKEY__ * *,HKEY__ * *)

- ea: `0x180018d84`
- end: `0x180018e6d`
- name: `?GetHKCUClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z`
- size: `233`
- prototype: `void(void *, HKEY *, HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018624`
- `0x180018b44`

## callees

- `0x180018d84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180018db8`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180018db8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018df7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018e51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018df7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180018e12`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180018e12`

## string_xrefs

- `0x180018dc7`: `CLSID`
- `0x180018e21`: `Software\Classes\CLSID`

## pseudocode

```c
void __fastcall GetHKCUClassesCLSID(void *a1, HKEY *a2, HKEY *a3)
{
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  phkResult = 0;
  if ( !RegOpenUserClassesRoot(a1, 0, 0x20006u, &phkResult) )
  {
    RegCreateKeyExW(phkResult, L"CLSID", 0, 0, 0, 0x2000000u, 0, a2, 0);
    RegCloseKey(phkResult);
  }
  if ( !RegOpenCurrentUser(0x20006u, &phkResult) )
  {
    RegCreateKeyExW(phkResult, L"Software\\Classes\\CLSID", 0, 0, 0, 0x2000000u, 0, a3, 0);
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x180018d84  mov     [rsp+arg_0], rbx
0x180018d89  push    rdi
0x180018d8a  sub     rsp, 50h
0x180018d8e  mov     qword ptr [rdx], 0
0x180018d95  lea     r9, [rsp+58h+phkResult]; phkResult
0x180018d9a  mov     qword ptr [r8], 0
0x180018da1  mov     rdi, r8
0x180018da4  mov     rbx, rdx
0x180018da7  mov     [rsp+58h+phkResult], 0
0x180018db0  mov     r8d, 20006h; samDesired
0x180018db6  xor     edx, edx; dwOptions
0x180018db8  call    cs:__imp_RegOpenUserClassesRoot
0x180018dbe  test    eax, eax
0x180018dc0  jnz     short loc_180018E08
0x180018dc2  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018dc7  lea     rdx, aClsid; "CLSID"
0x180018dce  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180018dd7  xor     r9d, r9d; lpClass
0x180018dda  mov     [rsp+58h+var_20], rbx; phkResult
0x180018ddf  xor     r8d, r8d; Reserved
0x180018de2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180018deb  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180018df3  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180018df7  call    cs:__imp_RegCreateKeyExW
0x180018dfd  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018e02  call    cs:__imp_RegCloseKey
0x180018e08  lea     rdx, [rsp+58h+phkResult]; phkResult
0x180018e0d  mov     ecx, 20006h; samDesired
0x180018e12  call    cs:__imp_RegOpenCurrentUser
0x180018e18  test    eax, eax
0x180018e1a  jnz     short loc_180018E62
0x180018e1c  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018e21  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\CLSID"
0x180018e28  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180018e31  xor     r9d, r9d; lpClass
0x180018e34  mov     [rsp+58h+var_20], rdi; phkResult
0x180018e39  xor     r8d, r8d; Reserved
0x180018e3c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180018e45  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180018e4d  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180018e51  call    cs:__imp_RegCreateKeyExW
0x180018e57  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018e5c  call    cs:__imp_RegCloseKey
0x180018e62  mov     rbx, [rsp+58h+arg_0]
0x180018e67  add     rsp, 50h
0x180018e6b  pop     rdi
0x180018e6c  retn
```
