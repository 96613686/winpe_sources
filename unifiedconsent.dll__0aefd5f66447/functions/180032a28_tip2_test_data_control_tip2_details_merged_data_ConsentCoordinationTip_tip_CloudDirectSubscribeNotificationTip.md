# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>(void)

- ea: `0x180032a28`
- end: `0x180032aaa`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800334a0`
- `0x180073f4e`
- `0x180074811`

## callees

- `0x180019838`
- `0x1800327f8`
- `0x180032a28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a99`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 312), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180032a28  mov     [rsp+arg_8], rbx
0x180032a2d  push    rdi
0x180032a2e  sub     rsp, 20h
0x180032a32  mov     rdi, rcx
0x180032a35  mov     rcx, [rcx]
0x180032a38  test    rcx, rcx
0x180032a3b  jz      short loc_180032A76
0x180032a3d  add     rcx, 8
0x180032a41  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180032a46  mov     rbx, [rdi]
0x180032a49  mov     qword ptr [rdi], 0
0x180032a50  test    rbx, rbx
0x180032a53  jz      short loc_180032A76
0x180032a55  or      eax, 0FFFFFFFFh
0x180032a58  lock xadd [rbx+138h], eax
0x180032a60  cmp     eax, 1
0x180032a63  jnz     short loc_180032A76
0x180032a65  mov     rcx, rbx
0x180032a68  call    ??1?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(void)
0x180032a6d  mov     rcx, rbx; pv
0x180032a70  call    cs:__imp_CoTaskMemFree
0x180032a76  mov     rbx, [rdi]
0x180032a79  test    rbx, rbx
0x180032a7c  jz      short loc_180032A9F
0x180032a7e  or      eax, 0FFFFFFFFh
0x180032a81  lock xadd [rbx+138h], eax
0x180032a89  cmp     eax, 1
0x180032a8c  jnz     short loc_180032A9F
0x180032a8e  mov     rcx, rbx
0x180032a91  call    ??1?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(void)
0x180032a96  mov     rcx, rbx; pv
0x180032a99  call    cs:__imp_CoTaskMemFree
0x180032a9f  mov     rbx, [rsp+28h+arg_8]
0x180032aa4  add     rsp, 20h
0x180032aa8  pop     rdi
0x180032aa9  retn
```
