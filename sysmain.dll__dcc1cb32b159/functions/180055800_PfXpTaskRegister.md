# PfXpTaskRegister

- ea: `0x180055800`
- end: `0x180055969`
- name: `PfXpTaskRegister`
- size: `361`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003c5b4`
- `0x180058b30`
- `0x18006bf88`
- `0x180096e14`

## callees

- `0x180055800`
- `0x180055970`
- `0x180058d58`
- `0x180064c38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005580e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005580e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055823`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005585d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055823`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005585d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005586a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005586a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800558a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800558a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800558c4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800558c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005595e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005595e`

## pseudocode

```c
__int64 __fastcall PfXpTaskRegister(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION i; // rbx
  LONG LockCount; // eax
  DWORD LastError; // esi
  HANDLE *p_OwningThread; // r14
  bool v6; // zf
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  PTP_WAIT ThreadpoolWait; // rax
  HANDLE LockSemaphore; // rdx
  struct _TP_WAIT *DebugInfo; // rcx

  for ( i = lpCriticalSection; ; lpCriticalSection = i )
  {
    EnterCriticalSection(lpCriticalSection);
    LockCount = i[1].LockCount;
    if ( LockCount == 52943 )
      goto LABEL_3;
    if ( LockCount == 52944 )
    {
      LeaveCriticalSection(i);
      PfXpTaskUnregister(i);
      continue;
    }
    if ( LockCount != 52945 )
      break;
    LeaveCriticalSection(i);
    WaitForSingleObject(i[1].DebugInfo, 0xFFFFFFFF);
  }
  p_OwningThread = &i[1].OwningThread;
  if ( LockCount != 52942 )
  {
    LastError = 5023;
    goto LABEL_20;
  }
  v6 = i[1].DebugInfo == 0;
  *p_OwningThread = 0;
  if ( (!v6 || (EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 1, 1, 0), (i[1].DebugInfo = EventW) != 0))
    && (i[2].DebugInfo
     || (ThreadpoolWait = CreateThreadpoolWait(PfXpTaskCommonCallback, i, 0),
         (i[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)ThreadpoolWait) != 0)) )
  {
    LastError = PfsIdleTaskMgrRegister(
                  *(_DWORD *)&PfSvcGlobals + 4104,
                  i[2].LockCount,
                  (int)i + 56,
                  (int)i + 64,
                  (__int64)&i[1].SpinCount);
    if ( !LastError )
    {
      LockSemaphore = i[1].LockSemaphore;
      DebugInfo = (struct _TP_WAIT *)i[2].DebugInfo;
      i[1].LockCount = 52943;
      SetThreadpoolWait(DebugInfo, LockSemaphore, 0);
LABEL_3:
      LastError = 0;
      goto LABEL_4;
    }
    *p_OwningThread = 0;
LABEL_20:
    if ( *p_OwningThread )
    {
      PfsIdleTaskMgrUnregister(*(_QWORD *)&PfSvcGlobals + 4104LL, *p_OwningThread, i[1].LockSemaphore, i[1].SpinCount);
      *p_OwningThread = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_20;
  }
LABEL_4:
  LeaveCriticalSection(i);
  return LastError;
}

