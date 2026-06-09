# CUtils::IsSDPerfOptimized(void)

- ea: `0x18009dcf4`
- end: `0x18009dd93`
- name: `?IsSDPerfOptimized@CUtils@@SAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180076970`
- `0x180076cb0`
- `0x180077e94`

## callees

- `0x18009dcf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009dd64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009dd64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dd7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dd7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dd2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dd2c`

## string_xrefs

- `0x18009dd41`: `SessionDirectoryPerf`

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
0x18009dcf4  push    rbp
0x18009dcf6  mov     rbp, rsp
0x18009dcf9  sub     rsp, 30h
0x18009dcfd  lea     rax, [rbp+hKey]
0x18009dd01  mov     [rbp+hKey], 0
0x18009dd09  mov     r9d, 20019h; samDesired
0x18009dd0f  mov     [rsp+30h+phkResult], rax; phkResult
0x18009dd14  xor     r8d, r8d; ulOptions
0x18009dd17  mov     [rbp+Data], 1
0x18009dd1e  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Control\\Ter"...
0x18009dd25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009dd2c  call    cs:__imp_RegOpenKeyExW
0x18009dd32  test    eax, eax
0x18009dd34  jnz     short loc_18009DD85
0x18009dd36  mov     rcx, [rbp+hKey]; hKey
0x18009dd3a  lea     r9, [rbp+Type]; lpType
0x18009dd3e  mov     [rbp+Type], eax
0x18009dd41  lea     rdx, aSessiondirecto_1; "SessionDirectoryPerf"
0x18009dd48  lea     rax, [rbp+cbData]
0x18009dd4c  mov     [rbp+cbData], 4
0x18009dd53  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18009dd58  xor     r8d, r8d; lpReserved
0x18009dd5b  lea     rax, [rbp+Data]
0x18009dd5f  mov     [rsp+30h+phkResult], rax; lpData
0x18009dd64  call    cs:__imp_RegQueryValueExW
0x18009dd6a  test    eax, eax
0x18009dd6c  jnz     short loc_18009DD74
0x18009dd6e  cmp     [rbp+Type], 4
0x18009dd72  jz      short loc_18009DD7B
0x18009dd74  mov     [rbp+Data], 1
0x18009dd7b  mov     rcx, [rbp+hKey]; hKey
0x18009dd7f  call    cs:__imp_RegCloseKey
0x18009dd85  xor     eax, eax
0x18009dd87  cmp     [rbp+Data], eax
0x18009dd8a  setnz   al
0x18009dd8d  add     rsp, 30h
0x18009dd91  pop     rbp
0x18009dd92  retn
```
