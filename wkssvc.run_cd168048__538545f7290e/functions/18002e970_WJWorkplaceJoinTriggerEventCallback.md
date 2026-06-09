# WJWorkplaceJoinTriggerEventCallback

- ea: `0x18002e970`
- end: `0x18002ea1d`
- name: `WJWorkplaceJoinTriggerEventCallback`
- size: `173`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e970`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e9f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e9f2`
- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x18002e9ba`
- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x18002e9ba`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e9db`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e9db`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e987`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e9a8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e987`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e9a8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002ea11`

## string_xrefs

- `0x18002e9d4`: `AutoJoinSvc/%s: Failed to write the auto join trigger event with error 0x%08x.`

## pseudocode

```c
void __fastcall WJWorkplaceJoinTriggerEventCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  int v4; // eax

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJWorkplaceJoinTriggerEventCallback");
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Writing the auto join trigger event after sleeping for %d seconds.",
    L"WJWorkplaceJoinTriggerEventCallback",
    (unsigned int)g_AutoJoinTriggerEventDelay);
  v4 = DsrWriteAutoJoinSvcTriggerEvent((unsigned int)g_AutoJoinTriggerEventDelay);
  if ( v4 < 0 )
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to write the auto join trigger event with error 0x%08x.",
      L"WJWorkplaceJoinTriggerEventCallback",
      (unsigned int)v4);
  SetThreadpoolTimer(Timer, 0, 0, 0);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJWorkplaceJoinTriggerEventCallback");
}

```

## disassembly

```asm
0x18002e970  push    rbx
0x18002e972  sub     rsp, 20h
0x18002e976  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002e97d  mov     rbx, r8
0x18002e980  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002e987  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e98e  nop     dword ptr [rax+rax+00h]
0x18002e993  mov     r8d, cs:g_AutoJoinTriggerEventDelay
0x18002e99a  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002e9a1  lea     rcx, aAutojoinsvcSWr; "AutoJoinSvc/%s: Writing the auto join t"...
0x18002e9a8  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e9af  nop     dword ptr [rax+rax+00h]
0x18002e9b4  mov     ecx, cs:g_AutoJoinTriggerEventDelay
0x18002e9ba  call    cs:__imp_DsrWriteAutoJoinSvcTriggerEvent
0x18002e9c1  nop     dword ptr [rax+rax+00h]
0x18002e9c6  test    eax, eax
0x18002e9c8  jns     short loc_18002E9E7
0x18002e9ca  mov     r8d, eax
0x18002e9cd  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002e9d4  lea     rcx, aAutojoinsvcSFa_13; "AutoJoinSvc/%s: Failed to write the aut"...
0x18002e9db  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e9e2  nop     dword ptr [rax+rax+00h]
0x18002e9e7  xor     r9d, r9d; msWindowLength
0x18002e9ea  xor     r8d, r8d; msPeriod
0x18002e9ed  xor     edx, edx; pftDueTime
0x18002e9ef  mov     rcx, rbx; pti
0x18002e9f2  call    cs:__imp_SetThreadpoolTimer
0x18002e9f9  nop     dword ptr [rax+rax+00h]
0x18002e9fe  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002ea05  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002ea0c  add     rsp, 20h
0x18002ea10  pop     rbx
0x18002ea11  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
