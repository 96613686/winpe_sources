# WsGetMessageSendRegValue

- ea: `0x180010f30`
- end: `0x180010fca`
- name: `WsGetMessageSendRegValue`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180008b04`

## callees

- `0x180010f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010fbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010fbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010fa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010fa0`

## string_xrefs

- `0x180010f5a`: `System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

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
0x180010f30  push    rbp
0x180010f32  mov     rbp, rsp
0x180010f35  sub     rsp, 30h
0x180010f39  lea     rax, [rbp+hKey]
0x180010f3d  mov     [rbp+Data], 0
0x180010f44  mov     r9d, 20019h; samDesired
0x180010f4a  mov     [rsp+30h+phkResult], rax; phkResult
0x180010f4f  xor     r8d, r8d; ulOptions
0x180010f52  mov     [rbp+hKey], 0
0x180010f5a  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\La"...
0x180010f61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010f68  call    cs:__imp_RegOpenKeyExW
0x180010f6e  test    eax, eax
0x180010f70  jnz     short loc_180010FC1
0x180010f72  mov     rcx, [rbp+hKey]; hKey
0x180010f76  lea     r9, [rbp+Type]; lpType
0x180010f7a  mov     [rbp+Type], eax
0x180010f7d  lea     rdx, aLimitmessagese; "limitmessagesend"
0x180010f84  lea     rax, [rbp+cbData]
0x180010f88  mov     [rbp+cbData], 4
0x180010f8f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180010f94  xor     r8d, r8d; lpReserved
0x180010f97  lea     rax, [rbp+Data]
0x180010f9b  mov     [rsp+30h+phkResult], rax; lpData
0x180010fa0  call    cs:__imp_RegQueryValueExW
0x180010fa6  test    eax, eax
0x180010fa8  jnz     short loc_180010FB0
0x180010faa  cmp     [rbp+Type], 4
0x180010fae  jz      short loc_180010FB7
0x180010fb0  mov     [rbp+Data], 0
0x180010fb7  mov     rcx, [rbp+hKey]; hKey
0x180010fbb  call    cs:__imp_RegCloseKey
0x180010fc1  mov     eax, [rbp+Data]
0x180010fc4  add     rsp, 30h
0x180010fc8  pop     rbp
0x180010fc9  retn
```
