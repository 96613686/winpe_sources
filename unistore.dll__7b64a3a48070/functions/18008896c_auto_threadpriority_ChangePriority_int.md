# auto_threadpriority::ChangePriority(int)

- ea: `0x18008896c`
- end: `0x1800889c7`
- name: `?ChangePriority@auto_threadpriority@@QEAAXH@Z`
- size: `91`
- prototype: `void(auto_threadpriority *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025034`

## callees

- `0x18006f180`
- `0x18008896c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800889b3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800889b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180088993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800889a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180088993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800889a8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008899c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008899c`

## pseudocode

```c
void __fastcall auto_threadpriority::ChangePriority(auto_threadpriority *this, int a2)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  HANDLE v6; // rax

  if ( *((_DWORD *)this + 1) )
    Log_AssertionEvent(this, "onecoreuap\\private\\base\\inc\\UserDataPlatformHelper.h", 768);
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  *(_DWORD *)this = ThreadPriority;
  if ( ThreadPriority != a2 )
  {
    v6 = GetCurrentThread();
    *((_DWORD *)this + 1) = SetThreadPriority(v6, a2);
  }
}

```

## disassembly

```asm
0x18008896c  mov     [rsp+arg_0], rbx
0x180088971  push    rdi
0x180088972  sub     rsp, 20h
0x180088976  cmp     dword ptr [rcx+4], 0
0x18008897a  mov     edi, edx
0x18008897c  mov     rbx, rcx
0x18008897f  jz      short loc_180088993
0x180088981  mov     r8d, 300h
0x180088987  lea     rdx, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\UserDat"...
0x18008898e  call    Log_AssertionEvent
0x180088993  call    cs:__imp_GetCurrentThread
0x180088999  mov     rcx, rax; hThread
0x18008899c  call    cs:__imp_GetThreadPriority
0x1800889a2  mov     [rbx], eax
0x1800889a4  cmp     eax, edi
0x1800889a6  jz      short loc_1800889BC
0x1800889a8  call    cs:__imp_GetCurrentThread
0x1800889ae  mov     rcx, rax; hThread
0x1800889b1  mov     edx, edi; nPriority
0x1800889b3  call    cs:__imp_SetThreadPriority
0x1800889b9  mov     [rbx+4], eax
0x1800889bc  mov     rbx, [rsp+28h+arg_0]
0x1800889c1  add     rsp, 20h
0x1800889c5  pop     rdi
0x1800889c6  retn
```
