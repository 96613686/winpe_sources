# CProtocolHandler::HandleClusterDisconnect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x18001d364`
- end: `0x18001d68d`
- name: `?HandleClusterDisconnect@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00K@Z`
- size: `809`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032e00`

## callees

- `0x18001d364`
- `0x18001d694`
- `0x18001dbfc`
- `0x18001dcac`
- `0x18001dd14`
- `0x18001ddc8`
- `0x18001de04`
- `0x18001e0ac`
- `0x18001e1e4`
- `0x18001fbd0`
- `0x180033cd0`
- `0x1800343f8`
- `0x180034480`
- `0x180034944`
- `0x1800351fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d63b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d63b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CProtocolHandler::HandleClusterDisconnect(__int64 a1, _QWORD *a2, __int64 *a3, __int64 a4, char a5)
{
  CProtocolHandler *v7; // r13
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  CClusterConnection *v12; // rdi
  int v13; // r15d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r9
  char *v18; // rcx
  _QWORD *v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rax
  _QWORD *v24; // r9
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v29; // [rsp+38h] [rbp-59h] BYREF
  __int64 v30; // [rsp+40h] [rbp-51h]
  _QWORD *v31; // [rsp+48h] [rbp-49h]
  __int64 *v32; // [rsp+50h] [rbp-41h]
  __int64 v33; // [rsp+58h] [rbp-39h]
  _BYTE v34[32]; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v35[32]; // [rsp+80h] [rbp-11h] BYREF

  v30 = a4;
  v31 = a2;
  v32 = a3;
  v33 = a4;
  v7 = WitnessProtocolHandler;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  if ( !*((_DWORD *)v7 + 32) )
    goto LABEL_54;
  if ( (a5 & 1) != 0 )
  {
    v9 = std::operator+<unsigned short>(v35, a2);
    v10 = std::operator+<unsigned short>(v34, v9, a3);
    v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v7 + 24,
                       &v29,
                       v10);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v35);
    if ( v11 == *((_QWORD *)v7 + 3) )
      v12 = 0;
    else
      v12 = *(CClusterConnection **)(v11 + 64);
    v13 = a5 & 2;
  }
  else
  {
    v13 = a5 & 2;
    if ( (a5 & 2) == 0 )
      goto LABEL_43;
    v14 = std::operator+<unsigned short>(v35, a2);
    v15 = std::operator+<unsigned short>(v34, v14, a3);
    v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v7 + 40,
                       &v29,
                       v15);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v35);
    if ( v11 == *((_QWORD *)v7 + 5) )
      goto LABEL_43;
    v12 = *(CClusterConnection **)(v11 + 64);
  }
  if ( !v12 )
  {
LABEL_43:
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      if ( (unsigned __int64)a3[3] <= 7 )
        v26 = (__int64)a3;
      else
        v26 = *a3;
      if ( a2[3] <= 7u )
        LODWORD(v27) = (_DWORD)a2;
      else
        v27 = *a2;
      WPP_SF_SS(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 33, v8, v27, v26);
    }
    v25 = 87;
    goto LABEL_55;
  }
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( (unsigned __int64)a3[3] <= 7 )
      v16 = (__int64)a3;
    else
      v16 = *a3;
    if ( a2[3] <= 7u )
      LODWORD(v17) = (_DWORD)a2;
    else
      v17 = *a2;
    WPP_SF_SS(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 34, v8, v17, v16);
  }
  if ( (a5 & 1) != 0 )
  {
    v18 = (char *)v7 + 24;
  }
  else
  {
    if ( !v13 )
      goto LABEL_26;
    v18 = (char *)v7 + 40;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    v18,
    v11);
