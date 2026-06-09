# SlbNatStop

- ea: `0x140032d2c`
- end: `0x140032e71`
- name: `SlbNatStop`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000db20`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x140013708`
- `0x1400148ac`
- `0x14002fed8`
- `0x140031300`
- `0x140032d2c`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140032e26`
- `ntoskrnl!IoFreeWorkItem` at `0x140032e26`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032e5e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032e5e`
- `ntoskrnl!KeCancelTimer` at `0x140032e42`
- `ntoskrnl!KeCancelTimer` at `0x140032e42`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140032d4d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140032d4d`
- `NETIO!NsiDeregisterChangeNotification` at `0x140032d73`
- `NETIO!NsiDeregisterChangeNotification` at `0x140032da8`
- `NETIO!NsiDeregisterChangeNotification` at `0x140032d73`
- `NETIO!NsiDeregisterChangeNotification` at `0x140032da8`

## pseudocode

```c
void SlbNatStop()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  PVOID v8; // rcx
  __int64 v9; // rax

  if ( SlbNatGlobalState )
  {
    byte_1400264E0 = 1;
    ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
    if ( (_QWORD)xmmword_1400263E0 )
    {
      if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2, v3);
      *(_QWORD *)&xmmword_1400263E0 = 0;
    }
    if ( *((_QWORD *)&xmmword_1400263E0 + 1) )
    {
      if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 10) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
      *((_QWORD *)&xmmword_1400263E0 + 1) = 0;
    }
    while ( 1 )
    {
      v8 = qword_140026338;
      if ( qword_140026338 == &qword_140026338 )
        break;
      if ( *((PVOID **)qword_140026338 + 1) != &qword_140026338
        || (v9 = *(_QWORD *)qword_140026338, *(PVOID *)(*(_QWORD *)qword_140026338 + 8LL) != qword_140026338) )
      {
        __fastfail(3u);
      }
      qword_140026338 = *(PVOID *)qword_140026338;
      *(_QWORD *)(v9 + 8) = &qword_140026338;
      --dword_140026348;
      SlbNatDeleteInstance(v8);
    }
    SlbNatCheckLastInstance();
    SlbNatDrainOutstandingWorkItems();
    CleanupWsk();
    if ( qword_1400264C8 )
      IoFreeWorkItem(qword_1400264C8);
    if ( byte_1400263F0 && KeCancelTimer(&Timer) == 1 )
      WinNatDereferenceGlobal();
    ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  }
}

```

## disassembly

```asm
0x140032d2c  push    rdi
0x140032d2e  sub     rsp, 20h
0x140032d32  cmp     cs:SlbNatGlobalState, 0
0x140032d39  jz      loc_140032E6A
0x140032d3f  lea     rcx, Resource; Resource
0x140032d46  mov     cs:byte_1400264E0, 1
0x140032d4d  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140032d54  nop     dword ptr [rax+rax+00h]
0x140032d59  mov     r8, qword ptr cs:xmmword_1400263E0
0x140032d60  mov     edi, 0Ah
0x140032d65  test    r8, r8
0x140032d68  jz      short loc_140032D93
0x140032d6a  mov     edx, edi
0x140032d6c  lea     rcx, NPI_MS_IPV4_MODULEID
0x140032d73  call    cs:__imp_NsiDeregisterChangeNotification
0x140032d7a  nop     dword ptr [rax+rax+00h]
0x140032d7f  test    eax, eax
0x140032d81  jns     short loc_140032D88
0x140032d83  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140032d88  mov     qword ptr cs:xmmword_1400263E0, 0
0x140032d93  mov     r8, qword ptr cs:xmmword_1400263E0+8
0x140032d9a  test    r8, r8
0x140032d9d  jz      short loc_140032DC8
0x140032d9f  mov     edx, edi
0x140032da1  lea     rcx, NPI_MS_IPV6_MODULEID
0x140032da8  call    cs:__imp_NsiDeregisterChangeNotification
0x140032daf  nop     dword ptr [rax+rax+00h]
0x140032db4  test    eax, eax
0x140032db6  jns     short loc_140032DBD
0x140032db8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140032dbd  mov     qword ptr cs:xmmword_1400263E0+8, 0
0x140032dc8  lea     rdi, qword_140026338
0x140032dcf  mov     rcx, cs:qword_140026338; P
0x140032dd6  cmp     rcx, rdi
0x140032dd9  jz      short loc_140032E0B
0x140032ddb  cmp     [rcx+8], rdi
0x140032ddf  jnz     short loc_140032E04
0x140032de1  mov     rax, [rcx]
0x140032de4  cmp     [rax+8], rcx
0x140032de8  jnz     short loc_140032E04
0x140032dea  mov     cs:qword_140026338, rax
0x140032df1  mov     dl, 1
0x140032df3  mov     [rax+8], rdi
0x140032df7  dec     cs:dword_140026348
0x140032dfd  call    SlbNatDeleteInstance
0x140032e02  jmp     short loc_140032DCF
0x140032e04  mov     ecx, 3
0x140032e09  int     29h; Win8: RtlFailFast(ecx)
0x140032e0b  call    SlbNatCheckLastInstance
0x140032e10  call    SlbNatDrainOutstandingWorkItems
0x140032e15  call    CleanupWsk
0x140032e1a  mov     rcx, cs:qword_1400264C8; IoWorkItem
0x140032e21  test    rcx, rcx
0x140032e24  jz      short loc_140032E32
0x140032e26  call    cs:__imp_IoFreeWorkItem
0x140032e2d  nop     dword ptr [rax+rax+00h]
0x140032e32  cmp     cs:byte_1400263F0, 0
0x140032e39  jz      short loc_140032E57
0x140032e3b  lea     rcx, Timer; PKTIMER
0x140032e42  call    cs:__imp_KeCancelTimer
0x140032e49  nop     dword ptr [rax+rax+00h]
0x140032e4e  cmp     al, 1
0x140032e50  jnz     short loc_140032E57
0x140032e52  call    WinNatDereferenceGlobal
0x140032e57  lea     rcx, Resource; Resource
0x140032e5e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140032e65  nop     dword ptr [rax+rax+00h]
0x140032e6a  add     rsp, 20h
0x140032e6e  pop     rdi
0x140032e6f  retn
```
