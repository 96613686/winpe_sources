# IsSysprepPresent

- ea: `0x180012004`
- end: `0x180012052`
- name: `IsSysprepPresent`
- size: `78`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a6b0`

## callees

- `0x180012004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012044`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012044`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012032`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012032`

## pseudocode

```c
__int64 IsSysprepPresent()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\Sysprep",
          0,
          0x20019u,
          &hKey) )
  {
    v0 = 1;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180012004  push    rbx
0x180012006  sub     rsp, 30h
0x18001200a  lea     rax, [rsp+38h+hKey]
0x18001200f  xor     ebx, ebx
0x180012011  mov     r9d, 20019h; samDesired
0x180012017  mov     [rsp+38h+hKey], rbx
0x18001201c  xor     r8d, r8d; ulOptions
0x18001201f  mov     [rsp+38h+phkResult], rax; phkResult
0x180012024  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001202b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012032  call    cs:__imp_RegOpenKeyExW
0x180012038  test    eax, eax
0x18001203a  jnz     short loc_18001204A
0x18001203c  mov     rcx, [rsp+38h+hKey]; hKey
0x180012041  lea     ebx, [rax+1]
0x180012044  call    cs:__imp_RegCloseKey
0x18001204a  mov     eax, ebx
0x18001204c  add     rsp, 30h
0x180012050  pop     rbx
0x180012051  retn
```
