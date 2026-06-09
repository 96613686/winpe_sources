# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>>(void)

- ea: `0x180013b48`
- end: `0x180013bca`
- name: `??1?$test_data_control@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018380`
- `0x180071aa5`
- `0x180071b1f`

## callees

- `0x180013a68`
- `0x180013b48`
- `0x180019838`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bb9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update((__int64)&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180013b48  mov     [rsp+arg_8], rbx
0x180013b4d  push    rdi
0x180013b4e  sub     rsp, 20h
0x180013b52  mov     rdi, rcx
0x180013b55  mov     rcx, [rcx]
0x180013b58  test    rcx, rcx
0x180013b5b  jz      short loc_180013B96
0x180013b5d  add     rcx, 8
0x180013b61  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013b66  mov     rbx, [rdi]
0x180013b69  mov     qword ptr [rdi], 0
0x180013b70  test    rbx, rbx
0x180013b73  jz      short loc_180013B96
0x180013b75  or      eax, 0FFFFFFFFh
0x180013b78  lock xadd [rbx+120h], eax
0x180013b80  cmp     eax, 1
0x180013b83  jnz     short loc_180013B96
0x180013b85  mov     rcx, rbx
0x180013b88  call    ??1?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(void)
0x180013b8d  mov     rcx, rbx; pv
0x180013b90  call    cs:__imp_CoTaskMemFree
0x180013b96  mov     rbx, [rdi]
0x180013b99  test    rbx, rbx
0x180013b9c  jz      short loc_180013BBF
0x180013b9e  or      eax, 0FFFFFFFFh
0x180013ba1  lock xadd [rbx+120h], eax
0x180013ba9  cmp     eax, 1
0x180013bac  jnz     short loc_180013BBF
0x180013bae  mov     rcx, rbx
0x180013bb1  call    ??1?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(void)
0x180013bb6  mov     rcx, rbx; pv
0x180013bb9  call    cs:__imp_CoTaskMemFree
0x180013bbf  mov     rbx, [rsp+28h+arg_8]
0x180013bc4  add     rsp, 20h
0x180013bc8  pop     rdi
0x180013bc9  retn
```
