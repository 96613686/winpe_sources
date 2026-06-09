# CThreadTask::_ThreadProc(void *)

- ea: `0x180014000`
- end: `0x1800140e0`
- name: `?_ThreadProc@CThreadTask@@CAKPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180014000`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001400d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001400d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001401c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014079`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001401c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001405b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001405b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140a3`

## pseudocode

```c
__int64 __fastcall CThreadTask::_ThreadProc(PVOID Parameter)
{
  DWORD CurrentThreadId; // esi
  __int64 i; // rcx
  unsigned int v4; // edi
  __int64 j; // rdx

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&stru_18003E438);
  if ( (unsigned int)++dword_18003EFB0 <= 0x14 )
  {
    for ( i = 0; (unsigned int)i < 0x14; i = (unsigned int)(i + 1) )
    {
      if ( !*((_DWORD *)CThreadTask::_currentthreads + i) )
      {
        *((_DWORD *)CThreadTask::_currentthreads + i) = CurrentThreadId;
        break;
      }
    }
  }
  LeaveCriticalSection(&stru_18003E438);
  v4 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Parameter + 8LL))(Parameter);
  EnterCriticalSection(&stru_18003E438);
  for ( j = 0; (unsigned int)j < 0x14; j = (unsigned int)(j + 1) )
  {
    if ( CurrentThreadId == *((_DWORD *)CThreadTask::_currentthreads + j) )
    {
      *((_DWORD *)CThreadTask::_currentthreads + j) = 0;
      break;
    }
  }
  --dword_18003EFB0;
  LeaveCriticalSection(&stru_18003E438);
  *((_DWORD *)Parameter + 4) = v4;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(PVOID, __int64))Parameter)(Parameter, 1);
  return v4;
}

```

## disassembly

```asm
0x180014000  push    rbx
0x180014002  push    rsi
0x180014003  push    rdi
0x180014004  push    r14
0x180014006  sub     rsp, 28h
0x18001400a  mov     rbx, rcx
0x18001400d  call    cs:__imp_GetCurrentThreadId
0x180014013  lea     rcx, stru_18003E438; lpCriticalSection
0x18001401a  mov     esi, eax
0x18001401c  call    cs:__imp_EnterCriticalSection
0x180014022  mov     edx, cs:dword_18003EFB0
0x180014028  lea     r14, ?_currentthreads@CThreadTask@@0V?$CCurrentThreads@$0BE@@@A; CCurrentThreads<20> CThreadTask::_currentthreads
0x18001402f  inc     edx
0x180014031  mov     cs:dword_18003EFB0, edx
0x180014037  cmp     edx, 14h
0x18001403a  ja      short loc_180014054
0x18001403c  xor     ecx, ecx
0x18001403e  cmp     ecx, 14h
0x180014041  jnb     short loc_180014054
0x180014043  cmp     dword ptr [r14+rcx*4], 0
0x180014048  lea     rdx, [r14+rcx*4]
0x18001404c  jz      short loc_180014052
0x18001404e  inc     ecx
0x180014050  jmp     short loc_18001403E
0x180014052  mov     [rdx], esi
0x180014054  lea     rcx, stru_18003E438; lpCriticalSection
0x18001405b  call    cs:__imp_LeaveCriticalSection
0x180014061  mov     rax, [rbx]
0x180014064  mov     rcx, rbx
0x180014067  mov     rax, [rax+8]
0x18001406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014070  lea     rcx, stru_18003E438; lpCriticalSection
0x180014077  mov     edi, eax
0x180014079  call    cs:__imp_EnterCriticalSection
0x18001407f  xor     edx, edx
0x180014081  cmp     edx, 14h
0x180014084  jnb     short loc_180014096
0x180014086  cmp     esi, [r14+rdx*4]
0x18001408a  lea     rax, [r14+rdx*4]
0x18001408e  jnz     short loc_1800140C7
0x180014090  mov     dword ptr [rax], 0
0x180014096  dec     cs:dword_18003EFB0
0x18001409c  lea     rcx, stru_18003E438; lpCriticalSection
0x1800140a3  call    cs:__imp_LeaveCriticalSection
0x1800140a9  mov     eax, 0FFFFFFFFh
0x1800140ae  mov     [rbx+10h], edi
0x1800140b1  lock xadd [rbx+8], eax
0x1800140b6  cmp     eax, 1
0x1800140b9  jz      short loc_1800140CB
0x1800140bb  mov     eax, edi
0x1800140bd  add     rsp, 28h
0x1800140c1  pop     r14
0x1800140c3  pop     rdi
0x1800140c4  pop     rsi
0x1800140c5  pop     rbx
0x1800140c6  retn
0x1800140c7  inc     edx
0x1800140c9  jmp     short loc_180014081
0x1800140cb  mov     rax, [rbx]
0x1800140ce  mov     edx, 1
0x1800140d3  mov     rcx, rbx
0x1800140d6  mov     rax, [rax]
0x1800140d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140de  jmp     short loc_1800140BB
```
