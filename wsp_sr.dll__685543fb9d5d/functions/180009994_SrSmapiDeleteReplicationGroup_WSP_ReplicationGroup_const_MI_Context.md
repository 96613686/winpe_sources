# SrSmapiDeleteReplicationGroup(_WSP_ReplicationGroup const *,_MI_Context *)

- ea: `0x180009994`
- end: `0x180009ae6`
- name: `?SrSmapiDeleteReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEAU_MI_Context@@@Z`
- size: `338`
- prototype: `enum _MI_Result(const struct _WSP_ReplicationGroup *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003db0`

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
- `0x180009994`
- `0x18000a4b0`
- `0x18000cb64`
- `0x18001ab74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiDeleteReplicationGroup(const struct _MI_ConstStringField *a1, struct _MI_Context *a2)
{
  enum _MI_Result v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rax
  enum _MI_Result v7; // ebx
  _BYTE v9[32]; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v11[40]; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v12[2]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-9h] BYREF

  v4 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  CWMIContext::CWMIContext((CWMIContext *)v12, a2);
  std::wstring::wstring(v10);
  std::wstring::wstring(v11);
  if ( (unsigned int)MI_STRING_DEFINED(a1 + 4) )
    v4 = (unsigned int)DecodeReplicationGroupObjectId(*v5, 0, v10, v11);
  if ( v4 == MI_RESULT_OK )
  {
    v6 = std::wstring::wstring(v9, v10);
    v4 = (unsigned int)SrSmapiInvokeDeleteReplicationGroup(v6, v12);
  }
  v7 = (unsigned int)SrSmapipDeleteReplicationGroupSetReturn(v4, (struct CWMIContext *)v12);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v12, v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v7);
  std::wstring::_Tidy_deallocate(v11);
  std::wstring::_Tidy_deallocate(v10);
  v12[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009994  mov     [rsp-8+arg_8], rbx
0x180009999  mov     [rsp-8+arg_10], rsi
0x18000999e  push    rbp
0x18000999f  push    rdi
0x1800099a0  push    r14
0x1800099a2  lea     rbp, [rsp-47h]
0x1800099a7  sub     rsp, 0F0h
0x1800099ae  mov     rax, cs:__security_cookie
0x1800099b5  xor     rax, rsp
0x1800099b8  mov     [rbp+57h+var_20], rax
0x1800099bc  mov     rdi, rdx
0x1800099bf  mov     rsi, rcx
0x1800099c2  lea     r14, WPP_GLOBAL_Control
0x1800099c9  mov     ebx, 4
0x1800099ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099d5  cmp     rcx, r14
0x1800099d8  jz      short loc_1800099F2
0x1800099da  test    [rcx+1Ch], bl
0x1800099dd  jz      short loc_1800099F2
0x1800099df  lea     edx, [rbx+16h]
0x1800099e2  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x1800099e9  mov     rcx, [rcx+10h]
0x1800099ed  call    WPP_SF_
0x1800099f2  mov     rdx, rdi; struct _MI_Context *
0x1800099f5  lea     rcx, [rbp+57h+var_70]; this
0x1800099f9  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x1800099fe  nop
0x1800099ff  lea     rcx, [rbp+57h+var_B8]
0x180009a03  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009a08  nop
0x180009a09  lea     rcx, [rbp+57h+var_98]
0x180009a0d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009a12  nop
0x180009a13  lea     rcx, [rsi+40h]; struct _MI_ConstStringField *
0x180009a17  call    ?MI_STRING_DEFINED@@YAHPEBU_MI_ConstStringField@@@Z; MI_STRING_DEFINED(_MI_ConstStringField const *)
0x180009a1c  test    eax, eax
0x180009a1e  jz      short loc_180009A34
0x180009a20  lea     r9, [rbp+57h+var_98]
0x180009a24  lea     r8, [rbp+57h+var_B8]
0x180009a28  xor     edx, edx
0x180009a2a  mov     rcx, [rcx]
0x180009a2d  call    ?DecodeReplicationGroupObjectId@@YA?AW4_MI_Result@@PEB_WPEA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; DecodeReplicationGroupObjectId(wchar_t const *,bool *,std::wstring &,std::wstring &)
0x180009a32  mov     ebx, eax
0x180009a34  test    ebx, ebx
0x180009a36  jnz     short loc_180009A54
0x180009a38  lea     rdx, [rbp+57h+var_B8]
0x180009a3c  lea     rcx, [rsp+100h+var_D8]
0x180009a41  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009a46  lea     rdx, [rbp+57h+var_70]
0x180009a4a  mov     rcx, rax
0x180009a4d  call    ?SrSmapiInvokeDeleteReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@@Z; SrSmapiInvokeDeleteReplicationGroup(std::wstring,CWMIContext &)
0x180009a52  mov     ebx, eax
0x180009a54  lea     rdx, [rbp+57h+var_70]; struct CWMIContext *
0x180009a58  mov     ecx, ebx; enum _MI_Result
0x180009a5a  call    SrSmapipDeleteReplicationGroupSetReturn
0x180009a5f  mov     ebx, eax
0x180009a61  mov     edx, eax; enum _MI_Result
0x180009a63  lea     rcx, [rbp+57h+var_70]; this
0x180009a67  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x180009a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a73  cmp     rcx, r14
0x180009a76  jz      short loc_180009A97
0x180009a78  test    byte ptr [rcx+1Ch], 1
0x180009a7c  jz      short loc_180009A97
0x180009a7e  mov     edx, 1Bh
0x180009a83  mov     r9d, ebx
0x180009a86  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x180009a8d  mov     rcx, [rcx+10h]
0x180009a91  call    WPP_SF_d
0x180009a96  nop
0x180009a97  lea     rcx, [rbp+57h+var_98]
0x180009a9b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009aa0  nop
0x180009aa1  lea     rcx, [rbp+57h+var_B8]
0x180009aa5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009aaa  nop
0x180009aab  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180009ab2  mov     [rbp+57h+var_70], rax
0x180009ab6  lea     rcx, [rbp+57h+var_60]
0x180009aba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009abf  mov     eax, ebx
0x180009ac1  mov     rcx, [rbp+57h+var_20]
0x180009ac5  xor     rcx, rsp; StackCookie
0x180009ac8  call    __security_check_cookie
0x180009acd  lea     r11, [rsp+100h+var_10]
0x180009ad5  mov     rbx, [r11+28h]
0x180009ad9  mov     rsi, [r11+30h]
0x180009add  mov     rsp, r11
0x180009ae0  pop     r14
0x180009ae2  pop     rdi
0x180009ae3  pop     rbp
0x180009ae4  retn
```
