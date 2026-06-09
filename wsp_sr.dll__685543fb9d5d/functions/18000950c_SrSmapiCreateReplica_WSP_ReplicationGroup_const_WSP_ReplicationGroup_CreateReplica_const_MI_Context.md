# SrSmapiCreateReplica(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_CreateReplica const *,_MI_Context *)

- ea: `0x18000950c`
- end: `0x18000970e`
- name: `?SrSmapiCreateReplica@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_CreateReplica@@PEAU_MI_Context@@@Z`
- size: `514`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup *, const struct _WSP_ReplicationGroup_CreateReplica *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003cc0`

## callees

- `0x1800014e0`
- `0x180005884`
- `0x18000590c`
- `0x180005948`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x180008f8c`
- `0x1800090c4`
- `0x18000950c`
- `0x180009714`
- `0x18000a2c4`
- `0x18001ab74`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SrSmapiCreateReplica(
        const struct _MI_ConstStringField *a1,
        const struct _WSP_ReplicationGroup_CreateReplica *a2,
        struct _MI_Context *a3)
{
  enum _MI_Result v6; // ebx
  _QWORD *v7; // rcx
  enum _MI_Result v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  enum _MI_Result ReplicaSetReturn; // ebx
  _BYTE v15[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v18[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v19[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v20[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v21[40]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v22[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v23[64]; // [rsp+140h] [rbp+40h] BYREF

  v6 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v22, a3);
  std::wstring::wstring(v20);
  std::wstring::wstring(v19);
  std::wstring::wstring(v21);
  std::wstring::wstring(v18);
  if ( (unsigned int)MI_STRING_DEFINED(a1 + 4) )
  {
    v8 = (unsigned int)DecodeReplicationGroupObjectId(*v7, 0, v20, v21);
    if ( v8 )
    {
LABEL_10:
      v6 = v8;
      goto LABEL_11;
    }
    if ( (unsigned int)MI_STRING_DEFINED((const struct _MI_ConstStringField *)((char *)a2 + 104)) )
      v6 = (unsigned int)DecodeReplicationGroupObjectId(*v9, 0, v19, v18);
    if ( v6 == MI_RESULT_OK )
    {
      v10 = std::wstring::wstring(v15, v18);
      v11 = std::wstring::wstring(v16, v19);
      v12 = std::wstring::wstring(v17, v20);
      v8 = (unsigned int)SrSmapiInvokeCreateReplicationPartnership(v12, v11, v10, v22);
      goto LABEL_10;
    }
  }
LABEL_11:
  ReplicaSetReturn = (unsigned int)SrSmapiCreateReplicaSetReturn(v6, (struct CWMIContext *)v22);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v22, ReplicaSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_97259de4980931de249eb41af43a46d5_Traceguids,
      (unsigned int)ReplicaSetReturn);
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v20);
  v22[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v23);
  return (unsigned int)ReplicaSetReturn;
}

```

## disassembly

```asm
0x18000950c  mov     [rsp-8+arg_10], rbx
0x180009511  push    rbp
0x180009512  push    rsi
0x180009513  push    rdi
0x180009514  push    r14
0x180009516  push    r15
0x180009518  lea     rbp, [rsp-90h]
0x180009520  sub     rsp, 190h
0x180009527  mov     rax, cs:__security_cookie
0x18000952e  xor     rax, rsp
0x180009531  mov     [rbp+0B0h+var_30], rax
0x180009538  mov     rdi, r8
0x18000953b  mov     rsi, rdx
0x18000953e  mov     r14, rcx
0x180009541  lea     r15, WPP_GLOBAL_Control
0x180009548  mov     ebx, 4
0x18000954d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009554  cmp     rcx, r15
0x180009557  jz      short loc_180009571
0x180009559  test    [rcx+1Ch], bl
0x18000955c  jz      short loc_180009571
0x18000955e  lea     edx, [rbx+33h]
0x180009561  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x180009568  mov     rcx, [rcx+10h]
0x18000956c  call    WPP_SF_
0x180009571  mov     rdx, rdi; struct _MI_Context *
0x180009574  lea     rcx, [rbp+0B0h+var_80]; this
0x180009578  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18000957d  nop
0x18000957e  lea     rcx, [rbp+0B0h+var_C8]
0x180009582  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009587  nop
0x180009588  lea     rcx, [rbp+0B0h+var_E8]
0x18000958c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009591  nop
0x180009592  lea     rcx, [rbp+0B0h+var_A8]
0x180009596  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000959b  nop
0x18000959c  lea     rcx, [rbp+0B0h+var_108]
0x1800095a0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800095a5  nop
0x1800095a6  lea     rcx, [r14+40h]; struct _MI_ConstStringField *
0x1800095aa  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x1800095af  test    eax, eax
0x1800095b1  jz      loc_18000964A
0x1800095b7  lea     r9, [rbp+0B0h+var_A8]
0x1800095bb  lea     r8, [rbp+0B0h+var_C8]
0x1800095bf  xor     edx, edx
0x1800095c1  mov     rcx, [rcx]
0x1800095c4  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x1800095c9  test    eax, eax
0x1800095cb  jnz     short loc_180009648
0x1800095cd  lea     rcx, [rsi+68h]; struct _MI_ConstStringField *
0x1800095d1  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x1800095d6  test    eax, eax
0x1800095d8  jz      short loc_1800095EE
0x1800095da  lea     r9, [rbp+0B0h+var_108]
0x1800095de  lea     r8, [rbp+0B0h+var_E8]
0x1800095e2  xor     edx, edx
0x1800095e4  mov     rcx, [rcx]
0x1800095e7  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x1800095ec  mov     ebx, eax
0x1800095ee  test    ebx, ebx
0x1800095f0  jnz     short loc_18000964A
0x1800095f2  lea     rax, [rsp+1B0h+var_168]
0x1800095f7  mov     [rsp+1B0h+var_180], rax
0x1800095fc  lea     rdx, [rbp+0B0h+var_108]
0x180009600  lea     rcx, [rsp+1B0h+var_168]
0x180009605  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000960a  mov     rdi, rax
0x18000960d  lea     rax, [rsp+1B0h+var_148]
0x180009612  mov     [rsp+1B0h+var_178], rax
0x180009617  lea     rdx, [rbp+0B0h+var_E8]
0x18000961b  lea     rcx, [rsp+1B0h+var_148]
0x180009620  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009625  mov     rbx, rax
0x180009628  lea     rdx, [rbp+0B0h+var_C8]
0x18000962c  lea     rcx, [rbp+0B0h+var_128]
0x180009630  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009635  nop
0x180009636  lea     r9, [rbp+0B0h+var_80]
0x18000963a  mov     r8, rdi
0x18000963d  mov     rdx, rbx
0x180009640  mov     rcx, rax
0x180009643  call    ?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationPartnership(std::wstring,std::wstring,std::wstring,CWMIContext &)
0x180009648  mov     ebx, eax
0x18000964a  cmp     byte ptr [rsi+60h], 0
0x18000964e  jz      short loc_180009656
0x180009650  mov     r9, [rsi+58h]
0x180009654  jmp     short loc_180009659
0x180009656  xor     r9d, r9d
0x180009659  lea     rax, [rbp+0B0h+var_80]
0x18000965d  mov     [rsp+1B0h+var_190], rax; struct CWMIContext *
0x180009662  lea     r8, [rbp+0B0h+var_108]
0x180009666  lea     rdx, [rbp+0B0h+var_E8]
0x18000966a  mov     ecx, ebx; enum _MI_Result
0x18000966c  call    SrSmapiCreateReplicaSetReturn
0x180009671  mov     ebx, eax
0x180009673  mov     edx, eax; enum _MI_Result
0x180009675  lea     rcx, [rbp+0B0h+var_80]; this
0x180009679  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000967e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009685  cmp     rcx, r15
0x180009688  jz      short loc_1800096A9
0x18000968a  test    byte ptr [rcx+1Ch], 1
0x18000968e  jz      short loc_1800096A9
0x180009690  mov     edx, 38h ; '8'
0x180009695  mov     r9d, ebx
0x180009698  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000969f  mov     rcx, [rcx+10h]
0x1800096a3  call    WPP_SF_d
0x1800096a8  nop
0x1800096a9  lea     rcx, [rbp+0B0h+var_108]
0x1800096ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096b2  nop
0x1800096b3  lea     rcx, [rbp+0B0h+var_A8]
0x1800096b7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096bc  nop
0x1800096bd  lea     rcx, [rbp+0B0h+var_E8]
0x1800096c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096c6  nop
0x1800096c7  lea     rcx, [rbp+0B0h+var_C8]
0x1800096cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096d0  nop
0x1800096d1  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x1800096d8  mov     [rbp+0B0h+var_80], rax
0x1800096dc  lea     rcx, [rbp+0B0h+var_70]
0x1800096e0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096e5  mov     eax, ebx
0x1800096e7  mov     rcx, [rbp+0B0h+var_30]
0x1800096ee  xor     rcx, rsp; StackCookie
0x1800096f1  call    __security_check_cookie
0x1800096f6  mov     rbx, [rsp+1B0h+arg_10]
0x1800096fe  add     rsp, 190h
0x180009705  pop     r15
0x180009707  pop     r14
0x180009709  pop     rdi
0x18000970a  pop     rsi
0x18000970b  pop     rbp
0x18000970c  retn
```
