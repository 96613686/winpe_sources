# WinNatCleanupGlobals

- ea: `0x14000db20`
- end: `0x14000dcf6`
- name: `WinNatCleanupGlobals`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ee80`

## callees

- `0x14000caa0`
- `0x14000d914`
- `0x14000db20`
- `0x14000dcfc`
- `0x14000f6e0`
- `0x14000f8ac`
- `0x140012100`
- `0x1400159b4`
- `0x140018918`
- `0x14002ff58`
- `0x140032d2c`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x14000dc7d`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14000dc7d`
- `ntoskrnl!IoDeleteDevice` at `0x14000dc59`
- `ntoskrnl!IoDeleteDevice` at `0x14000dc59`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dc22`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000dc22`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbf4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dcb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dcb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dccc`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000db62`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000db62`
- `NETIO!NmrDeregisterProvider` at `0x14000db43`
- `NETIO!NmrDeregisterProvider` at `0x14000db43`
- `NETIO!NetioShutdownWorkQueue` at `0x14000dcdf`
- `NETIO!NetioShutdownWorkQueue` at `0x14000dcdf`
- `NETIO!MdpDestroyPool` at `0x14000dc71`
- `NETIO!MdpDestroyPool` at `0x14000dc71`

## pseudocode

```c
void WinNatCleanupGlobals()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  bool v8; // di
  KIRQL v9; // al
  PVOID *v10; // rbx
  KIRQL v11; // si
  PVOID *v12; // rcx
  __int64 *v13; // rbx
  __int64 *v14; // rcx

  if ( WinNatGlobalDriverState )
  {
    if ( WinNatNsiRegistrationHandle )
    {
      if ( NmrDeregisterProvider(WinNatNsiRegistrationHandle) != 259 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2, v3);
      if ( NmrWaitForProviderDeregisterComplete(WinNatNsiRegistrationHandle) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
    }
    v8 = _InterlockedDecrement(&dword_140026A84) == 1;
    WinNatDeregisterChangeNotifications();
    v9 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v10 = (PVOID *)qword_140026B08;
    v11 = v9;
    while ( v10 != &qword_140026B08 )
    {
      v12 = v10;
      v10 = (PVOID *)*v10;
      WinNatDeleteUnspecifiedIf(v12);
    }
    v13 = (__int64 *)qword_140026AA0;
    while ( v13 != &qword_140026AA0 )
    {
      v14 = v13 - 41;
      v13 = (__int64 *)*v13;
      WinNatDeleteInstance(v14);
    }
    KeReleaseSpinLock(&SpinLock, v11);
    SlbNatStop();
    if ( !v8 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    SlbNatCleanup();
    if ( EnableXlat )
      IPxlatCleanup();
    WinNatCleanupWFP();
    WinNatLibCleanupState(qword_140026AE0);
    IoDeleteDevice(deviceObject);
    if ( qword_140026AE8 )
      MdpDestroyPool();
    KeFlushQueuedDpcs();
    if ( P )
    {
      if ( qword_140026B00 )
        PplDestroyLookasideList(qword_140026B00, 0x63744E57u);
      ExFreePoolWithTag(P, 0);
    }
    if ( qword_140026B68 )
      ExFreePoolWithTag(qword_140026B68, 0);
    NetioShutdownWorkQueue(qword_140026B18);
  }
}

```

## disassembly

