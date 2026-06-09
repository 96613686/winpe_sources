# CThreadPool::Close(void)

- ea: `0x1800357f0`
- end: `0x180035881`
- name: `?Close@CThreadPool@@QEAAXXZ`
- size: `145`
- prototype: `void __fastcall(CThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800340ec`

## callees

- `0x1800357f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035827`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035827`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035838`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035838`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035811`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035811`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003585a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003585a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180035869`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180035869`

## pseudocode

```c
void __fastcall CThreadPool::Close(CThreadPool *this)
{
  __int64 i; // rbx
  struct _TP_TIMER *v3; // rcx

  for ( i = 0; i != 3; ++i )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + i + 10);
    if ( v3 )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + i + 10), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)this + i + 10));
    }
  }
  if ( *(_QWORD *)this )
  {
    CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)this, 0, 0);
    CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)this);
  }
}

```

## disassembly

```asm
0x1800357f0  mov     [rsp+arg_0], rbx
0x1800357f5  push    rdi
0x1800357f6  sub     rsp, 20h
0x1800357fa  mov     rdi, rcx
0x1800357fd  xor     ebx, ebx
0x1800357ff  mov     rcx, [rdi+rbx*8+50h]; pti
0x180035804  test    rcx, rcx
0x180035807  jz      short loc_180035844
0x180035809  xor     r9d, r9d; msWindowLength
0x18003580c  xor     r8d, r8d; msPeriod
0x18003580f  xor     edx, edx; pftDueTime
0x180035811  call    cs:__imp_SetThreadpoolTimer
0x180035818  nop     dword ptr [rax+rax+00h]
0x18003581d  mov     rcx, [rdi+rbx*8+50h]; pti
0x180035822  mov     edx, 1; fCancelPendingCallbacks
0x180035827  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003582e  nop     dword ptr [rax+rax+00h]
0x180035833  mov     rcx, [rdi+rbx*8+50h]; pti
0x180035838  call    cs:__imp_CloseThreadpoolTimer
0x18003583f  nop     dword ptr [rax+rax+00h]
0x180035844  inc     rbx
0x180035847  cmp     rbx, 3
0x18003584b  jnz     short loc_1800357FF
0x18003584d  mov     rcx, [rdi]; ptpcg
0x180035850  test    rcx, rcx
0x180035853  jz      short loc_180035875
0x180035855  xor     r8d, r8d; pvCleanupContext
0x180035858  xor     edx, edx; fCancelPendingCallbacks
0x18003585a  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180035861  nop     dword ptr [rax+rax+00h]
0x180035866  mov     rcx, [rdi]; ptpcg
0x180035869  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180035870  nop     dword ptr [rax+rax+00h]
0x180035875  mov     rbx, [rsp+28h+arg_0]
0x18003587a  add     rsp, 20h
0x18003587e  pop     rdi
0x18003587f  retn
```
