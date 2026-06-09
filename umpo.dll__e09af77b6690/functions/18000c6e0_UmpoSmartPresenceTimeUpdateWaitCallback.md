# UmpoSmartPresenceTimeUpdateWaitCallback

- ea: `0x18000c6e0`
- end: `0x18000c779`
- name: `UmpoSmartPresenceTimeUpdateWaitCallback`
- size: `153`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800092a4`
- `0x180009d8c`
- `0x18000c6e0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c772`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c735`

## pseudocode

```c
void __fastcall UmpoSmartPresenceTimeUpdateWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  if ( WaitResult )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( Context )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !UmpoSmartPresenceEnabled )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( UmpoTimeUpdateWork != Wait )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( byte_180024808 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSmartPresenceLock);
  if ( byte_1800247D0 && !UmpoSmartPresenceTimerStop() )
    UmpoSmartPresenceTimerStart();
  if ( byte_180024808 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSmartPresenceLock);
}

```

## disassembly

```asm
0x18000c6e0  mov     [rsp+arg_0], rbx
0x18000c6e5  push    rdi
0x18000c6e6  sub     rsp, 20h
0x18000c6ea  mov     rdi, r8
0x18000c6ed  mov     rbx, rdx
0x18000c6f0  test    r9d, r9d
0x18000c6f3  jz      short loc_18000C6FA
0x18000c6f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c6fa  test    rbx, rbx
0x18000c6fd  jz      short loc_18000C704
0x18000c6ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c704  cmp     cs:UmpoSmartPresenceEnabled, 0
0x18000c70b  jnz     short loc_18000C712
0x18000c70d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c712  cmp     cs:UmpoTimeUpdateWork, rdi
0x18000c719  jz      short loc_18000C720
0x18000c71b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c720  cmp     cs:byte_180024808, 1
0x18000c727  jz      short loc_18000C72E
0x18000c729  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c72e  lea     rcx, UmpoSmartPresenceLock; lpCriticalSection
0x18000c735  call    cs:__imp_EnterCriticalSection
0x18000c73b  mov     al, cs:byte_1800247D0
0x18000c741  test    al, al
0x18000c743  jz      short loc_18000C753
0x18000c745  call    UmpoSmartPresenceTimerStop
0x18000c74a  test    eax, eax
0x18000c74c  jnz     short loc_18000C753
0x18000c74e  call    UmpoSmartPresenceTimerStart
0x18000c753  cmp     cs:byte_180024808, 1
0x18000c75a  jz      short loc_18000C761
0x18000c75c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c761  lea     rcx, UmpoSmartPresenceLock
0x18000c768  mov     rbx, [rsp+28h+arg_0]
0x18000c76d  add     rsp, 20h
0x18000c771  pop     rdi
0x18000c772  jmp     cs:__imp_LeaveCriticalSection
```
