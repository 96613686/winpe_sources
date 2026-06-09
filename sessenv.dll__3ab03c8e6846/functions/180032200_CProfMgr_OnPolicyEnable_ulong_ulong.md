# CProfMgr::OnPolicyEnable(ulong,ulong)

- ea: `0x180032200`
- end: `0x180032364`
- name: `?OnPolicyEnable@CProfMgr@@AEAAJKK@Z`
- size: `356`
- prototype: `__int64 __fastcall(PVOID Parameter, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001200c`

## callees

- `0x180003f30`
- `0x180030e64`
- `0x180032200`
- `0x1800326a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322f1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180032221`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180032221`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800322ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800322ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800322e7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800322e7`

## string_xrefs

- `0x180032249`: `CreateTimerQueue failed: 0x%x in %s`
- `0x1800322cc`: `CreateTimerQueueTimer failed: 0x%x in %s`
- `0x180032307`: `DeleteTimerQueueTimer failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProfMgr::OnPolicyEnable(PVOID Parameter, int a2)
{
  unsigned int v2; // ebx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  int v7; // eax
  void *v8; // rdx
  DWORD Period; // eax
  signed int v10; // eax
  bool v11; // zf
  signed int v12; // eax

  v2 = 0;
  if ( !*((_QWORD *)Parameter + 204) )
  {
    TimerQueue = CreateTimerQueue();
    *((_QWORD *)Parameter + 204) = TimerQueue;
    if ( !TimerQueue )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "CreateTimerQueue failed: 0x%x in %s", v2, "CProfMgr::OnPolicyEnable");
        goto LABEL_24;
      }
    }
  }
  v7 = *((_DWORD *)Parameter + 406);
  v8 = (void *)*((_QWORD *)Parameter + 205);
  if ( v8 )
  {
    if ( a2 == v7 )
      goto LABEL_22;
    if ( !DeleteTimerQueueTimer(*((HANDLE *)Parameter + 204), v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v12 = GetLastError();
      v2 = v12;
      if ( v12 > 0 )
        v2 = (unsigned __int16)v12 | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "DeleteTimerQueueTimer failed: 0x%x in %s", v2, "CProfMgr::OnPolicyEnable");
        goto LABEL_24;
      }
    }
    Period = 60000 * *((_DWORD *)Parameter + 406);
  }
  else
  {
    Period = 60000 * v7;
  }
  if ( CreateTimerQueueTimer(
         (PHANDLE)Parameter + 205,
         *((HANDLE *)Parameter + 204),
         CProfMgr::staticMonitorProfileDirectorySize,
         Parameter,
         0,
         Period,
         0x20u) )
  {
LABEL_22:
    v11 = v2 == 0;
    goto LABEL_23;
  }
  v10 = GetLastError();
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
  v11 = v2 == 0;
  if ( (v2 & 0x80000000) != 0 )
  {
    _DbgPrintMessage(8, "CreateTimerQueueTimer failed: 0x%x in %s", v2, "CProfMgr::OnPolicyEnable");
    goto LABEL_24;
  }
LABEL_23:
  if ( v11 )
  {
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      &EVENT_TS_RUP_POLICY_STATUS_ENABLED,
      0,
      0);
    return v2;
  }
LABEL_24:
  CrimsonHelper::RaiseEvent<long>(&CrimsonHelper::s_instance, EVENT_TS_RUP_POLICY_ENABLED_ERROR, v2);
  return v2;
}

```

## disassembly

