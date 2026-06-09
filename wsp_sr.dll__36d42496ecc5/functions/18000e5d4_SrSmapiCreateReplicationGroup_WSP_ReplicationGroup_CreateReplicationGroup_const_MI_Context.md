# SrSmapiCreateReplicationGroup(_WSP_ReplicationGroup_CreateReplicationGroup const *,_MI_Context *)

- ea: `0x18000e5d4`
- end: `0x18000e86c`
- name: `?SrSmapiCreateReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_CreateReplicationGroup@@PEAU_MI_Context@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(const struct _WSP_ReplicationGroup_CreateReplicationGroup *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003e20`

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
- `0x18000e5d4`
- `0x18000ed90`
- `0x18000f440`
- `0x18000fae4`
- `0x18001ba4c`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationGroup(
        const struct _WSP_ReplicationGroup_CreateReplicationGroup *a1,
        struct _MI_Context *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  enum _MI_Result v9; // ebx
  unsigned __int64 v10; // rbx
  int v11; // eax
  MI_Uint32 ReplicationGroupSetReturn; // ebx
  _WORD v14[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v18[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v20[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v21[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v22[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[32]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v24[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v25[64]; // [rsp+130h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v24, a2);
  std::wstring::wstring((__int64)v20);
  std::wstring::wstring((__int64)v23);
  std::wstring::wstring((__int64)v22);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v18);
  v17 = 0;
  v14[0] = 0;
  v15 = 3;
  v16 = 0;
  std::wstring::wstring((__int64)v21);
  if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 72)) )
  {
    v4 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 9));
    std::wstring::_Assign<wchar_t>(v20, v5, v4);
    if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 88)) )
    {
      v7 = std::_WChar_traits<wchar_t>::length(*((_QWORD *)a1 + 11));
      std::wstring::_Assign<wchar_t>(v23, v8, v7);
    }
    v9 = (unsigned int)SrSmapipExtractReplicationSettings((__int64)a1, v6, v22, &v17, v14, &v16, &v15);
    if ( v9 == MI_RESULT_OK )
    {
      v9 = *((_BYTE *)a1 + 120) && *((_DWORD *)a1 + 28)
         ? (unsigned int)SrSmapiExtractStorageObjects((__int64)a1 + 104, (__int64)v24, v16, v21, (__int64)v18)
         : MI_RESULT_INVALID_PARAMETER;
      if ( v9 == MI_RESULT_OK )
      {
        v10 = (unsigned __int64)v23
            & -(__int64)((unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a1 + 72)) != 0);
        v11 = std::wstring::wstring((__int64)v19, v21);
        v9 = (unsigned int)SrSmapiInvokeCreateReplicationGroup(
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
    v9 = MI_RESULT_INVALID_PARAMETER;
  }
  std::wstring::wstring((__int64)v19, v20);
  ReplicationGroupSetReturn = SrSmapipCreateReplicationGroupSetReturn(v9);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v24, ReplicationGroupSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      ReplicationGroupSetReturn);
  std::wstring::_Tidy_deallocate((__int64)v21);
  std::vector<std::wstring>::_Tidy((__int64)v18);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::wstring::_Tidy_deallocate((__int64)v23);
  std::wstring::_Tidy_deallocate((__int64)v20);
  v24[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v25);
  return ReplicationGroupSetReturn;
}

