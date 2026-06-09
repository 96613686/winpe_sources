# CSQMLogger::OnServiceStop(void)

- ea: `0x180019d10`
- end: `0x180019e81`
- name: `?OnServiceStop@CSQMLogger@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(CSQMLogger *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800405f4`

## callees

- `0x180003f30`
- `0x180017c4c`
- `0x180019d10`
- `0x180040c80`
- `0x180041900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180019dde`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180019dde`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180019d42`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180019d9a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180019d42`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180019d9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e67`

## string_xrefs

- `0x180019dfd`: `DeleteTimerQueueEx 0x%08x`
- `0x180019db9`: `DeleteTimerQueueTimer for m_RdshSqmTimerQueueTimer failed: 0x%x`
- `0x180019d61`: `DeleteTimerQueueTimer failed: 0x%x`
- `0x180019e51`: `CSQMUtil::WriteRdshSqmData() failed 0x%08X`

## pseudocode

```c
void __fastcall CSQMLogger::OnServiceStop(CSQMLogger *this)
{
  void *v1; // rdx
  HANDLE *v2; // rdi
  int v3; // esi
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax
  int v8; // eax
  int v9; // eax

  v1 = (void *)*((_QWORD *)this + 200);
  v2 = (HANDLE *)((char *)this + 1592);
  v3 = 0;
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(*v2, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "DeleteTimerQueueTimer failed: 0x%x", LastError);
    }
    *((_QWORD *)this + 200) = 0;
  }
  if ( *((_QWORD *)this + 201) )
  {
    _InterlockedExchange(&CSQMLogger::m_lRdshSqmWrittenSuccessfully, 0);
    v3 = 1;
    if ( !DeleteTimerQueueTimer(*v2, *((HANDLE *)this + 201), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      _DbgPrintMessage(8, "DeleteTimerQueueTimer for m_RdshSqmTimerQueueTimer failed: 0x%x", v6);
    }
    *((_QWORD *)this + 201) = 0;
  }
  if ( *v2 )
  {
    if ( !DeleteTimerQueueEx(*v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      _DbgPrintMessage(8, "DeleteTimerQueueEx 0x%08x", v7);
    }
    *((_QWORD *)this + 199) = 0;
  }
  v8 = CSQMUtil::CloseSQMSession();
  if ( v8 < 0 )
    _DbgPrintMessage(8, "CSQMUtil::CloseSQMSession() failed:0x%08x", v8);
  CSQMUtil::ClosePDHQuery();
  if ( v3 == 1 && !CSQMLogger::m_lRdshSqmWrittenSuccessfully )
  {
    v9 = CSQMUtil::WriteRdshSqmData();
    if ( v9 < 0 )
      _DbgPrintMessage(8, "CSQMUtil::WriteRdshSqmData() failed 0x%08X", v9);
  }
  LocalFree(hMem);
  _InterlockedExchange(&CSQMLogger::m_lRdshHourCounter, 0);
}

```

## disassembly

