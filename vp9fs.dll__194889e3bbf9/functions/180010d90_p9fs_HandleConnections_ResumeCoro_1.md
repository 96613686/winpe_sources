# p9fs::HandleConnections$_ResumeCoro$1

- ea: `0x180010d90`
- end: `0x1800114c0`
- name: `p9fs::HandleConnections$_ResumeCoro$1`
- size: `1840`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002753c`

## callees

- `0x180002c6c`
- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000c4bc`
- `0x18000cd74`
- `0x18000dbd8`
- `0x18000fddc`
- `0x180010d90`
- `0x180016684`
- `0x180018f14`
- `0x18001bbc0`
- `0x18001c7c4`
- `0x18001c7e0`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010e7e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180011399`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180010e7e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180011399`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800112de`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800112de`

## string_xrefs

- `0x180010e3f`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180010ec8`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18001135c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x1800113d7`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall p9fs::HandleConnections__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  const char *v8; // r9
  __int64 v9; // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // r12
  __int64 v11; // rax
  _DWORD *v12; // rcx
  _DWORD *v13; // rcx
  volatile signed __int64 *v14; // rbx
  _DWORD *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  _DWORD *v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rbx
  char *v25; // rax
  __int64 v26; // rbx
  _QWORD *v27; // rcx
  __int64 v28; // rax
  const struct std::exception_ptr *v29; // rbx
  const char *v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  volatile signed __int32 *v33; // rbx
  __int64 v34; // [rsp+38h] [rbp-1B0h]
  unsigned __int64 v35; // [rsp+40h] [rbp-1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_47;
    case 2:
      *(_DWORD *)(a1 + 128) = 0;
      *(_QWORD *)(a1 + 16) = 0;
      goto LABEL_26;
    case 4:
      goto LABEL_8;
    case 5:
      v6 = *(_QWORD *)(a1 + 32);
      if ( v6 )
      {
        if ( *(_WORD *)(v6 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v6 + 8) |= 1uLL;
        (*(void (**)(void))v6)();
      }
      goto LABEL_47;
    case 6:
      goto LABEL_40;
    case 7:
      v28 = *(_QWORD *)(a1 + 88);
      if ( v28 )
      {
        if ( *(_WORD *)(v28 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v28 + 8) |= 1uLL;
        (*(void (**)(void))v28)();
      }
      goto LABEL_47;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
LABEL_8:
    v7 = **(_QWORD **)(a1 + 3296);
    if ( __ExceptionPtrToBool((const void *)(v7 - 32)) )
    {
      v9 = std::exception_ptr::exception_ptr(
             (std::exception_ptr *)(a1 + 136),
             (const struct std::exception_ptr *)(v7 - 32));
      std::rethrow_exception(v9);
    }
    v10 = *(void (__fastcall ****)(_QWORD, __int64))(v7 - 16);
    *(_QWORD *)(v7 - 16) = 0;
    *(_QWORD *)(a1 + 24) = v10;
    v11 = *(_QWORD *)(a1 + 32);
    if ( v11 )
    {
      if ( *(_WORD *)(v11 + 8) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
          v8);
      *(_QWORD *)(v11 + 8) |= 1uLL;
      (*(void (**)(void))v11)();
      *(_QWORD *)(a1 + 32) = 0;
    }
    v12 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
    if ( *v12 > 5u )
      tlgWriteTransfer_EventWriteTransfer((int)v12, (int)&byte_180039235, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 152));
    if ( !v10 )
      break;
    v14 = (volatile signed __int64 *)(a1 + 16);
    v35 = *(_QWORD *)(a1 + 16);
    if ( v35 < (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 3328) + 16LL))(*(_QWORD *)(a1 + 3328)) )
    {
      _InterlockedAdd64(v14, 1u);
      Plan9TraceLoggingProvider::ClientConnected<std::atomic<unsigned __int64> &>(a1 + 16);
      v16 = *(_QWORD *)(a1 + 3344);
      _InterlockedAdd64((volatile signed __int64 *)(v16 + 8), 1u);
      v17 = *(_QWORD *)(a1 + 3328);
      v18 = *(_QWORD *)(a1 + 3336);
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 80) = 0;
      *(_QWORD *)(a1 + 56) = v14;
      *(_QWORD *)(a1 + 64) = v17;
      *(_QWORD *)(a1 + 72) = v18;
      *(_BYTE *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 248) = v10;
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 256) = v16;
      *(_QWORD *)(a1 + 264) = v14;
      *(_QWORD *)(a1 + 272) = v17;
      *(_QWORD *)(a1 + 280) = v18;
      *(_QWORD *)(a1 + 296) = a1 + 248;
      v19 = operator new(0xAD0u);
      *(_QWORD *)(a1 + 312) = v19;
      v19[339] = a1 + 288;
      v20 = *(_QWORD *)(a1 + 248);
      *(_QWORD *)(a1 + 248) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 312) + 2720LL) = v20;
      v21 = *(_QWORD *)(a1 + 256);
      *(_QWORD *)(a1 + 256) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 312) + 2728LL) = v21;
      *(_QWORD *)(*(_QWORD *)(a1 + 312) + 2736LL) = *(_QWORD *)(a1 + 264);
      *(_QWORD *)(*(_QWORD *)(a1 + 312) + 2744LL) = *(_QWORD *)(a1 + 272);
      *(_QWORD *)(*(_QWORD *)(a1 + 312) + 2752LL) = *(_QWORD *)(a1 + 280);
      **(_QWORD **)(a1 + 312) = lambda_6d29b35e36e5bb6c3c59788efe28ffe7___ResumeCoro_1::operator();
      *(_DWORD *)(*(_QWORD *)(a1 + 312) + 8LL) = 65538;
      p9fs::Scheduler::Schedule(&p9fs::g_Scheduler);
      *(_BYTE *)(*(_QWORD *)(a1 + 312) + 2704LL) = 0;
      lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_::__lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_(a1 + 248);
      lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_::__lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_(a1 + 40);
    }
    else
    {
      v15 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
      if ( *v15 > 2u )
        tlgWriteTransfer_EventWriteTransfer(
          (int)v15,
          (int)&byte_18003915B,
          0,
          0,
          2u,
          (PEVENT_DATA_DESCRIPTOR)(a1 + 216));
      (**v10)(v10, 1);
    }
    *(_DWORD *)(a1 + 128) |= 3u;
