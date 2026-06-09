# incrementsignal(void *)

- ea: `0x10040c410`
- end: `0x10040c5a4`
- name: `?incrementsignal@@YAIPEAX@Z`
- size: `404`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040c410`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040c4c1`
- `KERNEL32!EnterCriticalSection` at `0x10040c4fb`
- `KERNEL32!EnterCriticalSection` at `0x10040c4c1`
- `KERNEL32!EnterCriticalSection` at `0x10040c4fb`
- `KERNEL32!LeaveCriticalSection` at `0x10040c4e0`
- `KERNEL32!LeaveCriticalSection` at `0x10040c55c`
- `KERNEL32!LeaveCriticalSection` at `0x10040c4e0`
- `KERNEL32!LeaveCriticalSection` at `0x10040c55c`
- `KERNEL32!WaitForSingleObject` at `0x10040c4ee`
- `KERNEL32!WaitForSingleObject` at `0x10040c4ee`
- `KERNEL32!CloseHandle` at `0x10040c53a`
- `KERNEL32!CloseHandle` at `0x10040c53a`
- `ADVAPI32!SetServiceStatus` at `0x10040c52f`
- `ADVAPI32!SetServiceStatus` at `0x10040c52f`
- `sqlmin!?IsCompleted@StartupDependencies@@SA_NW4Components@1@@Z` at `0x10040c509`
- `sqlmin!?IsCompleted@StartupDependencies@@SA_NW4Components@1@@Z` at `0x10040c509`
- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040c455`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040c567`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040c567`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040c4b3`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040c4b3`
- `api-ms-win-crt-runtime-l1-1-0!_endthreadex` at `0x10040c56f`
- `api-ms-win-crt-runtime-l1-1-0!_endthreadex` at `0x10040c56f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall incrementsignal(void *a1)
{
  int v1; // ebx
  __int64 v2; // r8
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  void *v5; // rsp
  void *v6; // rsp
  void **v7; // r9
  HANDLE v8; // rdi
  __int64 v10; // [rsp+40h] [rbp+0h] BYREF
  _BYTE v11[6048]; // [rsp+50h] [rbp+10h] BYREF

  v10 = -2;
  v1 = (int)a1;
  v2 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
  if ( v2 )
  {
    v3 = 8 * v2 + 15;
    if ( v3 <= 8 * v2 )
      v3 = 0xFFFFFFFFFFFFFF0LL;
    v4 = v3 & 0xFFFFFFFFFFFFFFF0uLL;
    v5 = alloca(v4);
    v6 = alloca(v4);
    v7 = (void **)&v10;
  }
  else
  {
    v7 = 0;
  }
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v11, 0, v2, v7, 1, 0, 0);
  EnterCriticalSection(&SCMCrtSec);
  v8 = qword_1004D28C0;
  if ( v1 == 2 )
    v8 = hEvent;
  while ( 1 )
  {
    LeaveCriticalSection(&SCMCrtSec);
    WaitForSingleObject(v8, 0x2710u);
    EnterCriticalSection(&SCMCrtSec);
    if ( v1 == 2 )
    {
      if ( (unsigned __int8)StartupDependencies::IsCompleted(12) )
        break;
    }
    if ( SQLServiceStatus.dwCurrentState != v1 )
      break;
    ++SQLServiceStatus.dwCheckPoint;
    SetServiceStatus(SQLServiceHandle, &SQLServiceStatus);
  }
  CloseHandle(v8);
  if ( v1 == 2 )
    hEvent = 0;
  else
    qword_1004D28C0 = 0;
  LeaveCriticalSection(&SCMCrtSec);
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v11);
  _endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x10040c410  push    rbp
