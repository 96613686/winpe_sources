# TokenManager::HandleEnterExitNetQuiet(void)

- ea: `0x18001ecbc`
- end: `0x18001ed9a`
- name: `?HandleEnterExitNetQuiet@TokenManager@@SAXXZ`
- size: `222`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x18001ecbc`
- `0x18001f820`
- `0x1800dd81c`
- `0x1800dd8d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed85`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ed51`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ed51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleEnterExitNetQuiet(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __m128i v4; // xmm6
  std::_Ref_count_base *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( *((_QWORD *)&g_weakReference + 1)
    && std::_Ref_count_base::_Incref_nz(*((std::_Ref_count_base **)&g_weakReference + 1)) )
  {
    v4 = (__m128i)g_weakReference;
  }
  try
  {
    if ( v4.m128i_i64[0] )
    {
      v7 = v4.m128i_i64[0];
      EnterCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      v8 = v4.m128i_i64[0] + 8;
      if ( *(_BYTE *)(v4.m128i_i64[0] + 272) )
      {
        if ( v4.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      }
      else
      {
        if ( *(_DWORD *)v4.m128i_i64[0] == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleEnterExitNetQuiet_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 152,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleEnterExitNetQuiet_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 232,
            &v7);
        if ( v4.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v4.m128i_i64[0] + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v4.m128i_i64[0] + 128));
      }
    }
    v5 = (std::_Ref_count_base *)_mm_srli_si128(v4, 8).m128i_u64[0];
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      a4);
  }
}

```

## disassembly

```asm
0x18001ecbc  mov     [rsp+arg_10], rbx
0x18001ecc1  push    rdi
0x18001ecc2  sub     rsp, 40h
0x18001ecc6  movaps  [rsp+48h+var_18], xmm6
0x18001eccb  xorps   xmm6, xmm6
0x18001ecce  movdqu  [rsp+48h+var_28], xmm6
0x18001ecd4  mov     rcx, qword ptr cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A+8; this
0x18001ecdb  test    rcx, rcx
0x18001ecde  jz      short loc_18001ECF6
0x18001ece0  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18001ece5  test    al, al
0x18001ece7  jz      short loc_18001ECF6
0x18001ece9  movups  xmm6, cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A; std::weak_ptr<TokenManager> g_weakReference
0x18001ecf0  movdqu  [rsp+48h+var_28], xmm6
0x18001ecf6  movq    rbx, xmm6
0x18001ecfb  test    rbx, rbx
0x18001ecfe  jz      short loc_18001ED58
0x18001ed00  mov     [rsp+48h+arg_0], rbx
0x18001ed05  lea     rdi, [rbx+8]
0x18001ed09  mov     rcx, rdi; lpCriticalSection
0x18001ed0c  call    cs:__imp_EnterCriticalSection
0x18001ed12  mov     [rsp+48h+arg_8], rdi
0x18001ed17  lea     rcx, [rbx+98h]
0x18001ed1e  cmp     byte ptr [rcx+78h], 0
0x18001ed22  jnz     short loc_18001ED7D
0x18001ed24  lea     rdx, [rsp+48h+arg_0]
0x18001ed29  cmp     dword ptr [rbx], 1
0x18001ed2c  jnz     short loc_18001ED8D
0x18001ed2e  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleEnterExitNetQuiet____6____lambda_1___
0x18001ed33  nop
0x18001ed34  test    rdi, rdi
0x18001ed37  jz      short loc_18001ED42
0x18001ed39  mov     rcx, rdi; lpCriticalSection
0x18001ed3c  call    cs:__imp_LeaveCriticalSection
0x18001ed42  lock inc qword ptr [rbx+88h]
0x18001ed4a  mov     rcx, [rbx+80h]; pwk
0x18001ed51  call    cs:__imp_SubmitThreadpoolWork
0x18001ed57  nop
0x18001ed58  psrldq  xmm6, 8
0x18001ed5d  movq    rcx, xmm6; this
0x18001ed62  test    rcx, rcx
0x18001ed65  jz      short loc_18001ED6D
0x18001ed67  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ed6c  nop
0x18001ed6d  mov     rbx, [rsp+48h+arg_10]
0x18001ed72  movaps  xmm6, [rsp+48h+var_18]
0x18001ed77  add     rsp, 40h
0x18001ed7b  pop     rdi
0x18001ed7c  retn
0x18001ed7d  test    rdi, rdi
0x18001ed80  jz      short loc_18001ED58
0x18001ed82  mov     rcx, rdi; lpCriticalSection
0x18001ed85  call    cs:__imp_LeaveCriticalSection
0x18001ed8b  jmp     short loc_18001ED58
0x18001ed8d  add     rcx, 50h ; 'P'
0x18001ed91  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleEnterExitNetQuiet____6____lambda_1___
0x18001ed96  jmp     short loc_18001ED34
0x18001ed98  jmp     short loc_18001ED6D
```
