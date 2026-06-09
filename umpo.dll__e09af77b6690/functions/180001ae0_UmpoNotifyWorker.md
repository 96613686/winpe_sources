# UmpoNotifyWorker

- ea: `0x180001ae0`
- end: `0x180001bcd`
- name: `UmpoNotifyWorker`
- size: `237`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b39c`

## callees

- `0x180001770`
- `0x180001818`
- `0x18000186c`
- `0x180001ae0`
- `0x180001d24`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001b73`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b4f`

## pseudocode

```c
void __fastcall UmpoNotifyWorker(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // esi

  v1 = a1 + 40;
  v2 = 0;
  if ( *(_DWORD *)(a1 + 40) != 7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *(_BYTE *)(v1 + 21) )
    v2 = UmpoPushTransitionRecord(v1);
  if ( *(_DWORD *)(v1 + 12) == 10 && UmpoPowerStatusChangeWorker )
  {
    if ( byte_180024E88 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    EnterCriticalSection(&UmpoPowerStateNotificationLock);
    UmpoPowerStateNotificationNeeded = 1;
    if ( !UmpoPowerStateNotifyInProgress )
    {
      UmpoPowerStateNotifyInProgress = 1;
      SubmitThreadpoolWork(UmpoPowerStatusChangeWorker);
    }
    if ( byte_180024E88 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LeaveCriticalSection(&UmpoPowerStateNotificationLock);
  }
  else
  {
    UmpoNotify(v1);
  }
  if ( *(_BYTE *)(v1 + 21) || *(_BYTE *)(v1 + 20) )
  {
    if ( v2 )
      UmpoPopTransitionRecord();
    UmpoAlpcSendPortMessage(a1);
  }
}

```

## disassembly

```asm
0x180001ae0  mov     [rsp+arg_0], rbx
0x180001ae5  mov     [rsp+arg_8], rsi
0x180001aea  push    rdi
0x180001aeb  sub     rsp, 20h
0x180001aef  lea     rbx, [rcx+28h]
0x180001af3  xor     esi, esi
0x180001af5  cmp     dword ptr [rbx], 7
0x180001af8  mov     rdi, rcx
0x180001afb  jnz     loc_180001BC3
0x180001b01  cmp     [rbx+15h], sil
0x180001b05  jnz     loc_180001B9F
0x180001b0b  cmp     dword ptr [rbx+0Ch], 0Ah
0x180001b0f  jz      short loc_180001B35
0x180001b11  mov     rcx, rbx
0x180001b14  call    UmpoNotify
0x180001b19  cmp     byte ptr [rbx+15h], 0
0x180001b1d  jnz     short loc_180001B91
0x180001b1f  cmp     byte ptr [rbx+14h], 0
0x180001b23  jnz     short loc_180001B91
0x180001b25  mov     rbx, [rsp+28h+arg_0]
0x180001b2a  mov     rsi, [rsp+28h+arg_8]
0x180001b2f  add     rsp, 20h
0x180001b33  pop     rdi
0x180001b34  retn
0x180001b35  cmp     cs:UmpoPowerStatusChangeWorker, 0
0x180001b3d  jz      short loc_180001B11
0x180001b3f  cmp     cs:byte_180024E88, 1
0x180001b46  jnz     short loc_180001BBC
0x180001b48  lea     rcx, UmpoPowerStateNotificationLock; lpCriticalSection
0x180001b4f  call    cs:__imp_EnterCriticalSection
0x180001b55  cmp     cs:UmpoPowerStateNotifyInProgress, 0
0x180001b5c  mov     cs:UmpoPowerStateNotificationNeeded, 1
0x180001b63  jnz     short loc_180001B79
0x180001b65  mov     rcx, cs:UmpoPowerStatusChangeWorker; pwk
0x180001b6c  mov     cs:UmpoPowerStateNotifyInProgress, 1
0x180001b73  call    cs:__imp_SubmitThreadpoolWork
0x180001b79  cmp     cs:byte_180024E88, 1
0x180001b80  jnz     short loc_180001BB5
0x180001b82  lea     rcx, UmpoPowerStateNotificationLock; lpCriticalSection
0x180001b89  call    cs:__imp_LeaveCriticalSection
0x180001b8f  jmp     short loc_180001B19
0x180001b91  test    esi, esi
0x180001b93  jnz     short loc_180001BAE
0x180001b95  mov     rcx, rdi
0x180001b98  call    UmpoAlpcSendPortMessage
0x180001b9d  jmp     short loc_180001B25
0x180001b9f  mov     rcx, rbx
0x180001ba2  call    UmpoPushTransitionRecord
0x180001ba7  mov     esi, eax
0x180001ba9  jmp     loc_180001B0B
0x180001bae  call    UmpoPopTransitionRecord
0x180001bb3  jmp     short loc_180001B95
0x180001bb5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001bba  jmp     short loc_180001B82
0x180001bbc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001bc1  jmp     short loc_180001B48
0x180001bc3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001bc8  jmp     loc_180001B01
```
