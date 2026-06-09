# Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>::set_exception(std::exception_ptr)

- ea: `0x1803be49c`
- end: `0x1803be53f`
- name: `?set_exception@?$task_completion_event@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@QEBA_NVexception_ptr@std@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1804928ad`

## callees

- `0x18003abb0`
- `0x18003acf8`
- `0x180152cac`
- `0x1803bc97c`
- `0x1803be49c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1803be4d1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1803be4ef`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1803be4d1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1803be4ef`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1803be51b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1803be52f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1803be51b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1803be52f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::set_exception(
        __int64 a1,
        void *a2)
{
  __int64 v4; // r8
  char v5; // bl
  __int128 v7; // [rsp+20h] [rbp-40h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-18h] BYREF

  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v9);
  v9 = v4;
  v7 = 0;
  __ExceptionPtrCopy(&v7, a2);
  v8 = 0;
  __ExceptionPtrCopy(&v8, &v7);
  if ( (unsigned __int8)Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::_StoreException<std::exception_ptr>(
                          a1,
                          &v8,
                          &v9) )
    v5 = Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::_CancelInternal(a1);
  else
    v5 = 0;
  __ExceptionPtrDestroy(&v7);
  std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::~vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(v10);
  __ExceptionPtrDestroy(a2);
  return v5;
}

```

## disassembly

```asm
0x1803be49c  mov     [rsp-18h+arg_8], rdx
0x1803be4a1  push    rbp
0x1803be4a2  push    rbx
0x1803be4a3  push    rdi
0x1803be4a4  mov     rbp, rsp
0x1803be4a7  sub     rsp, 60h
0x1803be4ab  mov     rdi, rdx
0x1803be4ae  mov     rbx, rcx
0x1803be4b1  mov     r8, [rbp+18h]
0x1803be4b5  lea     rcx, [rbp+var_20]; this
0x1803be4b9  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1803be4be  mov     [rbp+var_20], r8
0x1803be4c2  xorps   xmm0, xmm0
0x1803be4c5  movdqu  [rbp+var_40], xmm0
0x1803be4ca  mov     rdx, rdi
0x1803be4cd  lea     rcx, [rbp+var_40]
0x1803be4d1  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1803be4d7  lea     rax, [rbp+var_40]
0x1803be4db  mov     [rbp+arg_10], rax
0x1803be4df  xorps   xmm0, xmm0
0x1803be4e2  movdqu  [rbp+var_30], xmm0
0x1803be4e7  lea     rdx, [rbp+var_40]
0x1803be4eb  lea     rcx, [rbp+var_30]
0x1803be4ef  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1803be4f5  lea     r8, [rbp+var_20]
0x1803be4f9  lea     rdx, [rbp+var_30]
0x1803be4fd  mov     rcx, rbx
0x1803be500  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::_StoreException<std::exception_ptr>(std::exception_ptr,Concurrency::details::_TaskCreationCallstack const &)
0x1803be505  test    al, al
0x1803be507  jz      short loc_1803BE515
0x1803be509  mov     rcx, rbx
0x1803be50c  call    ?_CancelInternal@?$task_completion_event@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@AEBA_NXZ; Concurrency::task_completion_event<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::_CancelInternal(void)
0x1803be511  mov     bl, al
0x1803be513  jmp     short loc_1803BE517
0x1803be515  xor     bl, bl
0x1803be517  lea     rcx, [rbp+var_40]
0x1803be51b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1803be521  nop
0x1803be522  lea     rcx, [rbp+var_18]
0x1803be526  call    ??1?$vector@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@V?$allocator@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::~vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(void)
0x1803be52b  nop
0x1803be52c  mov     rcx, rdi
0x1803be52f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1803be535  mov     al, bl
0x1803be537  add     rsp, 60h
0x1803be53b  pop     rdi
0x1803be53c  pop     rbx
0x1803be53d  pop     rbp
0x1803be53e  retn
```
