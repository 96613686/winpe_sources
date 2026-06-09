# WcTelemetryAndTracingCleanup

- ea: `0x14001b088`
- end: `0x14001b0b6`
- name: `WcTelemetryAndTracingCleanup`
- size: `46`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140022270`
- `0x1400351b4`

## callees

- `0x14001b794`
- `0x140022f00`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x14001b09f`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14001b09f`

## pseudocode

```c
__int64 WcTelemetryAndTracingCleanup()
{
  TlgUnregisterAggregateProvider();
  imp_WppRecorderLogDelete(wil_details_featureDescriptors_a, WcVerboseRecorder);
  return WppCleanupKm();
}

```

## disassembly

```asm
0x14001b088  sub     rsp, 28h
0x14001b08c  call    TlgUnregisterAggregateProvider
0x14001b091  mov     rdx, cs:_WcVerboseRecorder
0x14001b098  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001b09f  call    cs:__imp_imp_WppRecorderLogDelete
0x14001b0a6  nop     dword ptr [rax+rax+00h]
0x14001b0ab  call    WppCleanupKm
0x14001b0b0  add     rsp, 28h
0x14001b0b4  retn
```
