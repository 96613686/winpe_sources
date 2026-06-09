# TdxShutdownTlClientModule

- ea: `0x140017494`
- end: `0x1400174c4`
- name: `TdxShutdownTlClientModule`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014184`
- `0x1400145a0`

## import_xrefs

- `NETIO!NmrDeregisterClient` at `0x14001749f`
- `NETIO!NmrDeregisterClient` at `0x14001749f`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400174b2`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400174b2`

## pseudocode

```c
NTSTATUS TdxShutdownTlClientModule()
{
  NmrDeregisterClient(TdxTlClientHandle);
  return NmrWaitForClientDeregisterComplete(TdxTlClientHandle);
}

```

## disassembly

```asm
0x140017494  sub     rsp, 28h
0x140017498  mov     rcx, cs:TdxTlClientHandle; NmrClientHandle
0x14001749f  call    cs:__imp_NmrDeregisterClient
0x1400174a6  nop     dword ptr [rax+rax+00h]
0x1400174ab  mov     rcx, cs:TdxTlClientHandle; NmrClientHandle
0x1400174b2  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400174b9  nop     dword ptr [rax+rax+00h]
0x1400174be  add     rsp, 28h
0x1400174c2  retn
```
