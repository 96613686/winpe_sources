# SrSmapiCreateReplica(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_CreateReplica const *,_MI_Context *)

- ea: `0x18000934c`
- end: `0x18000954d`
- name: `?SrSmapiCreateReplica@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_CreateReplica@@PEAU_MI_Context@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(const struct _MI_ConstStringField *, const struct _WSP_ReplicationGroup_CreateReplica *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003d60`

## callees

- `0x1800014e0`
- `0x18000584c`
- `0x1800058d4`
- `0x180005910`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008df8`
- `0x180008f0c`
- `0x18000934c`
- `0x180009554`
- `0x18000a16c`
- `0x18001ab60`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  MI_Uint32 ReplicaSetReturn; // ebx
  _BYTE v15[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v18[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v19[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v20[4]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v21[40]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v22[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v23[64]; // [rsp+140h] [rbp+40h] BYREF

  v6 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v22, a3);
  std::wstring::wstring((__int64)v20);
  std::wstring::wstring((__int64)v19);
  std::wstring::wstring((__int64)v21);
  std::wstring::wstring((__int64)v18);
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
      v10 = std::wstring::wstring((__int64)v15, v18);
      v11 = std::wstring::wstring((__int64)v16, v19);
      v12 = std::wstring::wstring((__int64)v17, v20);
      v8 = (unsigned int)SrSmapiInvokeCreateReplicationPartnership(v12, v11, v10, v22);
      goto LABEL_10;
    }
  }
LABEL_11:
  ReplicaSetReturn = SrSmapiCreateReplicaSetReturn(v6, (struct CWMIContext *)v22);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v22, ReplicaSetReturn);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_97259de4980931de249eb41af43a46d5_Traceguids, ReplicaSetReturn);
  std::wstring::_Tidy_deallocate((__int64)v18);
  std::wstring::_Tidy_deallocate((__int64)v21);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v20);
  v22[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v23);
  return ReplicaSetReturn;
}

```

## disassembly

