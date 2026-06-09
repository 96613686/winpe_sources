# pStartWorkerThreads

- ea: `0x1800086c4`
- end: `0x1800087d7`
- name: `pStartWorkerThreads`
- size: `275`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003108`

## callees

- `0x180002250`
- `0x18000720c`
- `0x1800086c4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086f0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800086e0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800086e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008790`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008790`

## string_xrefs

- `0x180008733`: `pStartWorkerThreads`
- `0x180008701`: `Couldn't reset ExecQueue->hStopWorkerThreads`

## pseudocode

```c
__int64 __fastcall pStartWorkerThreads(char *lpParameter)
{
  DWORD LastError; // ebx
  int v3; // eax
  int i; // edi
  LPCWSTR lpModuleName; // [rsp+68h] [rbp+0h]
  DWORD ThreadId; // [rsp+70h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( ResetEvent(*((HANDLE *)lpParameter + 31)) )
  {
    for ( i = 0; i < 3; ++i )
    {
      if ( !CreateThread(0, 0, pWorkerThreadFunc, lpParameter, 0, &ThreadId) )
        return 0;
      pLock(lpParameter);
      ++*((_DWORD *)lpParameter + 58);
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 184));
    }
    return 1;
  }
  else
  {
    LastError = GetLastError();
    v3 = (unsigned int)ConstructPartialMsgW(0x2000088u, "Couldn't reset ExecQueue->hStopWorkerThreads");
    WdsSetupLogMessageW(
      v3,
      589824,
      (int)L"D",
      0,
      2482,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"pStartWorkerThreads",
      lpModuleName,
      LastError,
      0,
      0);
    return 0;
  }
}

```

## disassembly

```asm
0x1800086c4  mov     [rsp+arg_8], rbx
0x1800086c9  push    rdi
0x1800086ca  sub     rsp, 60h
0x1800086ce  mov     rbx, rcx
0x1800086d1  mov     [rsp+68h+ThreadId], 0
0x1800086d9  mov     rcx, [rcx+0F8h]; hEvent
0x1800086e0  call    cs:__imp_ResetEvent
0x1800086e7  nop     dword ptr [rax+rax+00h]
0x1800086ec  test    eax, eax
0x1800086ee  jnz     short loc_180008769
0x1800086f0  call    cs:__imp_GetLastError
0x1800086f7  nop     dword ptr [rax+rax+00h]
0x1800086fc  mov     rdi, [rsp+68h]
0x180008701  lea     rdx, aCouldnTResetEx; "Couldn't reset ExecQueue->hStopWorkerTh"...
0x180008708  mov     ecx, 2000088h; unsigned int
0x18000870d  mov     ebx, eax
0x18000870f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180008714  mov     [rsp+68h+var_18], 0; int
0x18000871c  lea     r8, aD_1; "D"
0x180008723  mov     [rsp+68h+var_20], 0; __int64
0x18000872c  mov     rcx, rax; int
0x18000872f  mov     [rsp+68h+var_28], ebx; int
0x180008733  lea     rax, aPstartworkerth; "pStartWorkerThreads"
0x18000873a  mov     [rsp+68h+lpModuleName], rdi; lpModuleName
0x18000873f  xor     r9d, r9d; int
0x180008742  mov     [rsp+68h+var_38], rax; __int64
0x180008747  mov     edx, 90000h; int
0x18000874c  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180008753  mov     [rsp+68h+lpThreadId], rax; unsigned __int16 *
0x180008758  mov     [rsp+68h+dwCreationFlags], 9B2h; int
0x180008760  call    WdsSetupLogMessageW
0x180008765  xor     eax, eax
0x180008767  jmp     short loc_1800087CB
0x180008769  xor     edi, edi
0x18000876b  cmp     edi, 3
0x18000876e  jge     short loc_1800087C6
0x180008770  lea     rax, [rsp+68h+ThreadId]
0x180008775  mov     r9, rbx; lpParameter
0x180008778  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18000877d  lea     r8, pWorkerThreadFunc; lpStartAddress
0x180008784  xor     edx, edx; dwStackSize
0x180008786  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000878e  xor     ecx, ecx; lpThreadAttributes
0x180008790  call    cs:__imp_CreateThread
0x180008797  nop     dword ptr [rax+rax+00h]
0x18000879c  test    rax, rax
0x18000879f  jz      short loc_180008765
0x1800087a1  mov     rcx, rbx
0x1800087a4  call    pLock
0x1800087a9  inc     dword ptr [rbx+0E8h]
0x1800087af  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x1800087b6  call    cs:__imp_LeaveCriticalSection
0x1800087bd  nop     dword ptr [rax+rax+00h]
0x1800087c2  inc     edi
0x1800087c4  jmp     short loc_18000876B
0x1800087c6  mov     eax, 1
0x1800087cb  mov     rbx, [rsp+68h+arg_8]
0x1800087d0  add     rsp, 60h
0x1800087d4  pop     rdi
0x1800087d5  retn
```
