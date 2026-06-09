# SlbNatCleanup

- ea: `0x140031088`
- end: `0x14003110b`
- name: `SlbNatCleanup`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000daf0`

## callees

- `0x14000caa0`
- `0x140018df8`
- `0x140031088`
- `0x1400343cc`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400310f4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400310f4`
- `ntoskrnl!IoFreeWorkItem` at `0x1400310c6`
- `ntoskrnl!IoFreeWorkItem` at `0x1400310c6`

## pseudocode

```c
__int64 __fastcall SlbNatCleanup(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 result; // rax

  if ( SlbNatGlobalState )
  {
    if ( qword_140027338 != &qword_140027338 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
    if ( qword_140027358 != &qword_140027358 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
    IoFreeWorkItem(IoWorkItem);
    if ( !qword_1400273D8 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
    WinNatLibCleanupState(qword_1400273D8);
    ExDeleteResourceLite(&Resource);
    return SlbNatIpsCleanupDataPathState();
  }
  return result;
}

```

## disassembly

```asm
0x140031088  sub     rsp, 28h
0x14003108c  cmp     cs:SlbNatGlobalState, 0
0x140031093  jz      short loc_140031105
0x140031095  lea     rax, qword_140027338
0x14003109c  cmp     cs:qword_140027338, rax
0x1400310a3  jz      short loc_1400310AA
0x1400310a5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400310aa  lea     rax, qword_140027358
0x1400310b1  cmp     cs:qword_140027358, rax
0x1400310b8  jz      short loc_1400310BF
0x1400310ba  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400310bf  mov     rcx, cs:IoWorkItem; IoWorkItem
0x1400310c6  call    cs:__imp_IoFreeWorkItem
0x1400310cd  nop     dword ptr [rax+rax+00h]
0x1400310d2  cmp     cs:qword_1400273D8, 0
0x1400310da  jnz     short loc_1400310E1
0x1400310dc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400310e1  mov     rcx, cs:qword_1400273D8; P
0x1400310e8  call    WinNatLibCleanupState
0x1400310ed  lea     rcx, Resource; Resource
0x1400310f4  call    cs:__imp_ExDeleteResourceLite
0x1400310fb  nop     dword ptr [rax+rax+00h]
0x140031100  call    SlbNatIpsCleanupDataPathState
0x140031105  add     rsp, 28h
0x140031109  retn
```
