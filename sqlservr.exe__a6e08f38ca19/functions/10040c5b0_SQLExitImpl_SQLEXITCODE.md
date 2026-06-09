# SQLExitImpl(SQLEXITCODE)

- ea: `0x10040c5b0`
- end: `0x10040c8c0`
- name: `?SQLExitImpl@@YAXW4SQLEXITCODE@@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10041a3f0`

## callees

- `0x1004095e0`
- `0x10040c5b0`
- `0x10040ca90`
- `0x10040cda0`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!Sleep` at `0x10040c80b`
- `KERNEL32!Sleep` at `0x10040c80b`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10040c783`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10040c78e`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10040c783`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10040c78e`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x10040c76c`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x10040c76c`
- `sqllang!?ShutdownNotifyFsAgent@@YAXXZ` at `0x10040c7a0`
- `sqllang!?ShutdownNotifyFsAgent@@YAXXZ` at `0x10040c7a0`
- `sqllang!?sql_exit_invoked_fire@XeSqlPkg@@YAXKK@Z` at `0x10040c620`
- `sqllang!?sql_exit_invoked_fire@XeSqlPkg@@YAXKK@Z` at `0x10040c620`
- `sqldk!?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA` at `0x10040c67a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c72e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c7f0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c847`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c72e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c7f0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040c847`
- `sqldk!SystemThread_TlsOffset` at `0x10040c715`
- `sqldk!SystemThread_TlsOffset` at `0x10040c7d5`
- `sqldk!SystemThread_TlsOffset` at `0x10040c82c`
- `sqldk!SystemThread_TlsIndex` at `0x10040c70c`
- `sqldk!SystemThread_TlsIndex` at `0x10040c7cc`
- `sqldk!SystemThread_TlsIndex` at `0x10040c823`
- `sqldk!?GetShutdownOption@@YA?AW4ShutdownOption@@XZ` at `0x10040c60c`
- `sqldk!?GetShutdownOption@@YA?AW4ShutdownOption@@XZ` at `0x10040c616`
- `sqldk!?GetShutdownOption@@YA?AW4ShutdownOption@@XZ` at `0x10040c60c`
- `sqldk!?GetShutdownOption@@YA?AW4ShutdownOption@@XZ` at `0x10040c616`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c5e1`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c63a`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c5e1`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c63a`
- `sqldk!?SQLExitNoHang@@YAXW4SQLEXITCODE@@@Z` at `0x10040c7bd`
- `sqldk!?SQLExitNoHang@@YAXW4SQLEXITCODE@@@Z` at `0x10040c7bd`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10040c5d7`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10040c5d7`
- `sqldk!?SOS_OS_sm_osProcessStatus@@3KA` at `0x10040c777`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10040c5d0`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10040c7b5`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10040c7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SQLExitImpl(unsigned int a1)
{
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v3; // r9
  unsigned int ShutdownOption; // eax
  unsigned int v5; // r8d
  __int64 v6; // rax
  struct IErrorReportingManager *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rcx
  struct IFFtSql *FFtSql; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rdi
  int v16; // ebx
  int v17; // [rsp+60h] [rbp-128h] BYREF
  __int64 v18; // [rsp+68h] [rbp-120h]
  __int64 v19; // [rsp+70h] [rbp-118h]
  __int64 v20; // [rsp+78h] [rbp-110h]
  __int64 v21; // [rsp+80h] [rbp-108h]
  __int64 v22; // [rsp+88h] [rbp-100h]
  _BYTE v23[16]; // [rsp+90h] [rbp-F8h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp-E8h] BYREF
  void *v25; // [rsp+A8h] [rbp-E0h] BYREF
  int v26; // [rsp+168h] [rbp-20h]

  v22 = -2;
  if ( !OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    ErrorReportingManager = GetErrorReportingManager();
    LOBYTE(v3) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)ErrorReportingManager + 168LL))(
      ErrorReportingManager,
      L"SQL Server shutdown has been initiated.\n",
      40,
      v3,
      -1);
  }
  if ( !(unsigned int)GetShutdownOption() )
  {
    ShutdownOption = GetShutdownOption();
    XeSqlPkg::sql_exit_invoked_fire((XeSqlPkg *)a1, ShutdownOption, v5);
  }
  v6 = qword_10049F340;
  if ( (*(_BYTE *)(qword_10049F340 + 774) & 0x20) != 0 )
  {
    v7 = GetErrorReportingManager();
    LOBYTE(v8) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)v7 + 168LL))(
      v7,
      L"Printing callstack to track calls to SQLExit ().\n",
      49,
      v8,
      -1);
    memset_0(v23, 0, 0xE8u);
    v26 = SOS_OS_StackBackTraceRoutine(1u, 0x18u, &v25, &v24);
    v24 = (((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10)))
          ^ ((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10))) >> 6))
         + ~(((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10)))
            ^ ((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10))) >> 6)) << 11))
        ^ ((((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10)))
           ^ ((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10))) >> 6))
          + ~(((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10)))
             ^ ((9 * ((v24 + ~(v24 << 15)) ^ ((v24 + ~(v24 << 15)) >> 10))) >> 6)) << 11)) >> 16);
    StackFrames<24>::Dump(v23);
    v6 = qword_10049F340;
  }
  if ( (*(_BYTE *)(v6 + 774) & 0x40) != 0 )
  {
    v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v10 = *(_QWORD *)(v9 + 256);
    if ( !v10 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v10 = *(_QWORD *)(v9 + 256);
    }
    stackTrace(*(_QWORD *)(v10 + 600), 0, L"SQLExit() invoked.\n", 416, 22, 0, 0, 0, 0);
  }
  DisableIdleForShutdown();
  if ( (SOS_OS_sm_osProcessStatus & 1) != 0 && GetFFtSql() )
  {
    FFtSql = GetFFtSql();
    (*(void (__fastcall **)(struct IFFtSql *))(*(_QWORD *)FFtSql + 128LL))(FFtSql);
  }
  ShutdownNotifyFsAgent();
  if ( *((_DWORD *)qword_10049F360 + 3645) )
    SbsShutdown();
  SQLExitNoHang(a1);
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  if ( (*(_BYTE *)(v13 + 800) & 4) != 0 )
  {
    Sleep(0xFFFFFFFF);
  }
  else
  {
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    v16 = !(*(_BYTE *)(v15 + 616) & 1);
    *(_DWORD *)(v15 + 616) |= 1u;
    v17 = 4194400;
    v18 = 0;
    v20 = 0;
    v19 = 0;
    v21 = 0;
    SOS_Task::Sleep(0xFFFFFFFFLL, &v17);
    *(_DWORD *)(v15 + 616) &= ~v16;
  }
}

