# tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(void)

- ea: `0x180015fc0`
- end: `0x18001604c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eb50`
- `0x180010f28`

## callees

- `0x18000f648`
- `0x18000fcd4`
- `0x180015fc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001600d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001600d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016038`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180015fc0  mov     [rsp+arg_10], rbx
0x180015fc5  push    rdi
0x180015fc6  sub     rsp, 20h
0x180015fca  cmp     qword ptr [rcx], 0
0x180015fce  mov     rdi, rcx
0x180015fd1  jnz     short loc_18001603E
0x180015fd3  lea     rcx, [rsp+28h+pv]
0x180015fd8  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,>(void)
0x180015fdd  mov     rdx, [rax]
0x180015fe0  mov     qword ptr [rax], 0
0x180015fe7  mov     rbx, [rdi]
0x180015fea  mov     [rdi], rdx
0x180015fed  test    rbx, rbx
0x180015ff0  jz      short loc_180016013
0x180015ff2  or      eax, 0FFFFFFFFh
0x180015ff5  lock xadd [rbx+118h], eax
0x180015ffd  cmp     eax, 1
0x180016000  jnz     short loc_180016013
0x180016002  mov     rcx, rbx
0x180016005  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18001600a  mov     rcx, rbx; pv
0x18001600d  call    cs:__imp_CoTaskMemFree
0x180016013  mov     rbx, [rsp+28h+pv]
0x180016018  test    rbx, rbx
0x18001601b  jz      short loc_18001603E
0x18001601d  or      eax, 0FFFFFFFFh
0x180016020  lock xadd [rbx+118h], eax
0x180016028  cmp     eax, 1
0x18001602b  jnz     short loc_18001603E
0x18001602d  mov     rcx, rbx
0x180016030  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x180016035  mov     rcx, rbx; pv
0x180016038  call    cs:__imp_CoTaskMemFree
0x18001603e  mov     rbx, [rsp+28h+arg_10]
0x180016043  mov     rax, rdi
0x180016046  add     rsp, 20h
0x18001604a  pop     rdi
0x18001604b  retn
```
