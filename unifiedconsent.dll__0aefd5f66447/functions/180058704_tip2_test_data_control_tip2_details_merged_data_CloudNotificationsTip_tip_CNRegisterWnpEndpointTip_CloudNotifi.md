# tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>(void)

- ea: `0x180058704`
- end: `0x180058786`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005d2e8`
- `0x180079d73`
- `0x180079ddf`

## callees

- `0x180019838`
- `0x180058544`
- `0x180058704`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005874c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005874c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058775`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::~test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 384), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 384), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180058704  mov     [rsp+arg_8], rbx
0x180058709  push    rdi
0x18005870a  sub     rsp, 20h
0x18005870e  mov     rdi, rcx
0x180058711  mov     rcx, [rcx]
0x180058714  test    rcx, rcx
0x180058717  jz      short loc_180058752
0x180058719  add     rcx, 8
0x18005871d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180058722  mov     rbx, [rdi]
0x180058725  mov     qword ptr [rdi], 0
0x18005872c  test    rbx, rbx
0x18005872f  jz      short loc_180058752
0x180058731  or      eax, 0FFFFFFFFh
0x180058734  lock xadd [rbx+180h], eax
0x18005873c  cmp     eax, 1
0x18005873f  jnz     short loc_180058752
0x180058741  mov     rcx, rbx
0x180058744  call    ??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)
0x180058749  mov     rcx, rbx; pv
0x18005874c  call    cs:__imp_CoTaskMemFree
0x180058752  mov     rbx, [rdi]
0x180058755  test    rbx, rbx
0x180058758  jz      short loc_18005877B
0x18005875a  or      eax, 0FFFFFFFFh
0x18005875d  lock xadd [rbx+180h], eax
0x180058765  cmp     eax, 1
0x180058768  jnz     short loc_18005877B
0x18005876a  mov     rcx, rbx
0x18005876d  call    ??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)
0x180058772  mov     rcx, rbx; pv
0x180058775  call    cs:__imp_CoTaskMemFree
0x18005877b  mov     rbx, [rsp+28h+arg_8]
0x180058780  add     rsp, 20h
0x180058784  pop     rdi
0x180058785  retn
```