```asm
0x18000934c  mov     [rsp-8+arg_10], rbx
0x180009351  push    rbp
0x180009352  push    rsi
0x180009353  push    rdi
0x180009354  push    r14
0x180009356  push    r15
0x180009358  lea     rbp, [rsp-90h]
0x180009360  sub     rsp, 190h
0x180009367  mov     rax, cs:__security_cookie
0x18000936e  xor     rax, rsp
0x180009371  mov     [rbp+0B0h+var_30], rax
0x180009378  mov     rdi, r8
0x18000937b  mov     rsi, rdx
0x18000937e  mov     r14, rcx
0x180009381  lea     r15, WPP_GLOBAL_Control
0x180009388  mov     ebx, 4
0x18000938d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009394  cmp     rcx, r15
0x180009397  jz      short loc_1800093B1
0x180009399  test    [rcx+1Ch], bl
0x18000939c  jz      short loc_1800093B1
0x18000939e  lea     edx, [rbx+33h]
0x1800093a1  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x1800093a8  mov     rcx, [rcx+10h]
0x1800093ac  call    WPP_SF_
0x1800093b1  mov     rdx, rdi; struct _MI_Context *
0x1800093b4  lea     rcx, [rbp+0B0h+var_80]; this
0x1800093b8  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x1800093bd  nop
0x1800093be  lea     rcx, [rbp+0B0h+var_C8]
0x1800093c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800093c7  nop
0x1800093c8  lea     rcx, [rbp+0B0h+var_E8]
0x1800093cc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800093d1  nop
0x1800093d2  lea     rcx, [rbp+0B0h+var_A8]
0x1800093d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800093db  nop
0x1800093dc  lea     rcx, [rbp+0B0h+var_108]
0x1800093e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800093e5  nop
0x1800093e6  lea     rcx, [r14+40h]; struct _MI_ConstStringField *
0x1800093ea  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x1800093ef  test    eax, eax
0x1800093f1  jz      loc_18000948A
0x1800093f7  lea     r9, [rbp+0B0h+var_A8]
0x1800093fb  lea     r8, [rbp+0B0h+var_C8]
0x1800093ff  xor     edx, edx
0x180009401  mov     rcx, [rcx]
0x180009404  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x180009409  test    eax, eax
0x18000940b  jnz     short loc_180009488
0x18000940d  lea     rcx, [rsi+68h]; struct _MI_ConstStringField *
0x180009411  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x180009416  test    eax, eax
0x180009418  jz      short loc_18000942E
0x18000941a  lea     r9, [rbp+0B0h+var_108]
0x18000941e  lea     r8, [rbp+0B0h+var_E8]
0x180009422  xor     edx, edx
0x180009424  mov     rcx, [rcx]
0x180009427  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x18000942c  mov     ebx, eax
0x18000942e  test    ebx, ebx
0x180009430  jnz     short loc_18000948A
0x180009432  lea     rax, [rsp+1B0h+var_168]
0x180009437  mov     [rsp+1B0h+var_180], rax
0x18000943c  lea     rdx, [rbp+0B0h+var_108]
0x180009440  lea     rcx, [rsp+1B0h+var_168]
0x180009445  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000944a  mov     rdi, rax
0x18000944d  lea     rax, [rsp+1B0h+var_148]
0x180009452  mov     [rsp+1B0h+var_178], rax
0x180009457  lea     rdx, [rbp+0B0h+var_E8]
0x18000945b  lea     rcx, [rsp+1B0h+var_148]
0x180009460  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009465  mov     rbx, rax
0x180009468  lea     rdx, [rbp+0B0h+var_C8]
0x18000946c  lea     rcx, [rbp+0B0h+var_128]
0x180009470  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009475  nop
0x180009476  lea     r9, [rbp+0B0h+var_80]
0x18000947a  mov     r8, rdi
0x18000947d  mov     rdx, rbx
0x180009480  mov     rcx, rax
0x180009483  call    ?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z; SrSmapiInvokeCreateReplicationPartnership(std::wstring,std::wstring,std::wstring,CWMIContext &)
0x180009488  mov     ebx, eax
0x18000948a  cmp     byte ptr [rsi+60h], 0
0x18000948e  jz      short loc_180009496
0x180009490  mov     r9, [rsi+58h]
0x180009494  jmp     short loc_180009499
0x180009496  xor     r9d, r9d
0x180009499  lea     rax, [rbp+0B0h+var_80]
0x18000949d  mov     [rsp+1B0h+var_190], rax; struct CWMIContext *
0x1800094a2  lea     r8, [rbp+0B0h+var_108]
0x1800094a6  lea     rdx, [rbp+0B0h+var_E8]
0x1800094aa  mov     ecx, ebx; enum _MI_Result
0x1800094ac  call    SrSmapiCreateReplicaSetReturn
0x1800094b1  mov     ebx, eax
0x1800094b3  mov     edx, eax; enum _MI_Result
0x1800094b5  lea     rcx, [rbp+0B0h+var_80]; this
0x1800094b9  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x1800094be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094c5  cmp     rcx, r15
0x1800094c8  jz      short loc_1800094E9
0x1800094ca  test    byte ptr [rcx+1Ch], 1
0x1800094ce  jz      short loc_1800094E9
0x1800094d0  mov     edx, 38h ; '8'
0x1800094d5  mov     r9d, ebx
0x1800094d8  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x1800094df  mov     rcx, [rcx+10h]
0x1800094e3  call    WPP_SF_d
0x1800094e8  nop
0x1800094e9  lea     rcx, [rbp+0B0h+var_108]
0x1800094ed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800094f2  nop
0x1800094f3  lea     rcx, [rbp+0B0h+var_A8]
0x1800094f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800094fc  nop
0x1800094fd  lea     rcx, [rbp+0B0h+var_E8]
0x180009501  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009506  nop
0x180009507  lea     rcx, [rbp+0B0h+var_C8]
0x18000950b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009510  nop
0x180009511  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180009518  mov     [rbp+0B0h+var_80], rax
0x18000951c  lea     rcx, [rbp+0B0h+var_70]
0x180009520  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009525  mov     eax, ebx
0x180009527  mov     rcx, [rbp+0B0h+var_30]
0x18000952e  xor     rcx, rsp; StackCookie
0x180009531  call    __security_check_cookie
0x180009536  mov     rbx, [rsp+1B0h+arg_10]
0x18000953e  add     rsp, 190h
0x180009545  pop     r15
0x180009547  pop     r14
0x180009549  pop     rdi
0x18000954a  pop     rsi
0x18000954b  pop     rbp
0x18000954c  retn
```
