# ServiceStop

- ea: `0x1800042d4`
- end: `0x180004429`
- name: `ServiceStop`
- size: `341`
- prototype: `__int64 __fastcall(int, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003150`
- `0x180004490`

## callees

- `0x180003450`
- `0x18000427c`
- `0x1800042d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000437d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000437d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043b6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800043fb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800043fb`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180004399`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180004399`

## pseudocode

```c
__int64 __fastcall ServiceStop(int a1, DWORD a2)
{
  unsigned int LastError; // ebx

  EnterCriticalSection(&csForProcessCount);
  if ( !a1 && (__int128 *)xmmword_1800096E0 != &xmmword_1800096E0 )
  {
    LastError = 0;
LABEL_6:
    LeaveCriticalSection(&csForProcessCount);
    return LastError;
  }
  LastError = MySetServiceStatus(3u, 0);
  if ( LastError && !a1 )
    goto LABEL_6;
  LeaveCriticalSection(&csForProcessCount);
  LastError = SeclStopRpcServer();
  if ( !LastError || a1 )
  {
    LastError = MySetServiceStatus(3u, 1u);
    if ( !LastError || a1 )
    {
      if ( g_fIsCsInitialized )
      {
        DeleteCriticalSection(&csForProcessCount);
        g_fIsCsInitialized = 0;
      }
      if ( *(&hServiceStatus + 1) )
      {
        LsaDeregisterLogonProcess(*(&hServiceStatus + 1));
        *(&hServiceStatus + 1) = 0;
      }
      if ( g_hIOCP )
      {
        CloseHandle(g_hIOCP);
        g_hIOCP = 0;
      }
      g_state.dwServiceType = 32;
      *(_QWORD *)&g_state.dwCurrentState = 1;
      g_state.dwWin32ExitCode = a2;
      *(_QWORD *)&g_state.dwCheckPoint = 0;
      if ( SetServiceStatus(hServiceStatus, &g_state) )
        return 0;
      LastError = GetLastError();
      if ( !LastError || a1 )
        return 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800042d4  mov     [rsp+arg_0], rbx
0x1800042d9  mov     [rsp+arg_8], rsi
0x1800042de  push    rdi
0x1800042df  sub     rsp, 20h
0x1800042e3  mov     edi, ecx
0x1800042e5  mov     esi, edx
0x1800042e7  lea     rcx, csForProcessCount; lpCriticalSection
0x1800042ee  call    cs:__imp_EnterCriticalSection
0x1800042f4  test    edi, edi
0x1800042f6  jnz     short loc_18000430C
0x1800042f8  lea     rax, xmmword_1800096E0
0x1800042ff  cmp     qword ptr cs:xmmword_1800096E0, rax
0x180004306  jz      short loc_18000430C
0x180004308  xor     ebx, ebx
0x18000430a  jmp     short loc_180004320
0x18000430c  xor     edx, edx
0x18000430e  lea     ecx, [rdx+3]
0x180004311  call    MySetServiceStatus
0x180004316  mov     ebx, eax
0x180004318  test    eax, eax
0x18000431a  jz      short loc_180004332
0x18000431c  test    edi, edi
0x18000431e  jnz     short loc_180004332
0x180004320  lea     rcx, csForProcessCount; lpCriticalSection
0x180004327  call    cs:__imp_LeaveCriticalSection
0x18000432d  jmp     loc_180004417
0x180004332  lea     rcx, csForProcessCount; lpCriticalSection
0x180004339  call    cs:__imp_LeaveCriticalSection
0x18000433f  call    SeclStopRpcServer
0x180004344  mov     ebx, eax
0x180004346  test    eax, eax
0x180004348  jz      short loc_180004352
0x18000434a  test    edi, edi
0x18000434c  jz      loc_180004417
0x180004352  mov     edx, 1
0x180004357  lea     ecx, [rdx+2]
0x18000435a  call    MySetServiceStatus
0x18000435f  mov     ebx, eax
0x180004361  test    eax, eax
0x180004363  jz      short loc_18000436D
0x180004365  test    edi, edi
0x180004367  jz      loc_180004417
0x18000436d  cmp     cs:g_fIsCsInitialized, 0
0x180004374  jz      short loc_18000438D
0x180004376  lea     rcx, csForProcessCount; lpCriticalSection
0x18000437d  call    cs:__imp_DeleteCriticalSection
0x180004383  mov     cs:g_fIsCsInitialized, 0
0x18000438d  mov     rcx, qword ptr cs:hServiceStatus+8; LsaHandle
0x180004394  test    rcx, rcx
0x180004397  jz      short loc_1800043AA
0x180004399  call    cs:__imp_LsaDeregisterLogonProcess
0x18000439f  mov     qword ptr cs:hServiceStatus+8, 0
0x1800043aa  mov     rcx, cs:g_hIOCP; hObject
0x1800043b1  test    rcx, rcx
0x1800043b4  jz      short loc_1800043C7
0x1800043b6  call    cs:__imp_CloseHandle
0x1800043bc  mov     cs:g_hIOCP, 0
0x1800043c7  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x1800043ce  lea     rdx, g_state; lpServiceStatus
0x1800043d5  mov     cs:g_state.dwServiceType, 20h ; ' '
0x1800043df  mov     qword ptr cs:g_state.dwCurrentState, 1
0x1800043ea  mov     cs:g_state.dwWin32ExitCode, esi
0x1800043f0  mov     qword ptr cs:g_state.dwCheckPoint, 0
0x1800043fb  call    cs:__imp_SetServiceStatus
0x180004401  test    eax, eax
0x180004403  jnz     short loc_180004415
0x180004405  call    cs:__imp_GetLastError
0x18000440b  mov     ebx, eax
0x18000440d  test    eax, eax
0x18000440f  jz      short loc_180004415
0x180004411  test    edi, edi
0x180004413  jz      short loc_180004417
0x180004415  xor     ebx, ebx
0x180004417  mov     rsi, [rsp+28h+arg_8]
0x18000441c  mov     eax, ebx
0x18000441e  mov     rbx, [rsp+28h+arg_0]
0x180004423  add     rsp, 20h
0x180004427  pop     rdi
0x180004428  retn
```
