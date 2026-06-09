# tip2::tip_test<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>::ensure_data(void)

- ea: `0x1800555ac`
- end: `0x180055638`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800519bc`
- `0x180052980`

## callees

- `0x180050fd8`
- `0x1800515bc`
- `0x1800555ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800555f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800555f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055624`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 80, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 80, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800555ac  mov     [rsp+arg_10], rbx
0x1800555b1  push    rdi
0x1800555b2  sub     rsp, 20h
0x1800555b6  cmp     qword ptr [rcx], 0
0x1800555ba  mov     rdi, rcx
0x1800555bd  jnz     short loc_18005562A
0x1800555bf  lea     rcx, [rsp+28h+pv]
0x1800555c4  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>,>(void)
0x1800555c9  mov     rdx, [rax]
0x1800555cc  mov     qword ptr [rax], 0
0x1800555d3  mov     rbx, [rdi]
0x1800555d6  mov     [rdi], rdx
0x1800555d9  test    rbx, rbx
0x1800555dc  jz      short loc_1800555FF
0x1800555de  or      eax, 0FFFFFFFFh
0x1800555e1  lock xadd [rbx+140h], eax
0x1800555e9  cmp     eax, 1
0x1800555ec  jnz     short loc_1800555FF
0x1800555ee  mov     rcx, rbx
0x1800555f1  call    ??1?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(void)
0x1800555f6  mov     rcx, rbx; pv
0x1800555f9  call    cs:__imp_CoTaskMemFree
0x1800555ff  mov     rbx, [rsp+28h+pv]
0x180055604  test    rbx, rbx
0x180055607  jz      short loc_18005562A
0x180055609  or      eax, 0FFFFFFFFh
0x18005560c  lock xadd [rbx+140h], eax
0x180055614  cmp     eax, 1
0x180055617  jnz     short loc_18005562A
0x180055619  mov     rcx, rbx
0x18005561c  call    ??1?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(void)
0x180055621  mov     rcx, rbx; pv
0x180055624  call    cs:__imp_CoTaskMemFree
0x18005562a  mov     rbx, [rsp+28h+arg_10]
0x18005562f  mov     rax, rdi
0x180055632  add     rsp, 20h
0x180055636  pop     rdi
0x180055637  retn
```
