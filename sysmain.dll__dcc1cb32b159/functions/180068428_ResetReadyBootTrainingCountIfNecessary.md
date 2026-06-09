# ResetReadyBootTrainingCountIfNecessary

- ea: `0x180068428`
- end: `0x1800685c0`
- name: `ResetReadyBootTrainingCountIfNecessary`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056b04`

## callees

- `0x180068428`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800685b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800685b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068574`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800685a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068574`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800685a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800684e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800684e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006848e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006852c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006848e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006852c`

## string_xrefs

- `0x180068443`: `LastTrustedInstallerBoot`
- `0x18006845b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`
- `0x1800684bc`: `System\CurrentControlSet\Services\RdyBoost\Diagnostics`
- `0x180068599`: `ReadyBootTrainingCountSinceLastServicing`
- `0x18006851a`: `LastTrustedInstallerBootCached`
- `0x18006855f`: `LastTrustedInstallerBootCached`

## pseudocode

```c
__int64 ResetReadyBootTrainingCountIfNecessary()
{
  LSTATUS ValueW; // eax
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  unsigned __int64 v3; // rax
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF
  int v7; // [rsp+88h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+28h] BYREF
  unsigned __int64 pvData; // [rsp+98h] [rbp+30h] BYREF

  *(_QWORD *)Data = 0;
  pvData = 0;
  hkey = 0;
  v7 = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
             L"LastTrustedInstallerBoot",
             0x48u,
             0,
             Data,
             &pcbData);
  v1 = ValueW;
  if ( ValueW == 2 )
  {
    v1 = 0;
    goto LABEL_12;
  }
  if ( !ValueW )
  {
    v1 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RdyBoost\\Diagnostics",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hkey,
           0);
    if ( !v1 )
    {
      pcbData = 8;
      v2 = RegGetValueW(hkey, 0, L"LastTrustedInstallerBootCached", 0x48u, 0, &pvData, &pcbData);
      v1 = v2;
      if ( v2 == 2 )
      {
        v3 = 0;
        pvData = 0;
      }
      else
      {
        if ( v2 )
          goto LABEL_12;
        v3 = pvData;
      }
      if ( *(_QWORD *)Data > v3 )
      {
        v1 = RegSetValueExW(hkey, L"LastTrustedInstallerBootCached", 0, 0xBu, Data, 8u);
        if ( !v1 )
          v1 = RegSetValueExW(hkey, L"ReadyBootTrainingCountSinceLastServicing", 0, 4u, (const BYTE *)&v7, 4u);
      }
    }
  }
LABEL_12:
  if ( hkey )
    RegCloseKey(hkey);
  return v1;
}

```

## disassembly

