# SrSmapiCreateReplicationGroup(_WSP_ReplicationGroup_CreateReplicationGroup const *,_MI_Context *)

- ea: `0x18000e5a8`
- end: `0x18000e841`
- name: `?SrSmapiCreateReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_CreateReplicationGroup@@PEAU_MI_Context@@@Z`
- size: `665`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup_CreateReplicationGroup *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d90`

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
- `0x18000e5a8`
- `0x18000ed64`
- `0x18000f414`
- `0x18000fabc`
- `0x18001babc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiCreateReplicationGroup(
        const struct _WSP_ReplicationGroup_CreateReplicationGroup *a1,
        struct _MI_Context *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // edx
  __int64 v7; // rax
  __int64 v8; // rcx
  enum _MI_Result ReplicationSettings; // ebx
  unsigned __int64 v10; // rbx
  int v11; // eax
  enum _MI_Result ReplicationGroupSetReturn; // ebx
  _WORD v14[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[32]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v24[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v25[64]; // [rsp+130h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v24, a2);
  std::wstring::wstring(v20);
  std::wstring::wstring(v23);
  std::wstring::wstring(v22);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v18);
  v17 = 0;
  v14[0] = 0;
  v15 = 3;
  v16 = 0;
  std::wstring::wstring(v21);
  if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 72)) )
  {
    v4 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 9));
    std::wstring::_Assign<wchar_t>(v20, v5, v4);
    if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 88)) )
    {
      v7 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 11));
      std::wstring::_Assign<wchar_t>(v23, v8, v7);
    }
    ReplicationSettings = (unsigned int)SrSmapipExtractReplicationSettings(
                                          (_DWORD)a1,
                                          v6,
                                          (unsigned int)v22,
                                          (unsigned int)&v17,
                                          (__int64)v14,
                                          (__int64)&v16,
                                          (__int64)&v15);
    if ( ReplicationSettings == MI_RESULT_OK )
    {
      ReplicationSettings = *((_BYTE *)a1 + 120) && *((_DWORD *)a1 + 28)
                          ? (unsigned int)SrSmapiExtractStorageObjects(
                                            (int)a1 + 104,
                                            (unsigned int)v24,
                                            v16,
                                            (unsigned int)v21,
                                            (__int64)v18)
                          : MI_RESULT_INVALID_PARAMETER;
      if ( ReplicationSettings == MI_RESULT_OK )
      {
        v10 = (unsigned __int64)v23
            & -(__int64)((unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 72)) != 0);
        v11 = std::wstring::wstring(v19, v21);
        ReplicationSettings = (unsigned int)SrSmapiInvokeCreateReplicationGroup(
                                              v11,
                                              (unsigned int)v20,
                                              v10,
                                              (unsigned int)v18,
                                              (__int64)v22,
                                              (__int64)&v17,
                                              (__int64)&v15);
      }
    }
  }
  else
  {
    ReplicationSettings = MI_RESULT_INVALID_PARAMETER;
  }
  std::wstring::wstring(v19, v20);
  ReplicationGroupSetReturn = (unsigned int)SrSmapipCreateReplicationGroupSetReturn(ReplicationSettings);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v24, ReplicationGroupSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)ReplicationGroupSetReturn);
  std::wstring::_Tidy_deallocate(v21);
  std::vector<std::wstring>::_Tidy(v18);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v20);
  v24[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v25);
  return (unsigned int)ReplicationGroupSetReturn;
}

