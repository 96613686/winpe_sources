# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x18007e668`
- end: `0x18007e7a5`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `317`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007e3a0`

## callees

- `0x180016b30`
- `0x18007e454`
- `0x18007e668`
- `0x1800822b4`
- `0x18008e010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007e76e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007e76e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e781`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e781`

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
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(a1 + 400, a2);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(a1 + 416, a3);
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
0x18007e668  mov     [rsp+arg_8], rbx
0x18007e66d  mov     [rsp+arg_10], rbp
0x18007e672  mov     [rsp+arg_0], rcx
0x18007e677  push    rsi
0x18007e678  push    rdi
0x18007e679  push    r14
0x18007e67b  sub     rsp, 20h
0x18007e67f  mov     rbx, r9
0x18007e682  mov     rbp, r8
0x18007e685  mov     r14, rdx
0x18007e688  mov     rdi, rcx
0x18007e68b  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x18007e690  nop
0x18007e691  lea     rsi, [rdi+10h]
0x18007e695  mov     [rsp+38h+arg_18], rsi
0x18007e69a  mov     qword ptr [rsi+38h], 0
0x18007e6a2  mov     rcx, [rbx+38h]
0x18007e6a6  test    rcx, rcx
0x18007e6a9  jz      short loc_18007E6BD
0x18007e6ab  mov     rax, [rcx]
0x18007e6ae  mov     rdx, rsi
0x18007e6b1  mov     rax, [rax]
0x18007e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6b9  mov     [rsi+38h], rax
0x18007e6bd  lea     rbx, [rdi+50h]
0x18007e6c1  mov     [rsp+38h+arg_18], rbx
0x18007e6c6  mov     qword ptr [rbx+38h], 0
0x18007e6ce  mov     rax, [rsp+38h+arg_20]
0x18007e6d3  mov     rcx, [rax+38h]
0x18007e6d7  test    rcx, rcx
0x18007e6da  jz      short loc_18007E6EE
0x18007e6dc  mov     rax, [rcx]
0x18007e6df  mov     rdx, rbx
0x18007e6e2  mov     rax, [rax]
0x18007e6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6ea  mov     [rbx+38h], rax
0x18007e6ee  lea     rbx, [rdi+90h]
0x18007e6f5  mov     [rsp+38h+arg_20], rbx
0x18007e6fa  mov     qword ptr [rbx+38h], 0
0x18007e702  mov     rax, [rsp+38h+arg_28]
0x18007e707  mov     rcx, [rax+38h]
0x18007e70b  test    rcx, rcx
0x18007e70e  jz      short loc_18007E722
0x18007e710  mov     rax, [rcx]
0x18007e713  mov     rdx, rbx
0x18007e716  mov     rax, [rax]
0x18007e719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e71e  mov     [rbx+38h], rax
0x18007e722  lea     rcx, [rdi+0D0h]; this
0x18007e729  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x18007e72e  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x18007e733  lea     rcx, [rdi+190h]
0x18007e73a  mov     rdx, r14
0x18007e73d  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007e742  lea     rcx, [rdi+1A0h]
0x18007e749  mov     rdx, rbp
0x18007e74c  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007e751  mov     byte ptr [rdi+1B0h], 0
0x18007e758  lea     rcx, [rdi+1B8h]
0x18007e75f  mov     qword ptr [rcx], 0
0x18007e766  mov     qword ptr [rcx+8], 0
0x18007e76e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007e775  nop     dword ptr [rax+rax+00h]
0x18007e77a  lea     rcx, [rdi+1C8h]; SRWLock
0x18007e781  call    cs:__imp_InitializeSRWLock
0x18007e788  nop     dword ptr [rax+rax+00h]
0x18007e78d  nop
0x18007e78e  mov     rax, rdi
0x18007e791  mov     rbx, [rsp+38h+arg_8]
0x18007e796  mov     rbp, [rsp+38h+arg_10]
0x18007e79b  add     rsp, 20h
0x18007e79f  pop     r14
0x18007e7a1  pop     rdi
0x18007e7a2  pop     rsi
0x18007e7a3  retn
```