```

## disassembly

```asm
0x18000e5d4  push    rbp
0x18000e5d6  push    rbx
0x18000e5d7  push    rsi
0x18000e5d8  push    rdi
0x18000e5d9  push    r13
0x18000e5db  push    r14
0x18000e5dd  lea     rbp, [rsp-88h]
0x18000e5e5  sub     rsp, 188h
0x18000e5ec  mov     rax, cs:__security_cookie
0x18000e5f3  xor     rax, rsp
0x18000e5f6  mov     [rbp+0B0h+var_40], rax
0x18000e5fa  mov     rbx, rdx
0x18000e5fd  mov     rdi, rcx
0x18000e600  lea     r13, WPP_GLOBAL_Control
0x18000e607  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e60e  cmp     rcx, r13
0x18000e611  jz      short loc_18000E62E
0x18000e613  test    byte ptr [rcx+1Ch], 4
0x18000e617  jz      short loc_18000E62E
0x18000e619  mov     edx, 18h
0x18000e61e  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e625  mov     rcx, [rcx+10h]
0x18000e629  call    WPP_SF_
0x18000e62e  mov     rdx, rbx; struct _MI_Context *
0x18000e631  lea     rcx, [rbp+0B0h+var_90]; this
0x18000e635  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000e63a  nop
0x18000e63b  lea     rcx, [rbp+0B0h+var_110]
0x18000e63f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e644  nop
0x18000e645  lea     rcx, [rbp+0B0h+var_B0]
0x18000e649  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e64e  nop
0x18000e64f  lea     rcx, [rbp+0B0h+var_D0]
0x18000e653  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e658  nop
0x18000e659  lea     rcx, [rsp+1B0h+var_148]
0x18000e65e  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000e663  nop
0x18000e664  mov     [rsp+1B0h+var_150], 0
0x18000e66d  xor     eax, eax
0x18000e66f  mov     [rsp+1B0h+var_160], ax
0x18000e674  mov     [rsp+1B0h+var_15C], 3
0x18000e67c  xor     esi, esi
0x18000e67e  mov     [rsp+1B0h+var_158], esi
0x18000e682  lea     rcx, [rbp+0B0h+var_F0]
0x18000e686  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e68b  nop
0x18000e68c  lea     r14, [rdi+48h]
0x18000e690  mov     rcx, r14; struct _MI_ConstStringField *
0x18000e693  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e698  test    eax, eax
0x18000e69a  jz      loc_18000E7AD
0x18000e6a0  mov     rcx, [r14]
0x18000e6a3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e6a8  mov     r8, rax
0x18000e6ab  mov     rdx, rcx
0x18000e6ae  lea     rcx, [rbp+0B0h+var_110]
0x18000e6b2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e6b7  lea     rcx, [rdi+58h]; struct _MI_ConstStringField *
0x18000e6bb  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e6c0  test    eax, eax
0x18000e6c2  jz      short loc_18000E6DC
0x18000e6c4  mov     rcx, [rdi+58h]
0x18000e6c8  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18000e6cd  mov     r8, rax
0x18000e6d0  mov     rdx, rcx
0x18000e6d3  lea     rcx, [rbp+0B0h+var_B0]
0x18000e6d7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e6dc  lea     rax, [rsp+1B0h+var_15C]
0x18000e6e1  mov     [rsp+1B0h+var_180], rax
0x18000e6e6  lea     rax, [rsp+1B0h+var_158]
0x18000e6eb  mov     [rsp+1B0h+var_188], rax
0x18000e6f0  lea     rax, [rsp+1B0h+var_160]
0x18000e6f5  mov     [rsp+1B0h+var_190], rax
0x18000e6fa  lea     r9, [rsp+1B0h+var_150]
0x18000e6ff  lea     r8, [rbp+0B0h+var_D0]
0x18000e703  mov     rcx, rdi
0x18000e706  call    SrSmapipExtractReplicationSettings
0x18000e70b  mov     ebx, eax
0x18000e70d  mov     esi, [rsp+1B0h+var_158]
0x18000e711  test    eax, eax
0x18000e713  jnz     loc_18000E7B2
0x18000e719  lea     rcx, [rdi+68h]
0x18000e71d  cmp     [rcx+10h], al
0x18000e720  jz      short loc_18000E745
0x18000e722  cmp     [rdi+70h], eax
0x18000e725  jz      short loc_18000E745
0x18000e727  lea     rax, [rsp+1B0h+var_148]
0x18000e72c  mov     [rsp+1B0h+var_190], rax
0x18000e731  lea     r9, [rbp+0B0h+var_F0]
0x18000e735  mov     r8d, esi
0x18000e738  lea     rdx, [rbp+0B0h+var_90]
0x18000e73c  call    ?SrSmapiExtractStorageObjects@@YA?AW4_MI_Result@@PEBU_MI_ConstStringA@@AEAVCWMIContext@@W4WSP_SUBSYSTEM_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@@Z; SrSmapiExtractStorageObjects(_MI_ConstStringA const *,CWMIContext &,WSP_SUBSYSTEM_TYPE,std::wstring &,std::vector<std::wstring> &)
0x18000e741  mov     ebx, eax
0x18000e743  jmp     short loc_18000E74A
0x18000e745  mov     ebx, 4
0x18000e74a  test    ebx, ebx
0x18000e74c  jnz     short loc_18000E7B2
0x18000e74e  mov     rcx, r14; struct _MI_ConstStringField *
0x18000e751  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000e756  neg     eax
0x18000e758  sbb     rbx, rbx
0x18000e75b  lea     rax, [rbp+0B0h+var_B0]
0x18000e75f  and     rbx, rax
0x18000e762  lea     rdx, [rbp+0B0h+var_F0]
0x18000e766  lea     rcx, [rbp+0B0h+var_130]
0x18000e76a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e76f  lea     rcx, [rbp+0B0h+var_90]
0x18000e773  mov     [rsp+1B0h+var_170], rcx
0x18000e778  lea     rcx, [rsp+1B0h+var_15C]
0x18000e77d  mov     [rsp+1B0h+var_180], rcx
0x18000e782  lea     rcx, [rsp+1B0h+var_150]
0x18000e787  mov     [rsp+1B0h+var_188], rcx
0x18000e78c  lea     rcx, [rbp+0B0h+var_D0]
0x18000e790  mov     [rsp+1B0h+var_190], rcx
0x18000e795  lea     r9, [rsp+1B0h+var_148]
0x18000e79a  mov     r8, rbx
0x18000e79d  lea     rdx, [rbp+0B0h+var_110]
0x18000e7a1  mov     rcx, rax
0x18000e7a4  call    ?SrSmapiInvokeCreateReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBV23@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1PEA_KPEAIPEAGAEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationGroup(std::wstring,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)
0x18000e7a9  mov     ebx, eax
0x18000e7ab  jmp     short loc_18000E7B2
0x18000e7ad  mov     ebx, 4
0x18000e7b2  lea     rdx, [rbp+0B0h+var_110]
0x18000e7b6  lea     rcx, [rbp+0B0h+var_130]
0x18000e7ba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e7bf  lea     r9, [rbp+0B0h+var_90]
0x18000e7c3  mov     r8, rax
0x18000e7c6  mov     edx, esi
0x18000e7c8  mov     ecx, ebx; enum _MI_Result
0x18000e7ca  call    SrSmapipCreateReplicationGroupSetReturn
0x18000e7cf  mov     ebx, eax
0x18000e7d1  mov     edx, eax; enum _MI_Result
0x18000e7d3  lea     rcx, [rbp+0B0h+var_90]; this
0x18000e7d7  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000e7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7e3  cmp     rcx, r13
0x18000e7e6  jz      short loc_18000E807
0x18000e7e8  test    byte ptr [rcx+1Ch], 1
0x18000e7ec  jz      short loc_18000E807
0x18000e7ee  mov     edx, 19h
0x18000e7f3  mov     r9d, ebx
0x18000e7f6  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000e7fd  mov     rcx, [rcx+10h]
0x18000e801  call    WPP_SF_d
0x18000e806  nop
0x18000e807  lea     rcx, [rbp+0B0h+var_F0]
0x18000e80b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e810  nop
0x18000e811  lea     rcx, [rsp+1B0h+var_148]
0x18000e816  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000e81b  nop
0x18000e81c  lea     rcx, [rbp+0B0h+var_D0]
0x18000e820  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e825  nop
0x18000e826  lea     rcx, [rbp+0B0h+var_B0]
0x18000e82a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e82f  nop
0x18000e830  lea     rcx, [rbp+0B0h+var_110]
0x18000e834  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e839  nop
0x18000e83a  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000e841  mov     [rbp+0B0h+var_90], rax
0x18000e845  lea     rcx, [rbp+0B0h+var_80]
0x18000e849  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e84e  mov     eax, ebx
0x18000e850  mov     rcx, [rbp+0B0h+var_40]
0x18000e854  xor     rcx, rsp; StackCookie
0x18000e857  call    __security_check_cookie
0x18000e85c  add     rsp, 188h
0x18000e863  pop     r14
0x18000e865  pop     r13
0x18000e867  pop     rdi
0x18000e868  pop     rsi
0x18000e869  pop     rbx
0x18000e86a  pop     rbp
0x18000e86b  retn
```
