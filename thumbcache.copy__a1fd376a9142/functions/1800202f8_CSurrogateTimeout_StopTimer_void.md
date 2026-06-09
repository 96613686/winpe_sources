# CSurrogateTimeout::StopTimer(void)

- ea: `0x1800202f8`
- end: `0x180020348`
- name: `?StopTimer@CSurrogateTimeout@@QEAAXXZ`
- size: `80`
- prototype: `void __fastcall(CSurrogateTimeout *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f884`
- `0x18001ff40`

## callees

- `0x180017714`
- `0x1800202f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020338`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020338`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002031f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002031f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002032e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002032e`

## pseudocode

```c
void __fastcall CSurrogateTimeout::StopTimer(CSurrogateTimeout *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 1), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  CAutoHandle<void *>::~CAutoHandle<void *>(this);
}

```

## disassembly

```asm
0x1800202f8  push    rbx
0x1800202fa  sub     rsp, 20h
0x1800202fe  mov     rbx, rcx
0x180020301  mov     rcx, [rcx+8]; pti
0x180020305  test    rcx, rcx
0x180020308  jnz     short loc_180020317
0x18002030a  mov     rcx, rbx
0x18002030d  add     rsp, 20h
0x180020311  pop     rbx
0x180020312  jmp     ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180020317  xor     r9d, r9d; msWindowLength
0x18002031a  xor     r8d, r8d; msPeriod
0x18002031d  xor     edx, edx; pftDueTime
0x18002031f  call    cs:__imp_SetThreadpoolTimer
0x180020325  mov     rcx, [rbx+8]; pti
0x180020329  mov     edx, 1; fCancelPendingCallbacks
0x18002032e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020334  mov     rcx, [rbx+8]; pti
0x180020338  call    cs:__imp_CloseThreadpoolTimer
0x18002033e  mov     qword ptr [rbx+8], 0
0x180020346  jmp     short loc_18002030A
```
