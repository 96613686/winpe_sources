# SaveLastClockRate(void)

- ea: `0x180039dd4`
- end: `0x180039ea0`
- name: `?SaveLastClockRate@@YAJXZ`
- size: `204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180009a80`

## callees

- `0x180039dd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039e20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039e20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039e85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039e85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039e65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039e65`

## string_xrefs

- `0x180039e12`: `System\CurrentControlSet\Services\W32Time\Config`

## pseudocode

```c
__int64 SaveLastClockRate(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  LSTATUS v2; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( dword_1800A3EDC != 2 || dword_1800A3810 == 3 )
    return 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 0, 2u, &hKey);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
    v2 = RegSetValueExW(hKey, L"LastClockRate", 0, 4u, &Data, 4u);
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    RegCloseKey(hKey);
    if ( v1 >= 0 )
      return 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180039dd4  push    rbx
0x180039dd6  sub     rsp, 30h
0x180039dda  mov     r9d, 2; samDesired
0x180039de0  cmp     cs:dword_1800A3EDC, r9d
0x180039de7  jnz     loc_180039E95
0x180039ded  mov     eax, cs:dword_1800A3810
0x180039df3  cmp     eax, 3
0x180039df6  jz      loc_180039E95
0x180039dfc  lea     rax, [rsp+38h+hKey]
0x180039e01  mov     [rsp+38h+hKey], 0
0x180039e0a  xor     r8d, r8d; ulOptions
0x180039e0d  mov     [rsp+38h+phkResult], rax; phkResult
0x180039e12  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180039e19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039e20  call    cs:__imp_RegOpenKeyExW
0x180039e27  nop     dword ptr [rax+rax+00h]
0x180039e2c  mov     ebx, eax
0x180039e2e  test    eax, eax
0x180039e30  jle     short loc_180039E3B
0x180039e32  movzx   ebx, ax
0x180039e35  or      ebx, 80070000h
0x180039e3b  test    ebx, ebx
0x180039e3d  js      short loc_180039E97
0x180039e3f  mov     rcx, [rsp+38h+hKey]; hKey
0x180039e44  lea     rax, Data
0x180039e4b  mov     r9d, 4; dwType
0x180039e51  lea     rdx, aLastclockrate; "LastClockRate"
0x180039e58  mov     [rsp+38h+cbData], r9d; cbData
0x180039e5d  xor     r8d, r8d; Reserved
0x180039e60  mov     [rsp+38h+phkResult], rax; lpData
0x180039e65  call    cs:__imp_RegSetValueExW
0x180039e6c  nop     dword ptr [rax+rax+00h]
0x180039e71  mov     ebx, eax
0x180039e73  test    eax, eax
0x180039e75  jle     short loc_180039E80
0x180039e77  movzx   ebx, ax
0x180039e7a  or      ebx, 80070000h
0x180039e80  mov     rcx, [rsp+38h+hKey]; hKey
0x180039e85  call    cs:__imp_RegCloseKey
0x180039e8c  nop     dword ptr [rax+rax+00h]
0x180039e91  test    ebx, ebx
0x180039e93  js      short loc_180039E97
0x180039e95  xor     ebx, ebx
0x180039e97  mov     eax, ebx
0x180039e99  add     rsp, 30h
0x180039e9d  pop     rbx
0x180039e9e  retn
```
