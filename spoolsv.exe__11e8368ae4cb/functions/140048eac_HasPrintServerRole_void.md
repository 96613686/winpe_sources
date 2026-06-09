# HasPrintServerRole(void)

- ea: `0x140048eac`
- end: `0x140048fb8`
- name: `?HasPrintServerRole@@YA_NXZ`
- size: `268`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400490bc`

## callees

- `0x1400160a0`
- `0x14002abc0`
- `0x14002b810`
- `0x140048eac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140048f2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140048f2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140048f5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140048f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140048f82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140048f82`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140048ee8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140048ee8`

## string_xrefs

- `0x140048f20`: `Software\Microsoft\Print\Components`
- `0x140048f6a`: `Print server role registry key does not exist`
- `0x140048f8a`: `Print components registry key does not exist`

## pseudocode

```c
char HasPrintServerRole(void)
{
  char v0; // bl
  HKEY hKey; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  char v4; // [rsp+15Ah] [rbp-1Eh]

  v0 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) && v4 == 3 )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Print\\Components", 0, 0x20019u, &hKey) )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError("HasPrintServerRole", L"Print components registry key does not exist");
    }
    else
    {
      if ( RegQueryValueExW(hKey, L"Server-Role", 0, 0, 0, 0) )
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "HasPrintServerRole",
          L"Print server role registry key does not exist");
      else
        v0 = 1;
      RegCloseKey(hKey);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140048eac  push    rbx
0x140048eae  sub     rsp, 170h
0x140048eb5  mov     rax, cs:__security_cookie
0x140048ebc  xor     rax, rsp
0x140048ebf  mov     [rsp+178h+var_18], rax
0x140048ec7  xor     edx, edx; Val
0x140048ec9  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x140048ece  mov     r8d, 118h; Size
0x140048ed4  xor     bl, bl
0x140048ed6  call    memset_0
0x140048edb  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x140048ee0  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140048ee8  call    cs:__imp_GetVersionExW
0x140048eee  test    eax, eax
0x140048ef0  jz      loc_140048F9D
0x140048ef6  cmp     [rsp+178h+var_1E], 3
0x140048efe  jnz     loc_140048F9D
0x140048f04  lea     rax, [rsp+178h+hKey]
0x140048f09  mov     [rsp+178h+hKey], 0
0x140048f12  mov     r9d, 20019h; samDesired
0x140048f18  mov     [rsp+178h+phkResult], rax; phkResult
0x140048f1d  xor     r8d, r8d; ulOptions
0x140048f20  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Print\\Components"
0x140048f27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140048f2e  call    cs:__imp_RegOpenKeyExW
0x140048f34  test    eax, eax
0x140048f36  jnz     short loc_140048F8A
0x140048f38  mov     rcx, [rsp+178h+hKey]; hKey
0x140048f3d  lea     rdx, aServerRole; "Server-Role"
0x140048f44  mov     [rsp+178h+lpcbData], 0; lpcbData
0x140048f4d  xor     r9d, r9d; lpType
0x140048f50  xor     r8d, r8d; lpReserved
0x140048f53  mov     [rsp+178h+phkResult], 0; lpData
0x140048f5c  call    cs:__imp_RegQueryValueExW
0x140048f62  test    eax, eax
0x140048f64  jnz     short loc_140048F6A
0x140048f66  mov     bl, 1
0x140048f68  jmp     short loc_140048F7D
0x140048f6a  lea     rdx, aPrintServerRol; "Print server role registry key does not"...
0x140048f71  lea     rcx, aHasprintserver; "HasPrintServerRole"
0x140048f78  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048f7d  mov     rcx, [rsp+178h+hKey]; hKey
0x140048f82  call    cs:__imp_RegCloseKey
0x140048f88  jmp     short loc_140048F9D
0x140048f8a  lea     rdx, aPrintComponent; "Print components registry key does not "...
0x140048f91  lea     rcx, aHasprintserver; "HasPrintServerRole"
0x140048f98  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048f9d  mov     al, bl
0x140048f9f  mov     rcx, [rsp+178h+var_18]
0x140048fa7  xor     rcx, rsp; StackCookie
0x140048faa  call    __security_check_cookie
0x140048faf  add     rsp, 170h
0x140048fb6  pop     rbx
0x140048fb7  retn
```
