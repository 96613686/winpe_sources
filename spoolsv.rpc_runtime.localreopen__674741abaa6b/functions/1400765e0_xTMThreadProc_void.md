# xTMThreadProc(void *)

- ea: `0x1400765e0`
- end: `0x14007674c`
- name: `?xTMThreadProc@@YAKPEAX@Z`
- size: `364`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140015290`
- `0x1400765e0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007668d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007668d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007666f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007670e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007666f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007670e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076633`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400766a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076633`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400766a0`

## string_xrefs

- `0x1400766e9`: `Woke and found job: uActiveThreads = %d.`
- `0x14007664e`: `xTMThreadProc`
- `0x1400766c1`: `xTMThreadProc`
- `0x1400766f4`: `xTMThreadProc`
- `0x140076732`: `xTMThreadProc`
- `0x140076727`: `No active jobs: uIdleThreads = %d, uActiveThreads = %d.`
- `0x1400766ba`: `No jobs, yet no idle threads.`

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
0x1400765e0  push    rbx
0x1400765e2  push    rbp
0x1400765e3  push    rsi
0x1400765e4  push    rdi
0x1400765e5  push    r14
0x1400765e7  sub     rsp, 20h
0x1400765eb  mov     rax, [rcx]
0x1400765ee  mov     rbx, rcx
0x1400765f1  xor     ebp, ebp
0x1400765f3  mov     rax, [rax+10h]
0x1400765f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400765fc  lea     rsi, [rbx+8]
0x140076600  mov     rdi, rax
0x140076603  test    rax, rax
0x140076606  jz      short loc_14007662C
0x140076608  mov     rax, [rbx]
0x14007660b  mov     rdx, rdi
0x14007660e  mov     rcx, rbx
0x140076611  mov     rax, [rax+8]
0x140076615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007661a  test    byte ptr [rsi], 1
0x14007661d  jnz     short loc_140076627
0x14007661f  mov     rax, [rbx]
0x140076622  mov     rcx, rbx
0x140076625  jmp     short loc_1400765F3
0x140076627  mov     ebp, 1
0x14007662c  mov     rcx, [rbx]
0x14007662f  mov     rcx, [rcx+28h]; lpCriticalSection
0x140076633  call    cs:__imp_EnterCriticalSection
0x14007663a  nop     dword ptr [rax+rax+00h]
0x14007663f  mov     r8d, [rbx+10h]
0x140076643  lea     rdx, aGoingToSleepUi; "Going to sleep: uIdle = %d, uActive = %"...
0x14007664a  mov     r9d, [rbx+0Ch]
0x14007664e  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x140076655  inc     r8d
0x140076658  dec     r9d
0x14007665b  mov     [rbx+10h], r8d
0x14007665f  mov     [rbx+0Ch], r9d
0x140076663  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140076668  mov     rcx, [rbx]
0x14007666b  mov     rcx, [rcx+28h]; lpCriticalSection
0x14007666f  call    cs:__imp_LeaveCriticalSection
0x140076676  nop     dword ptr [rax+rax+00h]
0x14007667b  test    ebp, ebp
0x14007667d  jnz     loc_140076723
0x140076683  mov     rdx, [rbx]
0x140076686  mov     rcx, [rbx+18h]; hHandle
0x14007668a  mov     edx, [rdx+4]; dwMilliseconds
0x14007668d  call    cs:__imp_WaitForSingleObject
0x140076694  nop     dword ptr [rax+rax+00h]
0x140076699  mov     rcx, [rbx]
0x14007669c  mov     rcx, [rcx+28h]; lpCriticalSection
0x1400766a0  call    cs:__imp_EnterCriticalSection
0x1400766a7  nop     dword ptr [rax+rax+00h]
0x1400766ac  test    byte ptr [rsi], 1
0x1400766af  jz      short loc_1400766CF
0x1400766b1  xor     edi, edi
0x1400766b3  mov     eax, [rbx+10h]
0x1400766b6  test    eax, eax
0x1400766b8  jnz     short loc_140076702
0x1400766ba  lea     rdx, aNoJobsYetNoIdl; "No jobs, yet no idle threads."
0x1400766c1  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x1400766c8  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400766cd  jmp     short loc_140076707
0x1400766cf  mov     rax, [rbx]
0x1400766d2  mov     rcx, rbx
0x1400766d5  mov     rax, [rax+10h]
0x1400766d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400766de  mov     rdi, rax
0x1400766e1  test    rax, rax
0x1400766e4  jz      short loc_1400766B3
0x1400766e6  inc     dword ptr [rbx+0Ch]
0x1400766e9  lea     rdx, aWokeAndFoundJo; "Woke and found job: uActiveThreads = %d"...
0x1400766f0  mov     r8d, [rbx+0Ch]
0x1400766f4  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x1400766fb  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140076700  jmp     short loc_140076707
0x140076702  dec     eax
0x140076704  mov     [rbx+10h], eax
0x140076707  mov     rcx, [rbx]
0x14007670a  mov     rcx, [rcx+28h]; lpCriticalSection
0x14007670e  call    cs:__imp_LeaveCriticalSection
0x140076715  nop     dword ptr [rax+rax+00h]
0x14007671a  test    rdi, rdi
0x14007671d  jnz     loc_140076608
0x140076723  mov     r9d, [rbx+0Ch]
0x140076727  lea     rdx, aNoActiveJobsUi; "No active jobs: uIdleThreads = %d, uAct"...
0x14007672e  mov     r8d, [rbx+10h]
0x140076732  lea     rcx, aXtmthreadproc; "xTMThreadProc"
0x140076739  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007673e  xor     eax, eax
0x140076740  add     rsp, 20h
0x140076744  pop     r14
0x140076746  pop     rdi
0x140076747  pop     rsi
0x140076748  pop     rbp
0x140076749  pop     rbx
0x14007674a  retn
```
