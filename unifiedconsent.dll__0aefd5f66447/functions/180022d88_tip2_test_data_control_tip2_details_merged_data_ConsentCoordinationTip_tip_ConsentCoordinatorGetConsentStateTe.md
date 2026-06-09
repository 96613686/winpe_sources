# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>(void)

- ea: `0x180022d88`
- end: `0x180022e0a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180024678`
- `0x180024794`
- `0x1800254a8`

## callees

- `0x180019838`
- `0x180022ac4`
- `0x180022d88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022df9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022df9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>(
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
        tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180022d88  mov     [rsp+arg_8], rbx
0x180022d8d  push    rdi
0x180022d8e  sub     rsp, 20h
0x180022d92  mov     rdi, rcx
0x180022d95  mov     rcx, [rcx]
0x180022d98  test    rcx, rcx
0x180022d9b  jz      short loc_180022DD6
0x180022d9d  add     rcx, 8
0x180022da1  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180022da6  mov     rbx, [rdi]
0x180022da9  mov     qword ptr [rdi], 0
0x180022db0  test    rbx, rbx
0x180022db3  jz      short loc_180022DD6
0x180022db5  or      eax, 0FFFFFFFFh
0x180022db8  lock xadd [rbx+118h], eax
0x180022dc0  cmp     eax, 1
0x180022dc3  jnz     short loc_180022DD6
0x180022dc5  mov     rcx, rbx
0x180022dc8  call    ??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)
0x180022dcd  mov     rcx, rbx; pv
0x180022dd0  call    cs:__imp_CoTaskMemFree
0x180022dd6  mov     rbx, [rdi]
0x180022dd9  test    rbx, rbx
0x180022ddc  jz      short loc_180022DFF
0x180022dde  or      eax, 0FFFFFFFFh
0x180022de1  lock xadd [rbx+118h], eax
0x180022de9  cmp     eax, 1
0x180022dec  jnz     short loc_180022DFF
0x180022dee  mov     rcx, rbx
0x180022df1  call    ??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)
0x180022df6  mov     rcx, rbx; pv
0x180022df9  call    cs:__imp_CoTaskMemFree
0x180022dff  mov     rbx, [rsp+28h+arg_8]
0x180022e04  add     rsp, 20h
0x180022e08  pop     rdi
0x180022e09  retn
```
