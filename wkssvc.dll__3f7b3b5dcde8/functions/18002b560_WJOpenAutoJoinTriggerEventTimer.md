# WJOpenAutoJoinTriggerEventTimer

- ea: `0x18002b560`
- end: `0x18002b62e`
- name: `WJOpenAutoJoinTriggerEventTimer`
- size: `206`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d4c0`

## callees

- `0x18002b560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18002b59c`
- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18002b59c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b584`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b620`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b620`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002b572`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002b572`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b5b7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b608`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b5b7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b608`

## string_xrefs

- `0x18002b5a9`: `WJOpenAutoJoinTriggerEventTimer`
- `0x18002b5d1`: `WJOpenAutoJoinTriggerEventTimer`

## pseudocode

```c
__int64 WJOpenAutoJoinTriggerEventTimer()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  g_AutoJoinTriggerEventTimer = CreateThreadpoolTimer(WJWorkplaceJoinTriggerEventCallback, 0, 0);
  if ( g_AutoJoinTriggerEventTimer )
  {
    v0 = 0;
    v3 = 0;
    v1 = _o_rand_s(&v3);
    if ( v1 )
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: rand_s failed with error %d, use 0 as default",
        L"WJOpenAutoJoinTriggerEventTimer",
        v1);
    g_AutoJoinTriggerEventDelay = v3 % 0xE10 + 300;
    pftDueTime = (struct _FILETIME)(-10000000LL * (int)(v3 % 0xE10 + 300));
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Sleeping for %d seconds before writng the auto join trigger event.",
      L"WJOpenAutoJoinTriggerEventTimer");
    SetThreadpoolTimer(g_AutoJoinTriggerEventTimer, &pftDueTime, 0, 0);
  }
  else
  {
    return GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x18002b560  push    rbx
0x18002b562  sub     rsp, 20h
0x18002b566  xor     r8d, r8d; pcbe
0x18002b569  lea     rcx, WJWorkplaceJoinTriggerEventCallback; pfnti
0x18002b570  xor     edx, edx; pv
0x18002b572  call    cs:__imp_CreateThreadpoolTimer
0x18002b578  mov     cs:g_AutoJoinTriggerEventTimer, rax
0x18002b57f  test    rax, rax
0x18002b582  jnz     short loc_18002B591
0x18002b584  call    cs:__imp_GetLastError
0x18002b58a  mov     ebx, eax
0x18002b58c  jmp     loc_18002B626
0x18002b591  xor     ebx, ebx
0x18002b593  lea     rcx, [rsp+28h+arg_0]
0x18002b598  mov     [rsp+28h+arg_0], ebx
0x18002b59c  call    cs:__imp__o_rand_s
0x18002b5a2  test    eax, eax
0x18002b5a4  jz      short loc_18002B5BD
0x18002b5a6  mov     r8d, eax
0x18002b5a9  lea     rdx, aWjopenautojoin; "WJOpenAutoJoinTriggerEventTimer"
0x18002b5b0  lea     rcx, aAutojoinsvcSRa; "AutoJoinSvc/%s: rand_s failed with erro"...
0x18002b5b7  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b5bd  mov     ecx, [rsp+28h+arg_0]
0x18002b5c1  mov     eax, 91A2B3C5h
0x18002b5c6  mul     ecx
0x18002b5c8  shr     edx, 0Bh
0x18002b5cb  imul    eax, edx, 0E10h
0x18002b5d1  lea     rdx, aWjopenautojoin; "WJOpenAutoJoinTriggerEventTimer"
0x18002b5d8  sub     ecx, eax
0x18002b5da  lea     r8d, [rcx+12Ch]
0x18002b5e1  movsxd  rax, r8d
0x18002b5e4  imul    rax, 0FFFFFFFFFF676980h
0x18002b5eb  mov     cs:g_AutoJoinTriggerEventDelay, r8d
0x18002b5f2  mov     rcx, rax
0x18002b5f5  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18002b5f9  shr     rcx, 20h
0x18002b5fd  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x18002b601  lea     rcx, aAutojoinsvcSSl; "AutoJoinSvc/%s: Sleeping for %d seconds"...
0x18002b608  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b60e  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18002b615  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002b61a  xor     r9d, r9d; msWindowLength
0x18002b61d  xor     r8d, r8d; msPeriod
0x18002b620  call    cs:__imp_SetThreadpoolTimer
0x18002b626  mov     eax, ebx
0x18002b628  add     rsp, 20h
0x18002b62c  pop     rbx
0x18002b62d  retn
```
