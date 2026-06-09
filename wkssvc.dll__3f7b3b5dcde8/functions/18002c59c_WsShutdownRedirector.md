# WsShutdownRedirector

- ea: `0x18002c59c`
- end: `0x18002c72b`
- name: `WsShutdownRedirector`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800068d0`
- `0x18002db4c`

## callees

- `0x180006428`
- `0x1800088a0`
- `0x180010e24`
- `0x18001e420`
- `0x18001ed46`
- `0x18002c224`
- `0x18002c3b8`
- `0x18002c59c`

## import_xrefs

- `ntdll!NtClose` at `0x18002c623`
- `ntdll!NtClose` at `0x18002c6f2`
- `ntdll!NtClose` at `0x18002c623`
- `ntdll!NtClose` at `0x18002c6f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c6d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c6d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6e0`

## string_xrefs

- `0x18002c69b`: `System\CurrentControlSet\Services\MRxSmb`

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
  _WORD v6[2]; // [rsp+80h] [rbp-19h] BYREF
  int v7; // [rsp+84h] [rbp-15h]

  v5 = 0;
  memset(v4, 0, sizeof(v4));
  memset_0(v6, 0, 0x60u);
  WsInformVirtualDiskHandlers();
  result = WsCSCWantToStopRedir();
  if ( (_DWORD)result )
    return result;
  DWORD1(v4[0]) = 6;
  v1 = WsRedirFsControl(WsRedirDeviceHandle, 0x140194u, v4, 0x24u, 0, 0);
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
    WsDgReceiverIoControl(WsDgReceiverDeviceHandle, 0x13000Bu, v6, 0x60u, 0, 0);
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
0x18002c59c  mov     [rsp-8+arg_0], rbx
0x18002c5a1  push    rbp
0x18002c5a2  lea     rbp, [rsp-57h]
0x18002c5a7  sub     rsp, 0F0h
0x18002c5ae  mov     rax, cs:__security_cookie
0x18002c5b5  xor     rax, rsp
0x18002c5b8  mov     [rbp+57h+var_10], rax
0x18002c5bc  xor     eax, eax
0x18002c5be  lea     rcx, [rbp+57h+var_70]; void *
0x18002c5c2  xorps   xmm0, xmm0
0x18002c5c5  mov     [rbp+57h+var_80], eax
0x18002c5c8  xor     edx, edx; Val
0x18002c5ca  movups  [rbp+57h+var_A0], xmm0
0x18002c5ce  lea     r8d, [rax+60h]; Size
0x18002c5d2  movups  [rbp+57h+var_90], xmm0
0x18002c5d6  call    memset_0
0x18002c5db  call    WsInformVirtualDiskHandlers
0x18002c5e0  call    WsCSCWantToStopRedir
0x18002c5e5  test    eax, eax
0x18002c5e7  jnz     loc_18002C70E
0x18002c5ed  mov     rcx, cs:WsRedirDeviceHandle
0x18002c5f4  lea     r9d, [rax+24h]
0x18002c5f8  mov     [rsp+0F0h+cbData], eax
0x18002c5fc  lea     r8, [rbp+57h+var_A0]
0x18002c600  mov     edx, 140194h
0x18002c605  mov     [rsp+0F0h+phkResult], 0
0x18002c60e  mov     dword ptr [rbp+57h+var_A0+4], 6
0x18002c615  call    WsRedirFsControl
0x18002c61a  mov     rcx, cs:WsRedirDeviceHandle; Handle
0x18002c621  mov     ebx, eax
0x18002c623  call    cs:__imp_NtClose
0x18002c629  mov     cs:WsRedirDeviceHandle, 0
0x18002c634  cmp     ebx, 702h
0x18002c63a  jz      short loc_18002C67A
0x18002c63c  mov     rcx, cs:WsDgReceiverDeviceHandle
0x18002c643  test    rcx, rcx
0x18002c646  jz      loc_18002C703
0x18002c64c  mov     [rsp+0F0h+cbData], 0
0x18002c654  lea     r8, [rbp+57h+var_70]
0x18002c658  mov     r9d, 60h ; '`'
0x18002c65e  mov     [rsp+0F0h+phkResult], 0
0x18002c667  mov     edx, 13000Bh
0x18002c66c  mov     [rbp+57h+var_6C], 6
0x18002c673  call    WsDgReceiverIoControl
0x18002c678  jmp     short loc_18002C6E6
0x18002c67a  lea     rax, [rbp+57h+hKey]
0x18002c67e  mov     [rbp+57h+hKey], 0
0x18002c686  mov     r9d, 0F003Fh; samDesired
0x18002c68c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002c691  xor     r8d, r8d; ulOptions
0x18002c694  mov     dword ptr [rbp+57h+Data], 0
0x18002c69b  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\MR"...
0x18002c6a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c6a9  call    cs:__imp_RegOpenKeyExW
0x18002c6af  test    eax, eax
0x18002c6b1  jnz     short loc_18002C6E6
0x18002c6b3  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c6b7  lea     r9d, [rax+4]; dwType
0x18002c6bb  mov     dword ptr [rbp+57h+Data], eax
0x18002c6be  lea     rdx, aLastloadstatus; "LastLoadStatus"
0x18002c6c5  lea     rax, [rbp+57h+Data]
0x18002c6c9  mov     [rsp+0F0h+cbData], r9d; cbData
0x18002c6ce  xor     r8d, r8d; Reserved
0x18002c6d1  mov     [rsp+0F0h+phkResult], rax; lpData
0x18002c6d6  call    cs:__imp_RegSetValueExW
0x18002c6dc  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c6e0  call    cs:__imp_RegCloseKey
0x18002c6e6  mov     rcx, cs:WsDgReceiverDeviceHandle; Handle
0x18002c6ed  test    rcx, rcx
0x18002c6f0  jz      short loc_18002C703
0x18002c6f2  call    cs:__imp_NtClose
0x18002c6f8  mov     cs:WsDgReceiverDeviceHandle, 0
0x18002c703  test    ebx, ebx
0x18002c705  jz      short loc_18002C70C
0x18002c707  call    WsCSCReportStartRedir
0x18002c70c  mov     eax, ebx
0x18002c70e  mov     rcx, [rbp+57h+var_10]
0x18002c712  xor     rcx, rsp; StackCookie
0x18002c715  call    __security_check_cookie
0x18002c71a  mov     rbx, [rsp+0F0h+arg_0]
0x18002c722  add     rsp, 0F0h
0x18002c729  pop     rbp
0x18002c72a  retn
```
