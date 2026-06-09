# CTraceStream::OpenTraceStream(void (*)(_EVENT_RECORD *),ulong (*)(_EVENT_TRACE_LOGFILEW *))

- ea: `0x18001e3e0`
- end: `0x18001e44d`
- name: `?OpenTraceStream@CTraceStream@@QEAAJP6AXPEAU_EVENT_RECORD@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@Z@Z`
- size: `109`
- prototype: `__int64 __fastcall(CTraceStream *__hidden this, void (*)(struct _EVENT_RECORD *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *))`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e318`

## callees

- `0x18001e3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e431`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001e41a`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001e41a`

## pseudocode

```c
signed int __fastcall CTraceStream::OpenTraceStream(
        CTraceStream *this,
        void (*a2)(struct _EVENT_RECORD *),
        unsigned int (*a3)(struct _EVENT_TRACE_LOGFILEW *))
{
  signed int result; // eax
  struct _EVENT_TRACE_LOGFILEW *v5; // rcx
  TRACEHANDLE v6; // rax

  if ( *((_QWORD *)this + 58) != -1 )
    return 1;
  v5 = (struct _EVENT_TRACE_LOGFILEW *)((char *)this + 8);
  v5->EventCallback = (PEVENT_CALLBACK)CTraceRelogger::EventCallbackThunk;
  *((_QWORD *)this + 51) = CTraceRelogger::BufferCallbackThunk;
  v6 = OpenTraceW(v5);
  *((_QWORD *)this + 58) = v6;
  if ( v6 != -1 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001e3e0  push    rbx
0x18001e3e2  sub     rsp, 20h
0x18001e3e6  cmp     qword ptr [rcx+1D0h], 0FFFFFFFFFFFFFFFFh
0x18001e3ee  mov     rbx, rcx
0x18001e3f1  jz      short loc_18001E3FA
0x18001e3f3  mov     eax, 1
0x18001e3f8  jmp     short loc_18001E447
0x18001e3fa  add     rcx, 8; Logfile
0x18001e3fe  lea     rax, ?EventCallbackThunk@CTraceRelogger@@CAXPEAU_EVENT_RECORD@@@Z; CTraceRelogger::EventCallbackThunk(_EVENT_RECORD *)
0x18001e405  mov     [rcx+1A8h], rax
0x18001e40c  lea     rax, ?BufferCallbackThunk@CTraceRelogger@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; CTraceRelogger::BufferCallbackThunk(_EVENT_TRACE_LOGFILEW *)
0x18001e413  mov     [rbx+198h], rax
0x18001e41a  call    cs:__imp_OpenTraceW
0x18001e420  mov     [rbx+1D0h], rax
0x18001e427  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e42b  jz      short loc_18001E431
0x18001e42d  xor     eax, eax
0x18001e42f  jmp     short loc_18001E447
0x18001e431  call    cs:__imp_GetLastError
0x18001e437  mov     ecx, eax
0x18001e439  test    eax, eax
0x18001e43b  jg      short loc_18001E43F
0x18001e43d  jmp     short loc_18001E447
0x18001e43f  movzx   eax, cx
0x18001e442  or      eax, 80070000h
0x18001e447  add     rsp, 20h
0x18001e44b  pop     rbx
0x18001e44c  retn
```
