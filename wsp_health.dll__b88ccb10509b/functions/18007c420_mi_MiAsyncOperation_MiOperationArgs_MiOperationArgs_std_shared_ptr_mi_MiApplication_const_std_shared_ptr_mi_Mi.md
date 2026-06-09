# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x18007c420`
- end: `0x18007c550`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `304`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007c160`

## callees

- `0x180016218`
- `0x18007c214`
- `0x18007c420`
- `0x18007ff20`
- `0x18008c010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c526`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c526`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007c533`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007c533`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
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
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>((_QWORD *)(a1 + 400), a2);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>((_QWORD *)(a1 + 416), a3);
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
0x18007c420  mov     [rsp+arg_8], rbx
0x18007c425  mov     [rsp+arg_10], rbp
0x18007c42a  mov     [rsp+arg_0], rcx
0x18007c42f  push    rsi
0x18007c430  push    rdi
0x18007c431  push    r14
0x18007c433  sub     rsp, 20h
0x18007c437  mov     rbx, r9
0x18007c43a  mov     rbp, r8
0x18007c43d  mov     r14, rdx
0x18007c440  mov     rdi, rcx
0x18007c443  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x18007c448  nop
0x18007c449  lea     rsi, [rdi+10h]
0x18007c44d  mov     [rsp+38h+arg_18], rsi
0x18007c452  mov     qword ptr [rsi+38h], 0
0x18007c45a  mov     rcx, [rbx+38h]
0x18007c45e  test    rcx, rcx
0x18007c461  jz      short loc_18007C475
0x18007c463  mov     rax, [rcx]
0x18007c466  mov     rdx, rsi
0x18007c469  mov     rax, [rax]
0x18007c46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c471  mov     [rsi+38h], rax
0x18007c475  lea     rbx, [rdi+50h]
0x18007c479  mov     [rsp+38h+arg_18], rbx
0x18007c47e  mov     qword ptr [rbx+38h], 0
0x18007c486  mov     rax, [rsp+38h+arg_20]
0x18007c48b  mov     rcx, [rax+38h]
0x18007c48f  test    rcx, rcx
0x18007c492  jz      short loc_18007C4A6
0x18007c494  mov     rax, [rcx]
0x18007c497  mov     rdx, rbx
0x18007c49a  mov     rax, [rax]
0x18007c49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4a2  mov     [rbx+38h], rax
0x18007c4a6  lea     rbx, [rdi+90h]
0x18007c4ad  mov     [rsp+38h+arg_20], rbx
0x18007c4b2  mov     qword ptr [rbx+38h], 0
0x18007c4ba  mov     rax, [rsp+38h+arg_28]
0x18007c4bf  mov     rcx, [rax+38h]
0x18007c4c3  test    rcx, rcx
0x18007c4c6  jz      short loc_18007C4DA
0x18007c4c8  mov     rax, [rcx]
0x18007c4cb  mov     rdx, rbx
0x18007c4ce  mov     rax, [rax]
0x18007c4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4d6  mov     [rbx+38h], rax
0x18007c4da  lea     rcx, [rdi+0D0h]; this
0x18007c4e1  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x18007c4e6  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x18007c4eb  lea     rcx, [rdi+190h]
0x18007c4f2  mov     rdx, r14
0x18007c4f5  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007c4fa  lea     rcx, [rdi+1A0h]
0x18007c501  mov     rdx, rbp
0x18007c504  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007c509  mov     byte ptr [rdi+1B0h], 0
0x18007c510  lea     rcx, [rdi+1B8h]
0x18007c517  mov     qword ptr [rcx], 0
0x18007c51e  mov     qword ptr [rcx+8], 0
0x18007c526  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007c52c  lea     rcx, [rdi+1C8h]; SRWLock
0x18007c533  call    cs:__imp_InitializeSRWLock
0x18007c539  nop
0x18007c53a  mov     rax, rdi
0x18007c53d  mov     rbx, [rsp+38h+arg_8]
0x18007c542  mov     rbp, [rsp+38h+arg_10]
0x18007c547  add     rsp, 20h
0x18007c54b  pop     r14
0x18007c54d  pop     rdi
0x18007c54e  pop     rsi
0x18007c54f  retn
```
