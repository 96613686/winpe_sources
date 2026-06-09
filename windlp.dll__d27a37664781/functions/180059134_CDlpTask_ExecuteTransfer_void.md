# CDlpTask::ExecuteTransfer(void)

- ea: `0x180059134`
- end: `0x180059856`
- name: `?ExecuteTransfer@CDlpTask@@AEAAJXZ`
- size: `1826`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180054950`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x1800471c0`
- `0x180059134`
- `0x18006c014`
- `0x180075124`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800592f7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800592f7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800595ad`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800595ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800591e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800591e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800593a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800593a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005953d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005953d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180059476`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005974b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180059476`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005974b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059202`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005924c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059202`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005924c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005983c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005983c`

## string_xrefs

- `0x180059374`: `CDlpTask::ExecuteTransfer`
- `0x1800596d6`: `CDlpTask::ExecuteTransfer`
- `0x18005977f`: `Transfer thread has exited.`
- `0x180059736`: `Waiting for transfer thread to exit.`
- `0x18005945b`: `Transfer execution thread timeout period: [%d ms]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecuteTransfer(CDlpTask *this)
{
  void *v2; // rdi
  signed int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rbx
  HANDLE Thread; // rax
  signed int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rax
  char *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rax
  DWORD v17; // eax
  signed int LastError; // eax
  signed int v19; // eax
  bool v20; // sf
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  char *v24; // r14
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-60h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-58h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-40h] BYREF
  struct _FILETIME v29; // [rsp+48h] [rbp-38h]
  HANDLE v30; // [rsp+50h] [rbp-30h]
  int v31; // [rsp+68h] [rbp-18h]
  DWORD ExitCode; // [rsp+C0h] [rbp+40h] BYREF
  signed int v33; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v34; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int64 v35; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  v30 = 0;
  ExitCode = 0;
  v33 = 0;
  SystemTimeAsFileTime = 0;
  v35 = 0;
  v34 = 0;
  v3 = (*(__int64 (__fastcall **)(CDlpTask *, unsigned __int64 *, __int64 *))(*(_QWORD *)this + 224LL))(
         this,
         &v35,
         &v34);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_76;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( !v4 )
      goto LABEL_24;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3218;
    goto LABEL_22;
  }
  *((_QWORD *)this + 181) = v34;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v29 = SystemTimeAsFileTime;
  v6 = v34;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
  v31 = 1;
  *((struct _FILETIME *)this + 117) = v29;
  *((_QWORD *)this + 118) = v6;
  *((_QWORD *)this + 119) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v31 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
    v31 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  v31 = 1;
  CArray<DP_CPP<CProgressData>,DP_CPP<CProgressData>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 1024, 0);
  *((_DWORD *)this + 254) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v31 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
    v31 = 0;
  }
  v3 = CProgressList::AddItem((CDlpTask *)((char *)this + 1016), (CDlpTask *)((char *)this + 936));
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_76;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( !v4 )
      goto LABEL_24;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3229;
    goto LABEL_22;
  }
  Thread = CreateThread(0, 0, CDlpTask::ExecuteTransferThreadProc, this, 0, 0);
  v2 = Thread;
  if ( Thread )
  {
    v30 = Thread;
    *((_DWORD *)this + 361) = GetTickCount();
    *((_QWORD *)this + 182) = 0;
    if ( v35 )
      v10 = 100 * v34 / v35;
    else
      v10 = 0;
    *((_QWORD *)this + 183) = v10;
    v3 = CDlpTask::ProgressHandlerTransfer(this, 1u);
    v11 = (char *)this + 176;
    v12 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    if ( v3 >= 0 )
    {
      if ( v12 )
      {
        v15 = *((_DWORD *)this + 359);
        v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))((char *)this + 176);
        CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2, L"Transfer execution thread timeout period: [%d ms]", v15);
      }
      while ( 1 )
      {
        v17 = WaitForSingleObject(v2, *((_DWORD *)this + 359));
        if ( !v17 )
          break;
        if ( v17 != 258 )
        {
          if ( v17 != -1 )
          {
            v3 = -2147418113;
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
              goto LABEL_72;
            v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
            v14 = 0;
            if ( v13 )
            {
              LODWORD(lpThreadId) = -2147418113;
              dwCreationFlags[0] = 3279;
              goto LABEL_69;
            }
            goto LABEL_71;
          }
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 >= 0 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
            goto LABEL_72;
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          v14 = 0;
          if ( !v13 )
            goto LABEL_71;
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3274;
          goto LABEL_69;
        }
        v3 = CDlpTask::ProgressHandlerTransfer(this, 0);
        if ( v3 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
            goto LABEL_72;
          v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          v14 = 0;
          if ( v13 )
          {
            LODWORD(lpThreadId) = v3;
            dwCreationFlags[0] = 3271;
            goto LABEL_69;
          }
          goto LABEL_71;
        }
      }
      if ( !GetExitCodeThread(v2, &ExitCode) )
      {
        v19 = GetLastError();
        v3 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v3 = (unsigned __int16)v19 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
          goto LABEL_72;
        v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v14 = 0;
        if ( v3 < 0 && v13 )
        {
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3262;
          goto LABEL_69;
        }
        goto LABEL_71;
      }
      v3 = CDlpTask::ProgressHandlerTransfer(this, 2u);
      if ( v3 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
          goto LABEL_72;
        v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v14 = 0;
        if ( v13 )
        {
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3266;
          goto LABEL_69;
        }
        goto LABEL_71;
      }
      v3 = ExitCode;
      v20 = (ExitCode & 0x80000000) != 0;
      if ( (int)ExitCode > 0 )
      {
        v3 = (unsigned __int16)ExitCode | 0x80070000;
        v20 = 1;
      }
      if ( !v20 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_72;
      v13 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_71;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3267;
    }
    else
    {
      if ( !v12 )
      {
LABEL_72:
        if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        {
          v22 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2, L"Waiting for transfer thread to exit.");
        }
        WaitForSingleObject(v2, 0xFFFFFFFF);
        if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        {
          v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"Transfer thread has exited.");
        }
        goto LABEL_76;
      }
      v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))((char *)this + 176);
      v14 = 0;
      if ( !v13 )
      {
LABEL_71:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
        goto LABEL_72;
      }
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3249;
    }
LABEL_69:
    v21 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v13,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::ExecuteTransfer",
            *(_QWORD *)dwCreationFlags,
            lpThreadId);
    v14 = (unsigned int)v21;
    if ( v21 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
    goto LABEL_71;
  }
  v2 = 0;
  v30 = 0;
  v8 = GetLastError();
  v3 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    v3 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
    {
LABEL_24:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
      goto LABEL_76;
    }
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3239;
LABEL_22:
    v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpTask::ExecuteTransfer",
           *(_QWORD *)dwCreationFlags,
           lpThreadId);
    v5 = (unsigned int)v9;
    if ( v9 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    goto LABEL_24;
  }
LABEL_76:
  v24 = (char *)this + 16;
  if ( (*(int (__fastcall **)(CDlpTask *, unsigned __int64 *, __int64 *))(*(_QWORD *)this + 224LL))(this, &v35, &v34) >= 0 )
  {
    (**(void (__fastcall ***)(char *, __int64, __int64, __int64 *, char *, _DWORD))v24)(
      (char *)this + 16,
      4099,
      1,
      &v34,
      (char *)this + 1488,
      0);
    (**(void (__fastcall ***)(char *, __int64, __int64, unsigned __int64 *, char *, _DWORD))v24)(
      (char *)this + 16,
      4100,
      1,
      &v35,
      (char *)this + 1488,
      0);
  }
  v33 = v3;
  (**(void (__fastcall ***)(char *, __int64, _QWORD, signed int *, char *, _DWORD))v24)(
    (char *)this + 16,
    4103,
    0,
    &v33,
    (char *)this + 1488,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180059134  push    rbp
0x180059136  push    rbx
0x180059137  push    rsi
0x180059138  push    rdi
0x180059139  push    r12
0x18005913b  push    r14
0x18005913d  push    r15
0x18005913f  mov     rbp, rsp
0x180059142  sub     rsp, 80h
0x180059149  mov     rsi, rcx
0x18005914c  xor     r12d, r12d
0x18005914f  mov     edi, r12d
0x180059152  mov     [rbp+var_30], r12
0x180059156  mov     [rbp+ExitCode], r12d
0x18005915a  mov     [rbp+arg_8], r12d
0x18005915e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r12
0x180059162  mov     [rbp+arg_18], r12
0x180059166  mov     [rbp+arg_10], r12
0x18005916a  mov     rax, [rcx]
0x18005916d  lea     r8, [rbp+arg_10]
0x180059171  lea     rdx, [rbp+arg_18]
0x180059175  mov     rax, [rax+0E0h]
0x18005917c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059181  mov     ebx, eax
0x180059183  test    eax, eax
0x180059185  jns     short loc_1800591D2
0x180059187  lea     r14, [rsi+0B0h]
0x18005918e  mov     rdx, [r14]
0x180059191  mov     rcx, r14
0x180059194  mov     rax, [rdx+10h]
0x180059198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005919d  test    rax, rax
0x1800591a0  jz      loc_18005978E
0x1800591a6  mov     rax, [r14]
0x1800591a9  mov     rcx, r14
0x1800591ac  mov     rax, [rax+10h]
0x1800591b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591b5  mov     ecx, r12d
0x1800591b8  test    rax, rax
0x1800591bb  jz      loc_18005939A
0x1800591c1  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x1800591c5  mov     [rsp+80h+dwCreationFlags], 0C92h
0x1800591cd  jmp     loc_180059374
0x1800591d2  mov     rax, [rbp+arg_10]
0x1800591d6  mov     [rsi+5A8h], rax
0x1800591dd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800591e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800591e7  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800591ea  mov     dword ptr [rbp+var_38+4], eax
0x1800591ed  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800591f0  mov     dword ptr [rbp+var_38], eax
0x1800591f3  lea     r14, [rsi+3A8h]
0x1800591fa  mov     rbx, [rbp+arg_10]
0x1800591fe  lea     rcx, [r14+20h]; lpCriticalSection
0x180059202  call    cs:__imp_EnterCriticalSection
0x180059208  mov     [rbp+var_18], 1
0x18005920f  mov     rax, [rbp+var_38]
0x180059213  mov     [r14], rax
0x180059216  mov     [r14+8], rbx
0x18005921a  mov     [r14+10h], r12
0x18005921e  xor     ecx, ecx
0x180059220  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180059225  mov     eax, [rbp+var_18]
0x180059228  test    eax, eax
0x18005922a  jz      short loc_18005923A
0x18005922c  lea     rcx, [r14+20h]; lpCriticalSection
0x180059230  call    cs:__imp_LeaveCriticalSection
0x180059236  mov     [rbp+var_18], r12d
0x18005923a  xor     ecx, ecx
0x18005923c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180059241  lea     rbx, [rsi+3F8h]
0x180059248  lea     rcx, [rbx+20h]; lpCriticalSection
0x18005924c  call    cs:__imp_EnterCriticalSection
0x180059252  mov     [rbp+var_18], 1
0x180059259  lea     rcx, [rbx+8]
0x18005925d  xor     edx, edx
0x18005925f  call    ?SetSize@?$CArray@V?$DP_CPP@VCProgressData@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_CPP<CProgressData>,DP_CPP<CProgressData>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180059264  mov     [rbx], r12d
0x180059267  xor     ecx, ecx
0x180059269  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005926e  mov     eax, [rbp+var_18]
0x180059271  test    eax, eax
0x180059273  jz      short loc_180059283
0x180059275  lea     rcx, [rbx+20h]; lpCriticalSection
0x180059279  call    cs:__imp_LeaveCriticalSection
0x18005927f  mov     [rbp+var_18], r12d
0x180059283  mov     rdx, r14; struct CProgressData *
0x180059286  mov     rcx, rbx; this
0x180059289  call    ?AddItem@CProgressList@@QEAAJPEAVCProgressData@@@Z; CProgressList::AddItem(CProgressData *)
0x18005928e  mov     ebx, eax
0x180059290  test    eax, eax
0x180059292  jns     short loc_1800592DF
0x180059294  lea     r14, [rsi+0B0h]
0x18005929b  mov     rax, [r14]
0x18005929e  mov     rcx, r14
0x1800592a1  mov     rax, [rax+10h]
0x1800592a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592aa  test    rax, rax
0x1800592ad  jz      loc_18005978E
0x1800592b3  mov     rax, [r14]
0x1800592b6  mov     rcx, r14
0x1800592b9  mov     rax, [rax+10h]
0x1800592bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592c2  mov     ecx, r12d
0x1800592c5  test    rax, rax
0x1800592c8  jz      loc_18005939A
0x1800592ce  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x1800592d2  mov     [rsp+80h+dwCreationFlags], 0C9Dh
0x1800592da  jmp     loc_180059374
0x1800592df  mov     [rsp+80h+lpThreadId], r12; lpThreadId
0x1800592e4  mov     [rsp+80h+dwCreationFlags], r12d; dwCreationFlags
0x1800592e9  mov     r9, rsi; lpParameter
0x1800592ec  lea     r8, ?ExecuteTransferThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x1800592f3  xor     edx, edx; dwStackSize
0x1800592f5  xor     ecx, ecx; lpThreadAttributes
0x1800592f7  call    cs:__imp_CreateThread
0x1800592fd  mov     rdi, rax
0x180059300  test    rax, rax
0x180059303  jnz     loc_1800593A4
0x180059309  mov     rdi, r12
0x18005930c  mov     [rbp+var_30], r12
0x180059310  call    cs:__imp_GetLastError
0x180059316  mov     ebx, eax
0x180059318  test    eax, eax
0x18005931a  jnz     short loc_180059323
0x18005931c  mov     ebx, 80004005h
0x180059321  jmp     short loc_18005932E
0x180059323  jle     short loc_18005932E
0x180059325  movzx   ebx, ax
0x180059328  or      ebx, 80070000h
0x18005932e  lea     r14, [rsi+0B0h]
0x180059335  mov     rax, [r14]
0x180059338  mov     rcx, r14
0x18005933b  mov     rax, [rax+10h]
0x18005933f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059344  test    rax, rax
0x180059347  jz      loc_18005978E
0x18005934d  mov     rax, [r14]
0x180059350  mov     rcx, r14
0x180059353  mov     rax, [rax+10h]
0x180059357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005935c  mov     ecx, r12d
0x18005935f  test    ebx, ebx
0x180059361  jns     short loc_18005939A
0x180059363  test    rax, rax
0x180059366  jz      short loc_18005939A
0x180059368  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x18005936c  mov     [rsp+80h+dwCreationFlags], 0CA7h
0x180059374  lea     r9, aCdlptaskExecut_2; "CDlpTask::ExecuteTransfer"
0x18005937b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180059382  mov     edx, 4
0x180059387  mov     rcx, rax
0x18005938a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18005938f  mov     ecx, eax
0x180059391  test    eax, eax
0x180059393  jns     short loc_18005939A
0x180059395  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005939a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005939f  jmp     loc_18005978E
0x1800593a4  mov     [rbp+var_30], rdi
0x1800593a8  call    cs:__imp_GetTickCount
0x1800593ae  mov     [rsi+5A4h], eax
0x1800593b4  mov     [rsi+5B0h], r12
0x1800593bb  mov     rcx, [rbp+arg_18]
0x1800593bf  test    rcx, rcx
0x1800593c2  jz      short loc_1800593D0
0x1800593c4  imul    rax, [rbp+arg_10], 64h ; 'd'
0x1800593c9  xor     edx, edx
0x1800593cb  div     rcx
0x1800593ce  jmp     short loc_1800593D3
0x1800593d0  mov     rax, r12
0x1800593d3  mov     [rsi+5B8h], rax
0x1800593da  mov     edx, 1; unsigned int
0x1800593df  mov     rcx, rsi; this
0x1800593e2  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x1800593e7  mov     ebx, eax
0x1800593e9  lea     r14, [rsi+0B0h]
0x1800593f0  mov     rax, [r14]
0x1800593f3  mov     rax, [rax+10h]
0x1800593f7  mov     r15d, 2
0x1800593fd  mov     rcx, r14
0x180059400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059405  test    ebx, ebx
0x180059407  jns     short loc_18005943E
0x180059409  test    rax, rax
0x18005940c  jz      loc_180059701
0x180059412  mov     rax, [r14]
0x180059415  mov     rcx, r14
0x180059418  mov     rax, [rax+10h]
0x18005941c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059421  mov     ecx, r12d
0x180059424  test    rax, rax
0x180059427  jz      loc_1800596FC
0x18005942d  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x180059431  mov     [rsp+80h+dwCreationFlags], 0CB1h
0x180059439  jmp     loc_1800596D6
0x18005943e  test    rax, rax
0x180059441  jz      short loc_18005946D
0x180059443  mov     ebx, [rsi+59Ch]
0x180059449  mov     rax, [r14]
0x18005944c  mov     rcx, r14
0x18005944f  mov     rax, [rax+10h]
0x180059453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059458  mov     r9d, ebx
0x18005945b  lea     r8, aTransferExecut; "Transfer execution thread timeout perio"...
0x180059462  mov     edx, r15d
0x180059465  mov     rcx, rax
0x180059468  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18005946d  mov     edx, [rsi+59Ch]; dwMilliseconds
0x180059473  mov     rcx, rdi; hHandle
0x180059476  call    cs:__imp_WaitForSingleObject
0x18005947c  test    eax, eax
0x18005947e  jz      loc_1800595A6
0x180059484  cmp     eax, 102h
0x180059489  jnz     short loc_1800594E7
0x18005948b  xor     edx, edx; unsigned int
0x18005948d  mov     rcx, rsi; this
0x180059490  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x180059495  mov     ebx, eax
0x180059497  test    eax, eax
0x180059499  jns     short loc_18005946D
0x18005949b  mov     rax, [rsi+0B0h]
0x1800594a2  mov     rcx, r14
0x1800594a5  mov     rax, [rax+10h]
0x1800594a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594ae  test    rax, rax
0x1800594b1  jz      loc_180059701
0x1800594b7  mov     rax, [rsi+0B0h]
0x1800594be  mov     rcx, r14
0x1800594c1  mov     rax, [rax+10h]
0x1800594c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594ca  mov     ecx, r12d
0x1800594cd  test    rax, rax
0x1800594d0  jz      loc_1800596FC
0x1800594d6  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x1800594da  mov     [rsp+80h+dwCreationFlags], 0CC7h
0x1800594e2  jmp     loc_1800596D6
0x1800594e7  cmp     eax, 0FFFFFFFFh
0x1800594ea  jz      short loc_18005953D
0x1800594ec  mov     ebx, 8000FFFFh
0x1800594f1  mov     rax, [rsi+0B0h]
0x1800594f8  mov     rcx, r14
0x1800594fb  mov     rax, [rax+10h]
0x1800594ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059504  test    rax, rax
0x180059507  jz      loc_180059701
0x18005950d  mov     rax, [rsi+0B0h]
0x180059514  mov     rcx, r14
0x180059517  mov     rax, [rax+10h]
0x18005951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059520  mov     ecx, r12d
0x180059523  test    rax, rax
0x180059526  jz      loc_1800596FC
0x18005952c  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x180059530  mov     [rsp+80h+dwCreationFlags], 0CCFh
0x180059538  jmp     loc_1800596D6
0x18005953d  call    cs:__imp_GetLastError
0x180059543  mov     ebx, eax
0x180059545  test    eax, eax
0x180059547  jle     short loc_180059552
0x180059549  movzx   ebx, ax
0x18005954c  or      ebx, 80070000h
0x180059552  test    ebx, ebx
0x180059554  jns     loc_180059701
0x18005955a  mov     rax, [rsi+0B0h]
0x180059561  mov     rcx, r14
0x180059564  mov     rax, [rax+10h]
0x180059568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005956d  test    rax, rax
0x180059570  jz      loc_180059701
0x180059576  mov     rax, [rsi+0B0h]
0x18005957d  mov     rcx, r14
0x180059580  mov     rax, [rax+10h]
0x180059584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059589  mov     ecx, r12d
0x18005958c  test    rax, rax
0x18005958f  jz      loc_1800596FC
0x180059595  mov     dword ptr [rsp+80h+lpThreadId], ebx
0x180059599  mov     [rsp+80h+dwCreationFlags], 0CCAh
0x1800595a1  jmp     loc_1800596D6
0x1800595a6  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800595aa  mov     rcx, rdi; hThread
0x1800595ad  call    cs:__imp_GetExitCodeThread
0x1800595b3  test    eax, eax
0x1800595b5  jnz     short loc_180059629
0x1800595b7  call    cs:__imp_GetLastError
0x1800595bd  mov     ebx, eax
0x1800595bf  test    eax, eax
0x1800595c1  jnz     short loc_1800595CA
0x1800595c3  mov     ebx, 80004005h
0x1800595c8  jmp     short loc_1800595D5
0x1800595ca  jle     short loc_1800595D5
0x1800595cc  movzx   ebx, ax
0x1800595cf  or      ebx, 80070000h
0x1800595d5  mov     rax, [rsi+0B0h]
0x1800595dc  mov     rcx, r14
0x1800595df  mov     rax, [rax+10h]
0x1800595e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595e8  test    rax, rax
0x1800595eb  jz      loc_180059701
  ... truncated ...
```
