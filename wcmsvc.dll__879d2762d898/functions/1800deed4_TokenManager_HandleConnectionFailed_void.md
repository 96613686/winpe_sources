# TokenManager::HandleConnectionFailed(void)

- ea: `0x1800deed4`
- end: `0x1800defa8`
- name: `?HandleConnectionFailed@TokenManager@@SAXXZ`
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
- `0x1800dd100`
- `0x1800dd1b4`
- `0x1800deed4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800def3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800def67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800def3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800def67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800def7c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800def7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleConnectionFailed(__int64 a1)
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleConnectionFailed_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleConnectionFailed_::_6_::_lambda_1___(
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
      (void *)0xE4,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800deed4  push    rbx
0x1800deed6  sub     rsp, 50h
0x1800deeda  mov     rax, cs:__security_cookie
0x1800deee1  xor     rax, rsp
0x1800deee4  mov     [rsp+58h+var_18], rax
0x1800deee9  xorps   xmm0, xmm0
0x1800deeec  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800deef1  lea     rdx, [rsp+58h+var_28]
0x1800deef6  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800deefb  nop
0x1800deefc  mov     rbx, [rsp+58h+var_28]
0x1800def01  test    rbx, rbx
0x1800def04  jz      short loc_1800DEF83
0x1800def06  mov     [rsp+58h+var_30], rbx
0x1800def0b  mov     [rsp+58h+lpCriticalSection], 0
0x1800def14  lea     rdx, [rbx+8]
0x1800def18  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800def1d  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800def22  nop
0x1800def23  lea     rcx, [rbx+98h]
0x1800def2a  cmp     byte ptr [rcx+78h], 0
0x1800def2e  jz      short loc_1800DEF42
0x1800def30  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800def35  test    rcx, rcx
0x1800def38  jz      short loc_1800DEF83
0x1800def3a  call    cs:__imp_LeaveCriticalSection
0x1800def40  jmp     short loc_1800DEF83
0x1800def42  lea     rdx, [rsp+58h+var_30]
0x1800def47  cmp     dword ptr [rbx], 1
0x1800def4a  jnz     short loc_1800DEF53
0x1800def4c  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleConnectionFailed____6____lambda_1___
0x1800def51  jmp     short loc_1800DEF5D
0x1800def53  add     rcx, 50h ; 'P'
0x1800def57  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleConnectionFailed____6____lambda_1___
0x1800def5c  nop
0x1800def5d  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800def62  test    rcx, rcx
0x1800def65  jz      short loc_1800DEF6D
0x1800def67  call    cs:__imp_LeaveCriticalSection
0x1800def6d  lock inc qword ptr [rbx+88h]
0x1800def75  mov     rcx, [rbx+80h]; pwk
0x1800def7c  call    cs:__imp_SubmitThreadpoolWork
0x1800def82  nop
0x1800def83  mov     rcx, [rsp+58h+var_28+8]; this
0x1800def88  test    rcx, rcx
0x1800def8b  jz      short loc_1800DEF93
0x1800def8d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800def92  nop
0x1800def93  jmp     short $+2
0x1800def95  mov     rcx, [rsp+58h+var_18]
0x1800def9a  xor     rcx, rsp; StackCookie
0x1800def9d  call    __security_check_cookie
0x1800defa2  add     rsp, 50h
0x1800defa6  pop     rbx
0x1800defa7  retn
```
