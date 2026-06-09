# CSmTimer::~CSmTimer(void)

- ea: `0x180033e24`
- end: `0x180033e41`
- name: `??1CSmTimer@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(CSmTimer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800340cc`
- `0x180034224`
- `0x180086bbd`
- `0x180086bcf`

## callees

- `0x180033e24`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033e36`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033e36`

## pseudocode

```c
void __fastcall CSmTimer::~CSmTimer(CSmTimer *this)
{
  void *v1; // rdx

  v1 = (void *)*((_QWORD *)this + 3);
  if ( v1 )
    DeleteTimerQueueTimer(0, v1, 0);
}

```

## disassembly

```asm
0x180033e24  sub     rsp, 28h
0x180033e28  mov     rdx, [rcx+18h]; Timer
0x180033e2c  test    rdx, rdx
0x180033e2f  jz      short loc_180033E3C
0x180033e31  xor     r8d, r8d; CompletionEvent
0x180033e34  xor     ecx, ecx; TimerQueue
0x180033e36  call    cs:__imp_DeleteTimerQueueTimer
0x180033e3c  add     rsp, 28h
0x180033e40  retn
```
