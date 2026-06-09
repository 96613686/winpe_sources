# SrSmapiDeleteReplicationRelationship(_WSP_ReplicationGroup_DeleteReplicationRelationship const *,_MI_Context *)

- ea: `0x18000ebd4`
- end: `0x18000ed89`
- name: `?SrSmapiDeleteReplicationRelationship@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup_DeleteReplicationRelationship@@PEAU_MI_Context@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(const struct _WSP_ReplicationGroup_DeleteReplicationRelationship *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180003f00`

## callees

- `0x1800014e0`
- `0x1800058d4`
- `0x180005910`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008df8`
- `0x180008f0c`
- `0x18000ebd4`
- `0x18000f290`
- `0x18001ab60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiDeleteReplicationRelationship(
        const struct _WSP_ReplicationGroup_DeleteReplicationRelationship *a1,
        struct _MI_Context *a2)
{
  MI_Uint32 v4; // ebx
  _QWORD *v5; // rcx
  MI_Uint32 v6; // eax
  _QWORD *v7; // rcx
  _BYTE v9[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v13[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v14[64]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v13, a2);
  std::wstring::wstring((__int64)v12);
  std::wstring::wstring((__int64)v11);
  std::wstring::wstring((__int64)v10);
  std::wstring::wstring((__int64)v9);
  if ( *((_BYTE *)a1 + 80)
    && (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)(*((_QWORD *)a1 + 9) + 64LL)) )
  {
    v6 = DecodeReplicationGroupObjectId(*v5, 0, v12, v10);
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
        v4 = DecodeReplicationGroupObjectId(*v7, 0, v11, v9);
        if ( !v4 )
        {
          v6 = SrSmapiInvokeRemoveReplicationRelationship(
                 (unsigned int)v10,
                 (unsigned int)v12,
                 (unsigned int)v9,
                 (unsigned int)v11,
                 (__int64)v13);
          goto LABEL_11;
        }
      }
    }
  }
LABEL_12:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v13, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, v4);
  std::wstring::_Tidy_deallocate((__int64)v9);
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v11);
  std::wstring::_Tidy_deallocate((__int64)v12);
  v13[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v14);
  return v4;
}

