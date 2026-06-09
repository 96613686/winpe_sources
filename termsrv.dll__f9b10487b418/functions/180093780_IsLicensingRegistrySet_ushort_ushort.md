# IsLicensingRegistrySet(ushort *,ushort *)

- ea: `0x180093780`
- end: `0x180093822`
- name: `?IsLicensingRegistrySet@@YAHPEAG0@Z`
- size: `162`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180093758`

## callees

- `0x180093780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800937f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800937f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093813`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800937bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800937bd`

## string_xrefs

- `0x1800937ad`: `System\CurrentControlSet\Services\termservice`

## pseudocode

```c
__int64 __fastcall IsLicensingRegistrySet(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  unsigned __int16 *Data; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Type = a2;
  Data = a1;
  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\termservice", 0, 0x20019u, &hKey) )
  {
    LODWORD(Type) = 0;
    LODWORD(Data) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"fForceRDVHLicensing", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) && (_DWORD)Type == 4 )
      LOBYTE(v2) = (_DWORD)Data == 1;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180093780  mov     [rsp-10h+Type], rdx
0x180093785  mov     [rsp-10h+Data], rcx
0x18009378a  push    rbp
0x18009378b  push    rbx
0x18009378c  mov     rbp, rsp
0x18009378f  sub     rsp, 38h
0x180093793  lea     rax, [rbp+hKey]
0x180093797  mov     [rbp+hKey], 0
0x18009379f  mov     r9d, 20019h; samDesired
0x1800937a5  mov     [rsp+38h+phkResult], rax; phkResult
0x1800937aa  xor     r8d, r8d; ulOptions
0x1800937ad  lea     rdx, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\te"...
0x1800937b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800937bb  xor     ebx, ebx
0x1800937bd  call    cs:__imp_RegOpenKeyExW
0x1800937c3  test    eax, eax
0x1800937c5  jnz     short loc_180093819
0x1800937c7  mov     rcx, [rbp+hKey]; hKey
0x1800937cb  lea     rax, [rbp+cbData]
0x1800937cf  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800937d4  lea     r9, [rbp+Type]; lpType
0x1800937d8  lea     rax, [rbp+Data]
0x1800937dc  mov     dword ptr [rbp+Type], ebx
0x1800937df  xor     r8d, r8d; lpReserved
0x1800937e2  mov     [rsp+38h+phkResult], rax; lpData
0x1800937e7  lea     rdx, aFforcerdvhlice; "fForceRDVHLicensing"
0x1800937ee  mov     dword ptr [rbp+Data], ebx
0x1800937f1  mov     [rbp+cbData], 4
0x1800937f8  call    cs:__imp_RegQueryValueExW
0x1800937fe  test    eax, eax
0x180093800  jnz     short loc_18009380F
0x180093802  cmp     dword ptr [rbp+Type], 4
0x180093806  jnz     short loc_18009380F
0x180093808  cmp     dword ptr [rbp+Data], 1
0x18009380c  setz    bl
0x18009380f  mov     rcx, [rbp+hKey]; hKey
0x180093813  call    cs:__imp_RegCloseKey
0x180093819  mov     eax, ebx
0x18009381b  add     rsp, 38h
0x18009381f  pop     rbx
0x180093820  pop     rbp
0x180093821  retn
```
