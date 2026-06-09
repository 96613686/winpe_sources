# PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>::Start(IUnknown *,ushort *)

- ea: `0x180089110`
- end: `0x1800892ce`
- name: `?Start@?$PFS_SCHED_TASK@VRESPRI_TASK@@$1?CLSID_ResPriTask@@3U_GUID@@B@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `446`
- prototype: `__int64 __fastcall(char *lpParameter, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180088608`
- `0x180089110`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089138`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089138`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089221`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089221`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008915b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089177`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008915b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180089247`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180089247`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800891d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800891d9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800892c1`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800892c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180089277`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180089277`

## pseudocode

```c
__int64 __fastcall PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>::Start(
        char *lpParameter,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  signed int v4; // ebx
  HANDLE EventW; // rax
  HANDLE v6; // rax
  signed int v7; // eax
  signed int LastError; // eax
  HANDLE Thread; // rax
  void *v11; // rcx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  phModule = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpParameter + 64));
  if ( *((_QWORD *)lpParameter + 15) )
  {
    v4 = -2147483635;
    goto LABEL_13;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)lpParameter + 17) = EventW;
  if ( EventW && (v6 = CreateEventW(0, 0, 0, 0), (*((_QWORD *)lpParameter + 18) = v6) != 0)
    || (v7 = GetLastError(), (v4 = v7) == 0) )
  {
    v4 = (**a2)(a2, &IID_ITaskHandlerStatus, &v12);
    if ( v4 >= 0 )
    {
      if ( GetModuleHandleExW(
             4u,
             (LPCWSTR)PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::WorkerStartRoutine,
             &phModule) )
      {
        Thread = CreateThread(
                   0,
                   0,
                   PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::WorkerStartRoutine,
                   lpParameter,
                   4u,
                   0);
        *((_QWORD *)lpParameter + 15) = Thread;
        if ( Thread )
        {
          (*(void (__fastcall **)(char *))(*(_QWORD *)lpParameter + 8LL))(lpParameter);
          v11 = (void *)*((_QWORD *)lpParameter + 15);
          *((_QWORD *)lpParameter + 13) = v12;
          *((_QWORD *)lpParameter + 14) = phModule;
          v12 = 0;
          phModule = 0;
          ResumeThread(v11);
          v4 = 0;
          goto LABEL_13;
        }
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::CommandCtxCleanup(lpParameter);
    *(_OWORD *)(lpParameter + 136) = 0;
    *((_QWORD *)lpParameter + 19) = 0;
    *((_DWORD *)lpParameter + 38) = 3;
    goto LABEL_13;
  }
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 64));
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( phModule )
    FreeLibrary(phModule);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180089110  mov     [rsp+arg_8], rbx
0x180089115  push    rbp
0x180089116  push    rsi
0x180089117  push    rdi
0x180089118  sub     rsp, 30h
0x18008911c  mov     rdi, rcx
0x18008911f  mov     [rsp+48h+arg_0], 0
0x180089128  add     rcx, 40h ; '@'; lpCriticalSection
0x18008912c  mov     [rsp+48h+phModule], 0
0x180089135  mov     rsi, rdx
0x180089138  call    cs:__imp_EnterCriticalSection
0x18008913e  cmp     qword ptr [rdi+78h], 0
0x180089143  jz      short loc_18008914F
0x180089145  mov     ebx, 8000000Dh
0x18008914a  jmp     loc_18008921D
0x18008914f  xor     r9d, r9d; lpName
0x180089152  xor     r8d, r8d; bInitialState
0x180089155  xor     ecx, ecx; lpEventAttributes
0x180089157  lea     edx, [r9+1]; bManualReset
0x18008915b  call    cs:__imp_CreateEventW
0x180089161  mov     [rdi+88h], rax
0x180089168  test    rax, rax
0x18008916b  jz      short loc_180089189
0x18008916d  xor     r9d, r9d; lpName
0x180089170  xor     r8d, r8d; bInitialState
0x180089173  xor     edx, edx; bManualReset
0x180089175  xor     ecx, ecx; lpEventAttributes
0x180089177  call    cs:__imp_CreateEventW
0x18008917d  mov     [rdi+90h], rax
0x180089184  test    rax, rax
0x180089187  jnz     short loc_1800891A6
0x180089189  call    cs:__imp_GetLastError
0x18008918f  mov     ebx, eax
0x180089191  test    eax, eax
0x180089193  jz      short loc_1800891A6
0x180089195  jle     loc_18008921D
0x18008919b  movzx   ebx, bx
0x18008919e  or      ebx, 80070000h
0x1800891a4  jmp     short loc_18008921D
0x1800891a6  mov     rax, [rsi]
0x1800891a9  lea     r8, [rsp+48h+arg_0]
0x1800891ae  lea     rdx, IID_ITaskHandlerStatus
0x1800891b5  mov     rcx, rsi
0x1800891b8  mov     rax, [rax]
0x1800891bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891c0  mov     ebx, eax
0x1800891c2  test    eax, eax
0x1800891c4  js      short loc_1800891F8
0x1800891c6  mov     ebx, 4
0x1800891cb  lea     r8, [rsp+48h+phModule]; phModule
0x1800891d0  mov     ecx, ebx; dwFlags
0x1800891d2  lea     rdx, ?WorkerStartRoutine@?$PFS_SCHED_TASK@VHBDRV_TASK@@$1?CLSID_HbDrvTask@@3U_GUID@@B@@CAKPEAX@Z; lpModuleName
0x1800891d9  call    cs:__imp_GetModuleHandleExW
0x1800891df  test    eax, eax
0x1800891e1  jnz     short loc_18008925C
0x1800891e3  call    cs:__imp_GetLastError
0x1800891e9  mov     ebx, eax
0x1800891eb  test    eax, eax
0x1800891ed  jle     short loc_1800891F8
0x1800891ef  movzx   ebx, ax
0x1800891f2  or      ebx, 80070000h
0x1800891f8  mov     rcx, rdi
0x1800891fb  call    ?CommandCtxCleanup@?$PFS_SCHED_TASK@VHBDRV_TASK@@$1?CLSID_HbDrvTask@@3U_GUID@@B@@AEAAXXZ; PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::CommandCtxCleanup(void)
0x180089200  xorps   xmm0, xmm0
0x180089203  xor     eax, eax
0x180089205  movups  xmmword ptr [rdi+88h], xmm0
0x18008920c  mov     [rdi+98h], rax
0x180089213  mov     dword ptr [rdi+98h], 3
0x18008921d  lea     rcx, [rdi+40h]; lpCriticalSection
0x180089221  call    cs:__imp_LeaveCriticalSection
0x180089227  mov     rcx, [rsp+48h+arg_0]
0x18008922c  test    rcx, rcx
0x18008922f  jz      short loc_18008923D
0x180089231  mov     rax, [rcx]
0x180089234  mov     rax, [rax+10h]
0x180089238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008923d  mov     rcx, [rsp+48h+phModule]; hLibModule
0x180089242  test    rcx, rcx
0x180089245  jz      short loc_18008924D
0x180089247  call    cs:__imp_FreeLibrary
0x18008924d  mov     eax, ebx
0x18008924f  mov     rbx, [rsp+48h+arg_8]
0x180089254  add     rsp, 30h
0x180089258  pop     rdi
0x180089259  pop     rsi
0x18008925a  pop     rbp
0x18008925b  retn
0x18008925c  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180089265  lea     r8, ?WorkerStartRoutine@?$PFS_SCHED_TASK@VHBDRV_TASK@@$1?CLSID_HbDrvTask@@3U_GUID@@B@@CAKPEAX@Z; lpStartAddress
0x18008926c  mov     r9, rdi; lpParameter
0x18008926f  mov     [rsp+48h+dwCreationFlags], ebx; dwCreationFlags
0x180089273  xor     edx, edx; dwStackSize
0x180089275  xor     ecx, ecx; lpThreadAttributes
0x180089277  call    cs:__imp_CreateThread
0x18008927d  mov     [rdi+78h], rax
0x180089281  test    rax, rax
0x180089284  jz      loc_1800891E3
0x18008928a  mov     rax, [rdi]
0x18008928d  mov     rcx, rdi
0x180089290  mov     rax, [rax+8]
0x180089294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089299  mov     rax, [rsp+48h+arg_0]
0x18008929e  mov     rcx, [rdi+78h]; hThread
0x1800892a2  mov     [rdi+68h], rax
0x1800892a6  mov     rax, [rsp+48h+phModule]
0x1800892ab  mov     [rdi+70h], rax
0x1800892af  mov     [rsp+48h+arg_0], 0
0x1800892b8  mov     [rsp+48h+phModule], 0
0x1800892c1  call    cs:__imp_ResumeThread
0x1800892c7  xor     ebx, ebx
0x1800892c9  jmp     loc_18008921D
```
