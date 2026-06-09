# tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::ensure_data(void)

- ea: `0x18006c260`
- end: `0x18006c2ec`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006974c`
- `0x18006a080`
- `0x18006cad0`

## callees

- `0x180069208`
- `0x180069484`
- `0x18006c260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c2d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c2d8`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 128, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 128, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18006c260  mov     [rsp+arg_10], rbx
0x18006c265  push    rdi
0x18006c266  sub     rsp, 20h
0x18006c26a  cmp     qword ptr [rcx], 0
0x18006c26e  mov     rdi, rcx
0x18006c271  jnz     short loc_18006C2DE
0x18006c273  lea     rcx, [rsp+28h+pv]
0x18006c278  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>,>(void)
0x18006c27d  mov     rdx, [rax]
0x18006c280  mov     qword ptr [rax], 0
0x18006c287  mov     rbx, [rdi]
0x18006c28a  mov     [rdi], rdx
0x18006c28d  test    rbx, rbx
0x18006c290  jz      short loc_18006C2B3
0x18006c292  or      eax, 0FFFFFFFFh
0x18006c295  lock xadd [rbx+200h], eax
0x18006c29d  cmp     eax, 1
0x18006c2a0  jnz     short loc_18006C2B3
0x18006c2a2  mov     rcx, rbx
0x18006c2a5  call    ??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)
0x18006c2aa  mov     rcx, rbx; pv
0x18006c2ad  call    cs:__imp_CoTaskMemFree
0x18006c2b3  mov     rbx, [rsp+28h+pv]
0x18006c2b8  test    rbx, rbx
0x18006c2bb  jz      short loc_18006C2DE
0x18006c2bd  or      eax, 0FFFFFFFFh
0x18006c2c0  lock xadd [rbx+200h], eax
0x18006c2c8  cmp     eax, 1
0x18006c2cb  jnz     short loc_18006C2DE
0x18006c2cd  mov     rcx, rbx
0x18006c2d0  call    ??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)
0x18006c2d5  mov     rcx, rbx; pv
0x18006c2d8  call    cs:__imp_CoTaskMemFree
0x18006c2de  mov     rbx, [rsp+28h+arg_10]
0x18006c2e3  mov     rax, rdi
0x18006c2e6  add     rsp, 20h
0x18006c2ea  pop     rdi
0x18006c2eb  retn
```
