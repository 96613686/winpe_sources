# WamRegGlobal::ReleaseAdmWriteLock(void)

- ea: `0x180003cdc`
- end: `0x180003d6c`
- name: `?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ`
- size: `144`
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

- `0x180003cdc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003ce9`
- `KERNEL32!EnterCriticalSection` at `0x180003ce9`
- `KERNEL32!LeaveCriticalSection` at `0x180003d65`
- `KERNEL32!GetCurrentThreadId` at `0x180003d0b`
- `KERNEL32!GetCurrentThreadId` at `0x180003d0b`
- `KERNEL32!SetEvent` at `0x180003d53`
- `KERNEL32!SetEvent` at `0x180003d53`
- `iisutil!PuDbgPrint` at `0x180003d40`
- `iisutil!PuDbgPrint` at `0x180003d40`

## string_xrefs

- `0x180003d34`: `Thread %08x released the WriteLock of WAMREG, ServiceNum is %d.\n`
- `0x180003d18`: `WamAdmLock::ReleaseWriteLock`

## pseudocode

```c
void __fastcall WamRegGlobal::ReleaseAdmWriteLock(WamRegGlobal *this)
{
  int v1; // ebx
  DWORD CurrentThreadId; // eax

  EnterCriticalSection(&CriticalSection);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
  {
    v1 = dword_18000B774;
    CurrentThreadId = GetCurrentThreadId();
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      320,
      "WamAdmLock::ReleaseWriteLock",
      "Thread %08x released the WriteLock of WAMREG, ServiceNum is %d.\n",
      CurrentThreadId,
      v1);
  }
  ++dword_18000B774;
  SetEvent(hEvent);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180003cdc  push    rbx
0x180003cde  sub     rsp, 40h
0x180003ce2  lea     rcx, CriticalSection; lpCriticalSection
0x180003ce9  call    cs:__imp_EnterCriticalSection
0x180003cef  mov     eax, cs:g_dwDebugFlags
0x180003cf5  test    al, 3
0x180003cf7  setnz   cl
0x180003cfa  bt      eax, 10h
0x180003cfe  setb    al
0x180003d01  test    al, cl
0x180003d03  jz      short loc_180003D46
0x180003d05  mov     ebx, cs:dword_18000B774
0x180003d0b  call    cs:__imp_GetCurrentThreadId
0x180003d11  mov     rcx, cs:g_pDebug
0x180003d18  lea     r9, aWamadmlockRele; "WamAdmLock::ReleaseWriteLock"
0x180003d1f  mov     [rsp+48h+var_18], ebx
0x180003d23  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180003d2a  mov     [rsp+48h+var_20], eax
0x180003d2e  mov     r8d, 140h
0x180003d34  lea     rax, aThread08xRelea; "Thread %08x released the WriteLock of W"...
0x180003d3b  mov     [rsp+48h+var_28], rax
0x180003d40  call    cs:__imp_PuDbgPrint
0x180003d46  mov     rcx, cs:hEvent; hEvent
0x180003d4d  inc     cs:dword_18000B774
0x180003d53  call    cs:__imp_SetEvent
0x180003d59  lea     rcx, CriticalSection
0x180003d60  add     rsp, 40h
0x180003d64  pop     rbx
0x180003d65  jmp     cs:__imp_LeaveCriticalSection
```
