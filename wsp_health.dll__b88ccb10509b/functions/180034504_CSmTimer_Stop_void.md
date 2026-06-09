# CSmTimer::Stop(void)

- ea: `0x180034504`
- end: `0x180034558`
- name: `?Stop@CSmTimer@@QEAAXXZ`
- size: `84`
- prototype: `void __fastcall(CSmTimer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800340cc`
- `0x180034224`

## callees

- `0x180034504`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034518`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034518`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003453f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003453f`

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
0x180034504  mov     [rsp+arg_0], rbx
0x180034509  push    rdi
0x18003450a  sub     rsp, 20h
0x18003450e  lea     rdi, [rcx+8]
0x180034512  mov     rbx, rcx
0x180034515  mov     rcx, rdi; lpPerformanceCount
0x180034518  call    cs:__imp_QueryPerformanceCounter
0x18003451e  test    eax, eax
0x180034520  jz      short loc_18003452A
0x180034522  mov     rax, [rbx]
0x180034525  cmp     [rdi], rax
0x180034528  jnb     short loc_180034530
0x18003452a  mov     rax, [rbx]
0x18003452d  mov     [rdi], rax
0x180034530  mov     rdx, [rbx+18h]; Timer
0x180034534  test    rdx, rdx
0x180034537  jz      short loc_18003454D
0x180034539  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003453d  xor     ecx, ecx; TimerQueue
0x18003453f  call    cs:__imp_DeleteTimerQueueTimer
0x180034545  mov     qword ptr [rbx+18h], 0
0x18003454d  mov     rbx, [rsp+28h+arg_0]
0x180034552  add     rsp, 20h
0x180034556  pop     rdi
0x180034557  retn
```
