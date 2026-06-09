# WinNatCleanupGlobals

- ea: `0x14000daf0`
- end: `0x14000dcc6`
- name: `WinNatCleanupGlobals`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002fe80`

## callees

- `0x14000caa0`
- `0x14000d8e4`
- `0x14000daf0`
- `0x14000dccc`
- `0x14000f738`
- `0x14000f904`
- `0x140012a40`
- `0x140016334`
- `0x140018df8`
- `0x140031088`
- `0x140033e5c`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x14000dc4d`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14000dc4d`
- `ntoskrnl!IoDeleteDevice` at `0x14000dc29`
- `ntoskrnl!IoDeleteDevice` at `0x14000dc29`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dbf2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dbf2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbc4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db67`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc9c`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000db32`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000db32`
- `NETIO!NmrDeregisterProvider` at `0x14000db13`
- `NETIO!NmrDeregisterProvider` at `0x14000db13`
- `NETIO!NetioShutdownWorkQueue` at `0x14000dcaf`
- `NETIO!NetioShutdownWorkQueue` at `0x14000dcaf`
- `NETIO!MdpDestroyPool` at `0x14000dc41`
- `NETIO!MdpDestroyPool` at `0x14000dc41`

## pseudocode

```c
void WinNatCleanupGlobals()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  bool v6; // di
  KIRQL v7; // al
  PVOID *v8; // rbx
  KIRQL v9; // si
  PVOID *v10; // rcx
  __int64 *v11; // rbx
  __int64 *v12; // rcx

  if ( WinNatGlobalDriverState )
  {
    if ( WinNatNsiRegistrationHandle )
    {
      if ( NmrDeregisterProvider(WinNatNsiRegistrationHandle) != 259 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2);
      if ( NmrWaitForProviderDeregisterComplete(WinNatNsiRegistrationHandle) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
    }
    v6 = _InterlockedDecrement(&dword_140027A84) == 1;
    WinNatDeregisterChangeNotifications();
    v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v8 = (PVOID *)qword_140027B08;
    v9 = v7;
    while ( v8 != &qword_140027B08 )
    {
      v10 = v8;
      v8 = (PVOID *)*v8;
      WinNatDeleteUnspecifiedIf(v10);
    }
    v11 = (__int64 *)qword_140027AA0;
    while ( v11 != &qword_140027AA0 )
    {
      v12 = v11 - 41;
      v11 = (__int64 *)*v11;
      WinNatDeleteInstance(v12);
    }
    KeReleaseSpinLock(&SpinLock, v9);
    SlbNatStop();
    if ( !v6 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    SlbNatCleanup();
    if ( EnableXlat )
      IPxlatCleanup();
    WinNatCleanupWFP();
    WinNatLibCleanupState(qword_140027AE0);
    IoDeleteDevice(deviceObject);
    if ( qword_140027AE8 )
      MdpDestroyPool();
    KeFlushQueuedDpcs();
    if ( P )
    {
      if ( qword_140027B00 )
        PplDestroyLookasideList(qword_140027B00, 0x63744E57u);
      ExFreePoolWithTag(P, 0);
    }
    if ( qword_140027B68 )
      ExFreePoolWithTag(qword_140027B68, 0);
    NetioShutdownWorkQueue(qword_140027B18);
  }
}

```

## disassembly

```asm
0x14000daf0  push    rbx
0x14000daf2  push    rsi
0x14000daf3  push    rdi
0x14000daf4  push    r14
0x14000daf6  sub     rsp, 38h
0x14000dafa  cmp     cs:WinNatGlobalDriverState, 0
0x14000db01  jz      loc_14000DCBB
0x14000db07  mov     rcx, cs:WinNatNsiRegistrationHandle; NmrProviderHandle
0x14000db0e  test    rcx, rcx
0x14000db11  jz      short loc_14000DB47
0x14000db13  call    cs:__imp_NmrDeregisterProvider
0x14000db1a  nop     dword ptr [rax+rax+00h]
0x14000db1f  cmp     eax, 103h
0x14000db24  jz      short loc_14000DB2B
0x14000db26  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000db2b  mov     rcx, cs:WinNatNsiRegistrationHandle; NmrProviderHandle
0x14000db32  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14000db39  nop     dword ptr [rax+rax+00h]
0x14000db3e  test    eax, eax
0x14000db40  jz      short loc_14000DB47
0x14000db42  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000db47  or      eax, 0FFFFFFFFh
0x14000db4a  lock xadd cs:dword_140027A84, eax
0x14000db52  dec     eax
0x14000db54  cmp     eax, 1
0x14000db57  setz    dil
0x14000db5b  call    WinNatDeregisterChangeNotifications
0x14000db60  lea     rcx, SpinLock; SpinLock
0x14000db67  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000db6e  nop     dword ptr [rax+rax+00h]
0x14000db73  mov     rbx, cs:qword_140027B08
0x14000db7a  lea     r14, qword_140027B08
0x14000db81  mov     sil, al
0x14000db84  jmp     short loc_14000DB91
0x14000db86  mov     rcx, rbx; P
0x14000db89  mov     rbx, [rbx]
0x14000db8c  call    WinNatDeleteUnspecifiedIf
0x14000db91  cmp     rbx, r14
0x14000db94  jnz     short loc_14000DB86
0x14000db96  mov     rbx, cs:qword_140027AA0
0x14000db9d  lea     r14, qword_140027AA0
0x14000dba4  jmp     short loc_14000DBB5
0x14000dba6  lea     rcx, [rbx-148h]; P
0x14000dbad  mov     rbx, [rbx]
0x14000dbb0  call    WinNatDeleteInstance
0x14000dbb5  cmp     rbx, r14
0x14000dbb8  jnz     short loc_14000DBA6
0x14000dbba  mov     dl, sil; NewIrql
0x14000dbbd  lea     rcx, SpinLock; SpinLock
0x14000dbc4  call    cs:__imp_KeReleaseSpinLock
0x14000dbcb  nop     dword ptr [rax+rax+00h]
0x14000dbd0  call    SlbNatStop
0x14000dbd5  test    dil, dil
0x14000dbd8  jnz     short loc_14000DBFE
0x14000dbda  xor     r9d, r9d; Alertable
0x14000dbdd  mov     [rsp+58h+Timeout], 0; Timeout
0x14000dbe6  xor     r8d, r8d; WaitMode
0x14000dbe9  lea     rcx, Event; Object
0x14000dbf0  xor     edx, edx; WaitReason
0x14000dbf2  call    cs:__imp_KeWaitForSingleObject
0x14000dbf9  nop     dword ptr [rax+rax+00h]
0x14000dbfe  call    SlbNatCleanup
0x14000dc03  cmp     cs:EnableXlat, 0
0x14000dc0a  jz      short loc_14000DC11
0x14000dc0c  call    IPxlatCleanup
0x14000dc11  call    WinNatCleanupWFP
0x14000dc16  mov     rcx, cs:qword_140027AE0; P
0x14000dc1d  call    WinNatLibCleanupState
0x14000dc22  mov     rcx, cs:deviceObject; DeviceObject
0x14000dc29  call    cs:__imp_IoDeleteDevice
0x14000dc30  nop     dword ptr [rax+rax+00h]
0x14000dc35  mov     rcx, cs:qword_140027AE8
0x14000dc3c  test    rcx, rcx
0x14000dc3f  jz      short loc_14000DC4D
0x14000dc41  call    cs:__imp_MdpDestroyPool
0x14000dc48  nop     dword ptr [rax+rax+00h]
0x14000dc4d  call    cs:__imp_KeFlushQueuedDpcs
0x14000dc54  nop     dword ptr [rax+rax+00h]
0x14000dc59  cmp     cs:P, 0
0x14000dc61  jz      short loc_14000DC8E
0x14000dc63  mov     rcx, cs:qword_140027B00; P
0x14000dc6a  test    rcx, rcx
0x14000dc6d  jz      short loc_14000DC79
0x14000dc6f  mov     edx, 63744E57h; Tag
0x14000dc74  call    PplDestroyLookasideList
0x14000dc79  mov     rcx, cs:P; P
0x14000dc80  xor     edx, edx; Tag
0x14000dc82  call    cs:__imp_ExFreePoolWithTag
0x14000dc89  nop     dword ptr [rax+rax+00h]
0x14000dc8e  mov     rcx, cs:qword_140027B68; P
0x14000dc95  test    rcx, rcx
0x14000dc98  jz      short loc_14000DCA8
0x14000dc9a  xor     edx, edx; Tag
0x14000dc9c  call    cs:__imp_ExFreePoolWithTag
0x14000dca3  nop     dword ptr [rax+rax+00h]
0x14000dca8  lea     rcx, qword_140027B18
0x14000dcaf  call    cs:__imp_NetioShutdownWorkQueue
0x14000dcb6  nop     dword ptr [rax+rax+00h]
0x14000dcbb  add     rsp, 38h
0x14000dcbf  pop     r14
0x14000dcc1  pop     rdi
0x14000dcc2  pop     rsi
0x14000dcc3  pop     rbx
0x14000dcc4  retn
```
