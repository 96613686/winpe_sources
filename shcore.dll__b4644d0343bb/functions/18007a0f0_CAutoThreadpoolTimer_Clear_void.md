# CAutoThreadpoolTimer::_Clear(void)

- ea: `0x18007a0f0`
- end: `0x18007a133`
- name: `?_Clear@CAutoThreadpoolTimer@@AEAAXXZ`
- size: `67`
- prototype: `void __fastcall(CAutoThreadpoolTimer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18007315c`
- `0x1800792e8`

## callees

- `0x18007a0f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007a117`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007a117`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007a120`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007a120`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007a109`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007a109`

## pseudocode

```c
void __fastcall CAutoThreadpoolTimer::_Clear(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18007a0f0  push    rbx
0x18007a0f2  sub     rsp, 20h
0x18007a0f6  mov     rbx, rcx
0x18007a0f9  mov     rcx, [rcx]; pti
0x18007a0fc  test    rcx, rcx
0x18007a0ff  jz      short loc_18007A12D
0x18007a101  xor     r9d, r9d; msWindowLength
0x18007a104  xor     r8d, r8d; msPeriod
0x18007a107  xor     edx, edx; pftDueTime
0x18007a109  call    cs:__imp_SetThreadpoolTimer
0x18007a10f  mov     rcx, [rbx]; pti
0x18007a112  mov     edx, 1; fCancelPendingCallbacks
0x18007a117  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007a11d  mov     rcx, [rbx]; pti
0x18007a120  call    cs:__imp_CloseThreadpoolTimer
0x18007a126  mov     qword ptr [rbx], 0
0x18007a12d  add     rsp, 20h
0x18007a131  pop     rbx
0x18007a132  retn
```
