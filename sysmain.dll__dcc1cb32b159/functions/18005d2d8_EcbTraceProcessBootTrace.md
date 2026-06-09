# EcbTraceProcessBootTrace

- ea: `0x18005d2d8`
- end: `0x18005d533`
- name: `EcbTraceProcessBootTrace`
- size: `603`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64 LastError, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001d394`

## callees

- `0x18001cb30`
- `0x18001ce0c`
- `0x180020bec`
- `0x180020ee8`
- `0x18005d2d8`
- `0x18007254c`
- `0x1800726b4`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005d391`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005d391`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d4bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d504`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d504`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005d4cd`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005d4cd`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005d39c`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005d39c`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005d43c`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005d477`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005d43c`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005d477`

## string_xrefs

- `0x18005d3b6`: `ERROR: Could not open trace %ws, error %d\n`

## pseudocode

```c
__int64 __fastcall EcbTraceProcessBootTrace(LPCRITICAL_SECTION lpCriticalSection, __int64 LastError, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  LARGE_INTEGER PerfFreq; // rax
  bool v10; // cc
  ULONG64 HandleArray; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v13[3]; // [rsp+28h] [rbp-D8h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268439552;
  Logfile.EventCallback = (PEVENT_CALLBACK)EcbTraceSingleEventCallback;
  Logfile.LogFileName = (LPWSTR)&lpCriticalSection[1].LockSemaphore;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)EcbTraceBufferCallback;
  v13[0] = lpCriticalSection;
  Logfile.Context = v13;
  v13[1] = a3;
  v13[2] = LastError;
  EcbFileNameHashInitialize(&lpCriticalSection[1], v6, v7, v8);
  EcbUtilsOut(16, "Loading %ws...\n", &lpCriticalSection[1].LockSemaphore);
  InitializeCriticalSection(lpCriticalSection);
  HandleArray = OpenTraceW(&Logfile);
  if ( HandleArray == -1 )
  {
    LastError = GetLastError();
    EcbUtilsOut(1, "ERROR: Could not open trace %ws, error %d\n", &lpCriticalSection[1].LockSemaphore, LastError);
    goto LABEL_13;
  }
  PerfFreq.QuadPart = 1;
  lpCriticalSection[14].LockSemaphore = 0;
  v10 = Logfile.LogfileHeader.PerfFreq.QuadPart <= 1;
  lpCriticalSection[14].SpinCount = 0;
  if ( !v10 )
    PerfFreq = Logfile.LogfileHeader.PerfFreq;
  lpCriticalSection[15].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)PerfFreq.QuadPart;
  lpCriticalSection[16].LockCount = 0;
  LODWORD(LastError) = RdBtTraceAddUnknownFileEntry(lpCriticalSection, a3, LastError);
  if ( !(_DWORD)LastError )
  {
    lpCriticalSection[16].RecursionCount = 1;
    ProcessTrace(&HandleArray, 1u, 0, 0);
    LODWORD(LastError) = lpCriticalSection[16].LockCount;
    if ( !(_DWORD)LastError )
    {
      if ( *(_DWORD *)lpCriticalSection[15].SpinCount )
      {
LABEL_8:
        LODWORD(LastError) = 995;
        goto LABEL_13;
      }
      lpCriticalSection[16].RecursionCount = 2;
      ProcessTrace(&HandleArray, 1u, 0, 0);
      LODWORD(LastError) = lpCriticalSection[16].LockCount;
      if ( !(_DWORD)LastError )
      {
        if ( *(_DWORD *)lpCriticalSection[15].SpinCount )
          goto LABEL_8;
        LODWORD(LastError) = EcbFileExtentsPhysicalToLogicalOrdered(&lpCriticalSection[16].LockSemaphore, a3);
        if ( !(_DWORD)LastError )
          LODWORD(LastError) = HIDWORD(lpCriticalSection[1450].SpinCount) == 0 ? 0x3EE : 0;
      }
    }
  }
