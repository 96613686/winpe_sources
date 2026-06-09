# SrSmapiDeleteReplicationRelationship(_WSP_ReplicationGroup_DeleteReplicationRelationship const *,_MI_Context *)

- ea: `0x18000eba8`
- end: `0x18000ed5e`
- name: `?SrSmapiDeleteReplicationRelationship@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_DeleteReplicationRelationship@@PEAU_MI_Context@@@Z`
- size: `438`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup_DeleteReplicationRelationship *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180003e70`

## callees

- `0x1800014e0`
- `0x18000590c`
- `0x180005948`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180008f8c`
- `0x1800090c4`
- `0x18000eba8`
- `0x18000f264`
- `0x18001ab74`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SrSmapiDeleteReplicationRelationship(
        const struct _WSP_ReplicationGroup_DeleteReplicationRelationship *a1,
        struct _MI_Context *a2)
{
  enum _MI_Result v4; // ebx
  _QWORD *v5; // rcx
  enum _MI_Result v6; // eax
  _QWORD *v7; // rcx
  _BYTE v9[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v13[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v14[64]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v13, a2);
  std::wstring::wstring(v12);
  std::wstring::wstring(v11);
  std::wstring::wstring(v10);
  std::wstring::wstring(v9);
  if ( *((_BYTE *)a1 + 80)
    && (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)(*((_QWORD *)a1 + 9) + 64LL)) )
  {
    v6 = (unsigned int)DecodeReplicationGroupObjectId(*v5, 0, v12, v10);
    if ( v6 )
    {
LABEL_11:
      v4 = v6;
      goto LABEL_12;
    }
    if ( *((_BYTE *)a1 + 96) )
    {
      if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)(*((_QWORD *)a1 + 11) + 168LL)) )
      {
        v4 = (unsigned int)DecodeReplicationGroupObjectId(*v7, 0, v11, v9);
        if ( v4 == MI_RESULT_OK )
        {
          v6 = (unsigned int)SrSmapiInvokeRemoveReplicationRelationship(
                               (__int64)v10,
                               (__int64)v12,
                               (__int64)v9,
                               (__int64)v11,
                               (struct CWMIContext *)v13);
          goto LABEL_11;
        }
      }
    }
  }
