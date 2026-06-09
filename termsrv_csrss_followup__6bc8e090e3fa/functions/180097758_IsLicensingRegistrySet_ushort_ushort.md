# IsLicensingRegistrySet(ushort *,ushort *)

- ea: `0x180097758`
- end: `0x18009780d`
- name: `?IsLicensingRegistrySet@@YAHPEAG0@Z`
- size: `181`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180097730`

## callees

- `0x180097758`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800977d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800977d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097795`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097795`

## string_xrefs

- `0x180097785`: `System\CurrentControlSet\Services\termservice`

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
0x180097758  mov     [rsp-10h+Type], rdx
0x18009775d  mov     [rsp-10h+Data], rcx
0x180097762  push    rbp
0x180097763  push    rbx
0x180097764  mov     rbp, rsp
0x180097767  sub     rsp, 38h
0x18009776b  lea     rax, [rbp+hKey]
0x18009776f  mov     [rbp+hKey], 0
0x180097777  mov     r9d, 20019h; samDesired
0x18009777d  mov     [rsp+38h+phkResult], rax; phkResult
0x180097782  xor     r8d, r8d; ulOptions
0x180097785  lea     rdx, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\te"...
0x18009778c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097793  xor     ebx, ebx
0x180097795  call    cs:__imp_RegOpenKeyExW
0x18009779c  nop     dword ptr [rax+rax+00h]
0x1800977a1  test    eax, eax
0x1800977a3  jnz     short loc_180097803
0x1800977a5  mov     rcx, [rbp+hKey]; hKey
0x1800977a9  lea     rax, [rbp+cbData]
0x1800977ad  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800977b2  lea     r9, [rbp+Type]; lpType
0x1800977b6  lea     rax, [rbp+Data]
0x1800977ba  mov     dword ptr [rbp+Type], ebx
0x1800977bd  xor     r8d, r8d; lpReserved
0x1800977c0  mov     [rsp+38h+phkResult], rax; lpData
0x1800977c5  lea     rdx, aFforcerdvhlice; "fForceRDVHLicensing"
0x1800977cc  mov     dword ptr [rbp+Data], ebx
0x1800977cf  mov     [rbp+cbData], 4
0x1800977d6  call    cs:__imp_RegQueryValueExW
0x1800977dd  nop     dword ptr [rax+rax+00h]
0x1800977e2  test    eax, eax
0x1800977e4  jnz     short loc_1800977F3
0x1800977e6  cmp     dword ptr [rbp+Type], 4
0x1800977ea  jnz     short loc_1800977F3
0x1800977ec  cmp     dword ptr [rbp+Data], 1
0x1800977f0  setz    bl
0x1800977f3  mov     rcx, [rbp+hKey]; hKey
0x1800977f7  call    cs:__imp_RegCloseKey
0x1800977fe  nop     dword ptr [rax+rax+00h]
0x180097803  mov     eax, ebx
0x180097805  add     rsp, 38h
0x180097809  pop     rbx
0x18009780a  pop     rbp
0x18009780b  retn
```