LABEL_26:
  if ( CClusterConnection::ReleaseRegisterReference(v12) )
  {
LABEL_54:
    v25 = 0;
LABEL_55:
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)v7 + 10));
    goto LABEL_56;
  }
  if ( (a5 & 1) != 0 )
  {
    if ( a2[3] <= 7u )
      v19 = a2;
    else
      v19 = (_QWORD *)*a2;
    std::wstring::wstring(v34, v19);
    v20 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Eqrange<std::wstring>(
                       (char *)v7 + 8,
                       v35,
                       v34);
    v21 = *v20;
    v22 = v20[1];
    v23 = *v20;
    v29 = v23;
    while ( v23 != v22 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v29);
      v23 = v29;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
      (char *)v7 + 8,
      v21,
      v22);
    std::wstring::~wstring(v34);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)v7 + 10));
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( a2[3] <= 7u )
      v24 = a2;
    else
      v24 = (_QWORD *)*a2;
    WPP_SF_S(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 35, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v24);
  }
  CClusterConnection::Terminate(v12);
  v25 = 0;
LABEL_56:
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(v30);
  return v25;
}

```

## disassembly

```asm
0x18001d364  mov     [rsp-8+arg_0], rbx
0x18001d369  push    rbp
0x18001d36a  push    rsi
0x18001d36b  push    rdi
0x18001d36c  push    r12
0x18001d36e  push    r13
0x18001d370  push    r14
0x18001d372  push    r15
0x18001d374  lea     rbp, [rsp-1Fh]
0x18001d379  sub     rsp, 0B0h
0x18001d380  mov     rax, cs:__security_cookie
0x18001d387  xor     rax, rsp
0x18001d38a  mov     [rbp+4Fh+var_40], rax
0x18001d38e  mov     rax, r9
0x18001d391  mov     [rbp+4Fh+var_A0], rax
0x18001d395  mov     r14, r8
0x18001d398  mov     rsi, rdx
0x18001d39b  mov     [rbp+4Fh+var_98], rdx
0x18001d39f  mov     [rbp+4Fh+var_90], r8
0x18001d3a3  mov     [rbp+4Fh+var_88], rax
0x18001d3a7  mov     r13, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18001d3ae  mov     [rbp+4Fh+var_B0], 0
0x18001d3b5  mov     rcx, [r13+50h]; lpCriticalSection
0x18001d3b9  call    cs:__imp_EnterCriticalSection
0x18001d3c0  nop     dword ptr [rax+rax+00h]
0x18001d3c5  cmp     dword ptr [r13+80h], 0
0x18001d3cd  jz      loc_18001D634
0x18001d3d3  mov     r15d, [rbp+4Fh+arg_20]
0x18001d3d7  mov     r12d, r15d
0x18001d3da  and     r12d, 1
0x18001d3de  jz      short loc_18001D436
0x18001d3e0  mov     rdx, rsi
0x18001d3e3  lea     rcx, [rbp+4Fh+var_60]
0x18001d3e7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001d3ec  nop
0x18001d3ed  mov     r8, r14
0x18001d3f0  mov     rdx, rax
0x18001d3f3  lea     rcx, [rbp+4Fh+var_80]
0x18001d3f7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001d3fc  mov     r8, rax
0x18001d3ff  lea     rdx, [rbp+4Fh+var_A8]
0x18001d403  lea     rcx, [r13+18h]
0x18001d407  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001d40c  mov     rbx, [rax]
0x18001d40f  lea     rcx, [rbp+4Fh+var_80]
0x18001d413  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d418  nop
0x18001d419  lea     rcx, [rbp+4Fh+var_60]
0x18001d41d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d422  cmp     rbx, [r13+18h]
0x18001d426  jnz     short loc_18001D42C
0x18001d428  xor     edi, edi
0x18001d42a  jmp     short loc_18001D430
0x18001d42c  mov     rdi, [rbx+40h]
0x18001d430  and     r15d, 2
0x18001d434  jmp     short loc_18001D490
0x18001d436  and     r15d, 2
0x18001d43a  jz      loc_18001D5DD
0x18001d440  mov     rdx, rsi
0x18001d443  lea     rcx, [rbp+4Fh+var_60]
0x18001d447  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001d44c  nop
0x18001d44d  mov     r8, r14
0x18001d450  mov     rdx, rax
0x18001d453  lea     rcx, [rbp+4Fh+var_80]
0x18001d457  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001d45c  mov     r8, rax
0x18001d45f  lea     rdx, [rbp+4Fh+var_A8]
0x18001d463  lea     rcx, [r13+28h]
0x18001d467  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001d46c  mov     rbx, [rax]
0x18001d46f  lea     rcx, [rbp+4Fh+var_80]
0x18001d473  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d478  nop
0x18001d479  lea     rcx, [rbp+4Fh+var_60]
0x18001d47d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d482  cmp     rbx, [r13+28h]
0x18001d486  jz      loc_18001D5DD
0x18001d48c  mov     rdi, [rbx+40h]
0x18001d490  test    rdi, rdi
0x18001d493  jz      loc_18001D5DD
0x18001d499  lea     rax, WPP_witness_GLOBAL_Control
0x18001d4a0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d4a7  cmp     rcx, rax
0x18001d4aa  jz      short loc_18001D4E9
0x18001d4ac  test    byte ptr [rcx+1Ch], 1
0x18001d4b0  jz      short loc_18001D4E9
0x18001d4b2  cmp     byte ptr [rcx+19h], 3
0x18001d4b6  jb      short loc_18001D4E9
0x18001d4b8  cmp     qword ptr [r14+18h], 7
0x18001d4bd  jbe     short loc_18001D4C4
0x18001d4bf  mov     rax, [r14]
0x18001d4c2  jmp     short loc_18001D4C7
0x18001d4c4  mov     rax, r14
0x18001d4c7  cmp     qword ptr [rsi+18h], 7
0x18001d4cc  jbe     short loc_18001D4D3
0x18001d4ce  mov     r9, [rsi]
0x18001d4d1  jmp     short loc_18001D4D6
0x18001d4d3  mov     r9, rsi
0x18001d4d6  mov     edx, 22h ; '"'
0x18001d4db  mov     [rsp+0E0h+var_C0], rax
0x18001d4e0  mov     rcx, [rcx+10h]
0x18001d4e4  call    WPP_SF_SS
0x18001d4e9  test    r12d, r12d
0x18001d4ec  jz      short loc_18001D4F4
0x18001d4ee  lea     rcx, [r13+18h]
0x18001d4f2  jmp     short loc_18001D4FD
0x18001d4f4  test    r15d, r15d
0x18001d4f7  jz      short loc_18001D505
0x18001d4f9  lea     rcx, [r13+28h]
0x18001d4fd  mov     rdx, rbx
0x18001d500  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x18001d505  mov     rcx, rdi; this
0x18001d508  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x18001d50d  test    eax, eax
0x18001d50f  jnz     loc_18001D634
0x18001d515  test    r12d, r12d
0x18001d518  jz      short loc_18001D57D
0x18001d51a  cmp     qword ptr [rsi+18h], 7
0x18001d51f  jbe     short loc_18001D526
0x18001d521  mov     rdx, [rsi]
0x18001d524  jmp     short loc_18001D529
0x18001d526  mov     rdx, rsi
0x18001d529  lea     rcx, [rbp+4Fh+var_80]
0x18001d52d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d532  lea     r8, [rbp+4Fh+var_80]
0x18001d536  lea     rdx, [rbp+4Fh+var_60]
0x18001d53a  lea     rcx, [r13+8]
0x18001d53e  call    ??$_Eqrange@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x18001d543  mov     r10, [rax]
0x18001d546  mov     r9, [rax+8]
0x18001d54a  mov     rax, r10
0x18001d54d  mov     [rbp+4Fh+var_A8], rax
0x18001d551  cmp     rax, r9
0x18001d554  jz      short loc_18001D565
0x18001d556  lea     rcx, [rbp+4Fh+var_A8]
0x18001d55a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x18001d55f  mov     rax, [rbp+4Fh+var_A8]
0x18001d563  jmp     short loc_18001D551
0x18001d565  mov     r8, r9
0x18001d568  mov     rdx, r10
0x18001d56b  lea     rcx, [r13+8]
0x18001d56f  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x18001d574  lea     rcx, [rbp+4Fh+var_80]
0x18001d578  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d57d  mov     rcx, [r13+50h]; lpCriticalSection
0x18001d581  call    cs:__imp_LeaveCriticalSection
0x18001d588  nop     dword ptr [rax+rax+00h]
0x18001d58d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d594  lea     rax, WPP_witness_GLOBAL_Control
0x18001d59b  cmp     rcx, rax
0x18001d59e  jz      short loc_18001D5D0
0x18001d5a0  test    byte ptr [rcx+1Ch], 1
0x18001d5a4  jz      short loc_18001D5D0
0x18001d5a6  cmp     byte ptr [rcx+19h], 3
0x18001d5aa  jb      short loc_18001D5D0
0x18001d5ac  cmp     qword ptr [rsi+18h], 7
0x18001d5b1  jbe     short loc_18001D5B8
0x18001d5b3  mov     r9, [rsi]
0x18001d5b6  jmp     short loc_18001D5BB
0x18001d5b8  mov     r9, rsi
0x18001d5bb  mov     edx, 23h ; '#'
0x18001d5c0  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18001d5c7  mov     rcx, [rcx+10h]
0x18001d5cb  call    WPP_SF_S
0x18001d5d0  mov     rcx, rdi; this
0x18001d5d3  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x18001d5d8  mov     ebx, [rbp+4Fh+var_B0]
0x18001d5db  jmp     short loc_18001D648
0x18001d5dd  lea     rax, WPP_witness_GLOBAL_Control
0x18001d5e4  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d5eb  cmp     rcx, rax
0x18001d5ee  jz      short loc_18001D62D
0x18001d5f0  test    byte ptr [rcx+1Ch], 1
0x18001d5f4  jz      short loc_18001D62D
0x18001d5f6  cmp     byte ptr [rcx+19h], 1
0x18001d5fa  jb      short loc_18001D62D
0x18001d5fc  cmp     qword ptr [r14+18h], 7
0x18001d601  jbe     short loc_18001D608
0x18001d603  mov     rax, [r14]
0x18001d606  jmp     short loc_18001D60B
0x18001d608  mov     rax, r14
0x18001d60b  cmp     qword ptr [rsi+18h], 7
0x18001d610  jbe     short loc_18001D617
0x18001d612  mov     r9, [rsi]
0x18001d615  jmp     short loc_18001D61A
0x18001d617  mov     r9, rsi
0x18001d61a  mov     edx, 21h ; '!'
0x18001d61f  mov     [rsp+0E0h+var_C0], rax
0x18001d624  mov     rcx, [rcx+10h]
0x18001d628  call    WPP_SF_SS
0x18001d62d  mov     ebx, 57h ; 'W'
0x18001d632  jmp     short loc_18001D637
0x18001d634  mov     ebx, [rbp+4Fh+var_B0]
0x18001d637  mov     rcx, [r13+50h]; lpCriticalSection
0x18001d63b  call    cs:__imp_LeaveCriticalSection
0x18001d642  nop     dword ptr [rax+rax+00h]
0x18001d647  nop
0x18001d648  mov     rcx, rsi
0x18001d64b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d650  nop
0x18001d651  mov     rcx, r14
0x18001d654  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d659  nop
0x18001d65a  mov     rcx, [rbp+4Fh+var_A0]
0x18001d65e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d663  mov     eax, ebx
0x18001d665  mov     rcx, [rbp+4Fh+var_40]
0x18001d669  xor     rcx, rsp; StackCookie
0x18001d66c  call    __security_check_cookie
0x18001d671  mov     rbx, [rsp+0E0h+arg_0]
0x18001d679  add     rsp, 0B0h
0x18001d680  pop     r15
0x18001d682  pop     r14
0x18001d684  pop     r13
0x18001d686  pop     r12
0x18001d688  pop     rdi
0x18001d689  pop     rsi
0x18001d68a  pop     rbp
0x18001d68b  retn
```
