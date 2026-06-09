# RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal(_WCM_NOTIFICATION_DATA const *)

- ea: `0x1800a7c1c`
- end: `0x1800a7d0d`
- name: `?HandleConnectionCompleteNotificationInternal@RoutePolicyOnDemand@@AEAAXPEBU_WCM_NOTIFICATION_DATA@@@Z`
- size: `241`
- prototype: `void __fastcall(RoutePolicyOnDemand *__hidden this, const struct _WCM_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a7bb8`

## callees

- `0x180027630`
- `0x18003a08c`
- `0x1800a3500`
- `0x1800a359c`
- `0x1800a7c1c`
- `0x1800a870c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7ce4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7cf9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7cf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal(
        RoutePolicyOnDemand *this,
        const struct _WCM_NOTIFICATION_DATA *a2,
        unsigned int a3)
{
  const char *v5; // r9
  _OWORD *v6; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-48h] BYREF
  RoutePolicyOnDemand *v8; // [rsp+28h] [rbp-40h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h]
  _OWORD v10[2]; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    if ( *((_DWORD *)a2 + 6) != 3 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *((_DWORD *)a2 + 6) == 3 )
    {
      if ( *((_DWORD *)a2 + 7) != 28 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v6 = (_OWORD *)*((_QWORD *)a2 + 4);
      v8 = this;
      v9 = *(_OWORD *)((char *)a2 + 8);
      v10[0] = *v6;
      *(_OWORD *)((char *)v10 + 12) = *(_OWORD *)((char *)v6 + 12);
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1___(
            (char *)this + 248,
            &v8);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1___(
            (char *)this + 328,
            &v8);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)this + 29);
        SubmitThreadpoolWork(*((PTP_WORK *)this + 28));
      }
    }
    else
    {
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x3B2, a3, (const char *)0x8000FFFFLL, (int)lpCriticalSection);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x1800a7c1c  mov     [rsp+arg_8], rbx
0x1800a7c21  push    rdi
0x1800a7c22  sub     rsp, 60h
0x1800a7c26  mov     rdi, rdx
0x1800a7c29  mov     rbx, rcx
0x1800a7c2c  cmp     dword ptr [rdx+18h], 3
0x1800a7c30  jz      short loc_1800A7C37
0x1800a7c32  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a7c37  cmp     dword ptr [rdi+18h], 3
0x1800a7c3b  jz      short loc_1800A7C58
0x1800a7c3d  mov     rcx, [rsp+68h]; this
0x1800a7c42  mov     edx, 3B2h; void *
0x1800a7c47  mov     r9d, 8000FFFFh; char *
0x1800a7c4d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a7c52  nop
0x1800a7c53  jmp     loc_1800A7D02
0x1800a7c58  cmp     dword ptr [rdi+1Ch], 1Ch
0x1800a7c5c  jz      short loc_1800A7C63
0x1800a7c5e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a7c63  mov     rax, [rdi+20h]
0x1800a7c67  mov     [rsp+68h+var_40], rbx
0x1800a7c6c  movups  xmm0, xmmword ptr [rdi+8]
0x1800a7c70  movdqu  [rsp+68h+var_38], xmm0
0x1800a7c76  movups  xmm1, xmmword ptr [rax]
0x1800a7c79  movups  xmmword ptr [rsp+68h+var_28], xmm1
0x1800a7c7e  movups  xmm0, xmmword ptr [rax+0Ch]
0x1800a7c82  movups  xmmword ptr [rsp+68h+var_28+0Ch], xmm0
0x1800a7c87  mov     [rsp+68h+lpCriticalSection], 0
0x1800a7c90  lea     rdx, [rbx+68h]
0x1800a7c94  lea     rcx, [rsp+68h+lpCriticalSection]
0x1800a7c99  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a7c9e  nop
0x1800a7c9f  lea     rcx, [rbx+0F8h]
0x1800a7ca6  cmp     byte ptr [rcx+78h], 0
0x1800a7caa  jz      short loc_1800A7CBE
0x1800a7cac  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800a7cb1  test    rcx, rcx
0x1800a7cb4  jz      short loc_1800A7D00
0x1800a7cb6  call    cs:__imp_LeaveCriticalSection
0x1800a7cbc  jmp     short loc_1800A7D00
0x1800a7cbe  lea     rdx, [rsp+68h+var_40]
0x1800a7cc3  cmp     dword ptr [rbx+60h], 1
0x1800a7cc7  jnz     short loc_1800A7CD0
0x1800a7cc9  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__HandleConnectionCompleteNotificationInternal____3____lambda_1___
0x1800a7cce  jmp     short loc_1800A7CDA
0x1800a7cd0  add     rcx, 50h ; 'P'
0x1800a7cd4  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__HandleConnectionCompleteNotificationInternal____3____lambda_1___
0x1800a7cd9  nop
0x1800a7cda  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800a7cdf  test    rcx, rcx
0x1800a7ce2  jz      short loc_1800A7CEA
0x1800a7ce4  call    cs:__imp_LeaveCriticalSection
0x1800a7cea  lock inc qword ptr [rbx+0E8h]
0x1800a7cf2  mov     rcx, [rbx+0E0h]; pwk
0x1800a7cf9  call    cs:__imp_SubmitThreadpoolWork
0x1800a7cff  nop
0x1800a7d00  jmp     short $+2
0x1800a7d02  mov     rbx, [rsp+68h+arg_8]
0x1800a7d07  add     rsp, 60h
0x1800a7d0b  pop     rdi
0x1800a7d0c  retn
```
