# SrSmapiRemoveSyncPair(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_MSFT_StorageObject_ConstArray const *,_MSFT_StorageObject_ConstArray const *,CWMIContext &)

- ea: `0x18000c13c`
- end: `0x18000c342`
- name: `?SrSmapiRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00PEBU_MSFT_StorageObject_ConstArray@@1AEAVCWMIContext@@@Z`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000c348`

## callees

- `0x1800014e0`
- `0x180005884`
- `0x18000590c`
- `0x180005930`
- `0x1800066d0`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000795c`
- `0x1800080d4`
- `0x18000ad2c`
- `0x18000c13c`
- `0x180022b1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SrSmapiRemoveSyncPair(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned int PartitionAccessPath; // ebx
  int v9; // edx
  int v10; // r8d
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 v14; // rsi
  _BYTE v16[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v17; // [rsp+38h] [rbp-71h]
  __int64 v18; // [rsp+40h] [rbp-69h]
  _QWORD v19[3]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v20[24]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v21[32]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v22[32]; // [rsp+98h] [rbp-11h] BYREF

  PartitionAccessPath = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v19);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v20);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v16);
  v11 = *(_DWORD *)(a4 + 8);
  if ( v11 == *(_DWORD *)(a5 + 8) )
  {
    v12 = 0;
    if ( v11 )
    {
      while ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a4 + 8 * v12) + 72LL)
           && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a5 + 8 * v12) + 72LL) )
      {
        std::vector<std::wstring>::emplace_back<wchar_t * &>(v19);
        std::vector<std::wstring>::emplace_back<wchar_t * &>(v20);
        if ( ++v12 >= (unsigned __int64)*(unsigned int *)(a4 + 8) )
          goto LABEL_9;
      }
    }
    else
    {
LABEL_9:
      v13 = v19[0];
      v14 = v19[1];
      while ( v13 != v14 )
      {
        std::wstring::wstring(v22, v13);
        std::wstring::wstring(v21);
        PartitionAccessPath = SrSmapiQueryPartitionAccessPath(v22, a6, v21);
        if ( PartitionAccessPath )
        {
          std::wstring::_Tidy_deallocate(v21);
          std::wstring::_Tidy_deallocate(v22);
          goto LABEL_18;
        }
        if ( v17 == v18 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v16, v17, v21);
        }
        else
        {
          std::wstring::wstring(v17, v21);
          v17 += 32;
        }
        std::wstring::_Tidy_deallocate(v21);
        std::wstring::_Tidy_deallocate(v22);
        v13 += 32;
      }
      PartitionAccessPath = SrSmapiInvokeRemoveSyncPair(a1, v9, v10, (unsigned int)v16);
    }
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_97259de4980931de249eb41af43a46d5_Traceguids,
      PartitionAccessPath);
  std::vector<std::wstring>::_Tidy(v16);
  std::vector<std::wstring>::_Tidy(v20);
  std::vector<std::wstring>::_Tidy(v19);
  return PartitionAccessPath;
}

```

## disassembly

