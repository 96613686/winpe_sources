# SrSmapiCreateReplicationRelationship(_WSP_ReplicationGroup_CreateReplicationRelationship const *,_MI_Context *)

- ea: `0x18000e874`
- end: `0x18000ebcd`
- name: `?SrSmapiCreateReplicationRelationship@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_CreateReplicationRelationship@@PEAU_MI_Context@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(const struct _WSP_ReplicationGroup_CreateReplicationRelationship *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180003e30`

## callees

- `0x1800014e0`
- `0x180005570`
- `0x18000584c`
- `0x1800058d4`
- `0x1800058f8`
- `0x180005910`
- `0x180006688`
- `0x1800066d8`
- `0x18000673c`
- `0x180006778`
- `0x1800067a0`
- `0x180008df8`
- `0x180008f0c`
- `0x18000e874`
- `0x18000efc0`
- `0x18000f6d4`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship(
        const struct _WSP_ReplicationGroup_CreateReplicationRelationship *a1,
        struct _MI_Context *a2)
{
  enum _MI_Result v4; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  MI_Uint32 ReplicationRelationshipSetReturn; // ebx
  _BYTE *v17; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v18[3]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v19[3]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v20[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v22[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v23[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v24[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v25[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v26[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v27[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v28[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v29[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v30[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v31[64]; // [rsp+200h] [rbp+100h] BYREF

  v4 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v30, a2);
  std::wstring::wstring((__int64)v23);
  std::wstring::wstring((__int64)v22);
  std::wstring::wstring((__int64)v25);
  std::wstring::wstring((__int64)v24);
  std::wstring::wstring((__int64)v29);
  std::wstring::wstring((__int64)v28);
  std::wstring::wstring((__int64)v27);
  std::wstring::wstring((__int64)v26);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v19);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v18);
  v17 = 0;
  if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 88)) )
  {
    v5 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 11));
    std::wstring::_Assign<wchar_t>(v23, v6, v5);
    if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)a1 + 10) )
    {
      v8 = std::_WChar_traits<wchar_t>::length(*v7);
      std::wstring::_Assign<wchar_t>(v22, v9, v8);
      if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 104)) )
      {
        v10 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 13));
        std::wstring::_Assign<wchar_t>(v25, v11, v10);
      }
      if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)a1 + 11) )
      {
        v13 = std::_WChar_traits<wchar_t>::length(*v12);
        std::wstring::_Assign<wchar_t>(v24, v14, v13);
      }
      if ( *((_BYTE *)a1 + 152)
        && *((_BYTE *)a1 + 136)
        && *((_DWORD *)a1 + 32)
        && *((_BYTE *)a1 + 208)
        && *((_DWORD *)a1 + 50) )
      {
        v4 = (unsigned int)SrSmapiInvokeCreateReplicationPartnership(
                             (unsigned int)v23,
                             (unsigned int)v22,
                             (unsigned int)v27,
                             (unsigned int)v26,
                             (__int64)v25,
                             (__int64)v24,
                             (__int64)v19,
                             (__int64)v18,
                             (__int64)v29,
                             (__int64)v28,
                             (__int64)&v17);
      }
    }
  }
  v17 = v20;
  std::wstring::wstring((__int64)v20, v22);
  std::wstring::wstring((__int64)v21, v23);
  ReplicationRelationshipSetReturn = SrSmapipCreateReplicationRelationshipSetReturn(v4, (struct CWMIContext *)v30);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v30, ReplicationRelationshipSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      ReplicationRelationshipSetReturn);
  std::vector<std::wstring>::_Tidy((__int64)v18);
  std::vector<std::wstring>::_Tidy((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v26);
  std::wstring::_Tidy_deallocate((__int64)v27);
  std::wstring::_Tidy_deallocate((__int64)v28);
  std::wstring::_Tidy_deallocate((__int64)v29);
  std::wstring::_Tidy_deallocate((__int64)v24);
  std::wstring::_Tidy_deallocate((__int64)v25);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::wstring::_Tidy_deallocate((__int64)v23);
  v30[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v31);
  return ReplicationRelationshipSetReturn;
}

