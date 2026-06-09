# CRegistry::SetPlatformID(void)

- ea: `0x18000b410`
- end: `0x18000b470`
- name: `?SetPlatformID@CRegistry@@CAHXZ`
- size: `96`
- prototype: `BOOL(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800034f0`

## callees

- `0x18001d377`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x18000b448`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x18000b448`

## pseudocode

```c
BOOL CRegistry::SetPlatformID(void)
{
  BOOL result; // eax
  _OSVERSIONINFOA VersionInformation; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  VersionInformation.dwOSVersionInfoSize = 148;
  result = GetVersionExA(&VersionInformation);
  CRegistry::s_dwPlatform = VersionInformation.dwPlatformId;
  return result;
}

```

## disassembly

```asm
0x18000b410  sub     rsp, 0D8h
0x18000b417  mov     rax, cs:__security_cookie
0x18000b41e  xor     rax, rsp
0x18000b421  mov     [rsp+0D8h+var_18], rax
0x18000b429  xor     edx, edx; Val
0x18000b42b  lea     rcx, [rsp+0D8h+VersionInformation.dwMajorVersion]; void *
0x18000b430  mov     r8d, 90h; Size
0x18000b436  call    memset_0
0x18000b43b  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x18000b440  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], 94h
0x18000b448  call    cs:__imp_GetVersionExA
0x18000b44e  mov     ecx, [rsp+0D8h+VersionInformation.dwPlatformId]
0x18000b452  mov     cs:?s_dwPlatform@CRegistry@@0KA, ecx; ulong CRegistry::s_dwPlatform
0x18000b458  mov     rcx, [rsp+0D8h+var_18]
0x18000b460  xor     rcx, rsp; StackCookie
0x18000b463  call    __security_check_cookie
0x18000b468  add     rsp, 0D8h
0x18000b46f  retn
```