LABEL_13:
  DeleteCriticalSection(lpCriticalSection);
  if ( HandleArray != -1 )
    CloseTrace(HandleArray);
  if ( (_DWORD)LastError )
  {
    EcbBootPlanPhaseCleanup(&lpCriticalSection[16].LockSemaphore, 1);
    EcbBootPlanPhaseCleanup(&lpCriticalSection[16].LockSemaphore, 0);
    EcbFileNameHashCleanup(&lpCriticalSection[1], 0);
    DeleteFileW((LPCWSTR)&lpCriticalSection[1].LockSemaphore);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005d2d8  mov     [rsp-8+arg_18], rbx
0x18005d2dd  push    rbp
0x18005d2de  push    rdi
0x18005d2df  push    r12
0x18005d2e1  push    r14
0x18005d2e3  push    r15
0x18005d2e5  lea     rbp, [rsp-110h]
0x18005d2ed  sub     rsp, 210h
0x18005d2f4  mov     rax, cs:__security_cookie
0x18005d2fb  xor     rax, rsp
0x18005d2fe  mov     [rbp+130h+var_30], rax
0x18005d305  mov     r14, r8
0x18005d308  mov     [rsp+230h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x18005d311  mov     rdi, rdx
0x18005d314  mov     rbx, rcx
0x18005d317  xor     edx, edx; Val
0x18005d319  lea     rcx, [rsp+230h+Logfile]; void *
0x18005d31e  mov     r8d, 1C0h; Size
0x18005d324  call    memset_0
0x18005d329  lea     rax, EcbTraceSingleEventCallback
0x18005d330  mov     dword ptr [rsp+230h+Logfile.1Ch], 10001000h
0x18005d338  mov     qword ptr [rbp+130h+Logfile.1A8h], rax
0x18005d33f  lea     r15, [rbx+40h]
0x18005d343  lea     rax, EcbTraceBufferCallback
0x18005d34a  mov     [rsp+230h+Logfile.LogFileName], r15
0x18005d34f  mov     [rbp+130h+Logfile.BufferCallback], rax
0x18005d356  lea     rcx, [rbx+28h]
0x18005d35a  lea     rax, [rsp+230h+var_208]
0x18005d35f  mov     [rsp+230h+var_208], rbx
0x18005d364  mov     [rbp+130h+Logfile.Context], rax
0x18005d36b  mov     [rsp+230h+var_200], r14
0x18005d370  mov     [rsp+230h+var_1F8], rdi
0x18005d375  call    EcbFileNameHashInitialize
0x18005d37a  lea     rdx, aLoadingWs; "Loading %ws...\n"
0x18005d381  mov     ecx, 10h
0x18005d386  mov     r8, r15
0x18005d389  call    EcbUtilsOut
0x18005d38e  mov     rcx, rbx; lpCriticalSection
0x18005d391  call    cs:__imp_InitializeCriticalSection
0x18005d397  lea     rcx, [rsp+230h+Logfile]; Logfile
0x18005d39c  call    cs:__imp_OpenTraceW
0x18005d3a2  mov     [rsp+230h+HandleArray], rax
0x18005d3a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d3ab  jnz     short loc_18005D3D1
0x18005d3ad  call    cs:__imp_GetLastError
0x18005d3b3  mov     r8, r15
0x18005d3b6  lea     rdx, aErrorCouldNotO; "ERROR: Could not open trace %ws, error "...
0x18005d3bd  mov     r9d, eax
0x18005d3c0  mov     ecx, 1
0x18005d3c5  mov     edi, eax
0x18005d3c7  call    EcbUtilsOut
0x18005d3cc  jmp     loc_18005D4B9
0x18005d3d1  mov     eax, 1
0x18005d3d6  mov     qword ptr [rbx+248h], 0
0x18005d3e1  cmp     qword ptr [rbp+130h+Logfile.LogfileHeader.PerfFreq], rax
0x18005d3e8  mov     r8, rdi
0x18005d3eb  mov     rdx, r14
0x18005d3ee  mov     qword ptr [rbx+250h], 0
0x18005d3f9  cmovg   rax, qword ptr [rbp+130h+Logfile.LogfileHeader.PerfFreq]
0x18005d401  mov     rcx, rbx
0x18005d404  mov     [rbx+258h], rax
0x18005d40b  mov     dword ptr [rbx+288h], 0
0x18005d415  call    RdBtTraceAddUnknownFileEntry
0x18005d41a  mov     edi, eax
0x18005d41c  test    eax, eax
0x18005d41e  jnz     loc_18005D4B9
0x18005d424  xor     r9d, r9d; EndTime
0x18005d427  mov     dword ptr [rbx+28Ch], 1
0x18005d431  xor     r8d, r8d; StartTime
0x18005d434  lea     edx, [rax+1]; HandleCount
0x18005d437  lea     rcx, [rsp+230h+HandleArray]; HandleArray
0x18005d43c  call    cs:__imp_ProcessTrace
0x18005d442  mov     edi, [rbx+288h]
0x18005d448  test    edi, edi
0x18005d44a  jnz     short loc_18005D4B9
0x18005d44c  mov     rax, [rbx+278h]
0x18005d453  cmp     [rax], edi
0x18005d455  jz      short loc_18005D45E
0x18005d457  mov     edi, 3E3h
0x18005d45c  jmp     short loc_18005D4B9
0x18005d45e  xor     r9d, r9d; EndTime
0x18005d461  mov     dword ptr [rbx+28Ch], 2
0x18005d46b  xor     r8d, r8d; StartTime
0x18005d46e  lea     rcx, [rsp+230h+HandleArray]; HandleArray
0x18005d473  lea     edx, [r9+1]; HandleCount
0x18005d477  call    cs:__imp_ProcessTrace
0x18005d47d  mov     edi, [rbx+288h]
0x18005d483  test    edi, edi
0x18005d485  jnz     short loc_18005D4B9
0x18005d487  mov     rax, [rbx+278h]
0x18005d48e  cmp     [rax], edi
0x18005d490  jnz     short loc_18005D457
0x18005d492  lea     rcx, [rbx+298h]
0x18005d499  mov     rdx, r14
0x18005d49c  call    EcbFileExtentsPhysicalToLogicalOrdered
0x18005d4a1  mov     edi, eax
0x18005d4a3  test    eax, eax
0x18005d4a5  jnz     short loc_18005D4B9
0x18005d4a7  mov     eax, [rbx+0E2B4h]
0x18005d4ad  neg     eax
0x18005d4af  sbb     edi, edi
0x18005d4b1  not     edi
0x18005d4b3  and     edi, 3EEh
0x18005d4b9  mov     rcx, rbx; lpCriticalSection
0x18005d4bc  call    cs:__imp_DeleteCriticalSection
0x18005d4c2  mov     rcx, [rsp+230h+HandleArray]; TraceHandle
0x18005d4c7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005d4cb  jz      short loc_18005D4D3
0x18005d4cd  call    cs:__imp_CloseTrace
0x18005d4d3  test    edi, edi
0x18005d4d5  jz      short loc_18005D50A
0x18005d4d7  mov     edx, 1
0x18005d4dc  lea     rcx, [rbx+298h]
0x18005d4e3  call    EcbBootPlanPhaseCleanup
0x18005d4e8  xor     edx, edx
0x18005d4ea  lea     rcx, [rbx+298h]
0x18005d4f1  call    EcbBootPlanPhaseCleanup
0x18005d4f6  xor     edx, edx
0x18005d4f8  lea     rcx, [rbx+28h]
0x18005d4fc  call    EcbFileNameHashCleanup
0x18005d501  mov     rcx, r15; lpFileName
0x18005d504  call    cs:__imp_DeleteFileW
0x18005d50a  mov     eax, edi
0x18005d50c  mov     rcx, [rbp+130h+var_30]
0x18005d513  xor     rcx, rsp; StackCookie
0x18005d516  call    __security_check_cookie
0x18005d51b  mov     rbx, [rsp+230h+arg_18]
0x18005d523  add     rsp, 210h
0x18005d52a  pop     r15
0x18005d52c  pop     r14
0x18005d52e  pop     r12
0x18005d530  pop     rdi
0x18005d531  pop     rbp
0x18005d532  retn
```