```asm
0x14000db20  push    rbx
0x14000db22  push    rsi
0x14000db23  push    rdi
0x14000db24  push    r14
0x14000db26  sub     rsp, 38h
0x14000db2a  cmp     cs:WinNatGlobalDriverState, 0
0x14000db31  jz      loc_14000DCEB
0x14000db37  mov     rcx, cs:WinNatNsiRegistrationHandle; NmrProviderHandle
0x14000db3e  test    rcx, rcx
0x14000db41  jz      short loc_14000DB77
0x14000db43  call    cs:__imp_NmrDeregisterProvider
0x14000db4a  nop     dword ptr [rax+rax+00h]
0x14000db4f  cmp     eax, 103h
0x14000db54  jz      short loc_14000DB5B
0x14000db56  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000db5b  mov     rcx, cs:WinNatNsiRegistrationHandle; NmrProviderHandle
0x14000db62  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14000db69  nop     dword ptr [rax+rax+00h]
0x14000db6e  test    eax, eax
0x14000db70  jz      short loc_14000DB77
0x14000db72  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000db77  or      eax, 0FFFFFFFFh
0x14000db7a  lock xadd cs:dword_140026A84, eax
0x14000db82  dec     eax
0x14000db84  cmp     eax, 1
0x14000db87  setz    dil
0x14000db8b  call    WinNatDeregisterChangeNotifications
0x14000db90  lea     rcx, SpinLock; SpinLock
0x14000db97  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000db9e  nop     dword ptr [rax+rax+00h]
0x14000dba3  mov     rbx, cs:qword_140026B08
0x14000dbaa  lea     r14, qword_140026B08
0x14000dbb1  mov     sil, al
0x14000dbb4  jmp     short loc_14000DBC1
0x14000dbb6  mov     rcx, rbx; P
0x14000dbb9  mov     rbx, [rbx]
0x14000dbbc  call    WinNatDeleteUnspecifiedIf
0x14000dbc1  cmp     rbx, r14
0x14000dbc4  jnz     short loc_14000DBB6
0x14000dbc6  mov     rbx, cs:qword_140026AA0
0x14000dbcd  lea     r14, qword_140026AA0
0x14000dbd4  jmp     short loc_14000DBE5
0x14000dbd6  lea     rcx, [rbx-148h]; P
0x14000dbdd  mov     rbx, [rbx]
0x14000dbe0  call    WinNatDeleteInstance
0x14000dbe5  cmp     rbx, r14
0x14000dbe8  jnz     short loc_14000DBD6
0x14000dbea  mov     dl, sil; NewIrql
0x14000dbed  lea     rcx, SpinLock; SpinLock
0x14000dbf4  call    cs:__imp_KeReleaseSpinLock
0x14000dbfb  nop     dword ptr [rax+rax+00h]
0x14000dc00  call    SlbNatStop
0x14000dc05  test    dil, dil
0x14000dc08  jnz     short loc_14000DC2E
0x14000dc0a  xor     r9d, r9d; Alertable
0x14000dc0d  mov     [rsp+58h+Timeout], 0; Timeout
0x14000dc16  xor     r8d, r8d; WaitMode
0x14000dc19  lea     rcx, Event; Object
0x14000dc20  xor     edx, edx; WaitReason
0x14000dc22  call    cs:__imp_KeWaitForSingleObject
0x14000dc29  nop     dword ptr [rax+rax+00h]
0x14000dc2e  call    SlbNatCleanup
0x14000dc33  cmp     cs:EnableXlat, 0
0x14000dc3a  jz      short loc_14000DC41
0x14000dc3c  call    IPxlatCleanup
0x14000dc41  call    WinNatCleanupWFP
0x14000dc46  mov     rcx, cs:qword_140026AE0; P
0x14000dc4d  call    WinNatLibCleanupState
0x14000dc52  mov     rcx, cs:deviceObject; DeviceObject
0x14000dc59  call    cs:__imp_IoDeleteDevice
0x14000dc60  nop     dword ptr [rax+rax+00h]
0x14000dc65  mov     rcx, cs:qword_140026AE8
0x14000dc6c  test    rcx, rcx
0x14000dc6f  jz      short loc_14000DC7D
0x14000dc71  call    cs:__imp_MdpDestroyPool
0x14000dc78  nop     dword ptr [rax+rax+00h]
0x14000dc7d  call    cs:__imp_KeFlushQueuedDpcs
0x14000dc84  nop     dword ptr [rax+rax+00h]
0x14000dc89  cmp     cs:P, 0
0x14000dc91  jz      short loc_14000DCBE
0x14000dc93  mov     rcx, cs:qword_140026B00; P
0x14000dc9a  test    rcx, rcx
0x14000dc9d  jz      short loc_14000DCA9
0x14000dc9f  mov     edx, 63744E57h; Tag
0x14000dca4  call    PplDestroyLookasideList
0x14000dca9  mov     rcx, cs:P; P
0x14000dcb0  xor     edx, edx; Tag
0x14000dcb2  call    cs:__imp_ExFreePoolWithTag
0x14000dcb9  nop     dword ptr [rax+rax+00h]
0x14000dcbe  mov     rcx, cs:qword_140026B68; P
0x14000dcc5  test    rcx, rcx
0x14000dcc8  jz      short loc_14000DCD8
0x14000dcca  xor     edx, edx; Tag
0x14000dccc  call    cs:__imp_ExFreePoolWithTag
0x14000dcd3  nop     dword ptr [rax+rax+00h]
0x14000dcd8  lea     rcx, qword_140026B18
0x14000dcdf  call    cs:__imp_NetioShutdownWorkQueue
0x14000dce6  nop     dword ptr [rax+rax+00h]
0x14000dceb  add     rsp, 38h
0x14000dcef  pop     r14
0x14000dcf1  pop     rdi
0x14000dcf2  pop     rsi
0x14000dcf3  pop     rbx
0x14000dcf4  retn
```
