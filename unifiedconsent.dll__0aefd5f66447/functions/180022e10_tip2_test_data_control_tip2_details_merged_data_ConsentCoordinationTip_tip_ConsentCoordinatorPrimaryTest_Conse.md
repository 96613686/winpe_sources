# tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>(void)

- ea: `0x180022e10`
- end: `0x180022e92`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800264c0`
- `0x1800729dc`

## callees

- `0x180019838`
- `0x180022b50`
- `0x180022e10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e81`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180022e10  mov     [rsp+arg_8], rbx
0x180022e15  push    rdi
0x180022e16  sub     rsp, 20h
0x180022e1a  mov     rdi, rcx
0x180022e1d  mov     rcx, [rcx]
0x180022e20  test    rcx, rcx
0x180022e23  jz      short loc_180022E5E
0x180022e25  add     rcx, 8
0x180022e29  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180022e2e  mov     rbx, [rdi]
0x180022e31  mov     qword ptr [rdi], 0
0x180022e38  test    rbx, rbx
0x180022e3b  jz      short loc_180022E5E
0x180022e3d  or      eax, 0FFFFFFFFh
0x180022e40  lock xadd [rbx+118h], eax
0x180022e48  cmp     eax, 1
0x180022e4b  jnz     short loc_180022E5E
0x180022e4d  mov     rcx, rbx
0x180022e50  call    ??1?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(void)
0x180022e55  mov     rcx, rbx; pv
0x180022e58  call    cs:__imp_CoTaskMemFree
0x180022e5e  mov     rbx, [rdi]
0x180022e61  test    rbx, rbx
0x180022e64  jz      short loc_180022E87
0x180022e66  or      eax, 0FFFFFFFFh
0x180022e69  lock xadd [rbx+118h], eax
0x180022e71  cmp     eax, 1
0x180022e74  jnz     short loc_180022E87
0x180022e76  mov     rcx, rbx
0x180022e79  call    ??1?$merged_data@U_tip_ConsentCoordinatorPrimaryTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest,ConsentCoordinationTip::_tip_ConsentCoordinatorPrimaryTest>(void)
0x180022e7e  mov     rcx, rbx; pv
0x180022e81  call    cs:__imp_CoTaskMemFree
0x180022e87  mov     rbx, [rsp+28h+arg_8]
0x180022e8c  add     rsp, 20h
0x180022e90  pop     rdi
0x180022e91  retn
```
