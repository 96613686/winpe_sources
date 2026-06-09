# RawClockInit(ushort const *,unsigned __int64)

- ea: `0x14001e6d8`
- end: `0x14001e7a0`
- name: `?RawClockInit@@YAXPEBG_K@Z`
- size: `200`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018d04`

## callees

- `0x14001e6d8`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x14001e776`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x14001e776`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x14001e74c`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x14001e74c`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x14001e781`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x14001e781`

## pseudocode

```c
void __fastcall RawClockInit(WCHAR *a1)
{
  ULONG64 HandleArray[2]; // [rsp+20h] [rbp-1E8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.EventCallback = (PEVENT_CALLBACK)RawClockEventCallback;
  Logfile.LogFileName = a1;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)matherr;
  Logfile.LogFileMode = 268439552;
  Logfile.LogfileHeader.ReservedFlags = 0;
  HandleArray[0] = OpenTraceW(&Logfile);
  if ( HandleArray[0] != -1 )
  {
    dword_140083690 = 0;
    ProcessTrace(HandleArray, 1u, 0, 0);
    CloseTrace(HandleArray[0]);
  }
}

```

## disassembly

```asm
0x14001e6d8  push    rbx
0x14001e6da  sub     rsp, 200h
0x14001e6e1  mov     rax, cs:__security_cookie
0x14001e6e8  xor     rax, rsp
0x14001e6eb  mov     [rsp+208h+var_18], rax
0x14001e6f3  mov     rbx, rcx
0x14001e6f6  xor     edx, edx; Val
0x14001e6f8  lea     rcx, [rsp+208h+Logfile]; void *
0x14001e6fd  mov     r8d, 1C0h; Size
0x14001e703  call    memset_0
0x14001e708  lea     rax, RawClockEventCallback
0x14001e70f  mov     [rsp+208h+HandleArray], 0
0x14001e718  mov     qword ptr [rsp+208h+Logfile.1A8h], rax
0x14001e720  lea     rcx, [rsp+208h+Logfile]; Logfile
0x14001e725  lea     rax, _matherr
0x14001e72c  mov     [rsp+208h+Logfile.LogFileName], rbx
0x14001e731  mov     [rsp+208h+Logfile.BufferCallback], rax
0x14001e739  mov     dword ptr [rsp+208h+Logfile.1Ch], 10001000h
0x14001e741  mov     [rsp+208h+Logfile.LogfileHeader.ReservedFlags], 0
0x14001e74c  call    cs:__imp_OpenTraceW
0x14001e752  mov     [rsp+208h+HandleArray], rax
0x14001e757  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e75b  jz      short loc_14001E787
0x14001e75d  xor     r9d, r9d; EndTime
0x14001e760  mov     cs:dword_140083690, 0
0x14001e76a  xor     r8d, r8d; StartTime
0x14001e76d  lea     rcx, [rsp+208h+HandleArray]; HandleArray
0x14001e772  lea     edx, [r9+1]; HandleCount
0x14001e776  call    cs:__imp_ProcessTrace
0x14001e77c  mov     rcx, [rsp+208h+HandleArray]; TraceHandle
0x14001e781  call    cs:__imp_CloseTrace
0x14001e787  mov     rcx, [rsp+208h+var_18]
0x14001e78f  xor     rcx, rsp; StackCookie
0x14001e792  call    __security_check_cookie
0x14001e797  add     rsp, 200h
0x14001e79e  pop     rbx
0x14001e79f  retn
```
