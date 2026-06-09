# WsCreateApiStructures

- ea: `0x180006c3c`
- end: `0x180006c98`
- name: `WsCreateApiStructures`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800065c0`

## callees

- `0x180006c3c`
- `0x1800079c4`
- `0x180007c80`
- `0x180008274`
- `0x180008b04`
- `0x18002eb48`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180006c7c`
- `ntdll!RtlInitUnicodeString` at `0x180006c7c`

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
0x180006c3c  sub     rsp, 28h
0x180006c40  call    WsCreateConfigInfoObject
0x180006c45  test    eax, eax
0x180006c47  js      short loc_180006C5B
0x180006c49  call    WsCreateMessageSendObject
0x180006c4e  test    eax, eax
0x180006c50  js      short loc_180006C5B
0x180006c52  call    WsCreateNetApiObject
0x180006c57  test    eax, eax
0x180006c59  jns     short loc_180006C66
0x180006c5b  mov     ecx, eax; Status
0x180006c5d  call    NetpNtStatusToApiStatus
0x180006c62  test    eax, eax
0x180006c64  jnz     short loc_180006C93
0x180006c66  bts     cs:WsInitState, 1Ch
0x180006c6e  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x180006c75  lea     rcx, RedirectorDeviceName; DestinationString
0x180006c7c  call    cs:__imp_RtlInitUnicodeString
0x180006c82  call    WsInitializeUsersObject
0x180006c87  test    eax, eax
0x180006c89  jnz     short loc_180006C93
0x180006c8b  bts     cs:WsInitState, 1Dh
0x180006c93  add     rsp, 28h
0x180006c97  retn
```
