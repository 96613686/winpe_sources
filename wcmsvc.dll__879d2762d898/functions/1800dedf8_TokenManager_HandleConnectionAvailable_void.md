# TokenManager::HandleConnectionAvailable(void)

- ea: `0x1800dedf8`
- end: `0x1800deecc`
- name: `?HandleConnectionAvailable@TokenManager@@SAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003c684`
- `0x180084f50`
- `0x1800dcf94`
- `0x1800dd048`
- `0x1800dedf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dee5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dee8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dee5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dee8b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800deea0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800deea0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleConnectionAvailable(__int64 a1)
{
  const char *v1; // r9
  std::_Ref_count_base *v2; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v4; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v5 = 0;
  std::weak_ptr<TokenManager>::lock(a1, v5);
  try
  {
    v2 = v5[0];
    if ( v5[0] )
    {
      v4 = v5[0];
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, (char *)v5[0] + 8);
      if ( *((_BYTE *)v2 + 272) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *(_DWORD *)v2 == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleConnectionAvailable_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleConnectionAvailable_::_6_::_lambda_1___(
            (char *)v2 + 232,
            &v4);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 17);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 16));
      }
    }
    if ( v5[1] )
      std::_Ref_count_base::_Decref(v5[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800dedf8  push    rbx
0x1800dedfa  sub     rsp, 50h
0x1800dedfe  mov     rax, cs:__security_cookie
0x1800dee05  xor     rax, rsp
0x1800dee08  mov     [rsp+58h+var_18], rax
0x1800dee0d  xorps   xmm0, xmm0
0x1800dee10  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800dee15  lea     rdx, [rsp+58h+var_28]
0x1800dee1a  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800dee1f  nop
0x1800dee20  mov     rbx, [rsp+58h+var_28]
0x1800dee25  test    rbx, rbx
0x1800dee28  jz      short loc_1800DEEA7
0x1800dee2a  mov     [rsp+58h+var_30], rbx
0x1800dee2f  mov     [rsp+58h+lpCriticalSection], 0
0x1800dee38  lea     rdx, [rbx+8]
0x1800dee3c  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800dee41  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800dee46  nop
0x1800dee47  lea     rcx, [rbx+98h]
0x1800dee4e  cmp     byte ptr [rcx+78h], 0
0x1800dee52  jz      short loc_1800DEE66
0x1800dee54  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800dee59  test    rcx, rcx
0x1800dee5c  jz      short loc_1800DEEA7
0x1800dee5e  call    cs:__imp_LeaveCriticalSection
0x1800dee64  jmp     short loc_1800DEEA7
0x1800dee66  lea     rdx, [rsp+58h+var_30]
0x1800dee6b  cmp     dword ptr [rbx], 1
0x1800dee6e  jnz     short loc_1800DEE77
0x1800dee70  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleConnectionAvailable____6____lambda_1___
0x1800dee75  jmp     short loc_1800DEE81
0x1800dee77  add     rcx, 50h ; 'P'
0x1800dee7b  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleConnectionAvailable____6____lambda_1___
0x1800dee80  nop
0x1800dee81  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800dee86  test    rcx, rcx
0x1800dee89  jz      short loc_1800DEE91
0x1800dee8b  call    cs:__imp_LeaveCriticalSection
0x1800dee91  lock inc qword ptr [rbx+88h]
0x1800dee99  mov     rcx, [rbx+80h]; pwk
0x1800deea0  call    cs:__imp_SubmitThreadpoolWork
0x1800deea6  nop
0x1800deea7  mov     rcx, [rsp+58h+var_28+8]; this
0x1800deeac  test    rcx, rcx
0x1800deeaf  jz      short loc_1800DEEB7
0x1800deeb1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800deeb6  nop
0x1800deeb7  jmp     short $+2
0x1800deeb9  mov     rcx, [rsp+58h+var_18]
0x1800deebe  xor     rcx, rsp; StackCookie
0x1800deec1  call    __security_check_cookie
0x1800deec6  add     rsp, 50h
0x1800deeca  pop     rbx
0x1800deecb  retn
```
