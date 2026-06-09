# WsCreateApiStructures

- ea: `0x180007224`
- end: `0x180007287`
- name: `WsCreateApiStructures`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006a98`

## callees

- `0x180007224`
- `0x180007ecc`
- `0x1800081b0`
- `0x1800087fc`
- `0x1800091d4`
- `0x1800316e8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180007264`
- `ntdll!RtlInitUnicodeString` at `0x180007264`

## pseudocode

```c
__int64 WsCreateApiStructures()
{
  NTSTATUS ConfigInfoObject; // eax
  __int64 result; // rax

  ConfigInfoObject = WsCreateConfigInfoObject();
  if ( ConfigInfoObject >= 0
    && (ConfigInfoObject = WsCreateMessageSendObject(), ConfigInfoObject >= 0)
    && (ConfigInfoObject = WsCreateNetApiObject(), ConfigInfoObject >= 0)
    || (result = NetpNtStatusToApiStatus(ConfigInfoObject), !(_DWORD)result) )
  {
    WsInitState |= 0x10000000u;
    RtlInitUnicodeString(&RedirectorDeviceName, L"\\Device\\LanmanRedirector");
    result = WsInitializeUsersObject();
    if ( !(_DWORD)result )
      WsInitState |= 0x20000000u;
  }
  return result;
}

```

## disassembly

```asm
0x180007224  sub     rsp, 28h
0x180007228  call    WsCreateConfigInfoObject
0x18000722d  test    eax, eax
0x18000722f  js      short loc_180007243
0x180007231  call    WsCreateMessageSendObject
0x180007236  test    eax, eax
0x180007238  js      short loc_180007243
0x18000723a  call    WsCreateNetApiObject
0x18000723f  test    eax, eax
0x180007241  jns     short loc_18000724E
0x180007243  mov     ecx, eax; Status
0x180007245  call    NetpNtStatusToApiStatus
0x18000724a  test    eax, eax
0x18000724c  jnz     short loc_180007281
0x18000724e  bts     cs:WsInitState, 1Ch
0x180007256  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x18000725d  lea     rcx, RedirectorDeviceName; DestinationString
0x180007264  call    cs:__imp_RtlInitUnicodeString
0x18000726b  nop     dword ptr [rax+rax+00h]
0x180007270  call    WsInitializeUsersObject
0x180007275  test    eax, eax
0x180007277  jnz     short loc_180007281
0x180007279  bts     cs:WsInitState, 1Dh
0x180007281  add     rsp, 28h
0x180007285  retn
```
