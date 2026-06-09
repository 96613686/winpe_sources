# RefreshConfig(void)

- ea: `0x180030e70`
- end: `0x180030fe6`
- name: `?RefreshConfig@@YAJXZ`
- size: `374`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180039100`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180030e70`
- `0x18004a58c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030eb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fd0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030fb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030fb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f9c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030f12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030f12`

## string_xrefs

- `0x180030e9a`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x180030f4d`: `ReadConfig: '%s'=0x%08X (%d)\n`

## pseudocode

```c
__int64 RefreshConfig(void)
{
  LSTATUS v0; // eax
  int refreshed; // ebx
  int v2; // ecx
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+28h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+30h] BYREF

  pcbData = 0;
  pdwType = 0;
  Data = 0;
  hkey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 0, 0x2001Fu, &hkey);
  refreshed = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      refreshed = (unsigned __int16)v0 | 0x80070000;
    goto LABEL_14;
  }
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"RefreshSettingsFlags", 0xFFFFu, &pdwType, &Data, &pcbData) || pdwType != 4 )
  {
LABEL_13:
    refreshed = 0;
    goto LABEL_14;
  }
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"RefreshSettingsFlags", Data, 2);
  if ( !Data
    || (refreshed = RefreshRegValues(v2), refreshed >= 0)
    && (!Data
     || (Data = 0,
         refreshed = RegSetValueExW(hkey, L"RefreshSettingsFlags", 0, 4u, (const BYTE *)&Data, 4u),
         refreshed >= 0)) )
  {
    RegDeleteValueW(hkey, L"RefreshSettingsFlags");
    goto LABEL_13;
  }
LABEL_14:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x180030e70  push    rbp
0x180030e72  push    rbx
0x180030e73  mov     rbp, rsp
0x180030e76  sub     rsp, 48h
0x180030e7a  lea     rax, [rbp+hkey]
0x180030e7e  mov     [rbp+arg_8], 0
0x180030e85  mov     r9d, 2001Fh; samDesired
0x180030e8b  mov     [rsp+48h+phkResult], rax; phkResult
0x180030e90  xor     r8d, r8d; ulOptions
0x180030e93  mov     [rbp+pdwType], 0
0x180030e9a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180030ea1  mov     [rbp+Data], 0
0x180030ea8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030eaf  mov     [rbp+hkey], 0
0x180030eb7  call    cs:__imp_RegOpenKeyExW
0x180030ebe  nop     dword ptr [rax+rax+00h]
0x180030ec3  mov     ebx, eax
0x180030ec5  test    eax, eax
0x180030ec7  jz      short loc_180030EDD
0x180030ec9  jle     loc_180030FC7
0x180030ecf  movzx   ebx, ax
0x180030ed2  or      ebx, 80070000h
0x180030ed8  jmp     loc_180030FC7
0x180030edd  mov     rcx, [rbp+hkey]; hkey
0x180030ee1  lea     rax, [rbp+arg_8]
0x180030ee5  mov     [rsp+48h+pcbData], rax; pcbData
0x180030eea  lea     r8, aRefreshsetting; "RefreshSettingsFlags"
0x180030ef1  lea     rax, [rbp+Data]
0x180030ef5  mov     [rbp+arg_8], 4
0x180030efc  mov     [rsp+48h+pvData], rax; pvData
0x180030f01  mov     r9d, 0FFFFh; dwFlags
0x180030f07  lea     rax, [rbp+pdwType]
0x180030f0b  xor     edx, edx; lpSubKey
0x180030f0d  mov     [rsp+48h+phkResult], rax; pdwType
0x180030f12  call    cs:__imp_RegGetValueW
0x180030f19  nop     dword ptr [rax+rax+00h]
0x180030f1e  test    eax, eax
0x180030f20  jnz     loc_180030FC5
0x180030f26  cmp     [rbp+pdwType], 4
0x180030f2a  jnz     loc_180030FC5
0x180030f30  lea     ecx, [rax+70h]
0x180030f33  call    FileLogAllowEntry
0x180030f38  test    al, al
0x180030f3a  jz      short loc_180030F59
0x180030f3c  mov     r8d, [rbp+Data]
0x180030f40  lea     rdx, aRefreshsetting; "RefreshSettingsFlags"
0x180030f47  mov     r9d, 2
0x180030f4d  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180030f54  call    FileLogAdd
0x180030f59  cmp     [rbp+Data], 0
0x180030f5d  jz      short loc_180030FAE
0x180030f5f  call    ?RefreshRegValues@@YAJH@Z; RefreshRegValues(int)
0x180030f64  mov     ebx, eax
0x180030f66  test    eax, eax
0x180030f68  js      short loc_180030FC7
0x180030f6a  cmp     [rbp+Data], 0
0x180030f6e  jz      short loc_180030FAE
0x180030f70  mov     rcx, [rbp+hkey]; hKey
0x180030f74  lea     rax, [rbp+Data]
0x180030f78  mov     dword ptr [rsp+48h+pvData], 4; cbData
0x180030f80  lea     rdx, aRefreshsetting; "RefreshSettingsFlags"
0x180030f87  mov     r9d, 4; dwType
0x180030f8d  mov     [rsp+48h+phkResult], rax; lpData
0x180030f92  xor     r8d, r8d; Reserved
0x180030f95  mov     [rbp+Data], 0
0x180030f9c  call    cs:__imp_RegSetValueExW
0x180030fa3  nop     dword ptr [rax+rax+00h]
0x180030fa8  mov     ebx, eax
0x180030faa  test    eax, eax
0x180030fac  js      short loc_180030FC7
0x180030fae  mov     rcx, [rbp+hkey]; hKey
0x180030fb2  lea     rdx, aRefreshsetting; "RefreshSettingsFlags"
0x180030fb9  call    cs:__imp_RegDeleteValueW
0x180030fc0  nop     dword ptr [rax+rax+00h]
0x180030fc5  xor     ebx, ebx
0x180030fc7  mov     rcx, [rbp+hkey]; hKey
0x180030fcb  test    rcx, rcx
0x180030fce  jz      short loc_180030FDC
0x180030fd0  call    cs:__imp_RegCloseKey
0x180030fd7  nop     dword ptr [rax+rax+00h]
0x180030fdc  mov     eax, ebx
0x180030fde  add     rsp, 48h
0x180030fe2  pop     rbx
0x180030fe3  pop     rbp
0x180030fe4  retn
```