```

## disassembly

```asm
0x18000e874  mov     [rsp-8+arg_8], rbx
0x18000e879  mov     [rsp-8+arg_10], rsi
0x18000e87e  push    rbp
0x18000e87f  push    rdi
0x18000e880  push    r14
0x18000e882  lea     rbp, [rsp-150h]
0x18000e88a  sub     rsp, 250h
0x18000e891  mov     rax, cs:__security_cookie
0x18000e898  xor     rax, rsp
0x18000e89b  mov     [rbp+160h+var_20], rax
0x18000e8a2  mov     rsi, rdx
0x18000e8a5  mov     rbx, rcx
0x18000e8a8  lea     r14, WPP_GLOBAL_Control
0x18000e8af  mov     edi, 4
0x18000e8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8bb  cmp     rcx, r14
0x18000e8be  jz      short loc_18000E8D9
0x18000e8c0  test    [rcx+1Ch], dil
0x18000e8c4  jz      short loc_18000E8D9
0x18000e8c6  lea     edx, [rdi+16h]
0x18000e8c9  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e8d0  mov     rcx, [rcx+10h]
0x18000e8d4  call    WPP_SF_
0x18000e8d9  mov     rdx, rsi; struct _MI_Context *
0x18000e8dc  lea     rcx, [rbp+160h+var_70]; this
0x18000e8e3  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000e8e8  nop
0x18000e8e9  lea     rcx, [rbp+160h+var_150]
0x18000e8ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8f2  nop
0x18000e8f3  lea     rcx, [rbp+160h+var_170]
0x18000e8f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8fc  nop
0x18000e8fd  lea     rcx, [rbp+160h+var_110]
0x18000e901  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e906  nop
0x18000e907  lea     rcx, [rbp+160h+var_130]
0x18000e90b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e910  nop
0x18000e911  lea     rcx, [rbp+160h+var_90]
0x18000e918  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e91d  nop
0x18000e91e  lea     rcx, [rbp+160h+var_B0]
0x18000e925  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e92a  nop
0x18000e92b  lea     rcx, [rbp+160h+var_D0]
0x18000e932  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e937  nop
0x18000e938  lea     rcx, [rbp+160h+var_F0]
0x18000e93c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e941  nop
0x18000e942  lea     rcx, [rbp+160h+var_1C8]
0x18000e946  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e94b  nop
0x18000e94c  lea     rcx, [rbp+160h+var_1E0]
0x18000e950  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e955  nop
0x18000e956  xor     esi, esi
0x18000e958  mov     [rsp+260h+var_1F0], rsi
0x18000e95d  lea     rcx, [rbx+58h]; struct _MI_ConstStringField *
0x18000e961  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e966  test    eax, eax
0x18000e968  jz      loc_18000EAA2
0x18000e96e  mov     rcx, [rbx+58h]
0x18000e972  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e977  mov     r8, rax
0x18000e97a  mov     rdx, rcx
0x18000e97d  lea     rcx, [rbp+160h+var_150]
0x18000e981  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e986  lea     r9, [rbx+0A0h]
0x18000e98d  mov     rcx, r9; struct _MI_ConstStringField *
0x18000e990  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e995  test    eax, eax
0x18000e997  jz      loc_18000EAA2
0x18000e99d  mov     rcx, [r9]
0x18000e9a0  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e9a5  mov     r8, rax
0x18000e9a8  mov     rdx, rcx
0x18000e9ab  lea     rcx, [rbp+160h+var_170]
0x18000e9af  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e9b4  lea     rcx, [rbx+68h]; struct _MI_ConstStringField *
0x18000e9b8  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e9bd  test    eax, eax
0x18000e9bf  jz      short loc_18000E9D9
0x18000e9c1  mov     rcx, [rbx+68h]
0x18000e9c5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e9ca  mov     r8, rax
0x18000e9cd  mov     rdx, rcx
0x18000e9d0  lea     rcx, [rbp+160h+var_110]
0x18000e9d4  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e9d9  lea     r9, [rbx+0B0h]
0x18000e9e0  mov     rcx, r9; struct _MI_ConstStringField *
0x18000e9e3  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e9e8  test    eax, eax
0x18000e9ea  jz      short loc_18000EA03
0x18000e9ec  mov     rcx, [r9]
0x18000e9ef  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e9f4  mov     r8, rax
0x18000e9f7  mov     rdx, rcx
0x18000e9fa  lea     rcx, [rbp+160h+var_130]
0x18000e9fe  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000ea03  cmp     [rbx+98h], sil
0x18000ea0a  jz      loc_18000EAA2
0x18000ea10  cmp     [rbx+88h], sil
0x18000ea17  jz      loc_18000EAA2
0x18000ea1d  cmp     [rbx+80h], esi
0x18000ea23  jz      short loc_18000EAA2
0x18000ea25  cmp     [rbx+0D0h], sil
0x18000ea2c  jz      short loc_18000EAA2
0x18000ea2e  cmp     [rbx+0C8h], esi
0x18000ea34  jz      short loc_18000EAA2
0x18000ea36  lea     rax, [rbp+160h+var_70]
0x18000ea3d  mov     [rsp+260h+var_1F8], rax
0x18000ea42  lea     rax, [rsp+260h+var_1F0]
0x18000ea47  mov     [rsp+260h+var_210], rax
0x18000ea4c  lea     rax, [rbp+160h+var_B0]
0x18000ea53  mov     [rsp+260h+var_218], rax
0x18000ea58  lea     rax, [rbp+160h+var_90]
0x18000ea5f  mov     [rsp+260h+var_220], rax
0x18000ea64  lea     rax, [rbp+160h+var_1E0]
0x18000ea68  mov     [rsp+260h+var_228], rax
0x18000ea6d  lea     rax, [rbp+160h+var_1C8]
0x18000ea71  mov     [rsp+260h+var_230], rax
0x18000ea76  lea     rax, [rbp+160h+var_130]
0x18000ea7a  mov     [rsp+260h+var_238], rax
0x18000ea7f  lea     rax, [rbp+160h+var_110]
0x18000ea83  mov     [rsp+260h+var_240], rax
0x18000ea88  lea     r9, [rbp+160h+var_F0]
0x18000ea8c  lea     r8, [rbp+160h+var_D0]
0x18000ea93  lea     rdx, [rbp+160h+var_170]
0x18000ea97  lea     rcx, [rbp+160h+var_150]
0x18000ea9b  call    ?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@100PEA_KPEAIPEAGAEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationPartnership(std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::vector<std::wstring> const *,std::wstring const *,std::wstring const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)
0x18000eaa0  mov     edi, eax
0x18000eaa2  lea     rax, [rbp+160h+var_1B0]
0x18000eaa6  mov     [rsp+260h+var_1F0], rax
0x18000eaab  lea     rdx, [rbp+160h+var_170]
0x18000eaaf  lea     rcx, [rbp+160h+var_1B0]
0x18000eab3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000eab8  mov     rbx, rax
0x18000eabb  lea     rdx, [rbp+160h+var_150]
0x18000eabf  lea     rcx, [rbp+160h+var_190]
0x18000eac3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000eac8  nop
0x18000eac9  lea     rcx, [rbp+160h+var_70]
0x18000ead0  mov     [rsp+260h+var_240], rcx; struct CWMIContext *
0x18000ead5  mov     r9, rbx
0x18000ead8  mov     r8, rax
0x18000eadb  mov     ecx, edi; enum _MI_Result
0x18000eadd  call    SrSmapipCreateReplicationRelationshipSetReturn
0x18000eae2  mov     ebx, eax
0x18000eae4  mov     edx, eax; enum _MI_Result
0x18000eae6  lea     rcx, [rbp+160h+var_70]; this
0x18000eaed  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000eaf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eaf9  cmp     rcx, r14
0x18000eafc  jz      short loc_18000EB1D
0x18000eafe  test    byte ptr [rcx+1Ch], 1
0x18000eb02  jz      short loc_18000EB1D
0x18000eb04  mov     edx, 1Bh
0x18000eb09  mov     r9d, ebx
0x18000eb0c  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000eb13  mov     rcx, [rcx+10h]
0x18000eb17  call    WPP_SF_d
0x18000eb1c  nop
0x18000eb1d  lea     rcx, [rbp+160h+var_1E0]
0x18000eb21  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000eb26  nop
0x18000eb27  lea     rcx, [rbp+160h+var_1C8]
0x18000eb2b  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000eb30  nop
0x18000eb31  lea     rcx, [rbp+160h+var_F0]
0x18000eb35  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb3a  nop
0x18000eb3b  lea     rcx, [rbp+160h+var_D0]
0x18000eb42  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb47  nop
0x18000eb48  lea     rcx, [rbp+160h+var_B0]
0x18000eb4f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb54  nop
0x18000eb55  lea     rcx, [rbp+160h+var_90]
0x18000eb5c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb61  nop
0x18000eb62  lea     rcx, [rbp+160h+var_130]
0x18000eb66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb6b  nop
0x18000eb6c  lea     rcx, [rbp+160h+var_110]
0x18000eb70  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb75  nop
0x18000eb76  lea     rcx, [rbp+160h+var_170]
0x18000eb7a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb7f  nop
0x18000eb80  lea     rcx, [rbp+160h+var_150]
0x18000eb84  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb89  nop
0x18000eb8a  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000eb91  mov     [rbp+160h+var_70], rax
0x18000eb98  lea     rcx, [rbp+160h+var_60]
0x18000eb9f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eba4  mov     eax, ebx
0x18000eba6  mov     rcx, [rbp+160h+var_20]
0x18000ebad  xor     rcx, rsp; StackCookie
0x18000ebb0  call    __security_check_cookie
0x18000ebb5  lea     r11, [rsp+260h+var_10]
0x18000ebbd  mov     rbx, [r11+28h]
0x18000ebc1  mov     rsi, [r11+30h]
0x18000ebc5  mov     rsp, r11
0x18000ebc8  pop     r14
0x18000ebca  pop     rdi
0x18000ebcb  pop     rbp
0x18000ebcc  retn
```
