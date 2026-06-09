# tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>::ensure_data(void)

- ea: `0x18002e2f8`
- end: `0x18002e384`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023704`
- `0x18002aae0`
- `0x18002f4bc`

## callees

- `0x1800212fc`
- `0x180022a38`
- `0x18002e2f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e370`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e370`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e2f8  mov     [rsp+arg_10], rbx
0x18002e2fd  push    rdi
0x18002e2fe  sub     rsp, 20h
0x18002e302  cmp     qword ptr [rcx], 0
0x18002e306  mov     rdi, rcx
0x18002e309  jnz     short loc_18002E376
0x18002e30b  lea     rcx, [rsp+28h+pv]
0x18002e310  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>,>(void)
0x18002e315  mov     rdx, [rax]
0x18002e318  mov     qword ptr [rax], 0
0x18002e31f  mov     rbx, [rdi]
0x18002e322  mov     [rdi], rdx
0x18002e325  test    rbx, rbx
0x18002e328  jz      short loc_18002E34B
0x18002e32a  or      eax, 0FFFFFFFFh
0x18002e32d  lock xadd [rbx+138h], eax
0x18002e335  cmp     eax, 1
0x18002e338  jnz     short loc_18002E34B
0x18002e33a  mov     rcx, rbx
0x18002e33d  call    ??1?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(void)
0x18002e342  mov     rcx, rbx; pv
0x18002e345  call    cs:__imp_CoTaskMemFree
0x18002e34b  mov     rbx, [rsp+28h+pv]
0x18002e350  test    rbx, rbx
0x18002e353  jz      short loc_18002E376
0x18002e355  or      eax, 0FFFFFFFFh
0x18002e358  lock xadd [rbx+138h], eax
0x18002e360  cmp     eax, 1
0x18002e363  jnz     short loc_18002E376
0x18002e365  mov     rcx, rbx
0x18002e368  call    ??1?$merged_data@U_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest,ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest>(void)
0x18002e36d  mov     rcx, rbx; pv
0x18002e370  call    cs:__imp_CoTaskMemFree
0x18002e376  mov     rbx, [rsp+28h+arg_10]
0x18002e37b  mov     rax, rdi
0x18002e37e  add     rsp, 20h
0x18002e382  pop     rdi
0x18002e383  retn
```
