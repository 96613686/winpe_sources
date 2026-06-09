# CProtocolHandler::HandleClusterConnect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_GUID *,ulong)

- ea: `0x18001d6d8`
- end: `0x18001dbf5`
- name: `?HandleClusterConnect@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAU_GUID@@K@Z`
- size: `1309`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032c40`

## callees

- `0x18001d694`
- `0x18001d6d8`
- `0x18001dbfc`
- `0x18001deac`
- `0x18001df08`
- `0x18001dfcc`
- `0x18001e0ac`
- `0x18001e1e4`
- `0x18001e540`
- `0x18001e720`
- `0x18001f050`
- `0x18001fbd0`
- `0x180021d0c`
- `0x180024550`
- `0x1800336ac`
- `0x1800339dc`
- `0x180034944`
- `0x180034ff8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dba3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dba3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d737`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CProtocolHandler::HandleClusterConnect(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  CProtocolHandler *v8; // r15
  unsigned int v9; // ebx
  __int64 *v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r14
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // rax
  CClusterConnection *v17; // r14
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r9
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // r9
  CClusterConnection *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  int v37; // [rsp+60h] [rbp-79h]
  char v39[16]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v40; // [rsp+80h] [rbp-59h]
  _QWORD *v41; // [rsp+88h] [rbp-51h]
  __int64 *v42; // [rsp+90h] [rbp-49h]
  __int64 v43; // [rsp+98h] [rbp-41h]
  _BYTE v44[32]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v45[32]; // [rsp+C0h] [rbp-19h] BYREF

  v41 = a2;
  v42 = a3;
  v43 = a4;
  v40 = a5;
  v8 = WitnessProtocolHandler;
  v9 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  if ( !*((_DWORD *)v8 + 32) )
    goto LABEL_70;
  if ( (a6 & 1) != 0 )
  {
    v10 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v8 + 8,
                       v39,
                       a2);
    v13 = *v10;
    v14 = *v10 == *((_QWORD *)v8 + 1);
  }
  else
  {
    if ( (a6 & 2) == 0 )
    {
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 28, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, a6);
      }
      goto LABEL_70;
    }
    v15 = std::operator+<unsigned short>(v45, a2);
    v16 = std::operator+<unsigned short>(v44, v15, a3);
    v13 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v8 + 40,
                       v39,
                       v16);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v45);
    v14 = v13 == *((_QWORD *)v8 + 5);
  }
  if ( v14 || (v17 = *(CClusterConnection **)(v13 + 64)) == 0 )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      if ( (unsigned __int64)a3[3] <= 7 )
        v29 = (__int64)a3;
      else
        v29 = *a3;
      if ( a2[3] <= 7u )
        LODWORD(v30) = (_DWORD)a2;
      else
        v30 = *a2;
      WPP_SF_SSd(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), v11, v12, v30, v29, a6);
    }
    *(_QWORD *)v39 = operator new(0x1E8u);
    v31 = (CClusterConnection *)CClusterConnection::CClusterConnection(
                                  v39[0],
                                  (__int64)v8 + 96,
                                  v40,
                                  *(_DWORD *)v8,
                                  a6,
                                  (__int64)v8,
                                  *((_DWORD *)v8 + 1),
                                  *((_QWORD *)v8 + 8));
    v17 = v31;
    if ( !v31 )
    {
      v9 = 0;
      goto LABEL_70;
    }
    v9 = CClusterConnection::Initialize(v31, *((void **)v8 + 11));
    if ( v9 )
    {
      (**(void (__fastcall ***)(CClusterConnection *, __int64))v17)(v17, 1);
LABEL_70:
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)v8 + 10));
      goto LABEL_71;
    }
    v37 = 1;
    if ( (a6 & 1) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring const &,>(
                               (char *)v8 + 8,
                               v39,
                               a2)
                + 64LL) = v17;
      v32 = std::operator+<unsigned short>(v44, a2);
      v33 = std::operator+<unsigned short>(v45, v32, a3);
      *(_QWORD *)(*(_QWORD *)std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(
                               (char *)v8 + 24,
                               v39,
                               v33)
                + 64LL) = v17;
      std::wstring::~wstring(v45);
    }
    else
    {
      if ( (a6 & 2) == 0 )
      {
LABEL_60:
        CClusterConnection::AddRegisterReference(v17);
        *((_QWORD *)v17 + 51) = *((_QWORD *)v8 + 8);
        goto LABEL_61;
      }
      v34 = std::operator+<unsigned short>(v44, a2);
      v35 = std::operator+<unsigned short>(v45, v34, a3);
      *(_QWORD *)(*(_QWORD *)std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(
                               (char *)v8 + 40,
                               v39,
                               v35)
                + 64LL) = v17;
      std::wstring::~wstring(v45);
    }
    std::wstring::~wstring(v44);
    goto LABEL_60;
  }
  v37 = 0;
  if ( (a6 & 1) != 0 )
  {
    v18 = std::operator+<unsigned short>(v44, a2);
    v19 = std::operator+<unsigned short>(v45, v18, a3);
    v20 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v8 + 24,
                       v39,
                       v19);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v44);
    if ( v20 == *((_QWORD *)v8 + 3) )
    {
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
      {
        if ( (unsigned __int64)a3[3] <= 7 )
          v21 = (__int64)a3;
        else
          v21 = *a3;
        if ( a2[3] <= 7u )
          LODWORD(v22) = (_DWORD)a2;
        else
          v22 = *a2;
        WPP_SF_SS(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 30, v12, v22, v21);
      }
      v23 = std::operator+<unsigned short>(v44, a2);
      v24 = std::operator+<unsigned short>(v45, v23, a3);
      *(_QWORD *)(*(_QWORD *)std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(
                               (char *)v8 + 24,
                               v39,
                               v24)
                + 64LL) = v17;
      std::wstring::~wstring(v45);
      std::wstring::~wstring(v44);
      CClusterConnection::AddRegisterReference(v17);
      goto LABEL_61;
    }
    v25 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      if ( (unsigned __int64)a3[3] <= 7 )
        v26 = (__int64)a3;
      else
        v26 = *a3;
      if ( a2[3] <= 7u )
        LODWORD(v27) = (_DWORD)a2;
      else
        v27 = *a2;
      v28 = 31;
LABEL_31:
      WPP_SF_SS(v25[2], v28, v12, v27, v26);
    }
  }
  else
  {
    v25 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      if ( (unsigned __int64)a3[3] <= 7 )
        v26 = (__int64)a3;
      else
        v26 = *a3;
      if ( a2[3] <= 7u )
        LODWORD(v27) = (_DWORD)a2;
      else
        v27 = *a2;
      v28 = 32;
      goto LABEL_31;
    }
  }
LABEL_61:
  _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)v8 + 10));
  if ( v37 )
    CClusterConnection::BindToFileServerForGetInterface(v17);
  else
    CClusterConnection::Connect(v17);
  RefCountObject::Release(v17);
  v9 = 0;
LABEL_71:
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  return v9;
}

```

