# tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>(void)

- ea: `0x1800585f4`
- end: `0x180058676`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180059840`
- `0x180078e08`
- `0x180078f40`
- `0x180078f74`
- `0x180078fa8`
- `0x180078fdc`
- `0x1800790f1`
- `0x180079229`
- `0x1800793a6`
- `0x180079500`

## callees

- `0x180019838`
- `0x1800583f0`
- `0x1800585f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005863c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005863c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058665`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 576), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 576), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x1800585f4  mov     [rsp+arg_8], rbx
0x1800585f9  push    rdi
0x1800585fa  sub     rsp, 20h
0x1800585fe  mov     rdi, rcx
0x180058601  mov     rcx, [rcx]
0x180058604  test    rcx, rcx
0x180058607  jz      short loc_180058642
0x180058609  add     rcx, 8
0x18005860d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180058612  mov     rbx, [rdi]
0x180058615  mov     qword ptr [rdi], 0
0x18005861c  test    rbx, rbx
0x18005861f  jz      short loc_180058642
0x180058621  or      eax, 0FFFFFFFFh
0x180058624  lock xadd [rbx+240h], eax
0x18005862c  cmp     eax, 1
0x18005862f  jnz     short loc_180058642
0x180058631  mov     rcx, rbx
0x180058634  call    ??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)
0x180058639  mov     rcx, rbx; pv
0x18005863c  call    cs:__imp_CoTaskMemFree
0x180058642  mov     rbx, [rdi]
0x180058645  test    rbx, rbx
0x180058648  jz      short loc_18005866B
0x18005864a  or      eax, 0FFFFFFFFh
0x18005864d  lock xadd [rbx+240h], eax
0x180058655  cmp     eax, 1
0x180058658  jnz     short loc_18005866B
0x18005865a  mov     rcx, rbx
0x18005865d  call    ??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)
0x180058662  mov     rcx, rbx; pv
0x180058665  call    cs:__imp_CoTaskMemFree
0x18005866b  mov     rbx, [rsp+28h+arg_8]
0x180058670  add     rsp, 20h
0x180058674  pop     rdi
0x180058675  retn
```
