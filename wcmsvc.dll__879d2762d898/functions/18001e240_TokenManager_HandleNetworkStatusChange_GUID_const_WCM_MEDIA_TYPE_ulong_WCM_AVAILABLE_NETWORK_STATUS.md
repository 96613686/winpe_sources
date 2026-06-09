# TokenManager::HandleNetworkStatusChange(_GUID const &,_WCM_MEDIA_TYPE,ulong,_WCM_AVAILABLE_NETWORK_STATUS)

- ea: `0x18001e240`
- end: `0x18001e340`
- name: `?HandleNetworkStatusChange@TokenManager@@SAXAEBU_GUID@@W4_WCM_MEDIA_TYPE@@KW4_WCM_AVAILABLE_NETWORK_STATUS@@@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x18001e240`
- `0x18001f820`
- `0x1800ddc80`
- `0x1800ddcbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e2af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e2af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e316`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e316`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e32b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e32b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleNetworkStatusChange(__int128 *a1, int a2, int a3, int a4)
{
  int v4; // r10d
  __int128 *v5; // r11
  __m128i v6; // xmm6
  std::_Ref_count_base *v7; // rcx
  const char *v8; // r9
  __int64 v9; // [rsp+38h] [rbp-40h] BYREF
  __int128 v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+54h] [rbp-24h]
  int v13; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = a2;
  v5 = a1;
  v6 = 0;
  if ( *((_QWORD *)&g_weakReference + 1)
    && std::_Ref_count_base::_Incref_nz(*((std::_Ref_count_base **)&g_weakReference + 1)) )
  {
    v6 = (__m128i)g_weakReference;
  }
  if ( v6.m128i_i64[0] )
  {
    v9 = v6.m128i_i64[0];
    v10 = *v5;
    v11 = v4;
    v12 = a3;
    v13 = a4;
    EnterCriticalSection((LPCRITICAL_SECTION)(v6.m128i_i64[0] + 8));
    if ( *(_BYTE *)(v6.m128i_i64[0] + 272) )
    {
      if ( v6.m128i_i64[0] != -8 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v6.m128i_i64[0] + 8));
    }
    else
    {
      try
      {
        if ( *(_DWORD *)v6.m128i_i64[0] == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleNetworkStatusChange_::_6_::_lambda_1___(
            v6.m128i_i64[0] + 152,
            &v9);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleNetworkStatusChange_::_6_::_lambda_1___(
            v6.m128i_i64[0] + 232,
            &v9);
        if ( v6.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v6.m128i_i64[0] + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v6.m128i_i64[0] + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v6.m128i_i64[0] + 128));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
          v8);
        return;
      }
    }
  }
  v7 = (std::_Ref_count_base *)_mm_srli_si128(v6, 8).m128i_u64[0];
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x18001e240  mov     [rsp+arg_0], rbx
0x18001e245  push    rdi
0x18001e246  sub     rsp, 70h
0x18001e24a  movaps  [rsp+78h+var_18], xmm6
0x18001e24f  mov     r10d, edx
0x18001e252  mov     r11, rcx
0x18001e255  xorps   xmm6, xmm6
0x18001e258  movdqu  [rsp+78h+var_50], xmm6
0x18001e25e  mov     rcx, qword ptr cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A+8; this
0x18001e265  test    rcx, rcx
0x18001e268  jz      short loc_18001E280
0x18001e26a  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18001e26f  test    al, al
0x18001e271  jz      short loc_18001E280
0x18001e273  movups  xmm6, cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A; std::weak_ptr<TokenManager> g_weakReference
0x18001e27a  movdqu  [rsp+78h+var_50], xmm6
0x18001e280  movq    rbx, xmm6
0x18001e285  test    rbx, rbx
0x18001e288  jz      short loc_18001E2D6
0x18001e28a  mov     [rsp+78h+var_40], rbx
0x18001e28f  movups  xmm0, xmmword ptr [r11]
0x18001e293  movdqu  [rsp+78h+var_38], xmm0
0x18001e299  mov     [rsp+78h+var_28], r10d
0x18001e29e  mov     [rsp+78h+var_24], r8d
0x18001e2a3  mov     [rsp+78h+var_20], r9d
0x18001e2a8  lea     rdi, [rbx+8]
0x18001e2ac  mov     rcx, rdi; lpCriticalSection
0x18001e2af  call    cs:__imp_EnterCriticalSection
0x18001e2b5  mov     [rsp+78h+var_58], rdi
0x18001e2ba  lea     rcx, [rbx+98h]
0x18001e2c1  cmp     byte ptr [rcx+78h], 0
0x18001e2c5  jz      short loc_18001E2FE
0x18001e2c7  test    rdi, rdi
0x18001e2ca  jz      short loc_18001E2D6
0x18001e2cc  mov     rcx, rdi; lpCriticalSection
0x18001e2cf  call    cs:__imp_LeaveCriticalSection
0x18001e2d5  nop
0x18001e2d6  psrldq  xmm6, 8
0x18001e2db  movq    rcx, xmm6; this
0x18001e2e0  test    rcx, rcx
0x18001e2e3  jz      short loc_18001E2EB
0x18001e2e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e2ea  nop
0x18001e2eb  mov     rbx, [rsp+78h+arg_0]
0x18001e2f3  movaps  xmm6, [rsp+78h+var_18]
0x18001e2f8  add     rsp, 70h
0x18001e2fc  pop     rdi
0x18001e2fd  retn
0x18001e2fe  lea     rdx, [rsp+78h+var_40]
0x18001e303  cmp     dword ptr [rbx], 1
0x18001e306  jnz     short loc_18001E333
0x18001e308  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleNetworkStatusChange____6____lambda_1___
0x18001e30d  nop
0x18001e30e  test    rdi, rdi
0x18001e311  jz      short loc_18001E31C
0x18001e313  mov     rcx, rdi; lpCriticalSection
0x18001e316  call    cs:__imp_LeaveCriticalSection
0x18001e31c  lock inc qword ptr [rbx+88h]
0x18001e324  mov     rcx, [rbx+80h]; pwk
0x18001e32b  call    cs:__imp_SubmitThreadpoolWork
0x18001e331  jmp     short loc_18001E2D6
0x18001e333  add     rcx, 50h ; 'P'
0x18001e337  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleNetworkStatusChange____6____lambda_1___
0x18001e33c  jmp     short loc_18001E30E
0x18001e33e  jmp     short loc_18001E2EB
```
