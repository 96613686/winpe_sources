# PolicyRefreshCacheHelper::WaitForGPWNFEvents(void)

- ea: `0x18002402c`
- end: `0x18002425c`
- name: `?WaitForGPWNFEvents@PolicyRefreshCacheHelper@@SAJXZ`
- size: `560`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000cfc0`

## callees

- `0x18000aae4`
- `0x18000ab04`
- `0x18000e620`
- `0x18000ec2c`
- `0x18002402c`
- `0x1800247e4`
- `0x180024f3c`
- `0x180025478`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002406b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002406b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002415c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002415c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002407d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002407d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002418f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002418f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024128`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024198`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024128`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024198`

## string_xrefs

- `0x18002422f`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 PolicyRefreshCacheHelper::WaitForGPWNFEvents(void)
{
  void *v0; // rdx
  HANDLE Event; // rbx
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 v4; // rcx
  __int64 v5; // r8
  void **v6; // rsi
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  volatile signed __int32 *v8; // rdi
  void (__fastcall ***v9)(_QWORD, __int64); // rbx
  ULONGLONG TickCount64; // r12
  HANDLE v11; // rax
  void *v12; // rcx
  __int64 v13; // r8
  const char *v14; // r9
  DWORD v15; // r15d
  const char *v16; // r9
  unsigned __int64 v17; // r14
  unsigned int LastError; // esi
  HANDLE *lpHandles[2]; // [rsp+20h] [rbp-79h] BYREF
  HANDLE *v21; // [rsp+30h] [rbp-69h]
  __int128 v22; // [rsp+38h] [rbp-61h] BYREF
  char v23[8]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v24[13]; // [rsp+60h] [rbp-39h] BYREF
  _QWORD *v25; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  void (__fastcall ***v27)(_QWORD, __int64); // [rsp+100h] [rbp+67h] BYREF
  __int64 v28; // [rsp+108h] [rbp+6Fh]

  *(_OWORD *)lpHandles = 0;
  v21 = 0;
  v22 = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v0, v2, v3);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    &v22,
    Event);
  v28 = 0;
  v6 = (void **)v22;
  if ( (_QWORD)v22 )
    v7 = *(void (__fastcall ****)(_QWORD, __int64))v22;
  else
    v7 = 0;
  v27 = v7;
  if ( lpHandles[1] == v21 )
    std::vector<void *>::_Emplace_reallocate<void *>(lpHandles, lpHandles[1], &v27);
  else
    *lpHandles[1]++ = v7;
  v8 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  if ( *((_QWORD *)&v22 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL));
  v24[0] = &off_18003BF40;
  v24[1] = v6;
  v24[2] = v8;
  v25 = v24;
  v27 = 0;
  v9 = 0;
  if ( (int)wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v4, v23, v5, &v27) >= 0 )
    v9 = v27;
  if ( v25 )
    (*(void (__fastcall **)(_QWORD *))(*v25 + 24LL))(v25);
  TickCount64 = GetTickCount64();
  while ( 1 )
  {
    v15 = WaitForMultipleObjects(lpHandles[1] - lpHandles[0], lpHandles[0], 0, 0x7530u);
    v17 = GetTickCount64() - TickCount64;
    if ( v15 == 258 )
    {
LABEL_25:
      LastError = 0;
      goto LABEL_26;
    }
    v11 = v6 ? *v6 : 0LL;
    if ( lpHandles[0][v15] != v11 )
      break;
    if ( v6 )
      v12 = *v6;
    else
      v12 = 0;
    if ( !ResetEvent(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CC, v13, v14);
    if ( v17 >= 0x927C0 )
      goto LABEL_25;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1D3,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
                v16);
LABEL_26:
  if ( v9 )
    (**v9)(v9, 1);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  std::vector<void *>::~vector<void *>(lpHandles);
  return LastError;
}

```

## disassembly

