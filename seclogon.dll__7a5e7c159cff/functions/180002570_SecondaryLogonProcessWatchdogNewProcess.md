# SecondaryLogonProcessWatchdogNewProcess

- ea: `0x180002570`
- end: `0x1800028e8`
- name: `SecondaryLogonProcessWatchdogNewProcess`
- size: `888`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180001470`

## callees

- `0x180002570`
- `0x180002d80`
- `0x180003450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800026ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800026ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800025dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800025dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800025f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800025f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002850`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800026af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800026af`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800028a7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800028a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002763`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002846`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002846`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800027e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800027e0`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180002756`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180002756`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180002741`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180002741`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1800027ba`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1800027ba`

## pseudocode

```c
__int64 __fastcall SecondaryLogonProcessWatchdogNewProcess(__int64 a1)
{
  int v2; // r15d
  int v3; // edi
  _OWORD *v4; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v6; // esi
  _QWORD *v7; // rcx
  __int128 *i; // r15
  signed int LastError; // r12d
  HANDLE JobObjectW; // rax
  __int128 JobObjectInformation; // [rsp+40h] [rbp-98h] BYREF
  _OWORD v13[4]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v14; // [rsp+90h] [rbp-48h]
  int TokenInformation; // [rsp+E8h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+F0h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+F8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  JobObjectInformation = 0;
  TokenInformation = 0;
  v4 = 0;
  memset(v13, 0, sizeof(v13));
  v14 = 0;
  if ( !a1 )
    goto LABEL_22;
  EnterCriticalSection(&csForProcessCount);
  v3 = 1;
  ProcessHeap = GetProcessHeap();
  v6 = 8;
  v4 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  if ( !v4 )
  {
    v2 = 1;
    v4 = v13;
  }
  v7 = (_QWORD *)*((_QWORD *)&xmmword_1800096E0 + 1);
  if ( **((__int128 ***)&xmmword_1800096E0 + 1) != &xmmword_1800096E0 )
    __fastfail(3u);
  *((_QWORD *)v4 + 6) = &xmmword_1800096E0;
  *((_QWORD *)v4 + 7) = v7;
  *v7 = v4 + 3;
  *((_QWORD *)&xmmword_1800096E0 + 1) = v4 + 3;
  *((_QWORD *)v4 + 1) = *(_QWORD *)a1;
  *((_QWORD *)v4 + 2) = *(_QWORD *)(a1 + 8);
  *((_QWORD *)v4 + 3) = *(_QWORD *)(a1 + 16);
  *((_QWORD *)v4 + 5) = *(_QWORD *)(a1 + 40);
  *((_DWORD *)v4 + 16) = v2 ^ 1;
  if ( !v2 )
  {
    *((_DWORD *)v4 + 8) = *(_DWORD *)(a1 + 32);
    for ( i = (__int128 *)xmmword_1800096E0; i != &xmmword_1800096E0; i = *(__int128 **)i )
    {
      ReturnLength = 0;
      TokenHandle = 0;
      if ( OpenProcessToken(*((HANDLE *)i - 5), 8u, &TokenHandle)
        && GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
      }
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      if ( LastError < 0 )
        goto LABEL_16;
      if ( TokenInformation == *(_DWORD *)(a1 + 32) )
      {
        *((_DWORD *)v4 + 8) = *((_DWORD *)i - 4);
        break;
      }
    }
    JobObjectW = CreateJobObjectW(0, 0);
    *(_QWORD *)v4 = JobObjectW;
    if ( !JobObjectW )
      goto LABEL_16;
    if ( !AssignProcessToJobObject(JobObjectW, *((HANDLE *)v4 + 1)) )
    {
      CloseHandle(*(HANDLE *)v4);
      *(_QWORD *)v4 = 0;
      v4 = 0;
      MySetServiceStatus(4, 0);
LABEL_22:
      v6 = 0;
      goto LABEL_32;
    }
    *(_QWORD *)&JobObjectInformation = v4;
    *((_QWORD *)&JobObjectInformation + 1) = g_hIOCP;
    if ( !SetInformationJobObject(
            *(HANDLE *)v4,
            JobObjectAssociateCompletionPortInformation,
            &JobObjectInformation,
            0x10u) )
    {
LABEL_16:
      v6 = GetLastError();
      goto LABEL_32;
    }
    if ( !g_fCleanupThreadActive )
      g_fCleanupThreadActive = QueueUserWorkItem(WaitForNextJobTermination, 0, 0x10u);
    v4 = 0;
    EnterCriticalSection(&csForProcessCount);
    g_state.dwServiceType = 32;
    g_state.dwCurrentState = 4;
    g_state.dwControlsAccepted = ((_QWORD)xmmword_1800096E0 == (_QWORD)&xmmword_1800096E0) + 130;
    g_state.dwWin32ExitCode = 0;
    *(_QWORD *)&g_state.dwCheckPoint = 0;
    if ( SetServiceStatus(hServiceStatus, &g_state) )
      v6 = 0;
    else
      v6 = GetLastError();
    LeaveCriticalSection(&csForProcessCount);
    if ( !v6 )
      goto LABEL_22;
    SetLastError(v6);
  }
LABEL_32:
  if ( v4 )
  {
    ReturnLength = 0;
    TerminateProcess(*((HANDLE *)v4 + 1), v6);
    SecondaryLogonCleanupJob(1, v4, &ReturnLength);
  }
  if ( v3 )
    LeaveCriticalSection(&csForProcessCount);
  return v6;
}

```

