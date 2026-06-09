# SrSmapiRemoveSyncPair(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_MSFT_StorageObject_ConstArray const *,_MSFT_StorageObject_ConstArray const *,CWMIContext &)

- ea: `0x18000c0a8`
- end: `0x18000c2ad`
- name: `?SrSmapiRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00PEBU_MSFT_StorageObject_ConstArray@@1AEAVCWMIContext@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000c2b4`

## callees

- `0x1800014e0`
- `0x18000584c`
- `0x1800058d4`
- `0x1800058f8`
- `0x180006688`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x18000787c`
- `0x180007f98`
- `0x18000abc4`
- `0x18000c0a8`
- `0x18002295c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiRemoveSyncPair(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct CWMIContext *a6)
{
  unsigned int PartitionAccessPath; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdi
  _QWORD *v13; // rdi
  _QWORD *v14; // rsi
  int v16; // [rsp+20h] [rbp-89h]
  __int64 v17; // [rsp+30h] [rbp-79h] BYREF
  __int64 v18; // [rsp+38h] [rbp-71h]
  __int64 v19; // [rsp+40h] [rbp-69h]
  _QWORD v20[3]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v21[3]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v22[4]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v23[32]; // [rsp+98h] [rbp-11h] BYREF

  PartitionAccessPath = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v20);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v21);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(&v17);
  v11 = *(_DWORD *)(a4 + 8);
  if ( v11 == *(_DWORD *)(a5 + 8) )
  {
    v12 = 0;
    if ( v11 )
    {
      while ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a4 + 8 * v12) + 72LL)
           && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a5 + 8 * v12) + 72LL) )
      {
        std::vector<std::wstring>::emplace_back<wchar_t * &>(v20);
        std::vector<std::wstring>::emplace_back<wchar_t * &>(v21);
        if ( ++v12 >= (unsigned __int64)*(unsigned int *)(a4 + 8) )
          goto LABEL_9;
      }
    }
    else
    {
LABEL_9:
      v13 = (_QWORD *)v20[0];
      v14 = (_QWORD *)v20[1];
      while ( v13 != v14 )
      {
        std::wstring::wstring((__int64)v23, v13);
        std::wstring::wstring((__int64)v22);
        PartitionAccessPath = SrSmapiQueryPartitionAccessPath((__int64)v23, a6, v22);
        if ( PartitionAccessPath )
        {
          std::wstring::_Tidy_deallocate((__int64)v22);
          std::wstring::_Tidy_deallocate((__int64)v23);
          goto LABEL_18;
        }
        if ( v18 == v19 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v17, v18, v22);
        }
        else
        {
          std::wstring::wstring(v18, v22);
          v18 += 32;
        }
        std::wstring::_Tidy_deallocate((__int64)v22);
        std::wstring::_Tidy_deallocate((__int64)v23);
        v13 += 4;
      }
      PartitionAccessPath = SrSmapiInvokeRemoveSyncPair(a1, v9, v10, (__int64)&v17, v16, a6);
    }
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_97259de4980931de249eb41af43a46d5_Traceguids,
      PartitionAccessPath);
  std::vector<std::wstring>::_Tidy((__int64)&v17);
  std::vector<std::wstring>::_Tidy((__int64)v21);
  std::vector<std::wstring>::_Tidy((__int64)v20);
  return PartitionAccessPath;
}

