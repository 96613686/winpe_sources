# _lambda_3123e5f836e94e335610d7bf7d199c56_$_ResumeCoro$1::operator()

- ea: `0x18000ec20`
- end: `0x18000eef8`
- name: `_lambda_3123e5f836e94e335610d7bf7d199c56_$_ResumeCoro$1::operator()`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180017b10`

## callees

- `0x180004144`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000e23c`
- `0x18000e45c`
- `0x18000ec20`
- `0x18000ef00`
- `0x180018f14`
- `0x18001c7e0`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000edb1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000edb1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000ed01`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000ed01`

## string_xrefs

- `0x18000ed74`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000edef`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall lambda_3123e5f836e94e335610d7bf7d199c56___ResumeCoro_1::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  unsigned __int64 v5; // rdx
  char *v6; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  const struct std::exception_ptr *v10; // rbx
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-C8h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = 0x180000000uLL;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_17;
    case 2:
      v6 = (char *)operator new(0xF0u) + 32;
      *(_QWORD *)(a1 + 24) = v6;
      *((_QWORD *)v6 + 25) = a1 + 352;
      **(_QWORD **)(a1 + 24) = lambda_3d5f3bee0032f150f7b5c906833347cc___ResumeCoro_1::operator();
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL) = 65538;
      v7 = *(_QWORD *)(a1 + 24);
      *(_OWORD *)(v7 - 32) = 0;
      *(_OWORD *)(v7 - 16) = 0;
      v17 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(v17 - 32) = 0;
      *(_BYTE *)(v17 - 24) = 0;
      v8 = (_QWORD *)(v17 - 16);
      *v8 = 0;
      v8[1] = 0;
      __ExceptionPtrCreate((void *)(v17 - 16));
      *(_QWORD *)(a1 + 16) = v7;
      *(_BYTE *)(*(_QWORD *)(a1 + 24) + 192LL) = 0;
      lambda_3d5f3bee0032f150f7b5c906833347cc___ResumeCoro_1::operator()(*(_QWORD *)(a1 + 24));
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 16) - 24LL) )
      {
        *(_WORD *)(a1 + 8) = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(a1 + 16, a1) )
          return;
      }
      goto LABEL_10;
    case 4:
LABEL_10:
      v10 = (const struct std::exception_ptr *)(*(_QWORD *)(a1 + 16) - 16LL);
      if ( __ExceptionPtrToBool(v10) )
      {
        v13 = std::exception_ptr::exception_ptr((std::exception_ptr *)(a1 + 304), v10);
        std::rethrow_exception(v13);
      }
      v14 = *(_QWORD *)(a1 + 16);
      if ( v14 )
      {
        if ( *(_WORD *)(v14 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v12);
        *(_QWORD *)(v14 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD, __int64))v14)(*(_QWORD *)(a1 + 16), v11);
      }
      p9fs::AsyncTask::promise_type::Signal((p9fs::AsyncTask::promise_type *)(a1 - 16));
      goto LABEL_17;
    case 5:
      v9 = *(_QWORD *)(a1 + 16);
      if ( v9 )
      {
        if ( *(_WORD *)(v9 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v9 + 8) |= 1uLL;
        (*(void (**)(void))v9)();
      }
LABEL_17:
      v15 = *(volatile signed __int32 **)(a1 - 8);
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = *(_QWORD *)(a1 + 472);
      if ( v16 )
      {
        LOBYTE(v5) = v16 != a1 + 416;
        (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v16 + 32LL))(v16, v5);
        *(_QWORD *)(a1 + 472) = 0;
      }
      p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 384));
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 360);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 16), 0x1F0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18000ec20  mov     rax, rsp
0x18000ec23  mov     [rax+10h], rbx
0x18000ec27  mov     [rax+18h], rsi
0x18000ec2b  mov     [rax+8], rcx
0x18000ec2f  push    rdi
0x18000ec30  push    r14
0x18000ec32  push    r15
0x18000ec34  sub     rsp, 0D0h
0x18000ec3b  mov     rdi, rcx
0x18000ec3e  mov     [rsp+0E8h+var_B0], rcx
0x18000ec43  movzx   eax, word ptr [rdi+8]
0x18000ec47  mov     [rsp+0E8h+var_B8], ax
0x18000ec4c  mov     r15d, 1
0x18000ec52  add     ax, r15w
0x18000ec56  cmp     ax, 6; switch 7 cases
0x18000ec5a  ja      def_18000EC75; jumptable 000000018000EC75 default case, cases 1,2
0x18000ec60  movsx   rax, ax
0x18000ec64  lea     rdx, cs:180000000h
0x18000ec6b  mov     ecx, ds:(jpt_18000EC75 - 180000000h)[rdx+rax*4]
0x18000ec72  add     rcx, rdx
0x18000ec75  jmp     rcx; switch jump
0x18000ec77  xor     esi, esi; jumptable 000000018000EC75 case 4
0x18000ec79  jmp     loc_18000EE29
0x18000ec7e  mov     ecx, 0F0h; jumptable 000000018000EC75 case 3
0x18000ec83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec88  lea     r14, [rdi+10h]
0x18000ec8c  lea     rcx, [r14+150h]
0x18000ec93  mov     [rsp+0E8h+var_C8], rax
0x18000ec98  add     rax, 20h ; ' '
0x18000ec9c  mov     [rdi+18h], rax
0x18000eca0  mov     [rsp+0E8h+var_C8], rax
0x18000eca5  mov     [rax+0C8h], rcx
0x18000ecac  mov     rax, [rdi+18h]
0x18000ecb0  mov     [rsp+0E8h+var_C8], rax
0x18000ecb5  lea     rcx, _lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1__operator__
0x18000ecbc  mov     [rax], rcx
0x18000ecbf  mov     rax, [rdi+18h]
0x18000ecc3  mov     [rsp+0E8h+var_C8], rax
0x18000ecc8  mov     dword ptr [rax+8], 10002h
0x18000eccf  mov     rbx, [rdi+18h]
0x18000ecd3  mov     [rsp+0E8h+var_C8], rbx
0x18000ecd8  xorps   xmm0, xmm0
0x18000ecdb  movups  xmmword ptr [rbx-20h], xmm0
0x18000ecdf  movups  xmmword ptr [rbx-10h], xmm0
0x18000ece3  mov     rcx, [rdi+18h]
0x18000ece7  mov     [rsp+0E8h+var_C8], rcx
0x18000ecec  xor     esi, esi
0x18000ecee  mov     [rcx-20h], rsi
0x18000ecf2  mov     [rcx-18h], sil
0x18000ecf6  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000ecfa  mov     [rcx], rsi
0x18000ecfd  mov     [rcx+8], rsi
0x18000ed01  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000ed07  nop
0x18000ed08  mov     [r14], rbx
0x18000ed0b  mov     rax, [rdi+18h]
0x18000ed0f  mov     [rsp+0E8h+var_C8], rax
0x18000ed14  xor     ecx, ecx
0x18000ed16  mov     [rax+0C0h], cl
0x18000ed1c  mov     rcx, [rdi+18h]
0x18000ed20  mov     [rsp+0E8h+var_C8], rcx
0x18000ed25  call    _lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1__operator__
0x18000ed2a  nop
0x18000ed2b  mov     rax, [r14]
0x18000ed2e  mov     [rsp+0E8h+var_C0], rax
0x18000ed33  mov     dl, [rax-18h]
0x18000ed36  nop
0x18000ed37  test    dl, dl
0x18000ed39  jnz     short loc_18000EDA1
0x18000ed3b  lea     eax, [rsi+4]
0x18000ed3e  mov     [rdi+8], ax
0x18000ed42  mov     rdx, rdi
0x18000ed45  mov     rcx, r14
0x18000ed48  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x18000ed4d  test    al, al
0x18000ed4f  jz      short loc_18000EDA1
0x18000ed51  jmp     loc_18000EEC2
0x18000ed56  mov     rax, [rdi+10h]; jumptable 000000018000EC75 case 6
0x18000ed5a  mov     [rsp+0E8h+var_C0], rax
0x18000ed5f  xor     esi, esi
0x18000ed61  test    rax, rax
0x18000ed64  jz      short loc_18000ED9A
0x18000ed66  mov     rcx, [rsp+0E8h]; this
0x18000ed6e  cmp     [rax+8], si
0x18000ed72  jz      short loc_18000ED84
0x18000ed74  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000ed7b  lea     edx, [rsi+34h]; void *
0x18000ed7e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ed84  or      [rax+8], r15
0x18000ed88  mov     rax, [rax]
0x18000ed8b  mov     rcx, [rdi+10h]
0x18000ed8f  mov     [rsp+0E8h+var_C0], rcx
0x18000ed94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed99  nop
0x18000ed9a  jmp     loc_18000EE29
0x18000ed9f  xor     esi, esi; jumptable 000000018000EC75 case 5
0x18000eda1  mov     rax, [rdi+10h]
0x18000eda5  mov     [rsp+0E8h+var_C0], rax
0x18000edaa  lea     rbx, [rax-10h]
0x18000edae  mov     rcx, rbx
0x18000edb1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000edb7  test    al, al
0x18000edb9  jz      short loc_18000EDD3
0x18000edbb  lea     rcx, [rdi+130h]; this
0x18000edc2  mov     rdx, rbx; struct std::exception_ptr *
0x18000edc5  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18000edca  mov     rcx, rax
0x18000edcd  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18000edd3  mov     rax, [rdi+10h]
0x18000edd7  mov     [rsp+0E8h+var_C0], rax
0x18000eddc  test    rax, rax
0x18000eddf  jz      short loc_18000EE16
0x18000ede1  mov     rcx, [rsp+0E8h]; this
0x18000ede9  cmp     [rax+8], si
0x18000eded  jz      short loc_18000EE01
0x18000edef  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000edf6  mov     edx, 34h ; '4'; void *
0x18000edfb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ee01  or      [rax+8], r15
0x18000ee05  mov     rax, [rax]
0x18000ee08  mov     rcx, [rdi+10h]
0x18000ee0c  mov     [rsp+0E8h+var_C0], rcx
0x18000ee11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee16  lea     rcx, [rdi-10h]; this
0x18000ee1a  call    ?Signal@promise_type@AsyncTask@p9fs@@AEAAXXZ; p9fs::AsyncTask::promise_type::Signal(void)
0x18000ee1f  nop
0x18000ee20  jmp     short loc_18000EE29
0x18000ee22  mov     rdi, [rsp+0E8h+var_B0]
0x18000ee27  xor     esi, esi; jumptable 000000018000EC75 case 0
0x18000ee29  mov     rbx, [rdi-8]
0x18000ee2d  test    rbx, rbx
0x18000ee30  jz      short loc_18000EE6D
0x18000ee32  or      r15d, 0FFFFFFFFh
0x18000ee36  mov     eax, r15d
0x18000ee39  lock xadd [rbx+8], eax
0x18000ee3e  add     eax, r15d
0x18000ee41  jnz     short loc_18000EE6D
0x18000ee43  mov     rax, [rbx]
0x18000ee46  mov     rcx, rbx
0x18000ee49  mov     rax, [rax]
0x18000ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee51  mov     eax, r15d
0x18000ee54  lock xadd [rbx+0Ch], eax
0x18000ee59  add     eax, r15d
0x18000ee5c  jnz     short loc_18000EE6D
0x18000ee5e  mov     rax, [rbx]
0x18000ee61  mov     rcx, rbx
0x18000ee64  mov     rax, [rax+8]
0x18000ee68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee6d  lea     rbx, [rdi+1A0h]
0x18000ee74  mov     rcx, [rbx+38h]
0x18000ee78  test    rcx, rcx
0x18000ee7b  jz      short loc_18000EE93
0x18000ee7d  mov     rax, [rcx]
0x18000ee80  cmp     rcx, rbx
0x18000ee83  setnz   dl
0x18000ee86  mov     rax, [rax+20h]
0x18000ee8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee8f  mov     [rbx+38h], rsi
0x18000ee93  lea     rcx, [rdi+180h]; this
0x18000ee9a  call    ??1RequestTracker@Handler@p9fs@@QEAA@XZ; p9fs::Handler::RequestTracker::~RequestTracker(void)
0x18000ee9f  lea     rcx, [rdi+168h]
0x18000eea6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000eeab  cmp     [rdi+0Ah], si
0x18000eeaf  jz      short loc_18000EEC2
0x18000eeb1  mov     edx, 1F0h; unsigned __int64
0x18000eeb6  lea     rcx, [rdi-10h]; void *
0x18000eeba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eebf  jmp     short loc_18000EEC2
0x18000eec1  int     3; Trap to Debugger
0x18000eec2  lea     r11, [rsp+0E8h+var_18]
0x18000eeca  mov     rbx, [r11+28h]
0x18000eece  mov     rsi, [r11+30h]
0x18000eed2  mov     rsp, r11
0x18000eed5  pop     r15
0x18000eed7  pop     r14
0x18000eed9  pop     rdi
0x18000eeda  retn
```
