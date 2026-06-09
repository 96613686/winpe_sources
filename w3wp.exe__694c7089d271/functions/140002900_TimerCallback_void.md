# TimerCallback(void)

- ea: `0x140002900`
- end: `0x14000296b`
- name: `?TimerCallback@@YAXXZ`
- size: `107`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002900`

## import_xrefs

- `msvcrt!printf` at `0x140002924`
- `msvcrt!printf` at `0x140002924`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002958`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002958`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000293c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000293c`

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
0x140002900  sub     rsp, 28h
0x140002904  mov     ecx, 1
0x140002909  xor     eax, eax
0x14000290b  lock cmpxchg cs:?g_lShuttingDown@@3JC, ecx; long volatile g_lShuttingDown
0x140002913  cmp     eax, ecx
0x140002915  jz      short loc_140002965
0x140002917  mov     edx, cs:?g_dwShutDownTimeout@@3KA; ulong g_dwShutDownTimeout
0x14000291d  lea     rcx, aProcessIsTermi; "Process is terminated due to shutdown t"...
0x140002924  call    cs:__imp_printf
0x14000292b  nop     dword ptr [rax+rax+00h]
0x140002930  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x140002937  test    rcx, rcx
0x14000293a  jz      short loc_140002953
0x14000293c  call    cs:__imp_CloseThreadpoolTimer
0x140002943  nop     dword ptr [rax+rax+00h]
0x140002948  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_pTimer
0x140002953  mov     ecx, 800705B4h; uExitCode
0x140002958  call    cs:__imp_ExitProcess
0x140002965  add     rsp, 28h
0x140002969  retn
```
