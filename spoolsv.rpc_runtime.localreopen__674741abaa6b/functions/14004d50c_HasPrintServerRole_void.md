# HasPrintServerRole(void)

- ea: `0x14004d50c`
- end: `0x14004d631`
- name: `?HasPrintServerRole@@YA_NXZ`
- size: `293`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004d74c`

## callees

- `0x14001748c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14004d50c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d594`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d5c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d5c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d5f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d5f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14004d548`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14004d548`

## string_xrefs

- `0x14004d586`: `Software\Microsoft\Print\Components`
- `0x14004d5dc`: `Print server role registry key does not exist`
- `0x14004d602`: `Print components registry key does not exist`

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
0x14004d50c  push    rbx
0x14004d50e  sub     rsp, 170h
0x14004d515  mov     rax, cs:__security_cookie
0x14004d51c  xor     rax, rsp
0x14004d51f  mov     [rsp+178h+var_18], rax
0x14004d527  xor     edx, edx; Val
0x14004d529  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x14004d52e  mov     r8d, 118h; Size
0x14004d534  xor     bl, bl
0x14004d536  call    memset_0
0x14004d53b  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x14004d540  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14004d548  call    cs:__imp_GetVersionExW
0x14004d54f  nop     dword ptr [rax+rax+00h]
0x14004d554  test    eax, eax
0x14004d556  jz      loc_14004D615
0x14004d55c  cmp     [rsp+178h+var_1E], 3
0x14004d564  jnz     loc_14004D615
0x14004d56a  lea     rax, [rsp+178h+hKey]
0x14004d56f  mov     [rsp+178h+hKey], 0
0x14004d578  mov     r9d, 20019h; samDesired
0x14004d57e  mov     [rsp+178h+phkResult], rax; phkResult
0x14004d583  xor     r8d, r8d; ulOptions
0x14004d586  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Print\\Components"
0x14004d58d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004d594  call    cs:__imp_RegOpenKeyExW
0x14004d59b  nop     dword ptr [rax+rax+00h]
0x14004d5a0  test    eax, eax
0x14004d5a2  jnz     short loc_14004D602
0x14004d5a4  mov     rcx, [rsp+178h+hKey]; hKey
0x14004d5a9  lea     rdx, aServerRole; "Server-Role"
0x14004d5b0  mov     [rsp+178h+lpcbData], 0; lpcbData
0x14004d5b9  xor     r9d, r9d; lpType
0x14004d5bc  xor     r8d, r8d; lpReserved
0x14004d5bf  mov     [rsp+178h+phkResult], 0; lpData
0x14004d5c8  call    cs:__imp_RegQueryValueExW
0x14004d5cf  nop     dword ptr [rax+rax+00h]
0x14004d5d4  test    eax, eax
0x14004d5d6  jnz     short loc_14004D5DC
0x14004d5d8  mov     bl, 1
0x14004d5da  jmp     short loc_14004D5EF
0x14004d5dc  lea     rdx, aPrintServerRol; "Print server role registry key does not"...
0x14004d5e3  lea     rcx, aHasprintserver; "HasPrintServerRole"
0x14004d5ea  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004d5ef  mov     rcx, [rsp+178h+hKey]; hKey
0x14004d5f4  call    cs:__imp_RegCloseKey
0x14004d5fb  nop     dword ptr [rax+rax+00h]
0x14004d600  jmp     short loc_14004D615
0x14004d602  lea     rdx, aPrintComponent; "Print components registry key does not "...
0x14004d609  lea     rcx, aHasprintserver; "HasPrintServerRole"
0x14004d610  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004d615  mov     al, bl
0x14004d617  mov     rcx, [rsp+178h+var_18]
0x14004d61f  xor     rcx, rsp; StackCookie
0x14004d622  call    __security_check_cookie
0x14004d627  add     rsp, 170h
0x14004d62e  pop     rbx
0x14004d62f  retn
```
