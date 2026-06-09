# tip2::test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>::~test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>(void)

- ea: `0x1800516bc`
- end: `0x18005173e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180052980`
- `0x180077f1a`
- `0x180078879`

## callees

- `0x180019838`
- `0x1800515bc`
- `0x1800516bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005172d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005172d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>::~test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 320), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 320), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x1800516bc  mov     [rsp+arg_8], rbx
0x1800516c1  push    rdi
0x1800516c2  sub     rsp, 20h
0x1800516c6  mov     rdi, rcx
0x1800516c9  mov     rcx, [rcx]
0x1800516cc  test    rcx, rcx
0x1800516cf  jz      short loc_18005170A
0x1800516d1  add     rcx, 8
0x1800516d5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x1800516da  mov     rbx, [rdi]
0x1800516dd  mov     qword ptr [rdi], 0
0x1800516e4  test    rbx, rbx
0x1800516e7  jz      short loc_18005170A
0x1800516e9  or      eax, 0FFFFFFFFh
0x1800516ec  lock xadd [rbx+140h], eax
0x1800516f4  cmp     eax, 1
0x1800516f7  jnz     short loc_18005170A
0x1800516f9  mov     rcx, rbx
0x1800516fc  call    ??1?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(void)
0x180051701  mov     rcx, rbx; pv
0x180051704  call    cs:__imp_CoTaskMemFree
0x18005170a  mov     rbx, [rdi]
0x18005170d  test    rbx, rbx
0x180051710  jz      short loc_180051733
0x180051712  or      eax, 0FFFFFFFFh
0x180051715  lock xadd [rbx+140h], eax
0x18005171d  cmp     eax, 1
0x180051720  jnz     short loc_180051733
0x180051722  mov     rcx, rbx
0x180051725  call    ??1?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(void)
0x18005172a  mov     rcx, rbx; pv
0x18005172d  call    cs:__imp_CoTaskMemFree
0x180051733  mov     rbx, [rsp+28h+arg_8]
0x180051738  add     rsp, 20h
0x18005173c  pop     rdi
0x18005173d  retn
```
