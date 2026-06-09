# Windows::Internal::CloudRequestor::TokenBrokerHandler::SetTokenRefreshTime(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)

- ea: `0x180046a00`
- end: `0x180046cd2`
- name: `?SetTokenRefreshTime@TokenBrokerHandler@CloudRequestor@Internal@Windows@@AEAAJV?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800446f0`

## callees

- `0x180002810`
- `0x18000c784`
- `0x1800139fc`
- `0x18004254c`
- `0x180046a00`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180046b3f`
- `msvcp_win!_Xtime_get_ticks` at `0x180046b3f`

## string_xrefs

- `0x180046c44`: `LastAccessTime`
- `0x180046a3d`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180046ada`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180046bc2`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CloudRequestor::TokenBrokerHandler::SetTokenRefreshTime(__int64 a1, __int128 *a2)
{
  volatile signed __int32 *v4; // rdi
  __int64 v5; // rax
  _QWORD *v7; // r8
  int v8; // esi
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rdi
  int v12; // [rsp+20h] [rbp-29h]
  __int64 *v13; // [rsp+20h] [rbp-29h]
  __int64 v14; // [rsp+48h] [rbp-1h] BYREF
  __int128 v15; // [rsp+50h] [rbp+7h] BYREF
  __int128 *v16; // [rsp+60h] [rbp+17h]
  _QWORD v17[4]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v16 = a2;
  if ( !*(_QWORD *)(a1 + 40) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
      (const char *)0x80070057LL,
      v12);
    v4 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
    if ( !v4 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    goto LABEL_12;
  }
  v15 = 0;
  v5 = *((_QWORD *)a2 + 1);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v15 = *a2;
  Windows::Internal::CloudRequestor::TokenBrokerHandler::GetRefreshTimeRegistryPath(a1, v17, &v15);
  if ( !v17[2] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
      (const char *)0x80070057LL,
      v12);
    std::wstring::_Tidy_deallocate(v17);
    v4 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
    if ( !v4 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
LABEL_12:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    return 2147942487LL;
  }
  v14 = _Xtime_get_ticks() / 10000000;
  v7 = v17;
  if ( v17[3] > 7u )
    v7 = (_QWORD *)v17[0];
  LODWORD(v13) = 983103;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64))(**(_QWORD **)(a1 + 40) + 16LL))(
         *(_QWORD *)(a1 + 40),
         -2147483647,
         v7,
         1);
  if ( v8 < 0 )
  {
    v9 = 280;
    goto LABEL_18;
  }
  v13 = &v14;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64))(**(_QWORD **)(a1 + 40) + 24LL))(
         *(_QWORD *)(a1 + 40),
         0,
         L"LastAccessTime",
         11);
  if ( v8 < 0 )
  {
    v9 = 288;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
      (const char *)(unsigned int)v8,
      (int)v13);
    std::wstring::_Tidy_deallocate(v17);
    v10 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    return (unsigned int)v8;
  }
  std::wstring::_Tidy_deallocate(v17);
  v11 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180046a00  mov     [rsp-8+arg_10], rbx
0x180046a05  push    rbp
0x180046a06  push    rsi
0x180046a07  push    rdi
0x180046a08  lea     rbp, [rsp-47h]
0x180046a0d  sub     rsp, 90h
0x180046a14  mov     rax, cs:__security_cookie
0x180046a1b  xor     rax, rsp
0x180046a1e  mov     [rbp+57h+var_18], rax
0x180046a22  mov     rdi, rdx
0x180046a25  mov     rbx, rcx
0x180046a28  mov     [rbp+57h+var_40], rdx
0x180046a2c  cmp     qword ptr [rcx+28h], 0
0x180046a31  jnz     short loc_180046A97
0x180046a33  mov     rcx, [rbp+5Fh]; this
0x180046a37  mov     r9d, 80070057h; char *
0x180046a3d  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180046a44  mov     edx, 106h; void *
0x180046a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046a4e  nop
0x180046a4f  mov     rdi, [rdi+8]
0x180046a53  test    rdi, rdi
0x180046a56  jz      loc_180046B35
0x180046a5c  or      ebx, 0FFFFFFFFh
0x180046a5f  mov     eax, ebx
0x180046a61  lock xadd [rdi+8], eax
0x180046a66  add     eax, ebx
0x180046a68  jnz     loc_180046B35
0x180046a6e  mov     rax, [rdi]
0x180046a71  mov     rcx, rdi
0x180046a74  mov     rax, [rax]
0x180046a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a7c  mov     eax, ebx
0x180046a7e  lock xadd [rdi+0Ch], eax
0x180046a83  add     eax, ebx
0x180046a85  jnz     loc_180046B35
0x180046a8b  mov     rax, [rdi]
0x180046a8e  mov     rax, [rax+8]
0x180046a92  jmp     loc_180046B2D
0x180046a97  xorps   xmm0, xmm0
0x180046a9a  movdqu  [rbp+57h+var_50], xmm0
0x180046a9f  mov     rax, [rdx+8]
0x180046aa3  test    rax, rax
0x180046aa6  jz      short loc_180046AAC
0x180046aa8  lock inc dword ptr [rax+8]
0x180046aac  mov     rax, [rdx]
0x180046aaf  mov     qword ptr [rbp+57h+var_50], rax
0x180046ab3  mov     rax, [rdx+8]
0x180046ab7  mov     qword ptr [rbp+57h+var_50+8], rax
0x180046abb  lea     r8, [rbp+57h+var_50]
0x180046abf  lea     rdx, [rbp+57h+var_38]
0x180046ac3  call    ?GetRefreshTimeRegistryPath@TokenBrokerHandler@CloudRequestor@Internal@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@6@@Z; Windows::Internal::CloudRequestor::TokenBrokerHandler::GetRefreshTimeRegistryPath(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)
0x180046ac8  nop
0x180046ac9  cmp     [rbp+57h+var_28], 0
0x180046ace  jnz     short loc_180046B3F
0x180046ad0  mov     rcx, [rbp+5Fh]; this
0x180046ad4  mov     r9d, 80070057h; char *
0x180046ada  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180046ae1  mov     edx, 10Ah; void *
0x180046ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046aeb  nop
0x180046aec  lea     rcx, [rbp+57h+var_38]
0x180046af0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046af5  nop
0x180046af6  mov     rdi, [rdi+8]
0x180046afa  test    rdi, rdi
0x180046afd  jz      short loc_180046B35
0x180046aff  or      ebx, 0FFFFFFFFh
0x180046b02  mov     eax, ebx
0x180046b04  lock xadd [rdi+8], eax
0x180046b09  add     eax, ebx
0x180046b0b  jnz     short loc_180046B35
0x180046b0d  mov     rax, [rdi]
0x180046b10  mov     rcx, rdi
0x180046b13  mov     rax, [rax]
0x180046b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b1b  mov     edx, ebx
0x180046b1d  lock xadd [rdi+0Ch], edx
0x180046b22  add     edx, ebx
0x180046b24  jnz     short loc_180046B35
0x180046b26  mov     rdx, [rdi]
0x180046b29  mov     rax, [rdx+8]
0x180046b2d  mov     rcx, rdi
0x180046b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b35  mov     eax, 80070057h
0x180046b3a  jmp     loc_180046CB3
0x180046b3f  call    cs:__imp__Xtime_get_ticks
0x180046b45  mov     rcx, rax
0x180046b48  mov     rax, 0D6BF94D5E57A42BDh
0x180046b52  imul    rcx
0x180046b55  add     rdx, rcx
0x180046b58  sar     rdx, 17h
0x180046b5c  mov     rax, rdx
0x180046b5f  shr     rax, 3Fh
0x180046b63  add     rdx, rax
0x180046b66  mov     [rbp+57h+var_58], rdx
0x180046b6a  mov     [rbp+57h+var_60], 0
0x180046b72  mov     rcx, [rbx+28h]
0x180046b76  mov     rax, [rcx]
0x180046b79  lea     r8, [rbp+57h+var_38]
0x180046b7d  cmp     [rbp+57h+var_20], 7
0x180046b82  cmova   r8, [rbp+57h+var_38]
0x180046b87  mov     [rsp+0A0h+var_70], 0
0x180046b90  lea     rdx, [rbp+57h+var_60]
0x180046b94  mov     [rsp+0A0h+var_78], rdx
0x180046b99  mov     [rsp+0A0h+var_80], 0F003Fh; int
0x180046ba1  mov     rdx, 0FFFFFFFF80000001h
0x180046ba8  mov     r9d, 1
0x180046bae  mov     rax, [rax+10h]
0x180046bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bb7  mov     esi, eax
0x180046bb9  test    eax, eax
0x180046bbb  jns     short loc_180046C26
0x180046bbd  mov     edx, 118h; void *
0x180046bc2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180046bc9  mov     r9d, esi; char *
0x180046bcc  mov     rcx, [rbp+5Fh]; this
0x180046bd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046bd5  nop
0x180046bd6  lea     rcx, [rbp+57h+var_38]
0x180046bda  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046bdf  nop
0x180046be0  mov     rdi, [rdi+8]
0x180046be4  test    rdi, rdi
0x180046be7  jz      short loc_180046C1F
0x180046be9  or      ebx, 0FFFFFFFFh
0x180046bec  mov     eax, ebx
0x180046bee  lock xadd [rdi+8], eax
0x180046bf3  add     eax, ebx
0x180046bf5  jnz     short loc_180046C1F
0x180046bf7  mov     rax, [rdi]
0x180046bfa  mov     rcx, rdi
0x180046bfd  mov     rax, [rax]
0x180046c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c05  mov     eax, ebx
0x180046c07  lock xadd [rdi+0Ch], eax
0x180046c0c  add     eax, ebx
0x180046c0e  jnz     short loc_180046C1F
0x180046c10  mov     rax, [rdi]
0x180046c13  mov     rcx, rdi
0x180046c16  mov     rax, [rax+8]
0x180046c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c1f  mov     eax, esi
0x180046c21  jmp     loc_180046CB3
0x180046c26  mov     rcx, [rbx+28h]
0x180046c2a  mov     rax, [rcx]
0x180046c2d  mov     dword ptr [rsp+0A0h+var_78], 8
0x180046c35  lea     rdx, [rbp+57h+var_58]
0x180046c39  mov     qword ptr [rsp+0A0h+var_80], rdx
0x180046c3e  mov     r9d, 0Bh
0x180046c44  lea     r8, aLastaccesstime; "LastAccessTime"
0x180046c4b  mov     rdx, [rbp+57h+var_60]
0x180046c4f  mov     rax, [rax+18h]
0x180046c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c58  mov     esi, eax
0x180046c5a  test    eax, eax
0x180046c5c  jns     short loc_180046C68
0x180046c5e  mov     edx, 120h
0x180046c63  jmp     loc_180046BC2
0x180046c68  lea     rcx, [rbp+57h+var_38]
0x180046c6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046c71  nop
0x180046c72  mov     rdi, [rdi+8]
0x180046c76  test    rdi, rdi
0x180046c79  jz      short loc_180046CB1
0x180046c7b  or      ebx, 0FFFFFFFFh
0x180046c7e  mov     eax, ebx
0x180046c80  lock xadd [rdi+8], eax
0x180046c85  add     eax, ebx
0x180046c87  jnz     short loc_180046CB1
0x180046c89  mov     rax, [rdi]
0x180046c8c  mov     rcx, rdi
0x180046c8f  mov     rax, [rax]
0x180046c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c97  mov     eax, ebx
0x180046c99  lock xadd [rdi+0Ch], eax
0x180046c9e  add     eax, ebx
0x180046ca0  jnz     short loc_180046CB1
0x180046ca2  mov     rax, [rdi]
0x180046ca5  mov     rcx, rdi
0x180046ca8  mov     rax, [rax+8]
0x180046cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cb1  xor     eax, eax
0x180046cb3  mov     rcx, [rbp+57h+var_18]
0x180046cb7  xor     rcx, rsp; StackCookie
0x180046cba  call    __security_check_cookie
0x180046cbf  mov     rbx, [rsp+0A0h+arg_10]
0x180046cc7  add     rsp, 90h
0x180046cce  pop     rdi
0x180046ccf  pop     rsi
0x180046cd0  pop     rbp
0x180046cd1  retn
```
