# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x180039858`
- end: `0x180039b02`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038998`
- `0x180038bcc`

## callees

- `0x180007dfc`
- `0x180039858`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180039a82`
- `msvcp_win!_Cnd_broadcast` at `0x180039a82`
- `msvcp_win!_Mtx_unlock` at `0x1800399f5`
- `msvcp_win!_Mtx_unlock` at `0x180039a78`
- `msvcp_win!_Mtx_unlock` at `0x1800399f5`
- `msvcp_win!_Mtx_unlock` at `0x180039a78`
- `msvcp_win!_Mtx_lock` at `0x18003998d`
- `msvcp_win!_Mtx_lock` at `0x180039a3b`
- `msvcp_win!_Mtx_lock` at `0x18003998d`
- `msvcp_win!_Mtx_lock` at `0x180039a3b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039a4a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039a67`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039a4a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180039a67`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180039a04`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180039a04`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, __int64 *a2)
{
  volatile signed __int32 *v4; // rdi
  char v5; // r12
  __int64 v6; // rsi
  Concurrency::details::platform *v7; // rcx
  char *v8; // rbx
  struct _Mtx_internal_imp_t *v9; // r14
  __int64 v10; // rsi
  char **v11; // rax
  int result; // eax
  signed __int32 CurrentThreadId; // esi
  signed __int32 v14; // eax
  volatile signed __int32 *v15; // rcx

  v4 = (volatile signed __int32 *)a2[1];
  v5 = 0;
  if ( v4 )
  {
    v6 = *a2;
    _InterlockedIncrement(v4 + 3);
  }
  else
  {
    v4 = 0;
    v6 = 0;
  }
  v8 = (char *)operator new(0xD0u);
  *(_QWORD *)v8 = &Concurrency::details::_RefCounter::`vftable';
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 4) = 3;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_OWORD *)(v8 + 40) = 0;
  *(_OWORD *)(v8 + 56) = 0;
  *(_OWORD *)(v8 + 72) = 0;
  *((_QWORD *)v8 + 11) = 0;
  v9 = (struct _Mtx_internal_imp_t *)(v8 + 96);
  *((_QWORD *)v8 + 12) = 2;
  *(_OWORD *)(v8 + 120) = 0;
  *(_OWORD *)(v8 + 136) = 0;
  *(_OWORD *)(v8 + 152) = 0;
  *((_QWORD *)v8 + 13) = 0;
  *((_QWORD *)v8 + 14) = 0;
  *((_DWORD *)v8 + 42) = -1;
  *((_DWORD *)v8 + 43) = 0;
  v8[176] = 0;
  *((_QWORD *)v8 + 23) = 0;
  *(_QWORD *)v8 = &Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable';
  *((_QWORD *)v8 + 24) = 0;
  *((_QWORD *)v8 + 25) = 0;
  if ( v4 )
  {
    *((_QWORD *)v8 + 24) = v6;
    *((_QWORD *)v8 + 25) = v4;
    _InterlockedIncrement(v4 + 3);
  }
  *(_QWORD *)(a1 + 128) = v8;
  v10 = *(_QWORD *)(a1 + 120);
  _InterlockedExchange((volatile __int32 *)v8 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  *((_QWORD *)v8 + 23) = v10;
  if ( *(_DWORD *)(v10 + 16) )
    goto LABEL_17;
  if ( _Mtx_lock((_Mtx_t)(v10 + 24)) )
    goto LABEL_22;
  if ( *(_DWORD *)(v10 + 100) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v10 + 100) = 2147483646;
    goto LABEL_25;
  }
  if ( *(_DWORD *)(v10 + 16) )
  {
    v5 = 1;
  }
  else
  {
    v11 = (char **)operator new(0x10u);
    *v11 = v8;
    v11[1] = 0;
    if ( *(_QWORD *)(v10 + 104) )
      *(_QWORD *)(*(_QWORD *)(v10 + 112) + 8LL) = v11;
    else
      *(_QWORD *)(v10 + 104) = v11;
    *(_QWORD *)(v10 + 112) = v11;
  }
  result = _Mtx_unlock((_Mtx_t)(v10 + 24));
  if ( v5 )
  {
LABEL_17:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(v7);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v14 )
        CurrentThreadId = v14;
      if ( CurrentThreadId == 2 )
      {
        if ( _Mtx_lock(v9) )
        {
LABEL_22:
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)v8 + 43) == 0x7FFFFFFF )
        {
          *((_DWORD *)v8 + 43) = 2147483646;
LABEL_25:
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v8[176] = 1;
        _Mtx_unlock(v9);
        _Cnd_broadcast((_Cnd_t)(v8 + 24));
      }
    }
    result = _InterlockedDecrement((volatile signed __int32 *)v8 + 2);
    if ( !result )
      result = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  if ( v4 )
  {
    result = _InterlockedDecrement(v4 + 3);
    if ( !result )
      result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  v15 = (volatile signed __int32 *)a2[1];
  if ( v15 )
  {
    result = _InterlockedDecrement(v15 + 3);
    if ( !result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
  return result;
}

```

## disassembly

```asm
0x180039858  mov     rax, rsp
0x18003985b  mov     [rax+18h], rbx
0x18003985f  push    rbp
0x180039860  push    rsi
0x180039861  push    rdi
0x180039862  push    r12
0x180039864  push    r13
0x180039866  push    r14
0x180039868  push    r15
0x18003986a  sub     rsp, 40h
0x18003986e  mov     r15, rdx
0x180039871  mov     rbp, rcx
0x180039874  mov     [rax-40h], rdx
0x180039878  xorps   xmm0, xmm0
0x18003987b  movdqu  xmmword ptr [rax-50h], xmm0
0x180039880  mov     rdi, [rdx+8]
0x180039884  xor     r12d, r12d
0x180039887  test    rdi, rdi
0x18003988a  jz      short loc_18003989D
0x18003988c  mov     rsi, [rdx]
0x18003988f  mov     [rax-50h], rsi
0x180039893  mov     [rax-48h], rdi
0x180039897  lock inc dword ptr [rdi+0Ch]
0x18003989b  jmp     short loc_1800398A7
0x18003989d  mov     rdi, [rsp+78h+var_48]
0x1800398a2  mov     rsi, [rsp+78h+var_50]
0x1800398a7  mov     ecx, 0D0h; Size
0x1800398ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800398b1  mov     rbx, rax
0x1800398b4  mov     [rsp+78h+var_58], rax
0x1800398b9  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x1800398c0  mov     [rbx], rax
0x1800398c3  mov     dword ptr [rbx+8], 1
0x1800398ca  mov     dword ptr [rbx+10h], 3
0x1800398d1  mov     [rbx+18h], r12
0x1800398d5  mov     [rbx+20h], r12
0x1800398d9  xorps   xmm0, xmm0
0x1800398dc  xor     eax, eax
0x1800398de  movups  xmmword ptr [rbx+28h], xmm0
0x1800398e2  movups  xmmword ptr [rbx+38h], xmm0
0x1800398e6  movups  xmmword ptr [rbx+48h], xmm0
0x1800398ea  mov     [rbx+58h], rax
0x1800398ee  lea     r14, [rbx+60h]
0x1800398f2  mov     qword ptr [r14], 2
0x1800398f9  movups  xmmword ptr [r14+18h], xmm0
0x1800398fe  movups  xmmword ptr [r14+28h], xmm0
0x180039903  movups  xmmword ptr [r14+38h], xmm0
0x180039908  mov     [r14+8], r12
0x18003990c  mov     [r14+10h], r12
0x180039910  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180039918  mov     [r14+4Ch], r12d
0x18003991c  mov     [rbx+0B0h], r12b
0x180039923  mov     [rbx+0B8h], r12
0x18003992a  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x180039931  mov     [rbx], rax
0x180039934  mov     [rbx+0C0h], r12
0x18003993b  mov     [rbx+0C8h], r12
0x180039942  test    rdi, rdi
0x180039945  jz      short loc_180039959
0x180039947  mov     [rbx+0C0h], rsi
0x18003994e  mov     [rbx+0C8h], rdi
0x180039955  lock inc dword ptr [rdi+0Ch]
0x180039959  mov     [rbp+80h], rbx
0x180039960  mov     rsi, [rbp+78h]
0x180039964  mov     eax, r12d
0x180039967  xchg    eax, [rbx+10h]
0x18003996a  lock inc dword ptr [rbx+8]
0x18003996e  mov     [rbx+0B8h], rsi
0x180039975  mov     eax, [rsi+10h]
0x180039978  nop
0x180039979  test    eax, eax
0x18003997b  jnz     loc_180039A04
0x180039981  lea     rbp, [rsi+18h]
0x180039985  mov     [rsp+78h+var_58], rbp
0x18003998a  mov     rcx, rbp; _Mtx_t
0x18003998d  call    cs:__imp__Mtx_lock
0x180039993  test    eax, eax
0x180039995  jnz     loc_180039A45
0x18003999b  mov     eax, [rbp+4Ch]
0x18003999e  cmp     eax, 7FFFFFFFh
0x1800399a3  jnz     short loc_1800399AF
0x1800399a5  dec     eax
0x1800399a7  mov     [rbp+4Ch], eax
0x1800399aa  jmp     loc_180039A62
0x1800399af  mov     eax, [rsi+10h]
0x1800399b2  nop
0x1800399b3  test    eax, eax
0x1800399b5  jz      short loc_1800399BC
0x1800399b7  mov     r12b, 1
0x1800399ba  jmp     short loc_1800399F2
0x1800399bc  mov     ecx, 10h; Size
0x1800399c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800399c6  mov     rcx, rax
0x1800399c9  mov     [rsp+78h+var_58], rax
0x1800399ce  mov     [rax], rbx
0x1800399d1  mov     qword ptr [rax+8], 0
0x1800399d9  cmp     qword ptr [rsi+68h], 0
0x1800399de  jnz     short loc_1800399E6
0x1800399e0  mov     [rsi+68h], rax
0x1800399e4  jmp     short loc_1800399EE
0x1800399e6  mov     rax, [rsi+70h]
0x1800399ea  mov     [rax+8], rcx
0x1800399ee  mov     [rsi+70h], rcx
0x1800399f2  mov     rcx, rbp; _Mtx_t
0x1800399f5  call    cs:__imp__Mtx_unlock
0x1800399fb  test    r12b, r12b
0x1800399fe  jz      loc_180039AA7
0x180039a04  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180039a0a  mov     esi, eax
0x180039a0c  xor     eax, eax
0x180039a0e  lock cmpxchg [rbx+10h], esi
0x180039a13  jnz     short loc_180039A88
0x180039a15  mov     rcx, [rbx]
0x180039a18  mov     rax, [rcx+10h]
0x180039a1c  mov     rcx, rbx
0x180039a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a24  mov     eax, esi
0x180039a26  mov     ecx, 3
0x180039a2b  lock cmpxchg [rbx+10h], ecx
0x180039a30  cmovnz  esi, eax
0x180039a33  cmp     esi, 2
0x180039a36  jnz     short loc_180039A88
0x180039a38  mov     rcx, r14; _Mtx_t
0x180039a3b  call    cs:__imp__Mtx_lock
0x180039a41  test    eax, eax
0x180039a43  jz      short loc_180039A51
0x180039a45  mov     ecx, 5
0x180039a4a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180039a50  int     3; Trap to Debugger
0x180039a51  mov     eax, [r14+4Ch]
0x180039a55  cmp     eax, 7FFFFFFFh
0x180039a5a  jnz     short loc_180039A6E
0x180039a5c  dec     eax
0x180039a5e  mov     [r14+4Ch], eax
0x180039a62  mov     ecx, 6
0x180039a67  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180039a6d  int     3; Trap to Debugger
0x180039a6e  mov     byte ptr [rbx+0B0h], 1
0x180039a75  mov     rcx, r14; _Mtx_t
0x180039a78  call    cs:__imp__Mtx_unlock
0x180039a7e  lea     rcx, [rbx+18h]; _Cnd_t
0x180039a82  call    cs:__imp__Cnd_broadcast
0x180039a88  or      esi, 0FFFFFFFFh
0x180039a8b  mov     eax, esi
0x180039a8d  lock xadd [rbx+8], eax
0x180039a92  add     eax, esi
0x180039a94  jnz     short loc_180039AAA
0x180039a96  mov     rax, [rbx]
0x180039a99  mov     rcx, rbx
0x180039a9c  mov     rax, [rax+8]
0x180039aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aa5  jmp     short loc_180039AAA
0x180039aa7  or      esi, 0FFFFFFFFh
0x180039aaa  test    rdi, rdi
0x180039aad  jz      short loc_180039ACA
0x180039aaf  mov     eax, esi
0x180039ab1  lock xadd [rdi+0Ch], eax
0x180039ab6  add     eax, esi
0x180039ab8  jnz     short loc_180039ACA
0x180039aba  mov     rax, [rdi]
0x180039abd  mov     rcx, rdi
0x180039ac0  mov     rax, [rax+8]
0x180039ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ac9  nop
0x180039aca  mov     rcx, [r15+8]
0x180039ace  test    rcx, rcx
0x180039ad1  jz      short loc_180039AEA
0x180039ad3  mov     eax, esi
0x180039ad5  lock xadd [rcx+0Ch], eax
0x180039ada  add     eax, esi
0x180039adc  jnz     short loc_180039AEA
0x180039ade  mov     rax, [rcx]
0x180039ae1  mov     rax, [rax+8]
0x180039ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aea  mov     rbx, [rsp+78h+arg_10]
0x180039af2  add     rsp, 40h
0x180039af6  pop     r15
0x180039af8  pop     r14
0x180039afa  pop     r13
0x180039afc  pop     r12
0x180039afe  pop     rdi
0x180039aff  pop     rsi
0x180039b00  pop     rbp
0x180039b01  retn
```
