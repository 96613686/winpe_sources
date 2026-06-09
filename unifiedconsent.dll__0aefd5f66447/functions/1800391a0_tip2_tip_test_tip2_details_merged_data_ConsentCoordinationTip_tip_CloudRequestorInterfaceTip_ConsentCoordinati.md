# tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(void)

- ea: `0x1800391a0`
- end: `0x18003922c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036900`
- `0x1800750be`

## callees

- `0x180031e98`
- `0x180032890`
- `0x1800391a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039218`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800391a0  mov     [rsp+arg_10], rbx
0x1800391a5  push    rdi
0x1800391a6  sub     rsp, 20h
0x1800391aa  cmp     qword ptr [rcx], 0
0x1800391ae  mov     rdi, rcx
0x1800391b1  jnz     short loc_18003921E
0x1800391b3  lea     rcx, [rsp+28h+pv]
0x1800391b8  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>,>(void)
0x1800391bd  mov     rdx, [rax]
0x1800391c0  mov     qword ptr [rax], 0
0x1800391c7  mov     rbx, [rdi]
0x1800391ca  mov     [rdi], rdx
0x1800391cd  test    rbx, rbx
0x1800391d0  jz      short loc_1800391F3
0x1800391d2  or      eax, 0FFFFFFFFh
0x1800391d5  lock xadd [rbx+138h], eax
0x1800391dd  cmp     eax, 1
0x1800391e0  jnz     short loc_1800391F3
0x1800391e2  mov     rcx, rbx
0x1800391e5  call    ??1?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(void)
0x1800391ea  mov     rcx, rbx; pv
0x1800391ed  call    cs:__imp_CoTaskMemFree
0x1800391f3  mov     rbx, [rsp+28h+pv]
0x1800391f8  test    rbx, rbx
0x1800391fb  jz      short loc_18003921E
0x1800391fd  or      eax, 0FFFFFFFFh
0x180039200  lock xadd [rbx+138h], eax
0x180039208  cmp     eax, 1
0x18003920b  jnz     short loc_18003921E
0x18003920d  mov     rcx, rbx
0x180039210  call    ??1?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(void)
0x180039215  mov     rcx, rbx; pv
0x180039218  call    cs:__imp_CoTaskMemFree
0x18003921e  mov     rbx, [rsp+28h+arg_10]
0x180039223  mov     rax, rdi
0x180039226  add     rsp, 20h
0x18003922a  pop     rdi
0x18003922b  retn
```
