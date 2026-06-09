# TdxShutdownPnpEventClientModule

- ea: `0x1400156d4`
- end: `0x140015704`
- name: `TdxShutdownPnpEventClientModule`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014184`
- `0x1400145a0`

## import_xrefs

- `NETIO!NmrDeregisterClient` at `0x1400156df`
- `NETIO!NmrDeregisterClient` at `0x1400156df`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400156f2`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400156f2`

## pseudocode

```c
NTSTATUS TdxShutdownPnpEventClientModule()
{
  NmrDeregisterClient(WPP_MAIN_CB.DeviceExtension);
  return NmrWaitForClientDeregisterComplete(WPP_MAIN_CB.DeviceExtension);
}

```

## disassembly

```asm
0x1400156d4  sub     rsp, 28h
0x1400156d8  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; NmrClientHandle
0x1400156df  call    cs:__imp_NmrDeregisterClient
0x1400156e6  nop     dword ptr [rax+rax+00h]
0x1400156eb  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; NmrClientHandle
0x1400156f2  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400156f9  nop     dword ptr [rax+rax+00h]
0x1400156fe  add     rsp, 28h
0x140015702  retn
```
