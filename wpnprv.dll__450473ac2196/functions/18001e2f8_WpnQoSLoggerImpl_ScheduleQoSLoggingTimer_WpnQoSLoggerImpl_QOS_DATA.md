# WpnQoSLoggerImpl::ScheduleQoSLoggingTimer(WpnQoSLoggerImpl::_QOS_DATA *)

- ea: `0x18001e2f8`
- end: `0x18001e430`
- name: `?ScheduleQoSLoggingTimer@WpnQoSLoggerImpl@@CAJPEAU_QOS_DATA@1@@Z`
- size: `312`
- prototype: `__int64 __fastcall(struct WpnQoSLoggerImpl::_QOS_DATA *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001dc50`
- `0x18001de60`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001e2f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e41d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e41d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e33f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e33f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e374`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e40e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e40e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001e35f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001e35f`

## pseudocode

```c
__int64 __fastcall WpnQoSLoggerImpl::ScheduleQoSLoggingTimer(struct WpnQoSLoggerImpl::_QOS_DATA *a1)
{
  unsigned int v2; // ebx
  struct _TP_TIMER *v3; // rcx
  signed int LastError; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  v2 = 1;
  pftDueTime = 0;
  if ( WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds && !WpnQoSLoggerImpl::s_Timer )
  {
    EnterCriticalSection(&WpnQoSLoggerImpl::s_TimerLock);
    if ( !WpnQoSLoggerImpl::s_Timer )
    {
      WpnQoSLoggerImpl::s_Timer = CreateThreadpoolTimer(WpnQoSLoggerImpl::TimerProcessing, 0, 0);
      v3 = WpnQoSLoggerImpl::s_Timer;
      if ( !WpnQoSLoggerImpl::s_Timer )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( (v2 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
            (const char *)v2,
            v6);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, v2);
          goto LABEL_15;
        }
        v3 = WpnQoSLoggerImpl::s_Timer;
      }
      WpnQoSLoggerImpl::s_TimerData = a1;
      pftDueTime = (struct _FILETIME)(-10000000LL * WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds);
      SetThreadpoolTimer(v3, &pftDueTime, 0, 0x3E8u);
      v2 = 0;
    }
LABEL_15:
    LeaveCriticalSection(&WpnQoSLoggerImpl::s_TimerLock);
  }
  return v2;
}

```

## disassembly

```asm
0x18001e2f8  mov     [rsp+arg_8], rbx
0x18001e2fd  push    rdi; int
0x18001e2fe  sub     rsp, 20h
0x18001e302  mov     rdi, rcx
0x18001e305  test    rcx, rcx
0x18001e308  jnz     short loc_18001E30F
0x18001e30a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e30f  cmp     cs:?s_QoSLoggerDelaySeconds@WpnQoSLoggerImpl@@0KA, 0; ulong WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds
0x18001e316  mov     ebx, 1
0x18001e31b  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18001e324  jz      loc_18001E423
0x18001e32a  cmp     cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA, 0; _TP_TIMER * WpnQoSLoggerImpl::s_Timer
0x18001e332  jnz     loc_18001E423
0x18001e338  lea     rcx, ?s_TimerLock@WpnQoSLoggerImpl@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e33f  call    cs:__imp_EnterCriticalSection
0x18001e345  cmp     cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA, 0; _TP_TIMER * WpnQoSLoggerImpl::s_Timer
0x18001e34d  jnz     loc_18001E416
0x18001e353  xor     r8d, r8d; pcbe
0x18001e356  lea     rcx, ?TimerProcessing@WpnQoSLoggerImpl@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001e35d  xor     edx, edx; pv
0x18001e35f  call    cs:__imp_CreateThreadpoolTimer
0x18001e365  mov     cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA, rax; _TP_TIMER * WpnQoSLoggerImpl::s_Timer
0x18001e36c  mov     rcx, rax
0x18001e36f  test    rax, rax
0x18001e372  jnz     short loc_18001E3E0
0x18001e374  call    cs:__imp_GetLastError
0x18001e37a  mov     ebx, eax
0x18001e37c  test    eax, eax
0x18001e37e  jle     short loc_18001E389
0x18001e380  movzx   ebx, ax
0x18001e383  or      ebx, 80070000h
0x18001e389  test    ebx, ebx
0x18001e38b  jns     short loc_18001E3D9
0x18001e38d  mov     rcx, [rsp+28h]; this
0x18001e392  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e399  mov     r9d, ebx; char *
0x18001e39c  mov     edx, 7Ch ; '|'; void *
0x18001e3a1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3ad  lea     rax, WPP_GLOBAL_Control
0x18001e3b4  cmp     rcx, rax
0x18001e3b7  jz      short loc_18001E416
0x18001e3b9  test    byte ptr [rcx+1Ch], 80h
0x18001e3bd  jz      short loc_18001E416
0x18001e3bf  mov     rcx, [rcx+10h]
0x18001e3c3  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001e3ca  mov     edx, 0Ah
0x18001e3cf  mov     r9d, ebx
0x18001e3d2  call    WPP_SF_d
0x18001e3d7  jmp     short loc_18001E416
0x18001e3d9  mov     rcx, cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA; pti
0x18001e3e0  mov     eax, cs:?s_QoSLoggerDelaySeconds@WpnQoSLoggerImpl@@0KA; ulong WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds
0x18001e3e6  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001e3eb  imul    rax, 0FFFFFFFFFF676980h
0x18001e3f2  mov     r9d, 3E8h; msWindowLength
0x18001e3f8  mov     cs:?s_TimerData@WpnQoSLoggerImpl@@0PEAU_QOS_DATA@1@EA, rdi; WpnQoSLoggerImpl::_QOS_DATA * WpnQoSLoggerImpl::s_TimerData
0x18001e3ff  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001e403  xor     r8d, r8d; msPeriod
0x18001e406  shr     rax, 20h
0x18001e40a  mov     [rsp+28h+pftDueTime.dwHighDateTime], eax
0x18001e40e  call    cs:__imp_SetThreadpoolTimer
0x18001e414  xor     ebx, ebx
0x18001e416  lea     rcx, ?s_TimerLock@WpnQoSLoggerImpl@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e41d  call    cs:__imp_LeaveCriticalSection
0x18001e423  mov     eax, ebx
0x18001e425  mov     rbx, [rsp+28h+arg_8]
0x18001e42a  add     rsp, 20h
0x18001e42e  pop     rdi
0x18001e42f  retn
```
