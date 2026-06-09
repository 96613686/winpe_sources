# CUtils::IsSDPerfOptimized(void)

- ea: `0x1800a2c9c`
- end: `0x1800a2d4e`
- name: `?IsSDPerfOptimized@CUtils@@SAHXZ`
- size: `178`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180079f40`
- `0x18007a290`
- `0x18007b4b4`

## callees

- `0x1800a2c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2d12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2d12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2d33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2d33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2cd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2cd4`

## string_xrefs

- `0x1800a2cef`: `SessionDirectoryPerf`

## pseudocode

```c
_BOOL8 CUtils::IsSDPerfOptimized(void)
{
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\ClusterSettings",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"SessionDirectoryPerf", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 1;
    RegCloseKey(hKey);
  }
  return Data != 0;
}

```

## disassembly

```asm
0x1800a2c9c  push    rbp
0x1800a2c9e  mov     rbp, rsp
0x1800a2ca1  sub     rsp, 30h
0x1800a2ca5  lea     rax, [rbp+hKey]
0x1800a2ca9  mov     [rbp+hKey], 0
0x1800a2cb1  mov     r9d, 20019h; samDesired
0x1800a2cb7  mov     [rsp+30h+phkResult], rax; phkResult
0x1800a2cbc  xor     r8d, r8d; ulOptions
0x1800a2cbf  mov     [rbp+Data], 1
0x1800a2cc6  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Control\\Ter"...
0x1800a2ccd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2cd4  call    cs:__imp_RegOpenKeyExW
0x1800a2cdb  nop     dword ptr [rax+rax+00h]
0x1800a2ce0  test    eax, eax
0x1800a2ce2  jnz     short loc_1800A2D3F
0x1800a2ce4  mov     rcx, [rbp+hKey]; hKey
0x1800a2ce8  lea     r9, [rbp+Type]; lpType
0x1800a2cec  mov     [rbp+Type], eax
0x1800a2cef  lea     rdx, aSessiondirecto_1; "SessionDirectoryPerf"
0x1800a2cf6  lea     rax, [rbp+cbData]
0x1800a2cfa  mov     [rbp+cbData], 4
0x1800a2d01  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800a2d06  xor     r8d, r8d; lpReserved
0x1800a2d09  lea     rax, [rbp+Data]
0x1800a2d0d  mov     [rsp+30h+phkResult], rax; lpData
0x1800a2d12  call    cs:__imp_RegQueryValueExW
0x1800a2d19  nop     dword ptr [rax+rax+00h]
0x1800a2d1e  test    eax, eax
0x1800a2d20  jnz     short loc_1800A2D28
0x1800a2d22  cmp     [rbp+Type], 4
0x1800a2d26  jz      short loc_1800A2D2F
0x1800a2d28  mov     [rbp+Data], 1
0x1800a2d2f  mov     rcx, [rbp+hKey]; hKey
0x1800a2d33  call    cs:__imp_RegCloseKey
0x1800a2d3a  nop     dword ptr [rax+rax+00h]
0x1800a2d3f  xor     eax, eax
0x1800a2d41  cmp     [rbp+Data], eax
0x1800a2d44  setnz   al
0x1800a2d47  add     rsp, 30h
0x1800a2d4b  pop     rbp
0x1800a2d4c  retn
```
