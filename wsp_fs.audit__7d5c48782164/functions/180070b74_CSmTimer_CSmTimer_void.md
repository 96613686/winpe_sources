# CSmTimer::~CSmTimer(void)

- ea: `0x180070b74`
- end: `0x180070b98`
- name: `??1CSmTimer@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CSmTimer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180072394`

## callees

- `0x180070b74`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180070b86`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180070b86`

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
0x180070b74  sub     rsp, 28h
0x180070b78  mov     rdx, [rcx+18h]; Timer
0x180070b7c  test    rdx, rdx
0x180070b7f  jz      short loc_180070B92
0x180070b81  xor     r8d, r8d; CompletionEvent
0x180070b84  xor     ecx, ecx; TimerQueue
0x180070b86  call    cs:__imp_DeleteTimerQueueTimer
0x180070b8d  nop     dword ptr [rax+rax+00h]
0x180070b92  add     rsp, 28h
0x180070b96  retn
```
