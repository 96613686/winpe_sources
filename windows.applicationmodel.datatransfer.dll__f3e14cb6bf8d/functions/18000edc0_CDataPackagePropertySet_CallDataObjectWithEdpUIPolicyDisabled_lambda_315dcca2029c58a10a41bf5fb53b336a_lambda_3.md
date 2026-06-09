# CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_315dcca2029c58a10a41bf5fb53b336a_>(_lambda_315dcca2029c58a10a41bf5fb53b336a_ &&)

- ea: `0x18000edc0`
- end: `0x18000f094`
- name: `??$_CallDataObjectWithEdpUIPolicyDisabled@V_lambda_315dcca2029c58a10a41bf5fb53b336a_@@@CDataPackagePropertySet@@AEAAJ$$QEAV_lambda_315dcca2029c58a10a41bf5fb53b336a_@@@Z`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180058360`

## callees

- `0x180004388`
- `0x180005180`
- `0x18000edc0`
- `0x1800116e8`
- `0x180011810`
- `0x180016c04`
- `0x1800181f8`
- `0x180024cb4`
- `0x180025144`
- `0x180056e20`
- `0x1800570e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efee`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000ee87`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000ee87`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_315dcca2029c58a10a41bf5fb53b336a_>(
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
  int String; // eax
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
      String = DataObj_GetString(v7, word_1800AA660, v8);
      v12 = String;
      v13 = String < 0
         && (GUID *)_std_find_trivial_4(
                      &`DataTransferTip::UnexpectedHresult'::`2'::expectedErrors,
                      &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219,
                      (unsigned int)String) == &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219;
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
0x18000edc0  mov     [rsp-18h+arg_0], rbx
0x18000edc5  mov     [rsp-18h+arg_8], rsi
0x18000edca  push    rbp
0x18000edcb  push    rdi
0x18000edcc  push    r14
0x18000edce  mov     rbp, rsp
0x18000edd1  sub     rsp, 80h
0x18000edd8  mov     rdi, rdx
0x18000eddb  mov     rbx, rcx
0x18000edde  mov     [rbp+var_60], 0
0x18000ede6  call    IsOleInitializePresent
0x18000edeb  test    al, al
0x18000eded  jz      loc_18000F05C
0x18000edf3  mov     rcx, [rbp+var_60]
0x18000edf7  test    rcx, rcx
0x18000edfa  jz      short loc_18000EE11
0x18000edfc  mov     [rbp+var_60], 0
0x18000ee04  mov     rax, [rcx]
0x18000ee07  mov     rax, [rax+10h]
0x18000ee0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee10  nop
0x18000ee11  xor     ecx, ecx
0x18000ee13  mov     [rbp+var_60], rcx
0x18000ee17  mov     r9, [rbx+0C0h]
0x18000ee1e  test    r9, r9
0x18000ee21  jnz     short loc_18000EE27
0x18000ee23  xor     eax, eax
0x18000ee25  jmp     short loc_18000EE45
0x18000ee27  mov     rax, [r9]
0x18000ee2a  lea     r8, [rbp+var_60]
0x18000ee2e  lea     rdx, _GUID_61ebf5c7_efea_4346_9554_981d7e198ffe
0x18000ee35  mov     rcx, r9
0x18000ee38  mov     rax, [rax+18h]
0x18000ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee41  mov     rcx, [rbp+var_60]
0x18000ee45  test    eax, eax
0x18000ee47  js      loc_18000F060
0x18000ee4d  test    rcx, rcx
0x18000ee50  jz      loc_18000F060
0x18000ee56  mov     [rbp+var_58], 0
0x18000ee5e  mov     rax, [rcx]
0x18000ee61  lea     r8, [rbp+var_58]
0x18000ee65  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x18000ee6c  mov     rax, [rax]
0x18000ee6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee74  nop
0x18000ee75  test    eax, eax
0x18000ee77  js      loc_18000F03E
0x18000ee7d  lea     rcx, [rbp+var_40]
0x18000ee81  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000ee86  nop
0x18000ee87  call    cs:__imp_EdpGetIsManaged
0x18000ee8d  test    eax, eax
0x18000ee8f  jz      short loc_18000EEA1
0x18000ee91  mov     [rbp+arg_10], 1
0x18000ee95  mov     ecx, 1; int
0x18000ee9a  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000ee9f  jmp     short loc_18000EEA5
0x18000eea1  mov     [rbp+arg_10], 0
0x18000eea5  lea     rax, [rbp+arg_10]
0x18000eea9  mov     [rbp+var_50], rax
0x18000eead  mov     [rbp+var_48], 1
0x18000eeb1  mov     r14, [rbp+var_58]
0x18000eeb5  mov     rdi, [rdi]
0x18000eeb8  mov     rsi, [rdi]
0x18000eebb  test    rsi, rsi
0x18000eebe  jz      short loc_18000EED9
0x18000eec0  call    cs:__imp_GetLastError
0x18000eec6  mov     ebx, eax
0x18000eec8  mov     rcx, rsi; pv
0x18000eecb  call    cs:__imp_CoTaskMemFree
0x18000eed1  mov     ecx, ebx; dwErrCode
0x18000eed3  call    cs:__imp_SetLastError
0x18000eed9  mov     qword ptr [rdi], 0
0x18000eee0  mov     r8, rdi; unsigned __int16 **
0x18000eee3  movzx   edx, cs:word_1800AA660; unsigned __int16
0x18000eeea  mov     rcx, r14; struct IDataObject *
0x18000eeed  call    ?DataObj_GetString@@YAJPEAUIDataObject@@GPEAPEAG@Z; DataObj_GetString(IDataObject *,ushort,ushort * *)
0x18000eef2  mov     esi, eax
0x18000eef4  test    eax, eax
0x18000eef6  jns     short loc_18000EF1A
0x18000eef8  mov     r8d, eax
0x18000eefb  lea     rbx, _GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219
0x18000ef02  mov     rdx, rbx
0x18000ef05  lea     rcx, ?expectedErrors@?1??UnexpectedHresult@DataTransferTip@@YA_NJ@Z@4V?$array@J$01@std@@B; std::array<long,2> const `DataTransferTip::UnexpectedHresult(long)'::`2'::expectedErrors
0x18000ef0c  call    __std_find_trivial_4
0x18000ef11  cmp     rax, rbx
0x18000ef14  jnz     short loc_18000EF1A
0x18000ef16  mov     dl, 1
0x18000ef18  jmp     short loc_18000EF1C
0x18000ef1a  xor     dl, dl
0x18000ef1c  lea     rax, aDatatransferti; "DataTransferTip::reason::resultFailed"
0x18000ef23  mov     rdi, rax
0x18000ef26  mov     cl, 44h ; 'D'
0x18000ef28  inc     rax
0x18000ef2b  cmp     cl, 3Ah ; ':'
0x18000ef2e  jnz     short loc_18000EF33
0x18000ef30  mov     rdi, rax
0x18000ef33  mov     cl, [rax]
0x18000ef35  test    cl, cl
0x18000ef37  jnz     short loc_18000EF28
0x18000ef39  test    dl, dl
0x18000ef3b  jz      short loc_18000EF7A
0x18000ef3d  mov     rbx, [rbp+pv]
0x18000ef41  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000ef48  call    cs:__imp_EnterCriticalSection
0x18000ef4e  inc     dword ptr [rbx+0F0h]
0x18000ef54  test    dword ptr [rbx+48h], 100h
0x18000ef5b  jnz     short loc_18000EF71
0x18000ef5d  mov     edx, 1
0x18000ef62  mov     r9d, esi
0x18000ef65  mov     r8, rdi
0x18000ef68  lea     rcx, [rbx+8]
0x18000ef6c  call    ??$set_flag_value@J@?$shared_data@$0A@$0A@$00@details@tip2@@QEAAXGPEBDJ@Z; tip2::details::shared_data<0,0,1>::set_flag_value<long>(ushort,char const *,long)
0x18000ef71  lea     rcx, [rbx+8]
0x18000ef75  call    ?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::end_update(void)
0x18000ef7a  mov     rbx, [rbp+pv]
0x18000ef7e  lea     rdi, [rbx+0C8h]
0x18000ef85  mov     rcx, rdi; lpCriticalSection
0x18000ef88  call    cs:__imp_EnterCriticalSection
0x18000ef8e  or      dword ptr [rbx+48h], 300h
0x18000ef95  cmp     qword ptr [rbx+0F8h], 0
0x18000ef9d  jz      short loc_18000EFAD
0x18000ef9f  mov     edx, 2
0x18000efa4  lea     rcx, [rbx+8]
0x18000efa8  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x18000efad  test    rdi, rdi
0x18000efb0  jz      short loc_18000EFBC
0x18000efb2  mov     rcx, rdi; lpCriticalSection
0x18000efb5  call    cs:__imp_LeaveCriticalSection
0x18000efbb  nop
0x18000efbc  cmp     [rbp+arg_10], 0
0x18000efc0  jz      short loc_18000EFCA
0x18000efc2  xor     ecx, ecx; int
0x18000efc4  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000efc9  nop
0x18000efca  mov     rbx, [rbp+pv]
0x18000efce  test    rbx, rbx
0x18000efd1  jz      short loc_18000EFF4
0x18000efd3  or      eax, 0FFFFFFFFh
0x18000efd6  lock xadd [rbx+150h], eax
0x18000efde  cmp     eax, 1
0x18000efe1  jnz     short loc_18000EFF4
0x18000efe3  mov     rcx, rbx
0x18000efe6  call    ??1?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(void)
0x18000efeb  mov     rcx, rbx; pv
0x18000efee  call    cs:__imp_CoTaskMemFree
0x18000eff4  lea     rcx, [rbp+var_38]; this
0x18000eff8  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000effd  nop
0x18000effe  mov     rcx, [rbp+var_58]
0x18000f002  test    rcx, rcx
0x18000f005  jz      short loc_18000F01C
0x18000f007  mov     [rbp+var_58], 0
0x18000f00f  mov     rax, [rcx]
0x18000f012  mov     rax, [rax+10h]
0x18000f016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f01b  nop
0x18000f01c  mov     rcx, [rbp+var_60]
0x18000f020  test    rcx, rcx
0x18000f023  jz      short loc_18000F03A
0x18000f025  mov     [rbp+var_60], 0
0x18000f02d  mov     rax, [rcx]
0x18000f030  mov     rax, [rax+10h]
0x18000f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f039  nop
0x18000f03a  mov     eax, esi
0x18000f03c  jmp     short loc_18000F07C
0x18000f03e  mov     rcx, [rbp+var_58]
0x18000f042  test    rcx, rcx
0x18000f045  jz      short loc_18000F05C
0x18000f047  mov     [rbp+var_58], 0
0x18000f04f  mov     rax, [rcx]
0x18000f052  mov     rax, [rax+10h]
0x18000f056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f05b  nop
0x18000f05c  mov     rcx, [rbp+var_60]
0x18000f060  test    rcx, rcx
0x18000f063  jz      short loc_18000F07A
0x18000f065  mov     [rbp+var_60], 0
0x18000f06d  mov     rax, [rcx]
0x18000f070  mov     rax, [rax+10h]
0x18000f074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f079  nop
0x18000f07a  xor     eax, eax
0x18000f07c  lea     r11, [rsp+80h+var_s0]
0x18000f084  mov     rbx, [r11+20h]
0x18000f088  mov     rsi, [r11+28h]
0x18000f08c  mov     rsp, r11
0x18000f08f  pop     r14
0x18000f091  pop     rdi
0x18000f092  pop     rbp
0x18000f093  retn
```
