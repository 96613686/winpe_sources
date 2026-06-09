# Is45PerfCounterInstallError(void)

- ea: `0x18003a2f8`
- end: `0x18003a3c6`
- name: `?Is45PerfCounterInstallError@@YAHXZ`
- size: `206`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180039aa4`

## callees

- `0x18003a2f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003a3b7`
- `ADVAPI32!RegCloseKey` at `0x18003a3b7`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a338`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a338`
- `ADVAPI32!RegQueryValueExW` at `0x18003a365`
- `ADVAPI32!RegQueryValueExW` at `0x18003a392`
- `ADVAPI32!RegQueryValueExW` at `0x18003a365`
- `ADVAPI32!RegQueryValueExW` at `0x18003a392`

## string_xrefs

- `0x18003a30f`: `SYSTEM\CurrentControlSet\services\ASP.NET_4.0.30319\Performance`

## pseudocode

```c
_BOOL8 Is45PerfCounterInstallError(void)
{
  BOOL v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v3; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Data = 0;
  v3 = 0;
  cbData = 4;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\services\\ASP.NET_4.0.30319\\Performance",
          0,
          0x20019u,
          &hKey)
    && !RegQueryValueExW(hKey, L"First Counter", 0, 0, (LPBYTE)&Data, &cbData)
    && !RegQueryValueExW(hKey, L"Last Counter", 0, 0, (LPBYTE)&v3, &cbData) )
  {
    v0 = (unsigned int)(v3 - Data) < 0xE0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18003a2f8  push    rbp
0x18003a2fa  push    rbx
0x18003a2fb  mov     rbp, rsp
0x18003a2fe  sub     rsp, 38h
0x18003a302  and     [rbp+hKey], 0
0x18003a307  lea     rax, [rbp+hKey]
0x18003a30b  and     [rbp+Data], 0
0x18003a30f  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\services\\AS"...
0x18003a316  and     [rbp+arg_8], 0
0x18003a31a  mov     r9d, 20019h; samDesired
0x18003a320  xor     r8d, r8d; ulOptions
0x18003a323  mov     [rsp+38h+phkResult], rax; phkResult
0x18003a328  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a32f  mov     [rbp+cbData], 4
0x18003a336  xor     ebx, ebx
0x18003a338  call    cs:__imp_RegOpenKeyExW
0x18003a33e  test    eax, eax
0x18003a340  jnz     short loc_18003A3AE
0x18003a342  mov     rcx, [rbp+hKey]; hKey
0x18003a346  lea     rax, [rbp+cbData]
0x18003a34a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003a34f  lea     rdx, aFirstCounter; "First Counter"
0x18003a356  lea     rax, [rbp+Data]
0x18003a35a  xor     r9d, r9d; lpType
0x18003a35d  xor     r8d, r8d; lpReserved
0x18003a360  mov     [rsp+38h+phkResult], rax; lpData
0x18003a365  call    cs:__imp_RegQueryValueExW
0x18003a36b  test    eax, eax
0x18003a36d  jnz     short loc_18003A3AE
0x18003a36f  mov     rcx, [rbp+hKey]; hKey
0x18003a373  lea     rax, [rbp+cbData]
0x18003a377  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003a37c  lea     rdx, aLastCounter; "Last Counter"
0x18003a383  lea     rax, [rbp+arg_8]
0x18003a387  xor     r9d, r9d; lpType
0x18003a38a  xor     r8d, r8d; lpReserved
0x18003a38d  mov     [rsp+38h+phkResult], rax; lpData
0x18003a392  call    cs:__imp_RegQueryValueExW
0x18003a398  test    eax, eax
0x18003a39a  jnz     short loc_18003A3AE
0x18003a39c  mov     ecx, [rbp+arg_8]
0x18003a39f  lea     eax, [rbx+1]
0x18003a3a2  sub     ecx, [rbp+Data]
0x18003a3a5  cmp     ecx, 0E0h
0x18003a3ab  cmovb   ebx, eax
0x18003a3ae  mov     rcx, [rbp+hKey]; hKey
0x18003a3b2  test    rcx, rcx
0x18003a3b5  jz      short loc_18003A3BD
0x18003a3b7  call    cs:__imp_RegCloseKey
0x18003a3bd  mov     eax, ebx
0x18003a3bf  add     rsp, 38h
0x18003a3c3  pop     rbx
0x18003a3c4  pop     rbp
0x18003a3c5  retn
```
