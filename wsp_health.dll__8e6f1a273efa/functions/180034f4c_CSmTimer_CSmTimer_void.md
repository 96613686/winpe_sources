# CSmTimer::~CSmTimer(void)

- ea: `0x180034f4c`
- end: `0x180034f70`
- name: `??1CSmTimer@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CSmTimer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800351fc`
- `0x180035354`
- `0x180089024`
- `0x180089036`

## callees

- `0x180034f4c`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180034f5e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180034f5e`

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
0x180034f4c  sub     rsp, 28h
0x180034f50  mov     rdx, [rcx+18h]; Timer
0x180034f54  test    rdx, rdx
0x180034f57  jz      short loc_180034F6A
0x180034f59  xor     r8d, r8d; CompletionEvent
0x180034f5c  xor     ecx, ecx; TimerQueue
0x180034f5e  call    cs:__imp_DeleteTimerQueueTimer
0x180034f65  nop     dword ptr [rax+rax+00h]
0x180034f6a  add     rsp, 28h
0x180034f6e  retn
```
