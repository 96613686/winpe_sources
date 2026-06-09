# WdsSetupLogMessageA

- ea: `0x18001d920`
- end: `0x18001dc6a`
- name: `WdsSetupLogMessageA`
- size: `842`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *, char *, LPCWSTR lpModuleName, int, __int64, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18001a0c8`
- `0x18001a85c`
- `0x18001abcc`
- `0x18001b348`
- `0x18001b9e0`
- `0x18001bab0`
- `0x18001ca90`
- `0x18001d920`
- `0x180022e90`
- `0x1800274de`
- `0x180027510`
- `0x18002a010`

## import_xrefs

- `msvcrt!strrchr` at `0x18001da40`
- `msvcrt!strrchr` at `0x18001da40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dae4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dae4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dad0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dc14`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dc14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001db06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001db06`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001dbee`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001dbee`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001da28`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001da28`

## pseudocode

```c
__int64 __fastcall WdsSetupLogMessageA(
        unsigned int *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        char *a6,
        char *a7,
        LPCWSTR lpModuleName,
        int a9,
        __int64 a10,
        int a11)
{
  DWORD LastError; // esi
  CHAR *v14; // r13
  HMODULE v15; // rax
  char *v16; // rax
  int v17; // eax
  unsigned int v18; // ecx
  char *v19; // rbx
  HANDLE ProcessHeap; // rax
  __int64 (__fastcall *v21)(struct ILogManager *, __int64, __int64, _QWORD, __int64, __int64, unsigned int, _QWORD, char *, unsigned int, __int64, unsigned int, DWORD, __int64, char *, CHAR *, int, __int64, int, _QWORD); // r15
  double CurrentDateTime; // xmm0_8
  DWORD CurrentThreadId; // eax
  unsigned int v24; // edi
  DWORD v25; // ebx
  __int64 v26; // rsi
  unsigned int v27; // ebp
  __int64 MinorTaskA; // r14
  __int64 MajorTaskA; // rax
  unsigned int v30; // ebx
  int v32; // [rsp+B0h] [rbp-198h]
  DWORD dwErrCode; // [rsp+B4h] [rbp-194h]
  CHAR Filename[10]; // [rsp+E0h] [rbp-168h] BYREF
  _BYTE v37[6]; // [rsp+EAh] [rbp-15Eh] BYREF

  LastError = GetLastError();
  dwErrCode = LastError;
  strcpy(Filename, "<unknown>");
  memset_0(v37, 0, 0xFAu);
  if ( !g_pLogManager || !a1 )
    return 0;
  a1[1] |= a2;
  v14 = 0;
  v32 = 0;
  if ( lpModuleName )
  {
    v15 = (HMODULE)pIPtoHModule(lpModuleName);
    if ( v15 && (GetModuleFileNameA(v15, Filename, 0x104u), (v16 = strrchr(Filename, 92)) != 0) )
      v14 = v16 + 1;
    else
      v14 = Filename;
  }
  v17 = *a1;
  if ( *a1 == 1694498816 || !v17 )
  {
    v18 = g_dwPrevFlags;
    if ( (g_dwPrevFlags & 0x80000) != 0 )
    {
      v17 = 1795162112;
      *a1 = 1795162112;
    }
    if ( (v18 & 0x40000) != 0 )
      v32 = 1;
  }
  if ( ((v17 - 0x1000000) & 0xFEFFFFFF) == 0 && (unsigned int)ShouldTelemetryAssert() )
  {
    v19 = BuildTelAssertReportA(*((const char **)a1 + 1), a7, a6);
    MicrosoftTelemetryAssertTriggeredArgs(v19, a5, LastError);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
  }
  v21 = *(__int64 (__fastcall **)(struct ILogManager *, __int64, __int64, _QWORD, __int64, __int64, unsigned int, _QWORD, char *, unsigned int, __int64, unsigned int, DWORD, __int64, char *, CHAR *, int, __int64, int, _QWORD))(*(_QWORD *)g_pLogManager + 32LL);
  CurrentDateTime = GetCurrentDateTime();
  CurrentThreadId = GetCurrentThreadId();
  v24 = g_ProcessID;
  v25 = CurrentThreadId;
  v26 = *((_QWORD *)a1 + 1);
  v27 = a1[1];
  MinorTaskA = GetMinorTaskA();
  MajorTaskA = GetMajorTaskA();
  v30 = v21(
          g_pLogManager,
          17,
          a3,
          *a1,
          MajorTaskA,
          MinorTaskA,
          a5,
          0,
          a7,
          v27,
          v26,
          v24,
          v25,
          a4,
          g_ProcessExeA,
          v14,
          a9,
          a10,
          a11,
          *(_QWORD *)&CurrentDateTime);
  if ( v30 == 4 )
  {
    WdsSetupLogDestroy();
    ExitProcess(0);
  }
  if ( v32 )
    RaiseException(0xC0000025, 1u, 0, 0);
  SetLastError(dwErrCode);
  return v30;
}

```

## disassembly

