# CTimer::~CTimer(void)

- ea: `0x18006ae2c`
- end: `0x18006ae6a`
- name: `??1CTimer@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006adf0`

## callees

- `0x18001ce3c`
- `0x18006ae70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ae57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ae57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae3f`

## pseudocode

```c
void __fastcall CTimer::~CTimer(CTimer *this)
{
  DWORD CurrentThreadId; // eax

  *(_QWORD *)this = &CTimer::`vftable';
  CurrentThreadId = GetCurrentThreadId();
  CTimer::_DestroyThreadPoolTimer(this, CurrentThreadId != *((_DWORD *)this + 18));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CBaseObject::~CBaseObject(this);
}

```

## disassembly

```asm
0x18006ae2c  push    rbx
0x18006ae2e  sub     rsp, 20h
0x18006ae32  lea     rax, ??_7CTimer@@6B@; const CTimer::`vftable'
0x18006ae39  mov     rbx, rcx
0x18006ae3c  mov     [rcx], rax
0x18006ae3f  call    cs:__imp_GetCurrentThreadId
0x18006ae45  cmp     eax, [rbx+48h]
0x18006ae48  mov     rcx, rbx; this
0x18006ae4b  setnz   dl; bool
0x18006ae4e  call    ?_DestroyThreadPoolTimer@CTimer@@AEAAX_N@Z; CTimer::_DestroyThreadPoolTimer(bool)
0x18006ae53  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006ae57  call    cs:__imp_DeleteCriticalSection
0x18006ae5d  mov     rcx, rbx; this
0x18006ae60  add     rsp, 20h
0x18006ae64  pop     rbx
0x18006ae65  jmp     ??1CBaseObject@@UEAA@XZ; CBaseObject::~CBaseObject(void)
```
