# SlbNatCleanup

- ea: `0x14002ff58`
- end: `0x14002ffdb`
- name: `SlbNatCleanup`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000db20`

## callees

- `0x14000caa0`
- `0x140018918`
- `0x14002ff58`
- `0x14003329c`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14002ff96`
- `ntoskrnl!IoFreeWorkItem` at `0x14002ff96`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002ffc4`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002ffc4`

## pseudocode

```c
__int64 __fastcall SlbNatCleanup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 result; // rax

  if ( SlbNatGlobalState )
  {
    if ( qword_140026338 != &qword_140026338 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
    if ( qword_140026358 != &qword_140026358 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
    IoFreeWorkItem(IoWorkItem);
    if ( !qword_1400263D8 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
    WinNatLibCleanupState(qword_1400263D8);
    ExDeleteResourceLite(&Resource);
    return SlbNatIpsCleanupDataPathState();
  }
  return result;
}

```

## disassembly

```asm
0x14002ff58  sub     rsp, 28h
0x14002ff5c  cmp     cs:SlbNatGlobalState, 0
0x14002ff63  jz      short loc_14002FFD5
0x14002ff65  lea     rax, qword_140026338
0x14002ff6c  cmp     cs:qword_140026338, rax
0x14002ff73  jz      short loc_14002FF7A
0x14002ff75  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ff7a  lea     rax, qword_140026358
0x14002ff81  cmp     cs:qword_140026358, rax
0x14002ff88  jz      short loc_14002FF8F
0x14002ff8a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ff8f  mov     rcx, cs:IoWorkItem; IoWorkItem
0x14002ff96  call    cs:__imp_IoFreeWorkItem
0x14002ff9d  nop     dword ptr [rax+rax+00h]
0x14002ffa2  cmp     cs:qword_1400263D8, 0
0x14002ffaa  jnz     short loc_14002FFB1
0x14002ffac  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ffb1  mov     rcx, cs:qword_1400263D8; P
0x14002ffb8  call    WinNatLibCleanupState
0x14002ffbd  lea     rcx, Resource; Resource
0x14002ffc4  call    cs:__imp_ExDeleteResourceLite
0x14002ffcb  nop     dword ptr [rax+rax+00h]
0x14002ffd0  call    SlbNatIpsCleanupDataPathState
0x14002ffd5  add     rsp, 28h
0x14002ffd9  retn
```
