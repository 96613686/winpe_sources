# OnProcess

- ea: `0x140018d04`
- end: `0x1400191f0`
- name: `OnProcess`
- size: `1260`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x140017398`

## callees

- `0x1400152e8`
- `0x14001601c`
- `0x1400164c4`
- `0x140016754`
- `0x140016a24`
- `0x140018d04`
- `0x14001e6d8`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400191bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400191bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400191ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400191ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140018d85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140018d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018efb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400190de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400190de`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140018f43`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140018f43`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x140019123`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x140019123`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x140018ea4`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x140018ea4`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x14001918e`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x14001918e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001910e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140019140`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001910e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140019140`
- `wevtapi!EvtIntCreateLocalLogfile` at `0x1400190ed`
- `wevtapi!EvtIntCreateLocalLogfile` at `0x1400190ed`

## pseudocode

```c
__int64 OnProcess()
{
  LPVOID v0; // rdi
  ULONG v1; // ebp
  ULONG v2; // esi
  unsigned int v4; // r14d
  HANDLE ProcessHeap; // rax
  struct _EVENT_TRACE_LOGFILEW *v6; // rax
  struct _EVENT_TRACE_LOGFILEW *v7; // rbx
  unsigned __int64 v8; // rdx
  LPWSTR LogFileName; // rax
  unsigned int v10; // r14d
  DWORD LastError; // ebx
  ULONG v12; // ebp
  int v13; // r15d
  int v14; // r15d
  PEVENT_TRACE_LOGFILEW v15; // rcx
  TRACEHANDLE v16; // rax
  int v17; // r14d
  const WCHAR *v18; // rcx
  int v19; // r14d
  struct _iobuf *v20; // rax
  struct _iobuf *v21; // rbx
  DWORD v22; // eax
  __int64 flag; // rcx
  int v24; // eax
  __int64 LocalLogfile; // rax
  __int64 v26; // r14
  TRACEHANDLE v27; // rcx
  PEVENT_TRACE_LOGFILEW v28; // r15
  HANDLE v29; // rax
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp-868h] BYREF
  PEVENT_TRACE_LOGFILEW Logfile[256]; // [rsp+C0h] [rbp-858h] BYREF

  v0 = g_TraceContext;
  memset_0(Logfile, 0, sizeof(Logfile));
  v1 = *((_DWORD *)v0 + 2);
  v2 = v1;
  if ( !v1 )
    v2 = *((_DWORD *)v0 + 3);
  if ( v2 >= 0x100 )
    return 4;
  v4 = 0;
  if ( v2 )
  {
    while ( 1 )
    {
      ProcessHeap = GetProcessHeap();
      v6 = (struct _EVENT_TRACE_LOGFILEW *)HeapAlloc(ProcessHeap, 8u, 0x1C0u);
      v7 = v6;
      Logfile[v4] = v6;
      if ( !v6 )
        break;
      memset_0(v6, 0, sizeof(struct _EVENT_TRACE_LOGFILEW));
      if ( v1 )
      {
        v7->BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)matherr;
        v7->LogFileName = (LPWSTR)*((_QWORD *)v0 + v4 + 3);
        CountFileBuffers();
      }
      else
      {
        v7->LoggerName = (LPWSTR)*((_QWORD *)v0 + v4 + 259);
        v7->LogFileMode = 256;
      }
      if ( ++v4 >= v2 )
        goto LABEL_11;
    }
    LastError = 14;
    goto LABEL_20;
  }
