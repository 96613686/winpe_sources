# _SHGetExplorerHkey(void)

- ea: `0x180019198`
- end: `0x18001921b`
- name: `?_SHGetExplorerHkey@@YAPEAUHKEY__@@XZ`
- size: `131`
- prototype: `HKEY(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001910c`

## callees

- `0x180019198`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019200`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019200`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001920b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001920b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800191b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800191b8`

## pseudocode

```c
HKEY _SHGetExplorerHkey(void)
{
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF
  HKEY v2; // [rsp+68h] [rbp+10h] BYREF

  phkResult = 0;
  v2 = 0;
  if ( !RegOpenCurrentUser(0x20006u, &phkResult) )
  {
    RegCreateKeyExW(
      phkResult,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      0,
      0,
      0,
      0x2000000u,
      0,
      &v2,
      0);
    RegCloseKey(phkResult);
  }
  return v2;
}

```

## disassembly

```asm
0x180019198  sub     rsp, 58h
0x18001919c  lea     rdx, [rsp+58h+phkResult]; phkResult
0x1800191a1  mov     [rsp+58h+phkResult], 0
0x1800191aa  mov     ecx, 20006h; samDesired
0x1800191af  mov     [rsp+58h+arg_8], 0
0x1800191b8  call    cs:__imp_RegOpenCurrentUser
0x1800191be  test    eax, eax
0x1800191c0  jnz     short loc_180019211
0x1800191c2  mov     rcx, [rsp+58h+phkResult]; hKey
0x1800191c7  lea     rax, [rsp+58h+arg_8]
0x1800191cc  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800191d5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800191dc  mov     [rsp+58h+var_20], rax; phkResult
0x1800191e1  xor     r9d, r9d; lpClass
0x1800191e4  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800191ed  xor     r8d, r8d; Reserved
0x1800191f0  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x1800191f8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180019200  call    cs:__imp_RegCreateKeyExW
0x180019206  mov     rcx, [rsp+58h+phkResult]; hKey
0x18001920b  call    cs:__imp_RegCloseKey
0x180019211  mov     rax, [rsp+58h+arg_8]
0x180019216  add     rsp, 58h
0x18001921a  retn
```
