# CProtocolHandler::HandleClusterConnect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_GUID *,ulong)

- ea: `0x18001c120`
- end: `0x18001c62a`
- name: `?HandleClusterConnect@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAU_GUID@@K@Z`
- size: `1290`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *, __int64 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fed0`

## callees

- `0x18001c0e0`
- `0x18001c120`
- `0x18001c630`
- `0x18001c8c4`
- `0x18001c920`
- `0x18001c9dc`
- `0x18001cabc`
- `0x18001cbf4`
- `0x18001cf24`
- `0x18001d0f4`
- `0x18001d940`
- `0x18001e420`
- `0x18002055c`
- `0x180022b7c`
- `0x180030898`
- `0x180030bc4`
- `0x180031b00`
- `0x180032134`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c5df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c5df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c17f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c17f`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::HandleClusterConnect(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 *a4,
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
  __int64 v39[2]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v40; // [rsp+80h] [rbp-59h]
  _QWORD *v41; // [rsp+88h] [rbp-51h]
  __int64 *v42; // [rsp+90h] [rbp-49h]
  __int64 *v43; // [rsp+98h] [rbp-41h]
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
    v39[0] = (__int64)operator new(0x1E8u);
    v31 = (CClusterConnection *)CClusterConnection::CClusterConnection(
                                  v39[0],
                                  (__int64)a2,
                                  (__int64)a3,
                                  (__int64)a4,
                                  (__int64)v8 + 96,
                                  (_OWORD *)v40,
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
    CClusterConnection::Connect(v17, a4, (_QWORD *)v40);
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
0x18001c120  mov     [rsp-8+arg_0], rbx
0x18001c125  push    rbp
0x18001c126  push    rsi
0x18001c127  push    rdi
0x18001c128  push    r12
0x18001c12a  push    r13
0x18001c12c  push    r14
0x18001c12e  push    r15
0x18001c130  lea     rbp, [rsp-17h]
0x18001c135  sub     rsp, 0F0h
0x18001c13c  mov     rax, cs:__security_cookie
0x18001c143  xor     rax, rsp
0x18001c146  mov     [rbp+47h+var_40], rax
0x18001c14a  mov     rax, r9
0x18001c14d  mov     [rbp+47h+var_B8], rax
0x18001c151  mov     rsi, r8
0x18001c154  mov     rdi, rdx
0x18001c157  mov     [rbp+47h+var_98], rdx
0x18001c15b  mov     [rbp+47h+var_90], r8
0x18001c15f  mov     [rbp+47h+var_88], rax
0x18001c163  mov     rax, [rbp+47h+arg_20]
0x18001c167  mov     [rbp+47h+var_A0], rax
0x18001c16b  mov     r12d, dword ptr [rbp+47h+arg_28]
0x18001c16f  mov     r15, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18001c176  xor     ebx, ebx
0x18001c178  mov     [rbp+47h+var_C0], ebx
0x18001c17b  mov     rcx, [r15+50h]; lpCriticalSection
0x18001c17f  call    cs:__imp_EnterCriticalSection
0x18001c185  cmp     [r15+80h], ebx
0x18001c18c  jz      loc_18001C5DB
0x18001c192  mov     r13d, r12d
0x18001c195  and     r13d, 1
0x18001c199  jz      short loc_18001C1B4
0x18001c19b  mov     r8, rdi
0x18001c19e  lea     rdx, [rbp+47h+var_B0]
0x18001c1a2  lea     rcx, [r15+8]
0x18001c1a6  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001c1ab  mov     r14, [rax]
0x18001c1ae  cmp     r14, [r15+8]
0x18001c1b2  jmp     short loc_18001C204
0x18001c1b4  test    r12b, 2
0x18001c1b8  jz      loc_18001C59F
0x18001c1be  mov     rdx, rdi
0x18001c1c1  lea     rcx, [rbp+47h+var_60]
0x18001c1c5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001c1ca  nop
0x18001c1cb  mov     r8, rsi
0x18001c1ce  mov     rdx, rax
0x18001c1d1  lea     rcx, [rbp+47h+var_80]
0x18001c1d5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001c1da  mov     r8, rax
0x18001c1dd  lea     rdx, [rbp+47h+var_B0]
0x18001c1e1  lea     rcx, [r15+28h]
0x18001c1e5  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001c1ea  mov     r14, [rax]
0x18001c1ed  lea     rcx, [rbp+47h+var_80]
0x18001c1f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c1f6  nop
0x18001c1f7  lea     rcx, [rbp+47h+var_60]
0x18001c1fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c200  cmp     r14, [r15+28h]
0x18001c204  jz      loc_18001C3CA
0x18001c20a  mov     r14, [r14+40h]
0x18001c20e  test    r14, r14
0x18001c211  jz      loc_18001C3CA
0x18001c217  mov     [rbp+47h+var_C0], 0
0x18001c21e  test    r13d, r13d
0x18001c221  jz      loc_18001C37A
0x18001c227  lea     r12, [r15+18h]
0x18001c22b  mov     rdx, rdi
0x18001c22e  lea     rcx, [rbp+47h+var_80]
0x18001c232  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001c237  nop
0x18001c238  mov     r8, rsi
0x18001c23b  mov     rdx, rax
0x18001c23e  lea     rcx, [rbp+47h+var_60]
0x18001c242  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001c247  mov     r8, rax
0x18001c24a  lea     rdx, [rbp+47h+var_B0]
0x18001c24e  mov     rcx, r12
0x18001c251  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001c256  mov     rbx, [rax]
0x18001c259  lea     rcx, [rbp+47h+var_60]
0x18001c25d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c262  nop
0x18001c263  lea     rcx, [rbp+47h+var_80]
0x18001c267  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c26c  cmp     rbx, [r12]
0x18001c270  jnz     loc_18001C319
0x18001c276  lea     rax, WPP_witness_GLOBAL_Control
0x18001c27d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001c284  cmp     rcx, rax
0x18001c287  jz      short loc_18001C2C6
0x18001c289  test    byte ptr [rcx+1Ch], 1
0x18001c28d  jz      short loc_18001C2C6
0x18001c28f  cmp     byte ptr [rcx+19h], 3
0x18001c293  jb      short loc_18001C2C6
0x18001c295  cmp     qword ptr [rsi+18h], 7
0x18001c29a  jbe     short loc_18001C2A1
0x18001c29c  mov     rax, [rsi]
0x18001c29f  jmp     short loc_18001C2A4
0x18001c2a1  mov     rax, rsi
0x18001c2a4  cmp     qword ptr [rdi+18h], 7
0x18001c2a9  jbe     short loc_18001C2B0
0x18001c2ab  mov     r9, [rdi]
0x18001c2ae  jmp     short loc_18001C2B3
0x18001c2b0  mov     r9, rdi
0x18001c2b3  mov     edx, 1Eh
0x18001c2b8  mov     [rsp+120h+var_100], rax
0x18001c2bd  mov     rcx, [rcx+10h]
0x18001c2c1  call    WPP_SF_SS
0x18001c2c6  mov     rdx, rdi
0x18001c2c9  lea     rcx, [rbp+47h+var_80]
0x18001c2cd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001c2d2  nop
0x18001c2d3  mov     r8, rsi
0x18001c2d6  mov     rdx, rax
0x18001c2d9  lea     rcx, [rbp+47h+var_60]
0x18001c2dd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001c2e2  nop
0x18001c2e3  mov     r8, rax
0x18001c2e6  lea     rdx, [rbp+47h+var_B0]
0x18001c2ea  mov     rcx, r12
0x18001c2ed  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001c2f2  mov     rcx, [rax]
0x18001c2f5  mov     [rcx+40h], r14
0x18001c2f9  lea     rcx, [rbp+47h+var_60]
0x18001c2fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c302  nop
0x18001c303  lea     rcx, [rbp+47h+var_80]
0x18001c307  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c30c  mov     rcx, r14; this
0x18001c30f  call    ?AddRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::AddRegisterReference(void)
0x18001c314  jmp     loc_18001C567
0x18001c319  lea     rax, WPP_witness_GLOBAL_Control
0x18001c320  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001c327  cmp     rcx, rax
0x18001c32a  jz      loc_18001C567
0x18001c330  test    byte ptr [rcx+1Ch], 1
0x18001c334  jz      loc_18001C567
0x18001c33a  cmp     byte ptr [rcx+19h], 3
0x18001c33e  jb      loc_18001C567
0x18001c344  cmp     qword ptr [rsi+18h], 7
0x18001c349  jbe     short loc_18001C350
0x18001c34b  mov     rax, [rsi]
0x18001c34e  jmp     short loc_18001C353
0x18001c350  mov     rax, rsi
0x18001c353  cmp     qword ptr [rdi+18h], 7
0x18001c358  jbe     short loc_18001C35F
0x18001c35a  mov     r9, [rdi]
0x18001c35d  jmp     short loc_18001C362
0x18001c35f  mov     r9, rdi
0x18001c362  mov     edx, 1Fh
0x18001c367  mov     [rsp+120h+var_100], rax
0x18001c36c  mov     rcx, [rcx+10h]
0x18001c370  call    WPP_SF_SS
0x18001c375  jmp     loc_18001C567
0x18001c37a  lea     rax, WPP_witness_GLOBAL_Control
0x18001c381  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001c388  cmp     rcx, rax
0x18001c38b  jz      loc_18001C567
0x18001c391  test    byte ptr [rcx+1Ch], 1
0x18001c395  jz      loc_18001C567
0x18001c39b  cmp     byte ptr [rcx+19h], 3
0x18001c39f  jb      loc_18001C567
0x18001c3a5  cmp     qword ptr [rsi+18h], 7
0x18001c3aa  jbe     short loc_18001C3B1
0x18001c3ac  mov     rax, [rsi]
0x18001c3af  jmp     short loc_18001C3B4
0x18001c3b1  mov     rax, rsi
0x18001c3b4  cmp     qword ptr [rdi+18h], 7
0x18001c3b9  jbe     short loc_18001C3C0
0x18001c3bb  mov     r9, [rdi]
0x18001c3be  jmp     short loc_18001C3C3
0x18001c3c0  mov     r9, rdi
0x18001c3c3  mov     edx, 20h ; ' '
0x18001c3c8  jmp     short loc_18001C367
0x18001c3ca  lea     rax, WPP_witness_GLOBAL_Control
0x18001c3d1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001c3d8  cmp     rcx, rax
0x18001c3db  jz      short loc_18001C41A
0x18001c3dd  test    byte ptr [rcx+1Ch], 1
0x18001c3e1  jz      short loc_18001C41A
0x18001c3e3  cmp     byte ptr [rcx+19h], 3
0x18001c3e7  jb      short loc_18001C41A
0x18001c3e9  cmp     qword ptr [rsi+18h], 7
0x18001c3ee  jbe     short loc_18001C3F5
0x18001c3f0  mov     rax, [rsi]
0x18001c3f3  jmp     short loc_18001C3F8
0x18001c3f5  mov     rax, rsi
0x18001c3f8  cmp     qword ptr [rdi+18h], 7
0x18001c3fd  jbe     short loc_18001C404
0x18001c3ff  mov     r9, [rdi]
0x18001c402  jmp     short loc_18001C407
0x18001c404  mov     r9, rdi
0x18001c407  mov     dword ptr [rsp+120h+var_F8], r12d
0x18001c40c  mov     [rsp+120h+var_100], rax
0x18001c411  mov     rcx, [rcx+10h]
0x18001c415  call    WPP_SF_SSd
0x18001c41a  mov     ecx, 1E8h; Size
0x18001c41f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c424  mov     [rbp+47h+var_B0], rax
0x18001c428  lea     rdx, [r15+60h]
0x18001c42c  mov     rcx, [r15+40h]
0x18001c430  mov     [rsp+120h+var_D0], rcx; __int64
0x18001c435  mov     ecx, [r15+4]
0x18001c439  mov     [rsp+120h+var_D8], ecx; int
0x18001c43d  mov     [rsp+120h+var_E0], r15; __int64
0x18001c442  mov     dword ptr [rsp+120h+var_E8], r12d; char
0x18001c447  mov     ecx, [r15]
0x18001c44a  mov     [rsp+120h+var_F0], ecx; int
0x18001c44e  mov     rcx, [rbp+47h+var_A0]
0x18001c452  mov     [rsp+120h+var_F8], rcx; __int64
0x18001c457  mov     [rsp+120h+var_100], rdx; __int64
0x18001c45c  mov     r9, [rbp+47h+var_B8]
0x18001c460  mov     r8, rsi
0x18001c463  mov     rdx, rdi
0x18001c466  mov     rcx, rax; char
0x18001c469  call    ??0CClusterConnection@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEBU_GUID@@KKPEAVCProtocolHandler@@KPEAX@Z; CClusterConnection::CClusterConnection(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,_GUID const *,ulong,ulong,CProtocolHandler *,ulong,void *)
0x18001c46e  mov     r14, rax
0x18001c471  test    rax, rax
0x18001c474  jz      loc_18001C5D8
0x18001c47a  mov     rdx, [r15+58h]; void *
0x18001c47e  mov     rcx, rax; this
0x18001c481  call    ?Initialize@CClusterConnection@@QEAAKPEAX@Z; CClusterConnection::Initialize(void *)
0x18001c486  mov     ebx, eax
0x18001c488  test    eax, eax
0x18001c48a  jz      short loc_18001C4A4
0x18001c48c  mov     rcx, [r14]
0x18001c48f  mov     rax, [rcx]
0x18001c492  mov     edx, 1
0x18001c497  mov     rcx, r14
0x18001c49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c49f  jmp     loc_18001C5DB
0x18001c4a4  mov     [rbp+47h+var_C0], 1
0x18001c4ab  test    r13d, r13d
0x18001c4ae  jz      short loc_18001C507
0x18001c4b0  lea     rcx, [r15+8]
0x18001c4b4  mov     r8, rdi
0x18001c4b7  lea     rdx, [rbp+47h+var_B0]
0x18001c4bb  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18001c4c0  mov     rcx, [rax]
0x18001c4c3  mov     [rcx+40h], r14
0x18001c4c7  mov     rdx, rdi
0x18001c4ca  lea     rcx, [rbp+47h+var_80]
0x18001c4ce  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001c4d3  nop
0x18001c4d4  mov     r8, rsi
0x18001c4d7  mov     rdx, rax
0x18001c4da  lea     rcx, [rbp+47h+var_60]
0x18001c4de  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001c4e3  nop
0x18001c4e4  mov     r8, rax
0x18001c4e7  lea     rdx, [rbp+47h+var_B0]
0x18001c4eb  lea     rcx, [r15+18h]
0x18001c4ef  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001c4f4  mov     rcx, [rax]
0x18001c4f7  mov     [rcx+40h], r14
0x18001c4fb  lea     rcx, [rbp+47h+var_60]
0x18001c4ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c504  nop
0x18001c505  jmp     short loc_18001C54B
0x18001c507  test    r12b, 2
0x18001c50b  jz      short loc_18001C554
0x18001c50d  mov     rdx, rdi
0x18001c510  lea     rcx, [rbp+47h+var_80]
0x18001c514  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001c519  nop
0x18001c51a  mov     r8, rsi
0x18001c51d  mov     rdx, rax
0x18001c520  lea     rcx, [rbp+47h+var_60]
0x18001c524  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001c529  nop
0x18001c52a  mov     r8, rax
0x18001c52d  lea     rdx, [rbp+47h+var_B0]
0x18001c531  lea     rcx, [r15+28h]
0x18001c535  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18001c53a  mov     rcx, [rax]
0x18001c53d  mov     [rcx+40h], r14
0x18001c541  lea     rcx, [rbp+47h+var_60]
0x18001c545  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c54a  nop
0x18001c54b  lea     rcx, [rbp+47h+var_80]
0x18001c54f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c554  mov     rcx, r14; this
0x18001c557  call    ?AddRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::AddRegisterReference(void)
0x18001c55c  mov     rax, [r15+40h]
0x18001c560  mov     [r14+198h], rax
0x18001c567  lock inc dword ptr [r14+8]
0x18001c56c  mov     rcx, [r15+50h]; lpCriticalSection
0x18001c570  call    cs:__imp_LeaveCriticalSection
0x18001c576  mov     rcx, r14; this
0x18001c579  cmp     [rbp+47h+var_C0], 0
0x18001c57d  jz      short loc_18001C586
0x18001c57f  call    ?BindToFileServerForGetInterface@CClusterConnection@@AEAAXXZ; CClusterConnection::BindToFileServerForGetInterface(void)
0x18001c584  jmp     short loc_18001C593
0x18001c586  mov     r8, [rbp+47h+var_A0]
0x18001c58a  mov     rdx, [rbp+47h+var_B8]
0x18001c58e  call    ?Connect@CClusterConnection@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_GUID@@@Z; CClusterConnection::Connect(std::wstring const &,_GUID const *)
0x18001c593  mov     rcx, r14; this
  ... truncated ...
```
