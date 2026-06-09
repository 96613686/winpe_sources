# WcmTcpip::InterfaceChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)

- ea: `0x18002bc50`
- end: `0x18002bf2e`
- name: `?InterfaceChangeCallback@WcmTcpip@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z`
- size: `734`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002bc50`
- `0x18002bf34`
- `0x18003a08c`
- `0x1800693d8`
- `0x180084f50`
- `0x180087ab8`
- `0x1800e2650`
- `0x1800e2e7c`
- `0x1800e2eb8`
- `0x1800e3048`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be84`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002be1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002be1d`

## string_xrefs

- `0x18002bee4`: `onecoreuap\net\wcm\service\base\wcmtcpip\wcmtcpip.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall WcmTcpip::InterfaceChangeCallback(unsigned __int16 a1, __int64 a2, __int64 a3, const char *a4)
{
  int v4; // edi
  signed __int32 v8; // r15d
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  __m128i v12; // xmm6
  __int64 v13; // rdx
  signed __int32 v14; // eax
  signed __int32 v15; // ett
  _QWORD *v16; // rax
  char v17; // r10
  volatile signed __int32 *v18; // xmm6_8
  __int64 v19; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int16 v21; // [rsp+48h] [rbp-50h]
  char v22; // [rsp+4Ah] [rbp-4Eh]
  __int128 v23; // [rsp+50h] [rbp-48h]
  _QWORD *v24; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = (int)a4;
  v8 = _InterlockedCompareExchange(&dword_18013FB7C, 0, 0);
  if ( a1 != 2 && a1 != 23 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\wcmtcpip\\wcmtcpip.cpp",
      a4);
  if ( *(_DWORD *)(a2 + 8) != 8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = *(_QWORD **)a2;
  v24 = *(_QWORD **)a2;
  if ( v4 != 2 )
  {
    if ( v4 || *(_DWORD *)a3 != 1 || *(_DWORD *)(a3 + 20) != 16 )
      return;
    if ( *(_DWORD *)(a3 + 16) != 4 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v10 = v24;
    }
    v11 = 0;
    if ( *(_DWORD *)(a3 + 16) == 4 )
      v11 = **(unsigned __int8 **)(a3 + 8);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_DDi(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a1, WPP_GLOBAL_Control, v11, a1, *v10);
    }
  }
  v12 = 0;
  v23 = 0;
  v13 = *((_QWORD *)&xmmword_180140188 + 1);
  if ( *((_QWORD *)&xmmword_180140188 + 1) )
  {
    v14 = *(_DWORD *)(*((_QWORD *)&xmmword_180140188 + 1) + 8LL);
    while ( v14 )
    {
      v15 = v14;
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 8), v14 + 1, v14);
      if ( v15 == v14 )
      {
        v12 = (__m128i)xmmword_180140188;
        v23 = xmmword_180140188;
        break;
      }
    }
  }
  if ( v12.m128i_i64[0] )
  {
    if ( v8 )
    {
      v16 = (_QWORD *)`winrt::Windows::UI::Notifications::ToastNotification::ToastNotification'::`1'::_lambda_25__::_lambda_25__(
                        &v19,
                        &v24);
      if ( (unsigned __int8)std::none_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types__NET_LUID_LH_______WcmTcpip::InterfaceChangeCallback_::_1_::_lambda_2___(
                              *(_QWORD *)(v12.m128i_i64[0] + 304),
                              *(_QWORD *)(v12.m128i_i64[0] + 312),
                              *v16) )
      {
        v20[0] = v12.m128i_i64[0];
        v20[1] = *v24;
        v21 = a1;
        v22 = v17;
        EnterCriticalSection((LPCRITICAL_SECTION)(v12.m128i_i64[0] + 8));
        v19 = v12.m128i_i64[0] + 8;
        if ( *(_BYTE *)(v12.m128i_i64[0] + 272) )
        {
          if ( v12.m128i_i64[0] != -8 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v12.m128i_i64[0] + 8));
        }
        else
        {
          if ( *(_DWORD *)v12.m128i_i64[0] == 1 )
            std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__WcmTcpip::InterfaceChangeCallback_::_26_::_lambda_3___(
              v12.m128i_i64[0] + 152,
              v20);
          else
            std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__WcmTcpip::InterfaceChangeCallback_::_26_::_lambda_3___(
              v12.m128i_i64[0] + 232,
              v20);
          if ( v12.m128i_i64[0] != -8 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v12.m128i_i64[0] + 8));
          _InterlockedIncrement64((volatile signed __int64 *)(v12.m128i_i64[0] + 136));
          SubmitThreadpoolWork(*(PTP_WORK *)(v12.m128i_i64[0] + 128));
        }
      }
    }
    else
    {
      v19 = v12.m128i_i64[0];
      WcmCommon::ThreadPoolWorkQueue::SubmitWork__WcmTcpip::InterfaceChangeCallback_::_21_::_lambda_1___(
        v12.m128i_i64[0],
        &v19);
    }
  }
  v18 = (volatile signed __int32 *)_mm_srli_si128(v12, 8).m128i_u64[0];
  if ( v18 && _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
    if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
  }
}

