# tip2::test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>::~test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>(void)

- ea: `0x18004070c`
- end: `0x18004078e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180041410`
- `0x180075b21`
- `0x180075b7b`

## callees

- `0x180019838`
- `0x180040674`
- `0x18004070c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004077d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004077d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>::~test_data_control<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>(
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
        tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x18004070c  mov     [rsp+arg_8], rbx
0x180040711  push    rdi
0x180040712  sub     rsp, 20h
0x180040716  mov     rdi, rcx
0x180040719  mov     rcx, [rcx]
0x18004071c  test    rcx, rcx
0x18004071f  jz      short loc_18004075A
0x180040721  add     rcx, 8
0x180040725  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18004072a  mov     rbx, [rdi]
0x18004072d  mov     qword ptr [rdi], 0
0x180040734  test    rbx, rbx
0x180040737  jz      short loc_18004075A
0x180040739  or      eax, 0FFFFFFFFh
0x18004073c  lock xadd [rbx+138h], eax
0x180040744  cmp     eax, 1
0x180040747  jnz     short loc_18004075A
0x180040749  mov     rcx, rbx
0x18004074c  call    ??1?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(void)
0x180040751  mov     rcx, rbx; pv
0x180040754  call    cs:__imp_CoTaskMemFree
0x18004075a  mov     rbx, [rdi]
0x18004075d  test    rbx, rbx
0x180040760  jz      short loc_180040783
0x180040762  or      eax, 0FFFFFFFFh
0x180040765  lock xadd [rbx+138h], eax
0x18004076d  cmp     eax, 1
0x180040770  jnz     short loc_180040783
0x180040772  mov     rcx, rbx
0x180040775  call    ??1?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(void)
0x18004077a  mov     rcx, rbx; pv
0x18004077d  call    cs:__imp_CoTaskMemFree
0x180040783  mov     rbx, [rsp+28h+arg_8]
0x180040788  add     rsp, 20h
0x18004078c  pop     rdi
0x18004078d  retn
```
