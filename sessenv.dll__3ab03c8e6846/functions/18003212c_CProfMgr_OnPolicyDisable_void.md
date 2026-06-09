# CProfMgr::OnPolicyDisable(void)

- ea: `0x18003212c`
- end: `0x1800321f8`
- name: `?OnPolicyDisable@CProfMgr@@AEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CProfMgr *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001200c`
- `0x1800162cc`

## callees

- `0x180003f30`
- `0x180016c6c`
- `0x180030e64`
- `0x18003212c`
- `0x1800326a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003215c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003215c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180032152`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180032152`

## string_xrefs

- `0x18003217f`: `DeleteTimerQueueTimer failed: 0x%x in %s`
- `0x180032192`: `DeleteTimerQueueTimer`

## pseudocode

```c
__int64 __fastcall CProfMgr::OnPolicyDisable(CProfMgr *this)
{
  void *v1; // rdx
  unsigned int v2; // ebx
  signed int LastError; // eax

  v1 = (void *)*((_QWORD *)this + 205);
  v2 = 0;
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(*((HANDLE *)this + 204), v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "DeleteTimerQueueTimer failed: 0x%x in %s", v2, "CProfMgr::OnPolicyDisable");
        goto LABEL_9;
      }
    }
    _DbgPrintMessage(1, "DeleteTimerQueueTimer");
    *((_QWORD *)this + 205) = 0;
  }
  CProfMgr::FreeUserProfileList(this);
  if ( !v2 )
  {
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      &EVENT_TS_RUP_POLICY_STATUS_DISABLED,
      0,
      0);
    return v2;
  }
LABEL_9:
  CrimsonHelper::RaiseEvent<long>(&CrimsonHelper::s_instance, EVENT_TS_RUP_POLICY_DISABLED_ERROR, v2);
  return v2;
}

```

## disassembly

```asm
0x18003212c  mov     [rsp+arg_0], rbx
0x180032131  push    rdi
0x180032132  sub     rsp, 20h
0x180032136  mov     rdx, [rcx+668h]; Timer
0x18003213d  xor     ebx, ebx
0x18003213f  mov     rdi, rcx
0x180032142  test    rdx, rdx
0x180032145  jz      short loc_1800321AE
0x180032147  mov     rcx, [rcx+660h]; TimerQueue
0x18003214e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180032152  call    cs:__imp_DeleteTimerQueueTimer
0x180032158  test    eax, eax
0x18003215a  jnz     short loc_180032192
0x18003215c  call    cs:__imp_GetLastError
0x180032162  mov     ebx, eax
0x180032164  test    eax, eax
0x180032166  jle     short loc_180032171
0x180032168  movzx   ebx, ax
0x18003216b  or      ebx, 80070000h
0x180032171  test    ebx, ebx
0x180032173  jns     short loc_180032192
0x180032175  lea     r9, aCprofmgrOnpoli_1; "CProfMgr::OnPolicyDisable"
0x18003217c  mov     r8d, ebx
0x18003217f  lea     rdx, aDeletetimerque_2; "DeleteTimerQueueTimer failed: 0x%x in %"...
0x180032186  mov     ecx, 8; int
0x18003218b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032190  jmp     short loc_1800321BA
0x180032192  lea     rdx, aDeletetimerque_3; "DeleteTimerQueueTimer"
0x180032199  mov     ecx, 1; int
0x18003219e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800321a3  mov     qword ptr [rdi+668h], 0
0x1800321ae  mov     rcx, rdi; this
0x1800321b1  call    ?FreeUserProfileList@CProfMgr@@AEAAXXZ; CProfMgr::FreeUserProfileList(void)
0x1800321b6  test    ebx, ebx
0x1800321b8  jz      short loc_1800321D2
0x1800321ba  mov     r8d, ebx
0x1800321bd  lea     rdx, EVENT_TS_RUP_POLICY_DISABLED_ERROR
0x1800321c4  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x1800321cb  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x1800321d0  jmp     short loc_1800321EB
0x1800321d2  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x1800321d5  lea     rdx, EVENT_TS_RUP_POLICY_STATUS_DISABLED; struct _EVENT_DESCRIPTOR *
0x1800321dc  xor     r8d, r8d; unsigned int
0x1800321df  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x1800321e6  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x1800321eb  mov     eax, ebx
0x1800321ed  mov     rbx, [rsp+28h+arg_0]
0x1800321f2  add     rsp, 20h
0x1800321f6  pop     rdi
0x1800321f7  retn
```