```

## disassembly

```asm
0x10040c5b0  mov     rax, rsp
0x10040c5b3  push    rdi
0x10040c5b4  sub     rsp, 180h
0x10040c5bb  mov     qword ptr [rax-100h], 0FFFFFFFFFFFFFFFEh
0x10040c5c6  mov     [rax+8], rbx
0x10040c5ca  mov     [rax+10h], rsi
0x10040c5ce  mov     edi, ecx
0x10040c5d0  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10040c5d7  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x10040c5dd  test    al, al
0x10040c5df  jnz     short loc_10040C60C
0x10040c5e1  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x10040c5e7  mov     r10, [rax]
0x10040c5ea  mov     [rsp+188h+var_168], 0FFFFFFFFh
0x10040c5f2  mov     r9b, 1
0x10040c5f5  mov     r8d, 28h ; '('
0x10040c5fb  lea     rdx, aSqlServerShutd; "SQL Server shutdown has been initiated."...
0x10040c602  mov     rcx, rax
0x10040c605  call    qword ptr [r10+0A8h]
0x10040c60c  call    cs:__imp_?GetShutdownOption@@YA?AW4ShutdownOption@@XZ; GetShutdownOption(void)
0x10040c612  test    eax, eax
0x10040c614  jnz     short loc_10040C626
0x10040c616  call    cs:__imp_?GetShutdownOption@@YA?AW4ShutdownOption@@XZ; GetShutdownOption(void)
0x10040c61c  mov     edx, eax
0x10040c61e  mov     ecx, edi
0x10040c620  call    cs:__imp_?sql_exit_invoked_fire@XeSqlPkg@@YAXKK@Z; XeSqlPkg::sql_exit_invoked_fire(ulong,ulong)
0x10040c626  mov     rax, cs:qword_10049F340
0x10040c62d  test    byte ptr [rax+306h], 20h
0x10040c634  jz      loc_10040C6F8
0x10040c63a  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x10040c640  mov     r10, [rax]
0x10040c643  mov     [rsp+188h+var_168], 0FFFFFFFFh
0x10040c64b  mov     r9b, 1
0x10040c64e  mov     r8d, 31h ; '1'
0x10040c654  lea     rdx, aPrintingCallst; "Printing callstack to track calls to SQ"...
0x10040c65b  mov     rcx, rax
0x10040c65e  call    qword ptr [r10+0A8h]
0x10040c665  xor     edx, edx; Val
0x10040c667  mov     r8d, 0E8h; Size
0x10040c66d  lea     rcx, [rsp+188h+var_F8]; void *
0x10040c675  call    memset_0
0x10040c67a  mov     rax, cs:__imp_?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA; ushort (*SOS_OS_StackBackTraceRoutine)(ulong,ulong,void * *,ulong *)
0x10040c681  mov     r10, [rax]
0x10040c684  lea     r9, [rsp+188h+var_E8]
0x10040c68c  lea     r8, [rsp+188h+var_E0]
0x10040c694  mov     edx, 18h
0x10040c699  lea     ecx, [rdx-17h]
0x10040c69c  call    r10
0x10040c69f  movzx   eax, ax
0x10040c6a2  mov     [rsp+188h+var_20], eax
0x10040c6a9  mov     ecx, [rsp+188h+var_E8]
0x10040c6b0  shl     ecx, 0Fh
0x10040c6b3  not     ecx
0x10040c6b5  add     ecx, [rsp+188h+var_E8]
0x10040c6bc  mov     eax, ecx
0x10040c6be  shr     eax, 0Ah
0x10040c6c1  xor     eax, ecx
0x10040c6c3  lea     eax, [rax+rax*8]
0x10040c6c6  mov     ecx, eax
0x10040c6c8  shr     ecx, 6
0x10040c6cb  xor     ecx, eax
0x10040c6cd  mov     edx, ecx
0x10040c6cf  shl     edx, 0Bh
0x10040c6d2  not     edx
0x10040c6d4  add     edx, ecx
0x10040c6d6  mov     eax, edx
0x10040c6d8  shr     eax, 10h
0x10040c6db  xor     eax, edx
0x10040c6dd  mov     [rsp+188h+var_E8], eax
0x10040c6e4  lea     rcx, [rsp+188h+var_F8]
0x10040c6ec  call    ?Dump@?$StackFrames@$0BI@@@QEAAXXZ; StackFrames<24>::Dump(void)
0x10040c6f1  mov     rax, cs:qword_10049F340
0x10040c6f8  xor     esi, esi
0x10040c6fa  test    byte ptr [rax+306h], 40h
0x10040c701  jz      short loc_10040C772
0x10040c703  mov     rdx, gs:58h
0x10040c70c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c713  mov     ecx, [rax]
0x10040c715  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c71c  mov     ebx, [rax]
0x10040c71e  add     rbx, [rdx+rcx*8]
0x10040c722  mov     rcx, [rbx+100h]
0x10040c729  test    rcx, rcx
0x10040c72c  jnz     short loc_10040C73B
0x10040c72e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040c734  mov     rcx, [rbx+100h]
0x10040c73b  mov     [rsp+188h+var_148], rsi
0x10040c740  mov     [rsp+188h+var_150], rsi
0x10040c745  mov     [rsp+188h+var_158], esi
0x10040c749  mov     [rsp+188h+var_160], rsi
0x10040c74e  mov     [rsp+188h+var_168], 16h
0x10040c756  mov     r9d, 1A0h
0x10040c75c  lea     r8, aSqlexitInvoked; "SQLExit() invoked.\n"
0x10040c763  xor     edx, edx
0x10040c765  mov     rcx, [rcx+258h]
0x10040c76c  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x10040c772  call    ?DisableIdleForShutdown@@YAXXZ; DisableIdleForShutdown(void)
0x10040c777  mov     rax, cs:__imp_?SOS_OS_sm_osProcessStatus@@3KA; ulong SOS_OS_sm_osProcessStatus
0x10040c77e  test    byte ptr [rax], 1
0x10040c781  jz      short loc_10040C7A0
0x10040c783  call    cs:__imp_?GetFFtSql@@YAAEAVIFFtSql@@XZ; GetFFtSql(void)
0x10040c789  test    rax, rax
0x10040c78c  jz      short loc_10040C7A0
0x10040c78e  call    cs:__imp_?GetFFtSql@@YAAEAVIFFtSql@@XZ; GetFFtSql(void)
0x10040c794  mov     rdx, [rax]
0x10040c797  mov     rcx, rax
0x10040c79a  call    qword ptr [rdx+80h]
0x10040c7a0  call    cs:__imp_?ShutdownNotifyFsAgent@@YAXXZ; ShutdownNotifyFsAgent(void)
0x10040c7a6  mov     rax, cs:qword_10049F360
0x10040c7ad  cmp     [rax+38F4h], esi
0x10040c7b3  jz      short loc_10040C7BB
0x10040c7b5  call    cs:__imp_?SbsShutdown@@YAXXZ; SbsShutdown(void)
0x10040c7bb  mov     ecx, edi
0x10040c7bd  call    cs:__imp_?SQLExitNoHang@@YAXW4SQLEXITCODE@@@Z; SQLExitNoHang(SQLEXITCODE)
0x10040c7c3  mov     rdx, gs:58h
0x10040c7cc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c7d3  mov     ecx, [rax]
0x10040c7d5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c7dc  mov     ebx, [rax]
0x10040c7de  add     rbx, [rdx+rcx*8]
0x10040c7e2  mov     rax, [rbx+100h]
0x10040c7e9  test    rax, rax
0x10040c7ec  jnz     short loc_10040C7FD
0x10040c7ee  xor     ecx, ecx
0x10040c7f0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040c7f6  mov     rax, [rbx+100h]
0x10040c7fd  test    byte ptr [rax+320h], 4
0x10040c804  jz      short loc_10040C816
0x10040c806  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x10040c80b  call    cs:__imp_Sleep
0x10040c811  jmp     loc_10040C8AB
0x10040c816  mov     [rsp+188h+var_138], esi
0x10040c81a  mov     rdx, gs:58h
0x10040c823  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040c82a  mov     ecx, [rax]
0x10040c82c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040c833  mov     ebx, [rax]
0x10040c835  add     rbx, [rdx+rcx*8]
0x10040c839  mov     rdi, [rbx+100h]
0x10040c840  test    rdi, rdi
0x10040c843  jnz     short loc_10040C854
0x10040c845  xor     ecx, ecx
0x10040c847  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040c84d  mov     rdi, [rbx+100h]
0x10040c854  mov     [rsp+188h+var_130], rdi
0x10040c859  mov     eax, [rdi+268h]
0x10040c85f  mov     ebx, eax
0x10040c861  and     ebx, 1
0x10040c864  xor     ebx, 1
0x10040c867  mov     [rsp+188h+var_138], ebx
0x10040c86b  or      eax, 1
0x10040c86e  mov     [rdi+268h], eax
0x10040c874  mov     [rsp+188h+var_128], 400060h
0x10040c87c  mov     [rsp+188h+var_120], rsi
0x10040c881  mov     [rsp+188h+var_110], rsi
0x10040c886  mov     [rsp+188h+var_118], rsi
0x10040c88b  mov     [rsp+188h+var_108], rsi
0x10040c893  lea     rdx, [rsp+188h+var_128]
0x10040c898  mov     ecx, 0FFFFFFFFh
0x10040c89d  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10040c8a2  nop
0x10040c8a3  not     ebx
0x10040c8a5  and     [rdi+268h], ebx
0x10040c8ab  lea     r11, [rsp+188h+var_8]
0x10040c8b3  mov     rbx, [r11+10h]
0x10040c8b7  mov     rsi, [r11+18h]
0x10040c8bb  mov     rsp, r11
0x10040c8be  pop     rdi
0x10040c8bf  retn
```
