# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(void)

- ea: `0x180032ab0`
- end: `0x180032b32`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036900`
- `0x180074af3`
- `0x1800750be`

## callees

- `0x180019838`
- `0x180032890`
- `0x180032ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b21`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(
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
        tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180032ab0  mov     [rsp+arg_8], rbx
0x180032ab5  push    rdi
0x180032ab6  sub     rsp, 20h
0x180032aba  mov     rdi, rcx
0x180032abd  mov     rcx, [rcx]
0x180032ac0  test    rcx, rcx
0x180032ac3  jz      short loc_180032AFE
0x180032ac5  add     rcx, 8
0x180032ac9  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180032ace  mov     rbx, [rdi]
0x180032ad1  mov     qword ptr [rdi], 0
0x180032ad8  test    rbx, rbx
0x180032adb  jz      short loc_180032AFE
0x180032add  or      eax, 0FFFFFFFFh
0x180032ae0  lock xadd [rbx+138h], eax
0x180032ae8  cmp     eax, 1
0x180032aeb  jnz     short loc_180032AFE
0x180032aed  mov     rcx, rbx
0x180032af0  call    ??1?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(void)
0x180032af5  mov     rcx, rbx; pv
0x180032af8  call    cs:__imp_CoTaskMemFree
0x180032afe  mov     rbx, [rdi]
0x180032b01  test    rbx, rbx
0x180032b04  jz      short loc_180032B27
0x180032b06  or      eax, 0FFFFFFFFh
0x180032b09  lock xadd [rbx+138h], eax
0x180032b11  cmp     eax, 1
0x180032b14  jnz     short loc_180032B27
0x180032b16  mov     rcx, rbx
0x180032b19  call    ??1?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(void)
0x180032b1e  mov     rcx, rbx; pv
0x180032b21  call    cs:__imp_CoTaskMemFree
0x180032b27  mov     rbx, [rsp+28h+arg_8]
0x180032b2c  add     rsp, 20h
0x180032b30  pop     rdi
0x180032b31  retn
```
