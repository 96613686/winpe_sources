# SrSmapiCreateReplicationRelationship(_WSP_ReplicationGroup_CreateReplicationRelationship const *,_MI_Context *)

- ea: `0x18000e848`
- end: `0x18000eba2`
- name: `?SrSmapiCreateReplicationRelationship@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_CreateReplicationRelationship@@PEAU_MI_Context@@@Z`
- size: `858`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup_CreateReplicationRelationship *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180003da0`

## callees

- `0x1800014e0`
- `0x18000559c`
- `0x180005884`
- `0x18000590c`
- `0x180005930`
- `0x180005948`
- `0x1800066d0`
- `0x180006724`
- `0x180006794`
- `0x1800067cc`
- `0x1800067fc`
- `0x180008f8c`
- `0x1800090c4`
- `0x18000e848`
- `0x18000ef94`
- `0x18000f6a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SrSmapiCreateReplicationRelationship(
        const struct _WSP_ReplicationGroup_CreateReplicationRelationship *a1,
        struct _MI_Context *a2)
{
  enum _MI_Result v4; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  enum _MI_Result ReplicationRelationshipSetReturn; // ebx
  _BYTE *v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v20[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v22[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[32]; // [rsp+110h] [rbp+10h] BYREF
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
  std::wstring::wstring(v23);
  std::wstring::wstring(v22);
  std::wstring::wstring(v25);
  std::wstring::wstring(v24);
  std::wstring::wstring(v29);
  std::wstring::wstring(v28);
  std::wstring::wstring(v27);
  std::wstring::wstring(v26);
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
  std::wstring::wstring(v20, v22);
  std::wstring::wstring(v21, v23);
  ReplicationRelationshipSetReturn = (unsigned int)SrSmapipCreateReplicationRelationshipSetReturn(
                                                     v4,
                                                     (struct CWMIContext *)v30);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v30, ReplicationRelationshipSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)ReplicationRelationshipSetReturn);
  std::vector<std::wstring>::_Tidy(v18);
  std::vector<std::wstring>::_Tidy(v19);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v28);
  std::wstring::_Tidy_deallocate(v29);
  std::wstring::_Tidy_deallocate(v24);
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  v30[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v31);
  return (unsigned int)ReplicationRelationshipSetReturn;
}