```

## disassembly

```asm
0x180055800  push    rbx
0x180055802  push    rsi
0x180055803  push    r14
0x180055805  push    r15
0x180055807  sub     rsp, 38h
0x18005580b  mov     rbx, rcx
0x18005580e  call    cs:__imp_EnterCriticalSection
0x180055814  mov     eax, [rbx+30h]
0x180055817  cmp     eax, 0CECFh
0x18005581c  jnz     short loc_180055836
0x18005581e  xor     esi, esi
0x180055820  mov     rcx, rbx; lpCriticalSection
0x180055823  call    cs:__imp_LeaveCriticalSection
0x180055829  mov     eax, esi
0x18005582b  add     rsp, 38h
0x18005582f  pop     r15
0x180055831  pop     r14
0x180055833  pop     rsi
0x180055834  pop     rbx
0x180055835  retn
0x180055836  cmp     eax, 0CED0h
0x18005583b  jnz     short loc_180055853
0x18005583d  mov     rcx, rbx; lpCriticalSection
0x180055840  call    cs:__imp_LeaveCriticalSection
0x180055846  mov     rcx, rbx; lpCriticalSection
0x180055849  call    PfXpTaskUnregister
0x18005584e  mov     rcx, rbx
0x180055851  jmp     short loc_18005580E
0x180055853  cmp     eax, 0CED1h
0x180055858  jnz     short loc_180055872
0x18005585a  mov     rcx, rbx; lpCriticalSection
0x18005585d  call    cs:__imp_LeaveCriticalSection
0x180055863  mov     rcx, [rbx+28h]; hHandle
0x180055867  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005586a  call    cs:__imp_WaitForSingleObject
0x180055870  jmp     short loc_18005584E
0x180055872  lea     r14, [rbx+38h]
0x180055876  cmp     eax, 0CECEh
0x18005587b  jz      short loc_180055887
0x18005587d  mov     esi, 139Fh
0x180055882  jmp     loc_180055918
0x180055887  cmp     qword ptr [rbx+28h], 0
0x18005588c  mov     qword ptr [r14], 0
0x180055893  jnz     short loc_1800558B0
0x180055895  xor     r9d, r9d; lpName
0x180055898  xor     ecx, ecx; lpEventAttributes
0x18005589a  lea     edx, [r9+1]; bManualReset
0x18005589e  mov     r8d, edx; bInitialState
0x1800558a1  call    cs:__imp_CreateEventW
0x1800558a7  mov     [rbx+28h], rax
0x1800558ab  test    rax, rax
0x1800558ae  jz      short loc_1800558D3
0x1800558b0  cmp     qword ptr [rbx+50h], 0
0x1800558b5  jnz     short loc_1800558E5
0x1800558b7  xor     r8d, r8d; pcbe
0x1800558ba  lea     rcx, PfXpTaskCommonCallback; pfnwa
0x1800558c1  mov     rdx, rbx; pv
0x1800558c4  call    cs:__imp_CreateThreadpoolWait
0x1800558ca  mov     [rbx+50h], rax
0x1800558ce  test    rax, rax
0x1800558d1  jnz     short loc_1800558E5
0x1800558d3  call    cs:__imp_GetLastError
0x1800558d9  mov     esi, eax
0x1800558db  test    eax, eax
0x1800558dd  jz      loc_180055820
0x1800558e3  jmp     short loc_180055918
0x1800558e5  mov     rcx, cs:PfSvcGlobals
0x1800558ec  lea     rax, [rbx+48h]
0x1800558f0  mov     edx, [rbx+58h]
0x1800558f3  lea     r9, [rbx+40h]
0x1800558f7  add     rcx, 1008h
0x1800558fe  mov     [rsp+58h+var_38], rax
0x180055903  mov     r8, r14
0x180055906  call    PfsIdleTaskMgrRegister
0x18005590b  mov     esi, eax
0x18005590d  test    eax, eax
0x18005590f  jz      short loc_18005594C
0x180055911  mov     qword ptr [r14], 0
0x180055918  cmp     qword ptr [r14], 0
0x18005591c  jz      loc_180055820
0x180055922  mov     rcx, cs:PfSvcGlobals
0x180055929  mov     r9, [rbx+48h]
0x18005592d  add     rcx, 1008h
0x180055934  mov     r8, [rbx+40h]
0x180055938  mov     rdx, [r14]
0x18005593b  call    PfsIdleTaskMgrUnregister
0x180055940  mov     qword ptr [r14], 0
0x180055947  jmp     loc_180055820
0x18005594c  mov     rdx, [rbx+40h]; h
0x180055950  xor     r8d, r8d; pftTimeout
0x180055953  mov     rcx, [rbx+50h]; pwa
0x180055957  mov     dword ptr [rbx+30h], 0CECFh
0x18005595e  call    cs:__imp_SetThreadpoolWait
0x180055964  jmp     loc_18005581E
```
