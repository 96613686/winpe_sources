# SrSmapiRemoveMember(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_RemoveMember const *,_MI_Context *)

- ea: `0x18000bec0`
- end: `0x18000c09f`
- name: `?SrSmapiRemoveMember@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_RemoveMember@@PEAU_MI_Context@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(const struct _MI_ConstStringField *, const struct _WSP_ReplicationGroup_RemoveMember *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180003fd0`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800058d4`
- `0x1800058f8`
- `0x180005910`
- `0x180006688`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008df8`
- `0x180008f0c`
- `0x18000aa28`
- `0x18000bec0`
- `0x18000d2ac`
- `0x18000e054`
- `0x18001ab60`

## pseudocode

```c
__int64 __fastcall SrSmapiRemoveMember(
        const struct _MI_ConstStringField *a1,
        const struct _WSP_ReplicationGroup_RemoveMember *a2,
        struct _MI_Context *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // edi
  _DWORD *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rdx
  MI_Uint32 v11; // ebx
  _BYTE v13[8]; // [rsp+20h] [rbp-A9h] BYREF
  _QWORD v14[3]; // [rsp+28h] [rbp-A1h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v16[4]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v18[64]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v19[32]; // [rsp+D0h] [rbp+7h] BYREF

  v6 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v17, a3);
  std::wstring::wstring((__int64)v16);
  v13[0] = 0;
  std::wstring::wstring((__int64)v19);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v14);
  if ( (unsigned int)MI_STRING_DEFINED(a1 + 4) )
  {
    std::wstring::wstring((__int64)v15);
    v7 = DecodeReplicationGroupObjectId(a1[4].value, v13, v16, v15);
    std::wstring::_Tidy_deallocate((__int64)v15);
    if ( v7 )
    {
      v6 = v7;
    }
    else if ( a2 != (const struct _WSP_ReplicationGroup_RemoveMember *)-88LL )
    {
      v8 = (_DWORD *)((char *)a2 + 80);
      if ( a2 != (const struct _WSP_ReplicationGroup_RemoveMember *)-80LL )
      {
        v9 = 0;
        if ( *v8 )
        {
          while ( 1 )
          {
            v10 = *(_QWORD *)(*((_QWORD *)a2 + 9) + 8 * v9);
            if ( !*(_BYTE *)(v10 + 72) )
              break;
            std::wstring::wstring((__int64)v15, *(_QWORD *)(v10 + 64));
            std::vector<std::wstring>::push_back(v14, v15);
            std::wstring::_Tidy_deallocate((__int64)v15);
            if ( ++v9 >= (unsigned __int64)(unsigned int)*v8 )
              goto LABEL_11;
          }
        }
        else
        {
LABEL_11:
          v6 = SrSmapiInvokeRemoveMember(v16, (__int64)v14, (struct CWMIContext *)v17);
        }
      }
    }
  }
  v11 = SrSmapipRemoveMemberSetReturn(v6, v17);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v17, v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v11);
  std::vector<std::wstring>::_Tidy((__int64)v14);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v16);
  v17[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v18);
  return v11;
}

```

## disassembly

