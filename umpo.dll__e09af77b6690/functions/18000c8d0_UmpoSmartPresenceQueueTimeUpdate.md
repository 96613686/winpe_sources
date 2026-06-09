# UmpoSmartPresenceQueueTimeUpdate

- ea: `0x18000c8d0`
- end: `0x18000c958`
- name: `UmpoSmartPresenceQueueTimeUpdate`
- size: `136`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c4a0`

## callees

- `0x18000c8d0`
- `0x18000f3dc`
- `0x18000f948`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000c923`
- `ntdll!DbgPrint` at `0x18000c923`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c8f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c8f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c93a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c93a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c951`

## string_xrefs

- `0x18000c91c`: `%s: Time update notification (Delta = %lld)\n`
- `0x18000c915`: `UmpoSmartPresenceQueueTimeUpdate`

## pseudocode

```c
BOOL __fastcall UmpoSmartPresenceQueueTimeUpdate(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx

  if ( !UmpoSmartPresenceEnabled )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  WaitForThreadpoolWaitCallbacks(UmpoTimeUpdateWork, 0);
  v4 = a2 - a1;
  UmpoTraceSmartPresenceTimeUpdate(v4);
  if ( (UmpoDebug & 2) != 0 )
    DbgPrint("%s: Time update notification (Delta = %lld)\n", "UmpoSmartPresenceQueueTimeUpdate", v4);
  SetThreadpoolWait(UmpoTimeUpdateWork, hObject, 0);
  return SetEvent(hObject);
}

```

## disassembly

```asm
0x18000c8d0  mov     [rsp+arg_0], rbx
0x18000c8d5  push    rdi
0x18000c8d6  sub     rsp, 20h
0x18000c8da  cmp     cs:UmpoSmartPresenceEnabled, 0
0x18000c8e1  mov     rbx, rdx
0x18000c8e4  mov     rdi, rcx
0x18000c8e7  jnz     short loc_18000C8EE
0x18000c8e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c8ee  mov     rcx, cs:UmpoTimeUpdateWork; pwa
0x18000c8f5  xor     edx, edx; fCancelPendingCallbacks
0x18000c8f7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000c8fd  sub     rbx, rdi
0x18000c900  mov     rcx, rbx
0x18000c903  call    UmpoTraceSmartPresenceTimeUpdate
0x18000c908  mov     eax, cs:UmpoDebug
0x18000c90e  test    al, 2
0x18000c910  jz      short loc_18000C929
0x18000c912  mov     r8, rbx
0x18000c915  lea     rdx, aUmposmartprese_5; "UmpoSmartPresenceQueueTimeUpdate"
0x18000c91c  lea     rcx, aSTimeUpdateNot; "%s: Time update notification (Delta = %"...
0x18000c923  call    cs:__imp_DbgPrint
0x18000c929  mov     rdx, cs:hObject; h
0x18000c930  xor     r8d, r8d; pftTimeout
0x18000c933  mov     rcx, cs:UmpoTimeUpdateWork; pwa
0x18000c93a  call    cs:__imp_SetThreadpoolWait
0x18000c940  mov     rcx, cs:hObject
0x18000c947  mov     rbx, [rsp+28h+arg_0]
0x18000c94c  add     rsp, 20h
0x18000c950  pop     rdi
0x18000c951  jmp     cs:__imp_SetEvent
```