```

## disassembly

```asm
0x18000e5a8  push    rbp
0x18000e5aa  push    rbx
0x18000e5ab  push    rsi
0x18000e5ac  push    rdi
0x18000e5ad  push    r13
0x18000e5af  push    r14
0x18000e5b1  lea     rbp, [rsp-88h]
0x18000e5b9  sub     rsp, 188h
0x18000e5c0  mov     rax, cs:__security_cookie
0x18000e5c7  xor     rax, rsp
0x18000e5ca  mov     [rbp+0B0h+var_40], rax
0x18000e5ce  mov     rbx, rdx
0x18000e5d1  mov     rdi, rcx
0x18000e5d4  lea     r13, WPP_GLOBAL_Control
0x18000e5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e2  cmp     rcx, r13
0x18000e5e5  jz      short loc_18000E602
0x18000e5e7  test    byte ptr [rcx+1Ch], 4
0x18000e5eb  jz      short loc_18000E602
0x18000e5ed  mov     edx, 18h
0x18000e5f2  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e5f9  mov     rcx, [rcx+10h]
0x18000e5fd  call    WPP_SF_
0x18000e602  mov     rdx, rbx; struct _MI_Context *
0x18000e605  lea     rcx, [rbp+0B0h+var_90]; this
0x18000e609  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000e60e  nop
0x18000e60f  lea     rcx, [rbp+0B0h+var_110]
0x18000e613  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e618  nop
0x18000e619  lea     rcx, [rbp+0B0h+var_B0]
0x18000e61d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e622  nop
0x18000e623  lea     rcx, [rbp+0B0h+var_D0]
0x18000e627  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e62c  nop
0x18000e62d  lea     rcx, [rsp+1B0h+var_148]
0x18000e632  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e637  nop
0x18000e638  mov     [rsp+1B0h+var_150], 0
0x18000e641  xor     eax, eax
0x18000e643  mov     [rsp+1B0h+var_160], ax
0x18000e648  mov     [rsp+1B0h+var_15C], 3
0x18000e650  xor     esi, esi
0x18000e652  mov     [rsp+1B0h+var_158], esi
0x18000e656  lea     rcx, [rbp+0B0h+var_F0]
0x18000e65a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e65f  nop
0x18000e660  lea     r14, [rdi+48h]
0x18000e664  mov     rcx, r14; struct _MI_ConstStringField *
0x18000e667  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e66c  test    eax, eax
0x18000e66e  jz      loc_18000E781
0x18000e674  mov     rcx, [r14]
0x18000e677  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e67c  mov     r8, rax
0x18000e67f  mov     rdx, rcx
0x18000e682  lea     rcx, [rbp+0B0h+var_110]
0x18000e686  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e68b  lea     rcx, [rdi+58h]; struct _MI_ConstStringField *
0x18000e68f  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e694  test    eax, eax
0x18000e696  jz      short loc_18000E6B0
0x18000e698  mov     rcx, [rdi+58h]
0x18000e69c  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e6a1  mov     r8, rax
0x18000e6a4  mov     rdx, rcx
0x18000e6a7  lea     rcx, [rbp+0B0h+var_B0]
0x18000e6ab  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e6b0  lea     rax, [rsp+1B0h+var_15C]
0x18000e6b5  mov     [rsp+1B0h+var_180], rax
0x18000e6ba  lea     rax, [rsp+1B0h+var_158]
0x18000e6bf  mov     [rsp+1B0h+var_188], rax
0x18000e6c4  lea     rax, [rsp+1B0h+var_160]
0x18000e6c9  mov     [rsp+1B0h+var_190], rax
0x18000e6ce  lea     r9, [rsp+1B0h+var_150]
0x18000e6d3  lea     r8, [rbp+0B0h+var_D0]
0x18000e6d7  mov     rcx, rdi
0x18000e6da  call    SrSmapipExtractReplicationSettings
0x18000e6df  mov     ebx, eax
0x18000e6e1  mov     esi, [rsp+1B0h+var_158]
0x18000e6e5  test    eax, eax
0x18000e6e7  jnz     loc_18000E786
0x18000e6ed  lea     rcx, [rdi+68h]
0x18000e6f1  cmp     [rcx+10h], al
0x18000e6f4  jz      short loc_18000E719
0x18000e6f6  cmp     [rdi+70h], eax
0x18000e6f9  jz      short loc_18000E719
0x18000e6fb  lea     rax, [rsp+1B0h+var_148]
0x18000e700  mov     [rsp+1B0h+var_190], rax
0x18000e705  lea     r9, [rbp+0B0h+var_F0]
0x18000e709  mov     r8d, esi
0x18000e70c  lea     rdx, [rbp+0B0h+var_90]
0x18000e710  call    ?SrSmapiExtractStorageObjects@@YA?AW4_MI_Result@@PEBU_MI_ConstStringA@@AEAVCWMIContext@@W4WSP_SUBSYSTEM_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@@Z; SrSmapiExtractStorageObjects(_MI_ConstStringA const *,CWMIContext &,WSP_SUBSYSTEM_TYPE,std::wstring &,std::vector<std::wstring> &)
0x18000e715  mov     ebx, eax
0x18000e717  jmp     short loc_18000E71E
0x18000e719  mov     ebx, 4
0x18000e71e  test    ebx, ebx
0x18000e720  jnz     short loc_18000E786
0x18000e722  mov     rcx, r14; struct _MI_ConstStringField *
0x18000e725  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e72a  neg     eax
0x18000e72c  sbb     rbx, rbx
0x18000e72f  lea     rax, [rbp+0B0h+var_B0]
0x18000e733  and     rbx, rax
0x18000e736  lea     rdx, [rbp+0B0h+var_F0]
0x18000e73a  lea     rcx, [rbp+0B0h+var_130]
0x18000e73e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e743  lea     rcx, [rbp+0B0h+var_90]
0x18000e747  mov     [rsp+1B0h+var_170], rcx
0x18000e74c  lea     rcx, [rsp+1B0h+var_15C]
0x18000e751  mov     [rsp+1B0h+var_180], rcx
0x18000e756  lea     rcx, [rsp+1B0h+var_150]
0x18000e75b  mov     [rsp+1B0h+var_188], rcx
0x18000e760  lea     rcx, [rbp+0B0h+var_D0]
0x18000e764  mov     [rsp+1B0h+var_190], rcx
0x18000e769  lea     r9, [rsp+1B0h+var_148]
0x18000e76e  mov     r8, rbx
0x18000e771  lea     rdx, [rbp+0B0h+var_110]
0x18000e775  mov     rcx, rax
0x18000e778  call    ?SrSmapiInvokeCreateReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBV23@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1PEA_KPEAIPEAGAEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationGroup(std::wstring,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)
0x18000e77d  mov     ebx, eax
0x18000e77f  jmp     short loc_18000E786
0x18000e781  mov     ebx, 4
0x18000e786  lea     rdx, [rbp+0B0h+var_110]
0x18000e78a  lea     rcx, [rbp+0B0h+var_130]
0x18000e78e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e793  lea     r9, [rbp+0B0h+var_90]
0x18000e797  mov     r8, rax
0x18000e79a  mov     edx, esi
0x18000e79c  mov     ecx, ebx; enum _MI_Result
0x18000e79e  call    SrSmapipCreateReplicationGroupSetReturn
0x18000e7a3  mov     ebx, eax
0x18000e7a5  mov     edx, eax; enum _MI_Result
0x18000e7a7  lea     rcx, [rbp+0B0h+var_90]; this
0x18000e7ab  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000e7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7b7  cmp     rcx, r13
0x18000e7ba  jz      short loc_18000E7DB
0x18000e7bc  test    byte ptr [rcx+1Ch], 1
0x18000e7c0  jz      short loc_18000E7DB
0x18000e7c2  mov     edx, 19h
0x18000e7c7  mov     r9d, ebx
0x18000e7ca  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e7d1  mov     rcx, [rcx+10h]
0x18000e7d5  call    WPP_SF_d
0x18000e7da  nop
0x18000e7db  lea     rcx, [rbp+0B0h+var_F0]
0x18000e7df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e7e4  nop
0x18000e7e5  lea     rcx, [rsp+1B0h+var_148]
0x18000e7ea  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000e7ef  nop
0x18000e7f0  lea     rcx, [rbp+0B0h+var_D0]
0x18000e7f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e7f9  nop
0x18000e7fa  lea     rcx, [rbp+0B0h+var_B0]
0x18000e7fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e803  nop
0x18000e804  lea     rcx, [rbp+0B0h+var_110]
0x18000e808  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e80d  nop
0x18000e80e  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000e815  mov     [rbp+0B0h+var_90], rax
0x18000e819  lea     rcx, [rbp+0B0h+var_80]
0x18000e81d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e822  mov     eax, ebx
0x18000e824  mov     rcx, [rbp+0B0h+var_40]
0x18000e828  xor     rcx, rsp; StackCookie
0x18000e82b  call    __security_check_cookie
0x18000e830  add     rsp, 188h
0x18000e837  pop     r14
0x18000e839  pop     r13
0x18000e83b  pop     rdi
0x18000e83c  pop     rsi
0x18000e83d  pop     rbx
0x18000e83e  pop     rbp
0x18000e83f  retn
```
