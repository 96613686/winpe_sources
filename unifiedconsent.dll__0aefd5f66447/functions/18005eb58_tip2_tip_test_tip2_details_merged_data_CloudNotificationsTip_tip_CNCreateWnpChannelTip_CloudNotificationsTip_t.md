# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::ensure_data(void)

- ea: `0x18005eb58`
- end: `0x18005ebe4`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058c08`
- `0x18005ba20`
- `0x18005ff6c`

## callees

- `0x180057af8`
- `0x180058488`
- `0x18005eb58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ebd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ebd0`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[10].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 102, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005eb58  mov     [rsp+arg_10], rbx
0x18005eb5d  push    rdi
0x18005eb5e  sub     rsp, 20h
0x18005eb62  cmp     qword ptr [rcx], 0
0x18005eb66  mov     rdi, rcx
0x18005eb69  jnz     short loc_18005EBD6
0x18005eb6b  lea     rcx, [rsp+28h+pv]
0x18005eb70  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>,>(void)
0x18005eb75  mov     rdx, [rax]
0x18005eb78  mov     qword ptr [rax], 0
0x18005eb7f  mov     rbx, [rdi]
0x18005eb82  mov     [rdi], rdx
0x18005eb85  test    rbx, rbx
0x18005eb88  jz      short loc_18005EBAB
0x18005eb8a  or      eax, 0FFFFFFFFh
0x18005eb8d  lock xadd [rbx+198h], eax
0x18005eb95  cmp     eax, 1
0x18005eb98  jnz     short loc_18005EBAB
0x18005eb9a  mov     rcx, rbx
0x18005eb9d  call    ??1?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(void)
0x18005eba2  mov     rcx, rbx; pv
0x18005eba5  call    cs:__imp_CoTaskMemFree
0x18005ebab  mov     rbx, [rsp+28h+pv]
0x18005ebb0  test    rbx, rbx
0x18005ebb3  jz      short loc_18005EBD6
0x18005ebb5  or      eax, 0FFFFFFFFh
0x18005ebb8  lock xadd [rbx+198h], eax
0x18005ebc0  cmp     eax, 1
0x18005ebc3  jnz     short loc_18005EBD6
0x18005ebc5  mov     rcx, rbx
0x18005ebc8  call    ??1?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(void)
0x18005ebcd  mov     rcx, rbx; pv
0x18005ebd0  call    cs:__imp_CoTaskMemFree
0x18005ebd6  mov     rbx, [rsp+28h+arg_10]
0x18005ebdb  mov     rax, rdi
0x18005ebde  add     rsp, 20h
0x18005ebe2  pop     rdi
0x18005ebe3  retn
```
