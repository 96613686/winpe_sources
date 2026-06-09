# CSrEtwEventManager::StartTracingInternal(void)

- ea: `0x180023f08`
- end: `0x180023fdf`
- name: `?StartTracingInternal@CSrEtwEventManager@@QEAAKXZ`
- size: `215`
- prototype: `unsigned int __fastcall(CSrEtwEventManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023310`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x180023f08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f9b`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180023fb9`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180023fb9`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180023f85`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180023f85`

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
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)CSrEtwEventManager::BufferCallback;
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
0x180023f08  push    rbx
0x180023f0a  sub     rsp, 1F0h
0x180023f11  mov     rax, cs:__security_cookie
0x180023f18  xor     rax, rsp
0x180023f1b  mov     [rsp+1F8h+var_18], rax
0x180023f23  mov     rbx, rcx
0x180023f26  xor     edx, edx; Val
0x180023f28  lea     rcx, [rsp+1F8h+Logfile]; void *
0x180023f2d  mov     r8d, 1C0h; Size
0x180023f33  call    memset_0
0x180023f38  lea     rax, [rbx+38h]
0x180023f3c  cmp     qword ptr [rax+18h], 7
0x180023f41  jbe     short loc_180023F46
0x180023f43  mov     rax, [rax]
0x180023f46  mov     [rsp+1F8h+Logfile.LoggerName], rax
0x180023f4b  lea     rcx, [rsp+1F8h+Logfile]; Logfile
0x180023f50  lea     rax, ?BufferCallback@CSrEtwEventManager@@SAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; CSrEtwEventManager::BufferCallback(_EVENT_TRACE_LOGFILEW *)
0x180023f57  mov     dword ptr [rsp+1F8h+Logfile.1Ch], 10000100h
0x180023f5f  mov     [rsp+1F8h+Logfile.BufferCallback], rax
0x180023f67  lea     rax, ?ProcessEvent@CSrEtwEventManager@@SAXPEAU_EVENT_RECORD@@@Z; CSrEtwEventManager::ProcessEvent(_EVENT_RECORD *)
0x180023f6e  mov     qword ptr [rsp+1F8h+Logfile.1A8h], rax
0x180023f76  mov     rax, [rbx+88h]
0x180023f7d  mov     [rsp+1F8h+Logfile.Context], rax
0x180023f85  call    cs:__imp_OpenTraceW
0x180023f8c  nop     dword ptr [rax+rax+00h]
0x180023f91  mov     [rbx+70h], rax
0x180023f95  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023f99  jnz     short loc_180023FAB
0x180023f9b  call    cs:__imp_GetLastError
0x180023fa2  nop     dword ptr [rax+rax+00h]
0x180023fa7  test    eax, eax
0x180023fa9  jnz     short loc_180023FC5
0x180023fab  xor     r9d, r9d; EndTime
0x180023fae  lea     rcx, [rbx+70h]; HandleArray
0x180023fb2  xor     r8d, r8d; StartTime
0x180023fb5  lea     edx, [r9+1]; HandleCount
0x180023fb9  call    cs:__imp_ProcessTrace
0x180023fc0  nop     dword ptr [rax+rax+00h]
0x180023fc5  mov     rcx, [rsp+1F8h+var_18]
0x180023fcd  xor     rcx, rsp; StackCookie
0x180023fd0  call    __security_check_cookie
0x180023fd5  add     rsp, 1F0h
0x180023fdc  pop     rbx
0x180023fdd  retn
```
