# GetEtwLogType

- ea: `0x14001717c`
- end: `0x140017257`
- name: `GetEtwLogType`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017398`

## callees

- `0x14001717c`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x14001721d`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x14001721d`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1400171fd`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1400171fd`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140017228`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140017228`

## pseudocode

```c
__int64 __fastcall GetEtwLogType(WCHAR *a1, _DWORD *a2)
{
  __int64 result; // rax
  ULONG64 HandleArray[2]; // [rsp+20h] [rbp-1E8h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  g_TerminateBufferCallback = 0;
  Logfile.EventCallback = (PEVENT_CALLBACK)CheckETWFileCallback;
  g_LogFileType = 0;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)CheckETWFileBufferCallback;
  Logfile.LogFileName = a1;
  Logfile.LogFileMode = 0x10000000;
  HandleArray[0] = OpenTraceW(&Logfile);
  if ( HandleArray[0] != -1 )
  {
    ProcessTrace(HandleArray, 1u, 0, 0);
    CloseTrace(HandleArray[0]);
  }
  result = g_LogFileType;
  *a2 = g_LogFileType;
  return result;
}

```

## disassembly

```asm
0x14001717c  mov     [rsp+arg_10], rbx
0x140017181  push    rdi
0x140017182  sub     rsp, 200h
0x140017189  mov     rax, cs:__security_cookie
0x140017190  xor     rax, rsp
0x140017193  mov     [rsp+208h+var_18], rax
0x14001719b  mov     rdi, rdx
0x14001719e  mov     [rsp+208h+HandleArray], 0
0x1400171a7  mov     rbx, rcx
0x1400171aa  xor     edx, edx; Val
0x1400171ac  lea     rcx, [rsp+208h+Logfile]; void *
0x1400171b1  mov     r8d, 1C0h; Size
0x1400171b7  call    memset_0
0x1400171bc  lea     rax, ?CheckETWFileCallback@@YAXPEAU_EVENT_RECORD@@@Z; CheckETWFileCallback(_EVENT_RECORD *)
0x1400171c3  mov     cs:?g_TerminateBufferCallback@@3EA, 0; uchar g_TerminateBufferCallback
0x1400171ca  mov     qword ptr [rsp+208h+Logfile.1A8h], rax
0x1400171d2  lea     rcx, [rsp+208h+Logfile]; Logfile
0x1400171d7  lea     rax, CheckETWFileBufferCallback
0x1400171de  mov     cs:?g_LogFileType@@3KA, 0; ulong g_LogFileType
0x1400171e8  mov     [rsp+208h+Logfile.BufferCallback], rax
0x1400171f0  mov     [rsp+208h+Logfile.LogFileName], rbx
0x1400171f5  mov     dword ptr [rsp+208h+Logfile.1Ch], 10000000h
0x1400171fd  call    cs:__imp_OpenTraceW
0x140017203  mov     [rsp+208h+HandleArray], rax
0x140017208  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001720c  jz      short loc_14001722E
0x14001720e  xor     r9d, r9d; EndTime
0x140017211  lea     rcx, [rsp+208h+HandleArray]; HandleArray
0x140017216  xor     r8d, r8d; StartTime
0x140017219  lea     edx, [r9+1]; HandleCount
0x14001721d  call    cs:__imp_ProcessTrace
0x140017223  mov     rcx, [rsp+208h+HandleArray]; TraceHandle
0x140017228  call    cs:__imp_CloseTrace
0x14001722e  mov     eax, cs:?g_LogFileType@@3KA; ulong g_LogFileType
0x140017234  mov     [rdi], eax
0x140017236  mov     rcx, [rsp+208h+var_18]
0x14001723e  xor     rcx, rsp; StackCookie
0x140017241  call    __security_check_cookie
0x140017246  mov     rbx, [rsp+208h+arg_10]
0x14001724e  add     rsp, 200h
0x140017255  pop     rdi
0x140017256  retn
```
