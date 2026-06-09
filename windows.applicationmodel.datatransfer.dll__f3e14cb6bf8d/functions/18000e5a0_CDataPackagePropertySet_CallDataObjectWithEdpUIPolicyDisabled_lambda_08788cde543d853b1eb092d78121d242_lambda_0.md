# CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_08788cde543d853b1eb092d78121d242_>(_lambda_08788cde543d853b1eb092d78121d242_ &&)

- ea: `0x18000e5a0`
- end: `0x18000e86d`
- name: `??$_CallDataObjectWithEdpUIPolicyDisabled@V_lambda_08788cde543d853b1eb092d78121d242_@@@CDataPackagePropertySet@@AEAAJ$$QEAV_lambda_08788cde543d853b1eb092d78121d242_@@@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800595b0`

## callees

- `0x180004388`
- `0x180005180`
- `0x18000e5a0`
- `0x1800116e8`
- `0x180011810`
- `0x180016c04`
- `0x1800181f8`
- `0x180024b5c`
- `0x180025144`
- `0x180056e20`
- `0x1800570e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e78e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e78e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e761`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7c7`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e667`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e667`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_08788cde543d853b1eb092d78121d242_>(
        __int64 a1,
        unsigned __int16 ***a2)
{
  __int64 v4; // rcx
  __int64 v5; // r9
  int v6; // eax
  struct IDataObject *v7; // r14
  unsigned __int16 **v8; // rdi
  unsigned __int16 *v9; // rsi
  DWORD LastError; // ebx
  int EnterpriseId; // eax
  unsigned int v12; // esi
  bool v13; // dl
  const char *v14; // rax
  const char *v15; // rdi
  char v16; // cl
  _DWORD *v17; // rbx
  _DWORD *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  void *v20; // rbx
  struct IDataObject *v21; // rcx
  __int64 v22; // rcx
  struct IDataObject *v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-60h] BYREF
  struct IDataObject *v26[2]; // [rsp+28h] [rbp-58h] BYREF
  char v27; // [rsp+38h] [rbp-48h]
  _BYTE v28[8]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v29[48]; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-8h]
  char v31; // [rsp+B0h] [rbp+30h] BYREF

  v25 = 0;
  if ( (unsigned __int8)IsOleInitializePresent(a1) )
  {
    v4 = 0;
    v25 = 0;
    v5 = *(_QWORD *)(a1 + 192);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v5 + 24LL))(
             *(_QWORD *)(a1 + 192),
             &GUID_61ebf5c7_efea_4346_9554_981d7e198ffe,
             &v25);
      v4 = v25;
    }
    else
    {
      v6 = 0;
    }
    if ( v6 < 0 || !v4 )
      goto LABEL_42;
    v26[0] = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IDataObject **))v4)(
           v4,
           &GUID_0000010e_0000_0000_c000_000000000046,
           v26) >= 0 )
    {
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>>>((__int64)v28);
      if ( (unsigned int)EdpGetIsManaged() )
      {
        v31 = 1;
        EdpInlSetCurrentThreadPolicyEvaluation((void *)1);
      }
      else
      {
        v31 = 0;
      }
      v26[1] = (struct IDataObject *)&v31;
      v27 = 1;
      v7 = v26[0];
      v8 = *a2;
      v9 = *v8;
      if ( *v8 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v9);
        SetLastError(LastError);
      }
      *v8 = 0;
      EnterpriseId = DataObj_GetEnterpriseId(v7, v8);
      v12 = EnterpriseId;
      v13 = EnterpriseId < 0
         && (GUID *)_std_find_trivial_4(
                      &`DataTransferTip::UnexpectedHresult'::`2'::expectedErrors,
                      &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219,
                      (unsigned int)EnterpriseId) == &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219;
      v14 = "DataTransferTip::reason::resultFailed";
      v15 = "DataTransferTip::reason::resultFailed";
      v16 = 68;
      do
      {
        ++v14;
        if ( v16 == 58 )
          v15 = v14;
        v16 = *v14;
      }
      while ( *v14 );
      if ( v13 )
      {
        v17 = pv;
        EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
        ++v17[60];
        if ( (v17[18] & 0x100) == 0 )
          tip2::details::shared_data<0,0,1>::set_flag_value<long>(v17 + 2, 1, v15, v12);
        tip2::details::shared_data<0,0,1>::end_update((__int64)(v17 + 2));
      }
      v18 = pv;
      v19 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v18[18] |= 0x300u;
      if ( *((_QWORD *)v18 + 31) )
        tip2::details::shared_data<0,0,1>::complete_helper(v18 + 2, 2);
      if ( v19 )
        LeaveCriticalSection(v19);
      if ( v31 )
        EdpInlSetCurrentThreadPolicyEvaluation(0);
      v20 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(v20);
        CoTaskMemFree(v20);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v29);
      v21 = v26[0];
      if ( v26[0] )
      {
        v26[0] = 0;
        ((void (__fastcall *)(struct IDataObject *))v21->lpVtbl->Release)(v21);
      }
      v22 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      return v12;
    }
    v24 = v26[0];
    if ( v26[0] )
    {
      v26[0] = 0;
      ((void (__fastcall *)(struct IDataObject *))v24->lpVtbl->Release)(v24);
    }
  }
  v4 = v25;
