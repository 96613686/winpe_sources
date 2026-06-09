# RoutePolicyOnDemand::CompleteRequest(RoutePolicyOnDemand::Request &,long,_NET_LUID_LH)

- ea: `0x1800a7830`
- end: `0x1800a7903`
- name: `?CompleteRequest@RoutePolicyOnDemand@@AEAAXAEAURequest@1@JT_NET_LUID_LH@@@Z`
- size: `211`
- prototype: `void __fastcall(RoutePolicyOnDemand *__hidden this, struct Request *, int, union _NET_LUID_LH)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a4d9c`
- `0x1800a4f5c`
- `0x1800a5144`
- `0x1800a54d8`
- `0x1800a5b90`
- `0x1800a61dc`
- `0x1800a639c`
- `0x1800a7964`
- `0x1800a8c40`

## callees

- `0x180027630`
- `0x1800a3124`
- `0x1800a3160`
- `0x1800a7830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7894`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a78c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7894`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a78c5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a78da`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a78da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RoutePolicyOnDemand::CompleteRequest(
        RoutePolicyOnDemand *this,
        struct Request *a2,
        int a3,
        union _NET_LUID_LH a4)
{
  const char *v6; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v8[3]; // [rsp+28h] [rbp-30h] BYREF
  int v9; // [rsp+40h] [rbp-18h]
  union _NET_LUID_LH v10; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8[0] = *((_QWORD *)a2 + 16);
  v8[1] = a2;
  v8[2] = *((_QWORD *)a2 + 17);
  v9 = a3;
  v10.Value = a4.Value;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 384);
  try
  {
    if ( *((_BYTE *)this + 648) )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( *((_DWORD *)this + 94) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RoutePolicyOnDemand::CompleteRequest_::_3_::_lambda_1___(
          (char *)this + 528,
          v8);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RoutePolicyOnDemand::CompleteRequest_::_3_::_lambda_1___(
          (char *)this + 608,
          v8);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      _InterlockedIncrement64((volatile signed __int64 *)this + 64);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 63));
    }
    *((_QWORD *)a2 + 16) = 0;
    *((_QWORD *)a2 + 17) = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x779,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x1800a7830  mov     r11, rsp
0x1800a7833  mov     [r11+18h], rbx
0x1800a7837  push    rdi
0x1800a7838  sub     rsp, 50h
0x1800a783c  mov     rdi, rdx
0x1800a783f  mov     rbx, rcx
0x1800a7842  mov     rax, [rdx+80h]
0x1800a7849  mov     [r11-30h], rax
0x1800a784d  mov     [r11-28h], rdx
0x1800a7851  mov     rax, [rdx+88h]
0x1800a7858  mov     [r11-20h], rax
0x1800a785c  mov     [r11-18h], r8d
0x1800a7860  mov     [r11-10h], r9
0x1800a7864  mov     qword ptr [r11-38h], 0
0x1800a786c  lea     rdx, [rcx+180h]
0x1800a7873  lea     rcx, [r11-38h]
0x1800a7877  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a787c  nop
0x1800a787d  lea     rcx, [rbx+210h]
0x1800a7884  cmp     byte ptr [rcx+78h], 0
0x1800a7888  jz      short loc_1800A789C
0x1800a788a  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800a788f  test    rcx, rcx
0x1800a7892  jz      short loc_1800A78E0
0x1800a7894  call    cs:__imp_LeaveCriticalSection
0x1800a789a  jmp     short loc_1800A78E0
0x1800a789c  lea     rdx, [rsp+58h+var_30]
0x1800a78a1  cmp     dword ptr [rbx+178h], 1
0x1800a78a8  jnz     short loc_1800A78B1
0x1800a78aa  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RoutePolicyOnDemand__CompleteRequest____3____lambda_1___
0x1800a78af  jmp     short loc_1800A78BB
0x1800a78b1  add     rcx, 50h ; 'P'
0x1800a78b5  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RoutePolicyOnDemand__CompleteRequest____3____lambda_1___
0x1800a78ba  nop
0x1800a78bb  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800a78c0  test    rcx, rcx
0x1800a78c3  jz      short loc_1800A78CB
0x1800a78c5  call    cs:__imp_LeaveCriticalSection
0x1800a78cb  lock inc qword ptr [rbx+200h]
0x1800a78d3  mov     rcx, [rbx+1F8h]; pwk
0x1800a78da  call    cs:__imp_SubmitThreadpoolWork
0x1800a78e0  mov     qword ptr [rdi+80h], 0
0x1800a78eb  mov     qword ptr [rdi+88h], 0
0x1800a78f6  jmp     short $+2
0x1800a78f8  mov     rbx, [rsp+58h+arg_10]
0x1800a78fd  add     rsp, 50h
0x1800a7901  pop     rdi
0x1800a7902  retn
```
