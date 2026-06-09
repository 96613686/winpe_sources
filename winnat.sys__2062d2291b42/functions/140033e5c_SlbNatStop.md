# SlbNatStop

- ea: `0x140033e5c`
- end: `0x140033fa1`
- name: `SlbNatStop`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000daf0`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x140014048`
- `0x1400151ec`
- `0x140031008`
- `0x140032430`
- `0x140033e5c`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140033f56`
- `ntoskrnl!IoFreeWorkItem` at `0x140033f56`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140033f8e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140033f8e`
- `ntoskrnl!KeCancelTimer` at `0x140033f72`
- `ntoskrnl!KeCancelTimer` at `0x140033f72`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033e7d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033e7d`
- `NETIO!NsiDeregisterChangeNotification` at `0x140033ea3`
- `NETIO!NsiDeregisterChangeNotification` at `0x140033ed8`
- `NETIO!NsiDeregisterChangeNotification` at `0x140033ea3`
- `NETIO!NsiDeregisterChangeNotification` at `0x140033ed8`

## pseudocode

```c
void SlbNatStop()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  PVOID v6; // rcx
  __int64 v7; // rax

  if ( SlbNatGlobalState )
  {
    byte_1400274E0 = 1;
    ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
    if ( (_QWORD)xmmword_1400273E0 )
    {
      if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2);
      *(_QWORD *)&xmmword_1400273E0 = 0;
    }
    if ( *((_QWORD *)&xmmword_1400273E0 + 1) )
    {
      if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 10) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
      *((_QWORD *)&xmmword_1400273E0 + 1) = 0;
    }
    while ( 1 )
    {
      v6 = qword_140027338;
      if ( qword_140027338 == &qword_140027338 )
        break;
      if ( *((PVOID **)qword_140027338 + 1) != &qword_140027338
        || (v7 = *(_QWORD *)qword_140027338, *(PVOID *)(*(_QWORD *)qword_140027338 + 8LL) != qword_140027338) )
      {
        __fastfail(3u);
      }
      qword_140027338 = *(PVOID *)qword_140027338;
      *(_QWORD *)(v7 + 8) = &qword_140027338;
      --dword_140027348;
      SlbNatDeleteInstance(v6);
    }
    SlbNatCheckLastInstance();
    SlbNatDrainOutstandingWorkItems();
    CleanupWsk();
    if ( qword_1400274C8 )
      IoFreeWorkItem(qword_1400274C8);
    if ( byte_1400273F0 && KeCancelTimer(&Timer) == 1 )
      WinNatDereferenceGlobal();
    ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  }
}

```

## disassembly

```asm
0x140033e5c  push    rdi
0x140033e5e  sub     rsp, 20h
0x140033e62  cmp     cs:SlbNatGlobalState, 0
0x140033e69  jz      loc_140033F9A
0x140033e6f  lea     rcx, Resource; Resource
0x140033e76  mov     cs:byte_1400274E0, 1
0x140033e7d  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140033e84  nop     dword ptr [rax+rax+00h]
0x140033e89  mov     r8, qword ptr cs:xmmword_1400273E0
0x140033e90  mov     edi, 0Ah
0x140033e95  test    r8, r8
0x140033e98  jz      short loc_140033EC3
0x140033e9a  mov     edx, edi
0x140033e9c  lea     rcx, NPI_MS_IPV4_MODULEID
0x140033ea3  call    cs:__imp_NsiDeregisterChangeNotification
0x140033eaa  nop     dword ptr [rax+rax+00h]
0x140033eaf  test    eax, eax
0x140033eb1  jns     short loc_140033EB8
0x140033eb3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033eb8  mov     qword ptr cs:xmmword_1400273E0, 0
0x140033ec3  mov     r8, qword ptr cs:xmmword_1400273E0+8
0x140033eca  test    r8, r8
0x140033ecd  jz      short loc_140033EF8
0x140033ecf  mov     edx, edi
0x140033ed1  lea     rcx, NPI_MS_IPV6_MODULEID
0x140033ed8  call    cs:__imp_NsiDeregisterChangeNotification
0x140033edf  nop     dword ptr [rax+rax+00h]
0x140033ee4  test    eax, eax
0x140033ee6  jns     short loc_140033EED
0x140033ee8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033eed  mov     qword ptr cs:xmmword_1400273E0+8, 0
0x140033ef8  lea     rdi, qword_140027338
0x140033eff  mov     rcx, cs:qword_140027338; P
0x140033f06  cmp     rcx, rdi
0x140033f09  jz      short loc_140033F3B
0x140033f0b  cmp     [rcx+8], rdi
0x140033f0f  jnz     short loc_140033F34
0x140033f11  mov     rax, [rcx]
0x140033f14  cmp     [rax+8], rcx
0x140033f18  jnz     short loc_140033F34
0x140033f1a  mov     cs:qword_140027338, rax
0x140033f21  mov     dl, 1
0x140033f23  mov     [rax+8], rdi
0x140033f27  dec     cs:dword_140027348
0x140033f2d  call    SlbNatDeleteInstance
0x140033f32  jmp     short loc_140033EFF
0x140033f34  mov     ecx, 3
0x140033f39  int     29h; Win8: RtlFailFast(ecx)
0x140033f3b  call    SlbNatCheckLastInstance
0x140033f40  call    SlbNatDrainOutstandingWorkItems
0x140033f45  call    CleanupWsk
0x140033f4a  mov     rcx, cs:qword_1400274C8; IoWorkItem
0x140033f51  test    rcx, rcx
0x140033f54  jz      short loc_140033F62
0x140033f56  call    cs:__imp_IoFreeWorkItem
0x140033f5d  nop     dword ptr [rax+rax+00h]
0x140033f62  cmp     cs:byte_1400273F0, 0
0x140033f69  jz      short loc_140033F87
0x140033f6b  lea     rcx, Timer; PKTIMER
0x140033f72  call    cs:__imp_KeCancelTimer
0x140033f79  nop     dword ptr [rax+rax+00h]
0x140033f7e  cmp     al, 1
0x140033f80  jnz     short loc_140033F87
0x140033f82  call    WinNatDereferenceGlobal
0x140033f87  lea     rcx, Resource; Resource
0x140033f8e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140033f95  nop     dword ptr [rax+rax+00h]
0x140033f9a  add     rsp, 20h
0x140033f9e  pop     rdi
0x140033f9f  retn
```
