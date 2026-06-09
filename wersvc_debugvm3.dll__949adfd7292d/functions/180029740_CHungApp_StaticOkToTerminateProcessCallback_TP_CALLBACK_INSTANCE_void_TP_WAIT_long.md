# CHungApp::StaticOkToTerminateProcessCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180029740`
- end: `0x1800297c3`
- name: `?StaticOkToTerminateProcessCallback@CHungApp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `131`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013df4`
- `0x180029740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002975f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002975f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002978f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800297a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002978f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800297a6`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800297b2`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800297b2`

## pseudocode

```c
void __fastcall CHungApp::StaticOkToTerminateProcessCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _RTL_CRITICAL_SECTION *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  struct _TP_WAIT *SpinCount; // rcx
  struct _TP_WAIT *LockSemaphore; // rcx

  if ( Context )
  {
    EnterCriticalSection(Context);
    if ( !Context[61].RecursionCount && Context[1].LockCount )
    {
      SpinCount = (struct _TP_WAIT *)Context[60].SpinCount;
      Context[8].LockCount = 1;
      if ( SpinCount )
        SetThreadpoolWait(SpinCount, 0, 0);
      LockSemaphore = (struct _TP_WAIT *)Context[59].LockSemaphore;
      if ( LockSemaphore )
        SetThreadpoolWait(LockSemaphore, 0, 0);
    }
    LeaveCriticalSectionWhenCallbackReturns(Instance, Context);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance, 0, Wait, WaitResult);
  }
}

```

## disassembly

```asm
0x180029740  mov     [rsp+arg_0], rbx
0x180029745  push    rdi
0x180029746  sub     rsp, 20h
0x18002974a  mov     rbx, rdx
0x18002974d  mov     rdi, rcx
0x180029750  test    rdx, rdx
0x180029753  jnz     short loc_18002975C
0x180029755  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002975a  jmp     short loc_1800297B8
0x18002975c  mov     rcx, rbx; lpCriticalSection
0x18002975f  call    cs:__imp_EnterCriticalSection
0x180029765  cmp     dword ptr [rbx+994h], 0
0x18002976c  jnz     short loc_1800297AC
0x18002976e  cmp     dword ptr [rbx+30h], 0
0x180029772  jz      short loc_1800297AC
0x180029774  mov     rcx, [rbx+980h]; pwa
0x18002977b  mov     dword ptr [rbx+148h], 1
0x180029785  test    rcx, rcx
0x180029788  jz      short loc_180029795
0x18002978a  xor     r8d, r8d; pftTimeout
0x18002978d  xor     edx, edx; h
0x18002978f  call    cs:__imp_SetThreadpoolWait
0x180029795  mov     rcx, [rbx+950h]; pwa
0x18002979c  test    rcx, rcx
0x18002979f  jz      short loc_1800297AC
0x1800297a1  xor     r8d, r8d; pftTimeout
0x1800297a4  xor     edx, edx; h
0x1800297a6  call    cs:__imp_SetThreadpoolWait
0x1800297ac  mov     rdx, rbx; pcs
0x1800297af  mov     rcx, rdi; pci
0x1800297b2  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x1800297b8  mov     rbx, [rsp+28h+arg_0]
0x1800297bd  add     rsp, 20h
0x1800297c1  pop     rdi
0x1800297c2  retn
```
