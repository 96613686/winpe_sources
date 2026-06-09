# std::unique_ptr<_TP_WAIT,sync_q<etw_event>::tpwait_deleter_t>::~unique_ptr<_TP_WAIT,sync_q<etw_event>::tpwait_deleter_t>(void)

- ea: `0x180049590`
- end: `0x1800495c9`
- name: `??1?$unique_ptr@U_TP_WAIT@@Utpwait_deleter_t@?$sync_q@Uetw_event@@@@@std@@QEAA@XZ`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180097333`

## callees

- `0x180049590`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800495a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800495a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800495bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800495bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800495b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800495b4`

## pseudocode

```c
void __fastcall std::unique_ptr<_TP_WAIT,sync_q<etw_event>::tpwait_deleter_t>::~unique_ptr<_TP_WAIT,sync_q<etw_event>::tpwait_deleter_t>(
        PTP_WAIT *a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolWait(*a1, 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
}

```

## disassembly

```asm
0x180049590  push    rbx
0x180049592  sub     rsp, 20h
0x180049596  mov     rbx, [rcx]
0x180049599  test    rbx, rbx
0x18004959c  jz      short loc_1800495C3
0x18004959e  xor     r8d, r8d; pftTimeout
0x1800495a1  xor     edx, edx; h
0x1800495a3  mov     rcx, rbx; pwa
0x1800495a6  call    cs:__imp_SetThreadpoolWait
0x1800495ac  mov     edx, 1; fCancelPendingCallbacks
0x1800495b1  mov     rcx, rbx; pwa
0x1800495b4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800495ba  mov     rcx, rbx; pwa
0x1800495bd  call    cs:__imp_CloseThreadpoolWait
0x1800495c3  add     rsp, 20h
0x1800495c7  pop     rbx
0x1800495c8  retn
```
