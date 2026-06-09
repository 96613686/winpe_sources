# tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::ensure_data(void)

- ea: `0x18002e38c`
- end: `0x18002e418`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024678`
- `0x1800254a8`

## callees

- `0x1800213f0`
- `0x180022ac4`
- `0x18002e38c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e404`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **ConsentState; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    ConsentState = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>,>(&pv);
    v3 = *ConsentState;
    *ConsentState = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e38c  mov     [rsp+arg_10], rbx
0x18002e391  push    rdi
0x18002e392  sub     rsp, 20h
0x18002e396  cmp     qword ptr [rcx], 0
0x18002e39a  mov     rdi, rcx
0x18002e39d  jnz     short loc_18002E40A
0x18002e39f  lea     rcx, [rsp+28h+pv]
0x18002e3a4  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>,>(void)
0x18002e3a9  mov     rdx, [rax]
0x18002e3ac  mov     qword ptr [rax], 0
0x18002e3b3  mov     rbx, [rdi]
0x18002e3b6  mov     [rdi], rdx
0x18002e3b9  test    rbx, rbx
0x18002e3bc  jz      short loc_18002E3DF
0x18002e3be  or      eax, 0FFFFFFFFh
0x18002e3c1  lock xadd [rbx+118h], eax
0x18002e3c9  cmp     eax, 1
0x18002e3cc  jnz     short loc_18002E3DF
0x18002e3ce  mov     rcx, rbx
0x18002e3d1  call    ??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)
0x18002e3d6  mov     rcx, rbx; pv
0x18002e3d9  call    cs:__imp_CoTaskMemFree
0x18002e3df  mov     rbx, [rsp+28h+pv]
0x18002e3e4  test    rbx, rbx
0x18002e3e7  jz      short loc_18002E40A
0x18002e3e9  or      eax, 0FFFFFFFFh
0x18002e3ec  lock xadd [rbx+118h], eax
0x18002e3f4  cmp     eax, 1
0x18002e3f7  jnz     short loc_18002E40A
0x18002e3f9  mov     rcx, rbx
0x18002e3fc  call    ??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)
0x18002e401  mov     rcx, rbx; pv
0x18002e404  call    cs:__imp_CoTaskMemFree
0x18002e40a  mov     rbx, [rsp+28h+arg_10]
0x18002e40f  mov     rax, rdi
0x18002e412  add     rsp, 20h
0x18002e416  pop     rdi
0x18002e417  retn
```
