# CThreadTask::_CallDoStuff(void)

- ea: `0x1800149a0`
- end: `0x180014a66`
- name: `?_CallDoStuff@CThreadTask@@AEAAJXZ`
- size: `198`
- prototype: `__int64 __fastcall(CThreadTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180020e60`
- `0x180023560`

## callees

- `0x1800149a0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800149b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800149b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a49`

## pseudocode

```c
__int64 __fastcall CThreadTask::_CallDoStuff(CThreadTask *this)
{
  DWORD CurrentThreadId; // ebx
  __int64 i; // rcx
  unsigned int v4; // edi
  __int64 j; // r8

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
  v4 = (*(__int64 (__fastcall **)(CThreadTask *))(*(_QWORD *)this + 8LL))(this);
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
  return v4;
}

```

## disassembly

```asm
0x1800149a0  mov     [rsp+arg_0], rbx
0x1800149a5  mov     [rsp+arg_8], rsi
0x1800149aa  push    rdi
0x1800149ab  sub     rsp, 20h
0x1800149af  mov     rdi, rcx
0x1800149b2  call    cs:__imp_GetCurrentThreadId
0x1800149b8  lea     rcx, stru_18003E438; lpCriticalSection
0x1800149bf  mov     ebx, eax
0x1800149c1  call    cs:__imp_EnterCriticalSection
0x1800149c7  mov     edx, cs:dword_18003EFB0
0x1800149cd  lea     rsi, ?_currentthreads@CThreadTask@@0V?$CCurrentThreads@$0BE@@@A; CCurrentThreads<20> CThreadTask::_currentthreads
0x1800149d4  inc     edx
0x1800149d6  mov     cs:dword_18003EFB0, edx
0x1800149dc  cmp     edx, 14h
0x1800149df  ja      short loc_1800149F8
0x1800149e1  xor     ecx, ecx
0x1800149e3  cmp     ecx, 14h
0x1800149e6  jnb     short loc_1800149F8
0x1800149e8  cmp     dword ptr [rsi+rcx*4], 0
0x1800149ec  lea     rdx, [rsi+rcx*4]
0x1800149f0  jz      short loc_1800149F6
0x1800149f2  inc     ecx
0x1800149f4  jmp     short loc_1800149E3
0x1800149f6  mov     [rdx], ebx
0x1800149f8  lea     rcx, stru_18003E438; lpCriticalSection
0x1800149ff  call    cs:__imp_LeaveCriticalSection
0x180014a05  mov     rax, [rdi]
0x180014a08  mov     rcx, rdi
0x180014a0b  mov     rax, [rax+8]
0x180014a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a14  lea     rcx, stru_18003E438; lpCriticalSection
0x180014a1b  mov     edi, eax
0x180014a1d  call    cs:__imp_EnterCriticalSection
0x180014a23  xor     r8d, r8d
0x180014a26  cmp     r8d, 14h
0x180014a2a  jnb     short loc_180014A3C
0x180014a2c  cmp     ebx, [rsi+r8*4]
0x180014a30  lea     rdx, [rsi+r8*4]
0x180014a34  jnz     short loc_180014A61
0x180014a36  mov     dword ptr [rdx], 0
0x180014a3c  dec     cs:dword_18003EFB0
0x180014a42  lea     rcx, stru_18003E438; lpCriticalSection
0x180014a49  call    cs:__imp_LeaveCriticalSection
0x180014a4f  mov     rbx, [rsp+28h+arg_0]
0x180014a54  mov     eax, edi
0x180014a56  mov     rsi, [rsp+28h+arg_8]
0x180014a5b  add     rsp, 20h
0x180014a5f  pop     rdi
0x180014a60  retn
0x180014a61  inc     r8d
0x180014a64  jmp     short loc_180014A26
```
