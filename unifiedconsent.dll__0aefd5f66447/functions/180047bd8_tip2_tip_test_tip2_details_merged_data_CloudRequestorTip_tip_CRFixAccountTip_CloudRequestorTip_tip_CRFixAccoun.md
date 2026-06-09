# tip2::tip_test<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>::ensure_data(void)

- ea: `0x180047bd8`
- end: `0x180047c64`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041410`
- `0x180075b7b`

## callees

- `0x18003fe84`
- `0x180040674`
- `0x180047bd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c50`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180047bd8  mov     [rsp+arg_10], rbx
0x180047bdd  push    rdi
0x180047bde  sub     rsp, 20h
0x180047be2  cmp     qword ptr [rcx], 0
0x180047be6  mov     rdi, rcx
0x180047be9  jnz     short loc_180047C56
0x180047beb  lea     rcx, [rsp+28h+pv]
0x180047bf0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>,>(void)
0x180047bf5  mov     rdx, [rax]
0x180047bf8  mov     qword ptr [rax], 0
0x180047bff  mov     rbx, [rdi]
0x180047c02  mov     [rdi], rdx
0x180047c05  test    rbx, rbx
0x180047c08  jz      short loc_180047C2B
0x180047c0a  or      eax, 0FFFFFFFFh
0x180047c0d  lock xadd [rbx+138h], eax
0x180047c15  cmp     eax, 1
0x180047c18  jnz     short loc_180047C2B
0x180047c1a  mov     rcx, rbx
0x180047c1d  call    ??1?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(void)
0x180047c22  mov     rcx, rbx; pv
0x180047c25  call    cs:__imp_CoTaskMemFree
0x180047c2b  mov     rbx, [rsp+28h+pv]
0x180047c30  test    rbx, rbx
0x180047c33  jz      short loc_180047C56
0x180047c35  or      eax, 0FFFFFFFFh
0x180047c38  lock xadd [rbx+138h], eax
0x180047c40  cmp     eax, 1
0x180047c43  jnz     short loc_180047C56
0x180047c45  mov     rcx, rbx
0x180047c48  call    ??1?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(void)
0x180047c4d  mov     rcx, rbx; pv
0x180047c50  call    cs:__imp_CoTaskMemFree
0x180047c56  mov     rbx, [rsp+28h+arg_10]
0x180047c5b  mov     rax, rdi
0x180047c5e  add     rsp, 20h
0x180047c62  pop     rdi
0x180047c63  retn
```