0x10040c412  mov     eax, 1800h
0x10040c417  call    _alloca_probe
0x10040c41c  sub     rsp, rax
0x10040c41f  lea     rbp, [rsp+40h]
0x10040c424  mov     [rbp+17C0h+var_17C0], 0FFFFFFFFFFFFFFFEh
0x10040c42c  mov     [rbp+17C0h+arg_0], rbx
0x10040c433  mov     [rbp+17C0h+arg_8], rsi
0x10040c43a  mov     [rbp+17C0h+arg_10], rdi
0x10040c441  mov     rax, cs:__security_cookie
0x10040c448  xor     rax, rbp
0x10040c44b  mov     [rbp+17C0h+var_10], rax
0x10040c452  mov     rbx, rcx
0x10040c455  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040c45c  mov     r8, [rax+8]
0x10040c460  xor     esi, esi
0x10040c462  test    r8, r8
0x10040c465  jz      short loc_10040C498
0x10040c467  lea     rax, ds:0[r8*8]
0x10040c46f  lea     rcx, [rax+0Fh]
0x10040c473  cmp     rcx, rax
0x10040c476  ja      short loc_10040C482
0x10040c478  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10040c482  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10040c486  mov     rax, rcx
0x10040c489  call    _alloca_probe
0x10040c48e  sub     rsp, rcx
0x10040c491  lea     r9, [rsp+1800h+var_17C0]
0x10040c496  jmp     short loc_10040C49B
0x10040c498  mov     r9, rsi
0x10040c49b  mov     [rsp+1800h+var_17D0], rsi
0x10040c4a0  mov     [rsp+1800h+var_17D8], rsi
0x10040c4a5  mov     [rsp+1800h+var_17E0], 1
0x10040c4ad  xor     edx, edx
0x10040c4af  lea     rcx, [rbp+17C0h+var_17B0]
0x10040c4b3  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040c4b9  nop
0x10040c4ba  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c4c1  call    cs:__imp_EnterCriticalSection
0x10040c4c7  mov     rdi, cs:qword_1004D28C0
0x10040c4ce  cmp     ebx, 2
0x10040c4d1  cmovz   rdi, cs:hEvent
0x10040c4d9  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c4e0  call    cs:__imp_LeaveCriticalSection
0x10040c4e6  mov     edx, 2710h; dwMilliseconds
0x10040c4eb  mov     rcx, rdi; hHandle
0x10040c4ee  call    cs:__imp_WaitForSingleObject
0x10040c4f4  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c4fb  call    cs:__imp_EnterCriticalSection
0x10040c501  cmp     ebx, 2
0x10040c504  jnz     short loc_10040C513
0x10040c506  lea     ecx, [rbx+0Ah]
0x10040c509  call    cs:__imp_?IsCompleted@StartupDependencies@@SA_NW4Components@1@@Z; StartupDependencies::IsCompleted(StartupDependencies::Components)
0x10040c50f  test    al, al
0x10040c511  jnz     short loc_10040C537
0x10040c513  cmp     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS SQLServiceStatus ...
0x10040c519  jnz     short loc_10040C537
0x10040c51b  inc     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS SQLServiceStatus ...
0x10040c521  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c528  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c52f  call    cs:__imp_SetServiceStatus
0x10040c535  jmp     short loc_10040C4D9
0x10040c537  mov     rcx, rdi; hObject
0x10040c53a  call    cs:__imp_CloseHandle
0x10040c540  cmp     ebx, 2
0x10040c543  jnz     short loc_10040C54E
0x10040c545  mov     cs:hEvent, rsi
0x10040c54c  jmp     short loc_10040C555
0x10040c54e  mov     cs:qword_1004D28C0, rsi
0x10040c555  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c55c  call    cs:__imp_LeaveCriticalSection
0x10040c562  nop
0x10040c563  lea     rcx, [rbp+17C0h+var_17B0]
0x10040c567  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040c56d  xor     ecx, ecx; ReturnCode
0x10040c56f  call    cs:__imp__endthreadex
0x10040c575  xor     eax, eax
0x10040c577  mov     rcx, [rbp+17C0h+var_10]
0x10040c57e  xor     rcx, rbp; StackCookie
0x10040c581  call    __security_check_cookie
0x10040c586  mov     rbx, [rbp+17C0h+arg_0]
0x10040c58d  mov     rsi, [rbp+17C0h+arg_8]
0x10040c594  mov     rdi, [rbp+17C0h+arg_10]
0x10040c59b  lea     rsp, [rbp+17C0h]
0x10040c5a2  pop     rbp
0x10040c5a3  retn
```
