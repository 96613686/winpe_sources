# RoutePolicyOnDemand::ConnectTimeoutCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180070e70`
- end: `0x180070f7f`
- name: `?ConnectTimeoutCallback@RoutePolicyOnDemand@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `271`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008344`
- `0x180010080`
- `0x180027630`
- `0x180070e70`
- `0x18007103c`
- `0x180084f50`
- `0x1800a3228`
- `0x1800a32dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070f3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070f3e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070f53`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070f53`

## string_xrefs

- `0x180070eb0`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RoutePolicyOnDemand::ConnectTimeoutCallback(
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::ConnectTimeoutCallback_::_3_::_lambda_1___(
            (char *)v4 + 248,
            v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::ConnectTimeoutCallback_::_3_::_lambda_1___(
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
        (void *)0x619,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x5DE,
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
0x180070e70  push    rbx
0x180070e72  sub     rsp, 50h
0x180070e76  mov     rax, cs:__security_cookie
0x180070e7d  xor     rax, rsp
0x180070e80  mov     [rsp+58h+var_10], rax
0x180070e85  mov     r9, rdx
0x180070e88  xorps   xmm0, xmm0
0x180070e8b  movups  xmmword ptr [rsp+58h+var_20], xmm0
0x180070e90  lea     rdx, [rsp+58h+var_20]
0x180070e95  call    ?lock@?$weak_ptr@VRoutePolicyOnDemand@@@std@@QEBA?AV?$shared_ptr@VRoutePolicyOnDemand@@@2@XZ; std::weak_ptr<RoutePolicyOnDemand>::lock(void)
0x180070e9a  nop
0x180070e9b  mov     rbx, [rsp+58h+var_20]
0x180070ea0  test    rbx, rbx
0x180070ea3  jnz     short loc_180070ED7
0x180070ea5  mov     rcx, [rsp+58h]; this
0x180070eaa  mov     r9d, 139Fh; char *
0x180070eb0  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180070eb7  mov     edx, 5DEh; void *
0x180070ebc  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070ec1  nop
0x180070ec2  mov     rcx, [rsp+58h+var_20+8]; this
0x180070ec7  test    rcx, rcx
0x180070eca  jz      short loc_180070ED2
0x180070ecc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070ed1  nop
0x180070ed2  jmp     loc_180070F6C
0x180070ed7  mov     [rsp+58h+var_30], rbx
0x180070edc  mov     [rsp+58h+var_28], r9
0x180070ee1  mov     [rsp+58h+lpCriticalSection], 0
0x180070eea  lea     rdx, [rbx+68h]
0x180070eee  lea     rcx, [rsp+58h+lpCriticalSection]
0x180070ef3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070ef8  nop
0x180070ef9  lea     rcx, [rbx+0F8h]
0x180070f00  cmp     byte ptr [rcx+78h], 0
0x180070f04  jz      short loc_180070F18
0x180070f06  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070f0b  test    rcx, rcx
0x180070f0e  jz      short loc_180070F5A
0x180070f10  call    cs:__imp_LeaveCriticalSection
0x180070f16  jmp     short loc_180070F5A
0x180070f18  lea     rdx, [rsp+58h+var_30]
0x180070f1d  cmp     dword ptr [rbx+60h], 1
0x180070f21  jnz     short loc_180070F2A
0x180070f23  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__ConnectTimeoutCallback____3____lambda_1___
0x180070f28  jmp     short loc_180070F34
0x180070f2a  add     rcx, 50h ; 'P'
0x180070f2e  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__ConnectTimeoutCallback____3____lambda_1___
0x180070f33  nop
0x180070f34  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180070f39  test    rcx, rcx
0x180070f3c  jz      short loc_180070F44
0x180070f3e  call    cs:__imp_LeaveCriticalSection
0x180070f44  lock inc qword ptr [rbx+0E8h]
0x180070f4c  mov     rcx, [rbx+0E0h]; pwk
0x180070f53  call    cs:__imp_SubmitThreadpoolWork
0x180070f59  nop
0x180070f5a  mov     rcx, [rsp+58h+var_20+8]; this
0x180070f5f  test    rcx, rcx
0x180070f62  jz      short loc_180070F6A
0x180070f64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070f69  nop
0x180070f6a  jmp     short $+2
0x180070f6c  mov     rcx, [rsp+58h+var_10]
0x180070f71  xor     rcx, rsp; StackCookie
0x180070f74  call    __security_check_cookie
0x180070f79  add     rsp, 50h
0x180070f7d  pop     rbx
0x180070f7e  retn
```
