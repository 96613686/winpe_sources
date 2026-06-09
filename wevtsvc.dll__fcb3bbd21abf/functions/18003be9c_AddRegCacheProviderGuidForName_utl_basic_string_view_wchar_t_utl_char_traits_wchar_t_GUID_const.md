# AddRegCacheProviderGuidForName(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_GUID const &)

- ea: `0x18003be9c`
- end: `0x18003bfff`
- name: `?AddRegCacheProviderGuidForName@@YAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBU_GUID@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007b190`
- `0x18007feac`

## callees

- `0x18003be9c`
- `0x18003c008`
- `0x180092008`
- `0x1800c13f4`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bec4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bec4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003bf58`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bf35`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bf35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AddRegCacheProviderGuidForName(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  __int128 pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+4Ch] [rbp-2Ch]
  int v16; // [rsp+50h] [rbp-28h]
  __int64 v17; // [rsp+90h] [rbp+18h] BYREF
  RTL_SRWLOCK *v18; // [rsp+98h] [rbp+20h]

  v18 = &stru_180111508;
  AcquireSRWLockExclusive(&stru_180111508);
  if ( (__int64 *)qword_180111520 == &qword_180111510 )
  {
    v6 = &qword_180111510;
LABEL_12:
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>>,0>::emplace_hint<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,_GUID const &,0>(
      v4,
      (unsigned int)&v17,
      (_DWORD)v6,
      (_DWORD)a1,
      a2);
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids, 14);
      }
      pExceptionObject = 0;
      v13 = 0;
      v14 = 14;
      v15 = -1;
      v16 = 309;
      throw (EvtException *)&pExceptionObject;
    }
    goto LABEL_10;
  }
  v5 = (__int64 *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
                    v4,
                    a1);
  LODWORD(v6) = (_DWORD)v5;
  if ( v5 == &qword_180111510 )
    goto LABEL_12;
  v7 = a1[1];
  v8 = v5[3];
  v9 = (v5[4] - v8) >> 1;
  if ( (v7 | (unsigned __int64)v9) > 0x7FFFFFFF )
    __int2c();
  v10 = 2;
  if ( v8 )
    v10 = v5[3];
  v11 = 2;
  if ( *a1 )
    v11 = *a1;
  if ( CompareStringOrdinal((LPCWCH)v11, v7, (LPCWCH)v10, v9, 1) == 1 )
    goto LABEL_12;
LABEL_10:
  ReleaseSRWLockExclusive(&stru_180111508);
}

```

## disassembly

```asm
0x18003be9c  mov     rax, rsp
0x18003be9f  mov     [rax+8], rbx
0x18003bea3  mov     [rax+10h], rsi
0x18003bea7  push    rdi
0x18003bea8  push    r14
0x18003beaa  push    r15
0x18003beac  sub     rsp, 60h
0x18003beb0  mov     rsi, rdx
0x18003beb3  mov     rdi, rcx
0x18003beb6  lea     r15, stru_180111508
0x18003bebd  mov     [rax+20h], r15
0x18003bec1  mov     rcx, r15; SRWLock
0x18003bec4  call    cs:__imp_AcquireSRWLockExclusive
0x18003beca  nop
0x18003becb  lea     r14, qword_180111510
0x18003bed2  cmp     cs:qword_180111520, r14
0x18003bed9  jz      loc_18003BF5F
0x18003bedf  mov     rdx, rdi
0x18003bee2  call    ??$_LowerBoundNonEmpty@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@utl@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18003bee7  mov     rbx, rax
0x18003beea  cmp     rax, r14
0x18003beed  jz      short loc_18003BF62
0x18003beef  mov     rdx, [rdi+8]; cchCount1
0x18003bef3  mov     rcx, [rax+18h]
0x18003bef7  mov     r9, [rax+20h]
0x18003befb  sub     r9, rcx
0x18003befe  sar     r9, 1; cchCount2
0x18003bf01  mov     rax, r9
0x18003bf04  or      rax, rdx
0x18003bf07  cmp     rax, 7FFFFFFFh
0x18003bf0d  ja      loc_18003BFF7
0x18003bf13  mov     r8d, 2
0x18003bf19  test    rcx, rcx
0x18003bf1c  cmovnz  r8, rcx; lpString2
0x18003bf20  mov     ecx, 2
0x18003bf25  cmp     qword ptr [rdi], 0
0x18003bf29  cmovnz  rcx, [rdi]; lpString1
0x18003bf2d  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18003bf35  call    cs:__imp_CompareStringOrdinal
0x18003bf3b  cmp     eax, 1
0x18003bf3e  jz      short loc_18003BF62
0x18003bf40  mov     rcx, r15
0x18003bf43  lea     r11, [rsp+78h+var_18]
0x18003bf48  mov     rbx, [r11+20h]
0x18003bf4c  mov     rsi, [r11+28h]
0x18003bf50  mov     rsp, r11
0x18003bf53  pop     r15
0x18003bf55  pop     r14
0x18003bf57  pop     rdi
0x18003bf58  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18003bf5f  mov     rbx, r14
0x18003bf62  mov     qword ptr [rsp+78h+bIgnoreCase], rsi
0x18003bf67  mov     r9, rdi
0x18003bf6a  mov     r8, rbx
0x18003bf6d  lea     rdx, [rsp+78h+arg_10]
0x18003bf75  call    ??$emplace_hint@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBU_GUID@@$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@utl@@@1@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_GUID@@@utl@@@1@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>>,0>::emplace_hint<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,_GUID const &,0>(utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,_GUID>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,_GUID const &)
0x18003bf7a  cmp     [rsp+78h+arg_10], 0
0x18003bf83  jnz     short loc_18003BF40
0x18003bf85  lea     rax, WPP_GLOBAL_Control
0x18003bf8c  mov     ebx, 0Eh
0x18003bf91  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf98  cmp     rcx, rax
0x18003bf9b  jz      short loc_18003BFBF
0x18003bf9d  test    byte ptr [rcx+1Ch], 4
0x18003bfa1  jz      short loc_18003BFBF
0x18003bfa3  cmp     byte ptr [rcx+19h], 2
0x18003bfa7  jb      short loc_18003BFBF
0x18003bfa9  lea     edx, [rbx-2]
0x18003bfac  mov     r9d, ebx
0x18003bfaf  lea     r8, WPP_85f31c24d3db3aa75d76f685e4bf8a71_Traceguids
0x18003bfb6  mov     rcx, [rcx+10h]
0x18003bfba  call    WPP_SF_d
0x18003bfbf  xorps   xmm0, xmm0
0x18003bfc2  movdqu  [rsp+78h+pExceptionObject], xmm0
0x18003bfc8  mov     [rsp+78h+var_38], 0
0x18003bfd1  mov     [rsp+78h+var_30], ebx
0x18003bfd5  mov     [rsp+78h+var_2C], 0FFFFFFFFh
0x18003bfdd  mov     [rsp+78h+var_28], 135h
0x18003bfe5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003bfec  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18003bff1  call    _CxxThrowException_0
0x18003bff7  int     2Ch; Windows NT - assertion failure
0x18003bff9  jmp     loc_18003BF13
```
