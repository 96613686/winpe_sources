# CSrEtwEventManager::StartTracingInternal(void)

- ea: `0x180023c7c`
- end: `0x180023d40`
- name: `?StartTracingInternal@CSrEtwEventManager@@QEAAKXZ`
- size: `196`
- prototype: `DWORD __fastcall(CSrEtwEventManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023140`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x180023c7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d09`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180023d21`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180023d21`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180023cf9`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180023cf9`

## pseudocode

```c
DWORD __fastcall CSrEtwEventManager::StartTracingInternal(CSrEtwEventManager *this)
{
  WCHAR *v2; // rax
  TRACEHANDLE v3; // rax
  DWORD result; // eax
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+20h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  v2 = (WCHAR *)((char *)this + 56);
  if ( *((_QWORD *)this + 10) > 7u )
    v2 = *(WCHAR **)v2;
  Logfile.LoggerName = v2;
  Logfile.LogFileMode = 268435712;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)get_startup_argv_mode;
  Logfile.EventCallback = (PEVENT_CALLBACK)CSrEtwEventManager::ProcessEvent;
  Logfile.Context = (PVOID)*((_QWORD *)this + 17);
  v3 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 14) = v3;
  if ( v3 != -1 )
    return ProcessTrace((PTRACEHANDLE)this + 14, 1u, 0, 0);
  result = GetLastError();
  if ( !result )
    return ProcessTrace((PTRACEHANDLE)this + 14, 1u, 0, 0);
  return result;
}

```

## disassembly

```asm
0x180023c7c  push    rbx
0x180023c7e  sub     rsp, 1F0h
0x180023c85  mov     rax, cs:__security_cookie
0x180023c8c  xor     rax, rsp
0x180023c8f  mov     [rsp+1F8h+var_18], rax
0x180023c97  mov     rbx, rcx
0x180023c9a  xor     edx, edx; Val
0x180023c9c  lea     rcx, [rsp+1F8h+Logfile]; void *
0x180023ca1  mov     r8d, 1C0h; Size
0x180023ca7  call    memset_0
0x180023cac  lea     rax, [rbx+38h]
0x180023cb0  cmp     qword ptr [rax+18h], 7
0x180023cb5  jbe     short loc_180023CBA
0x180023cb7  mov     rax, [rax]
0x180023cba  mov     [rsp+1F8h+Logfile.LoggerName], rax
0x180023cbf  lea     rcx, [rsp+1F8h+Logfile]; Logfile
0x180023cc4  lea     rax, _get_startup_argv_mode
0x180023ccb  mov     dword ptr [rsp+1F8h+Logfile.1Ch], 10000100h
0x180023cd3  mov     [rsp+1F8h+Logfile.BufferCallback], rax
0x180023cdb  lea     rax, ?ProcessEvent@CSrEtwEventManager@@SAXPEAU_EVENT_RECORD@@@Z; CSrEtwEventManager::ProcessEvent(_EVENT_RECORD *)
0x180023ce2  mov     qword ptr [rsp+1F8h+Logfile.1A8h], rax
0x180023cea  mov     rax, [rbx+88h]
0x180023cf1  mov     [rsp+1F8h+Logfile.Context], rax
0x180023cf9  call    cs:__imp_OpenTraceW
0x180023cff  mov     [rbx+70h], rax
0x180023d03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023d07  jnz     short loc_180023D13
0x180023d09  call    cs:__imp_GetLastError
0x180023d0f  test    eax, eax
0x180023d11  jnz     short loc_180023D27
0x180023d13  xor     r9d, r9d; EndTime
0x180023d16  lea     rcx, [rbx+70h]; HandleArray
0x180023d1a  xor     r8d, r8d; StartTime
0x180023d1d  lea     edx, [r9+1]; HandleCount
0x180023d21  call    cs:__imp_ProcessTrace
0x180023d27  mov     rcx, [rsp+1F8h+var_18]
0x180023d2f  xor     rcx, rsp; StackCookie
0x180023d32  call    __security_check_cookie
0x180023d37  add     rsp, 1F0h
0x180023d3e  pop     rbx
0x180023d3f  retn
```