LABEL_42:
  if ( v4 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e5a0  mov     [rsp-18h+arg_0], rbx
0x18000e5a5  mov     [rsp-18h+arg_8], rsi
0x18000e5aa  push    rbp
0x18000e5ab  push    rdi
0x18000e5ac  push    r14
0x18000e5ae  mov     rbp, rsp
0x18000e5b1  sub     rsp, 80h
0x18000e5b8  mov     rdi, rdx
0x18000e5bb  mov     rbx, rcx
0x18000e5be  mov     [rbp+var_60], 0
0x18000e5c6  call    IsOleInitializePresent
0x18000e5cb  test    al, al
0x18000e5cd  jz      loc_18000E835
0x18000e5d3  mov     rcx, [rbp+var_60]
0x18000e5d7  test    rcx, rcx
0x18000e5da  jz      short loc_18000E5F1
0x18000e5dc  mov     [rbp+var_60], 0
0x18000e5e4  mov     rax, [rcx]
0x18000e5e7  mov     rax, [rax+10h]
0x18000e5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f0  nop
0x18000e5f1  xor     ecx, ecx
0x18000e5f3  mov     [rbp+var_60], rcx
0x18000e5f7  mov     r9, [rbx+0C0h]
0x18000e5fe  test    r9, r9
0x18000e601  jnz     short loc_18000E607
0x18000e603  xor     eax, eax
0x18000e605  jmp     short loc_18000E625
0x18000e607  mov     rax, [r9]
0x18000e60a  lea     r8, [rbp+var_60]
0x18000e60e  lea     rdx, _GUID_61ebf5c7_efea_4346_9554_981d7e198ffe
0x18000e615  mov     rcx, r9
0x18000e618  mov     rax, [rax+18h]
0x18000e61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e621  mov     rcx, [rbp+var_60]
0x18000e625  test    eax, eax
0x18000e627  js      loc_18000E839
0x18000e62d  test    rcx, rcx
0x18000e630  jz      loc_18000E839
0x18000e636  mov     [rbp+var_58], 0
0x18000e63e  mov     rax, [rcx]
0x18000e641  lea     r8, [rbp+var_58]
0x18000e645  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x18000e64c  mov     rax, [rax]
0x18000e64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e654  nop
0x18000e655  test    eax, eax
0x18000e657  js      loc_18000E817
0x18000e65d  lea     rcx, [rbp+var_40]
0x18000e661  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000e666  nop
0x18000e667  call    cs:__imp_EdpGetIsManaged
0x18000e66d  test    eax, eax
0x18000e66f  jz      short loc_18000E681
0x18000e671  mov     [rbp+arg_10], 1
0x18000e675  mov     ecx, 1; int
0x18000e67a  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000e67f  jmp     short loc_18000E685
0x18000e681  mov     [rbp+arg_10], 0
0x18000e685  lea     rax, [rbp+arg_10]
0x18000e689  mov     [rbp+var_50], rax
0x18000e68d  mov     [rbp+var_48], 1
0x18000e691  mov     r14, [rbp+var_58]
0x18000e695  mov     rdi, [rdi]
0x18000e698  mov     rsi, [rdi]
0x18000e69b  test    rsi, rsi
0x18000e69e  jz      short loc_18000E6B9
0x18000e6a0  call    cs:__imp_GetLastError
0x18000e6a6  mov     ebx, eax
0x18000e6a8  mov     rcx, rsi; pv
0x18000e6ab  call    cs:__imp_CoTaskMemFree
0x18000e6b1  mov     ecx, ebx; dwErrCode
0x18000e6b3  call    cs:__imp_SetLastError
0x18000e6b9  mov     qword ptr [rdi], 0
0x18000e6c0  mov     rdx, rdi; unsigned __int16 **
0x18000e6c3  mov     rcx, r14; struct IDataObject *
0x18000e6c6  call    ?DataObj_GetEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z; DataObj_GetEnterpriseId(IDataObject *,ushort * *)
0x18000e6cb  mov     esi, eax
0x18000e6cd  test    eax, eax
0x18000e6cf  jns     short loc_18000E6F3
0x18000e6d1  mov     r8d, eax
0x18000e6d4  lea     rbx, _GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219
0x18000e6db  mov     rdx, rbx
0x18000e6de  lea     rcx, ?expectedErrors@?1??UnexpectedHresult@DataTransferTip@@YA_NJ@Z@4V?$array@J$01@std@@B; std::array<long,2> const `DataTransferTip::UnexpectedHresult(long)'::`2'::expectedErrors
0x18000e6e5  call    __std_find_trivial_4
0x18000e6ea  cmp     rax, rbx
0x18000e6ed  jnz     short loc_18000E6F3
0x18000e6ef  mov     dl, 1
0x18000e6f1  jmp     short loc_18000E6F5
0x18000e6f3  xor     dl, dl
0x18000e6f5  lea     rax, aDatatransferti; "DataTransferTip::reason::resultFailed"
0x18000e6fc  mov     rdi, rax
0x18000e6ff  mov     cl, 44h ; 'D'
0x18000e701  inc     rax
0x18000e704  cmp     cl, 3Ah ; ':'
0x18000e707  jnz     short loc_18000E70C
0x18000e709  mov     rdi, rax
0x18000e70c  mov     cl, [rax]
0x18000e70e  test    cl, cl
0x18000e710  jnz     short loc_18000E701
0x18000e712  test    dl, dl
0x18000e714  jz      short loc_18000E753
0x18000e716  mov     rbx, [rbp+pv]
0x18000e71a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000e721  call    cs:__imp_EnterCriticalSection
0x18000e727  inc     dword ptr [rbx+0F0h]
0x18000e72d  test    dword ptr [rbx+48h], 100h
0x18000e734  jnz     short loc_18000E74A
0x18000e736  mov     edx, 1
0x18000e73b  mov     r9d, esi
0x18000e73e  mov     r8, rdi
0x18000e741  lea     rcx, [rbx+8]
0x18000e745  call    ??$set_flag_value@J@?$shared_data@$0A@$0A@$00@details@tip2@@QEAAXGPEBDJ@Z; tip2::details::shared_data<0,0,1>::set_flag_value<long>(ushort,char const *,long)
0x18000e74a  lea     rcx, [rbx+8]
0x18000e74e  call    ?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::end_update(void)
0x18000e753  mov     rbx, [rbp+pv]
0x18000e757  lea     rdi, [rbx+0C8h]
0x18000e75e  mov     rcx, rdi; lpCriticalSection
0x18000e761  call    cs:__imp_EnterCriticalSection
0x18000e767  or      dword ptr [rbx+48h], 300h
0x18000e76e  cmp     qword ptr [rbx+0F8h], 0
0x18000e776  jz      short loc_18000E786
0x18000e778  mov     edx, 2
0x18000e77d  lea     rcx, [rbx+8]
0x18000e781  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x18000e786  test    rdi, rdi
0x18000e789  jz      short loc_18000E795
0x18000e78b  mov     rcx, rdi; lpCriticalSection
0x18000e78e  call    cs:__imp_LeaveCriticalSection
0x18000e794  nop
0x18000e795  cmp     [rbp+arg_10], 0
0x18000e799  jz      short loc_18000E7A3
0x18000e79b  xor     ecx, ecx; int
0x18000e79d  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000e7a2  nop
0x18000e7a3  mov     rbx, [rbp+pv]
0x18000e7a7  test    rbx, rbx
0x18000e7aa  jz      short loc_18000E7CD
0x18000e7ac  or      eax, 0FFFFFFFFh
0x18000e7af  lock xadd [rbx+150h], eax
0x18000e7b7  cmp     eax, 1
0x18000e7ba  jnz     short loc_18000E7CD
0x18000e7bc  mov     rcx, rbx
0x18000e7bf  call    ??1?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(void)
0x18000e7c4  mov     rcx, rbx; pv
0x18000e7c7  call    cs:__imp_CoTaskMemFree
0x18000e7cd  lea     rcx, [rbp+var_38]; this
0x18000e7d1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000e7d6  nop
0x18000e7d7  mov     rcx, [rbp+var_58]
0x18000e7db  test    rcx, rcx
0x18000e7de  jz      short loc_18000E7F5
0x18000e7e0  mov     [rbp+var_58], 0
0x18000e7e8  mov     rax, [rcx]
0x18000e7eb  mov     rax, [rax+10h]
0x18000e7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f4  nop
0x18000e7f5  mov     rcx, [rbp+var_60]
0x18000e7f9  test    rcx, rcx
0x18000e7fc  jz      short loc_18000E813
0x18000e7fe  mov     [rbp+var_60], 0
0x18000e806  mov     rax, [rcx]
0x18000e809  mov     rax, [rax+10h]
0x18000e80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e812  nop
0x18000e813  mov     eax, esi
0x18000e815  jmp     short loc_18000E855
0x18000e817  mov     rcx, [rbp+var_58]
0x18000e81b  test    rcx, rcx
0x18000e81e  jz      short loc_18000E835
0x18000e820  mov     [rbp+var_58], 0
0x18000e828  mov     rax, [rcx]
0x18000e82b  mov     rax, [rax+10h]
0x18000e82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e834  nop
0x18000e835  mov     rcx, [rbp+var_60]
0x18000e839  test    rcx, rcx
0x18000e83c  jz      short loc_18000E853
0x18000e83e  mov     [rbp+var_60], 0
0x18000e846  mov     rax, [rcx]
0x18000e849  mov     rax, [rax+10h]
0x18000e84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e852  nop
0x18000e853  xor     eax, eax
0x18000e855  lea     r11, [rsp+80h+var_s0]
0x18000e85d  mov     rbx, [r11+20h]
0x18000e861  mov     rsi, [r11+28h]
0x18000e865  mov     rsp, r11
0x18000e868  pop     r14
0x18000e86a  pop     rdi
0x18000e86b  pop     rbp
0x18000e86c  retn
```
