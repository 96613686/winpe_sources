# WsShutdownRedirector

- ea: `0x18002ee64`
- end: `0x18002f012`
- name: `WsShutdownRedirector`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006e0c`
- `0x180030544`

## callees

- `0x1800068d8`
- `0x180008f50`
- `0x180011ccc`
- `0x18001fbd0`
- `0x1800204f6`
- `0x18002ea78`
- `0x18002ec48`
- `0x18002ee64`

## import_xrefs

- `ntdll!NtClose` at `0x18002eeeb`
- `ntdll!NtClose` at `0x18002efd2`
- `ntdll!NtClose` at `0x18002eeeb`
- `ntdll!NtClose` at `0x18002efd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002efaa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002efaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002efba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002efba`

## string_xrefs

- `0x18002ef69`: `System\CurrentControlSet\Services\MRxSmb`

## pseudocode

```c
__int64 WsShutdownRedirector()
{
  __int64 result; // rax
  unsigned int v1; // ebx
  BYTE Data[8]; // [rsp+40h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-51h] BYREF
  _OWORD v4[2]; // [rsp+50h] [rbp-49h] BYREF
  int v5; // [rsp+70h] [rbp-29h]
  _BYTE v6[4]; // [rsp+80h] [rbp-19h] BYREF
  int v7; // [rsp+84h] [rbp-15h]

  v5 = 0;
  memset(v4, 0, sizeof(v4));
  memset_0(v6, 0, 0x60u);
  WsInformVirtualDiskHandlers();
  result = WsCSCWantToStopRedir();
  if ( (_DWORD)result )
    return result;
  DWORD1(v4[0]) = 6;
  v1 = WsRedirFsControl(WsRedirDeviceHandle, 1311124, v4, 36, 0, 0);
  NtClose(WsRedirDeviceHandle);
  WsRedirDeviceHandle = 0;
  if ( v1 == 1794 )
  {
    hKey = 0;
    *(_DWORD *)Data = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\MRxSmb", 0, 0xF003Fu, &hKey) )
    {
      *(_DWORD *)Data = 0;
      RegSetValueExW(hKey, L"LastLoadStatus", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
    goto LABEL_7;
  }
  if ( WsDgReceiverDeviceHandle )
  {
    v7 = 6;
    WsDgReceiverIoControl(WsDgReceiverDeviceHandle, 1245195, v6, 96, 0, 0);
LABEL_7:
    if ( WsDgReceiverDeviceHandle )
    {
      NtClose(WsDgReceiverDeviceHandle);
      WsDgReceiverDeviceHandle = 0;
    }
  }
  if ( v1 )
    WsCSCReportStartRedir();
  return v1;
}

```

## disassembly

```asm
0x18002ee64  mov     [rsp-8+arg_0], rbx
0x18002ee69  push    rbp
0x18002ee6a  lea     rbp, [rsp-57h]
0x18002ee6f  sub     rsp, 0F0h
0x18002ee76  mov     rax, cs:__security_cookie
0x18002ee7d  xor     rax, rsp
0x18002ee80  mov     [rbp+57h+var_10], rax
0x18002ee84  xor     eax, eax
0x18002ee86  lea     rcx, [rbp+57h+var_70]; void *
0x18002ee8a  xorps   xmm0, xmm0
0x18002ee8d  mov     [rbp+57h+var_80], eax
0x18002ee90  xor     edx, edx; Val
0x18002ee92  movups  [rbp+57h+var_A0], xmm0
0x18002ee96  lea     r8d, [rax+60h]; Size
0x18002ee9a  movups  [rbp+57h+var_90], xmm0
0x18002ee9e  call    memset_0
0x18002eea3  call    WsInformVirtualDiskHandlers
0x18002eea8  call    WsCSCWantToStopRedir
0x18002eead  test    eax, eax
0x18002eeaf  jnz     loc_18002EFF4
0x18002eeb5  mov     rcx, cs:WsRedirDeviceHandle
0x18002eebc  lea     r9d, [rax+24h]
0x18002eec0  mov     [rsp+0F0h+cbData], eax
0x18002eec4  lea     r8, [rbp+57h+var_A0]
0x18002eec8  mov     edx, 140194h
0x18002eecd  mov     [rsp+0F0h+phkResult], 0
0x18002eed6  mov     dword ptr [rbp+57h+var_A0+4], 6
0x18002eedd  call    WsRedirFsControl
0x18002eee2  mov     rcx, cs:WsRedirDeviceHandle; Handle
0x18002eee9  mov     ebx, eax
0x18002eeeb  call    cs:__imp_NtClose
0x18002eef2  nop     dword ptr [rax+rax+00h]
0x18002eef7  mov     cs:WsRedirDeviceHandle, 0
0x18002ef02  cmp     ebx, 702h
0x18002ef08  jz      short loc_18002EF48
0x18002ef0a  mov     rcx, cs:WsDgReceiverDeviceHandle
0x18002ef11  test    rcx, rcx
0x18002ef14  jz      loc_18002EFE9
0x18002ef1a  mov     [rsp+0F0h+cbData], 0
0x18002ef22  lea     r8, [rbp+57h+var_70]
0x18002ef26  mov     r9d, 60h ; '`'
0x18002ef2c  mov     [rsp+0F0h+phkResult], 0
0x18002ef35  mov     edx, 13000Bh
0x18002ef3a  mov     [rbp+57h+var_6C], 6
0x18002ef41  call    WsDgReceiverIoControl
0x18002ef46  jmp     short loc_18002EFC6
0x18002ef48  lea     rax, [rbp+57h+hKey]
0x18002ef4c  mov     [rbp+57h+hKey], 0
0x18002ef54  mov     r9d, 0F003Fh; samDesired
0x18002ef5a  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002ef5f  xor     r8d, r8d; ulOptions
0x18002ef62  mov     dword ptr [rbp+57h+Data], 0
0x18002ef69  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\MR"...
0x18002ef70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ef77  call    cs:__imp_RegOpenKeyExW
0x18002ef7e  nop     dword ptr [rax+rax+00h]
0x18002ef83  test    eax, eax
0x18002ef85  jnz     short loc_18002EFC6
0x18002ef87  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ef8b  lea     r9d, [rax+4]; dwType
0x18002ef8f  mov     dword ptr [rbp+57h+Data], eax
0x18002ef92  lea     rdx, aLastloadstatus; "LastLoadStatus"
0x18002ef99  lea     rax, [rbp+57h+Data]
0x18002ef9d  mov     [rsp+0F0h+cbData], r9d; cbData
0x18002efa2  xor     r8d, r8d; Reserved
0x18002efa5  mov     [rsp+0F0h+phkResult], rax; lpData
0x18002efaa  call    cs:__imp_RegSetValueExW
0x18002efb1  nop     dword ptr [rax+rax+00h]
0x18002efb6  mov     rcx, [rbp+57h+hKey]; hKey
0x18002efba  call    cs:__imp_RegCloseKey
0x18002efc1  nop     dword ptr [rax+rax+00h]
0x18002efc6  mov     rcx, cs:WsDgReceiverDeviceHandle; Handle
0x18002efcd  test    rcx, rcx
0x18002efd0  jz      short loc_18002EFE9
0x18002efd2  call    cs:__imp_NtClose
0x18002efd9  nop     dword ptr [rax+rax+00h]
0x18002efde  mov     cs:WsDgReceiverDeviceHandle, 0
0x18002efe9  test    ebx, ebx
0x18002efeb  jz      short loc_18002EFF2
0x18002efed  call    WsCSCReportStartRedir
0x18002eff2  mov     eax, ebx
0x18002eff4  mov     rcx, [rbp+57h+var_10]
0x18002eff8  xor     rcx, rsp; StackCookie
0x18002effb  call    __security_check_cookie
0x18002f000  mov     rbx, [rsp+0F0h+arg_0]
0x18002f008  add     rsp, 0F0h
0x18002f00f  pop     rbp
0x18002f010  retn
```
