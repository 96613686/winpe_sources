# WsGetMessageSendRegValue

- ea: `0x180011e10`
- end: `0x180011ebd`
- name: `WsGetMessageSendRegValue`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800091d4`

## callees

- `0x180011e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ea7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011e86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011e86`

## string_xrefs

- `0x180011e3a`: `System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

## pseudocode

```c
__int64 WsGetMessageSendRegValue()
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\LanmanWorkstation\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"limitmessagesend", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x180011e10  push    rbp
0x180011e12  mov     rbp, rsp
0x180011e15  sub     rsp, 30h
0x180011e19  lea     rax, [rbp+hKey]
0x180011e1d  mov     [rbp+Data], 0
0x180011e24  mov     r9d, 20019h; samDesired
0x180011e2a  mov     [rsp+30h+phkResult], rax; phkResult
0x180011e2f  xor     r8d, r8d; ulOptions
0x180011e32  mov     [rbp+hKey], 0
0x180011e3a  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\La"...
0x180011e41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011e48  call    cs:__imp_RegOpenKeyExW
0x180011e4f  nop     dword ptr [rax+rax+00h]
0x180011e54  test    eax, eax
0x180011e56  jnz     short loc_180011EB3
0x180011e58  mov     rcx, [rbp+hKey]; hKey
0x180011e5c  lea     r9, [rbp+Type]; lpType
0x180011e60  mov     [rbp+Type], eax
0x180011e63  lea     rdx, aLimitmessagese; "limitmessagesend"
0x180011e6a  lea     rax, [rbp+cbData]
0x180011e6e  mov     [rbp+cbData], 4
0x180011e75  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180011e7a  xor     r8d, r8d; lpReserved
0x180011e7d  lea     rax, [rbp+Data]
0x180011e81  mov     [rsp+30h+phkResult], rax; lpData
0x180011e86  call    cs:__imp_RegQueryValueExW
0x180011e8d  nop     dword ptr [rax+rax+00h]
0x180011e92  test    eax, eax
0x180011e94  jnz     short loc_180011E9C
0x180011e96  cmp     [rbp+Type], 4
0x180011e9a  jz      short loc_180011EA3
0x180011e9c  mov     [rbp+Data], 0
0x180011ea3  mov     rcx, [rbp+hKey]; hKey
0x180011ea7  call    cs:__imp_RegCloseKey
0x180011eae  nop     dword ptr [rax+rax+00h]
0x180011eb3  mov     eax, [rbp+Data]
0x180011eb6  add     rsp, 30h
0x180011eba  pop     rbp
0x180011ebb  retn
```
