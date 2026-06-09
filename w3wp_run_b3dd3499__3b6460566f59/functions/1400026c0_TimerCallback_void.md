# TimerCallback(void)

- ea: `0x1400026c0`
- end: `0x140002718`
- name: `?TimerCallback@@YAXXZ`
- size: `88`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400026c0`

## import_xrefs

- `msvcrt!printf` at `0x1400026e4`
- `msvcrt!printf` at `0x1400026e4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000270c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000270c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400026f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400026f6`

## pseudocode

```c
void __fastcall TimerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  if ( _InterlockedCompareExchange(&g_lShuttingDown, 1, 0) != 1 )
  {
    printf("Process is terminated due to shutdown timout (%d seconds) \n", g_dwShutDownTimeout);
    if ( g_pTimer )
    {
      CloseThreadpoolTimer(g_pTimer);
      g_pTimer = 0;
    }
    ExitProcess(0x800705B4);
  }
}

```

## disassembly

```asm
0x1400026c0  sub     rsp, 28h
0x1400026c4  mov     ecx, 1
0x1400026c9  xor     eax, eax
0x1400026cb  lock cmpxchg cs:?g_lShuttingDown@@3JC, ecx; long volatile g_lShuttingDown
0x1400026d3  cmp     eax, ecx
0x1400026d5  jz      short loc_140002713
0x1400026d7  mov     edx, cs:?g_dwShutDownTimeout@@3KA; ulong g_dwShutDownTimeout
0x1400026dd  lea     rcx, aProcessIsTermi; "Process is terminated due to shutdown t"...
0x1400026e4  call    cs:__imp_printf
0x1400026ea  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x1400026f1  test    rcx, rcx
0x1400026f4  jz      short loc_140002707
0x1400026f6  call    cs:__imp_CloseThreadpoolTimer
0x1400026fc  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_pTimer
0x140002707  mov     ecx, 800705B4h; uExitCode
0x14000270c  call    cs:__imp_ExitProcess
0x140002713  add     rsp, 28h
0x140002717  retn
```