LABEL_11:
  if ( v2 == 1 && v1 )
  {
    if ( !Logfile[0]->LogFileName )
      goto LABEL_21;
    v8 = 0x7FFFFFFF;
    LogFileName = Logfile[0]->LogFileName;
    do
    {
      if ( !*LogFileName )
        break;
      ++LogFileName;
      --v8;
    }
    while ( v8 );
    if ( !v8 )
    {
LABEL_21:
      LastError = GetLastError();
LABEL_20:
      v12 = 0;
      goto LABEL_53;
    }
    RawClockInit(Logfile[0]->LogFileName, v8);
    v10 = 0;
LABEL_23:
    v13 = 0;
    if ( !v1 )
      v13 = 256;
    v14 = v13 | 0x10000000;
    while ( 1 )
    {
      v15 = Logfile[v10];
      v15->LogFileMode = v14;
      v15->LogFileMode = v14 | *((_DWORD *)v0 + 1604) & 0x1000;
      v15->LogfileHeader.ReservedFlags = 0;
      v15->BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)GetMoreBuffers;
      v15->EventCallback = (PEVENT_CALLBACK)GeneralEventCallback;
      v16 = OpenTraceW(v15);
      *((_QWORD *)v0 + v10 + 805) = v16;
      if ( v16 == -1 )
        goto LABEL_21;
      if ( ++v10 >= v2 )
        goto LABEL_28;
    }
  }
  dword_140083648 = 1;
  v10 = 0;
  if ( v2 )
    goto LABEL_23;
LABEL_28:
  v17 = *((_DWORD *)v0 + 1604);
  if ( (v17 & 0x80u) != 0 )
  {
    v18 = (const WCHAR *)*((_QWORD *)v0 + 773);
    if ( (v17 & 0x12000000) != 0 )
    {
      DeleteFileW(v18);
      LocalLogfile = EvtIntCreateLocalLogfile(*((_QWORD *)v0 + 773), 0);
      if ( !LocalLogfile )
        goto LABEL_31;
      *((_QWORD *)v0 + 1088) = LocalLogfile;
    }
    else
    {
      v19 = *((_DWORD *)v0 + 1604) & 0x20;
      v20 = TracerptWFopen(v18, v19 != 0, 0);
      v21 = v20;
      if ( !v20 )
      {
LABEL_31:
        v22 = GetLastError();
LABEL_51:
        LastError = v22;
        goto LABEL_52;
      }
      *((_QWORD *)v0 + 799) = v20;
      if ( v19 )
      {
        flag = (unsigned int)v20[1365]._flag;
        NumberOfBytesWritten = 0;
        if ( (unsigned __int64)(flag + 2) > 0xFFFF )
        {
          WriteFile(v20->_ptr, &v20->_cnt, flag, &NumberOfBytesWritten, 0);
          LODWORD(flag) = 0;
          v21[1365]._file += NumberOfBytesWritten;
          v21[1365]._flag = 0;
        }
        *(_WORD *)((char *)&v21->_cnt + (unsigned int)flag) = -257;
        v21[1365]._flag += 2;
      }
      v24 = *((_DWORD *)v0 + 1604);
      if ( (v24 & 0x9000000) != 0 )
      {
        TracerptFPrintf(v21, "<Events>\r\n");
      }
      else if ( (v24 & 0x200) != 0 )
      {
        TracerptFWPrintf(
          v21,
          L"%12hs, %10hs, %12hs, %10hs, %10hs, %10hs, %10hs, %10hs, %18hs, %10hs, %10hs, %20hs, %12hs, %20hs, %40hs, %40hs"
           ", %20hs, %10hs, %10hs, User Data\r\n",
          "Event Name",
          "Type",
          "Event ID",
          "Version",
          "Channel",
          "Level",
          "Opcode",
          "Task",
          "Keyword",
          "PID",
          "TID",
          "Processor Number",
          "Instance ID",
          "Parent Instance ID",
          "Activity ID",
          "Related Activity ID",
          "Clock-Time",
          "Kernel(ms)",
          "User(ms)");
      }
      else
      {
        TracerptFWPrintf(
          v21,
          L"%12hs, %10hs,%11hs,%21hs,%11hs,%11hs, User Data\r\n",
          "Event Name",
          "Type",
          "TID",
          "Clock-Time",
          "Kernel(ms)",
          "User(ms)");
      }
    }
  }
  if ( !v1 )
    GetSystemTimeAsFileTime(&CurrentSystem);
  LastError = ProcessTrace((PTRACEHANDLE)v0 + 805, v2, 0, 0);
  if ( !v1 && SystemTimeAsFileTime == -1 )
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  dword_1400820F4 = SystemTimeAsFileTime.dwLowDateTime - CurrentSystem.dwLowDateTime;
  if ( !LastError && (*((_DWORD *)v0 + 1604) & 0x20000000) != 0 )
  {
    v22 = ExportEventSchema(*((const unsigned __int16 **)v0 + 786));
    goto LABEL_51;
  }
