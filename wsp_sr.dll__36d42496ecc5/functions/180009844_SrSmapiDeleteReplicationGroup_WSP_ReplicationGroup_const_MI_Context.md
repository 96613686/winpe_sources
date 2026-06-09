# SrSmapiDeleteReplicationGroup(_WSP_ReplicationGroup const *,_MI_Context *)

- ea: `0x180009844`
- end: `0x180009995`
- name: `?SrSmapiDeleteReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEAU_MI_Context@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(const struct _MI_ConstStringField *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003e40`

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
- `0x180009844`
- `0x18000a354`
- `0x18000cb74`
- `0x18001ab60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiDeleteReplicationGroup(const struct _MI_ConstStringField *a1, struct _MI_Context *a2)
{
  enum _MI_Result v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rax
  MI_Uint32 v7; // ebx
  _BYTE v9[32]; // [rsp+28h] [rbp-81h] BYREF
  _QWORD v10[4]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v11[40]; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v12[2]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-9h] BYREF

  v4 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v12, a2);
  std::wstring::wstring((__int64)v10);
  std::wstring::wstring((__int64)v11);
  if ( (unsigned int)MI_STRING_DEFINED(a1 + 4) )
    v4 = (unsigned int)DecodeReplicationGroupObjectId(*v5, 0, v10, v11);
  if ( v4 == MI_RESULT_OK )
  {
    v6 = std::wstring::wstring((__int64)v9, v10);
    v4 = (unsigned int)SrSmapiInvokeDeleteReplicationGroup(v6, v12);
  }
  v7 = SrSmapipDeleteReplicationGroupSetReturn(v4, (struct CWMIContext *)v12);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v12, v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v7);
  std::wstring::_Tidy_deallocate((__int64)v11);
  std::wstring::_Tidy_deallocate((__int64)v10);
  v12[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v13);
  return v7;
}

```

## disassembly

```asm
0x180009844  mov     [rsp-8+arg_8], rbx
0x180009849  mov     [rsp-8+arg_10], rsi
0x18000984e  push    rbp
0x18000984f  push    rdi
0x180009850  push    r14
0x180009852  lea     rbp, [rsp-47h]
0x180009857  sub     rsp, 0F0h
0x18000985e  mov     rax, cs:__security_cookie
0x180009865  xor     rax, rsp
0x180009868  mov     [rbp+57h+var_20], rax
0x18000986c  mov     rdi, rdx
0x18000986f  mov     rsi, rcx
0x180009872  lea     r14, WPP_GLOBAL_Control
0x180009879  mov     ebx, 4
0x18000987e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009885  cmp     rcx, r14
0x180009888  jz      short loc_1800098A2
0x18000988a  test    [rcx+1Ch], bl
0x18000988d  jz      short loc_1800098A2
0x18000988f  lea     edx, [rbx+16h]
0x180009892  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x180009899  mov     rcx, [rcx+10h]
0x18000989d  call    WPP_SF_
0x1800098a2  mov     rdx, rdi; struct _MI_Context *
0x1800098a5  lea     rcx, [rbp+57h+var_70]; this
0x1800098a9  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x1800098ae  nop
0x1800098af  lea     rcx, [rbp+57h+var_B8]
0x1800098b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800098b8  nop
0x1800098b9  lea     rcx, [rbp+57h+var_98]
0x1800098bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800098c2  nop
0x1800098c3  lea     rcx, [rsi+40h]; struct _MI_ConstStringField *
0x1800098c7  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x1800098cc  test    eax, eax
0x1800098ce  jz      short loc_1800098E4
0x1800098d0  lea     r9, [rbp+57h+var_98]
0x1800098d4  lea     r8, [rbp+57h+var_B8]
0x1800098d8  xor     edx, edx
0x1800098da  mov     rcx, [rcx]
0x1800098dd  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x1800098e2  mov     ebx, eax
0x1800098e4  test    ebx, ebx
0x1800098e6  jnz     short loc_180009904
0x1800098e8  lea     rdx, [rbp+57h+var_B8]
0x1800098ec  lea     rcx, [rsp+100h+var_D8]
0x1800098f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800098f6  lea     rdx, [rbp+57h+var_70]
0x1800098fa  mov     rcx, rax
0x1800098fd  call    ?SrSmapiInvokeDeleteReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@@Z; SrSmapiInvokeDeleteReplicationGroup(std::wstring,CWMIContext &)
0x180009902  mov     ebx, eax
0x180009904  lea     rdx, [rbp+57h+var_70]; struct CWMIContext *
0x180009908  mov     ecx, ebx; enum _MI_Result
0x18000990a  call    SrSmapipDeleteReplicationGroupSetReturn
0x18000990f  mov     ebx, eax
0x180009911  mov     edx, eax; enum _MI_Result
0x180009913  lea     rcx, [rbp+57h+var_70]; this
0x180009917  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000991c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009923  cmp     rcx, r14
0x180009926  jz      short loc_180009947
0x180009928  test    byte ptr [rcx+1Ch], 1
0x18000992c  jz      short loc_180009947
0x18000992e  mov     edx, 1Bh
0x180009933  mov     r9d, ebx
0x180009936  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000993d  mov     rcx, [rcx+10h]
0x180009941  call    WPP_SF_d
0x180009946  nop
0x180009947  lea     rcx, [rbp+57h+var_98]
0x18000994b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009950  nop
0x180009951  lea     rcx, [rbp+57h+var_B8]
0x180009955  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000995a  nop
0x18000995b  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180009962  mov     [rbp+57h+var_70], rax
0x180009966  lea     rcx, [rbp+57h+var_60]
0x18000996a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000996f  mov     eax, ebx
0x180009971  mov     rcx, [rbp+57h+var_20]
0x180009975  xor     rcx, rsp; StackCookie
0x180009978  call    __security_check_cookie
0x18000997d  lea     r11, [rsp+100h+var_10]
0x180009985  mov     rbx, [r11+28h]
0x180009989  mov     rsi, [r11+30h]
0x18000998d  mov     rsp, r11
0x180009990  pop     r14
0x180009992  pop     rdi
0x180009993  pop     rbp
0x180009994  retn
```
