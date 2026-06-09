# WamRegGlobal::AcquireAdmWriteLock(void)

- ea: `0x180001d2c`
- end: `0x180001e5e`
- name: `?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ`
- size: `306`
- prototype: `void __fastcall(WamRegGlobal *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180001ed0`
- `0x180002110`
- `0x1800021d0`
- `0x180002460`
- `0x180002850`
- `0x1800029e0`
- `0x1800034b0`
- `0x180003720`
- `0x180003d80`

## callees

- `0x180001d2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001dad`
- `KERNEL32!GetLastError` at `0x180001dad`
- `KERNEL32!EnterCriticalSection` at `0x180001d42`
- `KERNEL32!EnterCriticalSection` at `0x180001d83`
- `KERNEL32!EnterCriticalSection` at `0x180001d42`
- `KERNEL32!EnterCriticalSection` at `0x180001d83`
- `KERNEL32!LeaveCriticalSection` at `0x180001d5e`
- `KERNEL32!LeaveCriticalSection` at `0x180001d9c`
- `KERNEL32!LeaveCriticalSection` at `0x180001d5e`
- `KERNEL32!LeaveCriticalSection` at `0x180001d9c`
- `KERNEL32!WaitForSingleObject` at `0x180001d70`
- `KERNEL32!WaitForSingleObject` at `0x180001d70`
- `KERNEL32!GetCurrentThreadId` at `0x180001e13`
- `KERNEL32!GetCurrentThreadId` at `0x180001e13`
- `KERNEL32!ResetEvent` at `0x180001df7`
- `KERNEL32!ResetEvent` at `0x180001df7`
- `iisutil!PuDbgPrint` at `0x180001de2`
- `iisutil!PuDbgPrint` at `0x180001e48`
- `iisutil!PuDbgPrint` at `0x180001de2`
- `iisutil!PuDbgPrint` at `0x180001e48`

## string_xrefs

- `0x180001dba`: `WamAdmLock::AcquireWriteLock`
- `0x180001e20`: `WamAdmLock::AcquireWriteLock`
- `0x180001e3c`: `Thread %08x acquired the WriteLock of WAMREG, ServiceNum is %d.\n`

## pseudocode

```c
void __fastcall WamRegGlobal::AcquireAdmWriteLock(WamRegGlobal *this)
{
  int v1; // edi
  DWORD v2; // ebx
  DWORD v3; // esi
  DWORD LastError; // eax
  DWORD CurrentThreadId; // eax

  EnterCriticalSection(&CriticalSection);
  v1 = WamRegGlobal::m_WamAdmLock++;
  LeaveCriticalSection(&CriticalSection);
  v2 = 0;
  do
  {
    v3 = WaitForSingleObject(hEvent, 0xFFFFFFFF);
    if ( v3 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          286,
          "WamAdmLock::AcquireWriteLock",
          "WaitForSingleObject failed, function returns %08x, errno = %08x\n",
          v3,
          LastError);
      }
    }
    else
    {
      EnterCriticalSection(&CriticalSection);
      if ( v1 == dword_18000B774 )
        v2 = v3 + 1;
      LeaveCriticalSection(&CriticalSection);
    }
  }
  while ( !v2 );
  ResetEvent(hEvent);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      296,
      "WamAdmLock::AcquireWriteLock",
      "Thread %08x acquired the WriteLock of WAMREG, ServiceNum is %d.\n",
      CurrentThreadId,
      v1);
  }
}

```

## disassembly

```asm
0x180001d2c  mov     [rsp+arg_0], rbx
0x180001d31  mov     [rsp+arg_8], rsi
0x180001d36  push    rdi
0x180001d37  sub     rsp, 40h
0x180001d3b  lea     rcx, CriticalSection; lpCriticalSection
0x180001d42  call    cs:__imp_EnterCriticalSection
0x180001d48  mov     edi, cs:?m_WamAdmLock@WamRegGlobal@@0VWamAdmLock@@A; WamAdmLock WamRegGlobal::m_WamAdmLock
0x180001d4e  lea     rcx, CriticalSection; lpCriticalSection
0x180001d55  lea     eax, [rdi+1]
0x180001d58  mov     cs:?m_WamAdmLock@WamRegGlobal@@0VWamAdmLock@@A, eax; WamAdmLock WamRegGlobal::m_WamAdmLock
0x180001d5e  call    cs:__imp_LeaveCriticalSection
0x180001d64  xor     ebx, ebx
0x180001d66  mov     rcx, cs:hEvent; hHandle
0x180001d6d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001d70  call    cs:__imp_WaitForSingleObject
0x180001d76  mov     esi, eax
0x180001d78  test    eax, eax
0x180001d7a  jnz     short loc_180001DA4
0x180001d7c  lea     rcx, CriticalSection; lpCriticalSection
0x180001d83  call    cs:__imp_EnterCriticalSection
0x180001d89  cmp     edi, cs:dword_18000B774
0x180001d8f  lea     eax, [rsi+1]
0x180001d92  lea     rcx, CriticalSection; lpCriticalSection
0x180001d99  cmovz   ebx, eax
0x180001d9c  call    cs:__imp_LeaveCriticalSection
0x180001da2  jmp     short loc_180001DE8
0x180001da4  test    byte ptr cs:g_dwDebugFlags, 3
0x180001dab  jz      short loc_180001DE8
0x180001dad  call    cs:__imp_GetLastError
0x180001db3  mov     rcx, cs:g_pDebug
0x180001dba  lea     r9, aWamadmlockAcqu; "WamAdmLock::AcquireWriteLock"
0x180001dc1  mov     [rsp+48h+var_18], eax
0x180001dc5  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180001dcc  lea     rax, aWaitforsingleo; "WaitForSingleObject failed, function re"...
0x180001dd3  mov     [rsp+48h+var_20], esi
0x180001dd7  mov     r8d, 11Eh
0x180001ddd  mov     [rsp+48h+var_28], rax
0x180001de2  call    cs:__imp_PuDbgPrint
0x180001de8  test    ebx, ebx
0x180001dea  jz      loc_180001D66
0x180001df0  mov     rcx, cs:hEvent; hEvent
0x180001df7  call    cs:__imp_ResetEvent
0x180001dfd  mov     eax, cs:g_dwDebugFlags
0x180001e03  test    al, 3
0x180001e05  setnz   cl
0x180001e08  bt      eax, 10h
0x180001e0c  setb    al
0x180001e0f  test    al, cl
0x180001e11  jz      short loc_180001E4E
0x180001e13  call    cs:__imp_GetCurrentThreadId
0x180001e19  mov     rcx, cs:g_pDebug
0x180001e20  lea     r9, aWamadmlockAcqu; "WamAdmLock::AcquireWriteLock"
0x180001e27  mov     [rsp+48h+var_18], edi
0x180001e2b  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180001e32  mov     [rsp+48h+var_20], eax
0x180001e36  mov     r8d, 128h
0x180001e3c  lea     rax, aThread08xAcqui; "Thread %08x acquired the WriteLock of W"...
0x180001e43  mov     [rsp+48h+var_28], rax
0x180001e48  call    cs:__imp_PuDbgPrint
0x180001e4e  mov     rbx, [rsp+48h+arg_0]
0x180001e53  mov     rsi, [rsp+48h+arg_8]
0x180001e58  add     rsp, 40h
0x180001e5c  pop     rdi
0x180001e5d  retn
```
