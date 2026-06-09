# Private::TimerCallback::~TimerCallback(void)

- ea: `0x140065f38`
- end: `0x140065ff1`
- name: `??1TimerCallback@Private@@UEAA@XZ`
- size: `185`
- prototype: `void __fastcall(Private::TimerCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140066320`

## callees

- `0x140065f38`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x140065f6b`
- `KERNEL32!SetThreadpoolTimer` at `0x140065f6b`
- `KERNEL32!CloseThreadpoolTimer` at `0x140065f96`
- `KERNEL32!CloseThreadpoolTimer` at `0x140065f96`
- `KERNEL32!GetCurrentThreadId` at `0x140065f79`
- `KERNEL32!GetCurrentThreadId` at `0x140065f79`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140065f8c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140065f8c`

## pseudocode

```c
void __fastcall Private::TimerCallback::~TimerCallback(Private::TimerCallback *this)
{
  __int64 v2; // rbx
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)this = &Private::TimerCallback::`vftable';
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
  SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
  v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 64LL);
  if ( (_DWORD)v2 != GetCurrentThreadId() )
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
  CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  *(_QWORD *)this = &ITimerCallback::`vftable';
}

```

## disassembly

```asm
0x140065f38  mov     [rsp+arg_0], rbx
0x140065f3d  push    rdi
0x140065f3e  sub     rsp, 20h
0x140065f42  mov     rdi, rcx
0x140065f45  lea     rax, ??_7TimerCallback@Private@@6B@; const Private::TimerCallback::`vftable'
0x140065f4c  mov     [rcx], rax
0x140065f4f  mov     rcx, [rcx+8]
0x140065f53  mov     rax, [rcx]
0x140065f56  mov     rax, [rax+8]
0x140065f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065f5f  xor     r9d, r9d; msWindowLength
0x140065f62  xor     r8d, r8d; msPeriod
0x140065f65  xor     edx, edx; pftDueTime
0x140065f67  mov     rcx, [rdi+18h]; pti
0x140065f6b  call    cs:__imp_SetThreadpoolTimer
0x140065f71  mov     rbx, [rdi+8]
0x140065f75  mov     rbx, [rbx+40h]
0x140065f79  call    cs:__imp_GetCurrentThreadId
0x140065f7f  cmp     ebx, eax
0x140065f81  jz      short loc_140065F92
0x140065f83  mov     edx, 1; fCancelPendingCallbacks
0x140065f88  mov     rcx, [rdi+18h]; pti
0x140065f8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140065f92  mov     rcx, [rdi+18h]; pti
0x140065f96  call    cs:__imp_CloseThreadpoolTimer
0x140065f9c  mov     rbx, [rdi+10h]
0x140065fa0  test    rbx, rbx
0x140065fa3  jz      short loc_140065FDC
0x140065fa5  or      eax, 0FFFFFFFFh
0x140065fa8  lock xadd [rbx+8], eax
0x140065fad  cmp     eax, 1
0x140065fb0  jnz     short loc_140065FDC
0x140065fb2  mov     rax, [rbx]
0x140065fb5  mov     rcx, rbx
0x140065fb8  mov     rax, [rax]
0x140065fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065fc0  or      eax, 0FFFFFFFFh
0x140065fc3  lock xadd [rbx+0Ch], eax
0x140065fc8  cmp     eax, 1
0x140065fcb  jnz     short loc_140065FDC
0x140065fcd  mov     rax, [rbx]
0x140065fd0  mov     rcx, rbx
0x140065fd3  mov     rax, [rax+8]
0x140065fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065fdc  lea     rax, ??_7ITimerCallback@@6B@; const ITimerCallback::`vftable'
0x140065fe3  mov     [rdi], rax
0x140065fe6  mov     rbx, [rsp+28h+arg_0]
0x140065feb  add     rsp, 20h
0x140065fef  pop     rdi
0x140065ff0  retn
```
