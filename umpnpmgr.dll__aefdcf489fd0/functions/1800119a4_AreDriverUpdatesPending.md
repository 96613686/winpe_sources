# AreDriverUpdatesPending

- ea: `0x1800119a4`
- end: `0x180011a51`
- name: `AreDriverUpdatesPending`
- size: `173`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000ea20`
- `0x180013fb0`

## callees

- `0x1800119a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800119eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800119eb`

## string_xrefs

- `0x1800119cf`: `SYSTEM\CurrentControlSet\Services\DeviceInstall\Parameters`
- `0x180011a19`: `DriverUpdatesPending`

## pseudocode

```c
_BOOL8 AreDriverUpdatesPending()
{
  LSTATUS v0; // ebx
  int v1; // ecx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\DeviceInstall\\Parameters",
         0,
         1u,
         &hKey)
    || (cbData = 4,
        v0 = RegQueryValueExW(hKey, L"DriverUpdatesPending", 0, &Type, (LPBYTE)&Data, &cbData),
        RegCloseKey(hKey),
        !v0)
    && Type == 4 )
  {
    v1 = Data;
  }
  else
  {
    v1 = 0;
  }
  return v1 != 0;
}

```

## disassembly

```asm
0x1800119a4  push    rbp
0x1800119a6  push    rbx
0x1800119a7  mov     rbp, rsp
0x1800119aa  sub     rsp, 38h
0x1800119ae  lea     rax, [rbp+hKey]
0x1800119b2  mov     [rbp+hKey], 0
0x1800119ba  mov     r9d, 1; samDesired
0x1800119c0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800119c5  xor     r8d, r8d; ulOptions
0x1800119c8  mov     [rbp+Type], 0
0x1800119cf  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\De"...
0x1800119d6  mov     [rbp+cbData], 0
0x1800119dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800119e4  mov     [rbp+Data], 0
0x1800119eb  call    cs:__imp_RegOpenKeyExW
0x1800119f1  test    eax, eax
0x1800119f3  jnz     short loc_180011A40
0x1800119f5  mov     rcx, [rbp+hKey]; hKey
0x1800119f9  lea     rax, [rbp+cbData]
0x1800119fd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180011a02  lea     r9, [rbp+Type]; lpType
0x180011a06  lea     rax, [rbp+Data]
0x180011a0a  mov     [rbp+cbData], 4
0x180011a11  xor     r8d, r8d; lpReserved
0x180011a14  mov     [rsp+38h+phkResult], rax; lpData
0x180011a19  lea     rdx, aDriverupdatesp; "DriverUpdatesPending"
0x180011a20  call    cs:__imp_RegQueryValueExW
0x180011a26  mov     rcx, [rbp+hKey]; hKey
0x180011a2a  mov     ebx, eax
0x180011a2c  call    cs:__imp_RegCloseKey
0x180011a32  test    ebx, ebx
0x180011a34  jnz     short loc_180011A3C
0x180011a36  cmp     [rbp+Type], 4
0x180011a3a  jz      short loc_180011A40
0x180011a3c  xor     ecx, ecx
0x180011a3e  jmp     short loc_180011A43
0x180011a40  mov     ecx, [rbp+Data]
0x180011a43  xor     eax, eax
0x180011a45  test    ecx, ecx
0x180011a47  setnz   al
0x180011a4a  add     rsp, 38h
0x180011a4e  pop     rbx
0x180011a4f  pop     rbp
0x180011a50  retn
```
