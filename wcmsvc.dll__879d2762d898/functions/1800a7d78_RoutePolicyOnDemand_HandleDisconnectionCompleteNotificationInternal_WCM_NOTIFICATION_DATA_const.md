# RoutePolicyOnDemand::HandleDisconnectionCompleteNotificationInternal(_WCM_NOTIFICATION_DATA const *)

- ea: `0x1800a7d78`
- end: `0x1800a7e56`
- name: `?HandleDisconnectionCompleteNotificationInternal@RoutePolicyOnDemand@@AEAAXPEBU_WCM_NOTIFICATION_DATA@@@Z`
- size: `222`
- prototype: `void __fastcall(RoutePolicyOnDemand *__hidden this, const struct _WCM_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a7d14`

## callees

- `0x180027630`
- `0x18003a08c`
- `0x1800a3640`
- `0x1800a36f4`
- `0x1800a7d78`
- `0x1800a870c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7dff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7e2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7dff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7e2d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7e42`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7e42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RoutePolicyOnDemand::HandleDisconnectionCompleteNotificationInternal(
        RoutePolicyOnDemand *this,
        const struct _WCM_NOTIFICATION_DATA *a2,
        unsigned int a3)
{
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v7[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    if ( *((_DWORD *)a2 + 6) != 3 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *((_DWORD *)a2 + 6) == 3 )
    {
      if ( *((_DWORD *)a2 + 7) != 8 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v7[0] = this;
      v7[1] = **((_QWORD **)a2 + 4);
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 104);
      if ( *((_BYTE *)this + 368) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)this + 24) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::HandleDisconnectionCompleteNotificationInternal_::_3_::_lambda_1___(
            (char *)this + 248,
            v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::HandleDisconnectionCompleteNotificationInternal_::_3_::_lambda_1___(
            (char *)this + 328,
            v7);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)this + 29);
        SubmitThreadpoolWork(*((PTP_WORK *)this + 28));
      }
    }
    else
    {
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x483, a3, (const char *)0x8000FFFFLL, (int)lpCriticalSection);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4AC,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x1800a7d78  mov     [rsp+arg_8], rbx
0x1800a7d7d  push    rdi
0x1800a7d7e  sub     rsp, 40h
0x1800a7d82  mov     rdi, rdx
0x1800a7d85  mov     rbx, rcx
0x1800a7d88  cmp     dword ptr [rdx+18h], 3
0x1800a7d8c  jz      short loc_1800A7D93
0x1800a7d8e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a7d93  cmp     dword ptr [rdi+18h], 3
0x1800a7d97  jz      short loc_1800A7DB4
0x1800a7d99  mov     rcx, [rsp+48h]; this
0x1800a7d9e  mov     edx, 483h; void *
0x1800a7da3  mov     r9d, 8000FFFFh; char *
0x1800a7da9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a7dae  nop
0x1800a7daf  jmp     loc_1800A7E4B
0x1800a7db4  cmp     dword ptr [rdi+1Ch], 8
0x1800a7db8  jz      short loc_1800A7DBF
0x1800a7dba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a7dbf  mov     [rsp+48h+var_20], rbx
0x1800a7dc4  mov     rax, [rdi+20h]
0x1800a7dc8  mov     rcx, [rax]
0x1800a7dcb  mov     [rsp+48h+var_18], rcx
0x1800a7dd0  mov     [rsp+48h+lpCriticalSection], 0
0x1800a7dd9  lea     rdx, [rbx+68h]
0x1800a7ddd  lea     rcx, [rsp+48h+lpCriticalSection]
0x1800a7de2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a7de7  nop
0x1800a7de8  lea     rcx, [rbx+0F8h]
0x1800a7def  cmp     byte ptr [rcx+78h], 0
0x1800a7df3  jz      short loc_1800A7E07
0x1800a7df5  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800a7dfa  test    rcx, rcx
0x1800a7dfd  jz      short loc_1800A7E49
0x1800a7dff  call    cs:__imp_LeaveCriticalSection
0x1800a7e05  jmp     short loc_1800A7E49
0x1800a7e07  lea     rdx, [rsp+48h+var_20]
0x1800a7e0c  cmp     dword ptr [rbx+60h], 1
0x1800a7e10  jnz     short loc_1800A7E19
0x1800a7e12  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__HandleDisconnectionCompleteNotificationInternal____3____lambda_1___
0x1800a7e17  jmp     short loc_1800A7E23
0x1800a7e19  add     rcx, 50h ; 'P'
0x1800a7e1d  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__HandleDisconnectionCompleteNotificationInternal____3____lambda_1___
0x1800a7e22  nop
0x1800a7e23  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800a7e28  test    rcx, rcx
0x1800a7e2b  jz      short loc_1800A7E33
0x1800a7e2d  call    cs:__imp_LeaveCriticalSection
0x1800a7e33  lock inc qword ptr [rbx+0E8h]
0x1800a7e3b  mov     rcx, [rbx+0E0h]; pwk
0x1800a7e42  call    cs:__imp_SubmitThreadpoolWork
0x1800a7e48  nop
0x1800a7e49  jmp     short $+2
0x1800a7e4b  mov     rbx, [rsp+48h+arg_8]
0x1800a7e50  add     rsp, 40h
0x1800a7e54  pop     rdi
0x1800a7e55  retn
```
