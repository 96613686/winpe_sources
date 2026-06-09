# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::ensure_data(void)

- ea: `0x18005eac4`
- end: `0x18005eb50`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180058bb8`
- `0x180059840`
- `0x18005fe6c`

## callees

- `0x180057918`
- `0x1800583f0`
- `0x18005eac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eb11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eb3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eb11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eb3c`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::ensure_data(
        __int64 *a1)
{
  __int64 *updated; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    updated = (__int64 *)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>,>(&pv);
    v3 = *updated;
    *updated = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 576), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 144, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005eac4  mov     [rsp+arg_10], rbx
0x18005eac9  push    rdi
0x18005eaca  sub     rsp, 20h
0x18005eace  cmp     qword ptr [rcx], 0
0x18005ead2  mov     rdi, rcx
0x18005ead5  jnz     short loc_18005EB42
0x18005ead7  lea     rcx, [rsp+28h+pv]
0x18005eadc  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>,>(void)
0x18005eae1  mov     rdx, [rax]
0x18005eae4  mov     qword ptr [rax], 0
0x18005eaeb  mov     rbx, [rdi]
0x18005eaee  mov     [rdi], rdx
0x18005eaf1  test    rbx, rbx
0x18005eaf4  jz      short loc_18005EB17
0x18005eaf6  or      eax, 0FFFFFFFFh
0x18005eaf9  lock xadd [rbx+240h], eax
0x18005eb01  cmp     eax, 1
0x18005eb04  jnz     short loc_18005EB17
0x18005eb06  mov     rcx, rbx
0x18005eb09  call    ??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)
0x18005eb0e  mov     rcx, rbx; pv
0x18005eb11  call    cs:__imp_CoTaskMemFree
0x18005eb17  mov     rbx, [rsp+28h+pv]
0x18005eb1c  test    rbx, rbx
0x18005eb1f  jz      short loc_18005EB42
0x18005eb21  or      eax, 0FFFFFFFFh
0x18005eb24  lock xadd [rbx+240h], eax
0x18005eb2c  cmp     eax, 1
0x18005eb2f  jnz     short loc_18005EB42
0x18005eb31  mov     rcx, rbx
0x18005eb34  call    ??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)
0x18005eb39  mov     rcx, rbx; pv
0x18005eb3c  call    cs:__imp_CoTaskMemFree
0x18005eb42  mov     rbx, [rsp+28h+arg_10]
0x18005eb47  mov     rax, rdi
0x18005eb4a  add     rsp, 20h
0x18005eb4e  pop     rdi
0x18005eb4f  retn
```
