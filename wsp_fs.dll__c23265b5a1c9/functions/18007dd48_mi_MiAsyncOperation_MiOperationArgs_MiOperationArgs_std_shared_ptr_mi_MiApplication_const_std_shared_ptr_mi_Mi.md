# mi::MiAsyncOperation::MiOperationArgs::MiOperationArgs(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiValue const &)> const &,std::function<bool (mi::MiClass const &,_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiInstance const &)> const &,mi::MiCallbacks const &)

- ea: `0x18007dd48`
- end: `0x18007de85`
- name: `??0MiOperationArgs@MiAsyncOperation@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@4@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@4@AEBV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiValue@mi@@@Z@4@AEBV?$function@$$A6A_NAEBVMiClass@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVMiInstance@2@@Z@4@AEBVMiCallbacks@2@@Z`
- size: `317`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct mi::MiCallbacks *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007d984`
- `0x18007da80`

## callees

- `0x180019d00`
- `0x18007db34`
- `0x18007dd48`
- `0x180080e30`
- `0x1800ab010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007de4e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007de4e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007de61`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007de61`

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
0x18007dd48  mov     [rsp+arg_8], rbx
0x18007dd4d  mov     [rsp+arg_10], rbp
0x18007dd52  mov     [rsp+arg_0], rcx
0x18007dd57  push    rsi
0x18007dd58  push    rdi
0x18007dd59  push    r14
0x18007dd5b  sub     rsp, 20h
0x18007dd5f  mov     rbx, r9
0x18007dd62  mov     rbp, r8
0x18007dd65  mov     r14, rdx
0x18007dd68  mov     rdi, rcx
0x18007dd6b  call    ??0ManualResetEvent@mi@@QEAA@_N@Z; mi::ManualResetEvent::ManualResetEvent(bool)
0x18007dd70  nop
0x18007dd71  lea     rsi, [rdi+10h]
0x18007dd75  mov     [rsp+38h+arg_18], rsi
0x18007dd7a  mov     qword ptr [rsi+38h], 0
0x18007dd82  mov     rcx, [rbx+38h]
0x18007dd86  test    rcx, rcx
0x18007dd89  jz      short loc_18007DD9D
0x18007dd8b  mov     rax, [rcx]
0x18007dd8e  mov     rdx, rsi
0x18007dd91  mov     rax, [rax]
0x18007dd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd99  mov     [rsi+38h], rax
0x18007dd9d  lea     rbx, [rdi+50h]
0x18007dda1  mov     [rsp+38h+arg_18], rbx
0x18007dda6  mov     qword ptr [rbx+38h], 0
0x18007ddae  mov     rax, [rsp+38h+arg_20]
0x18007ddb3  mov     rcx, [rax+38h]
0x18007ddb7  test    rcx, rcx
0x18007ddba  jz      short loc_18007DDCE
0x18007ddbc  mov     rax, [rcx]
0x18007ddbf  mov     rdx, rbx
0x18007ddc2  mov     rax, [rax]
0x18007ddc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddca  mov     [rbx+38h], rax
0x18007ddce  lea     rbx, [rdi+90h]
0x18007ddd5  mov     [rsp+38h+arg_20], rbx
0x18007ddda  mov     qword ptr [rbx+38h], 0
0x18007dde2  mov     rax, [rsp+38h+arg_28]
0x18007dde7  mov     rcx, [rax+38h]
0x18007ddeb  test    rcx, rcx
0x18007ddee  jz      short loc_18007DE02
0x18007ddf0  mov     rax, [rcx]
0x18007ddf3  mov     rdx, rbx
0x18007ddf6  mov     rax, [rax]
0x18007ddf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddfe  mov     [rbx+38h], rax
0x18007de02  lea     rcx, [rdi+0D0h]; this
0x18007de09  mov     rdx, [rsp+38h+arg_30]; struct mi::MiCallbacks *
0x18007de0e  call    ??0MiCallbacks@mi@@QEAA@AEBV01@@Z; mi::MiCallbacks::MiCallbacks(mi::MiCallbacks const &)
0x18007de13  lea     rcx, [rdi+190h]
0x18007de1a  mov     rdx, r14
0x18007de1d  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007de22  lea     rcx, [rdi+1A0h]
0x18007de29  mov     rdx, rbp
0x18007de2c  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18007de31  mov     byte ptr [rdi+1B0h], 0
0x18007de38  lea     rcx, [rdi+1B8h]
0x18007de3f  mov     qword ptr [rcx], 0
0x18007de46  mov     qword ptr [rcx+8], 0
0x18007de4e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007de55  nop     dword ptr [rax+rax+00h]
0x18007de5a  lea     rcx, [rdi+1C8h]; SRWLock
0x18007de61  call    cs:__imp_InitializeSRWLock
0x18007de68  nop     dword ptr [rax+rax+00h]
0x18007de6d  nop
0x18007de6e  mov     rax, rdi
0x18007de71  mov     rbx, [rsp+38h+arg_8]
0x18007de76  mov     rbp, [rsp+38h+arg_10]
0x18007de7b  add     rsp, 20h
0x18007de7f  pop     r14
0x18007de81  pop     rdi
0x18007de82  pop     rsi
0x18007de83  retn
```
