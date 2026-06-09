# tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>(void)

- ea: `0x18005867c`
- end: `0x1800586fe`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005ba20`
- `0x1800798ea`
- `0x18007991e`
- `0x180079952`
- `0x180079a8a`
- `0x180079b8e`

## callees

- `0x180019838`
- `0x180058488`
- `0x18005867c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800586c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800586ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800586c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800586ed`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>(
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
      if ( _InterlockedExchangeAdd(&v3[10].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[10].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x18005867c  mov     [rsp+arg_8], rbx
0x180058681  push    rdi
0x180058682  sub     rsp, 20h
0x180058686  mov     rdi, rcx
0x180058689  mov     rcx, [rcx]
0x18005868c  test    rcx, rcx
0x18005868f  jz      short loc_1800586CA
0x180058691  add     rcx, 8
0x180058695  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18005869a  mov     rbx, [rdi]
0x18005869d  mov     qword ptr [rdi], 0
0x1800586a4  test    rbx, rbx
0x1800586a7  jz      short loc_1800586CA
0x1800586a9  or      eax, 0FFFFFFFFh
0x1800586ac  lock xadd [rbx+198h], eax
0x1800586b4  cmp     eax, 1
0x1800586b7  jnz     short loc_1800586CA
0x1800586b9  mov     rcx, rbx
0x1800586bc  call    ??1?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(void)
0x1800586c1  mov     rcx, rbx; pv
0x1800586c4  call    cs:__imp_CoTaskMemFree
0x1800586ca  mov     rbx, [rdi]
0x1800586cd  test    rbx, rbx
0x1800586d0  jz      short loc_1800586F3
0x1800586d2  or      eax, 0FFFFFFFFh
0x1800586d5  lock xadd [rbx+198h], eax
0x1800586dd  cmp     eax, 1
0x1800586e0  jnz     short loc_1800586F3
0x1800586e2  mov     rcx, rbx
0x1800586e5  call    ??1?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(void)
0x1800586ea  mov     rcx, rbx; pv
0x1800586ed  call    cs:__imp_CoTaskMemFree
0x1800586f3  mov     rbx, [rsp+28h+arg_8]
0x1800586f8  add     rsp, 20h
0x1800586fc  pop     rdi
0x1800586fd  retn
```
