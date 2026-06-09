# CTimerBase::~CTimerBase(void)

- ea: `0x18000a358`
- end: `0x18000a3bd`
- name: `??1CTimerBase@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CTimerBase *__hidden this)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0f4`
- `0x18000a220`
- `0x18000a498`
- `0x18000a64c`
- `0x18002487c`
- `0x180025f5c`
- `0x18002ddf0`
- `0x18002f190`
- `0x18002f510`
- `0x18002fa40`
- `0x18002fa80`
- `0x180030010`
- `0x180033ac0`

## callees

- `0x18000554c`
- `0x18000a358`
- `0x18001afe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a37d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000a38b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000a38b`

## pseudocode

```c
void __fastcall CTimerBase::~CTimerBase(CTimerBase *this)
{
  void *v1; // rdx

  v1 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = &CTimerBase::`vftable';
  if ( v1 )
  {
    if ( DeleteTimerQueueTimer(*((HANDLE *)this + 2), v1, 0) )
    {
      *((_QWORD *)this + 1) = 0;
    }
    else if ( (unsigned int)HrFromLastWin32Error() != -2147023899 )
    {
      goto LABEL_2;
    }
    CTimerQueue::ReleaseHandle((CTimerQueue *)&CTimerQueue::s_instance, (__int16 *)this + 16);
  }
LABEL_2:
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x18000a358  push    rbx
0x18000a35a  sub     rsp, 20h
0x18000a35e  mov     rdx, [rcx+8]; Timer
0x18000a362  lea     rax, ??_7CTimerBase@@6B@; const CTimerBase::`vftable'
0x18000a369  mov     [rcx], rax
0x18000a36c  mov     rbx, rcx
0x18000a36f  test    rdx, rdx
0x18000a372  jnz     short loc_18000A384
0x18000a374  lea     rcx, [rbx+28h]
0x18000a378  add     rsp, 20h
0x18000a37c  pop     rbx
0x18000a37d  jmp     cs:__imp_DeleteCriticalSection
0x18000a384  mov     rcx, [rcx+10h]; TimerQueue
0x18000a388  xor     r8d, r8d; CompletionEvent
0x18000a38b  call    cs:__imp_DeleteTimerQueueTimer
0x18000a391  test    eax, eax
0x18000a393  jnz     short loc_18000A3A3
0x18000a395  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000a39a  cmp     eax, 800703E5h
0x18000a39f  jnz     short loc_18000A374
0x18000a3a1  jmp     short loc_18000A3AB
0x18000a3a3  mov     qword ptr [rbx+8], 0
0x18000a3ab  lea     rdx, [rbx+20h]; __int16 *
0x18000a3af  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18000a3b6  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x18000a3bb  jmp     short loc_18000A374
```