```

## disassembly

```asm
0x18000e848  mov     [rsp-8+arg_8], rbx
0x18000e84d  mov     [rsp-8+arg_10], rsi
0x18000e852  push    rbp
0x18000e853  push    rdi
0x18000e854  push    r14
0x18000e856  lea     rbp, [rsp-150h]
0x18000e85e  sub     rsp, 250h
0x18000e865  mov     rax, cs:__security_cookie
0x18000e86c  xor     rax, rsp
0x18000e86f  mov     [rbp+160h+var_20], rax
0x18000e876  mov     rsi, rdx
0x18000e879  mov     rbx, rcx
0x18000e87c  lea     r14, WPP_GLOBAL_Control
0x18000e883  mov     edi, 4
0x18000e888  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e88f  cmp     rcx, r14
0x18000e892  jz      short loc_18000E8AD
0x18000e894  test    [rcx+1Ch], dil
0x18000e898  jz      short loc_18000E8AD
0x18000e89a  lea     edx, [rdi+16h]
0x18000e89d  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e8a4  mov     rcx, [rcx+10h]
0x18000e8a8  call    WPP_SF_
0x18000e8ad  mov     rdx, rsi; struct _MI_Context *
0x18000e8b0  lea     rcx, [rbp+160h+var_70]; this
0x18000e8b7  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000e8bc  nop
0x18000e8bd  lea     rcx, [rbp+160h+var_150]
0x18000e8c1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8c6  nop
0x18000e8c7  lea     rcx, [rbp+160h+var_170]
0x18000e8cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8d0  nop
0x18000e8d1  lea     rcx, [rbp+160h+var_110]
0x18000e8d5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8da  nop
0x18000e8db  lea     rcx, [rbp+160h+var_130]
0x18000e8df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8e4  nop
0x18000e8e5  lea     rcx, [rbp+160h+var_90]
0x18000e8ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8f1  nop
0x18000e8f2  lea     rcx, [rbp+160h+var_B0]
0x18000e8f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e8fe  nop
0x18000e8ff  lea     rcx, [rbp+160h+var_D0]
0x18000e906  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e90b  nop
0x18000e90c  lea     rcx, [rbp+160h+var_F0]
0x18000e910  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e915  nop
0x18000e916  lea     rcx, [rbp+160h+var_1C8]
0x18000e91a  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e91f  nop
0x18000e920  lea     rcx, [rbp+160h+var_1E0]
0x18000e924  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e929  nop
0x18000e92a  xor     esi, esi
0x18000e92c  mov     [rsp+260h+var_1F0], rsi
0x18000e931  lea     rcx, [rbx+58h]; struct _MI_ConstStringField *
0x18000e935  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e93a  test    eax, eax
0x18000e93c  jz      loc_18000EA76
0x18000e942  mov     rcx, [rbx+58h]
0x18000e946  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e94b  mov     r8, rax
0x18000e94e  mov     rdx, rcx
0x18000e951  lea     rcx, [rbp+160h+var_150]
0x18000e955  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e95a  lea     r9, [rbx+0A0h]
0x18000e961  mov     rcx, r9; struct _MI_ConstStringField *
0x18000e964  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e969  test    eax, eax
0x18000e96b  jz      loc_18000EA76
0x18000e971  mov     rcx, [r9]
0x18000e974  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e979  mov     r8, rax
0x18000e97c  mov     rdx, rcx
0x18000e97f  lea     rcx, [rbp+160h+var_170]
0x18000e983  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e988  lea     rcx, [rbx+68h]; struct _MI_ConstStringField *
0x18000e98c  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e991  test    eax, eax
0x18000e993  jz      short loc_18000E9AD
0x18000e995  mov     rcx, [rbx+68h]
0x18000e999  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e99e  mov     r8, rax
0x18000e9a1  mov     rdx, rcx
0x18000e9a4  lea     rcx, [rbp+160h+var_110]
0x18000e9a8  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e9ad  lea     r9, [rbx+0B0h]
0x18000e9b4  mov     rcx, r9; struct _MI_ConstStringField *
0x18000e9b7  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e9bc  test    eax, eax
0x18000e9be  jz      short loc_18000E9D7
0x18000e9c0  mov     rcx, [r9]
0x18000e9c3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e9c8  mov     r8, rax
0x18000e9cb  mov     rdx, rcx
0x18000e9ce  lea     rcx, [rbp+160h+var_130]
0x18000e9d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e9d7  cmp     [rbx+98h], sil
0x18000e9de  jz      loc_18000EA76
0x18000e9e4  cmp     [rbx+88h], sil
0x18000e9eb  jz      loc_18000EA76
0x18000e9f1  cmp     [rbx+80h], esi
0x18000e9f7  jz      short loc_18000EA76
0x18000e9f9  cmp     [rbx+0D0h], sil
0x18000ea00  jz      short loc_18000EA76
0x18000ea02  cmp     [rbx+0C8h], esi
0x18000ea08  jz      short loc_18000EA76
0x18000ea0a  lea     rax, [rbp+160h+var_70]
0x18000ea11  mov     [rsp+260h+var_1F8], rax
0x18000ea16  lea     rax, [rsp+260h+var_1F0]
0x18000ea1b  mov     [rsp+260h+var_210], rax
0x18000ea20  lea     rax, [rbp+160h+var_B0]
0x18000ea27  mov     [rsp+260h+var_218], rax
0x18000ea2c  lea     rax, [rbp+160h+var_90]
0x18000ea33  mov     [rsp+260h+var_220], rax
0x18000ea38  lea     rax, [rbp+160h+var_1E0]
0x18000ea3c  mov     [rsp+260h+var_228], rax
0x18000ea41  lea     rax, [rbp+160h+var_1C8]
0x18000ea45  mov     [rsp+260h+var_230], rax
0x18000ea4a  lea     rax, [rbp+160h+var_130]
0x18000ea4e  mov     [rsp+260h+var_238], rax
0x18000ea53  lea     rax, [rbp+160h+var_110]
0x18000ea57  mov     [rsp+260h+var_240], rax
0x18000ea5c  lea     r9, [rbp+160h+var_F0]
0x18000ea60  lea     r8, [rbp+160h+var_D0]
0x18000ea67  lea     rdx, [rbp+160h+var_170]
0x18000ea6b  lea     rcx, [rbp+160h+var_150]
0x18000ea6f  call    ?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@100PEA_KPEAIPEAGAEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationPartnership(std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::vector<std::wstring> const *,std::wstring const *,std::wstring const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)
0x18000ea74  mov     edi, eax
0x18000ea76  lea     rax, [rbp+160h+var_1B0]
0x18000ea7a  mov     [rsp+260h+var_1F0], rax
0x18000ea7f  lea     rdx, [rbp+160h+var_170]
0x18000ea83  lea     rcx, [rbp+160h+var_1B0]
0x18000ea87  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea8c  mov     rbx, rax
0x18000ea8f  lea     rdx, [rbp+160h+var_150]
0x18000ea93  lea     rcx, [rbp+160h+var_190]
0x18000ea97  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea9c  nop
0x18000ea9d  lea     rcx, [rbp+160h+var_70]
0x18000eaa4  mov     [rsp+260h+var_240], rcx; struct CWMIContext *
0x18000eaa9  mov     r9, rbx
0x18000eaac  mov     r8, rax
0x18000eaaf  mov     ecx, edi; enum _MI_Result
0x18000eab1  call    SrSmapipCreateReplicationRelationshipSetReturn
0x18000eab6  mov     ebx, eax
0x18000eab8  mov     edx, eax; enum _MI_Result
0x18000eaba  lea     rcx, [rbp+160h+var_70]; this
0x18000eac1  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000eac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eacd  cmp     rcx, r14
0x18000ead0  jz      short loc_18000EAF1
0x18000ead2  test    byte ptr [rcx+1Ch], 1
0x18000ead6  jz      short loc_18000EAF1
0x18000ead8  mov     edx, 1Bh
0x18000eadd  mov     r9d, ebx
0x18000eae0  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000eae7  mov     rcx, [rcx+10h]
0x18000eaeb  call    WPP_SF_d
0x18000eaf0  nop
0x18000eaf1  lea     rcx, [rbp+160h+var_1E0]
0x18000eaf5  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000eafa  nop
0x18000eafb  lea     rcx, [rbp+160h+var_1C8]
0x18000eaff  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000eb04  nop
0x18000eb05  lea     rcx, [rbp+160h+var_F0]
0x18000eb09  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb0e  nop
0x18000eb0f  lea     rcx, [rbp+160h+var_D0]
0x18000eb16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb1b  nop
0x18000eb1c  lea     rcx, [rbp+160h+var_B0]
0x18000eb23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb28  nop
0x18000eb29  lea     rcx, [rbp+160h+var_90]
0x18000eb30  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb35  nop
0x18000eb36  lea     rcx, [rbp+160h+var_130]
0x18000eb3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb3f  nop
0x18000eb40  lea     rcx, [rbp+160h+var_110]
0x18000eb44  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb49  nop
0x18000eb4a  lea     rcx, [rbp+160h+var_170]
0x18000eb4e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb53  nop
0x18000eb54  lea     rcx, [rbp+160h+var_150]
0x18000eb58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb5d  nop
0x18000eb5e  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000eb65  mov     [rbp+160h+var_70], rax
0x18000eb6c  lea     rcx, [rbp+160h+var_60]
0x18000eb73  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eb78  mov     eax, ebx
0x18000eb7a  mov     rcx, [rbp+160h+var_20]
0x18000eb81  xor     rcx, rsp; StackCookie
0x18000eb84  call    __security_check_cookie
0x18000eb89  lea     r11, [rsp+260h+var_10]
0x18000eb91  mov     rbx, [r11+28h]
0x18000eb95  mov     rsi, [r11+30h]
0x18000eb99  mov     rsp, r11
0x18000eb9c  pop     r14
0x18000eb9e  pop     rdi
0x18000eb9f  pop     rbp
0x18000eba0  retn
```
