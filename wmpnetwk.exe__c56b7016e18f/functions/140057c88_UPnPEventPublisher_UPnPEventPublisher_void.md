# UPnPEventPublisher::~UPnPEventPublisher(void)

- ea: `0x140057c88`
- end: `0x140057d95`
- name: `??1UPnPEventPublisher@@UEAA@XZ`
- size: `269`
- prototype: `void __fastcall(UPnPEventPublisher *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140057da0`
- `0x140058208`
- `0x14005a1fc`
- `0x14005f1e8`

## callees

- `0x140041874`
- `0x140057c88`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140057cb4`
- `KERNEL32!EnterCriticalSection` at `0x140057cb4`
- `KERNEL32!LeaveCriticalSection` at `0x140057d46`
- `KERNEL32!LeaveCriticalSection` at `0x140057d46`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140057d5a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140057d5a`
- `KERNEL32!DeleteTimerQueueEx` at `0x140057d77`
- `KERNEL32!DeleteTimerQueueEx` at `0x140057d77`
- `KERNEL32!DeleteCriticalSection` at `0x140057d8e`

## pseudocode

```c
void __fastcall UPnPEventPublisher::~UPnPEventPublisher(UPnPEventPublisher *this)
{
  __int64 v2; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  volatile __int64 *v4; // rcx
  __int64 v5; // rcx
  void *v6; // r15
  TimerCallbackContext *v7; // r14
  void *v8; // rdi
  unsigned int v9; // edx

  *(_QWORD *)this = &UPnPEventPublisher::`vftable';
  v2 = 0;
  *((_DWORD *)this + 2) = 1;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_QWORD *)this + 15) )
  {
    v4 = (volatile __int64 *)*((_QWORD *)this + 17);
    if ( v4 )
    {
      if ( !_InterlockedExchange64(v4, 0) )
        v2 = -1;
    }
  }
  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  v7 = (TimerCallbackContext *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  v8 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = -1;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 26) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 19) = 0;
  LeaveCriticalSection(v3);
  if ( v6 )
    DeleteTimerQueueTimer(v8, v6, (HANDLE)v2);
  if ( v7 )
    TimerCallbackContext::`scalar deleting destructor'(v7, v9);
  if ( v8 != (void *)-1LL )
    DeleteTimerQueueEx(v8, 0);
  DeleteCriticalSection(v3);
}

```

## disassembly

```asm
0x140057c88  push    rbx
0x140057c8a  push    rbp
0x140057c8b  push    rsi
0x140057c8c  push    rdi
0x140057c8d  push    r13
0x140057c8f  push    r14
0x140057c91  push    r15
0x140057c93  sub     rsp, 20h
0x140057c97  mov     rbx, rcx
0x140057c9a  lea     rax, ??_7UPnPEventPublisher@@6B@; const UPnPEventPublisher::`vftable'
0x140057ca1  mov     [rcx], rax
0x140057ca4  xor     esi, esi
0x140057ca6  mov     dword ptr [rcx+8], 1
0x140057cad  lea     rbp, [rcx+40h]
0x140057cb1  mov     rcx, rbp; lpCriticalSection
0x140057cb4  call    cs:__imp_EnterCriticalSection
0x140057cba  or      r13, 0FFFFFFFFFFFFFFFFh
0x140057cbe  cmp     [rbx+78h], rsi
0x140057cc2  jz      short loc_140057CDC
0x140057cc4  mov     rcx, [rbx+88h]
0x140057ccb  test    rcx, rcx
0x140057cce  jz      short loc_140057CDC
0x140057cd0  xor     eax, eax
0x140057cd2  xchg    rax, [rcx]
0x140057cd5  test    rax, rax
0x140057cd8  cmovz   rsi, r13
0x140057cdc  mov     rcx, [rbx+10h]
0x140057ce0  test    rcx, rcx
0x140057ce3  jz      short loc_140057CF9
0x140057ce5  mov     rax, [rcx]
0x140057ce8  mov     rax, [rax+10h]
0x140057cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057cf1  mov     qword ptr [rbx+10h], 0
0x140057cf9  mov     r15, [rbx+78h]
0x140057cfd  mov     qword ptr [rbx+78h], 0
0x140057d05  mov     r14, [rbx+88h]
0x140057d0c  mov     qword ptr [rbx+88h], 0
0x140057d17  mov     rdi, [rbx+70h]
0x140057d1b  mov     [rbx+70h], r13
0x140057d1f  mov     dword ptr [rbx+38h], 0
0x140057d26  mov     dword ptr [rbx+68h], 0
0x140057d2d  xorps   xmm0, xmm0
0x140057d30  movups  xmmword ptr [rbx+18h], xmm0
0x140057d34  movups  xmmword ptr [rbx+28h], xmm0
0x140057d38  mov     qword ptr [rbx+98h], 0
0x140057d43  mov     rcx, rbp; lpCriticalSection
0x140057d46  call    cs:__imp_LeaveCriticalSection
0x140057d4c  test    r15, r15
0x140057d4f  jz      short loc_140057D60
0x140057d51  mov     r8, rsi; CompletionEvent
0x140057d54  mov     rdx, r15; Timer
0x140057d57  mov     rcx, rdi; TimerQueue
0x140057d5a  call    cs:__imp_DeleteTimerQueueTimer
0x140057d60  test    r14, r14
0x140057d63  jz      short loc_140057D6D
0x140057d65  mov     rcx, r14; this
0x140057d68  call    ??_GTimerCallbackContext@@QEAAPEAXI@Z; TimerCallbackContext::`scalar deleting destructor'(uint)
0x140057d6d  cmp     rdi, r13
0x140057d70  jz      short loc_140057D7D
0x140057d72  xor     edx, edx; CompletionEvent
0x140057d74  mov     rcx, rdi; TimerQueue
0x140057d77  call    cs:__imp_DeleteTimerQueueEx
0x140057d7d  mov     rcx, rbp
0x140057d80  add     rsp, 20h
0x140057d84  pop     r15
0x140057d86  pop     r14
0x140057d88  pop     r13
0x140057d8a  pop     rdi
0x140057d8b  pop     rsi
0x140057d8c  pop     rbp
0x140057d8d  pop     rbx
0x140057d8e  jmp     cs:__imp_DeleteCriticalSection
```