```

## disassembly

```asm
0x18000c0a8  mov     [rsp-8+arg_8], rbx
0x18000c0ad  push    rbp
0x18000c0ae  push    rsi
0x18000c0af  push    rdi
0x18000c0b0  push    r12
0x18000c0b2  push    r13
0x18000c0b4  push    r14
0x18000c0b6  push    r15
0x18000c0b8  lea     rbp, [rsp-17h]
0x18000c0bd  sub     rsp, 0C0h
0x18000c0c4  mov     rax, cs:__security_cookie
0x18000c0cb  xor     rax, rsp
0x18000c0ce  mov     [rbp+47h+var_38], rax
0x18000c0d2  mov     rsi, r9
0x18000c0d5  mov     r12, rcx
0x18000c0d8  mov     r14, [rbp+47h+arg_20]
0x18000c0dc  mov     r15, [rbp+47h+arg_28]
0x18000c0e0  lea     r13, WPP_GLOBAL_Control
0x18000c0e7  mov     ebx, 4
0x18000c0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0f3  cmp     rcx, r13
0x18000c0f6  jz      short loc_18000C110
0x18000c0f8  test    [rcx+1Ch], bl
0x18000c0fb  jz      short loc_18000C110
0x18000c0fd  lea     edx, [rbx+20h]
0x18000c100  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c107  mov     rcx, [rcx+10h]
0x18000c10b  call    WPP_SF_
0x18000c110  lea     rcx, [rbp+47h+var_A8]
0x18000c114  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c119  nop
0x18000c11a  lea     rcx, [rbp+47h+var_90]
0x18000c11e  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c123  nop
0x18000c124  lea     rcx, [rbp+47h+var_C0]
0x18000c128  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c12d  nop
0x18000c12e  mov     eax, [rsi+8]
0x18000c131  cmp     eax, [r14+8]
0x18000c135  jnz     loc_18000C23C
0x18000c13b  xor     edi, edi
0x18000c13d  test    eax, eax
0x18000c13f  jz      short loc_18000C18F
0x18000c141  mov     rax, [rsi]
0x18000c144  mov     rdx, [rax+rdi*8]
0x18000c148  add     rdx, 40h ; '@'
0x18000c14c  cmp     byte ptr [rdx+8], 0
0x18000c150  jz      loc_18000C23C
0x18000c156  mov     rax, [r14]
0x18000c159  mov     rcx, [rax+rdi*8]
0x18000c15d  cmp     byte ptr [rcx+48h], 0
0x18000c161  jz      loc_18000C23C
0x18000c167  lea     rcx, [rbp+47h+var_A8]
0x18000c16b  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18000c170  mov     rax, [r14]
0x18000c173  mov     rdx, [rax+rdi*8]
0x18000c177  add     rdx, 40h ; '@'
0x18000c17b  lea     rcx, [rbp+47h+var_90]
0x18000c17f  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18000c184  inc     rdi
0x18000c187  mov     eax, [rsi+8]
0x18000c18a  cmp     rdi, rax
0x18000c18d  jb      short loc_18000C141
0x18000c18f  mov     rdi, [rbp+47h+var_A8]
0x18000c193  mov     rsi, [rbp+47h+var_A0]
0x18000c197  cmp     rdi, rsi
0x18000c19a  jz      loc_18000C229
0x18000c1a0  mov     rdx, rdi
0x18000c1a3  lea     rcx, [rbp+47h+var_58]
0x18000c1a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c1ac  nop
0x18000c1ad  lea     rcx, [rbp+47h+var_78]
0x18000c1b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000c1b6  nop
0x18000c1b7  lea     r8, [rbp+47h+var_78]
0x18000c1bb  mov     rdx, r15
0x18000c1be  lea     rcx, [rbp+47h+var_58]
0x18000c1c2  call    ?SrSmapiQueryPartitionAccessPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z; SrSmapiQueryPartitionAccessPath(std::wstring const &,CWMIContext &,std::wstring &)
0x18000c1c7  mov     ebx, eax
0x18000c1c9  test    eax, eax
0x18000c1cb  jnz     short loc_18000C214
0x18000c1cd  mov     rax, [rbp+47h+var_B8]
0x18000c1d1  cmp     rax, [rbp+47h+var_B0]
0x18000c1d5  jz      short loc_18000C1EA
0x18000c1d7  lea     rdx, [rbp+47h+var_78]
0x18000c1db  mov     rcx, rax
0x18000c1de  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c1e3  add     [rbp+47h+var_B8], 20h ; ' '
0x18000c1e8  jmp     short loc_18000C1FB
0x18000c1ea  lea     r8, [rbp+47h+var_78]
0x18000c1ee  mov     rdx, rax
0x18000c1f1  lea     rcx, [rbp+47h+var_C0]
0x18000c1f5  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000c1fa  nop
0x18000c1fb  lea     rcx, [rbp+47h+var_78]
0x18000c1ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c204  nop
0x18000c205  lea     rcx, [rbp+47h+var_58]
0x18000c209  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c20e  add     rdi, 20h ; ' '
0x18000c212  jmp     short loc_18000C197
0x18000c214  lea     rcx, [rbp+47h+var_78]
0x18000c218  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c21d  nop
0x18000c21e  lea     rcx, [rbp+47h+var_58]
0x18000c222  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c227  jmp     short loc_18000C23C
0x18000c229  mov     [rsp+0F0h+var_C8], r15
0x18000c22e  lea     r9, [rbp+47h+var_C0]
0x18000c232  mov     rcx, r12
0x18000c235  call    ?SrSmapiInvokeRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveSyncPair(std::wstring const &,std::wstring const &,std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,CWMIContext &)
0x18000c23a  mov     ebx, eax
0x18000c23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c243  cmp     rcx, r13
0x18000c246  jz      short loc_18000C267
0x18000c248  test    byte ptr [rcx+1Ch], 1
0x18000c24c  jz      short loc_18000C267
0x18000c24e  mov     edx, 25h ; '%'
0x18000c253  mov     r9d, ebx
0x18000c256  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c25d  mov     rcx, [rcx+10h]
0x18000c261  call    WPP_SF_d
0x18000c266  nop
0x18000c267  lea     rcx, [rbp+47h+var_C0]
0x18000c26b  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c270  nop
0x18000c271  lea     rcx, [rbp+47h+var_90]
0x18000c275  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c27a  nop
0x18000c27b  lea     rcx, [rbp+47h+var_A8]
0x18000c27f  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c284  mov     eax, ebx
0x18000c286  mov     rcx, [rbp+47h+var_38]
0x18000c28a  xor     rcx, rsp; StackCookie
0x18000c28d  call    __security_check_cookie
0x18000c292  mov     rbx, [rsp+0F0h+arg_8]
0x18000c29a  add     rsp, 0C0h
0x18000c2a1  pop     r15
0x18000c2a3  pop     r14
0x18000c2a5  pop     r13
0x18000c2a7  pop     r12
0x18000c2a9  pop     rdi
0x18000c2aa  pop     rsi
0x18000c2ab  pop     rbp
0x18000c2ac  retn
```
