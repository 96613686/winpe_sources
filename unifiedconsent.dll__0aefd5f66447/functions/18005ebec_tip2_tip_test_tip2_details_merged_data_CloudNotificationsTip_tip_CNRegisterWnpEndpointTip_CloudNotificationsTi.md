# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::ensure_data(void)

- ea: `0x18005ebec`
- end: `0x18005ec78`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058c58`
- `0x18005d2e8`
- `0x18006006c`

## callees

- `0x180057c38`
- `0x180058544`
- `0x18005ebec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec64`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 96, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 96, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005ebec  mov     [rsp+arg_10], rbx
0x18005ebf1  push    rdi
0x18005ebf2  sub     rsp, 20h
0x18005ebf6  cmp     qword ptr [rcx], 0
0x18005ebfa  mov     rdi, rcx
0x18005ebfd  jnz     short loc_18005EC6A
0x18005ebff  lea     rcx, [rsp+28h+pv]
0x18005ec04  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>,>(void)
0x18005ec09  mov     rdx, [rax]
0x18005ec0c  mov     qword ptr [rax], 0
0x18005ec13  mov     rbx, [rdi]
0x18005ec16  mov     [rdi], rdx
0x18005ec19  test    rbx, rbx
0x18005ec1c  jz      short loc_18005EC3F
0x18005ec1e  or      eax, 0FFFFFFFFh
0x18005ec21  lock xadd [rbx+180h], eax
0x18005ec29  cmp     eax, 1
0x18005ec2c  jnz     short loc_18005EC3F
0x18005ec2e  mov     rcx, rbx
0x18005ec31  call    ??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)
0x18005ec36  mov     rcx, rbx; pv
0x18005ec39  call    cs:__imp_CoTaskMemFree
0x18005ec3f  mov     rbx, [rsp+28h+pv]
0x18005ec44  test    rbx, rbx
0x18005ec47  jz      short loc_18005EC6A
0x18005ec49  or      eax, 0FFFFFFFFh
0x18005ec4c  lock xadd [rbx+180h], eax
0x18005ec54  cmp     eax, 1
0x18005ec57  jnz     short loc_18005EC6A
0x18005ec59  mov     rcx, rbx
0x18005ec5c  call    ??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)
0x18005ec61  mov     rcx, rbx; pv
0x18005ec64  call    cs:__imp_CoTaskMemFree
0x18005ec6a  mov     rbx, [rsp+28h+arg_10]
0x18005ec6f  mov     rax, rdi
0x18005ec72  add     rsp, 20h
0x18005ec76  pop     rdi
0x18005ec77  retn
```