LABEL_12:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v13, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, (unsigned int)v4);
  std::wstring::_Tidy_deallocate(v9);
  std::wstring::_Tidy_deallocate(v10);
  std::wstring::_Tidy_deallocate(v11);
  std::wstring::_Tidy_deallocate(v12);
  v13[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000eba8  mov     [rsp-8+arg_8], rbx
0x18000ebad  mov     [rsp-8+arg_10], rsi
0x18000ebb2  push    rbp
0x18000ebb3  push    rdi
0x18000ebb4  push    r14
0x18000ebb6  lea     rbp, [rsp-10h]
0x18000ebbb  sub     rsp, 110h
0x18000ebc2  mov     rax, cs:__security_cookie
0x18000ebc9  xor     rax, rsp
0x18000ebcc  mov     [rbp+20h+var_20], rax
0x18000ebd0  mov     rsi, rdx
0x18000ebd3  mov     rdi, rcx
0x18000ebd6  lea     r14, WPP_GLOBAL_Control
0x18000ebdd  mov     ebx, 4
0x18000ebe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe9  cmp     rcx, r14
0x18000ebec  jz      short loc_18000EC06
0x18000ebee  test    [rcx+1Ch], bl
0x18000ebf1  jz      short loc_18000EC06
0x18000ebf3  lea     edx, [rbx+18h]
0x18000ebf6  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ebfd  mov     rcx, [rcx+10h]
0x18000ec01  call    WPP_SF_
0x18000ec06  mov     rdx, rsi; struct _MI_Context *
0x18000ec09  lea     rcx, [rbp+20h+var_70]; this
0x18000ec0d  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000ec12  nop
0x18000ec13  lea     rcx, [rbp+20h+var_90]
0x18000ec17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec1c  nop
0x18000ec1d  lea     rcx, [rsp+120h+var_B0]
0x18000ec22  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec27  nop
0x18000ec28  lea     rcx, [rsp+120h+var_D0]
0x18000ec2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec32  nop
0x18000ec33  lea     rcx, [rsp+120h+var_F0]
0x18000ec38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec3d  nop
0x18000ec3e  cmp     byte ptr [rdi+50h], 0
0x18000ec42  jz      short loc_18000ECC2
0x18000ec44  mov     rcx, [rdi+48h]
0x18000ec48  add     rcx, 40h ; '@'; struct _MI_ConstStringField *
0x18000ec4c  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000ec51  test    eax, eax
0x18000ec53  jz      short loc_18000ECC2
0x18000ec55  lea     r9, [rsp+120h+var_D0]
0x18000ec5a  lea     r8, [rbp+20h+var_90]
0x18000ec5e  xor     edx, edx
0x18000ec60  mov     rcx, [rcx]
0x18000ec63  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000ec68  test    eax, eax
0x18000ec6a  jnz     short loc_18000ECC0
0x18000ec6c  cmp     [rdi+60h], al
0x18000ec6f  jz      short loc_18000ECC2
0x18000ec71  mov     rcx, [rdi+58h]
0x18000ec75  add     rcx, 0A8h; struct _MI_ConstStringField *
0x18000ec7c  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000ec81  test    eax, eax
0x18000ec83  jz      short loc_18000ECC2
0x18000ec85  lea     r9, [rsp+120h+var_F0]
0x18000ec8a  lea     r8, [rsp+120h+var_B0]
0x18000ec8f  xor     edx, edx
0x18000ec91  mov     rcx, [rcx]
0x18000ec94  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000ec99  mov     ebx, eax
0x18000ec9b  test    eax, eax
0x18000ec9d  jnz     short loc_18000ECC2
0x18000ec9f  lea     rax, [rbp+20h+var_70]
0x18000eca3  mov     [rsp+120h+var_100], rax
0x18000eca8  lea     r9, [rsp+120h+var_B0]
0x18000ecad  lea     r8, [rsp+120h+var_F0]
0x18000ecb2  lea     rdx, [rbp+20h+var_90]
0x18000ecb6  lea     rcx, [rsp+120h+var_D0]
0x18000ecbb  call    ?SrSmapiInvokeRemoveReplicationRelationship@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveReplicationRelationship(std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,CWMIContext &)
0x18000ecc0  mov     ebx, eax
0x18000ecc2  mov     edx, ebx; enum _MI_Result
0x18000ecc4  lea     rcx, [rbp+20h+var_70]; this
0x18000ecc8  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000eccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecd4  cmp     rcx, r14
0x18000ecd7  jz      short loc_18000ECF8
0x18000ecd9  test    byte ptr [rcx+1Ch], 1
0x18000ecdd  jz      short loc_18000ECF8
0x18000ecdf  mov     edx, 1Dh
0x18000ece4  mov     r9d, ebx
0x18000ece7  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ecee  mov     rcx, [rcx+10h]
0x18000ecf2  call    WPP_SF_d
0x18000ecf7  nop
0x18000ecf8  lea     rcx, [rsp+120h+var_F0]
0x18000ecfd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed02  nop
0x18000ed03  lea     rcx, [rsp+120h+var_D0]
0x18000ed08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed0d  nop
0x18000ed0e  lea     rcx, [rsp+120h+var_B0]
0x18000ed13  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed18  nop
0x18000ed19  lea     rcx, [rbp+20h+var_90]
0x18000ed1d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed22  nop
0x18000ed23  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000ed2a  mov     [rbp+20h+var_70], rax
0x18000ed2e  lea     rcx, [rbp+20h+var_60]
0x18000ed32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed37  mov     eax, ebx
0x18000ed39  mov     rcx, [rbp+20h+var_20]
0x18000ed3d  xor     rcx, rsp; StackCookie
0x18000ed40  call    __security_check_cookie
0x18000ed45  lea     r11, [rsp+120h+var_10]
0x18000ed4d  mov     rbx, [r11+28h]
0x18000ed51  mov     rsi, [r11+30h]
0x18000ed55  mov     rsp, r11
0x18000ed58  pop     r14
0x18000ed5a  pop     rdi
0x18000ed5b  pop     rbp
0x18000ed5c  retn
```
