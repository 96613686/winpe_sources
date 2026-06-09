# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>>(void)

- ea: `0x180022e98`
- end: `0x180022f1a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ConsentCoordinatorSetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180023994`

## callees

- `0x180019838`
- `0x180022bdc`
- `0x180022e98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f09`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180022e98  mov     [rsp+arg_8], rbx
0x180022e9d  push    rdi
0x180022e9e  sub     rsp, 20h
0x180022ea2  mov     rdi, rcx
0x180022ea5  mov     rcx, [rcx]
0x180022ea8  test    rcx, rcx
0x180022eab  jz      short loc_180022EE6
0x180022ead  add     rcx, 8
0x180022eb1  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180022eb6  mov     rbx, [rdi]
0x180022eb9  mov     qword ptr [rdi], 0
0x180022ec0  test    rbx, rbx
0x180022ec3  jz      short loc_180022EE6
0x180022ec5  or      eax, 0FFFFFFFFh
0x180022ec8  lock xadd [rbx+118h], eax
0x180022ed0  cmp     eax, 1
0x180022ed3  jnz     short loc_180022EE6
0x180022ed5  mov     rcx, rbx
0x180022ed8  call    ??1?$merged_data@U_tip_ConsentCoordinatorSetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>(void)
0x180022edd  mov     rcx, rbx; pv
0x180022ee0  call    cs:__imp_CoTaskMemFree
0x180022ee6  mov     rbx, [rdi]
0x180022ee9  test    rbx, rbx
0x180022eec  jz      short loc_180022F0F
0x180022eee  or      eax, 0FFFFFFFFh
0x180022ef1  lock xadd [rbx+118h], eax
0x180022ef9  cmp     eax, 1
0x180022efc  jnz     short loc_180022F0F
0x180022efe  mov     rcx, rbx
0x180022f01  call    ??1?$merged_data@U_tip_ConsentCoordinatorSetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>(void)
0x180022f06  mov     rcx, rbx; pv
0x180022f09  call    cs:__imp_CoTaskMemFree
0x180022f0f  mov     rbx, [rsp+28h+arg_8]
0x180022f14  add     rsp, 20h
0x180022f18  pop     rdi
0x180022f19  retn
```