```asm
0x18001d920  mov     rax, rsp
0x18001d923  mov     [rax+10h], rbx
0x18001d927  push    rbp
0x18001d928  push    rsi
0x18001d929  push    rdi
0x18001d92a  push    r12
0x18001d92c  push    r13
0x18001d92e  push    r14
0x18001d930  push    r15
0x18001d932  sub     rsp, 210h
0x18001d939  movaps  xmmword ptr [rax-48h], xmm6
0x18001d93d  mov     rax, cs:__security_cookie
0x18001d944  xor     rax, rsp
0x18001d947  mov     [rsp+248h+var_58], rax
0x18001d94f  mov     rax, [rsp+248h+arg_48]
0x18001d957  mov     edi, edx
0x18001d959  mov     rbp, [rsp+248h+arg_30]
0x18001d961  mov     r12, rcx
0x18001d964  mov     r14, [rsp+248h+arg_28]
0x18001d96c  mov     rbx, [rsp+248h+lpModuleName]
0x18001d974  mov     [rsp+248h+var_180], rbp
0x18001d97c  mov     [rsp+248h+var_190], rax
0x18001d984  mov     [rsp+248h+var_188], r9
0x18001d98c  mov     [rsp+248h+var_178], r8
0x18001d994  call    cs:__imp_GetLastError
0x18001d99b  nop     dword ptr [rax+rax+00h]
0x18001d9a0  movzx   ecx, word ptr cs:aUnknown_0+8; ">"
0x18001d9a7  xor     edx, edx; Val
0x18001d9a9  movsd   xmm0, qword ptr cs:aUnknown_0; "<unknown>"
0x18001d9b1  mov     r8d, 0FAh; Size
0x18001d9b7  mov     word ptr [rsp+248h+var_160], cx
0x18001d9bf  mov     esi, eax
0x18001d9c1  lea     rcx, [rsp+248h+var_160+2]; void *
0x18001d9c9  mov     [rsp+248h+dwErrCode], eax
0x18001d9d0  movsd   qword ptr [rsp+248h+Filename], xmm0
0x18001d9d9  call    memset_0
0x18001d9de  cmp     cs:?g_pLogManager@@3PEAVILogManager@@EA, 0; ILogManager * g_pLogManager
0x18001d9e6  jz      loc_18001DC37
0x18001d9ec  test    r12, r12
0x18001d9ef  jz      loc_18001DC37
0x18001d9f5  or      [r12+4], edi
0x18001d9fa  xor     r13d, r13d
0x18001d9fd  mov     [rsp+248h+var_198], r13d
0x18001da05  test    rbx, rbx
0x18001da08  jz      short loc_18001DA61
0x18001da0a  mov     rcx, rbx; lpModuleName
0x18001da0d  call    pIPtoHModule
0x18001da12  test    rax, rax
0x18001da15  jz      short loc_18001DA59
0x18001da17  mov     r8d, 104h; nSize
0x18001da1d  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18001da25  mov     rcx, rax; hModule
0x18001da28  call    cs:__imp_GetModuleFileNameA
0x18001da2f  nop     dword ptr [rax+rax+00h]
0x18001da34  lea     edx, [r13+5Ch]; Ch
0x18001da38  lea     rcx, [rsp+248h+Filename]; Str
0x18001da40  call    cs:__imp_strrchr
0x18001da47  nop     dword ptr [rax+rax+00h]
0x18001da4c  mov     r13, rax
0x18001da4f  test    rax, rax
0x18001da52  jz      short loc_18001DA59
0x18001da54  inc     r13
0x18001da57  jmp     short loc_18001DA61
0x18001da59  lea     r13, [rsp+248h+Filename]
0x18001da61  mov     eax, [r12]
0x18001da65  cmp     eax, 65000000h
0x18001da6a  jz      short loc_18001DA70
0x18001da6c  test    eax, eax
0x18001da6e  jnz     short loc_18001DA96
0x18001da70  mov     ecx, cs:?g_dwPrevFlags@@3KA; ulong g_dwPrevFlags
0x18001da76  bt      ecx, 13h
0x18001da7a  jnb     short loc_18001DA85
0x18001da7c  mov     eax, 6B000000h
0x18001da81  mov     [r12], eax
0x18001da85  bt      ecx, 12h
0x18001da89  jnb     short loc_18001DA96
0x18001da8b  mov     [rsp+248h+var_198], 1
0x18001da96  add     eax, 0FF000000h
0x18001da9b  test    eax, 0FEFFFFFFh
0x18001daa0  jnz     short loc_18001DAF0
0x18001daa2  call    ?ShouldTelemetryAssert@@YAHXZ; ShouldTelemetryAssert(void)
0x18001daa7  test    eax, eax
0x18001daa9  jz      short loc_18001DAF0
0x18001daab  mov     rcx, [r12+8]; char *
0x18001dab0  mov     r8, r14; char *
0x18001dab3  mov     rdx, rbp; char *
0x18001dab6  call    ?BuildTelAssertReportA@@YAPEADPEBD00@Z; BuildTelAssertReportA(char const *,char const *,char const *)
0x18001dabb  mov     rbx, rax
0x18001dabe  mov     edx, [rsp+248h+arg_20]
0x18001dac5  mov     r8d, esi
0x18001dac8  mov     rcx, rax
0x18001dacb  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001dad0  call    cs:__imp_GetProcessHeap
0x18001dad7  nop     dword ptr [rax+rax+00h]
0x18001dadc  mov     r8, rbx; lpMem
0x18001dadf  xor     edx, edx; dwFlags
0x18001dae1  mov     rcx, rax; hHeap
0x18001dae4  call    cs:__imp_HeapFree
0x18001daeb  nop     dword ptr [rax+rax+00h]
0x18001daf0  mov     rax, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001daf7  mov     rcx, [rax]
0x18001dafa  mov     r15, [rcx+20h]
0x18001dafe  call    ?GetCurrentDateTime@@YANXZ; GetCurrentDateTime(void)
0x18001db03  movaps  xmm6, xmm0
0x18001db06  call    cs:__imp_GetCurrentThreadId
0x18001db0d  nop     dword ptr [rax+rax+00h]
0x18001db12  mov     edi, cs:?g_ProcessID@@3KA; ulong g_ProcessID
0x18001db18  mov     ebx, eax
0x18001db1a  mov     rsi, [r12+8]
0x18001db1f  mov     ebp, [r12+4]
0x18001db24  call    GetMinorTaskA
0x18001db29  mov     r14, rax
0x18001db2c  call    GetMajorTaskA
0x18001db31  mov     ecx, [rsp+248h+arg_50]
0x18001db38  mov     edx, 11h
0x18001db3d  mov     r9d, [r12]
0x18001db41  mov     r8, [rsp+248h+var_178]
0x18001db49  movsd   [rsp+248h+var_1B0], xmm6
0x18001db52  mov     [rsp+248h+var_1B8], ecx
0x18001db59  mov     rcx, [rsp+248h+var_190]
0x18001db61  mov     [rsp+248h+var_1C0], rcx
0x18001db69  mov     ecx, [rsp+248h+arg_40]
0x18001db70  mov     [rsp+248h+var_1C8], ecx
0x18001db77  lea     rcx, ?g_ProcessExeA@@3PADA; "<unknown>"
0x18001db7e  mov     [rsp+248h+var_1D0], r13
0x18001db83  mov     [rsp+248h+var_1D8], rcx
0x18001db88  mov     rcx, [rsp+248h+var_188]
0x18001db90  mov     [rsp+248h+var_1E0], rcx
0x18001db95  mov     rcx, [rsp+248h+var_180]
0x18001db9d  mov     [rsp+248h+var_1E8], ebx
0x18001dba1  mov     [rsp+248h+var_1F0], edi
0x18001dba5  mov     [rsp+248h+var_1F8], rsi
0x18001dbaa  mov     [rsp+248h+var_200], ebp
0x18001dbae  mov     [rsp+248h+var_208], rcx
0x18001dbb3  mov     ecx, [rsp+248h+arg_20]
0x18001dbba  mov     [rsp+248h+var_210], 0
0x18001dbc3  mov     [rsp+248h+var_218], ecx
0x18001dbc7  mov     rcx, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001dbce  mov     [rsp+248h+var_220], r14
0x18001dbd3  mov     [rsp+248h+var_228], rax
0x18001dbd8  mov     rax, r15
0x18001dbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe0  mov     ebx, eax
0x18001dbe2  cmp     eax, 4
0x18001dbe5  jnz     short loc_18001DBFB
0x18001dbe7  call    WdsSetupLogDestroy
0x18001dbec  xor     ecx, ecx; uExitCode
0x18001dbee  call    cs:__imp_ExitProcess
0x18001dbfb  cmp     [rsp+248h+var_198], 0
0x18001dc03  jz      short loc_18001DC20
0x18001dc05  xor     r9d, r9d; lpArguments
0x18001dc08  xor     r8d, r8d; nNumberOfArguments
0x18001dc0b  mov     ecx, 0C0000025h; dwExceptionCode
0x18001dc10  lea     edx, [r9+1]; dwExceptionFlags
0x18001dc14  call    cs:__imp_RaiseException
0x18001dc1b  nop     dword ptr [rax+rax+00h]
0x18001dc20  mov     ecx, [rsp+248h+dwErrCode]; dwErrCode
0x18001dc27  call    cs:__imp_SetLastError
0x18001dc2e  nop     dword ptr [rax+rax+00h]
0x18001dc33  mov     eax, ebx
0x18001dc35  jmp     short loc_18001DC39
0x18001dc37  xor     eax, eax
0x18001dc39  mov     rcx, [rsp+248h+var_58]
0x18001dc41  xor     rcx, rsp; StackCookie
0x18001dc44  call    __security_check_cookie
0x18001dc49  lea     r11, [rsp+248h+var_38]
0x18001dc51  mov     rbx, [r11+48h]
0x18001dc55  movaps  xmm6, xmmword ptr [r11-10h]
0x18001dc5a  mov     rsp, r11
0x18001dc5d  pop     r15
0x18001dc5f  pop     r14
0x18001dc61  pop     r13
0x18001dc63  pop     r12
0x18001dc65  pop     rdi
0x18001dc66  pop     rsi
0x18001dc67  pop     rbp
0x18001dc68  retn
```
