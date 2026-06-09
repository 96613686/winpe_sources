# tip2::test_data_control<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::~test_data_control<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>(void)

- ea: `0x180060ed8`
- end: `0x180060f5a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180061d10`
- `0x18007a073`
- `0x18007a2f4`

## callees

- `0x180019838`
- `0x180060e40`
- `0x180060ed8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f49`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::~test_data_control<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>(
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
        tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180060ed8  mov     [rsp+arg_8], rbx
0x180060edd  push    rdi
0x180060ede  sub     rsp, 20h
0x180060ee2  mov     rdi, rcx
0x180060ee5  mov     rcx, [rcx]
0x180060ee8  test    rcx, rcx
0x180060eeb  jz      short loc_180060F26
0x180060eed  add     rcx, 8
0x180060ef1  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180060ef6  mov     rbx, [rdi]
0x180060ef9  mov     qword ptr [rdi], 0
0x180060f00  test    rbx, rbx
0x180060f03  jz      short loc_180060F26
0x180060f05  or      eax, 0FFFFFFFFh
0x180060f08  lock xadd [rbx+138h], eax
0x180060f10  cmp     eax, 1
0x180060f13  jnz     short loc_180060F26
0x180060f15  mov     rcx, rbx
0x180060f18  call    ??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)
0x180060f1d  mov     rcx, rbx; pv
0x180060f20  call    cs:__imp_CoTaskMemFree
0x180060f26  mov     rbx, [rdi]
0x180060f29  test    rbx, rbx
0x180060f2c  jz      short loc_180060F4F
0x180060f2e  or      eax, 0FFFFFFFFh
0x180060f31  lock xadd [rbx+138h], eax
0x180060f39  cmp     eax, 1
0x180060f3c  jnz     short loc_180060F4F
0x180060f3e  mov     rcx, rbx
0x180060f41  call    ??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)
0x180060f46  mov     rcx, rbx; pv
0x180060f49  call    cs:__imp_CoTaskMemFree
0x180060f4f  mov     rbx, [rsp+28h+arg_8]
0x180060f54  add     rsp, 20h
0x180060f58  pop     rdi
0x180060f59  retn
```
