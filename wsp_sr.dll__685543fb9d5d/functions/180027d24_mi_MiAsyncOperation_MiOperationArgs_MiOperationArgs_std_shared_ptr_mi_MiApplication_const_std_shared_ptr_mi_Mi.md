# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x180027d24`
- end: `0x180027e61`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `317`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180027890`
- `0x18002798c`
- `0x180027a40`

## callees

- `0x18001174c`
- `0x180027b10`
- `0x180027d24`
- `0x180028f78`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180027e2a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180027e2a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027e3d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027e3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180027d24  mov     [rsp+arg_8], rbx
0x180027d29  mov     [rsp+arg_10], rbp
0x180027d2e  mov     [rsp+arg_0], rcx
0x180027d33  push    rsi
0x180027d34  push    rdi
0x180027d35  push    r14
0x180027d37  sub     rsp, 20h
0x180027d3b  mov     rbx, r9
0x180027d3e  mov     rbp, r8
0x180027d41  mov     r14, rdx
0x180027d44  mov     rdi, rcx
0x180027d47  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x180027d4c  nop
0x180027d4d  lea     rsi, [rdi+10h]
0x180027d51  mov     [rsp+38h+arg_18], rsi
0x180027d56  mov     qword ptr [rsi+38h], 0
0x180027d5e  mov     rcx, [rbx+38h]
0x180027d62  test    rcx, rcx
0x180027d65  jz      short loc_180027D79
0x180027d67  mov     rax, [rcx]
0x180027d6a  mov     rdx, rsi
0x180027d6d  mov     rax, [rax]
0x180027d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d75  mov     [rsi+38h], rax
0x180027d79  lea     rbx, [rdi+50h]
0x180027d7d  mov     [rsp+38h+arg_18], rbx
0x180027d82  mov     qword ptr [rbx+38h], 0
0x180027d8a  mov     rax, [rsp+38h+arg_20]
0x180027d8f  mov     rcx, [rax+38h]
0x180027d93  test    rcx, rcx
0x180027d96  jz      short loc_180027DAA
0x180027d98  mov     rax, [rcx]
0x180027d9b  mov     rdx, rbx
0x180027d9e  mov     rax, [rax]
0x180027da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da6  mov     [rbx+38h], rax
0x180027daa  lea     rbx, [rdi+90h]
0x180027db1  mov     [rsp+38h+arg_20], rbx
0x180027db6  mov     qword ptr [rbx+38h], 0
0x180027dbe  mov     rax, [rsp+38h+arg_28]
0x180027dc3  mov     rcx, [rax+38h]
0x180027dc7  test    rcx, rcx
0x180027dca  jz      short loc_180027DDE
0x180027dcc  mov     rax, [rcx]
0x180027dcf  mov     rdx, rbx
0x180027dd2  mov     rax, [rax]
0x180027dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dda  mov     [rbx+38h], rax
0x180027dde  lea     rcx, [rdi+0D0h]; this
0x180027de5  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x180027dea  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x180027def  lea     rcx, [rdi+190h]
0x180027df6  mov     rdx, r14
0x180027df9  call    ??0?$shared_ptr@VMiApplication@mi@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(std::shared_ptr<mi::MiApplication> const &)
0x180027dfe  lea     rcx, [rdi+1A0h]
0x180027e05  mov     rdx, rbp
0x180027e08  call    ??0?$shared_ptr@VMiApplication@mi@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<mi::MiApplication>::shared_ptr<mi::MiApplication>(std::shared_ptr<mi::MiApplication> const &)
0x180027e0d  mov     byte ptr [rdi+1B0h], 0
0x180027e14  lea     rcx, [rdi+1B8h]
0x180027e1b  mov     qword ptr [rcx], 0
0x180027e22  mov     qword ptr [rcx+8], 0
0x180027e2a  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180027e31  nop     dword ptr [rax+rax+00h]
0x180027e36  lea     rcx, [rdi+1C8h]; SRWLock
0x180027e3d  call    cs:__imp_InitializeSRWLock
0x180027e44  nop     dword ptr [rax+rax+00h]
0x180027e49  nop
0x180027e4a  mov     rax, rdi
0x180027e4d  mov     rbx, [rsp+38h+arg_8]
0x180027e52  mov     rbp, [rsp+38h+arg_10]
0x180027e57  add     rsp, 20h
0x180027e5b  pop     r14
0x180027e5d  pop     rdi
0x180027e5e  pop     rsi
0x180027e5f  retn
```
