# tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)

- ea: `0x18000fe3c`
- end: `0x18000febe`
- name: `??1?$test_data_control@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010f28`
- `0x180011994`

## callees

- `0x18000fcd4`
- `0x18000fe3c`
- `0x180015e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fead`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x18000fe3c  mov     [rsp+arg_8], rbx
0x18000fe41  push    rdi
0x18000fe42  sub     rsp, 20h
0x18000fe46  mov     rdi, rcx
0x18000fe49  mov     rcx, [rcx]
0x18000fe4c  test    rcx, rcx
0x18000fe4f  jz      short loc_18000FE8A
0x18000fe51  add     rcx, 8
0x18000fe55  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x18000fe5a  mov     rbx, [rdi]
0x18000fe5d  mov     qword ptr [rdi], 0
0x18000fe64  test    rbx, rbx
0x18000fe67  jz      short loc_18000FE8A
0x18000fe69  or      eax, 0FFFFFFFFh
0x18000fe6c  lock xadd [rbx+118h], eax
0x18000fe74  cmp     eax, 1
0x18000fe77  jnz     short loc_18000FE8A
0x18000fe79  mov     rcx, rbx
0x18000fe7c  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000fe81  mov     rcx, rbx; pv
0x18000fe84  call    cs:__imp_CoTaskMemFree
0x18000fe8a  mov     rbx, [rdi]
0x18000fe8d  test    rbx, rbx
0x18000fe90  jz      short loc_18000FEB3
0x18000fe92  or      eax, 0FFFFFFFFh
0x18000fe95  lock xadd [rbx+118h], eax
0x18000fe9d  cmp     eax, 1
0x18000fea0  jnz     short loc_18000FEB3
0x18000fea2  mov     rcx, rbx
0x18000fea5  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000feaa  mov     rcx, rbx; pv
0x18000fead  call    cs:__imp_CoTaskMemFree
0x18000feb3  mov     rbx, [rsp+28h+arg_8]
0x18000feb8  add     rsp, 20h
0x18000febc  pop     rdi
0x18000febd  retn
```
