# CHungApp::StaticTerminateProcessCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180029800`
- end: `0x180029875`
- name: `?StaticTerminateProcessCallback@CHungApp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `117`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013df4`
- `0x180029800`
- `0x18002b424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029824`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029824`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002984f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002984f`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180029863`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180029863`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHungApp::StaticTerminateProcessCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _RTL_CRITICAL_SECTION *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _TP_WAIT *SpinCount; // rcx

  if ( Context )
  {
    EnterCriticalSection(Context);
    if ( !Context[61].RecursionCount && Context[1].LockCount )
    {
      SpinCount = (struct _TP_WAIT *)Context[59].SpinCount;
      if ( SpinCount )
        SetThreadpoolWait(SpinCount, 0, 0);
      CHungApp::_TerminateProcessCallback((CHungApp *)Context);
    }
    LeaveCriticalSectionWhenCallbackReturns(Instance, Context);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance);
  }
}

```

## disassembly

```asm
0x180029800  mov     [rsp+arg_0], rbx
0x180029805  push    rdi
0x180029806  sub     rsp, 30h
0x18002980a  mov     rbx, rdx
0x18002980d  mov     rdi, rcx
0x180029810  test    rdx, rdx
0x180029813  jnz     short loc_18002981C
0x180029815  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002981a  jmp     short loc_18002986A
0x18002981c  mov     [rsp+38h+var_18], rbx
0x180029821  mov     rcx, rbx; lpCriticalSection
0x180029824  call    cs:__imp_EnterCriticalSection
0x18002982a  mov     [rsp+38h+var_10], 1
0x18002982f  cmp     dword ptr [rbx+994h], 0
0x180029836  jnz     short loc_18002985D
0x180029838  cmp     dword ptr [rbx+30h], 0
0x18002983c  jz      short loc_18002985D
0x18002983e  mov     rcx, [rbx+958h]; pwa
0x180029845  test    rcx, rcx
0x180029848  jz      short loc_180029855
0x18002984a  xor     r8d, r8d; pftTimeout
0x18002984d  xor     edx, edx; h
0x18002984f  call    cs:__imp_SetThreadpoolWait
0x180029855  mov     rcx, rbx; this
0x180029858  call    ?_TerminateProcessCallback@CHungApp@@AEAAXXZ; CHungApp::_TerminateProcessCallback(void)
0x18002985d  mov     rdx, rbx; pcs
0x180029860  mov     rcx, rdi; pci
0x180029863  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x180029869  nop
0x18002986a  mov     rbx, [rsp+38h+arg_0]
0x18002986f  add     rsp, 30h
0x180029873  pop     rdi
0x180029874  retn
```
