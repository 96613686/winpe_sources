# xTMThreadProc(void *)

- ea: `0x14006f700`
- end: `0x14006f84d`
- name: `?xTMThreadProc@@YAKPEAX@Z`
- size: `333`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140013fe8`
- `0x14006f700`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006f7a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006f7a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f816`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f816`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f7ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f7ae`

## string_xrefs

- `0x14006f829`: `No active jobs: uIdleThreads = %d, uActiveThreads = %d.`
- `0x14006f7c2`: `No jobs, yet no idle threads.`
- `0x14006f7f1`: `Woke and found job: uActiveThreads = %d.`
- `0x14006f768`: `xTMThreadProc`
- `0x14006f7c9`: `xTMThreadProc`
- `0x14006f7fc`: `xTMThreadProc`
- `0x14006f834`: `xTMThreadProc`

## pseudocode

```c
__int64 __fastcall xTMThreadProc(char *Parameter)
{
  __int64 v1; // rax
  int v3; // ebp
  _BYTE *v4; // rsi
  __int64 v5; // rdi
  int v6; // r9d
  int v7; // eax

  v1 = *(_QWORD *)Parameter;
  v3 = 0;
LABEL_2:
  v4 = Parameter + 8;
  v5 = (*(__int64 (**)(void))(v1 + 16))();
  if ( !v5 )
    goto LABEL_6;
  do
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)Parameter + 8LL))(Parameter, v5);
    if ( (*v4 & 1) == 0 )
    {
      v1 = *(_QWORD *)Parameter;
      goto LABEL_2;
    }
    v3 = 1;
LABEL_6:
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(*(_QWORD *)Parameter + 40LL));
    v6 = *((_DWORD *)Parameter + 3) - 1;
    ++*((_DWORD *)Parameter + 4);
    *((_DWORD *)Parameter + 3) = v6;
    PrvSpoolssTelemetry::WriteDbgTraceInfo("xTMThreadProc", L"Going to sleep: uIdle = %d, uActive = %d.");
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(*(_QWORD *)Parameter + 40LL));
    if ( v3 )
      break;
    WaitForSingleObject(*((HANDLE *)Parameter + 3), *(_DWORD *)(*(_QWORD *)Parameter + 4LL));
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(*(_QWORD *)Parameter + 40LL));
    if ( (*v4 & 1) != 0 )
    {
      v5 = 0;
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
      if ( v5 )
      {
        PrvSpoolssTelemetry::WriteDbgTraceInfo(
          "xTMThreadProc",
          L"Woke and found job: uActiveThreads = %d.",
          (unsigned int)++*((_DWORD *)Parameter + 3));
        goto LABEL_14;
      }
    }
    v7 = *((_DWORD *)Parameter + 4);
    if ( v7 )
      *((_DWORD *)Parameter + 4) = v7 - 1;
    else
      PrvSpoolssTelemetry::WriteDbgTraceInfo("xTMThreadProc", L"No jobs, yet no idle threads.");
LABEL_14:
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(*(_QWORD *)Parameter + 40LL));
  }
  while ( v5 );
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "xTMThreadProc",
    L"No active jobs: uIdleThreads = %d, uActiveThreads = %d.",
    *((unsigned int *)Parameter + 4),
    *((unsigned int *)Parameter + 3));
  return 0;
}

```

## disassembly

