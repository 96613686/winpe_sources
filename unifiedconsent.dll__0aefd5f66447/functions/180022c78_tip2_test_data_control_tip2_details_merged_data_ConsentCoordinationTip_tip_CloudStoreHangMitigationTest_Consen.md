# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>(void)

- ea: `0x180022c78`
- end: `0x180022cfa`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002be40`

## callees

- `0x180019838`
- `0x1800229ac`
- `0x180022c78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ce9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180022c78  mov     [rsp+arg_8], rbx
0x180022c7d  push    rdi
0x180022c7e  sub     rsp, 20h
0x180022c82  mov     rdi, rcx
0x180022c85  mov     rcx, [rcx]
0x180022c88  test    rcx, rcx
0x180022c8b  jz      short loc_180022CC6
0x180022c8d  add     rcx, 8
0x180022c91  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180022c96  mov     rbx, [rdi]
0x180022c99  mov     qword ptr [rdi], 0
0x180022ca0  test    rbx, rbx
0x180022ca3  jz      short loc_180022CC6
0x180022ca5  or      eax, 0FFFFFFFFh
0x180022ca8  lock xadd [rbx+118h], eax
0x180022cb0  cmp     eax, 1
0x180022cb3  jnz     short loc_180022CC6
0x180022cb5  mov     rcx, rbx
0x180022cb8  call    ??1?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(void)
0x180022cbd  mov     rcx, rbx; pv
0x180022cc0  call    cs:__imp_CoTaskMemFree
0x180022cc6  mov     rbx, [rdi]
0x180022cc9  test    rbx, rbx
0x180022ccc  jz      short loc_180022CEF
0x180022cce  or      eax, 0FFFFFFFFh
0x180022cd1  lock xadd [rbx+118h], eax
0x180022cd9  cmp     eax, 1
0x180022cdc  jnz     short loc_180022CEF
0x180022cde  mov     rcx, rbx
0x180022ce1  call    ??1?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(void)
0x180022ce6  mov     rcx, rbx; pv
0x180022ce9  call    cs:__imp_CoTaskMemFree
0x180022cef  mov     rbx, [rsp+28h+arg_8]
0x180022cf4  add     rsp, 20h
0x180022cf8  pop     rdi
0x180022cf9  retn
```
