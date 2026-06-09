# ScIsPrimitiveServicingRunLevelRequested(void)

- ea: `0x140042ffc`
- end: `0x1400430a9`
- name: `?ScIsPrimitiveServicingRunLevelRequested@@YAHXZ`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140039bd4`

## callees

- `0x140042ffc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004306b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004306b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043030`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043030`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004308b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004308b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004309a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004309a`

## string_xrefs

- `0x14004305a`: `SystemUpdateOnBoot`
- `0x140043084`: `SystemUpdateOnBoot`

## pseudocode

```c
__int64 ScIsPrimitiveServicingRunLevelRequested(void)
{
  unsigned int v0; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Session Manager", 0, 0x2001Fu, &hKey) )
  {
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"SystemUpdateOnBoot", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
    {
      RegDeleteValueW(hKey, L"SystemUpdateOnBoot");
      v0 = 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x140042ffc  push    rbp
0x140042ffe  push    rbx
0x140042fff  mov     rbp, rsp
0x140043002  sub     rsp, 38h
0x140043006  lea     rax, [rbp+hKey]
0x14004300a  mov     [rbp+hKey], 0
0x140043012  mov     r9d, 2001Fh; samDesired
0x140043018  mov     [rsp+38h+phkResult], rax; phkResult
0x14004301d  xor     r8d, r8d; ulOptions
0x140043020  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Control\\Ses"...
0x140043027  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004302e  xor     ebx, ebx
0x140043030  call    cs:__imp_RegOpenKeyExW
0x140043036  test    eax, eax
0x140043038  jnz     short loc_1400430A0
0x14004303a  mov     rcx, [rbp+hKey]; hKey
0x14004303e  lea     rax, [rbp+cbData]
0x140043042  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140043047  lea     r9, [rbp+Type]; lpType
0x14004304b  lea     rax, [rbp+Data]
0x14004304f  mov     [rbp+Data], ebx
0x140043052  xor     r8d, r8d; lpReserved
0x140043055  mov     [rsp+38h+phkResult], rax; lpData
0x14004305a  lea     rdx, aSystemupdateon; "SystemUpdateOnBoot"
0x140043061  mov     [rbp+cbData], 4
0x140043068  mov     [rbp+Type], ebx
0x14004306b  call    cs:__imp_RegQueryValueExW
0x140043071  test    eax, eax
0x140043073  jnz     short loc_140043096
0x140043075  cmp     [rbp+Type], 4
0x140043079  jnz     short loc_140043096
0x14004307b  cmp     [rbp+Data], ebx
0x14004307e  jz      short loc_140043096
0x140043080  mov     rcx, [rbp+hKey]; hKey
0x140043084  lea     rdx, aSystemupdateon; "SystemUpdateOnBoot"
0x14004308b  call    cs:__imp_RegDeleteValueW
0x140043091  mov     ebx, 1
0x140043096  mov     rcx, [rbp+hKey]; hKey
0x14004309a  call    cs:__imp_RegCloseKey
0x1400430a0  mov     eax, ebx
0x1400430a2  add     rsp, 38h
0x1400430a6  pop     rbx
0x1400430a7  pop     rbp
0x1400430a8  retn
```
