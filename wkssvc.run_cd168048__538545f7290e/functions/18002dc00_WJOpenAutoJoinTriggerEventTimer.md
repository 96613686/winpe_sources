# WJOpenAutoJoinTriggerEventTimer

- ea: `0x18002dc00`
- end: `0x18002dcf3`
- name: `WJOpenAutoJoinTriggerEventTimer`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001eb30`

## callees

- `0x18002dc00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18002dc48`
- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18002dc48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dcde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dcde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002dc12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002dc12`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dc69`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dcc0`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dc69`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dcc0`

## string_xrefs

- `0x18002dc5b`: `WJOpenAutoJoinTriggerEventTimer`
- `0x18002dc89`: `WJOpenAutoJoinTriggerEventTimer`

## pseudocode

```c
__int64 WJOpenAutoJoinTriggerEventTimer()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  g_AutoJoinTriggerEventTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)WJWorkplaceJoinTriggerEventCallback, 0, 0);
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
0x18002dc00  push    rbx
0x18002dc02  sub     rsp, 20h
0x18002dc06  xor     r8d, r8d; pcbe
0x18002dc09  lea     rcx, WJWorkplaceJoinTriggerEventCallback; pfnti
0x18002dc10  xor     edx, edx; pv
0x18002dc12  call    cs:__imp_CreateThreadpoolTimer
0x18002dc19  nop     dword ptr [rax+rax+00h]
0x18002dc1e  mov     cs:g_AutoJoinTriggerEventTimer, rax
0x18002dc25  test    rax, rax
0x18002dc28  jnz     short loc_18002DC3D
0x18002dc2a  call    cs:__imp_GetLastError
0x18002dc31  nop     dword ptr [rax+rax+00h]
0x18002dc36  mov     ebx, eax
0x18002dc38  jmp     loc_18002DCEA
0x18002dc3d  xor     ebx, ebx
0x18002dc3f  lea     rcx, [rsp+28h+arg_0]
0x18002dc44  mov     [rsp+28h+arg_0], ebx
0x18002dc48  call    cs:__imp__o_rand_s
0x18002dc4f  nop     dword ptr [rax+rax+00h]
0x18002dc54  test    eax, eax
0x18002dc56  jz      short loc_18002DC75
0x18002dc58  mov     r8d, eax
0x18002dc5b  lea     rdx, aWjopenautojoin; "WJOpenAutoJoinTriggerEventTimer"
0x18002dc62  lea     rcx, aAutojoinsvcSRa; "AutoJoinSvc/%s: rand_s failed with erro"...
0x18002dc69  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002dc70  nop     dword ptr [rax+rax+00h]
0x18002dc75  mov     ecx, [rsp+28h+arg_0]
0x18002dc79  mov     eax, 91A2B3C5h
0x18002dc7e  mul     ecx
0x18002dc80  shr     edx, 0Bh
0x18002dc83  imul    eax, edx, 0E10h
0x18002dc89  lea     rdx, aWjopenautojoin; "WJOpenAutoJoinTriggerEventTimer"
0x18002dc90  sub     ecx, eax
0x18002dc92  lea     r8d, [rcx+12Ch]
0x18002dc99  movsxd  rax, r8d
0x18002dc9c  imul    rax, 0FFFFFFFFFF676980h
0x18002dca3  mov     cs:g_AutoJoinTriggerEventDelay, r8d
0x18002dcaa  mov     rcx, rax
0x18002dcad  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18002dcb1  shr     rcx, 20h
0x18002dcb5  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x18002dcb9  lea     rcx, aAutojoinsvcSSl; "AutoJoinSvc/%s: Sleeping for %d seconds"...
0x18002dcc0  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002dcc7  nop     dword ptr [rax+rax+00h]
0x18002dccc  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18002dcd3  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002dcd8  xor     r9d, r9d; msWindowLength
0x18002dcdb  xor     r8d, r8d; msPeriod
0x18002dcde  call    cs:__imp_SetThreadpoolTimer
0x18002dce5  nop     dword ptr [rax+rax+00h]
0x18002dcea  mov     eax, ebx
0x18002dcec  add     rsp, 20h
0x18002dcf0  pop     rbx
0x18002dcf1  retn
```