```asm
0x18002402c  mov     [rsp-8+arg_10], rbx
0x180024031  mov     [rsp-8+arg_18], rsi
0x180024036  push    rbp
0x180024037  push    rdi
0x180024038  push    r12
0x18002403a  push    r14
0x18002403c  push    r15
0x18002403e  lea     rbp, [rsp-37h]
0x180024043  sub     rsp, 0D0h
0x18002404a  xor     eax, eax
0x18002404c  xorps   xmm1, xmm1
0x18002404f  movdqu  xmmword ptr [rbp+57h+lpHandles], xmm1
0x180024054  mov     [rbp+57h+var_C0], rax
0x180024058  movdqu  [rbp+57h+var_B8], xmm1
0x18002405d  xor     edx, edx; lpName
0x18002405f  xor     ecx, ecx; lpEventAttributes
0x180024061  mov     r9d, 1F0003h; dwDesiredAccess
0x180024067  lea     r8d, [rax+1]; dwFlags
0x18002406b  call    cs:__imp_CreateEventExW
0x180024071  mov     rbx, rax
0x180024074  test    rax, rax
0x180024077  jz      loc_180024252
0x18002407d  call    cs:__imp_GetLastError
0x180024083  mov     rdx, rbx
0x180024086  lea     rcx, [rbp+57h+var_B8]
0x18002408a  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18002408f  nop
0x180024090  mov     [rbp+57h+arg_8], 0
0x180024098  mov     rsi, qword ptr [rbp+57h+var_B8]
0x18002409c  test    rsi, rsi
0x18002409f  jz      short loc_1800240A6
0x1800240a1  mov     rax, [rsi]
0x1800240a4  jmp     short loc_1800240A8
0x1800240a6  xor     eax, eax
0x1800240a8  mov     [rbp+57h+arg_0], rax
0x1800240ac  mov     rdx, [rbp+57h+lpHandles+8]
0x1800240b0  cmp     rdx, [rbp+57h+var_C0]
0x1800240b4  jz      short loc_1800240C0
0x1800240b6  mov     [rdx], rax
0x1800240b9  add     [rbp+57h+lpHandles+8], 8
0x1800240be  jmp     short loc_1800240CD
0x1800240c0  lea     r8, [rbp+57h+arg_0]
0x1800240c4  lea     rcx, [rbp+57h+lpHandles]
0x1800240c8  call    ??$_Emplace_reallocate@PEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAX$$QEAPEAX@Z; std::vector<void *>::_Emplace_reallocate<void *>(void * * const,void * &&)
0x1800240cd  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x1800240d1  test    rdi, rdi
0x1800240d4  jz      short loc_1800240DA
0x1800240d6  lock inc dword ptr [rdi+8]
0x1800240da  lea     rax, off_18003BF40
0x1800240e1  mov     [rbp+57h+var_90], rax
0x1800240e5  mov     [rbp+57h+var_88], rsi
0x1800240e9  mov     [rbp+57h+var_80], rdi
0x1800240ed  lea     rax, [rbp+57h+var_90]
0x1800240f1  mov     [rbp+57h+var_28], rax
0x1800240f5  mov     [rbp+57h+arg_0], 0
0x1800240fd  lea     r9, [rbp+57h+arg_0]
0x180024101  lea     rdx, [rbp+57h+var_98]
0x180024105  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x18002410a  xor     ebx, ebx
0x18002410c  test    eax, eax
0x18002410e  cmovns  rbx, [rbp+57h+arg_0]
0x180024113  mov     rcx, [rbp+57h+var_28]
0x180024117  test    rcx, rcx
0x18002411a  jz      short loc_180024128
0x18002411c  mov     rax, [rcx]
0x18002411f  mov     rax, [rax+18h]
0x180024123  call    _guard_dispatch_icall
0x180024128  call    cs:__imp_GetTickCount64
0x18002412e  mov     r12, rax
0x180024131  jmp     short loc_180024177
0x180024133  mov     edx, r15d
0x180024136  mov     rcx, [rbp+57h+lpHandles]
0x18002413a  test    rsi, rsi
0x18002413d  jz      short loc_180024144
0x18002413f  mov     rax, [rsi]
0x180024142  jmp     short loc_180024146
0x180024144  xor     eax, eax
0x180024146  cmp     [rcx+rdx*8], rax
0x18002414a  jnz     loc_18002422B
0x180024150  test    rsi, rsi
0x180024153  jz      short loc_18002415A
0x180024155  mov     rcx, [rsi]
0x180024158  jmp     short loc_18002415C
0x18002415a  xor     ecx, ecx; hEvent
0x18002415c  call    cs:__imp_ResetEvent
0x180024162  mov     rcx, [rbp+5Fh]; this
0x180024166  test    eax, eax
0x180024168  jz      loc_180024247
0x18002416e  cmp     r14, 927C0h
0x180024175  jnb     short loc_1800241AD
0x180024177  mov     rdx, [rbp+57h+lpHandles]; lpHandles
0x18002417b  mov     rcx, [rbp+57h+lpHandles+8]
0x18002417f  sub     rcx, rdx
0x180024182  mov     r9d, 7530h; dwMilliseconds
0x180024188  xor     r8d, r8d; bWaitAll
0x18002418b  sar     rcx, 3; nCount
0x18002418f  call    cs:__imp_WaitForMultipleObjects
0x180024195  mov     r15d, eax
0x180024198  call    cs:__imp_GetTickCount64
0x18002419e  mov     r14, rax
0x1800241a1  sub     r14, r12
0x1800241a4  cmp     r15d, 102h
0x1800241ab  jnz     short loc_180024133
0x1800241ad  xor     esi, esi
0x1800241af  test    rbx, rbx
0x1800241b2  jz      short loc_1800241C8
0x1800241b4  mov     rax, [rbx]
0x1800241b7  mov     edx, 1
0x1800241bc  mov     rcx, rbx
0x1800241bf  mov     rax, [rax]
0x1800241c2  call    _guard_dispatch_icall
0x1800241c7  nop
0x1800241c8  test    rdi, rdi
0x1800241cb  jz      short loc_180024204
0x1800241cd  or      ebx, 0FFFFFFFFh
0x1800241d0  mov     eax, ebx
0x1800241d2  lock xadd [rdi+8], eax
0x1800241d7  add     eax, ebx
0x1800241d9  jnz     short loc_180024204
0x1800241db  mov     rax, [rdi]
0x1800241de  mov     rcx, rdi
0x1800241e1  mov     rax, [rax]
0x1800241e4  call    _guard_dispatch_icall
0x1800241e9  mov     edx, ebx
0x1800241eb  lock xadd [rdi+0Ch], edx
0x1800241f0  add     edx, ebx
0x1800241f2  jnz     short loc_180024204
0x1800241f4  mov     rdx, [rdi]
0x1800241f7  mov     rcx, rdi
0x1800241fa  mov     rax, [rdx+8]
0x1800241fe  call    _guard_dispatch_icall
0x180024203  nop
0x180024204  lea     rcx, [rbp+57h+lpHandles]
0x180024208  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18002420d  mov     eax, esi
0x18002420f  lea     r11, [rsp+0F0h+var_20]
0x180024217  mov     rbx, [r11+40h]
0x18002421b  mov     rsi, [r11+48h]
0x18002421f  mov     rsp, r11
0x180024222  pop     r15
0x180024224  pop     r14
0x180024226  pop     r12
0x180024228  pop     rdi
0x180024229  pop     rbp
0x18002422a  retn
0x18002422b  mov     rcx, [rbp+5Fh]; this
0x18002422f  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180024236  mov     edx, 1D3h; void *
0x18002423b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024240  mov     esi, eax
0x180024242  jmp     loc_1800241AF
0x180024247  mov     edx, 9CCh; void *
0x18002424c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024252  mov     rcx, [rbp+5Fh]; this
0x180024256  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
