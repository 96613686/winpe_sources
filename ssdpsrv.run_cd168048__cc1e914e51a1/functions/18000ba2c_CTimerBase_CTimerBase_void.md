# CTimerBase::~CTimerBase(void)

- ea: `0x18000ba2c`
- end: `0x18000ba9c`
- name: `??1CTimerBase@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(CTimerBase *__hidden this)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b764`
- `0x18000b8cc`
- `0x18000bc1c`
- `0x18000bfc0`
- `0x180026394`
- `0x180027cd4`
- `0x18002fef0`
- `0x180031400`
- `0x1800317d0`
- `0x180031d40`
- `0x180031d80`
- `0x180032360`
- `0x180036560`

## callees

- `0x18000683c`
- `0x18000ba2c`
- `0x18001c3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ba51`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ba64`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ba64`

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
    CTimerQueue::ReleaseHandle((CTimerQueue *)CTimerQueue::s_instance, (__int16 *)this + 16);
  }
LABEL_2:
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x18000ba2c  push    rbx
0x18000ba2e  sub     rsp, 20h
0x18000ba32  mov     rdx, [rcx+8]; Timer
0x18000ba36  lea     rax, ??_7CTimerBase@@6B@; const CTimerBase::`vftable'
0x18000ba3d  mov     [rcx], rax
0x18000ba40  mov     rbx, rcx
0x18000ba43  test    rdx, rdx
0x18000ba46  jnz     short loc_18000BA5D
0x18000ba48  lea     rcx, [rbx+28h]
0x18000ba4c  add     rsp, 20h
0x18000ba50  pop     rbx
0x18000ba51  jmp     cs:__imp_DeleteCriticalSection
0x18000ba5d  mov     rcx, [rcx+10h]; TimerQueue
0x18000ba61  xor     r8d, r8d; CompletionEvent
0x18000ba64  call    cs:__imp_DeleteTimerQueueTimer
0x18000ba6b  nop     dword ptr [rax+rax+00h]
0x18000ba70  test    eax, eax
0x18000ba72  jnz     short loc_18000BA82
0x18000ba74  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000ba79  cmp     eax, 800703E5h
0x18000ba7e  jnz     short loc_18000BA48
0x18000ba80  jmp     short loc_18000BA8A
0x18000ba82  mov     qword ptr [rbx+8], 0
0x18000ba8a  lea     rdx, [rbx+20h]; __int16 *
0x18000ba8e  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18000ba95  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x18000ba9a  jmp     short loc_18000BA48
```
