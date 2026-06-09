# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016234`
- end: `0x180016279`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015ce4`
- `0x1800195b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016245`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016245`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001626d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016259`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016259`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180016234  push    rbx
0x180016236  sub     rsp, 20h
0x18001623a  xor     r9d, r9d; msWindowLength
0x18001623d  xor     r8d, r8d; msPeriod
0x180016240  xor     edx, edx; pftDueTime
0x180016242  mov     rbx, rcx
0x180016245  call    cs:__imp_SetThreadpoolTimer
0x18001624c  nop     dword ptr [rax+rax+00h]
0x180016251  mov     edx, 1; fCancelPendingCallbacks
0x180016256  mov     rcx, rbx; pti
0x180016259  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016260  nop     dword ptr [rax+rax+00h]
0x180016265  mov     rcx, rbx
0x180016268  add     rsp, 20h
0x18001626c  pop     rbx
0x18001626d  jmp     cs:__imp_CloseThreadpoolTimer
```
