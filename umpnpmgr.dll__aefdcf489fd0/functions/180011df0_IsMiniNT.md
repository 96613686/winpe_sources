# IsMiniNT

- ea: `0x180011df0`
- end: `0x180011e3e`
- name: `IsMiniNT`
- size: `78`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a6b0`
- `0x18000cf30`

## callees

- `0x180011df0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e1e`

## pseudocode

```c
__int64 IsMiniNT()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey) )
  {
    v0 = 1;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180011df0  push    rbx
0x180011df2  sub     rsp, 30h
0x180011df6  lea     rax, [rsp+38h+hKey]
0x180011dfb  xor     ebx, ebx
0x180011dfd  mov     r9d, 20019h; samDesired
0x180011e03  mov     [rsp+38h+hKey], rbx
0x180011e08  xor     r8d, r8d; ulOptions
0x180011e0b  mov     [rsp+38h+phkResult], rax; phkResult
0x180011e10  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180011e17  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011e1e  call    cs:__imp_RegOpenKeyExW
0x180011e24  test    eax, eax
0x180011e26  jnz     short loc_180011E36
0x180011e28  mov     rcx, [rsp+38h+hKey]; hKey
0x180011e2d  lea     ebx, [rax+1]
0x180011e30  call    cs:__imp_RegCloseKey
0x180011e36  mov     eax, ebx
0x180011e38  add     rsp, 30h
0x180011e3c  pop     rbx
0x180011e3d  retn
```
