# WJOpenSetTaskStateRetryTimer

- ea: `0x18002dcfc`
- end: `0x18002ddde`
- name: `WJOpenSetTaskStateRetryTimer`
- size: `226`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002e16c`

## callees

- `0x18002dcfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd3b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002dd67`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002dd67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ddc2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ddc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002dd23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002dd23`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dda7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dda7`

## string_xrefs

- `0x18002dd99`: `WJOpenSetTaskStateRetryTimer`
- `0x18002dda0`: `AutoJoinSvc/%s: Starting thread pool timer to retry %s task "%s\%s".`

## pseudocode

```c
__int64 __fastcall WJOpenSetTaskStateRetryTimer(char *pv, __int64 a2, __int64 a3, __int16 a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v9; // edi
  const wchar_t *v10; // r8
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)WJWorkplaceJoinTaskStateCallback, pv, 0);
  *((_QWORD *)pv + 8) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *(_QWORD *)pv = a2;
    v9 = 0;
    *((_QWORD *)pv + 1) = a3;
    *((_WORD *)pv + 8) = a4;
    *((_DWORD *)pv + 5) = 60;
    InitializeCriticalSection((LPCRITICAL_SECTION)(pv + 24));
    pftDueTime = (struct _FILETIME)-10000000LL;
    v10 = L"enabling";
    if ( !a4 )
      v10 = L"disabling";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Starting thread pool timer to retry %s task \"%s\\%s\".",
      L"WJOpenSetTaskStateRetryTimer",
      v10,
      a2,
      a3);
    SetThreadpoolTimer(*((PTP_TIMER *)pv + 8), &pftDueTime, 0, 0);
  }
  else
  {
    return GetLastError();
  }
  return v9;
}

```

## disassembly

```asm
0x18002dcfc  push    rbx
0x18002dcfe  push    rbp
0x18002dcff  push    rsi
0x18002dd00  push    rdi
0x18002dd01  push    r14
0x18002dd03  push    r15
0x18002dd05  sub     rsp, 38h
0x18002dd09  mov     r14, rdx
0x18002dd0c  mov     rbp, r8
0x18002dd0f  mov     rdx, rcx; pv
0x18002dd12  mov     rbx, rcx
0x18002dd15  lea     rcx, WJWorkplaceJoinTaskStateCallback; pfnti
0x18002dd1c  xor     r8d, r8d; pcbe
0x18002dd1f  movzx   esi, r9w
0x18002dd23  call    cs:__imp_CreateThreadpoolTimer
0x18002dd2a  nop     dword ptr [rax+rax+00h]
0x18002dd2f  xor     r15d, r15d
0x18002dd32  mov     [rbx+40h], rax
0x18002dd36  test    rax, rax
0x18002dd39  jnz     short loc_18002DD4E
0x18002dd3b  call    cs:__imp_GetLastError
0x18002dd42  nop     dword ptr [rax+rax+00h]
0x18002dd47  mov     edi, eax
0x18002dd49  jmp     loc_18002DDCE
0x18002dd4e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18002dd52  mov     [rbx], r14
0x18002dd55  mov     edi, r15d
0x18002dd58  mov     [rbx+8], rbp
0x18002dd5c  mov     [rbx+10h], si
0x18002dd60  mov     dword ptr [rbx+14h], 3Ch ; '<'
0x18002dd67  call    cs:__imp_InitializeCriticalSection
0x18002dd6e  nop     dword ptr [rax+rax+00h]
0x18002dd73  lea     rax, aDisabling; "disabling"
0x18002dd7a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18002dd83  test    si, si
0x18002dd86  mov     [rsp+68h+var_48], rbp
0x18002dd8b  lea     r8, aEnabling; "enabling"
0x18002dd92  mov     r9, r14
0x18002dd95  cmovz   r8, rax
0x18002dd99  lea     rdx, aWjopensettasks; "WJOpenSetTaskStateRetryTimer"
0x18002dda0  lea     rcx, aAutojoinsvcSSt; "AutoJoinSvc/%s: Starting thread pool ti"...
0x18002dda7  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002ddae  nop     dword ptr [rax+rax+00h]
0x18002ddb3  mov     rcx, [rbx+40h]; pti
0x18002ddb7  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002ddbc  xor     r9d, r9d; msWindowLength
0x18002ddbf  xor     r8d, r8d; msPeriod
0x18002ddc2  call    cs:__imp_SetThreadpoolTimer
0x18002ddc9  nop     dword ptr [rax+rax+00h]
0x18002ddce  mov     eax, edi
0x18002ddd0  add     rsp, 38h
0x18002ddd4  pop     r15
0x18002ddd6  pop     r14
0x18002ddd8  pop     rdi
0x18002ddd9  pop     rsi
0x18002ddda  pop     rbp
0x18002dddb  pop     rbx
0x18002dddc  retn
```
