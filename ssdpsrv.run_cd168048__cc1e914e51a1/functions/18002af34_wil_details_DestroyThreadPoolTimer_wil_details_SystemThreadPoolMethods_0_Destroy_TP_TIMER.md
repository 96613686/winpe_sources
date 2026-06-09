# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002af34`
- end: `0x18002af79`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180024bb4`
- `0x180024c40`
- `0x180024c60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002af59`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002af59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002af6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002af45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002af45`

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
0x18002af34  push    rbx
0x18002af36  sub     rsp, 20h
0x18002af3a  xor     r9d, r9d; msWindowLength
0x18002af3d  xor     r8d, r8d; msPeriod
0x18002af40  xor     edx, edx; pftDueTime
0x18002af42  mov     rbx, rcx
0x18002af45  call    cs:__imp_SetThreadpoolTimer
0x18002af4c  nop     dword ptr [rax+rax+00h]
0x18002af51  mov     edx, 1; fCancelPendingCallbacks
0x18002af56  mov     rcx, rbx; pti
0x18002af59  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002af60  nop     dword ptr [rax+rax+00h]
0x18002af65  mov     rcx, rbx
0x18002af68  add     rsp, 20h
0x18002af6c  pop     rbx
0x18002af6d  jmp     cs:__imp_CloseThreadpoolTimer
```
