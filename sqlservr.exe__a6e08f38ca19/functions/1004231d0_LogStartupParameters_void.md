# LogStartupParameters(void)

- ea: `0x1004231d0`
- end: `0x100423390`
- name: `?LogStartupParameters@@YAXXZ`
- size: `448`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x100416770`

## callees

- `0x100422c60`
- `0x100422ec0`
- `0x1004231d0`
- `0x100440340`
- `0x1004403d0`

## import_xrefs

- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10042330a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10042336c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10042330a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10042336c`
- `sqldk!SystemThread_TlsOffset` at `0x1004232e3`
- `sqldk!SystemThread_TlsOffset` at `0x100423345`
- `sqldk!SystemThread_TlsIndex` at `0x1004232da`
- `sqldk!SystemThread_TlsIndex` at `0x10042333c`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100423277`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100423277`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1004232bb`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1004232bb`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100423223`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100423223`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10042321c`

## pseudocode

```c
void LogStartupParameters(void)
{
  __int64 v0; // r8
  __int64 v1; // r9
  __int64 v2; // r9
  int v3; // eax
  __int64 v4; // r9
  int v5; // ebx
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  struct CSessionTraceFlags *v9; // rcx
  __int64 v10; // rax
  struct CSessionTraceFlags *v11; // rcx

  LogStartupParameters(17110, &qword_1004A1820, 0, 0);
  LOBYTE(v0) = 1;
  LogStartupParameters(17115, &qword_1004A1720, v0, 0);
  LOBYTE(v1) = 1;
  LogStartupParameters(17115, &qword_1004A17A0, 1, v1);
  if ( !OsInfo::IsLinux(SOS_OS_OsInfo) )
    LogStartupEnvironmentVariables(49955);
  LOBYTE(v2) = 1;
  v3 = LogStartupParameters(49907, &qword_1004A1820, 0, v2);
  LOBYTE(v4) = 1;
  v5 = LogStartupParameters(49908, &qword_1004A1720, 1, v4) + v3;
  if ( byte_1004D28A5 && v5 )
  {
    ErrorReportingManager = GetErrorReportingManager();
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, __int64))(*(_QWORD *)ErrorReportingManager + 224LL))(
      ErrorReportingManager,
      v7);
    scierrlogwithstate(0xC2FBu, 1, 1, L"WX");
    *((_DWORD *)qword_10049F360 + 10544) = 0;
    SQLExit(2);
  }
  if ( (*(_BYTE *)(qword_10049F340 + 139) & 0x20) != 0
    || (v8 = *(_QWORD *)(SystemThread_TlsOffset
                       + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
    && (v9 = **(struct CSessionTraceFlags ***)(v8 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v9, 0x45Du) )
  {
    scierrlog(0x42E2u, 1117);
  }
  if ( (*(_BYTE *)(qword_10049F340 + 139) & 0x40) != 0
    || (v10 = *(_QWORD *)(SystemThread_TlsOffset
                        + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
    && (v11 = **(struct CSessionTraceFlags ***)(v10 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x45Eu) )
  {
    scierrlog(0x42E2u, 1118);
  }
}

```

## disassembly

```asm
0x1004231d0  push    rbx
0x1004231d2  sub     rsp, 20h
0x1004231d6  xor     r9d, r9d
0x1004231d9  lea     rdx, qword_1004A1820
0x1004231e0  xor     r8d, r8d
0x1004231e3  mov     ecx, 42D6h
0x1004231e8  call    LogStartupParameters
0x1004231ed  xor     r9d, r9d
0x1004231f0  lea     rdx, qword_1004A1720
0x1004231f7  mov     r8b, 1
0x1004231fa  mov     ecx, 42DBh
0x1004231ff  call    LogStartupParameters
0x100423204  mov     r9b, 1
0x100423207  lea     rdx, qword_1004A17A0
0x10042320e  movzx   r8d, r9b
0x100423212  mov     ecx, 42DBh
0x100423217  call    LogStartupParameters
0x10042321c  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100423223  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x100423229  test    al, al
0x10042322b  jnz     short loc_100423237
0x10042322d  mov     ecx, 0C323h
0x100423232  call    LogStartupEnvironmentVariables
0x100423237  mov     r9b, 1
0x10042323a  lea     rdx, qword_1004A1820
0x100423241  xor     r8d, r8d
0x100423244  mov     ecx, 0C2F3h
0x100423249  call    LogStartupParameters
0x10042324e  mov     r9b, 1
0x100423251  lea     rdx, qword_1004A1720
0x100423258  movzx   r8d, r9b
0x10042325c  mov     ecx, 0C2F4h
0x100423261  mov     ebx, eax
0x100423263  call    LogStartupParameters
0x100423268  add     ebx, eax
0x10042326a  cmp     cs:byte_1004D28A5, 0
0x100423271  jz      short loc_1004232C1
0x100423273  test    ebx, ebx
0x100423275  jz      short loc_1004232C1
0x100423277  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x10042327d  mov     dl, 1
0x10042327f  mov     rcx, rax
0x100423282  mov     r8, [rax]
0x100423285  call    qword ptr [r8+0E0h]
0x10042328c  mov     edx, 1; int
0x100423291  lea     r9, aWx; "WX"
0x100423298  mov     r8d, edx; int
0x10042329b  mov     ecx, 0C2FBh; unsigned int
0x1004232a0  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x1004232a5  mov     rax, cs:qword_10049F360
0x1004232ac  mov     ecx, 2
0x1004232b1  mov     dword ptr [rax+0A4C0h], 0
0x1004232bb  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x1004232c1  mov     rax, cs:qword_10049F340
0x1004232c8  test    byte ptr [rax+8Bh], 20h
0x1004232cf  jnz     short loc_100423314
0x1004232d1  mov     r8, gs:58h
0x1004232da  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004232e1  mov     edx, [rax]
0x1004232e3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004232ea  mov     ecx, [rax]
0x1004232ec  mov     rax, [r8+rdx*8]
0x1004232f0  mov     rax, [rcx+rax]
0x1004232f4  test    rax, rax
0x1004232f7  jz      short loc_100423323
0x1004232f9  mov     rax, [rax+38h]
0x1004232fd  mov     rcx, [rax]
0x100423300  test    rcx, rcx
0x100423303  jz      short loc_100423323
0x100423305  mov     edx, 45Dh
0x10042330a  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100423310  test    eax, eax
0x100423312  jz      short loc_100423323
0x100423314  mov     edx, 45Dh
0x100423319  mov     ecx, 42E2h; unsigned int
0x10042331e  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100423323  mov     rax, cs:qword_10049F340
0x10042332a  test    byte ptr [rax+8Bh], 40h
0x100423331  jnz     short loc_100423376
0x100423333  mov     r8, gs:58h
0x10042333c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423343  mov     edx, [rax]
0x100423345  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042334c  mov     ecx, [rax]
0x10042334e  mov     rax, [r8+rdx*8]
0x100423352  mov     rax, [rcx+rax]
0x100423356  test    rax, rax
0x100423359  jz      short loc_10042338A
0x10042335b  mov     rax, [rax+38h]
0x10042335f  mov     rcx, [rax]
0x100423362  test    rcx, rcx
0x100423365  jz      short loc_10042338A
0x100423367  mov     edx, 45Eh
0x10042336c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100423372  test    eax, eax
0x100423374  jz      short loc_10042338A
0x100423376  mov     edx, 45Eh
0x10042337b  mov     ecx, 42E2h; unsigned int
0x100423380  add     rsp, 20h
0x100423384  pop     rbx
0x100423385  jmp     ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10042338a  add     rsp, 20h
0x10042338e  pop     rbx
0x10042338f  retn
```
