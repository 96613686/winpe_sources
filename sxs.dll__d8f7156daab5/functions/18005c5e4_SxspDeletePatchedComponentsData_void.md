# SxspDeletePatchedComponentsData(void)

- ea: `0x18005c5e4`
- end: `0x18005c6d3`
- name: `?SxspDeletePatchedComponentsData@@YAXXZ`
- size: `239`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800597f0`
- `0x180060ebc`

## callees

- `0x18002c540`
- `0x18005c5e4`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c67b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c67b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005c64e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005c6a0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005c64e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005c6a0`

## string_xrefs

- `0x18005c61b`: `Software\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x18005c66d`: `Software\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x18005c63e`: `PatchedComponents`
- `0x18005c690`: `PatchedComponents`

## pseudocode

```c
void SxspDeletePatchedComponentsData(void)
{
  HKEY phkResult; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
          0,
          0x10200u,
          &hKey) )
    RegDeleteKeyExW(hKey, L"PatchedComponents", 0x200u, 0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
          0,
          0x10100u,
          &phkResult) )
    RegDeleteKeyExW(phkResult, L"PatchedComponents", 0x100u, 0);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&phkResult);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&hKey);
}

```

## disassembly

```asm
0x18005c5e4  mov     r11, rsp
0x18005c5e7  sub     rsp, 58h
0x18005c5eb  mov     rax, cs:__security_cookie
0x18005c5f2  xor     rax, rsp
0x18005c5f5  mov     [rsp+58h+var_18], rax
0x18005c5fa  lea     rax, [r11-20h]
0x18005c5fe  mov     qword ptr [r11-20h], 0
0x18005c606  mov     r9d, 10200h; samDesired
0x18005c60c  mov     [r11-38h], rax
0x18005c610  xor     r8d, r8d; ulOptions
0x18005c613  mov     qword ptr [r11-28h], 0
0x18005c61b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005c622  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c629  call    cs:__imp_RegOpenKeyExW
0x18005c630  nop     dword ptr [rax+rax+00h]
0x18005c635  test    eax, eax
0x18005c637  jnz     short loc_18005C65A
0x18005c639  mov     rcx, [rsp+58h+hKey]; hKey
0x18005c63e  lea     rdx, aPatchedcompone; "PatchedComponents"
0x18005c645  xor     r9d, r9d; Reserved
0x18005c648  mov     r8d, 200h; samDesired
0x18005c64e  call    cs:__imp_RegDeleteKeyExW
0x18005c655  nop     dword ptr [rax+rax+00h]
0x18005c65a  lea     rax, [rsp+58h+var_28]
0x18005c65f  mov     r9d, 10100h; samDesired
0x18005c665  xor     r8d, r8d; ulOptions
0x18005c668  mov     [rsp+58h+phkResult], rax; phkResult
0x18005c66d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005c674  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c67b  call    cs:__imp_RegOpenKeyExW
0x18005c682  nop     dword ptr [rax+rax+00h]
0x18005c687  test    eax, eax
0x18005c689  jnz     short loc_18005C6AC
0x18005c68b  mov     rcx, [rsp+58h+var_28]; hKey
0x18005c690  lea     rdx, aPatchedcompone; "PatchedComponents"
0x18005c697  xor     r9d, r9d; Reserved
0x18005c69a  mov     r8d, 100h; samDesired
0x18005c6a0  call    cs:__imp_RegDeleteKeyExW
0x18005c6a7  nop     dword ptr [rax+rax+00h]
0x18005c6ac  lea     rcx, [rsp+58h+var_28]
0x18005c6b1  call    ??1?$CHandleTemplate@$1?hNull@@3QEAXEAVCOperatorFRegCloseKey@@@@QEAA@XZ; CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(void)
0x18005c6b6  lea     rcx, [rsp+58h+hKey]
0x18005c6bb  call    ??1?$CHandleTemplate@$1?hNull@@3QEAXEAVCOperatorFRegCloseKey@@@@QEAA@XZ; CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(void)
0x18005c6c0  mov     rcx, [rsp+58h+var_18]
0x18005c6c5  xor     rcx, rsp; StackCookie
0x18005c6c8  call    __security_check_cookie
0x18005c6cd  add     rsp, 58h
0x18005c6d1  retn
```
