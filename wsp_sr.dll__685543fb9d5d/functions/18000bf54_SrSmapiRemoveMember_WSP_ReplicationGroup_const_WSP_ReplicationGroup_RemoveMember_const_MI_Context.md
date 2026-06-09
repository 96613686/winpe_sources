# SrSmapiRemoveMember(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_RemoveMember const *,_MI_Context *)

- ea: `0x18000bf54`
- end: `0x18000c134`
- name: `?SrSmapiRemoveMember@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_RemoveMember@@PEAU_MI_Context@@@Z`
- size: `480`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup *, const struct _WSP_ReplicationGroup_RemoveMember *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180003f40`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x18000590c`
- `0x180005930`
- `0x180005948`
- `0x1800066d0`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180008f8c`
- `0x1800090c4`
- `0x18000ab90`
- `0x18000bf54`
- `0x18000d1d0`
- `0x18000df9c`
- `0x18001ab74`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  enum _MI_Result v11; // ebx
  _BYTE v13[8]; // [rsp+20h] [rbp-A9h] BYREF
  _BYTE v14[24]; // [rsp+28h] [rbp-A1h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v18[64]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v19[32]; // [rsp+D0h] [rbp+7h] BYREF

  v6 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v17, a3);
  std::wstring::wstring(v16);
  v13[0] = 0;
  std::wstring::wstring(v19);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v14);
  if ( (unsigned int)MI_STRING_DEFINED(a1 + 4) )
  {
    std::wstring::wstring(v15);
    v7 = ((__int64 (__fastcall *)(const MI_Char *, _BYTE *, _BYTE *, _BYTE *))DecodeReplicationGroupObjectId)(
           a1[4].value,
           v13,
           v16,
           v15);
    std::wstring::_Tidy_deallocate(v15);
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
            std::wstring::wstring(v15, *(_QWORD *)(v10 + 64));
            std::vector<std::wstring>::push_back(v14, v15);
            std::wstring::_Tidy_deallocate(v15);
            if ( ++v9 >= (unsigned __int64)(unsigned int)*v8 )
              goto LABEL_11;
          }
        }
        else
        {
LABEL_11:
          v6 = SrSmapiInvokeRemoveMember(v16, v14, v17);
        }
      }
    }
  }
  v11 = (unsigned int)SrSmapipRemoveMemberSetReturn(v6, v17);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v17, v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      WPP_97259de4980931de249eb41af43a46d5_Traceguids,
      (unsigned int)v11);
  std::vector<std::wstring>::_Tidy(v14);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v16);
  v17[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000bf54  mov     [rsp-8+arg_10], rbx
0x18000bf59  push    rbp
0x18000bf5a  push    rsi
0x18000bf5b  push    rdi
0x18000bf5c  push    r12
0x18000bf5e  push    r14
0x18000bf60  lea     rbp, [rsp-37h]
0x18000bf65  sub     rsp, 100h
0x18000bf6c  mov     rax, cs:__security_cookie
0x18000bf73  xor     rax, rsp
0x18000bf76  mov     [rbp+57h+var_30], rax
0x18000bf7a  mov     rdi, r8
0x18000bf7d  mov     r14, rdx
0x18000bf80  mov     rsi, rcx
0x18000bf83  lea     r12, WPP_GLOBAL_Control
0x18000bf8a  mov     ebx, 4
0x18000bf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf96  cmp     rcx, r12
0x18000bf99  jz      short loc_18000BFB3
0x18000bf9b  test    [rcx+1Ch], bl
0x18000bf9e  jz      short loc_18000BFB3
0x18000bfa0  lea     edx, [rbx+4Bh]
0x18000bfa3  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000bfaa  mov     rcx, [rcx+10h]
0x18000bfae  call    WPP_SF_
0x18000bfb3  mov     rdx, rdi; struct _MI_Context *
0x18000bfb6  lea     rcx, [rbp+57h+var_A0]; this
0x18000bfba  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000bfbf  nop
0x18000bfc0  lea     rcx, [rbp+57h+var_C0]
0x18000bfc4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bfc9  nop
0x18000bfca  mov     [rsp+120h+var_100], 0
0x18000bfcf  lea     rcx, [rbp+57h+var_50]
0x18000bfd3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bfd8  nop
0x18000bfd9  lea     rcx, [rsp+120h+var_F8]
0x18000bfde  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000bfe3  nop
0x18000bfe4  lea     rcx, [rsi+40h]; struct _MI_ConstStringField *
0x18000bfe8  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x18000bfed  test    eax, eax
0x18000bfef  jz      loc_18000C098
0x18000bff5  lea     rcx, [rsp+120h+var_E0]
0x18000bffa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000bfff  nop
0x18000c000  lea     r9, [rsp+120h+var_E0]
0x18000c005  lea     r8, [rbp+57h+var_C0]
0x18000c009  lea     rdx, [rsp+120h+var_100]
0x18000c00e  mov     rcx, [rsi+40h]
0x18000c012  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000c017  mov     edi, eax
0x18000c019  lea     rcx, [rsp+120h+var_E0]
0x18000c01e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c023  test    edi, edi
0x18000c025  jnz     short loc_18000C096
0x18000c027  lea     rax, [r14+58h]
0x18000c02b  test    rax, rax
0x18000c02e  jz      short loc_18000C098
0x18000c030  lea     rdi, [r14+50h]
0x18000c034  test    rdi, rdi
0x18000c037  jz      short loc_18000C098
0x18000c039  xor     esi, esi
0x18000c03b  cmp     [rdi], esi
0x18000c03d  jbe     short loc_18000C080
0x18000c03f  mov     rax, [r14+48h]
0x18000c043  mov     rdx, [rax+rsi*8]
0x18000c047  cmp     byte ptr [rdx+48h], 0
0x18000c04b  jz      short loc_18000C098
0x18000c04d  mov     rdx, [rdx+40h]
0x18000c051  lea     rcx, [rsp+120h+var_E0]
0x18000c056  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000c05b  nop
0x18000c05c  lea     rdx, [rsp+120h+var_E0]
0x18000c061  lea     rcx, [rsp+120h+var_F8]
0x18000c066  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18000c06b  nop
0x18000c06c  lea     rcx, [rsp+120h+var_E0]
0x18000c071  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c076  inc     rsi
0x18000c079  mov     eax, [rdi]
0x18000c07b  cmp     rsi, rax
0x18000c07e  jb      short loc_18000C03F
0x18000c080  lea     r8, [rbp+57h+var_A0]
0x18000c084  lea     rdx, [rsp+120h+var_F8]
0x18000c089  lea     rcx, [rbp+57h+var_C0]
0x18000c08d  call    ?SrSmapiInvokeRemoveMember@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveMember(std::wstring const &,std::vector<std::wstring> const &,CWMIContext &)
0x18000c092  mov     ebx, eax
0x18000c094  jmp     short loc_18000C098
0x18000c096  mov     ebx, edi
0x18000c098  lea     rdx, [rbp+57h+var_A0]
0x18000c09c  mov     ecx, ebx
0x18000c09e  call    SrSmapipRemoveMemberSetReturn
0x18000c0a3  mov     ebx, eax
0x18000c0a5  mov     edx, eax; enum _MI_Result
0x18000c0a7  lea     rcx, [rbp+57h+var_A0]; this
0x18000c0ab  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000c0b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0b7  cmp     rcx, r12
0x18000c0ba  jz      short loc_18000C0DB
0x18000c0bc  test    byte ptr [rcx+1Ch], 1
0x18000c0c0  jz      short loc_18000C0DB
0x18000c0c2  mov     edx, 50h ; 'P'
0x18000c0c7  mov     r9d, ebx
0x18000c0ca  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c0d1  mov     rcx, [rcx+10h]
0x18000c0d5  call    WPP_SF_d
0x18000c0da  nop
0x18000c0db  lea     rcx, [rsp+120h+var_F8]
0x18000c0e0  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c0e5  nop
0x18000c0e6  lea     rcx, [rbp+57h+var_50]
0x18000c0ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c0ef  nop
0x18000c0f0  lea     rcx, [rbp+57h+var_C0]
0x18000c0f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c0f9  nop
0x18000c0fa  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000c101  mov     [rbp+57h+var_A0], rax
0x18000c105  lea     rcx, [rbp+57h+var_90]
0x18000c109  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c10e  mov     eax, ebx
0x18000c110  mov     rcx, [rbp+57h+var_30]
0x18000c114  xor     rcx, rsp; StackCookie
0x18000c117  call    __security_check_cookie
0x18000c11c  mov     rbx, [rsp+120h+arg_10]
0x18000c124  add     rsp, 100h
0x18000c12b  pop     r14
0x18000c12d  pop     r12
0x18000c12f  pop     rdi
0x18000c130  pop     rsi
0x18000c131  pop     rbp
0x18000c132  retn
```
