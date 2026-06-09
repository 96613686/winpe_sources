# HTTP2PingOriginator::DisablePingsInternal(void)

- ea: `0x1800097b4`
- end: `0x18000981c`
- name: `?DisablePingsInternal@HTTP2PingOriginator@@AEAAXXZ`
- size: `104`
- prototype: `void __fastcall(HTTP2PingOriginator *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b90`
- `0x180012110`
- `0x18001964c`

## callees

- `0x1800097b4`
- `0x180016df8`
- `0x180025010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009807`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009807`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1800097c9`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1800097c9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800097f5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800097f5`

## pseudocode

```c
void __fastcall HTTP2PingOriginator::DisablePingsInternal(HTTP2PingOriginator *this)
{
  PTP_TIMER *v2; // rcx

  v2 = (PTP_TIMER *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    if ( IsThreadpoolTimerSet(*v2) )
    {
      (*((void (**)(void))pRuntimeImportTable + 96))();
      SetThreadpoolTimer(**((PTP_TIMER **)this + 5), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(**((PTP_TIMER **)this + 5), 1);
      HTTP2Channel::RemoveReference(*((HTTP2Channel **)this + 3));
    }
  }
}

```

## disassembly

```asm
0x1800097b4  push    rbx
0x1800097b6  sub     rsp, 20h
0x1800097ba  mov     rbx, rcx
0x1800097bd  mov     rcx, [rcx+28h]
0x1800097c1  test    rcx, rcx
0x1800097c4  jz      short loc_180009816
0x1800097c6  mov     rcx, [rcx]; pti
0x1800097c9  call    cs:__imp_IsThreadpoolTimerSet
0x1800097cf  test    eax, eax
0x1800097d1  jz      short loc_180009816
0x1800097d3  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800097da  mov     rax, [rax+300h]
0x1800097e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e6  mov     rcx, [rbx+28h]
0x1800097ea  xor     r9d, r9d; msWindowLength
0x1800097ed  xor     r8d, r8d; msPeriod
0x1800097f0  xor     edx, edx; pftDueTime
0x1800097f2  mov     rcx, [rcx]; pti
0x1800097f5  call    cs:__imp_SetThreadpoolTimer
0x1800097fb  mov     rcx, [rbx+28h]
0x1800097ff  mov     edx, 1; fCancelPendingCallbacks
0x180009804  mov     rcx, [rcx]; pti
0x180009807  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000980d  mov     rcx, [rbx+18h]; this
0x180009811  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x180009816  add     rsp, 20h
0x18000981a  pop     rbx
0x18000981b  retn
```
