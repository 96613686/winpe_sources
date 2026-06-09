# WaInitializeCallbackQueue

- ea: `0x18004021c`
- end: `0x180040385`
- name: `WaInitializeCallbackQueue`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180041954`

## callees

- `0x18002e460`
- `0x18004021c`
- `0x180072c70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180040237`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180040237`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040308`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040332`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040308`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040332`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004034f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004034f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004025e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004025e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040320`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040320`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800402a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800402a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004036b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004036b`

## pseudocode

```c
__int64 WaInitializeCallbackQueue()
{
  unsigned int LastError; // ebx

  qword_1800AEB38 = (__int64)&WaGlobalCallbackQueue;
  WaGlobalCallbackQueue = (__int64)&WaGlobalCallbackQueue;
  WaCallbackQueueTlsIndex = TlsAlloc();
  if ( WaCallbackQueueTlsIndex == -1 )
    return WaGetLastError();
  if ( InitializeCriticalSectionAndSpinCount(&WaGlobalCallbackQueueLock, 0xFA0u) )
  {
    memset_0(&WaCallbackWorkItem, 0, 0x40u);
    WaCallbackWorkItem = 1331122260;
    pwk = CreateThreadpoolWork(WapTpWorkItemCallback, &WaCallbackWorkItem, &WaTpEnvironment);
    if ( pwk )
    {
      qword_1800AEB90 = (__int64)WapCallbackWorkItem;
      xmmword_1800AEB98 = 0;
LABEL_6:
      WaCallbackQueueInitialized = 1;
      return 0;
    }
    LastError = WaGetLastError();
    if ( !LastError )
      goto LABEL_6;
    if ( pwk )
      CloseThreadpoolWork(pwk);
    if ( *((_QWORD *)&xmmword_1800AEB98 + 1) )
      CloseHandle(*((HANDLE *)&xmmword_1800AEB98 + 1));
    TlsFree(WaCallbackQueueTlsIndex);
    WaCallbackQueueTlsIndex = -1;
    DeleteCriticalSection(&WaGlobalCallbackQueueLock);
  }
  else
  {
    LastError = WaGetLastError();
    TlsFree(WaCallbackQueueTlsIndex);
    WaCallbackQueueTlsIndex = -1;
  }
  return LastError;
}

```

## disassembly

```asm
0x18004021c  push    rbx
0x18004021e  sub     rsp, 20h
0x180040222  lea     rax, WaGlobalCallbackQueue
0x180040229  mov     cs:qword_1800AEB38, rax
0x180040230  mov     cs:WaGlobalCallbackQueue, rax
0x180040237  call    cs:__imp_TlsAlloc
0x18004023e  nop     dword ptr [rax+rax+00h]
0x180040243  mov     cs:WaCallbackQueueTlsIndex, eax
0x180040249  cmp     eax, 0FFFFFFFFh
0x18004024c  jz      loc_1800402F1
0x180040252  mov     edx, 0FA0h; dwSpinCount
0x180040257  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x18004025e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180040265  nop     dword ptr [rax+rax+00h]
0x18004026a  test    eax, eax
0x18004026c  jz      loc_1800402FB
0x180040272  xor     edx, edx; Val
0x180040274  lea     rcx, WaCallbackWorkItem; void *
0x18004027b  lea     r8d, [rdx+40h]; Size
0x18004027f  call    memset_0
0x180040284  lea     r8, WaTpEnvironment; pcbe
0x18004028b  mov     cs:WaCallbackWorkItem, 4F575054h
0x180040295  lea     rdx, WaCallbackWorkItem; pv
0x18004029c  lea     rcx, WapTpWorkItemCallback; pfnwk
0x1800402a3  call    cs:__imp_CreateThreadpoolWork
0x1800402aa  nop     dword ptr [rax+rax+00h]
0x1800402af  mov     cs:pwk, rax
0x1800402b6  test    rax, rax
0x1800402b9  jz      short loc_1800402D6
0x1800402bb  lea     rax, WapCallbackWorkItem
0x1800402c2  xorps   xmm0, xmm0
0x1800402c5  mov     cs:qword_1800AEB90, rax
0x1800402cc  movdqu  cs:xmmword_1800AEB98, xmm0
0x1800402d4  jmp     short loc_1800402E1
0x1800402d6  call    WaGetLastError
0x1800402db  mov     ebx, eax
0x1800402dd  test    eax, eax
0x1800402df  jnz     short loc_18004035F
0x1800402e1  mov     cs:WaCallbackQueueInitialized, 1
0x1800402e8  xor     eax, eax
0x1800402ea  add     rsp, 20h
0x1800402ee  pop     rbx
0x1800402ef  retn
0x1800402f1  add     rsp, 20h
0x1800402f5  pop     rbx
0x1800402f6  jmp     WaGetLastError
0x1800402fb  call    WaGetLastError
0x180040300  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x180040306  mov     ebx, eax
0x180040308  call    cs:__imp_TlsFree
0x18004030f  nop     dword ptr [rax+rax+00h]
0x180040314  mov     cs:WaCallbackQueueTlsIndex, 0FFFFFFFFh
0x18004031e  jmp     short loc_18004035B
0x180040320  call    cs:__imp_CloseHandle
0x180040327  nop     dword ptr [rax+rax+00h]
0x18004032c  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x180040332  call    cs:__imp_TlsFree
0x180040339  nop     dword ptr [rax+rax+00h]
0x18004033e  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x180040345  mov     cs:WaCallbackQueueTlsIndex, 0FFFFFFFFh
0x18004034f  call    cs:__imp_DeleteCriticalSection
0x180040356  nop     dword ptr [rax+rax+00h]
0x18004035b  mov     eax, ebx
0x18004035d  jmp     short loc_1800402EA
0x18004035f  mov     rcx, cs:pwk; pwk
0x180040366  test    rcx, rcx
0x180040369  jz      short loc_180040377
0x18004036b  call    cs:__imp_CloseThreadpoolWork
0x180040372  nop     dword ptr [rax+rax+00h]
0x180040377  mov     rcx, qword ptr cs:xmmword_1800AEB98+8; hObject
0x18004037e  test    rcx, rcx
0x180040381  jz      short loc_18004032C
0x180040383  jmp     short loc_180040320
```
