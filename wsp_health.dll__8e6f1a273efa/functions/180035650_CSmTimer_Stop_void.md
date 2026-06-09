# CSmTimer::Stop(void)

- ea: `0x180035650`
- end: `0x1800356b1`
- name: `?Stop@CSmTimer@@QEAAXXZ`
- size: `97`
- prototype: `void __fastcall(CSmTimer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800351fc`
- `0x180035354`

## callees

- `0x180035650`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035664`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035664`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180035691`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180035691`

## pseudocode

```c
void __fastcall CSmTimer::Stop(LARGE_INTEGER *this)
{
  LARGE_INTEGER *v1; // rdi
  void *QuadPart; // rdx

  v1 = this + 1;
  if ( !QueryPerformanceCounter(this + 1) || v1->QuadPart < (unsigned __int64)this->QuadPart )
    *v1 = *this;
  QuadPart = (void *)this[3].QuadPart;
  if ( QuadPart )
  {
    DeleteTimerQueueTimer(0, QuadPart, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    this[3].QuadPart = 0;
  }
}

```

## disassembly

```asm
0x180035650  mov     [rsp+arg_0], rbx
0x180035655  push    rdi
0x180035656  sub     rsp, 20h
0x18003565a  lea     rdi, [rcx+8]
0x18003565e  mov     rbx, rcx
0x180035661  mov     rcx, rdi; lpPerformanceCount
0x180035664  call    cs:__imp_QueryPerformanceCounter
0x18003566b  nop     dword ptr [rax+rax+00h]
0x180035670  test    eax, eax
0x180035672  jz      short loc_18003567C
0x180035674  mov     rax, [rbx]
0x180035677  cmp     [rdi], rax
0x18003567a  jnb     short loc_180035682
0x18003567c  mov     rax, [rbx]
0x18003567f  mov     [rdi], rax
0x180035682  mov     rdx, [rbx+18h]; Timer
0x180035686  test    rdx, rdx
0x180035689  jz      short loc_1800356A5
0x18003568b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003568f  xor     ecx, ecx; TimerQueue
0x180035691  call    cs:__imp_DeleteTimerQueueTimer
0x180035698  nop     dword ptr [rax+rax+00h]
0x18003569d  mov     qword ptr [rbx+18h], 0
0x1800356a5  mov     rbx, [rsp+28h+arg_0]
0x1800356aa  add     rsp, 20h
0x1800356ae  pop     rdi
0x1800356af  retn
```