## disassembly

```asm
0x18001d6d8  mov     [rsp-8+arg_0], rbx
0x18001d6dd  push    rbp
0x18001d6de  push    rsi
0x18001d6df  push    rdi
0x18001d6e0  push    r12
0x18001d6e2  push    r13
0x18001d6e4  push    r14
0x18001d6e6  push    r15
0x18001d6e8  lea     rbp, [rsp-17h]
0x18001d6ed  sub     rsp, 0F0h
0x18001d6f4  mov     rax, cs:__security_cookie
0x18001d6fb  xor     rax, rsp
0x18001d6fe  mov     [rbp+47h+var_40], rax
0x18001d702  mov     rax, r9
0x18001d705  mov     [rbp+47h+var_B8], rax
0x18001d709  mov     rsi, r8
0x18001d70c  mov     rdi, rdx
0x18001d70f  mov     [rbp+47h+var_98], rdx
0x18001d713  mov     [rbp+47h+var_90], r8
0x18001d717  mov     [rbp+47h+var_88], rax
0x18001d71b  mov     rax, [rbp+47h+arg_20]
0x18001d71f  mov     [rbp+47h+var_A0], rax
0x18001d723  mov     r12d, dword ptr [rbp+47h+arg_28]
0x18001d727  mov     r15, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18001d72e  xor     ebx, ebx
0x18001d730  mov     [rbp+47h+var_C0], ebx
0x18001d733  mov     rcx, [r15+50h]; lpCriticalSection
0x18001d737  call    cs:__imp_EnterCriticalSection
0x18001d73e  nop     dword ptr [rax+rax+00h]
0x18001d743  cmp     [r15+80h], ebx
0x18001d74a  jz      loc_18001DB9F
0x18001d750  mov     r13d, r12d
0x18001d753  and     r13d, 1
0x18001d757  jz      short loc_18001D772
0x18001d759  mov     r8, rdi
0x18001d75c  lea     rdx, [rbp+47h+var_B0]
0x18001d760  lea     rcx, [r15+8]
0x18001d764  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001d769  mov     r14, [rax]
0x18001d76c  cmp     r14, [r15+8]
0x18001d770  jmp     short loc_18001D7C2
0x18001d772  test    r12b, 2
0x18001d776  jz      loc_18001DB63
0x18001d77c  mov     rdx, rdi
0x18001d77f  lea     rcx, [rbp+47h+var_60]
0x18001d783  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001d788  nop
0x18001d789  mov     r8, rsi
0x18001d78c  mov     rdx, rax
0x18001d78f  lea     rcx, [rbp+47h+var_80]
0x18001d793  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001d798  mov     r8, rax
0x18001d79b  lea     rdx, [rbp+47h+var_B0]
0x18001d79f  lea     rcx, [r15+28h]
0x18001d7a3  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001d7a8  mov     r14, [rax]
0x18001d7ab  lea     rcx, [rbp+47h+var_80]
0x18001d7af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d7b4  nop
0x18001d7b5  lea     rcx, [rbp+47h+var_60]
0x18001d7b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d7be  cmp     r14, [r15+28h]
0x18001d7c2  jz      loc_18001D988
0x18001d7c8  mov     r14, [r14+40h]
0x18001d7cc  test    r14, r14
0x18001d7cf  jz      loc_18001D988
0x18001d7d5  mov     [rbp+47h+var_C0], 0
0x18001d7dc  test    r13d, r13d
0x18001d7df  jz      loc_18001D938
0x18001d7e5  lea     r12, [r15+18h]
0x18001d7e9  mov     rdx, rdi
0x18001d7ec  lea     rcx, [rbp+47h+var_80]
0x18001d7f0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001d7f5  nop
0x18001d7f6  mov     r8, rsi
0x18001d7f9  mov     rdx, rax
0x18001d7fc  lea     rcx, [rbp+47h+var_60]
0x18001d800  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001d805  mov     r8, rax
0x18001d808  lea     rdx, [rbp+47h+var_B0]
0x18001d80c  mov     rcx, r12
0x18001d80f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001d814  mov     rbx, [rax]
0x18001d817  lea     rcx, [rbp+47h+var_60]
0x18001d81b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d820  nop
0x18001d821  lea     rcx, [rbp+47h+var_80]
0x18001d825  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d82a  cmp     rbx, [r12]
0x18001d82e  jnz     loc_18001D8D7
0x18001d834  lea     rax, WPP_witness_GLOBAL_Control
0x18001d83b  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d842  cmp     rcx, rax
0x18001d845  jz      short loc_18001D884
0x18001d847  test    byte ptr [rcx+1Ch], 1
0x18001d84b  jz      short loc_18001D884
0x18001d84d  cmp     byte ptr [rcx+19h], 3
0x18001d851  jb      short loc_18001D884
0x18001d853  cmp     qword ptr [rsi+18h], 7
0x18001d858  jbe     short loc_18001D85F
0x18001d85a  mov     rax, [rsi]
0x18001d85d  jmp     short loc_18001D862
0x18001d85f  mov     rax, rsi
0x18001d862  cmp     qword ptr [rdi+18h], 7
0x18001d867  jbe     short loc_18001D86E
0x18001d869  mov     r9, [rdi]
0x18001d86c  jmp     short loc_18001D871
0x18001d86e  mov     r9, rdi
0x18001d871  mov     edx, 1Eh
0x18001d876  mov     [rsp+120h+var_100], rax
0x18001d87b  mov     rcx, [rcx+10h]
0x18001d87f  call    WPP_SF_SS
0x18001d884  mov     rdx, rdi
0x18001d887  lea     rcx, [rbp+47h+var_80]
0x18001d88b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001d890  nop
0x18001d891  mov     r8, rsi
0x18001d894  mov     rdx, rax
0x18001d897  lea     rcx, [rbp+47h+var_60]
0x18001d89b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001d8a0  nop
0x18001d8a1  mov     r8, rax
0x18001d8a4  lea     rdx, [rbp+47h+var_B0]
0x18001d8a8  mov     rcx, r12
0x18001d8ab  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001d8b0  mov     rcx, [rax]
0x18001d8b3  mov     [rcx+40h], r14
0x18001d8b7  lea     rcx, [rbp+47h+var_60]
0x18001d8bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d8c0  nop
0x18001d8c1  lea     rcx, [rbp+47h+var_80]
0x18001d8c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d8ca  mov     rcx, r14; this
0x18001d8cd  call    ?AddRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::AddRegisterReference(void)
0x18001d8d2  jmp     loc_18001DB25
0x18001d8d7  lea     rax, WPP_witness_GLOBAL_Control
0x18001d8de  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d8e5  cmp     rcx, rax
0x18001d8e8  jz      loc_18001DB25
0x18001d8ee  test    byte ptr [rcx+1Ch], 1
0x18001d8f2  jz      loc_18001DB25
0x18001d8f8  cmp     byte ptr [rcx+19h], 3
0x18001d8fc  jb      loc_18001DB25
0x18001d902  cmp     qword ptr [rsi+18h], 7
0x18001d907  jbe     short loc_18001D90E
0x18001d909  mov     rax, [rsi]
0x18001d90c  jmp     short loc_18001D911
0x18001d90e  mov     rax, rsi
0x18001d911  cmp     qword ptr [rdi+18h], 7
0x18001d916  jbe     short loc_18001D91D
0x18001d918  mov     r9, [rdi]
0x18001d91b  jmp     short loc_18001D920
0x18001d91d  mov     r9, rdi
0x18001d920  mov     edx, 1Fh
0x18001d925  mov     [rsp+120h+var_100], rax
0x18001d92a  mov     rcx, [rcx+10h]
0x18001d92e  call    WPP_SF_SS
0x18001d933  jmp     loc_18001DB25
0x18001d938  lea     rax, WPP_witness_GLOBAL_Control
0x18001d93f  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d946  cmp     rcx, rax
0x18001d949  jz      loc_18001DB25
0x18001d94f  test    byte ptr [rcx+1Ch], 1
0x18001d953  jz      loc_18001DB25
0x18001d959  cmp     byte ptr [rcx+19h], 3
0x18001d95d  jb      loc_18001DB25
0x18001d963  cmp     qword ptr [rsi+18h], 7
0x18001d968  jbe     short loc_18001D96F
0x18001d96a  mov     rax, [rsi]
0x18001d96d  jmp     short loc_18001D972
0x18001d96f  mov     rax, rsi
0x18001d972  cmp     qword ptr [rdi+18h], 7
0x18001d977  jbe     short loc_18001D97E
0x18001d979  mov     r9, [rdi]
0x18001d97c  jmp     short loc_18001D981
0x18001d97e  mov     r9, rdi
0x18001d981  mov     edx, 20h ; ' '
0x18001d986  jmp     short loc_18001D925
0x18001d988  lea     rax, WPP_witness_GLOBAL_Control
0x18001d98f  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001d996  cmp     rcx, rax
0x18001d999  jz      short loc_18001D9D8
0x18001d99b  test    byte ptr [rcx+1Ch], 1
0x18001d99f  jz      short loc_18001D9D8
0x18001d9a1  cmp     byte ptr [rcx+19h], 3
0x18001d9a5  jb      short loc_18001D9D8
0x18001d9a7  cmp     qword ptr [rsi+18h], 7
0x18001d9ac  jbe     short loc_18001D9B3
0x18001d9ae  mov     rax, [rsi]
0x18001d9b1  jmp     short loc_18001D9B6
0x18001d9b3  mov     rax, rsi
0x18001d9b6  cmp     qword ptr [rdi+18h], 7
0x18001d9bb  jbe     short loc_18001D9C2
0x18001d9bd  mov     r9, [rdi]
0x18001d9c0  jmp     short loc_18001D9C5
0x18001d9c2  mov     r9, rdi
0x18001d9c5  mov     dword ptr [rsp+120h+var_F8], r12d
0x18001d9ca  mov     [rsp+120h+var_100], rax
0x18001d9cf  mov     rcx, [rcx+10h]
0x18001d9d3  call    WPP_SF_SSd
0x18001d9d8  mov     ecx, 1E8h; Size
0x18001d9dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d9e2  mov     qword ptr [rbp+47h+var_B0], rax
0x18001d9e6  lea     rdx, [r15+60h]
0x18001d9ea  mov     rcx, [r15+40h]
0x18001d9ee  mov     [rsp+120h+var_D0], rcx; __int64
0x18001d9f3  mov     ecx, [r15+4]
0x18001d9f7  mov     [rsp+120h+var_D8], ecx; int
0x18001d9fb  mov     [rsp+120h+var_E0], r15; __int64
0x18001da00  mov     dword ptr [rsp+120h+var_E8], r12d; char
0x18001da05  mov     ecx, [r15]
0x18001da08  mov     [rsp+120h+var_F0], ecx; int
0x18001da0c  mov     rcx, [rbp+47h+var_A0]
0x18001da10  mov     [rsp+120h+var_F8], rcx; __int64
0x18001da15  mov     [rsp+120h+var_100], rdx; __int64
0x18001da1a  mov     r9, [rbp+47h+var_B8]
0x18001da1e  mov     r8, rsi
0x18001da21  mov     rdx, rdi
0x18001da24  mov     rcx, rax; char
0x18001da27  call    ??0CClusterConnection@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEBU_GUID@@KKPEAVCProtocolHandler@@KPEAX@Z; CClusterConnection::CClusterConnection(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,_GUID const *,ulong,ulong,CProtocolHandler *,ulong,void *)
0x18001da2c  mov     r14, rax
0x18001da2f  test    rax, rax
0x18001da32  jz      loc_18001DB9C
0x18001da38  mov     rdx, [r15+58h]; void *
0x18001da3c  mov     rcx, rax; this
0x18001da3f  call    ?Initialize@CClusterConnection@@QEAAKPEAX@Z; CClusterConnection::Initialize(void *)
0x18001da44  mov     ebx, eax
0x18001da46  test    eax, eax
0x18001da48  jz      short loc_18001DA62
0x18001da4a  mov     rcx, [r14]
0x18001da4d  mov     rax, [rcx]
0x18001da50  mov     edx, 1
0x18001da55  mov     rcx, r14
0x18001da58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da5d  jmp     loc_18001DB9F
0x18001da62  mov     [rbp+47h+var_C0], 1
0x18001da69  test    r13d, r13d
0x18001da6c  jz      short loc_18001DAC5
0x18001da6e  lea     rcx, [r15+8]
0x18001da72  mov     r8, rdi
0x18001da75  lea     rdx, [rbp+47h+var_B0]
0x18001da79  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18001da7e  mov     rcx, [rax]
0x18001da81  mov     [rcx+40h], r14
0x18001da85  mov     rdx, rdi
0x18001da88  lea     rcx, [rbp+47h+var_80]
0x18001da8c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001da91  nop
0x18001da92  mov     r8, rsi
0x18001da95  mov     rdx, rax
0x18001da98  lea     rcx, [rbp+47h+var_60]
0x18001da9c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001daa1  nop
0x18001daa2  mov     r8, rax
0x18001daa5  lea     rdx, [rbp+47h+var_B0]
0x18001daa9  lea     rcx, [r15+18h]
0x18001daad  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001dab2  mov     rcx, [rax]
0x18001dab5  mov     [rcx+40h], r14
0x18001dab9  lea     rcx, [rbp+47h+var_60]
0x18001dabd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dac2  nop
0x18001dac3  jmp     short loc_18001DB09
0x18001dac5  test    r12b, 2
0x18001dac9  jz      short loc_18001DB12
0x18001dacb  mov     rdx, rdi
0x18001dace  lea     rcx, [rbp+47h+var_80]
0x18001dad2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001dad7  nop
0x18001dad8  mov     r8, rsi
0x18001dadb  mov     rdx, rax
0x18001dade  lea     rcx, [rbp+47h+var_60]
0x18001dae2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001dae7  nop
0x18001dae8  mov     r8, rax
0x18001daeb  lea     rdx, [rbp+47h+var_B0]
0x18001daef  lea     rcx, [r15+28h]
0x18001daf3  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001daf8  mov     rcx, [rax]
0x18001dafb  mov     [rcx+40h], r14
0x18001daff  lea     rcx, [rbp+47h+var_60]
0x18001db03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001db08  nop
0x18001db09  lea     rcx, [rbp+47h+var_80]
0x18001db0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001db12  mov     rcx, r14; this
0x18001db15  call    ?AddRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::AddRegisterReference(void)
0x18001db1a  mov     rax, [r15+40h]
0x18001db1e  mov     [r14+198h], rax
0x18001db25  lock inc dword ptr [r14+8]
0x18001db2a  mov     rcx, [r15+50h]; lpCriticalSection
0x18001db2e  call    cs:__imp_LeaveCriticalSection
0x18001db35  nop     dword ptr [rax+rax+00h]
0x18001db3a  mov     rcx, r14; this
0x18001db3d  cmp     [rbp+47h+var_C0], 0
0x18001db41  jz      short loc_18001DB4A
0x18001db43  call    ?BindToFileServerForGetInterface@CClusterConnection@@AEAAXXZ; CClusterConnection::BindToFileServerForGetInterface(void)
0x18001db48  jmp     short loc_18001DB57
0x18001db4a  mov     r8, [rbp+47h+var_A0]
0x18001db4e  mov     rdx, [rbp+47h+var_B8]
  ... truncated ...
```
