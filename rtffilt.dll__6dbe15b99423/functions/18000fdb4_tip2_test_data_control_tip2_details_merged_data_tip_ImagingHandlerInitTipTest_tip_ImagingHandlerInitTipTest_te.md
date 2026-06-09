# tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)

- ea: `0x18000fdb4`
- end: `0x18000fe36`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010b80`
- `0x18001a66d`

## callees

- `0x18000fc3c`
- `0x18000fdb4`
- `0x180015e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe25`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 312), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 312), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x18000fdb4  mov     [rsp+arg_8], rbx
0x18000fdb9  push    rdi
0x18000fdba  sub     rsp, 20h
0x18000fdbe  mov     rdi, rcx
0x18000fdc1  mov     rcx, [rcx]
0x18000fdc4  test    rcx, rcx
0x18000fdc7  jz      short loc_18000FE02
0x18000fdc9  add     rcx, 8
0x18000fdcd  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x18000fdd2  mov     rbx, [rdi]
0x18000fdd5  mov     qword ptr [rdi], 0
0x18000fddc  test    rbx, rbx
0x18000fddf  jz      short loc_18000FE02
0x18000fde1  or      eax, 0FFFFFFFFh
0x18000fde4  lock xadd [rbx+138h], eax
0x18000fdec  cmp     eax, 1
0x18000fdef  jnz     short loc_18000FE02
0x18000fdf1  mov     rcx, rbx
0x18000fdf4  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x18000fdf9  mov     rcx, rbx; pv
0x18000fdfc  call    cs:__imp_CoTaskMemFree
0x18000fe02  mov     rbx, [rdi]
0x18000fe05  test    rbx, rbx
0x18000fe08  jz      short loc_18000FE2B
0x18000fe0a  or      eax, 0FFFFFFFFh
0x18000fe0d  lock xadd [rbx+138h], eax
0x18000fe15  cmp     eax, 1
0x18000fe18  jnz     short loc_18000FE2B
0x18000fe1a  mov     rcx, rbx
0x18000fe1d  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x18000fe22  mov     rcx, rbx; pv
0x18000fe25  call    cs:__imp_CoTaskMemFree
0x18000fe2b  mov     rbx, [rsp+28h+arg_8]
0x18000fe30  add     rsp, 20h
0x18000fe34  pop     rdi
0x18000fe35  retn
```