```asm
0x18000bec0  mov     [rsp-8+arg_10], rbx
0x18000bec5  push    rbp
0x18000bec6  push    rsi
0x18000bec7  push    rdi
0x18000bec8  push    r12
0x18000beca  push    r14
0x18000becc  lea     rbp, [rsp-37h]
0x18000bed1  sub     rsp, 100h
0x18000bed8  mov     rax, cs:__security_cookie
0x18000bedf  xor     rax, rsp
0x18000bee2  mov     [rbp+57h+var_30], rax
0x18000bee6  mov     rdi, r8
0x18000bee9  mov     r14, rdx
0x18000beec  mov     rsi, rcx
0x18000beef  lea     r12, WPP_GLOBAL_Control
0x18000bef6  mov     ebx, 4
0x18000befb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf02  cmp     rcx, r12
0x18000bf05  jz      short loc_18000BF1F
0x18000bf07  test    [rcx+1Ch], bl
0x18000bf0a  jz      short loc_18000BF1F
0x18000bf0c  lea     edx, [rbx+4Bh]
0x18000bf0f  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000bf16  mov     rcx, [rcx+10h]
0x18000bf1a  call    WPP_SF_
0x18000bf1f  mov     rdx, rdi; struct _MI_Context *
0x18000bf22  lea     rcx, [rbp+57h+var_A0]; this
0x18000bf26  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000bf2b  nop
0x18000bf2c  lea     rcx, [rbp+57h+var_C0]
0x18000bf30  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bf35  nop
0x18000bf36  mov     [rsp+120h+var_100], 0
0x18000bf3b  lea     rcx, [rbp+57h+var_50]
0x18000bf3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bf44  nop
0x18000bf45  lea     rcx, [rsp+120h+var_F8]
0x18000bf4a  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000bf4f  nop
0x18000bf50  lea     rcx, [rsi+40h]; struct _MI_ConstStringField *
0x18000bf54  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000bf59  test    eax, eax
0x18000bf5b  jz      loc_18000C004
0x18000bf61  lea     rcx, [rsp+120h+var_E0]
0x18000bf66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bf6b  nop
0x18000bf6c  lea     r9, [rsp+120h+var_E0]
0x18000bf71  lea     r8, [rbp+57h+var_C0]
0x18000bf75  lea     rdx, [rsp+120h+var_100]
0x18000bf7a  mov     rcx, [rsi+40h]
0x18000bf7e  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000bf83  mov     edi, eax
0x18000bf85  lea     rcx, [rsp+120h+var_E0]
0x18000bf8a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bf8f  test    edi, edi
0x18000bf91  jnz     short loc_18000C002
0x18000bf93  lea     rax, [r14+58h]
0x18000bf97  test    rax, rax
0x18000bf9a  jz      short loc_18000C004
0x18000bf9c  lea     rdi, [r14+50h]
0x18000bfa0  test    rdi, rdi
0x18000bfa3  jz      short loc_18000C004
0x18000bfa5  xor     esi, esi
0x18000bfa7  cmp     [rdi], esi
0x18000bfa9  jbe     short loc_18000BFEC
0x18000bfab  mov     rax, [r14+48h]
0x18000bfaf  mov     rdx, [rax+rsi*8]
0x18000bfb3  cmp     byte ptr [rdx+48h], 0
0x18000bfb7  jz      short loc_18000C004
0x18000bfb9  mov     rdx, [rdx+40h]
0x18000bfbd  lea     rcx, [rsp+120h+var_E0]
0x18000bfc2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000bfc7  nop
0x18000bfc8  lea     rdx, [rsp+120h+var_E0]
0x18000bfcd  lea     rcx, [rsp+120h+var_F8]
0x18000bfd2  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18000bfd7  nop
0x18000bfd8  lea     rcx, [rsp+120h+var_E0]
0x18000bfdd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bfe2  inc     rsi
0x18000bfe5  mov     eax, [rdi]
0x18000bfe7  cmp     rsi, rax
0x18000bfea  jb      short loc_18000BFAB
0x18000bfec  lea     r8, [rbp+57h+var_A0]
0x18000bff0  lea     rdx, [rsp+120h+var_F8]
0x18000bff5  lea     rcx, [rbp+57h+var_C0]
0x18000bff9  call    ?SrSmapiInvokeRemoveMember@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveMember(std::wstring const &,std::vector<std::wstring> const &,CWMIContext &)
0x18000bffe  mov     ebx, eax
0x18000c000  jmp     short loc_18000C004
0x18000c002  mov     ebx, edi
0x18000c004  lea     rdx, [rbp+57h+var_A0]
0x18000c008  mov     ecx, ebx
0x18000c00a  call    SrSmapipRemoveMemberSetReturn
0x18000c00f  mov     ebx, eax
0x18000c011  mov     edx, eax; enum _MI_Result
0x18000c013  lea     rcx, [rbp+57h+var_A0]; this
0x18000c017  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000c01c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c023  cmp     rcx, r12
0x18000c026  jz      short loc_18000C047
0x18000c028  test    byte ptr [rcx+1Ch], 1
0x18000c02c  jz      short loc_18000C047
0x18000c02e  mov     edx, 50h ; 'P'
0x18000c033  mov     r9d, ebx
0x18000c036  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c03d  mov     rcx, [rcx+10h]
0x18000c041  call    WPP_SF_d
0x18000c046  nop
0x18000c047  lea     rcx, [rsp+120h+var_F8]
0x18000c04c  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c051  nop
0x18000c052  lea     rcx, [rbp+57h+var_50]
0x18000c056  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c05b  nop
0x18000c05c  lea     rcx, [rbp+57h+var_C0]
0x18000c060  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c065  nop
0x18000c066  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000c06d  mov     [rbp+57h+var_A0], rax
0x18000c071  lea     rcx, [rbp+57h+var_90]
0x18000c075  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c07a  mov     eax, ebx
0x18000c07c  mov     rcx, [rbp+57h+var_30]
0x18000c080  xor     rcx, rsp; StackCookie
0x18000c083  call    __security_check_cookie
0x18000c088  mov     rbx, [rsp+120h+arg_10]
0x18000c090  add     rsp, 100h
0x18000c097  pop     r14
0x18000c099  pop     r12
0x18000c09b  pop     rdi
0x18000c09c  pop     rsi
0x18000c09d  pop     rbp
0x18000c09e  retn
```
