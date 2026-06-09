# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>(void)

- ea: `0x180022d00`
- end: `0x180022d82`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002aae0`
- `0x180073413`

## callees

- `0x180019838`
- `0x180022a38`
- `0x180022d00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d71`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>(
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
        tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180022d00  mov     [rsp+arg_8], rbx
0x180022d05  push    rdi
0x180022d06  sub     rsp, 20h
0x180022d0a  mov     rdi, rcx
0x180022d0d  mov     rcx, [rcx]
0x180022d10  test    rcx, rcx
0x180022d13  jz      short loc_180022D4E
0x180022d15  add     rcx, 8
0x180022d19  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180022d1e  mov     rbx, [rdi]
0x180022d21  mov     qword ptr [rdi], 0
0x180022d28  test    rbx, rbx
0x180022d2b  jz      short loc_180022D4E
0x180022d2d  or      eax, 0FFFFFFFFh
0x180022d30  lock xadd [rbx+138h], eax
0x180022d38  cmp     eax, 1
0x180022d3b  jnz     short loc_180022D4E
0x180022d3d  mov     rcx, rbx
0x180022d40  call    ??1?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(void)
0x180022d45  mov     rcx, rbx; pv
0x180022d48  call    cs:__imp_CoTaskMemFree
0x180022d4e  mov     rbx, [rdi]
0x180022d51  test    rbx, rbx
0x180022d54  jz      short loc_180022D77
0x180022d56  or      eax, 0FFFFFFFFh
0x180022d59  lock xadd [rbx+138h], eax
0x180022d61  cmp     eax, 1
0x180022d64  jnz     short loc_180022D77
0x180022d66  mov     rcx, rbx
0x180022d69  call    ??1?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(void)
0x180022d6e  mov     rcx, rbx; pv
0x180022d71  call    cs:__imp_CoTaskMemFree
0x180022d77  mov     rbx, [rsp+28h+arg_8]
0x180022d7c  add     rsp, 20h
0x180022d80  pop     rdi
0x180022d81  retn
```