```asm
0x14006f700  push    rbx
0x14006f702  push    rbp
0x14006f703  push    rsi
0x14006f704  push    rdi
0x14006f705  push    r14
0x14006f707  sub     rsp, 20h
0x14006f70b  mov     rax, [rcx]
0x14006f70e  mov     rbx, rcx
0x14006f711  xor     ebp, ebp
0x14006f713  mov     rax, [rax+10h]
0x14006f717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006f71c  lea     rsi, [rbx+8]
0x14006f720  mov     rdi, rax
0x14006f723  test    rax, rax
0x14006f726  jz      short loc_14006F74C
0x14006f728  mov     rax, [rbx]
0x14006f72b  mov     rdx, rdi
0x14006f72e  mov     rcx, rbx
0x14006f731  mov     rax, [rax+8]
0x14006f735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006f73a  test    byte ptr [rsi], 1
0x14006f73d  jnz     short loc_14006F747
0x14006f73f  mov     rax, [rbx]
0x14006f742  mov     rcx, rbx
0x14006f745  jmp     short loc_14006F713
0x14006f747  mov     ebp, 1
0x14006f74c  mov     rcx, [rbx]
0x14006f74f  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f753  call    cs:__imp_EnterCriticalSection
0x14006f759  mov     r8d, [rbx+10h]
0x14006f75d  lea     rdx, aGoingToSleepUi; "Going to sleep: uIdle = %d, uActive = %"...
0x14006f764  mov     r9d, [rbx+0Ch]
0x14006f768  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x14006f76f  inc     r8d
0x14006f772  dec     r9d
0x14006f775  mov     [rbx+10h], r8d
0x14006f779  mov     [rbx+0Ch], r9d
0x14006f77d  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f782  mov     rcx, [rbx]
0x14006f785  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f789  call    cs:__imp_LeaveCriticalSection
0x14006f78f  test    ebp, ebp
0x14006f791  jnz     loc_14006F825
0x14006f797  mov     rdx, [rbx]
0x14006f79a  mov     rcx, [rbx+18h]; hHandle
0x14006f79e  mov     edx, [rdx+4]; dwMilliseconds
0x14006f7a1  call    cs:__imp_WaitForSingleObject
0x14006f7a7  mov     rcx, [rbx]
0x14006f7aa  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f7ae  call    cs:__imp_EnterCriticalSection
0x14006f7b4  test    byte ptr [rsi], 1
0x14006f7b7  jz      short loc_14006F7D7
0x14006f7b9  xor     edi, edi
0x14006f7bb  mov     eax, [rbx+10h]
0x14006f7be  test    eax, eax
0x14006f7c0  jnz     short loc_14006F80A
0x14006f7c2  lea     rdx, aNoJobsYetNoIdl; "No jobs, yet no idle threads."
0x14006f7c9  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x14006f7d0  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f7d5  jmp     short loc_14006F80F
0x14006f7d7  mov     rax, [rbx]
0x14006f7da  mov     rcx, rbx
0x14006f7dd  mov     rax, [rax+10h]
0x14006f7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006f7e6  mov     rdi, rax
0x14006f7e9  test    rax, rax
0x14006f7ec  jz      short loc_14006F7BB
0x14006f7ee  inc     dword ptr [rbx+0Ch]
0x14006f7f1  lea     rdx, aWokeAndFoundJo; "Woke and found job: uActiveThreads = %d"...
0x14006f7f8  mov     r8d, [rbx+0Ch]
0x14006f7fc  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x14006f803  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f808  jmp     short loc_14006F80F
0x14006f80a  dec     eax
0x14006f80c  mov     [rbx+10h], eax
0x14006f80f  mov     rcx, [rbx]
0x14006f812  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f816  call    cs:__imp_LeaveCriticalSection
0x14006f81c  test    rdi, rdi
0x14006f81f  jnz     loc_14006F728
0x14006f825  mov     r9d, [rbx+0Ch]
0x14006f829  lea     rdx, aNoActiveJobsUi; "No active jobs: uIdleThreads = %d, uAct"...
0x14006f830  mov     r8d, [rbx+10h]
0x14006f834  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x14006f83b  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f840  xor     eax, eax
0x14006f842  add     rsp, 20h
0x14006f846  pop     r14
0x14006f848  pop     rdi
0x14006f849  pop     rsi
0x14006f84a  pop     rbp
0x14006f84b  pop     rbx
0x14006f84c  retn
```
