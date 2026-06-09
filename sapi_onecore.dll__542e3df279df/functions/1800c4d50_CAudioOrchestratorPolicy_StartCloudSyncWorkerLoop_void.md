# CAudioOrchestratorPolicy::StartCloudSyncWorkerLoop(void)

- ea: `0x1800c4d50`
- end: `0x1800c4f0d`
- name: `?StartCloudSyncWorkerLoop@CAudioOrchestratorPolicy@@UEAAJXZ`
- size: `445`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x180082900`
- `0x18008618c`
- `0x1800c4d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c4e13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c4e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4e95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c4e3e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c4e3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4eae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4eae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4eeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4eeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c4ed3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c4ed3`

## pseudocode

```c
__int64 __fastcall CAudioOrchestratorPolicy::StartCloudSyncWorkerLoop(char *pv)
{
  int Win32Error; // esi
  HANDLE *v3; // rdi
  HANDLE EventW; // rax
  const wchar_t *v5; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  SpAutoLock::SpAutoLock((SpAutoLock *)&v10, (struct SpCritSect *)(pv + 128));
  if ( *((_QWORD *)pv + 27) )
  {
    Win32Error = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CAudioOrchestratorPolicy::StartCloudSyncWorkerLoop",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestratorpolicy.cpp(911)",
      -2147418113);
    v3 = (HANDLE *)(pv + 224);
LABEL_10:
    if ( *v3 )
    {
      CloseHandle(*v3);
      *v3 = 0;
    }
    v7 = (struct _TP_TIMER *)*((_QWORD *)pv + 27);
    if ( v7 )
    {
      CloseThreadpoolTimer(v7);
      *((_QWORD *)pv + 27) = 0;
    }
    goto LABEL_15;
  }
  v3 = (HANDLE *)(pv + 224);
  if ( *((_QWORD *)pv + 28) )
  {
    Win32Error = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CAudioOrchestratorPolicy::StartCloudSyncWorkerLoop",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestratorpolicy.cpp(912)",
      -2147418113);
    goto LABEL_10;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *v3 = EventW;
  if ( EventW )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(CAudioOrchestratorPolicy::CloudSyncThreadpoolCallback, pv, 0);
    *((_QWORD *)pv + 27) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      Win32Error = 0;
      *((_DWORD *)pv + 52) = 0;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      SetThreadpoolTimer(*((PTP_TIMER *)pv + 27), &SystemTimeAsFileTime, 0, 0);
      goto LABEL_15;
    }
    Win32Error = SpHrFromLastWin32Error();
    v5 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestratorpolicy.cpp(918)";
  }
  else
  {
    Win32Error = SpHrFromLastWin32Error();
    v5 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestratorpolicy.cpp(915)";
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    (const wchar_t *)&NLInternal::s_tracingPrefix,
    L"CAudioOrchestratorPolicy::StartCloudSyncWorkerLoop",
    v5,
    Win32Error);
  if ( Win32Error < 0 )
    goto LABEL_10;
LABEL_15:
  SpAutoLock::~SpAutoLock((SpAutoLock *)&v10);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800c4d50  mov     [rsp+arg_10], rbx
