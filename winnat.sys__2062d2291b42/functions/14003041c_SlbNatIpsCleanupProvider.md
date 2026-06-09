# SlbNatIpsCleanupProvider

- ea: `0x14003041c`
- end: `0x14003048e`
- name: `SlbNatIpsCleanupProvider`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140030f64`
- `0x140031008`

## callees

- `0x14000caa0`
- `0x14003041c`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140030444`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140030444`
- `ntoskrnl!IoFreeWorkItem` at `0x140030471`
- `ntoskrnl!IoFreeWorkItem` at `0x140030471`

## pseudocode

```c
void __fastcall SlbNatIpsCleanupProvider(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8

  if ( BYTE2(SlbNatIpsIpv4Provider) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( !*((_QWORD *)&SlbNatIpsIpv4Provider + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1));
  *((_QWORD *)&SlbNatIpsIpv4Provider + 1) = 0;
  if ( !*((_QWORD *)&xmmword_140027A40 + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
  IoFreeWorkItem(*((PIO_WORKITEM *)&xmmword_140027A40 + 1));
  *((_QWORD *)&xmmword_140027A40 + 1) = 0;
}

```

## disassembly

```asm
0x14003041c  sub     rsp, 28h
0x140030420  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x140030427  jz      short loc_14003042E
0x140030429  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003042e  cmp     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x140030436  jnz     short loc_14003043D
0x140030438  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003043d  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x140030444  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14003044b  nop     dword ptr [rax+rax+00h]
0x140030450  cmp     qword ptr cs:xmmword_140027A40+8, 0
0x140030458  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x140030463  jnz     short loc_14003046A
0x140030465  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003046a  mov     rcx, qword ptr cs:xmmword_140027A40+8; IoWorkItem
0x140030471  call    cs:__imp_IoFreeWorkItem
0x140030478  nop     dword ptr [rax+rax+00h]
0x14003047d  mov     qword ptr cs:xmmword_140027A40+8, 0
0x140030488  add     rsp, 28h
0x14003048c  retn
```
