# CThread::Stop(void)

- ea: `0x180039404`
- end: `0x180039452`
- name: `?Stop@CThread@@AEAAXXZ`
- size: `78`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800393e8`
- `0x180052388`

## callees

- `0x180039404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003943c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039425`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003943c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180039446`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180039446`

## pseudocode

```c
void __fastcall CThread::Stop(CThread *this)
{
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 3, 2) == 2 )
  {
    SetEvent(*((HANDLE *)this + 14));
  }
  else if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 3, 1) == 1 )
  {
    SetEvent(*((HANDLE *)this + 14));
    ResumeThread(*((HANDLE *)this + 1));
  }
}

```

## disassembly

```asm
0x180039404  push    rbx
0x180039406  sub     rsp, 20h
0x18003940a  mov     rbx, rcx
0x18003940d  mov     ecx, 3
0x180039412  lea     eax, [rcx-1]
0x180039415  lock cmpxchg [rbx+68h], ecx
0x18003941a  jnz     short loc_18003942C
0x18003941c  mov     rcx, [rbx+70h]
0x180039420  add     rsp, 20h
0x180039424  pop     rbx
0x180039425  jmp     cs:__imp_SetEvent
0x18003942c  mov     eax, 1
0x180039431  lock cmpxchg [rbx+68h], ecx
0x180039436  jnz     short loc_18003944C
0x180039438  mov     rcx, [rbx+70h]; hEvent
0x18003943c  call    cs:__imp_SetEvent
0x180039442  mov     rcx, [rbx+8]; hThread
0x180039446  call    cs:__imp_ResumeThread
0x18003944c  add     rsp, 20h
0x180039450  pop     rbx
0x180039451  retn
```