0x1800c4d55  mov     [rsp+arg_18], rsi
0x1800c4d5a  push    rdi
0x1800c4d5b  sub     rsp, 30h
0x1800c4d5f  mov     rbx, rcx
0x1800c4d62  lea     rdx, [rcx+80h]; struct SpCritSect *
0x1800c4d69  lea     rcx, [rsp+38h+arg_8]; this
0x1800c4d6e  call    ??0SpAutoLock@@QEAA@PEAVSpCritSect@@@Z; SpAutoLock::SpAutoLock(SpCritSect *)
0x1800c4d73  cmp     qword ptr [rbx+0D8h], 0
0x1800c4d7b  jz      short loc_1800C4DBF
0x1800c4d7d  mov     eax, 8000FFFFh
0x1800c4d82  lea     r9, aCaudioorchestr_123; "CAudioOrchestratorPolicy::StartCloudSyn"...
0x1800c4d89  mov     [rsp+38h+var_10], eax
0x1800c4d8d  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1800c4d94  mov     esi, eax
0x1800c4d96  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1800c4d9d  lea     rax, aOnecoreuapEndu_307; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800c4da4  mov     ecx, 2; int
0x1800c4da9  mov     [rsp+38h+var_18], rax
0x1800c4dae  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c4db3  lea     rdi, [rbx+0E0h]
0x1800c4dba  jmp     loc_1800C4E8D
0x1800c4dbf  lea     rdi, [rbx+0E0h]
0x1800c4dc6  cmp     qword ptr [rdi], 0
0x1800c4dca  jz      short loc_1800C4E07
0x1800c4dcc  mov     eax, 8000FFFFh
0x1800c4dd1  lea     r9, aCaudioorchestr_123; "CAudioOrchestratorPolicy::StartCloudSyn"...
0x1800c4dd8  mov     [rsp+38h+var_10], eax
0x1800c4ddc  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1800c4de3  mov     esi, eax
0x1800c4de5  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1800c4dec  lea     rax, aOnecoreuapEndu_333; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800c4df3  mov     ecx, 2; int
0x1800c4df8  mov     [rsp+38h+var_18], rax
0x1800c4dfd  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c4e02  jmp     loc_1800C4E8D
0x1800c4e07  xor     r9d, r9d; lpName
0x1800c4e0a  xor     r8d, r8d; bInitialState
0x1800c4e0d  xor     ecx, ecx; lpEventAttributes
0x1800c4e0f  lea     edx, [r9+1]; bManualReset
0x1800c4e13  call    cs:__imp_CreateEventW
0x1800c4e19  mov     [rdi], rax
0x1800c4e1c  test    rax, rax
0x1800c4e1f  jnz     short loc_1800C4E31
0x1800c4e21  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800c4e26  mov     esi, eax
0x1800c4e28  lea     rax, aOnecoreuapEndu_33; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800c4e2f  jmp     short loc_1800C4E5E
0x1800c4e31  xor     r8d, r8d; pcbe
0x1800c4e34  lea     rcx, ?CloudSyncThreadpoolCallback@CAudioOrchestratorPolicy@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800c4e3b  mov     rdx, rbx; pv
0x1800c4e3e  call    cs:__imp_CreateThreadpoolTimer
0x1800c4e44  mov     [rbx+0D8h], rax
0x1800c4e4b  test    rax, rax
0x1800c4e4e  jnz     short loc_1800C4EC1
0x1800c4e50  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800c4e55  mov     esi, eax
0x1800c4e57  lea     rax, aOnecoreuapEndu_50; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800c4e5e  mov     r10d, esi
0x1800c4e61  lea     r9, aCaudioorchestr_123; "CAudioOrchestratorPolicy::StartCloudSyn"...
0x1800c4e68  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1800c4e6f  mov     ecx, 2; int
0x1800c4e74  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1800c4e7b  mov     [rsp+38h+var_10], esi
0x1800c4e7f  mov     [rsp+38h+var_18], rax
0x1800c4e84  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c4e89  test    esi, esi
0x1800c4e8b  jns     short loc_1800C4EF1
0x1800c4e8d  mov     rcx, [rdi]; hObject
0x1800c4e90  test    rcx, rcx
0x1800c4e93  jz      short loc_1800C4EA2
0x1800c4e95  call    cs:__imp_CloseHandle
0x1800c4e9b  mov     qword ptr [rdi], 0
0x1800c4ea2  mov     rcx, [rbx+0D8h]; pti
0x1800c4ea9  test    rcx, rcx
0x1800c4eac  jz      short loc_1800C4EF1
0x1800c4eae  call    cs:__imp_CloseThreadpoolTimer
0x1800c4eb4  mov     qword ptr [rbx+0D8h], 0
0x1800c4ebf  jmp     short loc_1800C4EF1
0x1800c4ec1  xor     esi, esi
0x1800c4ec3  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c4ec8  mov     [rbx+0D0h], esi
0x1800c4ece  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800c4ed3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c4ed9  mov     rcx, [rbx+0D8h]; pti
0x1800c4ee0  lea     rdx, [rsp+38h+SystemTimeAsFileTime]; pftDueTime
0x1800c4ee5  xor     r9d, r9d; msWindowLength
0x1800c4ee8  xor     r8d, r8d; msPeriod
0x1800c4eeb  call    cs:__imp_SetThreadpoolTimer
0x1800c4ef1  lea     rcx, [rsp+38h+arg_8]; this
0x1800c4ef6  call    ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
0x1800c4efb  mov     rbx, [rsp+38h+arg_10]
0x1800c4f00  mov     eax, esi
0x1800c4f02  mov     rsi, [rsp+38h+arg_18]
0x1800c4f07  add     rsp, 30h
0x1800c4f0b  pop     rdi
0x1800c4f0c  retn
```
