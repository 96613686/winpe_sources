# CSurrogateTimeout::StartTimer(uint,void (*)(void *))

- ea: `0x180045cbc`
- end: `0x180045db3`
- name: `?StartTimer@CSurrogateTimeout@@QEAAJIP6AXPEAX@Z@Z`
- size: `247`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int, void (*)(void *))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b83c`

## callees

- `0x18000b3c0`
- `0x180045cbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180045d1c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180045d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045ce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045ce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045cf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045d3c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045d3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045d86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045d86`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180045d9d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180045d9d`

## pseudocode

```c
__int64 __fastcall CSurrogateTimeout::StartTimer(struct _TP_TIMER **pv, unsigned int a2, void (*a3)(void *))
{
  __int64 v4; // rbp
  int Error; // ebx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v8; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v10; // rcx
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+18h] BYREF

  pftDueTime = (struct _FILETIME)a3;
  v4 = a2;
  Error = -2147175934;
  if ( !CSurrogateTimeout::s_fTerminated )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v8 = GetCurrentProcess();
    if ( DuplicateHandle(v8, CurrentThread, CurrentProcess, (LPHANDLE)pv, 0x1FFFFFu, 1, 0)
      || (int)ResultFromKnownLastError() >= 0 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CSurrogateTimeout::_s_TimeOutThreadProc, pv, 0);
      pv[1] = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        Error = 0;
LABEL_7:
        pftDueTime = (struct _FILETIME)(-10000 * v4);
        v10 = pv[1];
        pv[2] = (struct _TP_TIMER *)ReportTimeout;
        SetThreadpoolTimer(v10, &pftDueTime, 0, 0);
        return (unsigned int)Error;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_7;
    }
    SHCreateThread(CSurrogateTimeout::_s_ReportTimeout, 0, 0, 0);
    return (unsigned int)-2147175934;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180045cbc  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180045cc1  push    rbx
0x180045cc2  push    rbp
0x180045cc3  push    rsi
0x180045cc4  push    rdi
0x180045cc5  sub     rsp, 48h
0x180045cc9  cmp     cs:?s_fTerminated@CSurrogateTimeout@@0_NA, 0; bool CSurrogateTimeout::s_fTerminated
0x180045cd0  mov     rsi, rcx
0x180045cd3  mov     ebp, edx
0x180045cd5  mov     ebx, 8004B202h
0x180045cda  jnz     loc_180045DA8
0x180045ce0  call    cs:__imp_GetCurrentProcess
0x180045ce6  mov     rdi, rax
0x180045ce9  call    cs:__imp_GetCurrentThread
0x180045cef  mov     rbx, rax
0x180045cf2  call    cs:__imp_GetCurrentProcess
0x180045cf8  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180045d00  mov     r9, rsi; lpTargetHandle
0x180045d03  mov     rcx, rax; hSourceProcessHandle
0x180045d06  mov     [rsp+68h+bInheritHandle], 1; bInheritHandle
0x180045d0e  mov     r8, rdi; hTargetProcessHandle
0x180045d11  mov     [rsp+68h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x180045d19  mov     rdx, rbx; hSourceHandle
0x180045d1c  call    cs:__imp_DuplicateHandle
0x180045d22  test    eax, eax
0x180045d24  jnz     short loc_180045D2F
0x180045d26  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045d2b  test    eax, eax
0x180045d2d  js      short loc_180045D8E
0x180045d2f  xor     r8d, r8d; pcbe
0x180045d32  lea     rcx, ?_s_TimeOutThreadProc@CSurrogateTimeout@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180045d39  mov     rdx, rsi; pv
0x180045d3c  call    cs:__imp_CreateThreadpoolTimer
0x180045d42  mov     [rsi+8], rax
0x180045d46  test    rax, rax
0x180045d49  jz      short loc_180045D4F
0x180045d4b  xor     ebx, ebx
0x180045d4d  jmp     short loc_180045D5A
0x180045d4f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045d54  mov     ebx, eax
0x180045d56  test    eax, eax
0x180045d58  js      short loc_180045D8E
0x180045d5a  imul    rcx, rbp, 0FFFFFFFFFFFFD8F0h
0x180045d61  lea     rax, ?ReportTimeout@@YAXPEAX@Z; ReportTimeout(void *)
0x180045d68  xor     r9d, r9d; msWindowLength
0x180045d6b  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rcx
0x180045d73  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180045d7b  mov     rcx, [rsi+8]; pti
0x180045d7f  xor     r8d, r8d; msPeriod
0x180045d82  mov     [rsi+10h], rax
0x180045d86  call    cs:__imp_SetThreadpoolTimer
0x180045d8c  jmp     short loc_180045DA8
0x180045d8e  xor     r9d, r9d; pfnCallback
0x180045d91  lea     rcx, ?_s_ReportTimeout@CSurrogateTimeout@@CAKPEAX@Z; pfnThreadProc
0x180045d98  xor     r8d, r8d; flags
0x180045d9b  xor     edx, edx; pData
0x180045d9d  call    cs:__imp_SHCreateThread
0x180045da3  mov     ebx, 8004B202h
0x180045da8  mov     eax, ebx
0x180045daa  add     rsp, 48h
0x180045dae  pop     rdi
0x180045daf  pop     rsi
0x180045db0  pop     rbp
0x180045db1  pop     rbx
0x180045db2  retn
```
