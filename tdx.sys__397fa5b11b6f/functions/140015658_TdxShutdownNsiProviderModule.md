# TdxShutdownNsiProviderModule

- ea: `0x140015658`
- end: `0x140015688`
- name: `TdxShutdownNsiProviderModule`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014184`
- `0x1400145a0`

## import_xrefs

- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140015676`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140015676`
- `NETIO!NmrDeregisterProvider` at `0x140015663`
- `NETIO!NmrDeregisterProvider` at `0x140015663`

## pseudocode

```c
NTSTATUS TdxShutdownNsiProviderModule()
{
  NmrDeregisterProvider(WPP_MAIN_CB.Queue.ListEntry.Flink);
  return NmrWaitForProviderDeregisterComplete(WPP_MAIN_CB.Queue.ListEntry.Flink);
}

```

## disassembly

```asm
0x140015658  sub     rsp, 28h
0x14001565c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; NmrProviderHandle
0x140015663  call    cs:__imp_NmrDeregisterProvider
0x14001566a  nop     dword ptr [rax+rax+00h]
0x14001566f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; NmrProviderHandle
0x140015676  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14001567d  nop     dword ptr [rax+rax+00h]
0x140015682  add     rsp, 28h
0x140015686  retn
```
