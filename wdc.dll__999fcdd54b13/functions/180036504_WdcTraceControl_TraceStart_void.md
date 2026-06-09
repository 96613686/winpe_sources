# WdcTraceControl::TraceStart(void)

- ea: `0x180036504`
- end: `0x1800369d0`
- name: `?TraceStart@WdcTraceControl@@AEAAJXZ`
- size: `1228`
- prototype: `__int64 __fastcall(WdcTraceControl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002415c`

## callees

- `0x18000b854`
- `0x180033698`
- `0x180036504`
- `0x18003a3c0`
- `0x18003b0ac`

## import_xrefs

- `ADVAPI32!CloseTrace` at `0x18003696a`
- `ADVAPI32!CloseTrace` at `0x18003696a`
- `ADVAPI32!StopTraceW` at `0x18003694d`
- `ADVAPI32!StopTraceW` at `0x18003694d`
- `ADVAPI32!OpenTraceW` at `0x180036567`
- `ADVAPI32!OpenTraceW` at `0x180036567`
- `ADVAPI32!StartTraceW` at `0x1800366f9`
- `ADVAPI32!StartTraceW` at `0x1800366f9`
- `ADVAPI32!EnableTraceEx` at `0x180036754`
- `ADVAPI32!EnableTraceEx` at `0x1800367a3`
- `ADVAPI32!EnableTraceEx` at `0x1800367ee`
- `ADVAPI32!EnableTraceEx` at `0x18003683d`
- `ADVAPI32!EnableTraceEx` at `0x180036888`
- `ADVAPI32!EnableTraceEx` at `0x1800368cf`
- `ADVAPI32!EnableTraceEx` at `0x180036754`
- `ADVAPI32!EnableTraceEx` at `0x1800367a3`
- `ADVAPI32!EnableTraceEx` at `0x1800367ee`
- `ADVAPI32!EnableTraceEx` at `0x18003683d`
- `ADVAPI32!EnableTraceEx` at `0x180036888`
- `ADVAPI32!EnableTraceEx` at `0x1800368cf`
- `KERNEL32!CloseHandle` at `0x1800369a1`
- `KERNEL32!CloseHandle` at `0x1800369a1`
- `KERNEL32!GetLastError` at `0x180036583`
- `KERNEL32!GetLastError` at `0x1800365e7`
- `KERNEL32!GetLastError` at `0x18003660d`
- `KERNEL32!GetLastError` at `0x180036629`
- `KERNEL32!GetLastError` at `0x180036656`
- `KERNEL32!GetLastError` at `0x180036583`
- `KERNEL32!GetLastError` at `0x1800365e7`
- `KERNEL32!GetLastError` at `0x18003660d`
- `KERNEL32!GetLastError` at `0x180036629`
- `KERNEL32!GetLastError` at `0x180036656`
- `KERNEL32!SetLastError` at `0x1800365a7`
- `KERNEL32!SetLastError` at `0x1800365a7`
- `KERNEL32!UnmapViewOfFile` at `0x180036987`
- `KERNEL32!UnmapViewOfFile` at `0x180036987`
- `KERNEL32!CreateFileMappingW` at `0x1800365d2`
- `KERNEL32!CreateFileMappingW` at `0x1800365d2`
- `KERNEL32!MapViewOfFile` at `0x180036644`
- `KERNEL32!MapViewOfFile` at `0x180036644`

## pseudocode

