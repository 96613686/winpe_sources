# CTSThreadInternal::ThreadWatchdogSetup(void (*)(void *),void (*)(void *),void *)

- ea: `0x18003eab0`
- end: `0x18003eb3b`
- name: `?ThreadWatchdogSetup@CTSThreadInternal@@UEAAJP6AXPEAX@Z10@Z`
- size: `139`
- prototype: `__int64 __fastcall(PVOID pv, void (*)(void *), void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003e860`

## callees

- `0x18001b318`
- `0x18001b5ac`
- `0x18003eab0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ead7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ead7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003eb1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003eb1c`

## pseudocode

```c
__int64 __fastcall CTSThreadInternal::ThreadWatchdogSetup(
        PTP_TIMER *pv,
        struct _TP_TIMER *a2,
        struct _TP_TIMER *a3,
        struct _TP_TIMER *a4)
{
  __int64 result; // rax
  PTP_TIMER ThreadpoolTimer; // rax

  if ( pv[7] )
  {
    PAL_System_WinCommon_StopThreadpoolTimer();
    CloseThreadpoolTimer(pv[7]);
    pv[7] = 0;
  }
  if ( a2 )
  {
    pv[8] = a2;
    pv[9] = a3;
    pv[10] = a4;
    PAL_System_AtomicExchange(pv + 11);
    ThreadpoolTimer = CreateThreadpoolTimer(CTSThreadInternal::TimerCallbackMultiplex, pv, 0);
    pv[7] = ThreadpoolTimer;
    return ThreadpoolTimer == 0 ? 0x80004005 : 0;
  }
  else
  {
    pv[8] = 0;
    result = 0;
    pv[9] = 0;
    pv[10] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003eab0  push    rbx
0x18003eab2  push    rbp
0x18003eab3  push    rsi
0x18003eab4  push    rdi
0x18003eab5  sub     rsp, 28h
0x18003eab9  mov     rbx, rcx
0x18003eabc  mov     rsi, r9
0x18003eabf  mov     rcx, [rcx+38h]
0x18003eac3  mov     rbp, r8
0x18003eac6  mov     rdi, rdx
0x18003eac9  test    rcx, rcx
0x18003eacc  jz      short loc_18003EAE5
0x18003eace  call    PAL_System_WinCommon_StopThreadpoolTimer
0x18003ead3  mov     rcx, [rbx+38h]; pti
0x18003ead7  call    cs:__imp_CloseThreadpoolTimer
0x18003eadd  mov     qword ptr [rbx+38h], 0
0x18003eae5  test    rdi, rdi
0x18003eae8  jnz     short loc_18003EAFA
0x18003eaea  mov     [rbx+40h], rdi
0x18003eaee  xor     eax, eax
0x18003eaf0  mov     [rbx+48h], rdi
0x18003eaf4  mov     [rbx+50h], rdi
0x18003eaf8  jmp     short loc_18003EB32
0x18003eafa  lea     rcx, [rbx+58h]
0x18003eafe  mov     [rbx+40h], rdi
0x18003eb02  mov     [rbx+48h], rbp
0x18003eb06  mov     [rbx+50h], rsi
0x18003eb0a  call    PAL_System_AtomicExchange
0x18003eb0f  xor     r8d, r8d; pcbe
0x18003eb12  lea     rcx, ?TimerCallbackMultiplex@CTSThreadInternal@@CAXPEAX00@Z; pfnti
0x18003eb19  mov     rdx, rbx; pv
0x18003eb1c  call    cs:__imp_CreateThreadpoolTimer
0x18003eb22  mov     [rbx+38h], rax
0x18003eb26  neg     rax
0x18003eb29  sbb     eax, eax
0x18003eb2b  not     eax
0x18003eb2d  and     eax, 80004005h
0x18003eb32  add     rsp, 28h
0x18003eb36  pop     rdi
0x18003eb37  pop     rsi
0x18003eb38  pop     rbp
0x18003eb39  pop     rbx
0x18003eb3a  retn
```
