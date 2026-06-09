# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x1800279b8`
- end: `0x180027ae8`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `304`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002752c`
- `0x180027628`
- `0x1800276dc`

## callees

- `0x18001188c`
- `0x1800277ac`
- `0x1800279b8`
- `0x180028b28`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180027abe`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180027abe`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027acb`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027acb`

## pseudocode

```c
__int64 __fastcall mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct mi::MiCallbacks *a7)
{
  __int64 (__fastcall ***v11)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v12)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v13)(_QWORD, __int64); // rcx

  mi::ManualResetEvent::ManualResetEvent((mi::ManualResetEvent *)a1);
  *(_QWORD *)(a1 + 72) = 0;
  v11 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a4 + 56);
  if ( v11 )
    *(_QWORD *)(a1 + 72) = (**v11)(v11, a1 + 16);
  *(_QWORD *)(a1 + 136) = 0;
  v12 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a5 + 56);
  if ( v12 )
    *(_QWORD *)(a1 + 136) = (**v12)(v12, a1 + 80);
  *(_QWORD *)(a1 + 200) = 0;
  v13 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a6 + 56);
  if ( v13 )
    *(_QWORD *)(a1 + 200) = (**v13)(v13, a1 + 144);
  mi::MiCallbacks::MiCallbacks((mi::MiCallbacks *)(a1 + 208), a7);
  std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(a1 + 400, a2);
  std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(a1 + 416, a3);
  *(_BYTE *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  __ExceptionPtrCreate((void *)(a1 + 440));
  InitializeSRWLock((PSRWLOCK)(a1 + 456));
  return a1;
}

```

## disassembly

```asm
0x1800279b8  mov     [rsp+arg_8], rbx
0x1800279bd  mov     [rsp+arg_10], rbp
0x1800279c2  mov     [rsp+arg_0], rcx
0x1800279c7  push    rsi
0x1800279c8  push    rdi
0x1800279c9  push    r14
0x1800279cb  sub     rsp, 20h
0x1800279cf  mov     rbx, r9
0x1800279d2  mov     rbp, r8
0x1800279d5  mov     r14, rdx
0x1800279d8  mov     rdi, rcx
0x1800279db  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x1800279e0  nop
0x1800279e1  lea     rsi, [rdi+10h]
0x1800279e5  mov     [rsp+38h+arg_18], rsi
0x1800279ea  mov     qword ptr [rsi+38h], 0
0x1800279f2  mov     rcx, [rbx+38h]
0x1800279f6  test    rcx, rcx
0x1800279f9  jz      short loc_180027A0D
0x1800279fb  mov     rax, [rcx]
0x1800279fe  mov     rdx, rsi
0x180027a01  mov     rax, [rax]
0x180027a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a09  mov     [rsi+38h], rax
0x180027a0d  lea     rbx, [rdi+50h]
0x180027a11  mov     [rsp+38h+arg_18], rbx
0x180027a16  mov     qword ptr [rbx+38h], 0
0x180027a1e  mov     rax, [rsp+38h+arg_20]
0x180027a23  mov     rcx, [rax+38h]
0x180027a27  test    rcx, rcx
0x180027a2a  jz      short loc_180027A3E
0x180027a2c  mov     rax, [rcx]
0x180027a2f  mov     rdx, rbx
0x180027a32  mov     rax, [rax]
0x180027a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a3a  mov     [rbx+38h], rax
0x180027a3e  lea     rbx, [rdi+90h]
0x180027a45  mov     [rsp+38h+arg_20], rbx
0x180027a4a  mov     qword ptr [rbx+38h], 0
0x180027a52  mov     rax, [rsp+38h+arg_28]
0x180027a57  mov     rcx, [rax+38h]
0x180027a5b  test    rcx, rcx
0x180027a5e  jz      short loc_180027A72
0x180027a60  mov     rax, [rcx]
0x180027a63  mov     rdx, rbx
0x180027a66  mov     rax, [rax]
0x180027a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a6e  mov     [rbx+38h], rax
0x180027a72  lea     rcx, [rdi+0D0h]; this
0x180027a79  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x180027a7e  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x180027a83  lea     rcx, [rdi+190h]
0x180027a8a  mov     rdx, r14
0x180027a8d  call    ??0?$shared_ptr@VMiApplication@mi@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(std::shared_ptr<mi::MiApplication> const &)
0x180027a92  lea     rcx, [rdi+1A0h]
0x180027a99  mov     rdx, rbp
0x180027a9c  call    ??0?$shared_ptr@VMiApplication@mi@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(std::shared_ptr<mi::MiApplication> const &)
0x180027aa1  mov     byte ptr [rdi+1B0h], 0
0x180027aa8  lea     rcx, [rdi+1B8h]
0x180027aaf  mov     qword ptr [rcx], 0
0x180027ab6  mov     qword ptr [rcx+8], 0
0x180027abe  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180027ac4  lea     rcx, [rdi+1C8h]; SRWLock
0x180027acb  call    cs:__imp_InitializeSRWLock
0x180027ad1  nop
0x180027ad2  mov     rax, rdi
0x180027ad5  mov     rbx, [rsp+38h+arg_8]
0x180027ada  mov     rbp, [rsp+38h+arg_10]
0x180027adf  add     rsp, 20h
0x180027ae3  pop     r14
0x180027ae5  pop     rdi
0x180027ae6  pop     rsi
0x180027ae7  retn
```