LABEL_52:
  v12 = 0;
  if ( v2 )
  {
LABEL_53:
    v26 = 0;
    do
    {
      v27 = *((_QWORD *)v0 + v26 + 805);
      if ( v27 != -1 )
      {
        CloseTrace(v27);
        *((_QWORD *)v0 + v26 + 805) = -1;
      }
      v28 = Logfile[v26];
      if ( v28 )
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v28);
      }
      ++v12;
      ++v26;
    }
    while ( v12 < v2 );
  }
  return LastError;
}

```

## disassembly

```asm
0x140018d04  push    rbx
0x140018d06  push    rbp
0x140018d07  push    rsi
0x140018d08  push    rdi
0x140018d09  push    r12
0x140018d0b  push    r13
0x140018d0d  push    r14
0x140018d0f  push    r15
0x140018d11  sub     rsp, 8D8h
0x140018d18  mov     rax, cs:__security_cookie
0x140018d1f  xor     rax, rsp
0x140018d22  mov     [rsp+918h+var_58], rax
0x140018d2a  mov     rdi, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140018d31  lea     rcx, [rsp+918h+Logfile]; void *
0x140018d39  xor     edx, edx; Val
0x140018d3b  mov     r8d, 800h; Size
0x140018d41  call    memset_0
0x140018d46  mov     ebp, [rdi+8]
0x140018d49  xor     r12d, r12d
0x140018d4c  mov     esi, ebp
0x140018d4e  test    ebp, ebp
0x140018d50  jnz     short loc_140018D55
0x140018d52  mov     esi, [rdi+0Ch]
0x140018d55  mov     r13d, 100h
0x140018d5b  cmp     esi, r13d
0x140018d5e  jb      short loc_140018D6A
0x140018d60  mov     eax, 4
0x140018d65  jmp     loc_1400191CC
0x140018d6a  mov     r14d, r12d
0x140018d6d  test    esi, esi
0x140018d6f  jz      short loc_140018DEB
0x140018d71  call    cs:__imp_GetProcessHeap
0x140018d77  mov     edx, 8; dwFlags
0x140018d7c  mov     r8d, 1C0h; dwBytes
0x140018d82  mov     rcx, rax; hHeap
0x140018d85  call    cs:__imp_HeapAlloc
0x140018d8b  mov     r15d, r14d
0x140018d8e  mov     rbx, rax
0x140018d91  mov     [rsp+r15*8+918h+Logfile], rax
0x140018d99  test    rax, rax
0x140018d9c  jz      loc_140018E2B
0x140018da2  xor     edx, edx; Val
0x140018da4  mov     r8d, 1C0h; Size
0x140018daa  mov     rcx, rax; void *
0x140018dad  call    memset_0
0x140018db2  test    ebp, ebp
0x140018db4  jnz     short loc_140018DC8
0x140018db6  mov     rcx, [rdi+r15*8+818h]
0x140018dbe  mov     [rbx+8], rcx
0x140018dc2  mov     [rbx+1Ch], r13d
0x140018dc6  jmp     short loc_140018DE3
0x140018dc8  lea     rax, _matherr
0x140018dcf  mov     [rbx+190h], rax
0x140018dd6  mov     rcx, [rdi+r15*8+18h]
0x140018ddb  mov     [rbx], rcx
0x140018dde  call    CountFileBuffers
0x140018de3  inc     r14d
0x140018de6  cmp     r14d, esi
0x140018de9  jb      short loc_140018D71
0x140018deb  cmp     esi, 1
0x140018dee  jnz     short loc_140018E42
0x140018df0  test    ebp, ebp
0x140018df2  jz      short loc_140018E42
0x140018df4  mov     rax, [rsp+918h+Logfile]
0x140018dfc  mov     rcx, [rax]; unsigned __int16 *
0x140018dff  test    rcx, rcx
0x140018e02  jz      short loc_140018E38
0x140018e04  mov     edx, 7FFFFFFFh
0x140018e09  mov     rax, rcx
0x140018e0c  cmp     [rax], r12w
0x140018e10  jz      short loc_140018E1C
0x140018e12  add     rax, 2
0x140018e16  sub     rdx, 1; unsigned __int64
0x140018e1a  jnz     short loc_140018E0C
0x140018e1c  test    rdx, rdx
0x140018e1f  jz      short loc_140018E38
0x140018e21  call    ?RawClockInit@@YAXPEBG_K@Z; RawClockInit(ushort const *,unsigned __int64)
0x140018e26  mov     r14d, r12d
0x140018e29  jmp     short loc_140018E53
0x140018e2b  mov     ebx, 0Eh
0x140018e30  mov     ebp, r12d
0x140018e33  jmp     loc_14001917D
0x140018e38  call    cs:__imp_GetLastError
0x140018e3e  mov     ebx, eax
0x140018e40  jmp     short loc_140018E30
0x140018e42  mov     cs:dword_140083648, 1
0x140018e4c  mov     r14d, r12d
0x140018e4f  test    esi, esi
0x140018e51  jz      short loc_140018EC0
0x140018e53  test    ebp, ebp
0x140018e55  mov     r15d, r12d
0x140018e58  cmovz   r15d, r13d
0x140018e5c  bts     r15d, 1Ch
0x140018e61  mov     ebx, r14d
0x140018e64  mov     rcx, [rsp+rbx*8+918h+Logfile]; Logfile
0x140018e6c  mov     [rcx+1Ch], r15d
0x140018e70  mov     eax, [rdi+1910h]
0x140018e76  and     eax, 1000h
0x140018e7b  or      eax, r15d
0x140018e7e  mov     [rcx+1Ch], eax
0x140018e81  lea     rax, GetMoreBuffers
0x140018e88  mov     [rcx+188h], r12d
0x140018e8f  mov     [rcx+190h], rax
0x140018e96  lea     rax, ?GeneralEventCallback@@YAXPEAU_EVENT_RECORD@@@Z; GeneralEventCallback(_EVENT_RECORD *)
0x140018e9d  mov     [rcx+1A8h], rax
0x140018ea4  call    cs:__imp_OpenTraceW
0x140018eaa  mov     [rdi+rbx*8+1928h], rax
0x140018eb2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140018eb6  jz      short loc_140018E38
0x140018eb8  inc     r14d
0x140018ebb  cmp     r14d, esi
0x140018ebe  jb      short loc_140018E61
0x140018ec0  mov     r14d, [rdi+1910h]
0x140018ec7  test    r14b, r14b
0x140018eca  jns     loc_140019103
0x140018ed0  mov     rcx, [rdi+1828h]; unsigned __int16 *
0x140018ed7  test    r14d, 12000000h
0x140018ede  jnz     loc_1400190DE
0x140018ee4  and     r14d, 20h
0x140018ee8  setnz   dl; unsigned __int8
0x140018eeb  xor     r8d, r8d; unsigned __int8
0x140018eee  call    ?TracerptWFopen@@YAPEAU_iobuf@@PEBGEE@Z; TracerptWFopen(ushort const *,uchar,uchar)
0x140018ef3  mov     rbx, rax
0x140018ef6  test    rax, rax
0x140018ef9  jnz     short loc_140018F06
0x140018efb  call    cs:__imp_GetLastError
0x140018f01  jmp     loc_140019174
0x140018f06  mov     [rdi+18F8h], rbx
0x140018f0d  test    r14d, r14d
0x140018f10  jz      short loc_140018F70
0x140018f12  mov     ecx, [rax+10008h]
0x140018f18  mov     [rsp+918h+NumberOfBytesWritten], r12d
0x140018f20  lea     rax, [rcx+2]
0x140018f24  cmp     rax, 0FFFFh
0x140018f2a  jbe     short loc_140018F60
0x140018f2c  mov     r8d, ecx; nNumberOfBytesToWrite
0x140018f2f  mov     [rsp+918h+lpOverlapped], r12; lpOverlapped
0x140018f34  mov     rcx, [rbx]; hFile
0x140018f37  lea     rdx, [rbx+8]; lpBuffer
0x140018f3b  lea     r9, [rsp+918h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140018f43  call    cs:__imp_WriteFile
0x140018f49  mov     eax, [rsp+918h+NumberOfBytesWritten]
0x140018f50  mov     ecx, r12d
0x140018f53  add     [rbx+1000Ch], eax
0x140018f59  mov     [rbx+10008h], r12d
0x140018f60  mov     eax, ecx
0x140018f62  mov     word ptr [rax+rbx+8], 0FEFFh
0x140018f69  add     dword ptr [rbx+10008h], 2
0x140018f70  mov     eax, [rdi+1910h]
0x140018f76  test    eax, 9000000h
0x140018f7b  jnz     loc_1400190CD
0x140018f81  bt      eax, 9
0x140018f85  lea     rax, aUserMs; "User(ms)"
0x140018f8c  jnb     loc_140019085
0x140018f92  mov     [rsp+918h+var_878], rax
0x140018f9a  lea     r9, aType; "Type"
0x140018fa1  lea     rax, aKernelMs; "Kernel(ms)"
0x140018fa8  mov     rcx, rbx; struct _iobuf *
0x140018fab  mov     [rsp+918h+var_880], rax
0x140018fb3  lea     r8, aEventName; "Event Name"
0x140018fba  lea     rax, aClockTime; "Clock-Time"
0x140018fc1  mov     [rsp+918h+var_888], rax
0x140018fc9  lea     rdx, a12hs10hs12hs10; "%12hs, %10hs, %12hs, %10hs, %10hs, %10h"...
0x140018fd0  lea     rax, aRelatedActivit; "Related Activity ID"
0x140018fd7  mov     [rsp+918h+var_890], rax
0x140018fdf  lea     rax, aActivityId; "Activity ID"
0x140018fe6  mov     [rsp+918h+var_898], rax
0x140018fee  lea     rax, aParentInstance; "Parent Instance ID"
0x140018ff5  mov     [rsp+918h+var_8A0], rax
0x140018ffa  lea     rax, aInstanceId; "Instance ID"
0x140019001  mov     [rsp+918h+var_8A8], rax
0x140019006  lea     rax, aProcessorNumbe; "Processor Number"
0x14001900d  mov     [rsp+918h+var_8B0], rax
0x140019012  lea     rax, aTid; "TID"
0x140019019  mov     [rsp+918h+var_8B8], rax
0x14001901e  lea     rax, aPid; "PID"
0x140019025  mov     [rsp+918h+var_8C0], rax
0x14001902a  lea     rax, aKeyword_0; "Keyword"
0x140019031  mov     [rsp+918h+var_8C8], rax
0x140019036  lea     rax, aTask_1; "Task"
0x14001903d  mov     [rsp+918h+var_8D0], rax
0x140019042  lea     rax, aOpcode_2; "Opcode"
0x140019049  mov     [rsp+918h+var_8D8], rax
0x14001904e  lea     rax, aLevel_1; "Level"
0x140019055  mov     [rsp+918h+var_8E0], rax
0x14001905a  lea     rax, aChannel_1; "Channel"
0x140019061  mov     [rsp+918h+var_8E8], rax
0x140019066  lea     rax, aVersion_0; "Version"
0x14001906d  mov     [rsp+918h+var_8F0], rax
0x140019072  lea     rax, aEventId; "Event ID"
0x140019079  mov     [rsp+918h+lpOverlapped], rax
0x14001907e  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140019083  jmp     short loc_140019103
0x140019085  mov     [rsp+918h+var_8E0], rax
0x14001908a  lea     r9, aType; "Type"
0x140019091  lea     rax, aKernelMs; "Kernel(ms)"
0x140019098  mov     rcx, rbx; struct _iobuf *
0x14001909b  mov     [rsp+918h+var_8E8], rax
0x1400190a0  lea     r8, aEventName; "Event Name"
0x1400190a7  lea     rax, aClockTime; "Clock-Time"
0x1400190ae  mov     [rsp+918h+var_8F0], rax
0x1400190b3  lea     rdx, a12hs10hs11hs21; "%12hs, %10hs,%11hs,%21hs,%11hs,%11hs, U"...
0x1400190ba  lea     rax, aTid; "TID"
0x1400190c1  mov     [rsp+918h+lpOverlapped], rax
0x1400190c6  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400190cb  jmp     short loc_140019103
0x1400190cd  lea     rdx, aEvents_3; "<Events>\r\n"
0x1400190d4  mov     rcx, rbx; struct _iobuf *
0x1400190d7  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400190dc  jmp     short loc_140019103
0x1400190de  call    cs:__imp_DeleteFileW
0x1400190e4  mov     rcx, [rdi+1828h]
0x1400190eb  xor     edx, edx
0x1400190ed  call    cs:__imp_EvtIntCreateLocalLogfile
0x1400190f3  test    rax, rax
0x1400190f6  jz      loc_140018EFB
0x1400190fc  mov     [rdi+2200h], rax
0x140019103  test    ebp, ebp
0x140019105  jnz     short loc_140019114
0x140019107  lea     rcx, ?CurrentSystem@@3U_SYSTEM_RECORD@@A; lpSystemTimeAsFileTime
0x14001910e  call    cs:__imp_GetSystemTimeAsFileTime
0x140019114  lea     rcx, [rdi+1928h]; HandleArray
0x14001911b  xor     r9d, r9d; EndTime
0x14001911e  xor     r8d, r8d; StartTime
0x140019121  mov     edx, esi; HandleCount
0x140019123  call    cs:__imp_ProcessTrace
0x140019129  mov     ebx, eax
0x14001912b  test    ebp, ebp
0x14001912d  jnz     short loc_140019146
0x14001912f  cmp     qword ptr cs:SystemTimeAsFileTime.dwLowDateTime, 0FFFFFFFFFFFFFFFFh
0x140019137  jnz     short loc_140019146
0x140019139  lea     rcx, SystemTimeAsFileTime; lpSystemTimeAsFileTime
0x140019140  call    cs:__imp_GetSystemTimeAsFileTime
0x140019146  mov     eax, cs:SystemTimeAsFileTime.dwLowDateTime
0x14001914c  sub     eax, cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140019152  mov     cs:dword_1400820F4, eax
0x140019158  test    ebx, ebx
0x14001915a  jnz     short loc_140019176
0x14001915c  test    dword ptr [rdi+1910h], 20000000h
0x140019166  jz      short loc_140019176
0x140019168  mov     rcx, [rdi+1890h]; unsigned __int16 *
0x14001916f  call    ?ExportEventSchema@@YAKPEBG@Z; ExportEventSchema(ushort const *)
0x140019174  mov     ebx, eax
0x140019176  mov     ebp, r12d
0x140019179  test    esi, esi
0x14001917b  jz      short loc_1400191CA
0x14001917d  mov     r14, r12
0x140019180  mov     rcx, [rdi+r14*8+1928h]; TraceHandle
0x140019188  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001918c  jz      short loc_1400191A0
0x14001918e  call    cs:__imp_CloseTrace
0x140019194  mov     qword ptr [rdi+r14*8+1928h], 0FFFFFFFFFFFFFFFFh
0x1400191a0  mov     r15, [rsp+r14*8+918h+Logfile]
0x1400191a8  test    r15, r15
0x1400191ab  jz      short loc_1400191C1
0x1400191ad  call    cs:__imp_GetProcessHeap
0x1400191b3  mov     r8, r15; lpMem
0x1400191b6  xor     edx, edx; dwFlags
0x1400191b8  mov     rcx, rax; hHeap
0x1400191bb  call    cs:__imp_HeapFree
0x1400191c1  inc     ebp
0x1400191c3  inc     r14
0x1400191c6  cmp     ebp, esi
0x1400191c8  jb      short loc_140019180
0x1400191ca  mov     eax, ebx
0x1400191cc  mov     rcx, [rsp+918h+var_58]
0x1400191d4  xor     rcx, rsp; StackCookie
0x1400191d7  call    __security_check_cookie
0x1400191dc  add     rsp, 8D8h
0x1400191e3  pop     r15
0x1400191e5  pop     r14
0x1400191e7  pop     r13
0x1400191e9  pop     r12
0x1400191eb  pop     rdi
0x1400191ec  pop     rsi
0x1400191ed  pop     rbp
0x1400191ee  pop     rbx
0x1400191ef  retn
```