```asm
0x18000c13c  mov     [rsp-8+arg_8], rbx
0x18000c141  push    rbp
0x18000c142  push    rsi
0x18000c143  push    rdi
0x18000c144  push    r12
0x18000c146  push    r13
0x18000c148  push    r14
0x18000c14a  push    r15
0x18000c14c  lea     rbp, [rsp-17h]
0x18000c151  sub     rsp, 0C0h
0x18000c158  mov     rax, cs:__security_cookie
0x18000c15f  xor     rax, rsp
0x18000c162  mov     [rbp+47h+var_38], rax
0x18000c166  mov     rsi, r9
0x18000c169  mov     r12, rcx
0x18000c16c  mov     r14, [rbp+47h+arg_20]
0x18000c170  mov     r15, [rbp+47h+arg_28]
0x18000c174  lea     r13, WPP_GLOBAL_Control
0x18000c17b  mov     ebx, 4
0x18000c180  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c187  cmp     rcx, r13
0x18000c18a  jz      short loc_18000C1A4
0x18000c18c  test    [rcx+1Ch], bl
0x18000c18f  jz      short loc_18000C1A4
0x18000c191  lea     edx, [rbx+20h]
0x18000c194  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c19b  mov     rcx, [rcx+10h]
0x18000c19f  call    WPP_SF_
0x18000c1a4  lea     rcx, [rbp+47h+var_A8]
0x18000c1a8  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c1ad  nop
0x18000c1ae  lea     rcx, [rbp+47h+var_90]
0x18000c1b2  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c1b7  nop
0x18000c1b8  lea     rcx, [rbp+47h+var_C0]
0x18000c1bc  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18000c1c1  nop
0x18000c1c2  mov     eax, [rsi+8]
0x18000c1c5  cmp     eax, [r14+8]
0x18000c1c9  jnz     loc_18000C2D0
0x18000c1cf  xor     edi, edi
0x18000c1d1  test    eax, eax
0x18000c1d3  jz      short loc_18000C223
0x18000c1d5  mov     rax, [rsi]
0x18000c1d8  mov     rdx, [rax+rdi*8]
0x18000c1dc  add     rdx, 40h ; '@'
0x18000c1e0  cmp     byte ptr [rdx+8], 0
0x18000c1e4  jz      loc_18000C2D0
0x18000c1ea  mov     rax, [r14]
0x18000c1ed  mov     rcx, [rax+rdi*8]
0x18000c1f1  cmp     byte ptr [rcx+48h], 0
0x18000c1f5  jz      loc_18000C2D0
0x18000c1fb  lea     rcx, [rbp+47h+var_A8]
0x18000c1ff  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18000c204  mov     rax, [r14]
0x18000c207  mov     rdx, [rax+rdi*8]
0x18000c20b  add     rdx, 40h ; '@'
0x18000c20f  lea     rcx, [rbp+47h+var_90]
0x18000c213  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18000c218  inc     rdi
0x18000c21b  mov     eax, [rsi+8]
0x18000c21e  cmp     rdi, rax
0x18000c221  jb      short loc_18000C1D5
0x18000c223  mov     rdi, [rbp+47h+var_A8]
0x18000c227  mov     rsi, [rbp+47h+var_A0]
0x18000c22b  cmp     rdi, rsi
0x18000c22e  jz      loc_18000C2BD
0x18000c234  mov     rdx, rdi
0x18000c237  lea     rcx, [rbp+47h+var_58]
0x18000c23b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c240  nop
0x18000c241  lea     rcx, [rbp+47h+var_78]
0x18000c245  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000c24a  nop
0x18000c24b  lea     r8, [rbp+47h+var_78]
0x18000c24f  mov     rdx, r15
0x18000c252  lea     rcx, [rbp+47h+var_58]
0x18000c256  call    ?SrSmapiQueryPartitionAccessPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z; SrSmapiQueryPartitionAccessPath(std::wstring const &,CWMIContext &,std::wstring &)
0x18000c25b  mov     ebx, eax
0x18000c25d  test    eax, eax
0x18000c25f  jnz     short loc_18000C2A8
0x18000c261  mov     rax, [rbp+47h+var_B8]
0x18000c265  cmp     rax, [rbp+47h+var_B0]
0x18000c269  jz      short loc_18000C27E
0x18000c26b  lea     rdx, [rbp+47h+var_78]
0x18000c26f  mov     rcx, rax
0x18000c272  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c277  add     [rbp+47h+var_B8], 20h ; ' '
0x18000c27c  jmp     short loc_18000C28F
0x18000c27e  lea     r8, [rbp+47h+var_78]
0x18000c282  mov     rdx, rax
0x18000c285  lea     rcx, [rbp+47h+var_C0]
0x18000c289  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000c28e  nop
0x18000c28f  lea     rcx, [rbp+47h+var_78]
0x18000c293  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c298  nop
0x18000c299  lea     rcx, [rbp+47h+var_58]
0x18000c29d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c2a2  add     rdi, 20h ; ' '
0x18000c2a6  jmp     short loc_18000C22B
0x18000c2a8  lea     rcx, [rbp+47h+var_78]
0x18000c2ac  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c2b1  nop
0x18000c2b2  lea     rcx, [rbp+47h+var_58]
0x18000c2b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c2bb  jmp     short loc_18000C2D0
0x18000c2bd  mov     [rsp+0F0h+var_C8], r15
0x18000c2c2  lea     r9, [rbp+47h+var_C0]
0x18000c2c6  mov     rcx, r12
0x18000c2c9  call    ?SrSmapiInvokeRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1AEAVCWMIContext@@@Z; SrSmapiInvokeRemoveSyncPair(std::wstring const &,std::wstring const &,std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,CWMIContext &)
0x18000c2ce  mov     ebx, eax
0x18000c2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2d7  cmp     rcx, r13
0x18000c2da  jz      short loc_18000C2FB
0x18000c2dc  test    byte ptr [rcx+1Ch], 1
0x18000c2e0  jz      short loc_18000C2FB
0x18000c2e2  mov     edx, 25h ; '%'
0x18000c2e7  mov     r9d, ebx
0x18000c2ea  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000c2f1  mov     rcx, [rcx+10h]
0x18000c2f5  call    WPP_SF_d
0x18000c2fa  nop
0x18000c2fb  lea     rcx, [rbp+47h+var_C0]
0x18000c2ff  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c304  nop
0x18000c305  lea     rcx, [rbp+47h+var_90]
0x18000c309  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c30e  nop
0x18000c30f  lea     rcx, [rbp+47h+var_A8]
0x18000c313  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000c318  mov     eax, ebx
0x18000c31a  mov     rcx, [rbp+47h+var_38]
0x18000c31e  xor     rcx, rsp; StackCookie
0x18000c321  call    __security_check_cookie
0x18000c326  mov     rbx, [rsp+0F0h+arg_8]
0x18000c32e  add     rsp, 0C0h
0x18000c335  pop     r15
0x18000c337  pop     r14
0x18000c339  pop     r13
0x18000c33b  pop     r12
0x18000c33d  pop     rdi
0x18000c33e  pop     rsi
0x18000c33f  pop     rbp
0x18000c340  retn
```