```asm
0x180019d10  push    rbx
0x180019d12  push    rsi
0x180019d13  push    rdi
0x180019d14  push    r12
0x180019d16  push    r14
0x180019d18  sub     rsp, 20h
0x180019d1c  mov     rdx, [rcx+640h]; Timer
0x180019d23  lea     rdi, [rcx+638h]
0x180019d2a  xor     esi, esi
0x180019d2c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180019d30  mov     rbx, rcx
0x180019d33  lea     r14d, [rsi+8]
0x180019d37  test    rdx, rdx
0x180019d3a  jz      short loc_180019D77
0x180019d3c  mov     rcx, [rdi]; TimerQueue
0x180019d3f  mov     r8, r12; CompletionEvent
0x180019d42  call    cs:__imp_DeleteTimerQueueTimer
0x180019d48  test    eax, eax
0x180019d4a  jnz     short loc_180019D70
0x180019d4c  call    cs:__imp_GetLastError
0x180019d52  test    eax, eax
0x180019d54  jle     short loc_180019D5E
0x180019d56  movzx   eax, ax
0x180019d59  or      eax, 80070000h
0x180019d5e  mov     r8d, eax
0x180019d61  lea     rdx, aDeletetimerque_0; "DeleteTimerQueueTimer failed: 0x%x"
0x180019d68  mov     ecx, r14d; int
0x180019d6b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019d70  mov     [rbx+640h], rsi
0x180019d77  cmp     [rbx+648h], rsi
0x180019d7e  jz      short loc_180019DD3
0x180019d80  xor     eax, eax
0x180019d82  mov     r8, r12; CompletionEvent
0x180019d85  xchg    eax, cs:?m_lRdshSqmWrittenSuccessfully@CSQMLogger@@0JA; long CSQMLogger::m_lRdshSqmWrittenSuccessfully
0x180019d8b  mov     rdx, [rbx+648h]; Timer
0x180019d92  mov     esi, 1
0x180019d97  mov     rcx, [rdi]; TimerQueue
0x180019d9a  call    cs:__imp_DeleteTimerQueueTimer
0x180019da0  test    eax, eax
0x180019da2  jnz     short loc_180019DC8
0x180019da4  call    cs:__imp_GetLastError
0x180019daa  test    eax, eax
0x180019dac  jle     short loc_180019DB6
0x180019dae  movzx   eax, ax
0x180019db1  or      eax, 80070000h
0x180019db6  mov     r8d, eax
0x180019db9  lea     rdx, aDeletetimerque_1; "DeleteTimerQueueTimer for m_RdshSqmTime"...
0x180019dc0  mov     ecx, r14d; int
0x180019dc3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019dc8  mov     qword ptr [rbx+648h], 0
0x180019dd3  mov     rcx, [rdi]; TimerQueue
0x180019dd6  test    rcx, rcx
0x180019dd9  jz      short loc_180019E17
0x180019ddb  mov     rdx, r12; CompletionEvent
0x180019dde  call    cs:__imp_DeleteTimerQueueEx
0x180019de4  test    eax, eax
0x180019de6  jnz     short loc_180019E0C
0x180019de8  call    cs:__imp_GetLastError
0x180019dee  test    eax, eax
0x180019df0  jle     short loc_180019DFA
0x180019df2  movzx   eax, ax
0x180019df5  or      eax, 80070000h
0x180019dfa  mov     r8d, eax
0x180019dfd  lea     rdx, aDeletetimerque; "DeleteTimerQueueEx 0x%08x"
0x180019e04  mov     ecx, r14d; int
0x180019e07  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019e0c  mov     qword ptr [rbx+638h], 0
0x180019e17  call    ?CloseSQMSession@CSQMUtil@@SAJXZ; CSQMUtil::CloseSQMSession(void)
0x180019e1c  test    eax, eax
0x180019e1e  jns     short loc_180019E32
0x180019e20  mov     r8d, eax
0x180019e23  lea     rdx, aCsqmutilCloses_0; "CSQMUtil::CloseSQMSession() failed:0x%0"...
0x180019e2a  mov     ecx, r14d; int
0x180019e2d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019e32  call    ?ClosePDHQuery@CSQMUtil@@SAXXZ; CSQMUtil::ClosePDHQuery(void)
0x180019e37  cmp     esi, 1
0x180019e3a  jnz     short loc_180019E60
0x180019e3c  cmp     cs:?m_lRdshSqmWrittenSuccessfully@CSQMLogger@@0JA, 0; long CSQMLogger::m_lRdshSqmWrittenSuccessfully
0x180019e43  jnz     short loc_180019E60
0x180019e45  call    ?WriteRdshSqmData@CSQMUtil@@SAJXZ; CSQMUtil::WriteRdshSqmData(void)
0x180019e4a  test    eax, eax
0x180019e4c  jns     short loc_180019E60
0x180019e4e  mov     r8d, eax
0x180019e51  lea     rdx, aCsqmutilWriter; "CSQMUtil::WriteRdshSqmData() failed 0x%"...
0x180019e58  mov     ecx, r14d; int
0x180019e5b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019e60  mov     rcx, cs:hMem; hMem
0x180019e67  call    cs:__imp_LocalFree
0x180019e6d  xor     eax, eax
0x180019e6f  xchg    eax, cs:?m_lRdshHourCounter@CSQMLogger@@0JA; long CSQMLogger::m_lRdshHourCounter
0x180019e75  add     rsp, 20h
0x180019e79  pop     r14
0x180019e7b  pop     r12
0x180019e7d  pop     rdi
0x180019e7e  pop     rsi
0x180019e7f  pop     rbx
0x180019e80  retn
```
