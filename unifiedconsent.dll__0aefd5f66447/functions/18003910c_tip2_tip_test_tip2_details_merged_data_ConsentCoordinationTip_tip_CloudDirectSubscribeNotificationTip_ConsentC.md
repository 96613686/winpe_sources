# tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>::ensure_data(void)

- ea: `0x18003910c`
- end: `0x180039198`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032f48`
- `0x1800334a0`

## callees

- `0x180031dac`
- `0x1800327f8`
- `0x18003910c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039184`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003910c  mov     [rsp+arg_10], rbx
0x180039111  push    rdi
0x180039112  sub     rsp, 20h
0x180039116  cmp     qword ptr [rcx], 0
0x18003911a  mov     rdi, rcx
0x18003911d  jnz     short loc_18003918A
0x18003911f  lea     rcx, [rsp+28h+pv]
0x180039124  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>,>(void)
0x180039129  mov     rdx, [rax]
0x18003912c  mov     qword ptr [rax], 0
0x180039133  mov     rbx, [rdi]
0x180039136  mov     [rdi], rdx
0x180039139  test    rbx, rbx
0x18003913c  jz      short loc_18003915F
0x18003913e  or      eax, 0FFFFFFFFh
0x180039141  lock xadd [rbx+138h], eax
0x180039149  cmp     eax, 1
0x18003914c  jnz     short loc_18003915F
0x18003914e  mov     rcx, rbx
0x180039151  call    ??1?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(void)
0x180039156  mov     rcx, rbx; pv
0x180039159  call    cs:__imp_CoTaskMemFree
0x18003915f  mov     rbx, [rsp+28h+pv]
0x180039164  test    rbx, rbx
0x180039167  jz      short loc_18003918A
0x180039169  or      eax, 0FFFFFFFFh
0x18003916c  lock xadd [rbx+138h], eax
0x180039174  cmp     eax, 1
0x180039177  jnz     short loc_18003918A
0x180039179  mov     rcx, rbx
0x18003917c  call    ??1?$merged_data@U_tip_CloudDirectSubscribeNotificationTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>::~merged_data<ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip,ConsentCoordinationTip::_tip_CloudDirectSubscribeNotificationTip>(void)
0x180039181  mov     rcx, rbx; pv
0x180039184  call    cs:__imp_CoTaskMemFree
0x18003918a  mov     rbx, [rsp+28h+arg_10]
0x18003918f  mov     rax, rdi
0x180039192  add     rsp, 20h
0x180039196  pop     rdi
0x180039197  retn
```