## disassembly

```asm
0x180002570  mov     r11, rsp
0x180002573  push    rbx
0x180002574  push    rsi
0x180002575  push    rdi
0x180002576  push    r12
0x180002578  push    r13
0x18000257a  push    r14
0x18000257c  push    r15
0x18000257e  sub     rsp, 0A0h
0x180002585  mov     r14, rcx
0x180002588  xor     r15d, r15d
0x18000258b  xor     edi, edi
0x18000258d  mov     [rsp+0D8h+var_A4], edi
0x180002591  xorps   xmm0, xmm0
0x180002594  movups  [rsp+0D8h+JobObjectInformation], xmm0
0x180002599  mov     [r11+10h], edi
0x18000259d  xor     ebx, ebx
0x18000259f  mov     [rsp+0D8h+var_A0], rbx
0x1800025a4  xor     eax, eax
0x1800025a6  movups  [rsp+0D8h+var_88], xmm0
0x1800025ab  movups  [rsp+0D8h+var_78], xmm0
0x1800025b0  movups  [rsp+0D8h+var_68], xmm0
0x1800025b5  movups  xmmword ptr [r11-58h], xmm0
0x1800025ba  mov     [r11-48h], rax
0x1800025be  test    rcx, rcx
0x1800025c1  jz      loc_180002787
0x1800025c7  lea     rcx, csForProcessCount; lpCriticalSection
0x1800025ce  call    cs:__imp_EnterCriticalSection
0x1800025d4  mov     edi, 1
0x1800025d9  mov     [rsp+0D8h+var_A4], edi
0x1800025dd  call    cs:__imp_GetProcessHeap
0x1800025e3  mov     rcx, rax; hHeap
0x1800025e6  mov     esi, 8
0x1800025eb  mov     r8d, 48h ; 'H'; dwBytes
0x1800025f1  mov     edx, esi; dwFlags
0x1800025f3  call    cs:__imp_HeapAlloc
0x1800025f9  mov     rbx, rax
0x1800025fc  mov     [rsp+0D8h+var_A0], rax
0x180002601  test    rax, rax
0x180002604  jnz     short loc_180002613
0x180002606  mov     r15d, edi
0x180002609  lea     rbx, [rsp+0D8h+var_88]
0x18000260e  mov     [rsp+0D8h+var_A0], rbx
0x180002613  mov     rcx, qword ptr cs:xmmword_1800096E0+8
0x18000261a  lea     r13, xmmword_1800096E0
0x180002621  cmp     [rcx], r13
0x180002624  jz      short loc_18000262D
0x180002626  mov     ecx, 3
0x18000262b  int     29h; Win8: RtlFailFast(ecx)
0x18000262d  lea     rax, [rbx+30h]
0x180002631  mov     [rax], r13
0x180002634  mov     [rax+8], rcx
0x180002638  mov     [rcx], rax
0x18000263b  mov     qword ptr cs:xmmword_1800096E0+8, rax
0x180002642  mov     rax, [r14]
0x180002645  mov     [rbx+8], rax
0x180002649  mov     rax, [r14+8]
0x18000264d  mov     [rbx+10h], rax
0x180002651  mov     rax, [r14+10h]
0x180002655  mov     [rbx+18h], rax
0x180002659  mov     rax, [r14+28h]
0x18000265d  mov     [rbx+28h], rax
0x180002661  mov     eax, r15d
0x180002664  xor     eax, edi
0x180002666  mov     [rbx+40h], eax
0x180002669  test    r15d, r15d
0x18000266c  jz      short loc_180002673
0x18000266e  jmp     loc_180002891
0x180002673  mov     eax, [r14+20h]
0x180002677  mov     [rbx+20h], eax
0x18000267a  mov     r15, qword ptr cs:xmmword_1800096E0
0x180002681  cmp     r15, r13
0x180002684  jz      loc_18000273D
0x18000268a  mov     [rsp+0D8h+arg_10], 0
0x180002695  mov     [rsp+0D8h+TokenHandle], 0
0x1800026a1  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x1800026a9  mov     edx, esi; DesiredAccess
0x1800026ab  mov     rcx, [r15-28h]; ProcessHandle
0x1800026af  call    cs:__imp_OpenProcessToken
0x1800026b5  test    eax, eax
0x1800026b7  jnz     short loc_1800026C4
0x1800026b9  call    cs:__imp_GetLastError
0x1800026bf  mov     r12d, eax
0x1800026c2  jmp     short loc_180002704
0x1800026c4  lea     rax, [rsp+0D8h+arg_10]
0x1800026cc  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x1800026d1  mov     r9d, 4; TokenInformationLength
0x1800026d7  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x1800026df  mov     edx, 0Ch; TokenInformationClass
0x1800026e4  mov     rcx, [rsp+0D8h+TokenHandle]; TokenHandle
0x1800026ec  call    cs:__imp_GetTokenInformation
0x1800026f2  test    eax, eax
0x1800026f4  jnz     short loc_180002701
0x1800026f6  call    cs:__imp_GetLastError
0x1800026fc  mov     r12d, eax
0x1800026ff  jmp     short loc_180002704
0x180002701  xor     r12d, r12d
0x180002704  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x18000270c  test    rcx, rcx
0x18000270f  jz      short loc_180002717
0x180002711  call    cs:__imp_CloseHandle
0x180002717  test    r12d, r12d
0x18000271a  jns     short loc_180002729
0x18000271c  call    cs:__imp_GetLastError
0x180002722  mov     esi, eax
0x180002724  jmp     loc_180002891
0x180002729  mov     eax, [r14+20h]
0x18000272d  cmp     [rsp+0D8h+TokenInformation], eax
0x180002734  jnz     short loc_18000278E
0x180002736  mov     eax, [r15-10h]
0x18000273a  mov     [rbx+20h], eax
0x18000273d  xor     edx, edx; lpName
0x18000273f  xor     ecx, ecx; lpJobAttributes
0x180002741  call    cs:__imp_CreateJobObjectW
0x180002747  mov     [rbx], rax
0x18000274a  test    rax, rax
0x18000274d  jz      short loc_18000271C
0x18000274f  mov     rdx, [rbx+8]; hProcess
0x180002753  mov     rcx, rax; hJob
0x180002756  call    cs:__imp_AssignProcessToJobObject
0x18000275c  test    eax, eax
0x18000275e  jnz     short loc_180002796
0x180002760  mov     rcx, [rbx]; hObject
0x180002763  call    cs:__imp_CloseHandle
0x180002769  mov     qword ptr [rbx], 0
0x180002770  xor     ebx, ebx
0x180002772  mov     [rsp+0D8h+var_A0], rbx
0x180002777  xor     edx, edx
0x180002779  mov     ecx, 4
0x18000277e  call    MySetServiceStatus
0x180002783  mov     [rsp+0D8h+var_A8], eax
0x180002787  xor     esi, esi
0x180002789  jmp     loc_180002891
0x18000278e  mov     r15, [r15]
0x180002791  jmp     loc_180002681
0x180002796  mov     qword ptr [rsp+0D8h+JobObjectInformation], rbx
0x18000279b  mov     rax, cs:g_hIOCP
0x1800027a2  mov     qword ptr [rsp+0D8h+JobObjectInformation+8], rax
0x1800027a7  mov     r9d, 10h; cbJobObjectInformationLength
0x1800027ad  lea     r8, [rsp+0D8h+JobObjectInformation]; lpJobObjectInformation
0x1800027b2  mov     edx, 7; JobObjectInformationClass
0x1800027b7  mov     rcx, [rbx]; hJob
0x1800027ba  call    cs:__imp_SetInformationJobObject
0x1800027c0  test    eax, eax
0x1800027c2  jz      loc_18000271C
0x1800027c8  cmp     cs:g_fCleanupThreadActive, 0
0x1800027cf  jnz     short loc_1800027EC
0x1800027d1  xor     edx, edx; Context
0x1800027d3  mov     r8d, 10h; Flags
0x1800027d9  lea     rcx, WaitForNextJobTermination; Function
0x1800027e0  call    cs:__imp_QueueUserWorkItem
0x1800027e6  mov     cs:g_fCleanupThreadActive, eax
0x1800027ec  xor     ebx, ebx
0x1800027ee  mov     [rsp+0D8h+var_A0], rbx
0x1800027f3  lea     rcx, csForProcessCount; lpCriticalSection
0x1800027fa  call    cs:__imp_EnterCriticalSection
0x180002800  xor     eax, eax
0x180002802  cmp     qword ptr cs:xmmword_1800096E0, r13
0x180002809  setz    al
0x18000280c  add     eax, 82h
0x180002811  mov     cs:g_state.dwServiceType, 20h ; ' '
0x18000281b  mov     cs:g_state.dwCurrentState, 4
0x180002825  mov     cs:g_state.dwControlsAccepted, eax
0x18000282b  mov     cs:g_state.dwWin32ExitCode, ebx
0x180002831  mov     qword ptr cs:g_state.dwCheckPoint, rbx
0x180002838  lea     rdx, g_state; lpServiceStatus
0x18000283f  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180002846  call    cs:__imp_SetServiceStatus
0x18000284c  test    eax, eax
0x18000284e  jnz     short loc_18000285A
0x180002850  call    cs:__imp_GetLastError
0x180002856  mov     esi, eax
0x180002858  jmp     short loc_18000285C
0x18000285a  xor     esi, esi
0x18000285c  lea     rcx, csForProcessCount; lpCriticalSection
0x180002863  call    cs:__imp_LeaveCriticalSection
0x180002869  mov     [rsp+0D8h+var_A8], esi
0x18000286d  test    esi, esi
0x18000286f  jz      loc_180002787
0x180002875  mov     ecx, esi; dwErrCode
0x180002877  call    cs:__imp_SetLastError
0x18000287d  jmp     short loc_180002891
0x18000287f  mov     esi, 0Dh
0x180002884  mov     [rsp+0D8h+var_A8], esi
0x180002888  mov     edi, [rsp+0D8h+var_A4]
0x18000288c  mov     rbx, [rsp+0D8h+var_A0]
0x180002891  test    rbx, rbx
0x180002894  jz      short loc_1800028C2
0x180002896  mov     [rsp+0D8h+arg_10], 0
0x1800028a1  mov     edx, esi; uExitCode
0x1800028a3  mov     rcx, [rbx+8]; hProcess
0x1800028a7  call    cs:__imp_TerminateProcess
0x1800028ad  lea     r8, [rsp+0D8h+arg_10]
0x1800028b5  mov     rdx, rbx
0x1800028b8  mov     ecx, 1
0x1800028bd  call    SecondaryLogonCleanupJob
0x1800028c2  test    edi, edi
0x1800028c4  jz      short loc_1800028D3
0x1800028c6  lea     rcx, csForProcessCount; lpCriticalSection
0x1800028cd  call    cs:__imp_LeaveCriticalSection
0x1800028d3  mov     eax, esi
0x1800028d5  add     rsp, 0A0h
0x1800028dc  pop     r15
0x1800028de  pop     r14
0x1800028e0  pop     r13
0x1800028e2  pop     r12
0x1800028e4  pop     rdi
0x1800028e5  pop     rsi
0x1800028e6  pop     rbx
0x1800028e7  retn
```
