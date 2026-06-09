# WdcTraceControl::Stop(int)

- ea: `0x180033248`
- end: `0x180033690`
- name: `?Stop@WdcTraceControl@@QEAAJH@Z`
- size: `1096`
- prototype: `__int64 __fastcall(WdcTraceControl *__hidden this, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800713bc`
- `0x1800714ac`
- `0x180075710`
- `0x180075a60`

## callees

- `0x18000b854`
- `0x1800150d0`
- `0x180016880`
- `0x18002b190`
- `0x180030770`
- `0x180033248`
- `0x180033698`
- `0x180078660`
- `0x180086010`

## import_xrefs

- `ADVAPI32!CloseTrace` at `0x1800332ed`
- `ADVAPI32!CloseTrace` at `0x1800332ed`
- `ADVAPI32!QueryTraceW` at `0x18003336e`
- `ADVAPI32!QueryTraceW` at `0x18003336e`
- `ADVAPI32!StopTraceW` at `0x1800333a5`
- `ADVAPI32!StopTraceW` at `0x1800333a5`
- `KERNEL32!CloseHandle` at `0x180033346`
- `KERNEL32!CloseHandle` at `0x1800333f6`
- `KERNEL32!CloseHandle` at `0x1800335a6`
- `KERNEL32!CloseHandle` at `0x1800335c1`
- `KERNEL32!CloseHandle` at `0x1800335dc`
- `KERNEL32!CloseHandle` at `0x1800335fc`
- `KERNEL32!CloseHandle` at `0x180033613`
- `KERNEL32!CloseHandle` at `0x180033629`
- `KERNEL32!CloseHandle` at `0x180033640`
- `KERNEL32!CloseHandle` at `0x180033658`
- `KERNEL32!CloseHandle` at `0x180033346`
- `KERNEL32!CloseHandle` at `0x1800333f6`
- `KERNEL32!CloseHandle` at `0x1800335a6`
- `KERNEL32!CloseHandle` at `0x1800335c1`
- `KERNEL32!CloseHandle` at `0x1800335dc`
- `KERNEL32!CloseHandle` at `0x1800335fc`
- `KERNEL32!CloseHandle` at `0x180033613`
- `KERNEL32!CloseHandle` at `0x180033629`
- `KERNEL32!CloseHandle` at `0x180033640`
- `KERNEL32!CloseHandle` at `0x180033658`
- `KERNEL32!GetLastError` at `0x180033517`
- `KERNEL32!GetLastError` at `0x180033553`
- `KERNEL32!GetLastError` at `0x180033517`
- `KERNEL32!GetLastError` at `0x180033553`
- `KERNEL32!WaitForSingleObject` at `0x180033429`
- `KERNEL32!WaitForSingleObject` at `0x18003343d`
- `KERNEL32!WaitForSingleObject` at `0x180033451`
- `KERNEL32!WaitForSingleObject` at `0x180033462`
- `KERNEL32!WaitForSingleObject` at `0x180033429`
- `KERNEL32!WaitForSingleObject` at `0x18003343d`
- `KERNEL32!WaitForSingleObject` at `0x180033451`
- `KERNEL32!WaitForSingleObject` at `0x180033462`
- `KERNEL32!SetEvent` at `0x18003332e`
- `KERNEL32!SetEvent` at `0x18003332e`
- `KERNEL32!SetThreadPriority` at `0x18003350d`
- `KERNEL32!SetThreadPriority` at `0x18003350d`
- `KERNEL32!GetCurrentThread` at `0x180033502`
- `KERNEL32!GetCurrentThread` at `0x180033502`
- `KERNEL32!UnmapViewOfFile` at `0x1800333d8`
- `KERNEL32!UnmapViewOfFile` at `0x1800333d8`
- `KERNEL32!SetProcessWorkingSetSize` at `0x180033545`
- `KERNEL32!SetProcessWorkingSetSize` at `0x180033545`
- `KERNEL32!GetCurrentProcess` at `0x180033532`
- `KERNEL32!GetCurrentProcess` at `0x180033532`
- `USER32!KillTimer` at `0x180033324`
- `USER32!KillTimer` at `0x180033324`