```c
__int64 __fastcall WdcTraceControl::TraceStart(WdcTraceControl *this)
{
  TRACEHANDLE v2; // rax
  signed int LastError; // eax
  signed int v4; // edi
  HANDLE *v5; // rsi
  HANDLE FileMappingW; // rax
  signed int v7; // eax
  signed int v8; // eax
  DWORD v9; // ebx
  LPVOID v10; // rax
  WdcTraceControl *v11; // rcx
  signed int inited; // eax
  PEVENT_TRACE_PROPERTIES *v13; // rbx
  signed int started; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  WdcTraceControl *v21; // rcx
  _QWORD *v22; // rax
  TRACEHANDLE v23; // rcx
  const void *v24; // rcx
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-248h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+50h] [rbp-218h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268439808;
  Logfile.EventCallback = (PEVENT_CALLBACK)WdcTraceControl::CallbackEvent;
  Logfile.LoggerName = (LPWSTR)L"WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE951";
  v2 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 28) = v2;
  if ( v2 == -1 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = (HANDLE *)((char *)this + 240);
LABEL_59:
      inited = v4;
      goto LABEL_60;
    }
  }
  SetLastError(0);
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   0,
                   4u,
                   0,
                   8u,
                   L"Global\\WDC.7B5C49BF-AE36-4B4B-9C2A-A1E727F6429B");
  v5 = (HANDLE *)((char *)this + 240);
  *((_QWORD *)this + 30) = FileMappingW;
  if ( !FileMappingW )
  {
    v7 = GetLastError();
    v4 = v7;
    if ( !v7 )
      goto LABEL_23;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  if ( *v5 != (HANDLE)-1LL )
    goto LABEL_16;
  v8 = GetLastError();
  v4 = v8;
  if ( !v8 )
  {
LABEL_23:
    v4 = -2147467259;
    goto LABEL_59;
  }
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_59;
LABEL_16:
  v9 = GetLastError();
  v10 = MapViewOfFile(*v5, 0xF001Fu, 0, 0, 8u);
  *((_QWORD *)this + 31) = v10;
  if ( !v10 )
  {
    inited = GetLastError();
    if ( inited > 0 )
      inited = (unsigned __int16)inited | 0x80070000;
    if ( inited >= 0 )
      inited = -2147467259;
    v4 = inited;
    goto LABEL_60;
  }
  if ( v9 == 183 )
    return 0;
  v13 = (PEVENT_TRACE_PROPERTIES *)((char *)this + 232);
  inited = WdcTraceControl::TraceInitProperties(v11, (struct _EVENT_TRACE_PROPERTIES **)this + 29, 0);
  v4 = inited;
  if ( inited < 0 )
  {
LABEL_60:
    dwMaximumSizeLow[0] = inited;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcTraceControl::TraceStart",
      0,
      L"FAILURE: 0x%08x",
      *(_QWORD *)dwMaximumSizeLow);
    if ( v4 < 0 )
    {
      v22 = (_QWORD *)*((_QWORD *)this + 31);
      if ( v22 && *v22 )
      {
        WdcTraceControl::TraceInitProperties(v21, (struct _EVENT_TRACE_PROPERTIES **)this + 29, 0);
        StopTraceW(0, L"WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE951", *((PEVENT_TRACE_PROPERTIES *)this + 29));
        **((_QWORD **)this + 31) = 0;
      }
      v23 = *((_QWORD *)this + 28);
      if ( v23 != -1 )
      {
        CloseTrace(v23);
        *((_QWORD *)this + 28) = -1;
      }
      v24 = (const void *)*((_QWORD *)this + 31);
      if ( v24 )
      {
        UnmapViewOfFile(v24);
        *((_QWORD *)this + 31) = 0;
      }
      if ( (char *)*v5 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(*v5);
        *v5 = 0;
      }
    }
    return (unsigned int)v4;
  }
  (*v13)->BufferSize = 64;
  (*v13)->MinimumBuffers = 16;
  (*v13)->LogFileMode = 256;
  (*v13)->Wnode.ClientContext = 3;
  (*v13)->FlushTimer = 1;
  started = StartTraceW(*((PTRACEHANDLE *)this + 31), L"WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE951", *v13);
  v4 = started;
  if ( started )
  {
    if ( started > 0 )
      v4 = (unsigned __int16)started | 0x80070000;
    if ( (unsigned __int16)v4 == 183 )
      return 0;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 < 0 )
    goto LABEL_59;
  v15 = EnableTraceEx(&ThreadPoolGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0, 0, 0, 0);
  v4 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  v16 = EnableTraceEx(&PsProvGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0x20u, 0, 0, 0);
  v4 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v4 = (unsigned __int16)v16 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  v17 = EnableTraceEx(&DiskProvGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0, 0, 0, 0);
  v4 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v4 = (unsigned __int16)v17 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  v18 = EnableTraceEx(&FileProvGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0x10u, 0, 0, 0);
  v4 = v18;
  if ( v18 )
  {
    if ( v18 > 0 )
      v4 = (unsigned __int16)v18 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  v19 = EnableTraceEx(&NetProvGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0, 0, 0, 0);
  v4 = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      v4 = (unsigned __int16)v19 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_59;
  }
  v20 = EnableTraceEx(&WdcRundownProvGuid, 0, **((_QWORD **)this + 31), 1u, 0, 0, 0, 0, 0);
  v4 = 0;
  if ( v20 )
  {
    if ( v20 > 0 )
      v4 = (unsigned __int16)v20 | 0x80070000;
    else
      v4 = v20;
  }
  if ( v4 < 0 )
    goto LABEL_59;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036504  push    rbx
0x180036506  push    rbp
0x180036507  push    rsi
0x180036508  push    rdi
0x180036509  push    r12
0x18003650b  push    r13
0x18003650d  push    r14
0x18003650f  push    r15
0x180036511  sub     rsp, 228h
0x180036518  mov     rax, cs:__security_cookie
0x18003651f  xor     rax, rsp
0x180036522  mov     [rsp+268h+var_58], rax
0x18003652a  mov     rbp, rcx
0x18003652d  xor     edx, edx; Val
0x18003652f  lea     rcx, [rsp+268h+Logfile]; void *
0x180036534  mov     r8d, 1C0h; Size
0x18003653a  call    memset_0
0x18003653f  lea     rax, ?CallbackEvent@WdcTraceControl@@CAXPEAU_EVENT_RECORD@@@Z; WdcTraceControl::CallbackEvent(_EVENT_RECORD *)
0x180036546  mov     dword ptr [rsp+268h+Logfile.1Ch], 10001100h
0x18003654e  lea     r12, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x180036555  mov     qword ptr [rsp+268h+Logfile.1A8h], rax
0x18003655d  lea     rcx, [rsp+268h+Logfile]; Logfile
0x180036562  mov     [rsp+268h+Logfile.LoggerName], r12
0x180036567  call    cs:__imp_OpenTraceW
0x18003656d  xor     r14d, r14d
0x180036570  mov     [rbp+0E0h], rax
0x180036577  mov     r15d, 80070000h
0x18003657d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036581  jnz     short loc_1800365A5
0x180036583  call    cs:__imp_GetLastError
0x180036589  mov     edi, eax
0x18003658b  test    eax, eax
0x18003658d  jle     short loc_180036595
0x18003658f  movzx   edi, ax
0x180036592  or      edi, r15d
0x180036595  test    edi, edi
0x180036597  jns     short loc_1800365A5
0x180036599  lea     rsi, [rbp+0F0h]
0x1800365a0  jmp     loc_1800368F7
0x1800365a5  xor     ecx, ecx; dwErrCode
0x1800365a7  call    cs:__imp_SetLastError
0x1800365ad  mov     r12d, 8
0x1800365b3  lea     rax, aGlobalWdc7b5c4; "Global\\WDC.7B5C49BF-AE36-4B4B-9C2A-A1E"...
0x1800365ba  mov     [rsp+268h+lpName], rax; lpName
0x1800365bf  xor     r9d, r9d; dwMaximumSizeHigh
0x1800365c2  xor     edx, edx; lpFileMappingAttributes
0x1800365c4  mov     [rsp+268h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x1800365c9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800365cd  lea     r8d, [r12-4]; flProtect
0x1800365d2  call    cs:__imp_CreateFileMappingW
0x1800365d8  lea     rsi, [rbp+0F0h]
0x1800365df  mov     [rsi], rax
0x1800365e2  test    rax, rax
0x1800365e5  jnz     short loc_180036607
0x1800365e7  call    cs:__imp_GetLastError
0x1800365ed  mov     edi, eax
0x1800365ef  test    eax, eax
0x1800365f1  jz      loc_18003667E
0x1800365f7  jle     short loc_1800365FF
0x1800365f9  movzx   edi, ax
0x1800365fc  or      edi, r15d
0x1800365ff  test    edi, edi
0x180036601  js      loc_1800368F0
0x180036607  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18003660b  jnz     short loc_180036629
0x18003660d  call    cs:__imp_GetLastError
0x180036613  mov     edi, eax
0x180036615  test    eax, eax
0x180036617  jz      short loc_18003667E
0x180036619  jle     short loc_180036621
0x18003661b  movzx   edi, ax
0x18003661e  or      edi, r15d
0x180036621  test    edi, edi
0x180036623  js      loc_1800368F0
0x180036629  call    cs:__imp_GetLastError
0x18003662f  mov     rcx, [rsi]; hFileMappingObject
0x180036632  xor     r9d, r9d; dwFileOffsetLow
0x180036635  xor     r8d, r8d; dwFileOffsetHigh
0x180036638  mov     qword ptr [rsp+268h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x18003663d  mov     edx, 0F001Fh; dwDesiredAccess
0x180036642  mov     ebx, eax
0x180036644  call    cs:__imp_MapViewOfFile
0x18003664a  mov     [rbp+0F8h], rax
0x180036651  test    rax, rax
0x180036654  jnz     short loc_180036688
0x180036656  call    cs:__imp_GetLastError
0x18003665c  test    eax, eax
0x18003665e  jle     short loc_180036666
0x180036660  movzx   eax, ax
0x180036663  or      eax, r15d
0x180036666  mov     edi, 80004005h
0x18003666b  test    eax, eax
0x18003666d  cmovns  eax, edi
0x180036670  mov     edi, eax
0x180036672  lea     r12, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x180036679  jmp     loc_1800368F9
0x18003667e  mov     edi, 80004005h
0x180036683  jmp     loc_1800368F0
0x180036688  mov     r12d, 0B7h
0x18003668e  cmp     ebx, r12d
0x180036691  jnz     short loc_18003669B
0x180036693  mov     edi, r14d
0x180036696  jmp     loc_1800369AA
0x18003669b  lea     rbx, [rbp+0E8h]
0x1800366a2  xor     r8d, r8d; int
0x1800366a5  mov     rdx, rbx; struct _EVENT_TRACE_PROPERTIES **
0x1800366a8  call    ?TraceInitProperties@WdcTraceControl@@AEAAJPEAPEAU_EVENT_TRACE_PROPERTIES@@H@Z; WdcTraceControl::TraceInitProperties(_EVENT_TRACE_PROPERTIES * *,int)
0x1800366ad  mov     edi, eax
0x1800366af  test    eax, eax
0x1800366b1  js      short loc_180036672
0x1800366b3  mov     rax, [rbx]
0x1800366b6  lea     rdx, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x1800366bd  mov     r13d, 1
0x1800366c3  mov     dword ptr [rax+30h], 40h ; '@'
0x1800366ca  mov     rax, [rbx]
0x1800366cd  mov     dword ptr [rax+34h], 10h
0x1800366d4  mov     rax, [rbx]
0x1800366d7  mov     dword ptr [rax+40h], 100h
0x1800366de  mov     rax, [rbx]
0x1800366e1  mov     dword ptr [rax+28h], 3
0x1800366e8  mov     rax, [rbx]
0x1800366eb  mov     [rax+44h], r13d
0x1800366ef  mov     r8, [rbx]; Properties
0x1800366f2  mov     rcx, [rbp+0F8h]; TraceHandle
0x1800366f9  call    cs:__imp_StartTraceW
0x1800366ff  mov     edi, eax
0x180036701  test    eax, eax
0x180036703  jz      short loc_18003671A
0x180036705  jle     short loc_18003670D
0x180036707  movzx   edi, ax
0x18003670a  or      edi, r15d
0x18003670d  movzx   eax, di
0x180036710  cmp     eax, r12d
0x180036713  jnz     short loc_18003671D
0x180036715  jmp     loc_180036693
0x18003671a  mov     edi, r14d
0x18003671d  test    edi, edi
0x18003671f  js      loc_1800368F0
0x180036725  mov     r8, [rbp+0F8h]
0x18003672c  lea     rcx, ThreadPoolGuid; ProviderId
0x180036733  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x180036738  mov     r9d, r13d; IsEnabled
0x18003673b  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x180036740  xor     edx, edx; SourceId
0x180036742  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x180036747  mov     r8, [r8]; TraceHandle
0x18003674a  mov     [rsp+268h+lpName], r14; MatchAnyKeyword
0x18003674f  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x180036754  call    cs:__imp_EnableTraceEx
0x18003675a  mov     edi, eax
0x18003675c  test    eax, eax
0x18003675e  jz      short loc_180036770
0x180036760  jle     short loc_180036768
0x180036762  movzx   edi, ax
0x180036765  or      edi, r15d
0x180036768  test    edi, edi
0x18003676a  js      loc_1800368F0
0x180036770  mov     r8, [rbp+0F8h]
0x180036777  lea     rcx, PsProvGuid; ProviderId
0x18003677e  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x180036783  mov     r9d, r13d; IsEnabled
0x180036786  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x18003678b  xor     edx, edx; SourceId
0x18003678d  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x180036792  mov     r8, [r8]; TraceHandle
0x180036795  mov     [rsp+268h+lpName], 20h ; ' '; MatchAnyKeyword
0x18003679e  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x1800367a3  call    cs:__imp_EnableTraceEx
0x1800367a9  mov     edi, eax
0x1800367ab  test    eax, eax
0x1800367ad  jz      short loc_1800367BF
0x1800367af  jle     short loc_1800367B7
0x1800367b1  movzx   edi, ax
0x1800367b4  or      edi, r15d
0x1800367b7  test    edi, edi
0x1800367b9  js      loc_1800368F0
0x1800367bf  mov     r8, [rbp+0F8h]
0x1800367c6  lea     rcx, DiskProvGuid; ProviderId
0x1800367cd  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x1800367d2  mov     r9d, r13d; IsEnabled
0x1800367d5  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x1800367da  xor     edx, edx; SourceId
0x1800367dc  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x1800367e1  mov     r8, [r8]; TraceHandle
0x1800367e4  mov     [rsp+268h+lpName], r14; MatchAnyKeyword
0x1800367e9  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x1800367ee  call    cs:__imp_EnableTraceEx
0x1800367f4  mov     edi, eax
0x1800367f6  test    eax, eax
0x1800367f8  jz      short loc_18003680A
0x1800367fa  jle     short loc_180036802
0x1800367fc  movzx   edi, ax
0x1800367ff  or      edi, r15d
0x180036802  test    edi, edi
0x180036804  js      loc_1800368F0
0x18003680a  mov     r8, [rbp+0F8h]
0x180036811  lea     rcx, FileProvGuid; ProviderId
0x180036818  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x18003681d  mov     r9d, r13d; IsEnabled
0x180036820  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x180036825  xor     edx, edx; SourceId
0x180036827  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x18003682c  mov     r8, [r8]; TraceHandle
0x18003682f  mov     [rsp+268h+lpName], 10h; MatchAnyKeyword
0x180036838  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x18003683d  call    cs:__imp_EnableTraceEx
0x180036843  mov     edi, eax
0x180036845  test    eax, eax
0x180036847  jz      short loc_180036859
0x180036849  jle     short loc_180036851
0x18003684b  movzx   edi, ax
0x18003684e  or      edi, r15d
0x180036851  test    edi, edi
0x180036853  js      loc_1800368F0
0x180036859  mov     r8, [rbp+0F8h]
0x180036860  lea     rcx, NetProvGuid; ProviderId
0x180036867  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x18003686c  mov     r9d, r13d; IsEnabled
0x18003686f  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x180036874  xor     edx, edx; SourceId
0x180036876  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x18003687b  mov     r8, [r8]; TraceHandle
0x18003687e  mov     [rsp+268h+lpName], r14; MatchAnyKeyword
0x180036883  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x180036888  call    cs:__imp_EnableTraceEx
0x18003688e  mov     edi, eax
0x180036890  test    eax, eax
0x180036892  jz      short loc_1800368A0
0x180036894  jle     short loc_18003689C
0x180036896  movzx   edi, ax
0x180036899  or      edi, r15d
0x18003689c  test    edi, edi
0x18003689e  js      short loc_1800368F0
0x1800368a0  mov     r8, [rbp+0F8h]
0x1800368a7  lea     rcx, WdcRundownProvGuid; ProviderId
0x1800368ae  mov     [rsp+268h+EnableFilterDesc], r14; EnableFilterDesc
0x1800368b3  mov     r9d, r13d; IsEnabled
0x1800368b6  mov     [rsp+268h+EnableProperty], r14d; EnableProperty
0x1800368bb  xor     edx, edx; SourceId
0x1800368bd  mov     [rsp+268h+MatchAllKeyword], r14; MatchAllKeyword
0x1800368c2  mov     r8, [r8]; TraceHandle
0x1800368c5  mov     [rsp+268h+lpName], r14; MatchAnyKeyword
0x1800368ca  mov     byte ptr [rsp+268h+dwMaximumSizeLow], r14b; Level
0x1800368cf  call    cs:__imp_EnableTraceEx
0x1800368d5  mov     edi, r14d
0x1800368d8  test    eax, eax
0x1800368da  jz      short loc_1800368E8
0x1800368dc  jg      short loc_1800368E2
0x1800368de  mov     edi, eax
0x1800368e0  jmp     short loc_1800368E8
0x1800368e2  movzx   edi, ax
0x1800368e5  or      edi, r15d
0x1800368e8  test    edi, edi
0x1800368ea  jns     loc_1800369AA
0x1800368f0  lea     r12, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x1800368f7  mov     eax, edi
0x1800368f9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180036900  mov     r8, r14; int
0x180036903  lea     rdx, aWdctracecontro_10; "WdcTraceControl::TraceStart"
0x18003690a  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x180036911  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180036915  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003691a  test    edi, edi
0x18003691c  jns     loc_1800369AA
0x180036922  mov     rax, [rbp+0F8h]
0x180036929  test    rax, rax
0x18003692c  jz      short loc_18003695D
0x18003692e  cmp     [rax], r14
0x180036931  jz      short loc_18003695D
0x180036933  lea     rbx, [rbp+0E8h]
0x18003693a  xor     r8d, r8d; int
0x18003693d  mov     rdx, rbx; struct _EVENT_TRACE_PROPERTIES **
0x180036940  call    ?TraceInitProperties@WdcTraceControl@@AEAAJPEAPEAU_EVENT_TRACE_PROPERTIES@@H@Z; WdcTraceControl::TraceInitProperties(_EVENT_TRACE_PROPERTIES * *,int)
0x180036945  mov     r8, [rbx]; Properties
0x180036948  mov     rdx, r12; InstanceName
0x18003694b  xor     ecx, ecx; TraceHandle
0x18003694d  call    cs:__imp_StopTraceW
0x180036953  mov     rax, [rbp+0F8h]
0x18003695a  mov     [rax], r14
0x18003695d  mov     rcx, [rbp+0E0h]; TraceHandle
0x180036964  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180036968  jz      short loc_18003697B
0x18003696a  call    cs:__imp_CloseTrace
0x180036970  mov     qword ptr [rbp+0E0h], 0FFFFFFFFFFFFFFFFh
0x18003697b  mov     rcx, [rbp+0F8h]; lpBaseAddress
0x180036982  test    rcx, rcx
0x180036985  jz      short loc_180036994
0x180036987  call    cs:__imp_UnmapViewOfFile
0x18003698d  mov     [rbp+0F8h], r14
0x180036994  mov     rcx, [rsi]; hObject
0x180036997  lea     rax, [rcx-1]
0x18003699b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003699f  ja      short loc_1800369AA
0x1800369a1  call    cs:__imp_CloseHandle
0x1800369a7  mov     [rsi], r14
0x1800369aa  mov     eax, edi
0x1800369ac  mov     rcx, [rsp+268h+var_58]
0x1800369b4  xor     rcx, rsp; StackCookie
0x1800369b7  call    __security_check_cookie
0x1800369bc  add     rsp, 228h
  ... truncated ...
```