```

## disassembly

```asm
0x18002bc50  mov     [rsp+arg_0], rbx
0x18002bc55  mov     [rsp+arg_8], rsi
0x18002bc5a  push    rdi
0x18002bc5b  push    r14
0x18002bc5d  push    r15
0x18002bc5f  sub     rsp, 80h
0x18002bc66  movaps  [rsp+98h+var_28], xmm6
0x18002bc6b  mov     rax, cs:__security_cookie
0x18002bc72  xor     rax, rsp
0x18002bc75  mov     [rsp+98h+var_30], rax
0x18002bc7a  mov     edi, r9d
0x18002bc7d  mov     r14, r8
0x18002bc80  mov     rbx, rdx
0x18002bc83  mov     rsi, rcx
0x18002bc86  xor     edx, edx
0x18002bc88  xor     eax, eax
0x18002bc8a  lock cmpxchg cs:dword_18013FB7C, edx
0x18002bc92  mov     r15d, eax
0x18002bc95  cmp     si, 2
0x18002bc99  jnz     short loc_18002BCFD
0x18002bc9b  xor     cl, cl
0x18002bc9d  mov     rax, [rsp+98h]
0x18002bca5  test    cl, cl
0x18002bca7  jnz     loc_18002BEE4
0x18002bcad  cmp     dword ptr [rbx+8], 8
0x18002bcb1  jnz     loc_18002BEF9
0x18002bcb7  mov     rcx, [rbx]
0x18002bcba  mov     [rsp+98h+var_38], rcx
0x18002bcbf  cmp     edi, 2
0x18002bcc2  jz      loc_18002BECE
0x18002bcc8  test    edi, edi
0x18002bcca  jnz     short loc_18002BCD2
0x18002bccc  cmp     dword ptr [r14], 1
0x18002bcd0  jz      short loc_18002BD07
0x18002bcd2  mov     rcx, [rsp+98h+var_30]
0x18002bcd7  xor     rcx, rsp; StackCookie
0x18002bcda  call    __security_check_cookie
0x18002bcdf  lea     r11, [rsp+98h+var_18]
0x18002bce7  mov     rbx, [r11+20h]
0x18002bceb  mov     rsi, [r11+28h]
0x18002bcef  movaps  xmm6, [rsp+98h+var_28]
0x18002bcf4  mov     rsp, r11
0x18002bcf7  pop     r15
0x18002bcf9  pop     r14
0x18002bcfb  pop     rdi
0x18002bcfc  retn
0x18002bcfd  cmp     si, 17h
0x18002bd01  jz      short loc_18002BC9B
0x18002bd03  mov     cl, 1
0x18002bd05  jmp     short loc_18002BC9D
0x18002bd07  cmp     dword ptr [r14+14h], 10h
0x18002bd0c  jnz     short loc_18002BCD2
0x18002bd0e  cmp     dword ptr [r14+10h], 4
0x18002bd13  jnz     loc_18002BF03
0x18002bd19  xor     ebx, ebx
0x18002bd1b  cmp     dword ptr [r14+10h], 4
0x18002bd20  jz      loc_18002BEC2
0x18002bd26  lea     rax, WPP_GLOBAL_Control
0x18002bd2d  mov     r8, cs:WPP_GLOBAL_Control
0x18002bd34  cmp     r8, rax
0x18002bd37  jnz     loc_18002BE8C
0x18002bd3d  test    ebx, ebx
0x18002bd3f  setnz   r10b
0x18002bd43  xorps   xmm6, xmm6
0x18002bd46  movdqu  [rsp+98h+var_48], xmm6
0x18002bd4c  mov     rdx, qword ptr cs:xmmword_180140188+8
0x18002bd53  test    rdx, rdx
0x18002bd56  jz      short loc_18002BD76
0x18002bd58  mov     eax, [rdx+8]
0x18002bd5b  test    eax, eax
0x18002bd5d  jz      short loc_18002BD76
0x18002bd5f  lea     ecx, [rax+1]
0x18002bd62  lock cmpxchg [rdx+8], ecx
0x18002bd67  jnz     short loc_18002BD5B
0x18002bd69  movups  xmm6, cs:xmmword_180140188
0x18002bd70  movdqu  [rsp+98h+var_48], xmm6
0x18002bd76  movq    rbx, xmm6
0x18002bd7b  test    rbx, rbx
0x18002bd7e  jz      loc_18002BE24
0x18002bd84  test    r15d, r15d
0x18002bd87  jz      loc_18002BF12
0x18002bd8d  lea     rdx, [rsp+98h+var_38]
0x18002bd92  lea     rcx, [rsp+98h+var_68]
0x18002bd97  call    ??0_lambda_25__@?0???0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@45@@Z@QEAA@0@Z; `winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)'::`1'::_lambda_25__::_lambda_25__(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x18002bd9c  mov     r8, [rax]
0x18002bd9f  mov     rdx, [rbx+138h]
0x18002bda6  mov     rcx, [rbx+130h]
0x18002bdad  call    std__none_of_std___Vector_iterator_std___Vector_val_std___Simple_types__NET_LUID_LH_______WcmTcpip__InterfaceChangeCallback____1____lambda_2___
0x18002bdb2  test    al, al
0x18002bdb4  jz      short loc_18002BE24
0x18002bdb6  mov     [rsp+98h+var_60], rbx
0x18002bdbb  mov     rax, [rsp+98h+var_38]
0x18002bdc0  mov     rcx, [rax]
0x18002bdc3  mov     [rsp+98h+var_58], rcx
0x18002bdc8  mov     [rsp+98h+var_50], si
0x18002bdcd  mov     [rsp+98h+var_4E], r10b
0x18002bdd2  lea     rdi, [rbx+8]
0x18002bdd6  mov     rcx, rdi; lpCriticalSection
0x18002bdd9  call    cs:__imp_EnterCriticalSection
0x18002bddf  mov     [rsp+98h+var_68], rdi
0x18002bde4  lea     rcx, [rbx+98h]
0x18002bdeb  cmp     byte ptr [rcx+78h], 0
0x18002bdef  jnz     loc_18002BE7C
0x18002bdf5  lea     rdx, [rsp+98h+var_60]
0x18002bdfa  cmp     dword ptr [rbx], 1
0x18002bdfd  jnz     loc_18002BED6
0x18002be03  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__WcmTcpip__InterfaceChangeCallback____26____lambda_3___
0x18002be08  nop
0x18002be09  test    rdi, rdi
0x18002be0c  jnz     short loc_18002BE71
0x18002be0e  lock inc qword ptr [rbx+88h]
0x18002be16  mov     rcx, [rbx+80h]; pwk
0x18002be1d  call    cs:__imp_SubmitThreadpoolWork
0x18002be23  nop
0x18002be24  psrldq  xmm6, 8
0x18002be29  movq    rbx, xmm6
0x18002be2e  test    rbx, rbx
0x18002be31  jz      short loc_18002BE6C
0x18002be33  mov     edi, 0FFFFFFFFh
0x18002be38  mov     eax, edi
0x18002be3a  lock xadd [rbx+8], eax
0x18002be3f  cmp     eax, 1
0x18002be42  jnz     short loc_18002BE6C
0x18002be44  mov     rax, [rbx]
0x18002be47  mov     rcx, rbx
0x18002be4a  mov     rax, [rax]
0x18002be4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be52  lock xadd [rbx+0Ch], edi
0x18002be57  cmp     edi, 1
0x18002be5a  jnz     short loc_18002BE6C
0x18002be5c  mov     rax, [rbx]
0x18002be5f  mov     rcx, rbx
0x18002be62  mov     rax, [rax+8]
0x18002be66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be6b  nop
0x18002be6c  jmp     loc_18002BCD2
0x18002be71  mov     rcx, rdi; lpCriticalSection
0x18002be74  call    cs:__imp_LeaveCriticalSection
0x18002be7a  jmp     short loc_18002BE0E
0x18002be7c  test    rdi, rdi
0x18002be7f  jz      short loc_18002BE24
0x18002be81  mov     rcx, rdi; lpCriticalSection
0x18002be84  call    cs:__imp_LeaveCriticalSection
0x18002be8a  jmp     short loc_18002BE24
0x18002be8c  cmp     byte ptr [r8+19h], 4
0x18002be91  jb      loc_18002BD3D
0x18002be97  test    byte ptr [r8+1Ch], 1
0x18002be9c  jz      loc_18002BD3D
0x18002bea2  movzx   edx, si
0x18002bea5  mov     rax, [rcx]
0x18002bea8  mov     [rsp+98h+var_70], rax
0x18002bead  mov     [rsp+98h+var_78], edx
0x18002beb1  mov     r9d, ebx
0x18002beb4  mov     rcx, [r8+10h]
0x18002beb8  call    WPP_SF_DDi
0x18002bebd  jmp     loc_18002BD3D
0x18002bec2  mov     rax, [r14+8]
0x18002bec6  movzx   ebx, byte ptr [rax]
0x18002bec9  jmp     loc_18002BD26
0x18002bece  xor     r10b, r10b
0x18002bed1  jmp     loc_18002BD43
0x18002bed6  add     rcx, 50h ; 'P'
0x18002beda  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__WcmTcpip__InterfaceChangeCallback____26____lambda_3___
0x18002bedf  jmp     loc_18002BE09
0x18002bee4  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wcm\\service\\base\\wc"...
0x18002beeb  mov     edx, 29Ch; void *
0x18002bef0  mov     rcx, rax; this
0x18002bef3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002bef9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002befe  jmp     loc_18002BCB7
0x18002bf03  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bf08  mov     rcx, [rsp+98h+var_38]
0x18002bf0d  jmp     loc_18002BD19
0x18002bf12  mov     [rsp+98h+var_68], rbx
0x18002bf17  lea     rdx, [rsp+98h+var_68]
0x18002bf1c  mov     rcx, rbx
0x18002bf1f  call    WcmCommon__ThreadPoolWorkQueue__SubmitWork__WcmTcpip__InterfaceChangeCallback____21____lambda_1___
0x18002bf24  jmp     loc_18002BE24
0x18002bf29  jmp     loc_18002BCD2
```
