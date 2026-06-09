# GetAbortEvent

- ea: `0x180039994`
- end: `0x180039a3b`
- name: `GetAbortEvent`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180039f98`

## callees

- `0x180039994`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800399c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800399c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039a12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039a12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800399e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800399e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a26`

## pseudocode

```c
void __fastcall GetAbortEvent(unsigned int a1, _QWORD *a2, struct _TP_TIMER **a3, _QWORD *a4)
{
  __int64 v5; // rbp
  HANDLE EventW; // rbx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v10; // rdi
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF

  v5 = a1;
  pftDueTime = 0;
  EventW = CreateEventW(0, 0, 0, L"CancelSCCredUI");
  if ( EventW )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(TimerCallback, (PVOID)L"CancelSCCredUI", 0);
    v10 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)(-10000000 * v5);
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      *a2 = EventW;
      *a3 = v10;
      *a4 = L"CancelSCCredUI";
    }
    else
    {
      CloseHandle(EventW);
    }
  }
}

```

## disassembly

```asm
0x180039994  push    rbx
0x180039996  push    rbp
0x180039997  push    rsi
0x180039998  push    rdi
0x180039999  push    r12
0x18003999b  push    r14
0x18003999d  push    r15
0x18003999f  sub     rsp, 30h
0x1800399a3  mov     rsi, r9
0x1800399a6  mov     ebp, ecx
0x1800399a8  mov     r14, r8
0x1800399ab  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x1800399b4  mov     r15, rdx
0x1800399b7  lea     r12, pv; "CancelSCCredUI"
0x1800399be  mov     r9, r12; lpName
0x1800399c1  xor     r8d, r8d; bInitialState
0x1800399c4  xor     edx, edx; bManualReset
0x1800399c6  xor     ecx, ecx; lpEventAttributes
0x1800399c8  call    cs:__imp_CreateEventW
0x1800399ce  mov     rbx, rax
0x1800399d1  test    rax, rax
0x1800399d4  jz      short loc_180039A2C
0x1800399d6  xor     r8d, r8d; pcbe
0x1800399d9  lea     rcx, TimerCallback; pfnti
0x1800399e0  mov     rdx, r12; pv
0x1800399e3  call    cs:__imp_CreateThreadpoolTimer
0x1800399e9  mov     rdi, rax
0x1800399ec  test    rax, rax
0x1800399ef  jz      short loc_180039A23
0x1800399f1  imul    rcx, rbp, 0FFFFFFFFFF676980h
0x1800399f8  xor     r9d, r9d; msWindowLength
0x1800399fb  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180039a00  mov     [rsp+68h+pftDueTime.dwLowDateTime], ecx
0x180039a04  xor     r8d, r8d; msPeriod
0x180039a07  shr     rcx, 20h
0x180039a0b  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x180039a0f  mov     rcx, rax; pti
0x180039a12  call    cs:__imp_SetThreadpoolTimer
0x180039a18  mov     [r15], rbx
0x180039a1b  mov     [r14], rdi
0x180039a1e  mov     [rsi], r12
0x180039a21  jmp     short loc_180039A2C
0x180039a23  mov     rcx, rbx; hObject
0x180039a26  call    cs:__imp_CloseHandle
0x180039a2c  add     rsp, 30h
0x180039a30  pop     r15
0x180039a32  pop     r14
0x180039a34  pop     r12
0x180039a36  pop     rdi
0x180039a37  pop     rsi
0x180039a38  pop     rbp
0x180039a39  pop     rbx
0x180039a3a  retn
```
