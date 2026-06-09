# RegDefaultDocInstalled(void)

- ea: `0x180027e90`
- end: `0x180027f20`
- name: `?RegDefaultDocInstalled@@YAJXZ`
- size: `144`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027b48`
- `0x180028144`

## callees

- `0x180027e90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180027f12`
- `ADVAPI32!RegCloseKey` at `0x180027f12`
- `ADVAPI32!RegOpenKeyExW` at `0x180027ebc`
- `ADVAPI32!RegOpenKeyExW` at `0x180027ebc`
- `ADVAPI32!RegSetValueExW` at `0x180027ef0`
- `ADVAPI32!RegSetValueExW` at `0x180027ef0`

## string_xrefs

- `0x180027ee1`: `DefaultDocInstalled`

## pseudocode

```c
__int64 RegDefaultDocInstalled(void)
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 2u, &hKey);
  if ( v1 || (Data = 1, (v1 = RegSetValueExW(hKey, L"DefaultDocInstalled", 0, 4u, (const BYTE *)&Data, 4u)) != 0) )
  {
    v0 = (unsigned __int16)v1 | 0x80070000;
    if ( v1 <= 0 )
      v0 = v1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180027e90  push    rbx
0x180027e92  sub     rsp, 30h
0x180027e96  xor     ebx, ebx
0x180027e98  lea     rax, [rsp+38h+hKey]
0x180027e9d  and     [rsp+38h+hKey], rbx
0x180027ea2  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x180027ea9  xor     r8d, r8d; ulOptions
0x180027eac  mov     [rsp+38h+phkResult], rax; phkResult
0x180027eb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027eb8  lea     r9d, [rbx+2]; samDesired
0x180027ebc  call    cs:__imp_RegOpenKeyExW
0x180027ec2  test    eax, eax
0x180027ec4  jnz     short loc_180027EFA
0x180027ec6  mov     rcx, [rsp+38h+hKey]; hKey
0x180027ecb  lea     r9d, [rbx+4]; dwType
0x180027ecf  lea     rax, [rsp+38h+Data]
0x180027ed4  mov     [rsp+38h+cbData], r9d; cbData
0x180027ed9  xor     r8d, r8d; Reserved
0x180027edc  mov     [rsp+38h+phkResult], rax; lpData
0x180027ee1  lea     rdx, ValueName; "DefaultDocInstalled"
0x180027ee8  mov     [rsp+38h+Data], 1
0x180027ef0  call    cs:__imp_RegSetValueExW
0x180027ef6  test    eax, eax
0x180027ef8  jz      short loc_180027F08
0x180027efa  movzx   ebx, ax
0x180027efd  or      ebx, 80070000h
0x180027f03  test    eax, eax
0x180027f05  cmovle  ebx, eax
0x180027f08  mov     rcx, [rsp+38h+hKey]; hKey
0x180027f0d  test    rcx, rcx
0x180027f10  jz      short loc_180027F18
0x180027f12  call    cs:__imp_RegCloseKey
0x180027f18  mov     eax, ebx
0x180027f1a  add     rsp, 30h
0x180027f1e  pop     rbx
0x180027f1f  retn
```
