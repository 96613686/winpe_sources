# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x18007bf6c`
- end: `0x18007c09c`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `304`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007bbb0`
- `0x18007bcac`

## callees

- `0x1800192f0`
- `0x18007bd60`
- `0x18007bf6c`
- `0x18007ef2c`
- `0x1800a9010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c072`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c072`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007c07f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007c07f`

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
0x18007bf6c  mov     [rsp+arg_8], rbx
0x18007bf71  mov     [rsp+arg_10], rbp
0x18007bf76  mov     [rsp+arg_0], rcx
0x18007bf7b  push    rsi
0x18007bf7c  push    rdi
0x18007bf7d  push    r14
0x18007bf7f  sub     rsp, 20h
0x18007bf83  mov     rbx, r9
0x18007bf86  mov     rbp, r8
0x18007bf89  mov     r14, rdx
0x18007bf8c  mov     rdi, rcx
0x18007bf8f  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x18007bf94  nop
0x18007bf95  lea     rsi, [rdi+10h]
0x18007bf99  mov     [rsp+38h+arg_18], rsi
0x18007bf9e  mov     qword ptr [rsi+38h], 0
0x18007bfa6  mov     rcx, [rbx+38h]
0x18007bfaa  test    rcx, rcx
0x18007bfad  jz      short loc_18007BFC1
0x18007bfaf  mov     rax, [rcx]
0x18007bfb2  mov     rdx, rsi
0x18007bfb5  mov     rax, [rax]
0x18007bfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfbd  mov     [rsi+38h], rax
0x18007bfc1  lea     rbx, [rdi+50h]
0x18007bfc5  mov     [rsp+38h+arg_18], rbx
0x18007bfca  mov     qword ptr [rbx+38h], 0
0x18007bfd2  mov     rax, [rsp+38h+arg_20]
0x18007bfd7  mov     rcx, [rax+38h]
0x18007bfdb  test    rcx, rcx
0x18007bfde  jz      short loc_18007BFF2
0x18007bfe0  mov     rax, [rcx]
0x18007bfe3  mov     rdx, rbx
0x18007bfe6  mov     rax, [rax]
0x18007bfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfee  mov     [rbx+38h], rax
0x18007bff2  lea     rbx, [rdi+90h]
0x18007bff9  mov     [rsp+38h+arg_20], rbx
0x18007bffe  mov     qword ptr [rbx+38h], 0
0x18007c006  mov     rax, [rsp+38h+arg_28]
0x18007c00b  mov     rcx, [rax+38h]
0x18007c00f  test    rcx, rcx
0x18007c012  jz      short loc_18007C026
0x18007c014  mov     rax, [rcx]
0x18007c017  mov     rdx, rbx
0x18007c01a  mov     rax, [rax]
0x18007c01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c022  mov     [rbx+38h], rax
0x18007c026  lea     rcx, [rdi+0D0h]; this
0x18007c02d  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x18007c032  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x18007c037  lea     rcx, [rdi+190h]
0x18007c03e  mov     rdx, r14
0x18007c041  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007c046  lea     rcx, [rdi+1A0h]
0x18007c04d  mov     rdx, rbp
0x18007c050  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007c055  mov     byte ptr [rdi+1B0h], 0
0x18007c05c  lea     rcx, [rdi+1B8h]
0x18007c063  mov     qword ptr [rcx], 0
0x18007c06a  mov     qword ptr [rcx+8], 0
0x18007c072  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007c078  lea     rcx, [rdi+1C8h]; SRWLock
0x18007c07f  call    cs:__imp_InitializeSRWLock
0x18007c085  nop
0x18007c086  mov     rax, rdi
0x18007c089  mov     rbx, [rsp+38h+arg_8]
0x18007c08e  mov     rbp, [rsp+38h+arg_10]
0x18007c093  add     rsp, 20h
0x18007c097  pop     r14
0x18007c099  pop     rdi
0x18007c09a  pop     rsi
0x18007c09b  retn
```