```

## disassembly

```asm
0x18000ebd4  mov     [rsp-8+arg_8], rbx
0x18000ebd9  mov     [rsp-8+arg_10], rsi
0x18000ebde  push    rbp
0x18000ebdf  push    rdi
0x18000ebe0  push    r14
0x18000ebe2  lea     rbp, [rsp-10h]
0x18000ebe7  sub     rsp, 110h
0x18000ebee  mov     rax, cs:__security_cookie
0x18000ebf5  xor     rax, rsp
0x18000ebf8  mov     [rbp+20h+var_20], rax
0x18000ebfc  mov     rsi, rdx
0x18000ebff  mov     rdi, rcx
0x18000ec02  lea     r14, WPP_GLOBAL_Control
0x18000ec09  mov     ebx, 4
0x18000ec0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec15  cmp     rcx, r14
0x18000ec18  jz      short loc_18000EC32
0x18000ec1a  test    [rcx+1Ch], bl
0x18000ec1d  jz      short loc_18000EC32
0x18000ec1f  lea     edx, [rbx+18h]
0x18000ec22  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ec29  mov     rcx, [rcx+10h]
0x18000ec2d  call    WPP_SF_
0x18000ec32  mov     rdx, rsi; struct _MI_Context *
0x18000ec35  lea     rcx, [rbp+20h+var_70]; this
0x18000ec39  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000ec3e  nop
0x18000ec3f  lea     rcx, [rbp+20h+var_90]
0x18000ec43  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec48  nop
0x18000ec49  lea     rcx, [rsp+120h+var_B0]
0x18000ec4e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec53  nop
0x18000ec54  lea     rcx, [rsp+120h+var_D0]
0x18000ec59  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec5e  nop
0x18000ec5f  lea     rcx, [rsp+120h+var_F0]
0x18000ec64  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ec69  nop
0x18000ec6a  cmp     byte ptr [rdi+50h], 0
0x18000ec6e  jz      short loc_18000ECEE
0x18000ec70  mov     rcx, [rdi+48h]
0x18000ec74  add     rcx, 40h ; '@'; struct _MI_ConstStringField *
0x18000ec78  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000ec7d  test    eax, eax
0x18000ec7f  jz      short loc_18000ECEE
0x18000ec81  lea     r9, [rsp+120h+var_D0]
0x18000ec86  lea     r8, [rbp+20h+var_90]
0x18000ec8a  xor     edx, edx
0x18000ec8c  mov     rcx, [rcx]
0x18000ec8f  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000ec94  test    eax, eax
0x18000ec96  jnz     short loc_18000ECEC
0x18000ec98  cmp     [rdi+60h], al
0x18000ec9b  jz      short loc_18000ECEE
0x18000ec9d  mov     rcx, [rdi+58h]
0x18000eca1  add     rcx, 0A8h; struct _MI_ConstStringField *
0x18000eca8  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000ecad  test    eax, eax
0x18000ecaf  jz      short loc_18000ECEE
0x18000ecb1  lea     r9, [rsp+120h+var_F0]
0x18000ecb6  lea     r8, [rsp+120h+var_B0]
0x18000ecbb  xor     edx, edx
0x18000ecbd  mov     rcx, [rcx]
0x18000ecc0  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000ecc5  mov     ebx, eax
0x18000ecc7  test    eax, eax
0x18000ecc9  jnz     short loc_18000ECEE
0x18000eccb  lea     rax, [rbp+20h+var_70]
0x18000eccf  mov     [rsp+120h+var_100], rax
0x18000ecd4  lea     r9, [rsp+120h+var_B0]
0x18000ecd9  lea     r8, [rsp+120h+var_F0]
0x18000ecde  lea     rdx, [rbp+20h+var_90]
0x18000ece2  lea     rcx, [rsp+120h+var_D0]
0x18000ece7  call    ?SrSmapiInvokeRemoveReplicationRelationship@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveReplicationRelationship(std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,CWMIContext &)
0x18000ecec  mov     ebx, eax
0x18000ecee  mov     edx, ebx; enum _MI_Result
0x18000ecf0  lea     rcx, [rbp+20h+var_70]; this
0x18000ecf4  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000ecf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed00  cmp     rcx, r14
0x18000ed03  jz      short loc_18000ED24
0x18000ed05  test    byte ptr [rcx+1Ch], 1
0x18000ed09  jz      short loc_18000ED24
0x18000ed0b  mov     edx, 1Dh
0x18000ed10  mov     r9d, ebx
0x18000ed13  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ed1a  mov     rcx, [rcx+10h]
0x18000ed1e  call    WPP_SF_d
0x18000ed23  nop
0x18000ed24  lea     rcx, [rsp+120h+var_F0]
0x18000ed29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed2e  nop
0x18000ed2f  lea     rcx, [rsp+120h+var_D0]
0x18000ed34  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed39  nop
0x18000ed3a  lea     rcx, [rsp+120h+var_B0]
0x18000ed3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed44  nop
0x18000ed45  lea     rcx, [rbp+20h+var_90]
0x18000ed49  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed4e  nop
0x18000ed4f  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000ed56  mov     [rbp+20h+var_70], rax
0x18000ed5a  lea     rcx, [rbp+20h+var_60]
0x18000ed5e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ed63  mov     eax, ebx
0x18000ed65  mov     rcx, [rbp+20h+var_20]
0x18000ed69  xor     rcx, rsp; StackCookie
0x18000ed6c  call    __security_check_cookie
0x18000ed71  lea     r11, [rsp+120h+var_10]
0x18000ed79  mov     rbx, [r11+28h]
0x18000ed7d  mov     rsi, [r11+30h]
0x18000ed81  mov     rsp, r11
0x18000ed84  pop     r14
0x18000ed86  pop     rdi
0x18000ed87  pop     rbp
0x18000ed88  retn
```
