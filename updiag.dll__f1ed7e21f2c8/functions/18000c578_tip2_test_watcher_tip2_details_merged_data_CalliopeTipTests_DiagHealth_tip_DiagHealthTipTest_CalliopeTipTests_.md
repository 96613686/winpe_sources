# tip2::test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)

- ea: `0x18000c578`
- end: `0x18000c5c2`
- name: `??1?$test_watcher@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800971b4`
- `0x1800971c6`

## callees

- `0x180005950`
- `0x18000c578`
- `0x18000e12c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5a9`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(
        __int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 48);
  if ( v1 && _InterlockedExchangeAdd(&v1[7].LockCount, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v1);
    CoTaskMemFree(v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x18000c578  mov     [rsp+arg_8], rbx
0x18000c57d  push    rdi
0x18000c57e  sub     rsp, 20h
0x18000c582  mov     rbx, [rcx+30h]
0x18000c586  mov     rdi, rcx
0x18000c589  test    rbx, rbx
0x18000c58c  jz      short loc_18000C5AF
0x18000c58e  or      eax, 0FFFFFFFFh
0x18000c591  lock xadd [rbx+120h], eax
0x18000c599  cmp     eax, 1
0x18000c59c  jnz     short loc_18000C5AF
0x18000c59e  mov     rcx, rbx
0x18000c5a1  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000c5a6  mov     rcx, rbx; pv
0x18000c5a9  call    cs:__imp_CoTaskMemFree
0x18000c5af  lea     rcx, [rdi+8]; this
0x18000c5b3  mov     rbx, [rsp+28h+arg_8]
0x18000c5b8  add     rsp, 20h
0x18000c5bc  pop     rdi
0x18000c5bd  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