```asm
0x180068428  push    rbp
0x18006842a  push    rbx
0x18006842b  mov     rbp, rsp
0x18006842e  sub     rsp, 68h
0x180068432  lea     rax, [rbp+arg_0]
0x180068436  mov     qword ptr [rbp+Data], 0
0x18006843e  mov     [rsp+68h+pcbData], rax; pcbData
0x180068443  lea     r8, aLasttrustedins; "LastTrustedInstallerBoot"
0x18006844a  lea     rax, [rbp+Data]
0x18006844e  mov     [rbp+arg_18], 0
0x180068456  mov     [rsp+68h+pvData], rax; pvData
0x18006845b  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180068462  mov     r9d, 48h ; 'H'; dwFlags
0x180068468  mov     [rsp+68h+pdwType], 0; pdwType
0x180068471  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180068478  mov     [rbp+hkey], 0
0x180068480  mov     [rbp+arg_8], 0
0x180068487  mov     [rbp+arg_0], 8
0x18006848e  call    cs:__imp_RegGetValueW
0x180068494  mov     ebx, eax
0x180068496  cmp     eax, 2
0x180068499  jnz     short loc_1800684A2
0x18006849b  xor     ebx, ebx
0x18006849d  jmp     loc_1800685A8
0x1800684a2  test    eax, eax
0x1800684a4  jnz     loc_1800685A8
0x1800684aa  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800684b3  lea     rax, [rbp+hkey]
0x1800684b7  mov     [rsp+68h+phkResult], rax; phkResult
0x1800684bc  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Rd"...
0x1800684c3  mov     [rsp+68h+pcbData], 0; lpSecurityAttributes
0x1800684cc  xor     r9d, r9d; lpClass
0x1800684cf  mov     dword ptr [rsp+68h+pvData], 2001Fh; samDesired
0x1800684d7  xor     r8d, r8d; Reserved
0x1800684da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800684e1  mov     dword ptr [rsp+68h+pdwType], 0; dwOptions
0x1800684e9  call    cs:__imp_RegCreateKeyExW
0x1800684ef  mov     ebx, eax
0x1800684f1  test    eax, eax
0x1800684f3  jnz     loc_1800685A8
0x1800684f9  mov     rcx, [rbp+hkey]; hkey
0x1800684fd  lea     rax, [rbp+arg_0]
0x180068501  mov     [rsp+68h+pcbData], rax; pcbData
0x180068506  lea     r9d, [rbx+48h]; dwFlags
0x18006850a  lea     rax, [rbp+arg_18]
0x18006850e  mov     [rbp+arg_0], 8
0x180068515  mov     [rsp+68h+pvData], rax; pvData
0x18006851a  lea     r8, aLasttrustedins_0; "LastTrustedInstallerBootCached"
0x180068521  xor     edx, edx; lpSubKey
0x180068523  mov     [rsp+68h+pdwType], 0; pdwType
0x18006852c  call    cs:__imp_RegGetValueW
0x180068532  mov     ebx, eax
0x180068534  cmp     eax, 2
0x180068537  jnz     short loc_180068541
0x180068539  xor     eax, eax
0x18006853b  mov     [rbp+arg_18], rax
0x18006853f  jmp     short loc_180068549
0x180068541  test    eax, eax
0x180068543  jnz     short loc_1800685A8
0x180068545  mov     rax, [rbp+arg_18]
0x180068549  cmp     qword ptr [rbp+Data], rax
0x18006854d  jbe     short loc_1800685A8
0x18006854f  mov     rcx, [rbp+hkey]; hKey
0x180068553  lea     rax, [rbp+Data]
0x180068557  mov     dword ptr [rsp+68h+pvData], 8; cbData
0x18006855f  lea     rdx, aLasttrustedins_0; "LastTrustedInstallerBootCached"
0x180068566  mov     r9d, 0Bh; dwType
0x18006856c  mov     [rsp+68h+pdwType], rax; lpData
0x180068571  xor     r8d, r8d; Reserved
0x180068574  call    cs:__imp_RegSetValueExW
0x18006857a  mov     ebx, eax
0x18006857c  test    eax, eax
0x18006857e  jnz     short loc_1800685A8
0x180068580  mov     rcx, [rbp+hkey]; hKey
0x180068584  lea     r9d, [rax+4]; dwType
0x180068588  lea     rax, [rbp+arg_8]
0x18006858c  mov     dword ptr [rsp+68h+pvData], r9d; cbData
0x180068591  xor     r8d, r8d; Reserved
0x180068594  mov     [rsp+68h+pdwType], rax; lpData
0x180068599  lea     rdx, aReadyboottrain; "ReadyBootTrainingCountSinceLastServicin"...
0x1800685a0  call    cs:__imp_RegSetValueExW
0x1800685a6  mov     ebx, eax
0x1800685a8  mov     rcx, [rbp+hkey]; hKey
0x1800685ac  test    rcx, rcx
0x1800685af  jz      short loc_1800685B7
0x1800685b1  call    cs:__imp_RegCloseKey
0x1800685b7  mov     eax, ebx
0x1800685b9  add     rsp, 68h
0x1800685bd  pop     rbx
0x1800685be  pop     rbp
0x1800685bf  retn
```
