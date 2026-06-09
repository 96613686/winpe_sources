# RoutePolicyOnDemand::ReadyTimeoutCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180070c30`
- end: `0x180070d3f`
- name: `?ReadyTimeoutCallback@RoutePolicyOnDemand@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `271`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008344`
- `0x180010080`
- `0x180027630`
- `0x180070c30`
- `0x18007103c`
- `0x180084f50`
- `0x1800a3cc0`
- `0x1800a3d74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070cfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070cfe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070d13`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070d13`

## string_xrefs

- `0x180070c70`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RoutePolicyOnDemand::ReadyTimeoutCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  __int64 v3; // r9
  std::_Ref_count_base *v4; // rbx
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v8[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v8 = 0;
  std::weak_ptr<RoutePolicyOnDemand>::lock(Instance, v8, Timer, Context);
  v4 = v8[0];
  if ( v8[0] )
  {
    v7[0] = v8[0];
    v7[1] = v3;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)v8[0] + 104);
    try
    {
      if ( *((_BYTE *)v4 + 368) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)v4 + 24) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::ReadyTimeoutCallback_::_3_::_lambda_1___(
            (char *)v4 + 248,
            v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::ReadyTimeoutCallback_::_3_::_lambda_1___(
            (char *)v4 + 328,
            v7);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v4 + 29);
        SubmitThreadpoolWork(*((PTP_WORK *)v4 + 28));
      }
      if ( v8[1] )
        std::_Ref_count_base::_Decref(v8[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x65B,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x621,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      (const char *)0x139F,
      (unsigned int)lpCriticalSection);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
  }
}

```

## disassembly

```asm
0x180070c30  push    rbx
0x180070c32  sub     rsp, 50h
0x180070c36  mov     rax, cs:__security_cookie
0x180070c3d  xor     rax, rsp
0x180070c40  mov     [rsp+58h+var_10], rax
0x180070c45  mov     r9, rdx
0x180070c48  xorps   xmm0, xmm0
0x180070c4b  movups  xmmword ptr [rsp+58h+var_20], xmm0
0x180070c50  lea     rdx, [rsp+58h+var_20]
0x180070c55  call    ?lock@?$weak_ptr@VRoutePolicyOnDemand@@@std@@QEBA?AV?$shared_ptr@VRoutePolicyOnDemand@@@2@XZ; std::weak_ptr<RoutePolicyOnDemand>::lock(void)
0x180070c5a  nop
0x180070c5b  mov     rbx, [rsp+58h+var_20]
0x180070c60  test    rbx, rbx
0x180070c63  jnz     short loc_180070C97
0x180070c65  mov     rcx, [rsp+58h]; this
0x180070c6a  mov     r9d, 139Fh; char *
0x180070c70  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180070c77  mov     edx, 621h; void *
0x180070c7c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070c81  nop
0x180070c82  mov     rcx, [rsp+58h+var_20+8]; this
0x180070c87  test    rcx, rcx
0x180070c8a  jz      short loc_180070C92
0x180070c8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070c91  nop
0x180070c92  jmp     loc_180070D2C
0x180070c97  mov     [rsp+58h+var_30], rbx
0x180070c9c  mov     [rsp+58h+var_28], r9
0x180070ca1  mov     [rsp+58h+lpCriticalSection], 0
0x180070caa  lea     rdx, [rbx+68h]
0x180070cae  lea     rcx, [rsp+58h+lpCriticalSection]
0x180070cb3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070cb8  nop
0x180070cb9  lea     rcx, [rbx+0F8h]
0x180070cc0  cmp     byte ptr [rcx+78h], 0
0x180070cc4  jz      short loc_180070CD8
0x180070cc6  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070ccb  test    rcx, rcx
0x180070cce  jz      short loc_180070D1A
0x180070cd0  call    cs:__imp_LeaveCriticalSection
0x180070cd6  jmp     short loc_180070D1A
0x180070cd8  lea     rdx, [rsp+58h+var_30]
0x180070cdd  cmp     dword ptr [rbx+60h], 1
0x180070ce1  jnz     short loc_180070CEA
0x180070ce3  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__ReadyTimeoutCallback____3____lambda_1___
0x180070ce8  jmp     short loc_180070CF4
0x180070cea  add     rcx, 50h ; 'P'
0x180070cee  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__ReadyTimeoutCallback____3____lambda_1___
0x180070cf3  nop
0x180070cf4  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070cf9  test    rcx, rcx
0x180070cfc  jz      short loc_180070D04
0x180070cfe  call    cs:__imp_LeaveCriticalSection
0x180070d04  lock inc qword ptr [rbx+0E8h]
0x180070d0c  mov     rcx, [rbx+0E0h]; pwk
0x180070d13  call    cs:__imp_SubmitThreadpoolWork
0x180070d19  nop
0x180070d1a  mov     rcx, [rsp+58h+var_20+8]; this
0x180070d1f  test    rcx, rcx
0x180070d22  jz      short loc_180070D2A
0x180070d24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070d29  nop
0x180070d2a  jmp     short $+2
0x180070d2c  mov     rcx, [rsp+58h+var_10]
0x180070d31  xor     rcx, rsp; StackCookie
0x180070d34  call    __security_check_cookie
0x180070d39  add     rsp, 50h
0x180070d3d  pop     rbx
0x180070d3e  retn
```
