# CWerService::StaticContinueWorkItem(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180018700`
- end: `0x1800187e0`
- name: `?StaticContinueWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `224`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180018700`
- `0x18001d7c0`
- `0x18001d92c`
- `0x18001df68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018722`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018722`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800187ce`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800187ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWerService::StaticContinueWorkItem(
        PTP_CALLBACK_INSTANCE Instance,
        struct _RTL_CRITICAL_SECTION *Context)
{
  int started; // eax
  PCRITICAL_SECTION pcs; // [rsp+20h] [rbp-18h] BYREF
  char v6; // [rsp+28h] [rbp-10h]

  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  pcs = Context;
  EnterCriticalSection(Context);
  v6 = 1;
  CWerService::_SetServiceStatus((CWerService *)Context, 5u);
  started = CWerService::_StartWork((CWerService *)Context, (__int64)&pcs);
  if ( started >= 0 )
  {
    CWerService::_SetServiceStatus((CWerService *)Context, 4u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)started);
    CWerService::_SignalStop((HANDLE *)&Context->DebugInfo, (__int64)&pcs);
  }
  LeaveCriticalSectionWhenCallbackReturns(Instance, pcs);
}

```

## disassembly

```asm
0x180018700  mov     [rsp+arg_0], rbx
0x180018705  push    rdi
0x180018706  sub     rsp, 30h
0x18001870a  mov     rbx, rdx
0x18001870d  mov     rdi, rcx
0x180018710  test    rdx, rdx
0x180018713  jnz     short loc_18001871A
0x180018715  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001871a  mov     [rsp+38h+pcs], rbx
0x18001871f  mov     rcx, rbx; lpCriticalSection
0x180018722  call    cs:__imp_EnterCriticalSection
0x180018728  mov     [rsp+38h+var_10], 1
0x18001872d  mov     edx, 5; unsigned int
0x180018732  mov     rcx, rbx; this
0x180018735  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001873a  lea     rdx, [rsp+38h+pcs]
0x18001873f  mov     rcx, rbx; this
0x180018742  call    ?_StartWork@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_StartWork(utl::unique_lock<utl::recursive_mutex> &)
0x180018747  test    eax, eax
0x180018749  jns     short loc_18001878B
0x18001874b  lea     rdx, WPP_GLOBAL_Control
0x180018752  mov     rcx, cs:WPP_GLOBAL_Control
0x180018759  cmp     rcx, rdx
0x18001875c  jz      short loc_18001877C
0x18001875e  test    byte ptr [rcx+1Ch], 1
0x180018762  jz      short loc_18001877C
0x180018764  mov     edx, 36h ; '6'
0x180018769  mov     r9d, eax
0x18001876c  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180018773  mov     rcx, [rcx+10h]
0x180018777  call    WPP_SF_d
0x18001877c  lea     rdx, [rsp+38h+pcs]
0x180018781  mov     rcx, rbx
0x180018784  call    ?_SignalStop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_SignalStop(utl::unique_lock<utl::recursive_mutex> &)
0x180018789  jmp     short loc_1800187C6
0x18001878b  mov     edx, 4; unsigned int
0x180018790  mov     rcx, rbx; this
0x180018793  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x180018798  lea     rdx, WPP_GLOBAL_Control
0x18001879f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187a6  cmp     rcx, rdx
0x1800187a9  jz      short loc_1800187C6
0x1800187ab  test    byte ptr [rcx+1Ch], 4
0x1800187af  jz      short loc_1800187C6
0x1800187b1  mov     edx, 37h ; '7'
0x1800187b6  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800187bd  mov     rcx, [rcx+10h]
0x1800187c1  call    WPP_SF_
0x1800187c6  mov     rdx, [rsp+38h+pcs]; pcs
0x1800187cb  mov     rcx, rdi; pci
0x1800187ce  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x1800187d4  nop
0x1800187d5  mov     rbx, [rsp+38h+arg_0]
0x1800187da  add     rsp, 30h
0x1800187de  pop     rdi
0x1800187df  retn
```
