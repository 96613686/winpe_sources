# Private::WaitCallback::~WaitCallback(void)

- ea: `0x140065ff8`
- end: `0x1400660ce`
- name: `??1WaitCallback@Private@@QEAA@XZ`
- size: `214`
- prototype: `void __fastcall(Private::WaitCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140067260`

## callees

- `0x140065ff8`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CloseThreadpoolWait` at `0x14006603d`
- `KERNEL32!CloseThreadpoolWait` at `0x14006603d`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x140066033`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x140066033`
- `KERNEL32!SetThreadpoolWait` at `0x140066013`
- `KERNEL32!SetThreadpoolWait` at `0x140066013`
- `KERNEL32!GetCurrentThreadId` at `0x140066020`
- `KERNEL32!GetCurrentThreadId` at `0x140066020`

## pseudocode

```c
void __fastcall Private::WaitCallback::~WaitCallback(PTP_WAIT *this)
{
  __int64 v2; // rbx
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx

  SetThreadpoolWait(this[4], 0, 0);
  v2 = *((_QWORD *)*this + 8);
  if ( (_DWORD)v2 != GetCurrentThreadId() )
    WaitForThreadpoolWaitCallbacks(this[4], 1);
  CloseThreadpoolWait(this[4]);
  v3 = (volatile signed __int32 *)this[3];
  if ( v3 )
  {
    if ( !_InterlockedDecrement(v3 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( !_InterlockedDecrement(v3 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (volatile signed __int32 *)this[1];
  if ( v4 && !_InterlockedDecrement(v4 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x140065ff8  mov     [rsp+arg_0], rbx
0x140065ffd  mov     [rsp+arg_8], rsi
0x140066002  push    rdi
0x140066003  sub     rsp, 20h
0x140066007  mov     rdi, rcx
0x14006600a  xor     r8d, r8d; pftTimeout
0x14006600d  mov     rcx, [rcx+20h]; pwa
0x140066011  xor     edx, edx; h
0x140066013  call    cs:__imp_SetThreadpoolWait
0x140066019  mov     rbx, [rdi]
0x14006601c  mov     rbx, [rbx+40h]
0x140066020  call    cs:__imp_GetCurrentThreadId
0x140066026  cmp     ebx, eax
0x140066028  jz      short loc_140066039
0x14006602a  mov     rcx, [rdi+20h]; pwa
0x14006602e  mov     edx, 1; fCancelPendingCallbacks
0x140066033  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140066039  mov     rcx, [rdi+20h]; pwa
0x14006603d  call    cs:__imp_CloseThreadpoolWait
0x140066043  mov     rbx, [rdi+18h]
0x140066047  or      esi, 0FFFFFFFFh
0x14006604a  test    rbx, rbx
0x14006604d  jz      short loc_140066082
0x14006604f  mov     eax, esi
0x140066051  lock xadd [rbx+8], eax
0x140066056  add     eax, esi
0x140066058  jnz     short loc_140066082
0x14006605a  mov     rax, [rbx]
0x14006605d  mov     rcx, rbx
0x140066060  mov     rax, [rax]
0x140066063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066068  mov     eax, esi
0x14006606a  lock xadd [rbx+0Ch], eax
0x14006606f  add     eax, esi
0x140066071  jnz     short loc_140066082
0x140066073  mov     rax, [rbx]
0x140066076  mov     rcx, rbx
0x140066079  mov     rax, [rax+8]
0x14006607d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066082  mov     rbx, [rdi+8]
0x140066086  test    rbx, rbx
0x140066089  jz      short loc_1400660BE
0x14006608b  mov     eax, esi
0x14006608d  lock xadd [rbx+8], eax
0x140066092  add     eax, esi
0x140066094  jnz     short loc_1400660BE
0x140066096  mov     rax, [rbx]
0x140066099  mov     rcx, rbx
0x14006609c  mov     rax, [rax]
0x14006609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400660a4  mov     eax, esi
0x1400660a6  lock xadd [rbx+0Ch], eax
0x1400660ab  add     eax, esi
0x1400660ad  jnz     short loc_1400660BE
0x1400660af  mov     rax, [rbx]
0x1400660b2  mov     rcx, rbx
0x1400660b5  mov     rax, [rax+8]
0x1400660b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400660be  mov     rbx, [rsp+28h+arg_0]
0x1400660c3  mov     rsi, [rsp+28h+arg_8]
0x1400660c8  add     rsp, 20h
0x1400660cc  pop     rdi
0x1400660cd  retn
```