LABEL_26:
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 3336) + 88LL) )
      goto LABEL_32;
    v22 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
    if ( *v22 > 5u )
      tlgWriteTransfer_EventWriteTransfer((int)v22, (int)&qword_180038750, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 96));
    v23 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 3320) + 8LL))(
                      *(_QWORD *)(a1 + 3320),
                      a1 + 32,
                      *(_QWORD *)(a1 + 3336));
    *(_QWORD *)(a1 + 3296) = v23;
    if ( !*(_BYTE *)(*v23 - 40LL) )
    {
      *(_WORD *)(a1 + 8) = 4;
      if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v23, a1) )
        return;
    }
  }
  v13 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
  if ( *v13 > 4u )
    tlgWriteTransfer_EventWriteTransfer((int)v13, (int)&byte_1800392AD, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 184));
  p9fs::CancelToken::Cancel(*(p9fs::CancelToken **)(a1 + 3336));
LABEL_32:
  v24 = *(_QWORD *)(a1 + 3344);
  v25 = (char *)operator new(0x70u) + 32;
  *(_QWORD *)(a1 + 304) = v25;
  *((_QWORD *)v25 + 9) = v24;
  **(_QWORD **)(a1 + 304) = p9fs::WaitGroup::Wait__ResumeCoro_1;
  *(_DWORD *)(*(_QWORD *)(a1 + 304) + 8LL) = 65538;
  v26 = *(_QWORD *)(a1 + 304);
  *(_OWORD *)(v26 - 32) = 0;
  *(_OWORD *)(v26 - 16) = 0;
  v34 = *(_QWORD *)(a1 + 304);
  *(_QWORD *)(v34 - 32) = 0;
  *(_BYTE *)(v34 - 24) = 0;
  v27 = (_QWORD *)(v34 - 16);
  *v27 = 0;
  v27[1] = 0;
  __ExceptionPtrCreate((void *)(v34 - 16));
  *(_QWORD *)(a1 + 88) = v26;
  *(_BYTE *)(*(_QWORD *)(a1 + 304) + 64LL) = 0;
  p9fs::WaitGroup::Wait__ResumeCoro_1();
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 88) - 24LL)
    || (*(_WORD *)(a1 + 8) = 6, !(unsigned __int8)p9fs::Task<void>::await_suspend(a1 + 88, a1)) )
  {
LABEL_40:
    v29 = (const struct std::exception_ptr *)(*(_QWORD *)(a1 + 88) - 16LL);
    if ( __ExceptionPtrToBool(v29) )
    {
      v31 = std::exception_ptr::exception_ptr((std::exception_ptr *)(a1 + 3264), v29);
      std::rethrow_exception(v31);
    }
    v32 = *(_QWORD *)(a1 + 88);
    if ( v32 )
    {
      if ( *(_WORD *)(v32 + 8) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
          v30);
      *(_QWORD *)(v32 + 8) |= 1uLL;
      (*(void (**)(void))v32)();
    }
    p9fs::AsyncTask::promise_type::Signal((p9fs::AsyncTask::promise_type *)(a1 - 16));
LABEL_47:
    v33 = *(volatile signed __int32 **)(a1 - 8);
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( !_InterlockedDecrement(v33 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    if ( *(_WORD *)(a1 + 10) )
      operator delete((void *)(a1 - 16), 0xD30u);
  }
}

```

## disassembly

```asm
0x180010d90  mov     r11, rsp
0x180010d93  mov     [r11+10h], rbx
0x180010d97  mov     [r11+18h], rsi
0x180010d9b  mov     [r11+8], rcx
0x180010d9f  push    rdi
0x180010da0  push    r12
0x180010da2  push    r13
0x180010da4  push    r14
0x180010da6  push    r15
0x180010da8  sub     rsp, 1C0h
0x180010daf  mov     rax, cs:__security_cookie
0x180010db6  xor     rax, rsp
0x180010db9  mov     [rsp+1E8h+var_30], rax
0x180010dc1  mov     rdi, rcx
0x180010dc4  mov     [rsp+1E8h+var_1A0], rcx
0x180010dc9  mov     r13, rcx
0x180010dcc  mov     [rsp+1E8h+var_1B0], rcx
0x180010dd1  movzx   eax, word ptr [rdi+8]
0x180010dd5  mov     [rsp+1E8h+var_198], ax
0x180010dda  mov     r14d, 1
0x180010de0  add     ax, r14w
0x180010de4  cmp     ax, 8; switch 9 cases
0x180010de8  ja      def_180010E03; jumptable 0000000180010E03 default case, cases 1,2
0x180010dee  movsx   rax, ax
0x180010df2  lea     rdx, cs:180000000h
0x180010df9  mov     ecx, ds:(jpt_180010E03 - 180000000h)[rdx+rax*4]
0x180010e00  add     rcx, rdx
0x180010e03  jmp     rcx; switch jump
0x180010e05  xor     esi, esi; jumptable 0000000180010E03 case 4
0x180010e07  jmp     loc_180011411
0x180010e0c  xor     esi, esi; jumptable 0000000180010E03 case 3
0x180010e0e  mov     [rdi+80h], esi
0x180010e14  mov     [rdi+10h], rsi
0x180010e18  lea     r15d, [rsi+2]
0x180010e1c  jmp     loc_1800111AB
0x180010e21  mov     rax, [rdi+20h]; jumptable 0000000180010E03 case 6
0x180010e25  mov     [rsp+1E8h+var_190], rax
0x180010e2a  xor     esi, esi
0x180010e2c  test    rax, rax
0x180010e2f  jz      short loc_180010E65
0x180010e31  mov     rcx, [rsp+1E8h]; this
0x180010e39  cmp     [rax+8], si
0x180010e3d  jz      short loc_180010E4F
0x180010e3f  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180010e46  lea     edx, [rsi+34h]; void *
0x180010e49  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010e4f  or      [rax+8], r14
0x180010e53  mov     rax, [rax]
0x180010e56  mov     rcx, [rdi+20h]
0x180010e5a  mov     [rsp+1E8h+var_190], rcx
0x180010e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e64  nop
0x180010e65  jmp     loc_180011411
0x180010e6a  xor     esi, esi; jumptable 0000000180010E03 case 5
0x180010e6c  lea     r15d, [rsi+2]
0x180010e70  mov     rbx, [rdi+0CE0h]
0x180010e77  mov     rbx, [rbx]
0x180010e7a  lea     rcx, [rbx-20h]
0x180010e7e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180010e84  test    al, al
0x180010e86  jz      short loc_180010EA0
0x180010e88  lea     rcx, [rdi+88h]; this
0x180010e8f  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x180010e93  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180010e98  mov     rcx, rax
0x180010e9b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180010ea0  mov     r12, [rbx-10h]
0x180010ea4  mov     [rbx-10h], rsi
0x180010ea8  mov     [rdi+18h], r12
0x180010eac  mov     rax, [rdi+20h]
0x180010eb0  mov     [rsp+1E8h+var_190], rax
0x180010eb5  test    rax, rax
0x180010eb8  jz      short loc_180010EF3
0x180010eba  mov     rcx, [rsp+1E8h]; this
0x180010ec2  cmp     [rax+8], si
0x180010ec6  jz      short loc_180010EDA
0x180010ec8  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180010ecf  mov     edx, 34h ; '4'; void *
0x180010ed4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010eda  or      [rax+8], r14
0x180010ede  mov     rax, [rax]
0x180010ee1  mov     rcx, [rdi+20h]
0x180010ee5  mov     [rsp+1E8h+var_190], rcx
0x180010eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eef  mov     [rdi+20h], rsi
0x180010ef3  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; Plan9TraceLoggingProvider::Instance(void)
0x180010ef8  mov     rcx, [rax+8]; int
0x180010efc  mov     eax, [rcx]
0x180010efe  cmp     eax, 5
0x180010f01  jbe     short loc_180010F26
0x180010f03  lea     rax, [rdi+98h]
0x180010f0a  mov     [rsp+1E8h+var_1C0], rax; PEVENT_DATA_DESCRIPTOR
0x180010f0f  mov     [rsp+1E8h+var_1C8], r15d; ULONG
0x180010f14  xor     r9d, r9d; int
0x180010f17  xor     r8d, r8d; int
0x180010f1a  lea     rdx, byte_180039235; int
0x180010f21  call    _tlgWriteTransfer_EventWriteTransfer
0x180010f26  test    r12, r12
0x180010f29  jnz     short loc_180010F70
0x180010f2b  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; Plan9TraceLoggingProvider::Instance(void)
0x180010f30  mov     rcx, [rax+8]; int
0x180010f34  mov     eax, [rcx]
0x180010f36  cmp     eax, 4
0x180010f39  jbe     short loc_180010F5E
0x180010f3b  lea     rax, [rdi+0B8h]
0x180010f42  mov     [rsp+1E8h+var_1C0], rax; PEVENT_DATA_DESCRIPTOR
0x180010f47  mov     [rsp+1E8h+var_1C8], r15d; ULONG
0x180010f4c  xor     r9d, r9d; int
0x180010f4f  xor     r8d, r8d; int
0x180010f52  lea     rdx, byte_1800392AD; int
0x180010f59  call    _tlgWriteTransfer_EventWriteTransfer
0x180010f5e  mov     rcx, [rdi+0D08h]; this
0x180010f65  call    ?Cancel@CancelToken@p9fs@@QEAAXXZ; p9fs::CancelToken::Cancel(void)
0x180010f6a  nop
0x180010f6b  jmp     loc_180011245
0x180010f70  lea     rbx, [rdi+10h]
0x180010f74  mov     rax, [rbx]
0x180010f77  mov     [rsp+1E8h+var_158], rax
0x180010f7f  mov     rax, [rsp+1E8h+var_158]
0x180010f87  mov     [rsp+1E8h+var_1A8], rax
0x180010f8c  nop
0x180010f8d  mov     rcx, [rbx+0CF0h]
0x180010f94  mov     rax, [rcx]
0x180010f97  mov     rax, [rax+10h]
0x180010f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fa0  cmp     [rsp+1E8h+var_1A8], rax
0x180010fa5  jb      short loc_180010FF1
0x180010fa7  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; Plan9TraceLoggingProvider::Instance(void)
0x180010fac  mov     rcx, [rax+8]; int
0x180010fb0  mov     eax, [rcx]
0x180010fb2  cmp     eax, r15d
0x180010fb5  jbe     short loc_180010FDA
0x180010fb7  lea     rax, [rdi+0D8h]
0x180010fbe  mov     [rsp+1E8h+var_1C0], rax; PEVENT_DATA_DESCRIPTOR
0x180010fc3  mov     [rsp+1E8h+var_1C8], r15d; ULONG
0x180010fc8  xor     r9d, r9d; int
0x180010fcb  xor     r8d, r8d; int
0x180010fce  lea     rdx, byte_18003915B; int
0x180010fd5  call    _tlgWriteTransfer_EventWriteTransfer
0x180010fda  mov     rax, [r12]
0x180010fde  mov     edx, r14d
0x180010fe1  mov     rcx, r12
0x180010fe4  mov     rax, [rax]
0x180010fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fec  jmp     loc_1800111A4
0x180010ff1  lock add [rbx], r14
0x180010ff5  mov     rcx, rbx
0x180010ff8  call    ??$ClientConnected@AEAU?$atomic@_K@std@@@Plan9TraceLoggingProvider@@SAXAEAU?$atomic@_K@std@@@Z; Plan9TraceLoggingProvider::ClientConnected<std::atomic<unsigned __int64> &>(std::atomic<unsigned __int64> &)
0x180010ffd  mov     rcx, [rdi+0D10h]
0x180011004  lock add [rcx+8], r14
0x180011009  mov     rax, [rbx+0CF0h]
0x180011010  mov     rdx, [rdi+0D08h]
0x180011017  mov     [rdi+18h], rsi
0x18001101b  mov     [rdi+50h], rsi
0x18001101f  mov     [rdi+38h], rbx
0x180011023  mov     [rdi+40h], rax
0x180011027  mov     [rdi+48h], rdx
0x18001102b  mov     [rdi+120h], sil
0x180011032  lea     r8, [rdi+0F8h]
0x180011039  mov     [rdi+28h], rsi
0x18001103d  mov     [r8], r12
0x180011040  mov     [rdi+30h], rsi
0x180011044  mov     [rdi+100h], rcx
0x18001104b  mov     [rdi+108h], rbx
0x180011052  mov     [rdi+110h], rax
0x180011059  mov     [rdi+118h], rdx
0x180011060  mov     [rdi+128h], r8
0x180011067  mov     ecx, 0AD0h; Size
0x18001106c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011071  mov     rcx, rax
0x180011074  mov     [rdi+138h], rax
0x18001107b  mov     [rsp+1E8h+var_1B8], rax
0x180011080  lea     rax, [rdi+120h]
0x180011087  mov     [rcx+0A98h], rax
0x18001108e  lea     rbx, [rdi+0F8h]
0x180011095  mov     rcx, [rbx]
0x180011098  mov     [rsp+1E8h+var_180], rcx
0x18001109d  mov     [rbx], rsi
0x1800110a0  mov     rax, [rdi+138h]
0x1800110a7  mov     [rsp+1E8h+var_1B8], rax
0x1800110ac  mov     [rax+0AA0h], rcx
0x1800110b3  mov     rcx, [rdi+100h]
0x1800110ba  mov     [rsp+1E8h+var_178], rcx
0x1800110bf  mov     [rdi+100h], rsi
0x1800110c6  mov     rax, [rdi+138h]
0x1800110cd  mov     [rsp+1E8h+var_1B8], rax
0x1800110d2  mov     [rax+0AA8h], rcx
0x1800110d9  mov     rcx, [rdi+138h]
0x1800110e0  mov     [rsp+1E8h+var_1B8], rcx
0x1800110e5  mov     rax, [rdi+108h]
0x1800110ec  mov     [rsp+1E8h+var_170], rax
0x1800110f1  mov     [rcx+0AB0h], rax
0x1800110f8  mov     rcx, [rdi+138h]
0x1800110ff  mov     [rsp+1E8h+var_1B8], rcx
0x180011104  mov     rax, [rdi+110h]
0x18001110b  mov     [rsp+1E8h+var_168], rax
0x180011113  mov     [rcx+0AB8h], rax
0x18001111a  mov     rcx, [rdi+138h]
0x180011121  mov     [rsp+1E8h+var_1B8], rcx
0x180011126  mov     rax, [rdi+118h]
0x18001112d  mov     [rsp+1E8h+var_160], rax
0x180011135  mov     [rcx+0AC0h], rax
0x18001113c  mov     rax, [rdi+138h]
0x180011143  mov     [rsp+1E8h+var_1B8], rax
0x180011148  lea     rcx, _lambda_6d29b35e36e5bb6c3c59788efe28ffe7_$_ResumeCoro$1__operator__
0x18001114f  mov     [rax], rcx
0x180011152  mov     rax, [rdi+138h]
0x180011159  mov     [rsp+1E8h+var_1B8], rax
0x18001115e  mov     dword ptr [rax+8], 10002h
0x180011165  mov     rdx, [rdi+138h]
0x18001116c  mov     [rsp+1E8h+var_1B8], rdx
0x180011171  lea     rcx, ?g_Scheduler@p9fs@@3VScheduler@1@A; _Smtx_t *
0x180011178  call    ?Schedule@Scheduler@p9fs@@QEAAXU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Scheduler::Schedule(std::experimental::coroutine_handle<void>)
0x18001117d  mov     rax, [rdi+138h]
0x180011184  mov     [rsp+1E8h+var_1B8], rax
0x180011189  xor     ecx, ecx
0x18001118b  mov     [rax+0A90h], cl
0x180011191  mov     rcx, rbx
0x180011194  call    _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_____lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_
0x180011199  nop
0x18001119a  lea     rcx, [rdi+28h]
0x18001119e  call    _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_____lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_
0x1800111a3  nop
0x1800111a4  or      dword ptr [rdi+80h], 3
0x1800111ab  mov     r12d, 4
0x1800111b1  mov     rax, [rdi+0D08h]
0x1800111b8  mov     cl, [rax+58h]
0x1800111bb  nop
0x1800111bc  test    cl, cl
0x1800111be  jnz     loc_180011245
0x1800111c4  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; Plan9TraceLoggingProvider::Instance(void)
0x1800111c9  mov     rcx, [rax+8]; int
0x1800111cd  mov     eax, [rcx]
0x1800111cf  cmp     eax, 5
0x1800111d2  jbe     short loc_1800111F4
0x1800111d4  lea     rax, [rdi+60h]
0x1800111d8  mov     [rsp+1E8h+var_1C0], rax; PEVENT_DATA_DESCRIPTOR
0x1800111dd  mov     [rsp+1E8h+var_1C8], r15d; ULONG
0x1800111e2  xor     r9d, r9d; int
0x1800111e5  xor     r8d, r8d; int
0x1800111e8  lea     rdx, qword_180038750; int
0x1800111ef  call    _tlgWriteTransfer_EventWriteTransfer
0x1800111f4  mov     rcx, [rdi+0CF8h]
0x1800111fb  mov     rax, [rcx]
0x1800111fe  lea     rdx, [rdi+20h]
0x180011202  mov     r8, [rdi+0D08h]
0x180011209  mov     rax, [rax+8]
0x18001120d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011212  mov     rcx, rax
0x180011215  mov     [rdi+0CE0h], rax
0x18001121c  mov     rax, [rax]
0x18001121f  mov     dl, [rax-28h]
0x180011222  nop
0x180011223  test    dl, dl
0x180011225  jnz     loc_180010E70
0x18001122b  mov     [rdi+8], r12w
0x180011230  mov     rdx, rdi
0x180011233  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180011238  test    al, al
0x18001123a  jz      loc_180010E70
0x180011240  jmp     loc_18001146C
0x180011245  jmp     short loc_180011255
0x180011247  xor     esi, esi
0x180011249  lea     r14d, [rsi+1]
0x18001124d  mov     r13, [rsp+1E8h+var_1B0]
0x180011252  mov     rdi, r13
0x180011255  mov     rbx, [rdi+0D10h]
0x18001125c  mov     ecx, 70h ; 'p'; Size
0x180011261  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011266  mov     [rsp+1E8h+var_1B0], rax
0x18001126b  add     rax, 20h ; ' '
0x18001126f  mov     [rdi+130h], rax
0x180011276  mov     [rsp+1E8h+var_1B0], rax
0x18001127b  mov     [rax+48h], rbx
0x18001127f  mov     rax, [rdi+130h]
0x180011286  mov     [rsp+1E8h+var_1B0], rax
0x18001128b  lea     rcx, p9fs__WaitGroup__Wait$_ResumeCoro$1
0x180011292  mov     [rax], rcx
0x180011295  mov     rax, [rdi+130h]
0x18001129c  mov     [rsp+1E8h+var_1B0], rax
0x1800112a1  mov     dword ptr [rax+8], 10002h
0x1800112a8  mov     rbx, [rdi+130h]
0x1800112af  mov     [rsp+1E8h+var_1B0], rbx
0x1800112b4  xorps   xmm0, xmm0
0x1800112b7  movups  xmmword ptr [rbx-20h], xmm0
0x1800112bb  movups  xmmword ptr [rbx-10h], xmm0
0x1800112bf  mov     rcx, [rdi+130h]
0x1800112c6  mov     [rsp+1E8h+var_1B0], rcx
0x1800112cb  mov     [rcx-20h], rsi
0x1800112cf  mov     [rcx-18h], sil
0x1800112d3  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800112d7  mov     [rcx], rsi
0x1800112da  mov     [rcx+8], rsi
0x1800112de  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800112e4  nop
0x1800112e5  lea     r15, [rdi+58h]
0x1800112e9  mov     [r15], rbx
0x1800112ec  mov     rax, [rdi+130h]
0x1800112f3  mov     [rsp+1E8h+var_1B0], rax
0x1800112f8  xor     ecx, ecx
  ... truncated ...
```
