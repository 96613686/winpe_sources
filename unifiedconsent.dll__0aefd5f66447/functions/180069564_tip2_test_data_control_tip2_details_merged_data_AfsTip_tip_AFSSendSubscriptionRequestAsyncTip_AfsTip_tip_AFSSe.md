# tip2::test_data_control<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::~test_data_control<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>(void)

- ea: `0x180069564`
- end: `0x1800695e6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006a080`
- `0x18007b56c`
- `0x18007b5a0`
- `0x18007b5d4`
- `0x18007b608`
- `0x18007b63c`
- `0x18007b856`
- `0x18007bbb8`
- `0x18007bcd2`

## callees

- `0x180019838`
- `0x180069484`
- `0x180069564`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695d5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::~test_data_control<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 512), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 512), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180069564  mov     [rsp+arg_8], rbx
0x180069569  push    rdi
0x18006956a  sub     rsp, 20h
0x18006956e  mov     rdi, rcx
0x180069571  mov     rcx, [rcx]
0x180069574  test    rcx, rcx
0x180069577  jz      short loc_1800695B2
0x180069579  add     rcx, 8
0x18006957d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180069582  mov     rbx, [rdi]
0x180069585  mov     qword ptr [rdi], 0
0x18006958c  test    rbx, rbx
0x18006958f  jz      short loc_1800695B2
0x180069591  or      eax, 0FFFFFFFFh
0x180069594  lock xadd [rbx+200h], eax
0x18006959c  cmp     eax, 1
0x18006959f  jnz     short loc_1800695B2
0x1800695a1  mov     rcx, rbx
0x1800695a4  call    ??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)
0x1800695a9  mov     rcx, rbx; pv
0x1800695ac  call    cs:__imp_CoTaskMemFree
0x1800695b2  mov     rbx, [rdi]
0x1800695b5  test    rbx, rbx
0x1800695b8  jz      short loc_1800695DB
0x1800695ba  or      eax, 0FFFFFFFFh
0x1800695bd  lock xadd [rbx+200h], eax
0x1800695c5  cmp     eax, 1
0x1800695c8  jnz     short loc_1800695DB
0x1800695ca  mov     rcx, rbx
0x1800695cd  call    ??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)
0x1800695d2  mov     rcx, rbx; pv
0x1800695d5  call    cs:__imp_CoTaskMemFree
0x1800695db  mov     rbx, [rsp+28h+arg_8]
0x1800695e0  add     rsp, 20h
0x1800695e4  pop     rdi
0x1800695e5  retn
```