```asm
0x180032200  push    rbx
0x180032202  push    rbp
0x180032203  push    rsi
0x180032204  push    rdi
0x180032205  push    r15
0x180032207  sub     rsp, 40h
0x18003220b  xor     ebx, ebx
0x18003220d  mov     ebp, edx
0x18003220f  mov     rdi, rcx
0x180032212  mov     r15d, 80070000h
0x180032218  cmp     [rcx+660h], rbx
0x18003221f  jnz     short loc_180032269
0x180032221  call    cs:__imp_CreateTimerQueue
0x180032227  mov     [rdi+660h], rax
0x18003222e  test    rax, rax
0x180032231  jnz     short loc_180032269
0x180032233  call    cs:__imp_GetLastError
0x180032239  mov     ebx, eax
0x18003223b  test    eax, eax
0x18003223d  jle     short loc_180032245
0x18003223f  movzx   ebx, ax
0x180032242  or      ebx, r15d
0x180032245  test    ebx, ebx
0x180032247  jns     short loc_180032269
0x180032249  lea     rdx, aCreatetimerque_2; "CreateTimerQueue failed: 0x%x in %s"
0x180032250  lea     r9, aCprofmgrOnpoli; "CProfMgr::OnPolicyEnable"
0x180032257  mov     r8d, ebx
0x18003225a  mov     ecx, 8; int
0x18003225f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032264  jmp     loc_180032326
0x180032269  mov     eax, [rdi+658h]
0x18003226f  lea     rsi, [rdi+668h]
0x180032276  mov     rdx, [rsi]; Timer
0x180032279  test    rdx, rdx
0x18003227c  jnz     short loc_1800322D8
0x18003227e  imul    eax, 0EA60h
0x180032284  mov     rdx, [rdi+660h]; TimerQueue
0x18003228b  lea     r8, ?staticMonitorProfileDirectorySize@CProfMgr@@CAXPEAXE@Z; Callback
0x180032292  mov     [rsp+68h+Flags], 20h ; ' '; Flags
0x18003229a  mov     r9, rdi; Parameter
0x18003229d  mov     [rsp+68h+Period], eax; Period
0x1800322a1  mov     rcx, rsi; phNewTimer
0x1800322a4  mov     [rsp+68h+DueTime], 0; DueTime
0x1800322ac  call    cs:__imp_CreateTimerQueueTimer
0x1800322b2  test    eax, eax
0x1800322b4  jnz     short loc_180032322
0x1800322b6  call    cs:__imp_GetLastError
0x1800322bc  mov     ebx, eax
0x1800322be  test    eax, eax
0x1800322c0  jle     short loc_1800322C8
0x1800322c2  movzx   ebx, ax
0x1800322c5  or      ebx, r15d
0x1800322c8  test    ebx, ebx
0x1800322ca  jns     short loc_180032324
0x1800322cc  lea     rdx, aCreatetimerque; "CreateTimerQueueTimer failed: 0x%x in %"...
0x1800322d3  jmp     loc_180032250
0x1800322d8  cmp     ebp, eax
0x1800322da  jz      short loc_180032322
0x1800322dc  mov     rcx, [rdi+660h]; TimerQueue
0x1800322e3  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800322e7  call    cs:__imp_DeleteTimerQueueTimer
0x1800322ed  test    eax, eax
0x1800322ef  jnz     short loc_180032313
0x1800322f1  call    cs:__imp_GetLastError
0x1800322f7  mov     ebx, eax
0x1800322f9  test    eax, eax
0x1800322fb  jle     short loc_180032303
0x1800322fd  movzx   ebx, ax
0x180032300  or      ebx, r15d
0x180032303  test    ebx, ebx
0x180032305  jns     short loc_180032313
0x180032307  lea     rdx, aDeletetimerque_2; "DeleteTimerQueueTimer failed: 0x%x in %"...
0x18003230e  jmp     loc_180032250
0x180032313  imul    eax, [rdi+658h], 0EA60h
0x18003231d  jmp     loc_180032284
0x180032322  test    ebx, ebx
0x180032324  jz      short loc_18003233E
0x180032326  mov     r8d, ebx
0x180032329  lea     rdx, EVENT_TS_RUP_POLICY_ENABLED_ERROR
0x180032330  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180032337  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x18003233c  jmp     short loc_180032357
0x18003233e  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180032341  lea     rdx, EVENT_TS_RUP_POLICY_STATUS_ENABLED; struct _EVENT_DESCRIPTOR *
0x180032348  xor     r8d, r8d; unsigned int
0x18003234b  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180032352  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180032357  mov     eax, ebx
0x180032359  add     rsp, 40h
0x18003235d  pop     r15
0x18003235f  pop     rdi
0x180032360  pop     rsi
0x180032361  pop     rbp
0x180032362  pop     rbx
0x180032363  retn
```
