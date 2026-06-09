# GetHKCUWow64ClassesCLSID(void *,HKEY__ * *,HKEY__ * *)

- ea: `0x180018e74`
- end: `0x180018f5d`
- name: `?GetHKCUWow64ClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z`
- size: `233`
- prototype: `void(void *, HKEY *, HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018624`
- `0x180018b44`

## callees

- `0x180018e74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180018ea8`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180018ea8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018ee7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018f41`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018ee7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018f41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180018f02`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180018f02`

## string_xrefs

- `0x180018eb7`: `Wow6432Node\CLSID`
- `0x180018f11`: `Software\Classes\Wow6432Node\CLSID`

## pseudocode

```c
void __fastcall GetHKCUWow64ClassesCLSID(void *a1, HKEY *a2, HKEY *a3)
{
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  phkResult = 0;
  if ( !RegOpenUserClassesRoot(a1, 0, 0x20006u, &phkResult) )
  {
    RegCreateKeyExW(phkResult, L"Wow6432Node\\CLSID", 0, 0, 0, 0x2000000u, 0, a2, 0);
    RegCloseKey(phkResult);
  }
  if ( !RegOpenCurrentUser(0x20006u, &phkResult) )
  {
    RegCreateKeyExW(phkResult, L"Software\\Classes\\Wow6432Node\\CLSID", 0, 0, 0, 0x2000000u, 0, a3, 0);
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x180018e74  mov     [rsp+arg_0], rbx
0x180018e79  push    rdi
0x180018e7a  sub     rsp, 50h
0x180018e7e  mov     qword ptr [rdx], 0
0x180018e85  lea     r9, [rsp+58h+phkResult]; phkResult
0x180018e8a  mov     qword ptr [r8], 0
0x180018e91  mov     rdi, r8
0x180018e94  mov     rbx, rdx
0x180018e97  mov     [rsp+58h+phkResult], 0
0x180018ea0  mov     r8d, 20006h; samDesired
0x180018ea6  xor     edx, edx; dwOptions
0x180018ea8  call    cs:__imp_RegOpenUserClassesRoot
0x180018eae  test    eax, eax
0x180018eb0  jnz     short loc_180018EF8
0x180018eb2  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018eb7  lea     rdx, aWow6432nodeCls; "Wow6432Node\\CLSID"
0x180018ebe  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180018ec7  xor     r9d, r9d; lpClass
0x180018eca  mov     [rsp+58h+var_20], rbx; phkResult
0x180018ecf  xor     r8d, r8d; Reserved
0x180018ed2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180018edb  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180018ee3  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180018ee7  call    cs:__imp_RegCreateKeyExW
0x180018eed  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018ef2  call    cs:__imp_RegCloseKey
0x180018ef8  lea     rdx, [rsp+58h+phkResult]; phkResult
0x180018efd  mov     ecx, 20006h; samDesired
0x180018f02  call    cs:__imp_RegOpenCurrentUser
0x180018f08  test    eax, eax
0x180018f0a  jnz     short loc_180018F52
0x180018f0c  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018f11  lea     rdx, aSoftwareClasse; "Software\\Classes\\Wow6432Node\\CLSID"
0x180018f18  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180018f21  xor     r9d, r9d; lpClass
0x180018f24  mov     [rsp+58h+var_20], rdi; phkResult
0x180018f29  xor     r8d, r8d; Reserved
0x180018f2c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180018f35  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180018f3d  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180018f41  call    cs:__imp_RegCreateKeyExW
0x180018f47  mov     rcx, [rsp+58h+phkResult]; hKey
0x180018f4c  call    cs:__imp_RegCloseKey
0x180018f52  mov     rbx, [rsp+58h+arg_0]
0x180018f57  add     rsp, 50h
0x180018f5b  pop     rdi
0x180018f5c  retn
```
