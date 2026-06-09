# tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>::ensure_data(void)

- ea: `0x18002e420`
- end: `0x18002e4ac`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800264c0`
- `0x1800729dc`

## callees

- `0x1800214b4`
- `0x180022b50`
- `0x18002e420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e498`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e420  mov     [rsp+arg_10], rbx
0x18002e425  push    rdi
0x18002e426  sub     rsp, 20h
0x18002e42a  cmp     qword ptr [rcx], 0
0x18002e42e  mov     rdi, rcx
0x18002e431  jnz     short loc_18002E49E
0x18002e433  lea     rcx, [rsp+28h+pv]
0x18002e438  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>,>(void)
0x18002e43d  mov     rdx, [rax]
0x18002e440  mov     qword ptr [rax], 0
0x18002e447  mov     rbx, [rdi]
0x18002e44a  mov     [rdi], rdx
0x18002e44d  test    rbx, rbx
0x18002e450  jz      short loc_18002E473
0x18002e452  or      eax, 0FFFFFFFFh
0x18002e455  lock xadd [rbx+118h], eax
0x18002e45d  cmp     eax, 1
0x18002e460  jnz     short loc_18002E473
0x18002e462  mov     rcx, rbx
0x18002e465  call    ??1?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(void)
0x18002e46a  mov     rcx, rbx; pv
0x18002e46d  call    cs:__imp_CoTaskMemFree
0x18002e473  mov     rbx, [rsp+28h+pv]
0x18002e478  test    rbx, rbx
0x18002e47b  jz      short loc_18002E49E
0x18002e47d  or      eax, 0FFFFFFFFh
0x18002e480  lock xadd [rbx+118h], eax
0x18002e488  cmp     eax, 1
0x18002e48b  jnz     short loc_18002E49E
0x18002e48d  mov     rcx, rbx
0x18002e490  call    ??1?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(void)
0x18002e495  mov     rcx, rbx; pv
0x18002e498  call    cs:__imp_CoTaskMemFree
0x18002e49e  mov     rbx, [rsp+28h+arg_10]
0x18002e4a3  mov     rax, rdi
0x18002e4a6  add     rsp, 20h
0x18002e4aa  pop     rdi
0x18002e4ab  retn
```
