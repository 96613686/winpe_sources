# tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::ensure_data(void)

- ea: `0x180067ca8`
- end: `0x180067d34`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800611c8`
- `0x180061d10`
- `0x1800685c8`

## callees

- `0x180060614`
- `0x180060e40`
- `0x180067ca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067d20`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180067ca8  mov     [rsp+arg_10], rbx
0x180067cad  push    rdi
0x180067cae  sub     rsp, 20h
0x180067cb2  cmp     qword ptr [rcx], 0
0x180067cb6  mov     rdi, rcx
0x180067cb9  jnz     short loc_180067D26
0x180067cbb  lea     rcx, [rsp+28h+pv]
0x180067cc0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>,>(void)
0x180067cc5  mov     rdx, [rax]
0x180067cc8  mov     qword ptr [rax], 0
0x180067ccf  mov     rbx, [rdi]
0x180067cd2  mov     [rdi], rdx
0x180067cd5  test    rbx, rbx
0x180067cd8  jz      short loc_180067CFB
0x180067cda  or      eax, 0FFFFFFFFh
0x180067cdd  lock xadd [rbx+138h], eax
0x180067ce5  cmp     eax, 1
0x180067ce8  jnz     short loc_180067CFB
0x180067cea  mov     rcx, rbx
0x180067ced  call    ??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)
0x180067cf2  mov     rcx, rbx; pv
0x180067cf5  call    cs:__imp_CoTaskMemFree
0x180067cfb  mov     rbx, [rsp+28h+pv]
0x180067d00  test    rbx, rbx
0x180067d03  jz      short loc_180067D26
0x180067d05  or      eax, 0FFFFFFFFh
0x180067d08  lock xadd [rbx+138h], eax
0x180067d10  cmp     eax, 1
0x180067d13  jnz     short loc_180067D26
0x180067d15  mov     rcx, rbx
0x180067d18  call    ??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)
0x180067d1d  mov     rcx, rbx; pv
0x180067d20  call    cs:__imp_CoTaskMemFree
0x180067d26  mov     rbx, [rsp+28h+arg_10]
0x180067d2b  mov     rax, rdi
0x180067d2e  add     rsp, 20h
0x180067d32  pop     rdi
0x180067d33  retn
```
