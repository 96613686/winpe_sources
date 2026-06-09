# SlbNatIpsCleanupProvider

- ea: `0x14002f2f8`
- end: `0x14002f36a`
- name: `SlbNatIpsCleanupProvider`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002fe34`
- `0x14002fed8`

## callees

- `0x14000caa0`
- `0x14002f2f8`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002f320`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002f320`
- `ntoskrnl!IoFreeWorkItem` at `0x14002f34d`
- `ntoskrnl!IoFreeWorkItem` at `0x14002f34d`

## pseudocode

```c
void __fastcall SlbNatIpsCleanupProvider(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9

  if ( BYTE2(SlbNatIpsIpv4Provider) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( !*((_QWORD *)&SlbNatIpsIpv4Provider + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1));
  *((_QWORD *)&SlbNatIpsIpv4Provider + 1) = 0;
  if ( !*((_QWORD *)&xmmword_140026A40 + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
  IoFreeWorkItem(*((PIO_WORKITEM *)&xmmword_140026A40 + 1));
  *((_QWORD *)&xmmword_140026A40 + 1) = 0;
}

```

## disassembly

```asm
0x14002f2f8  sub     rsp, 28h
0x14002f2fc  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x14002f303  jz      short loc_14002F30A
0x14002f305  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f30a  cmp     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x14002f312  jnz     short loc_14002F319
0x14002f314  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f319  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14002f320  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14002f327  nop     dword ptr [rax+rax+00h]
0x14002f32c  cmp     qword ptr cs:xmmword_140026A40+8, 0
0x14002f334  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x14002f33f  jnz     short loc_14002F346
0x14002f341  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f346  mov     rcx, qword ptr cs:xmmword_140026A40+8; IoWorkItem
0x14002f34d  call    cs:__imp_IoFreeWorkItem
0x14002f354  nop     dword ptr [rax+rax+00h]
0x14002f359  mov     qword ptr cs:xmmword_140026A40+8, 0
0x14002f364  add     rsp, 28h
0x14002f368  retn
```
