# RoutePolicyOnDemand::DelayedDisconnectCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180070d50`
- end: `0x180070e5f`
- name: `?DelayedDisconnectCallback@RoutePolicyOnDemand@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `271`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008344`
- `0x180010080`
- `0x180027630`
- `0x180070d50`
- `0x18007103c`
- `0x180084f50`
- `0x1800a3394`
- `0x1800a3448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070df0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070e1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070df0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070e1e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070e33`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070e33`

## string_xrefs

- `0x180070d90`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RoutePolicyOnDemand::DelayedDisconnectCallback(
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::DelayedDisconnectCallback_::_3_::_lambda_1___(
            (char *)v4 + 248,
            v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::DelayedDisconnectCallback_::_3_::_lambda_1___(
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
        (void *)0x6A5,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x663,
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
0x180070d50  push    rbx
0x180070d52  sub     rsp, 50h
0x180070d56  mov     rax, cs:__security_cookie
0x180070d5d  xor     rax, rsp
0x180070d60  mov     [rsp+58h+var_10], rax
0x180070d65  mov     r9, rdx
0x180070d68  xorps   xmm0, xmm0
0x180070d6b  movups  xmmword ptr [rsp+58h+var_20], xmm0
0x180070d70  lea     rdx, [rsp+58h+var_20]
0x180070d75  call    ?lock@?$weak_ptr@VRoutePolicyOnDemand@@@std@@QEBA?AV?$shared_ptr@VRoutePolicyOnDemand@@@2@XZ; std::weak_ptr<RoutePolicyOnDemand>::lock(void)
0x180070d7a  nop
0x180070d7b  mov     rbx, [rsp+58h+var_20]
0x180070d80  test    rbx, rbx
0x180070d83  jnz     short loc_180070DB7
0x180070d85  mov     rcx, [rsp+58h]; this
0x180070d8a  mov     r9d, 139Fh; char *
0x180070d90  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180070d97  mov     edx, 663h; void *
0x180070d9c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070da1  nop
0x180070da2  mov     rcx, [rsp+58h+var_20+8]; this
0x180070da7  test    rcx, rcx
0x180070daa  jz      short loc_180070DB2
0x180070dac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070db1  nop
0x180070db2  jmp     loc_180070E4C
0x180070db7  mov     [rsp+58h+var_30], rbx
0x180070dbc  mov     [rsp+58h+var_28], r9
0x180070dc1  mov     [rsp+58h+lpCriticalSection], 0
0x180070dca  lea     rdx, [rbx+68h]
0x180070dce  lea     rcx, [rsp+58h+lpCriticalSection]
0x180070dd3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070dd8  nop
0x180070dd9  lea     rcx, [rbx+0F8h]
0x180070de0  cmp     byte ptr [rcx+78h], 0
0x180070de4  jz      short loc_180070DF8
0x180070de6  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070deb  test    rcx, rcx
0x180070dee  jz      short loc_180070E3A
0x180070df0  call    cs:__imp_LeaveCriticalSection
0x180070df6  jmp     short loc_180070E3A
0x180070df8  lea     rdx, [rsp+58h+var_30]
0x180070dfd  cmp     dword ptr [rbx+60h], 1
0x180070e01  jnz     short loc_180070E0A
0x180070e03  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__DelayedDisconnectCallback____3____lambda_1___
0x180070e08  jmp     short loc_180070E14
0x180070e0a  add     rcx, 50h ; 'P'
0x180070e0e  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__DelayedDisconnectCallback____3____lambda_1___
0x180070e13  nop
0x180070e14  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070e19  test    rcx, rcx
0x180070e1c  jz      short loc_180070E24
0x180070e1e  call    cs:__imp_LeaveCriticalSection
0x180070e24  lock inc qword ptr [rbx+0E8h]
0x180070e2c  mov     rcx, [rbx+0E0h]; pwk
0x180070e33  call    cs:__imp_SubmitThreadpoolWork
0x180070e39  nop
0x180070e3a  mov     rcx, [rsp+58h+var_20+8]; this
0x180070e3f  test    rcx, rcx
0x180070e42  jz      short loc_180070E4A
0x180070e44  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070e49  nop
0x180070e4a  jmp     short $+2
0x180070e4c  mov     rcx, [rsp+58h+var_10]
0x180070e51  xor     rcx, rsp; StackCookie
0x180070e54  call    __security_check_cookie
0x180070e59  add     rsp, 50h
0x180070e5d  pop     rbx
0x180070e5e  retn
```