## pseudocode

```c
__int64 __fastcall WdcTraceControl::Stop(WdcTraceControl *this, int a2)
{
  int v3; // r13d
  int v4; // eax
  signed int v5; // ebx
  HANDLE *v6; // r14
  HANDLE *v7; // r12
  HANDLE *v8; // rbp
  HANDLE *v9; // r15
  HANDLE *v10; // rsi
  TRACEHANDLE v11; // rcx
  UINT_PTR v12; // rbx
  HWND v13; // rax
  char *v14; // rcx
  PEVENT_TRACE_PROPERTIES *v15; // rbx
  signed int TraceW; // eax
  WdcTraceControl *v17; // rcx
  bool v18; // sf
  ULONG v19; // eax
  const void *v20; // rcx
  char *v21; // rcx
  HANDLE v22; // r13
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  HANDLE CurrentThread; // rax
  signed int v28; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  char *v31; // rcx
  char *v32; // rcx
  int v34; // [rsp+80h] [rbp+8h]
  int v36; // [rsp+90h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+20h] BYREF

  v36 = 0;
  v3 = 0;
  hObject = 0;
  v34 = 0;
  v4 = (*(__int64 (__fastcall **)(WdcTraceControl *))(*(_QWORD *)this + 8LL))(this);
  v5 = v4;
  if ( v4 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcTraceControl::Stop",
      0,
      L"FAILURE: 0x%08x",
      v4);
    v6 = (HANDLE *)((char *)this + 64);
    v7 = (HANDLE *)((char *)this + 72);
    v8 = (HANDLE *)((char *)this + 80);
    v9 = (HANDLE *)((char *)this + 88);
    v10 = (HANDLE *)((char *)this + 96);
    goto LABEL_51;
  }
  WdcLockObject::LockEnter(this, &v36);
  *((_DWORD *)this + 14) = 0;
  WdcAcquireMutex(&hObject);
  v11 = *((_QWORD *)this + 28);
  if ( v11 != -1 )
  {
    CloseTrace(v11);
    *((_QWORD *)this + 28) = -1;
  }
  v7 = (HANDLE *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    v12 = *((_QWORD *)this + 15);
    v13 = (HWND)(*(__int64 (__fastcall **)(UINT_PTR))(*(_QWORD *)v12 + 360LL))(v12);
    KillTimer(v13, v12);
    SetEvent(*v7);
  }
  v8 = (HANDLE *)((char *)this + 80);
  v14 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v14);
    *v8 = 0;
  }
  v15 = (PEVENT_TRACE_PROPERTIES *)((char *)this + 232);
  WdcTraceControl::TraceInitProperties((WdcTraceControl *)v14, (struct _EVENT_TRACE_PROPERTIES **)this + 29, 0);
  TraceW = QueryTraceW(0, L"WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE951", *((PEVENT_TRACE_PROPERTIES *)this + 29));
  v18 = TraceW < 0;
  if ( TraceW )
  {
    if ( TraceW > 0 )
      v18 = 1;
    if ( v18 )
      goto LABEL_14;
  }
  if ( !(*v15)->Wnode.ProviderId )
  {
LABEL_14:
    WdcTraceControl::TraceInitProperties(v17, (struct _EVENT_TRACE_PROPERTIES **)this + 29, 0);
    v19 = StopTraceW(0, L"WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE951", *v15);
    if ( !v19 || (v34 = 1, (_WORD)v19 != 5) )
      v34 = 0;
  }
  v20 = (const void *)*((_QWORD *)this + 31);
  if ( v20 )
  {
    UnmapViewOfFile(v20);
    *((_QWORD *)this + 31) = 0;
  }
  v21 = (char *)*((_QWORD *)this + 30);
  if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v21);
    *((_QWORD *)this + 30) = 0;
  }
  v22 = hObject;
  if ( hObject )
    WdcReleaseMutex(hObject);
  v6 = (HANDLE *)((char *)this + 64);
  v23 = (void *)*((_QWORD *)this + 8);
  if ( v23 )
    WaitForSingleObject(v23, 0xFFFFFFFF);
  v9 = (HANDLE *)((char *)this + 88);
  v24 = (void *)*((_QWORD *)this + 11);
  if ( v24 )
    WaitForSingleObject(v24, 0xFFFFFFFF);
  v10 = (HANDLE *)((char *)this + 96);
  v25 = (void *)*((_QWORD *)this + 12);
  if ( v25 )
    WaitForSingleObject(v25, 0xFFFFFFFF);
  v26 = (void *)*((_QWORD *)this + 14);
  if ( v26 )
    WaitForSingleObject(v26, 0xFFFFFFFF);
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 16));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 17));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 18));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 19));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 20));
  if ( !a2 )
  {
    WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 21));
    WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 22));
  }
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 24));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 25));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 26));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 27));
  WdcDataMonitor::Stop(*((WdcDataMonitor **)this + 23));
  CurrentThread = GetCurrentThread();
  if ( SetThreadPriority(CurrentThread, 0) )
  {
LABEL_38:
    CurrentProcess = GetCurrentProcess();
    if ( SetProcessWorkingSetSize(CurrentProcess, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFFFFFFFFFFuLL) )
    {
      v5 = 0;
      goto LABEL_47;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_47;
      goto LABEL_46;
    }
    goto LABEL_45;
  }
  v28 = GetLastError();
  v5 = v28;
  if ( v28 )
  {
    if ( v28 > 0 )
      v5 = (unsigned __int16)v28 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_46;
    goto LABEL_38;
  }
LABEL_45:
  v5 = -2147467259;
LABEL_46:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
    "WdcTraceControl::Stop",
    0,
    L"FAILURE: 0x%08x",
    v5);
LABEL_47:
  if ( v22 && v22 != (HANDLE)-1LL )
    CloseHandle(v22);
  v3 = v34;
LABEL_51:
  if ( (char *)*v6 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v6);
    *v6 = 0;
  }
  if ( (char *)*v7 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v7);
    *v7 = 0;
  }
  if ( (char *)*v8 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v8);
    *v8 = 0;
  }
  if ( (char *)*v9 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v9);
    *v9 = 0;
  }
  if ( (char *)*v10 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v10);
    *v10 = 0;
  }
  v31 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v31);
    *((_QWORD *)this + 13) = 0;
  }
  v32 = (char *)*((_QWORD *)this + 14);
  if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v32);
    *((_QWORD *)this + 14) = 0;
  }
  WdcLockObject::LockLeave(this, &v36);
  if ( v3 )
    return (unsigned int)-2147024891;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180033248  mov     rax, rsp
0x18003324b  mov     [rax+10h], edx
0x18003324e  push    rbx
0x18003324f  push    rbp
0x180033250  push    rsi
0x180033251  push    rdi
0x180033252  push    r12
0x180033254  push    r13
0x180033256  push    r14
0x180033258  push    r15
0x18003325a  sub     rsp, 38h
0x18003325e  xor     esi, esi
0x180033260  mov     rdi, rcx
0x180033263  mov     [rax+18h], esi
0x180033266  mov     r13d, esi
0x180033269  mov     [rax+20h], rsi
0x18003326d  mov     rax, [rcx]
0x180033270  mov     [rsp+78h+arg_0], esi
0x180033277  mov     rax, [rax+8]
0x18003327b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033280  mov     ebx, eax
0x180033282  test    eax, eax
0x180033284  jns     short loc_1800332C0
0x180033286  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003328d  mov     [rsp+78h+var_58], eax
0x180033291  xor     r8d, r8d; int
0x180033294  lea     rdx, aWdctracecontro_7; "WdcTraceControl::Stop"
0x18003329b  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x1800332a2  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800332a7  lea     r14, [rdi+40h]
0x1800332ab  lea     r12, [rdi+48h]
0x1800332af  lea     rbp, [rdi+50h]
0x1800332b3  lea     r15, [rdi+58h]
0x1800332b7  lea     rsi, [rdi+60h]
0x1800332bb  jmp     loc_1800335B4
0x1800332c0  lea     rdx, [rsp+78h+arg_10]; int *
0x1800332c8  mov     rcx, rdi; this
0x1800332cb  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x1800332d0  lea     rcx, [rsp+78h+hObject]; void **
0x1800332d8  mov     [rdi+38h], esi
0x1800332db  call    ?WdcAcquireMutex@@YAJPEAPEAX@Z; WdcAcquireMutex(void * *)
0x1800332e0  mov     rcx, [rdi+0E0h]; TraceHandle
0x1800332e7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800332eb  jz      short loc_1800332FE
0x1800332ed  call    cs:__imp_CloseTrace
0x1800332f3  mov     qword ptr [rdi+0E0h], 0FFFFFFFFFFFFFFFFh
0x1800332fe  lea     r12, [rdi+48h]
0x180033302  cmp     [r12], rsi
0x180033306  jz      short loc_180033334
0x180033308  mov     rbx, [rdi+78h]
0x18003330c  mov     rcx, rbx
0x18003330f  mov     rax, [rbx]
0x180033312  mov     rax, [rax+168h]
0x180033319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003331e  mov     rdx, rbx; uIDEvent
0x180033321  mov     rcx, rax; hWnd
0x180033324  call    cs:__imp_KillTimer
0x18003332a  mov     rcx, [r12]; hEvent
0x18003332e  call    cs:__imp_SetEvent
0x180033334  lea     rbp, [rdi+50h]
0x180033338  mov     rcx, [rbp+0]; hObject
0x18003333c  lea     rax, [rcx-1]
0x180033340  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033344  ja      short loc_180033350
0x180033346  call    cs:__imp_CloseHandle
0x18003334c  mov     [rbp+0], rsi
0x180033350  lea     rbx, [rdi+0E8h]
0x180033357  xor     r8d, r8d; int
0x18003335a  mov     rdx, rbx; struct _EVENT_TRACE_PROPERTIES **
0x18003335d  call    ?TraceInitProperties@WdcTraceControl@@AEAAJPEAPEAU_EVENT_TRACE_PROPERTIES@@H@Z; WdcTraceControl::TraceInitProperties(_EVENT_TRACE_PROPERTIES * *,int)
0x180033362  mov     r8, [rbx]; Properties
0x180033365  lea     rdx, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x18003336c  xor     ecx, ecx; TraceHandle
0x18003336e  call    cs:__imp_QueryTraceW
0x180033374  test    eax, eax
0x180033376  jz      short loc_180033386
0x180033378  jle     short loc_180033384
0x18003337a  movzx   eax, ax
0x18003337d  or      eax, 80070000h
0x180033382  test    eax, eax
0x180033384  js      short loc_18003338E
0x180033386  mov     rax, [rbx]
0x180033389  cmp     [rax+4], esi
0x18003338c  jnz     short loc_1800333CC
0x18003338e  xor     r8d, r8d; int
0x180033391  mov     rdx, rbx; struct _EVENT_TRACE_PROPERTIES **
0x180033394  call    ?TraceInitProperties@WdcTraceControl@@AEAAJPEAPEAU_EVENT_TRACE_PROPERTIES@@H@Z; WdcTraceControl::TraceInitProperties(_EVENT_TRACE_PROPERTIES * *,int)
0x180033399  mov     r8, [rbx]; Properties
0x18003339c  lea     rdx, InstanceName; "WDC.BE95A9B1-DE15-4B78-B923-A12AB70BE95"...
0x1800333a3  xor     ecx, ecx; TraceHandle
0x1800333a5  call    cs:__imp_StopTraceW
0x1800333ab  test    eax, eax
0x1800333ad  jz      short loc_1800333C5
0x1800333af  jle     short loc_1800333B4
0x1800333b1  movzx   eax, ax
0x1800333b4  mov     [rsp+78h+arg_0], 1
0x1800333bf  cmp     ax, 5
0x1800333c3  jz      short loc_1800333CC
0x1800333c5  mov     [rsp+78h+arg_0], esi
0x1800333cc  mov     rcx, [rdi+0F8h]; lpBaseAddress
0x1800333d3  test    rcx, rcx
0x1800333d6  jz      short loc_1800333E5
0x1800333d8  call    cs:__imp_UnmapViewOfFile
0x1800333de  mov     [rdi+0F8h], rsi
0x1800333e5  mov     rcx, [rdi+0F0h]; hObject
0x1800333ec  lea     rax, [rcx-1]
0x1800333f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800333f4  ja      short loc_180033403
0x1800333f6  call    cs:__imp_CloseHandle
0x1800333fc  mov     [rdi+0F0h], rsi
0x180033403  mov     r13, [rsp+78h+hObject]
0x18003340b  test    r13, r13
0x18003340e  jz      short loc_180033418
0x180033410  mov     rcx, r13; void *
0x180033413  call    ?WdcReleaseMutex@@YAJPEAX@Z; WdcReleaseMutex(void *)
0x180033418  lea     r14, [rdi+40h]
0x18003341c  or      ebx, 0FFFFFFFFh
0x18003341f  mov     rcx, [r14]; hHandle
0x180033422  test    rcx, rcx
0x180033425  jz      short loc_18003342F
0x180033427  mov     edx, ebx; dwMilliseconds
0x180033429  call    cs:__imp_WaitForSingleObject
0x18003342f  lea     r15, [rdi+58h]
0x180033433  mov     rcx, [r15]; hHandle
0x180033436  test    rcx, rcx
0x180033439  jz      short loc_180033443
0x18003343b  mov     edx, ebx; dwMilliseconds
0x18003343d  call    cs:__imp_WaitForSingleObject
0x180033443  lea     rsi, [rdi+60h]
0x180033447  mov     rcx, [rsi]; hHandle
0x18003344a  test    rcx, rcx
0x18003344d  jz      short loc_180033457
0x18003344f  mov     edx, ebx; dwMilliseconds
0x180033451  call    cs:__imp_WaitForSingleObject
0x180033457  mov     rcx, [rdi+70h]; hHandle
0x18003345b  test    rcx, rcx
0x18003345e  jz      short loc_180033468
0x180033460  mov     edx, ebx; dwMilliseconds
0x180033462  call    cs:__imp_WaitForSingleObject
0x180033468  mov     rcx, [rdi+80h]; this
0x18003346f  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x180033474  mov     rcx, [rdi+88h]; this
0x18003347b  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x180033480  mov     rcx, [rdi+90h]; this
0x180033487  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x18003348c  mov     rcx, [rdi+98h]; this
0x180033493  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x180033498  mov     rcx, [rdi+0A0h]; this
0x18003349f  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334a4  cmp     [rsp+78h+arg_8], 0
0x1800334ac  jnz     short loc_1800334C6
0x1800334ae  mov     rcx, [rdi+0A8h]; this
0x1800334b5  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334ba  mov     rcx, [rdi+0B0h]; this
0x1800334c1  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334c6  mov     rcx, [rdi+0C0h]; this
0x1800334cd  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334d2  mov     rcx, [rdi+0C8h]; this
0x1800334d9  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334de  mov     rcx, [rdi+0D0h]; this
0x1800334e5  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334ea  mov     rcx, [rdi+0D8h]; this
0x1800334f1  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x1800334f6  mov     rcx, [rdi+0B8h]; this
0x1800334fd  call    ?Stop@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Stop(void)
0x180033502  call    cs:__imp_GetCurrentThread
0x180033508  mov     rcx, rax; hThread
0x18003350b  xor     edx, edx; nPriority
0x18003350d  call    cs:__imp_SetThreadPriority
0x180033513  test    eax, eax
0x180033515  jnz     short loc_180033532
0x180033517  call    cs:__imp_GetLastError
0x18003351d  mov     ebx, eax
0x18003351f  test    eax, eax
0x180033521  jz      short loc_180033570
0x180033523  jle     short loc_18003352E
0x180033525  movzx   ebx, ax
0x180033528  or      ebx, 80070000h
0x18003352e  test    ebx, ebx
0x180033530  js      short loc_180033575
0x180033532  call    cs:__imp_GetCurrentProcess
0x180033538  mov     rcx, rax; hProcess
0x18003353b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003353f  mov     r8, rax; dwMaximumWorkingSetSize
0x180033542  mov     rdx, rax; dwMinimumWorkingSetSize
0x180033545  call    cs:__imp_SetProcessWorkingSetSize
0x18003354b  test    eax, eax
0x18003354d  jz      short loc_180033553
0x18003354f  xor     ebx, ebx
0x180033551  jmp     short loc_180033598
0x180033553  call    cs:__imp_GetLastError
0x180033559  mov     ebx, eax
0x18003355b  test    eax, eax
0x18003355d  jz      short loc_180033570
0x18003355f  jle     short loc_18003356A
0x180033561  movzx   ebx, ax
0x180033564  or      ebx, 80070000h
0x18003356a  test    ebx, ebx
0x18003356c  jns     short loc_180033598
0x18003356e  jmp     short loc_180033575
0x180033570  mov     ebx, 80004005h
0x180033575  mov     eax, ebx
0x180033577  mov     [rsp+78h+var_58], ebx
0x18003357b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180033582  xor     r8d, r8d; int
0x180033585  lea     rdx, aWdctracecontro_7; "WdcTraceControl::Stop"
0x18003358c  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x180033593  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180033598  test    r13, r13
0x18003359b  jz      short loc_1800335AC
0x18003359d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800335a1  jz      short loc_1800335AC
0x1800335a3  mov     rcx, r13; hObject
0x1800335a6  call    cs:__imp_CloseHandle
0x1800335ac  mov     r13d, [rsp+78h+arg_0]
0x1800335b4  mov     rcx, [r14]; hObject
0x1800335b7  lea     rax, [rcx-1]
0x1800335bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800335bf  ja      short loc_1800335CE
0x1800335c1  call    cs:__imp_CloseHandle
0x1800335c7  mov     qword ptr [r14], 0
0x1800335ce  mov     rcx, [r12]; hObject
0x1800335d2  lea     rax, [rcx-1]
0x1800335d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800335da  ja      short loc_1800335EB
0x1800335dc  call    cs:__imp_CloseHandle
0x1800335e2  xor     r14d, r14d
0x1800335e5  mov     [r12], r14
0x1800335e9  jmp     short loc_1800335EE
0x1800335eb  xor     r14d, r14d
0x1800335ee  mov     rcx, [rbp+0]; hObject
0x1800335f2  lea     rax, [rcx-1]
0x1800335f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800335fa  ja      short loc_180033606
0x1800335fc  call    cs:__imp_CloseHandle
0x180033602  mov     [rbp+0], r14
0x180033606  mov     rcx, [r15]; hObject
0x180033609  lea     rax, [rcx-1]
0x18003360d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033611  ja      short loc_18003361C
0x180033613  call    cs:__imp_CloseHandle
0x180033619  mov     [r15], r14
0x18003361c  mov     rcx, [rsi]; hObject
0x18003361f  lea     rax, [rcx-1]
0x180033623  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033627  ja      short loc_180033632
0x180033629  call    cs:__imp_CloseHandle
0x18003362f  mov     [rsi], r14
0x180033632  mov     rcx, [rdi+68h]; hObject
0x180033636  lea     rax, [rcx-1]
0x18003363a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003363e  ja      short loc_18003364A
0x180033640  call    cs:__imp_CloseHandle
0x180033646  mov     [rdi+68h], r14
0x18003364a  mov     rcx, [rdi+70h]; hObject
0x18003364e  lea     rax, [rcx-1]
0x180033652  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033656  ja      short loc_180033662
0x180033658  call    cs:__imp_CloseHandle
0x18003365e  mov     [rdi+70h], r14
0x180033662  lea     rdx, [rsp+78h+arg_10]; int *
0x18003366a  mov     rcx, rdi; this
0x18003366d  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180033672  mov     eax, 80070005h
0x180033677  test    r13d, r13d
0x18003367a  cmovnz  ebx, eax
0x18003367d  mov     eax, ebx
0x18003367f  add     rsp, 38h
0x180033683  pop     r15
0x180033685  pop     r14
0x180033687  pop     r13
0x180033689  pop     r12
0x18003368b  pop     rdi
0x18003368c  pop     rsi
0x18003368d  pop     rbp
0x18003368e  pop     rbx
0x18003368f  retn
```
