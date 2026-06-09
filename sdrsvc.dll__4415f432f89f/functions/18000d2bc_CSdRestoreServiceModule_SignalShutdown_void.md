# CSdRestoreServiceModule::SignalShutdown(void)

- ea: `0x18000d2bc`
- end: `0x18000d3be`
- name: `?SignalShutdown@CSdRestoreServiceModule@@AEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e900`

## callees

- `0x18000d2bc`
- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000d364`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000d364`

## string_xrefs

- `0x18000d2d3`: `CSdRestoreServiceModule::SignalShutdown`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::SignalShutdown(CSdRestoreServiceModule *this)
{
  signed int LastFailureAsHRESULT; // ebx
  __int16 v2; // ax
  __int64 v3; // rcx
  signed int v5; // [rsp+30h] [rbp-40h] BYREF
  __int16 v6; // [rsp+34h] [rbp-3Ch]
  __int16 v7; // [rsp+36h] [rbp-3Ah]
  LARGE_INTEGER DueTime; // [rsp+80h] [rbp+10h] BYREF

  DueTime.QuadPart = (LONGLONG)this;
  LastFailureAsHRESULT = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v5, "CSdRestoreServiceModule::SignalShutdown", 702, 1);
  DueTime.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids);
  if ( hTimer )
  {
    DueTime.QuadPart = -1;
    _InterlockedExchange(&dword_18002E208, 1);
    if ( !SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v3);
      v5 = LastFailureAsHRESULT;
      v7 = 718;
      goto LABEL_10;
    }
    LastFailureAsHRESULT = 0;
    v2 = 718;
  }
  else
  {
    v2 = 710;
  }
  v6 = v2;
  v5 = LastFailureAsHRESULT;
LABEL_10:
  if ( LastFailureAsHRESULT < 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = LastFailureAsHRESULT;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000d2bc  mov     [rsp-8+arg_8], rbx
0x18000d2c1  mov     qword ptr [rsp-8+DueTime], rcx
0x18000d2c6  push    rbp
0x18000d2c7  mov     rbp, rsp
0x18000d2ca  sub     rsp, 70h
0x18000d2ce  mov     ebx, 1
0x18000d2d3  lea     rdx, aCsdrestoreserv_11; "CSdRestoreServiceModule::SignalShutdown"
0x18000d2da  mov     r9d, ebx; unsigned __int16
0x18000d2dd  lea     rcx, [rbp+var_40]; this
0x18000d2e1  mov     r8d, 2BEh; unsigned __int16
0x18000d2e7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d2ec  mov     qword ptr [rbp+DueTime], 0
0x18000d2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2fb  lea     rax, WPP_GLOBAL_Control
0x18000d302  cmp     rcx, rax
0x18000d305  jz      short loc_18000D323
0x18000d307  test    dword ptr [rcx+1Ch], 8000000h
0x18000d30e  jz      short loc_18000D323
0x18000d310  mov     rcx, [rcx+10h]
0x18000d314  lea     edx, [rbx+0Ch]
0x18000d317  lea     r8, WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids
0x18000d31e  call    WPP_SF_
0x18000d323  cmp     cs:hTimer, 0
0x18000d32b  jnz     short loc_18000D334
0x18000d32d  mov     eax, 2C6h
0x18000d332  jmp     short loc_18000D38A
0x18000d334  mov     qword ptr [rbp+DueTime], 0FFFFFFFFFFFFFFFFh
0x18000d33c  lea     rdx, [rbp+DueTime]; lpDueTime
0x18000d340  xchg    ebx, cs:dword_18002E208
0x18000d346  mov     rcx, cs:hTimer; hTimer
0x18000d34d  xor     r9d, r9d; pfnCompletionRoutine
0x18000d350  mov     [rsp+70h+fResume], 0; fResume
0x18000d358  xor     r8d, r8d; lPeriod
0x18000d35b  mov     [rsp+70h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18000d364  call    cs:__imp_SetWaitableTimer
0x18000d36a  test    eax, eax
0x18000d36c  jnz     short loc_18000D383
0x18000d36e  call    GetLastFailureAsHRESULT
0x18000d373  mov     ebx, eax
0x18000d375  mov     [rbp+var_40], eax
0x18000d378  mov     eax, 2CEh
0x18000d37d  mov     [rbp+var_3A], ax
0x18000d381  jmp     short loc_18000D391
0x18000d383  xor     ebx, ebx
0x18000d385  mov     eax, 2CEh
0x18000d38a  mov     [rbp+var_3C], ax
0x18000d38e  mov     [rbp+var_40], ebx
0x18000d391  test    ebx, ebx
0x18000d393  jns     short loc_18000D3A5
0x18000d395  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000d39f  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebx
0x18000d3a5  lea     rcx, [rbp+var_40]; this
0x18000d3a9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d3ae  mov     eax, ebx
0x18000d3b0  mov     rbx, [rsp+70h+arg_8]
0x18000d3b8  add     rsp, 70h
0x18000d3bc  pop     rbp
0x18000d3bd  retn
```
