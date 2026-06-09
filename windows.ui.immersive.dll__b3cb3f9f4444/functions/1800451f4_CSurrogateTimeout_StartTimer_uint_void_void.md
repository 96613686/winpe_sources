# CSurrogateTimeout::StartTimer(uint,void (*)(void *))

- ea: `0x1800451f4`
- end: `0x180045316`
- name: `?StartTimer@CSurrogateTimeout@@QEAAJIP6AXPEAX@Z@Z`
- size: `290`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int, void (*)(void *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180044a40`
- `0x180044b80`

## callees

- `0x18003d244`
- `0x1800451f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004522c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004522c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004521d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004523b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004521d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004523b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004526b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004526b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800452d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800452d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045291`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045291`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800452f2`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800452f2`

## pseudocode

```c
__int64 __fastcall CSurrogateTimeout::StartTimer(struct _TP_TIMER **pv, __int64 a2, void (*a3)(void *))
{
  int Error; // ebx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v7; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  pftDueTime = (struct _FILETIME)a3;
  Error = -2147175934;
  if ( !CSurrogateTimeout::s_fTerminated )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v7 = GetCurrentProcess();
    if ( DuplicateHandle(v7, CurrentThread, CurrentProcess, (LPHANDLE)pv, 0x1FFFFFu, 1, 0)
      || (int)ResultFromKnownLastError() >= 0 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CSurrogateTimeout::_s_TimeOutThreadProc, pv, 0);
      pv[1] = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        Error = 0;
LABEL_7:
        v9 = pv[1];
        pv[2] = 0;
        pftDueTime = (struct _FILETIME)-1200000000LL;
        SetThreadpoolTimer(v9, &pftDueTime, 0, 0);
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
0x1800451f4  mov     [rsp+arg_0], rbx
0x1800451f9  mov     [rsp+arg_8], rsi
0x1800451fe  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180045203  push    rdi
0x180045204  sub     rsp, 40h
0x180045208  cmp     cs:?s_fTerminated@CSurrogateTimeout@@0_NA, 0; bool CSurrogateTimeout::s_fTerminated
0x18004520f  mov     rsi, rcx
0x180045212  mov     ebx, 8004B202h
0x180045217  jnz     loc_180045303
0x18004521d  call    cs:__imp_GetCurrentProcess
0x180045224  nop     dword ptr [rax+rax+00h]
0x180045229  mov     rdi, rax
0x18004522c  call    cs:__imp_GetCurrentThread
0x180045233  nop     dword ptr [rax+rax+00h]
0x180045238  mov     rbx, rax
0x18004523b  call    cs:__imp_GetCurrentProcess
0x180045242  nop     dword ptr [rax+rax+00h]
0x180045247  mov     [rsp+48h+dwOptions], 0; dwOptions
0x18004524f  mov     r9, rsi; lpTargetHandle
0x180045252  mov     rcx, rax; hSourceProcessHandle
0x180045255  mov     [rsp+48h+bInheritHandle], 1; bInheritHandle
0x18004525d  mov     r8, rdi; hTargetProcessHandle
0x180045260  mov     [rsp+48h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x180045268  mov     rdx, rbx; hSourceHandle
0x18004526b  call    cs:__imp_DuplicateHandle
0x180045272  nop     dword ptr [rax+rax+00h]
0x180045277  test    eax, eax
0x180045279  jnz     short loc_180045284
0x18004527b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045280  test    eax, eax
0x180045282  js      short loc_1800452E3
0x180045284  xor     r8d, r8d; pcbe
0x180045287  lea     rcx, ?_s_TimeOutThreadProc@CSurrogateTimeout@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004528e  mov     rdx, rsi; pv
0x180045291  call    cs:__imp_CreateThreadpoolTimer
0x180045298  nop     dword ptr [rax+rax+00h]
0x18004529d  mov     [rsi+8], rax
0x1800452a1  test    rax, rax
0x1800452a4  jz      short loc_1800452AA
0x1800452a6  xor     ebx, ebx
0x1800452a8  jmp     short loc_1800452B5
0x1800452aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800452af  mov     ebx, eax
0x1800452b1  test    eax, eax
0x1800452b3  js      short loc_1800452E3
0x1800452b5  mov     rcx, [rsi+8]; pti
0x1800452b9  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800452be  xor     r9d, r9d; msWindowLength
0x1800452c1  mov     qword ptr [rsi+10h], 0
0x1800452c9  xor     r8d, r8d; msPeriod
0x1800452cc  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x1800452d5  call    cs:__imp_SetThreadpoolTimer
0x1800452dc  nop     dword ptr [rax+rax+00h]
0x1800452e1  jmp     short loc_180045303
0x1800452e3  xor     r9d, r9d; pfnCallback
0x1800452e6  lea     rcx, ?_s_ReportTimeout@CSurrogateTimeout@@CAKPEAX@Z; pfnThreadProc
0x1800452ed  xor     r8d, r8d; flags
0x1800452f0  xor     edx, edx; pData
0x1800452f2  call    cs:__imp_SHCreateThread
0x1800452f9  nop     dword ptr [rax+rax+00h]
0x1800452fe  mov     ebx, 8004B202h
0x180045303  mov     rsi, [rsp+48h+arg_8]
0x180045308  mov     eax, ebx
0x18004530a  mov     rbx, [rsp+48h+arg_0]
0x18004530f  add     rsp, 40h
0x180045313  pop     rdi
0x180045314  retn
```
