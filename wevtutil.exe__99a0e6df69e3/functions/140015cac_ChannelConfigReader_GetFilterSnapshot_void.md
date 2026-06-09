# ChannelConfigReader::GetFilterSnapshot(void)

- ea: `0x140015cac`
- end: `0x1400161f5`
- name: `?GetFilterSnapshot@ChannelConfigReader@@QEBA?AV?$optional@UQueryNode@@@utl@@XZ`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400073ec`

## callees

- `0x140003700`
- `0x1400039a0`
- `0x140004ae0`
- `0x140005600`
- `0x140005620`
- `0x140006db0`
- `0x140007fd0`
- `0x14000d6e8`
- `0x140015898`
- `0x140015cac`
- `0x14001634c`
- `0x1400193f0`
- `0x14001b5b4`
- `0x140022510`
- `0x140022cec`
- `0x14002aa9c`
- `0x14002c738`
- `0x14002f384`
- `0x14002f6c8`
- `0x14002ff54`
- `0x14002ff84`
- `0x140030034`
- `0x1400300ac`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016133`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016133`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BYTE *__fastcall ChannelConfigReader::GetFilterSnapshot(__int64 a1, _BYTE *a2)
{
  unsigned int StringValueNoThrow; // eax
  const char *v5; // r8
  unsigned int v6; // ebx
  const char *v7; // r8
  void *v8; // rbx
  HKEY *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r8
  DWORD v13; // edx
  __int64 v14; // r15
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // r14
  __int64 v17; // r12
  __int64 v18; // rbx
  QueryNode *Node; // rax
  const char *v20; // r8
  DWORD v21; // edx
  __int64 v22; // r15
  unsigned __int64 v23; // rsi
  unsigned __int64 v24; // r14
  __int64 v25; // r12
  __int64 v26; // rbx
  QueryNode *v27; // rax
  char v28; // al
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h]
  _QWORD pExceptionObject[3]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+5Ch] [rbp-A4h]
  char v35; // [rsp+64h] [rbp-9Ch]
  _QWORD v36[7]; // [rsp+80h] [rbp-80h] BYREF
  char v37; // [rsp+B8h] [rbp-48h]
  void *v38[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v39; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v40[11]; // [rsp+E8h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+150h] [rbp+50h] BYREF
  __int64 v42; // [rsp+160h] [rbp+60h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+68h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
  StringValueNoThrow = RegReadStringValueNoThrow(*(HKEY *)a1, 0, L"FilterId", (__int64)v38);
  v6 = StringValueNoThrow;
  if ( StringValueNoThrow )
  {
    if ( StringValueNoThrow != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
          StringValueNoThrow);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v6, v5, 480);
      throw (EvtException *)pExceptionObject;
    }
    goto LABEL_61;
  }
  v30 = *(_QWORD *)(a1 + 32);
  v31 = (*(_QWORD *)(a1 + 40) - v30) >> 1;
  if ( IsSecurityChannel(&v30) )
  {
LABEL_61:
    memset_0(a2, 0, 0x40u);
    *a2 = 0;
    a2[56] = 0;
    if ( v38[0] != &v39 )
      operator delete(v38[0]);
    return a2;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v40,
                           L"\\Filters\\")
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v40,
                           v38[0],
                           ((char *)v38[1] - (char *)v38[0]) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v7, 493);
    throw (EvtException *)pExceptionObject;
  }
  hKey = 0;
  v8 = *(void **)(a1 + 24);
  v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v10 = OpenRegKey(*(HKEY *)(a1 + 8), v40[0], 0x20019u, v9, v8);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v10);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v33 = v11;
    v34 = -1;
    v35 = 0;
    throw (EvtException *)pExceptionObject;
  }
  memset_0(v36, 0, 0x40u);
  LOBYTE(v36[0]) = 0;
  v37 = 0;
  pcbData = 0;
  v42 = 0;
  if ( !(unsigned int)RegReadByteArrayValueNoThrow(hKey, &ValueName, L"Selectors", &pcbData, (__int64)&v42) )
  {
    v13 = pcbData >> 1;
    if ( !(pcbData >> 1) || (v14 = v42, *(_WORD *)(v42 + 2LL * (v13 - 1))) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v12, 512);
      throw (EvtException *)pExceptionObject;
    }
    v15 = 0;
    v16 = v13;
    while ( v15 < v16 )
    {
      v17 = v14 + 2 * v15;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      v15 += v18 + 1;
      if ( !v37 )
      {
        Node = QueryNode::QueryNode((QueryNode *)pExceptionObject);
        utl::_OptionalData2<QueryNode>::_AssignVal<QueryNode>(v36, Node);
        QueryNode::~QueryNode((QueryNode *)pExceptionObject);
      }
      v30 = v17;
      v31 = v18;
      QueryNode::AddSelector(v36, &v30);
    }
  }
  if ( !(unsigned int)RegReadByteArrayValueNoThrow(hKey, &ValueName, L"Suppressors", &pcbData, (__int64)&v42) )
  {
    v21 = pcbData >> 1;
    if ( !(pcbData >> 1) || (v22 = v42, *(_WORD *)(v42 + 2LL * (v21 - 1))) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v20, 536);
      throw (EvtException *)pExceptionObject;
    }
    v23 = 0;
    v24 = v21;
    while ( v23 < v24 )
    {
      v25 = v22 + 2 * v23;
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)(v25 + 2 * v26) );
      v23 += v26 + 1;
      if ( !v37 )
      {
        v27 = QueryNode::QueryNode((QueryNode *)pExceptionObject);
        utl::_OptionalData2<QueryNode>::_AssignVal<QueryNode>(v36, v27);
        QueryNode::~QueryNode((QueryNode *)pExceptionObject);
      }
      v30 = v25;
      v31 = v26;
      QueryNode::AddSuppressor(v36, &v30);
    }
  }
  if ( v36[4] == v36[3]
    && v36[1] - v36[0] == 32
    && (unsigned __int8)utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36[0], L"*") )
  {
    v28 = v37;
    if ( v37 )
    {
      QueryNode::~QueryNode((QueryNode *)v36);
      v28 = 0;
      v37 = 0;
    }
  }
  else
  {
    v28 = v37;
  }
  *a2 = 0;
  a2[56] = 0;
  if ( v28 )
  {
    QueryNode::QueryNode(a2, v36);
    a2[56] = 1;
  }
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v42);
  utl::_OptionalData1<QueryNode,0>::~_OptionalData1<QueryNode,0>(v36);
  if ( hKey )
    RegCloseKey(hKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
  return a2;
}

```

## disassembly

```asm
0x140015cac  mov     [rsp-8+arg_8], rbx
0x140015cb1  push    rbp
0x140015cb2  push    rsi
0x140015cb3  push    rdi
0x140015cb4  push    r12
0x140015cb6  push    r13
0x140015cb8  push    r14
0x140015cba  push    r15
0x140015cbc  lea     rbp, [rsp-10h]
0x140015cc1  sub     rsp, 110h
0x140015cc8  mov     rdi, rdx
0x140015ccb  mov     rsi, rcx
0x140015cce  xor     r13d, r13d
0x140015cd1  lea     rcx, [rbp+40h+var_78]
0x140015cd5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140015cda  nop
0x140015cdb  lea     r9, [rbp+40h+var_78]
0x140015cdf  lea     r8, aFilterid; "FilterId"
0x140015ce6  xor     edx, edx
0x140015ce8  mov     rcx, [rsi]; hKey
0x140015ceb  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140015cf0  mov     ebx, eax
0x140015cf2  test    eax, eax
0x140015cf4  jz      short loc_140015D5B
0x140015cf6  cmp     eax, 2
0x140015cf9  jz      loc_1400161B0
0x140015cff  lea     rcx, WPP_GLOBAL_Control
0x140015d06  mov     r10, cs:WPP_GLOBAL_Control
0x140015d0d  cmp     r10, rcx
0x140015d10  jz      short loc_140015D37
0x140015d12  test    byte ptr [r10+1Ch], 4
0x140015d17  jz      short loc_140015D37
0x140015d19  cmp     byte ptr [r10+19h], 2
0x140015d1e  jb      short loc_140015D37
0x140015d20  lea     edx, [r13+23h]
0x140015d24  mov     r9d, eax
0x140015d27  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140015d2e  mov     rcx, [r10+10h]
0x140015d32  call    WPP_SF_d
0x140015d37  mov     r9d, 1E0h; int
0x140015d3d  mov     edx, ebx; unsigned int
0x140015d3f  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140015d44  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140015d49  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015d50  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x140015d55  call    _CxxThrowException_0
0x140015d5b  mov     rax, [rsi+20h]
0x140015d5f  mov     [rsp+140h+var_110], rax
0x140015d64  mov     rcx, [rsi+28h]
0x140015d68  sub     rcx, rax
0x140015d6b  sar     rcx, 1
0x140015d6e  mov     [rsp+140h+var_108], rcx
0x140015d73  lea     rcx, [rsp+140h+var_110]
0x140015d78  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015d7d  test    al, al
0x140015d7f  jnz     loc_1400161B0
0x140015d85  lea     rcx, [rbp+40h+var_58]
0x140015d89  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140015d8e  nop
0x140015d8f  lea     rdx, aFilters; "\\Filters\\"
0x140015d96  lea     rcx, [rbp+40h+var_58]
0x140015d9a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x140015d9f  test    al, al
0x140015da1  jz      loc_140016152
0x140015da7  mov     r8, [rbp+40h+var_70]
0x140015dab  mov     rdx, [rbp+40h+var_78]
0x140015daf  sub     r8, rdx
0x140015db2  sar     r8, 1
0x140015db5  lea     rcx, [rbp+40h+var_58]
0x140015db9  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140015dbe  test    al, al
0x140015dc0  jz      loc_140016152
0x140015dc6  mov     [rbp+40h+hKey], r13
0x140015dca  mov     rbx, [rsi+18h]
0x140015dce  lea     rcx, [rbp+40h+hKey]
0x140015dd2  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140015dd7  mov     [rsp+140h+var_120], rbx; void *
0x140015ddc  mov     r9, rax; HKEY *
0x140015ddf  mov     r8d, 20019h; unsigned int
0x140015de5  mov     rdx, [rbp+40h+var_58]; wchar_t *
0x140015de9  mov     rcx, [rsi+8]; HKEY
0x140015ded  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140015df2  mov     ebx, eax
0x140015df4  test    eax, eax
0x140015df6  jz      short loc_140015E6B
0x140015df8  lea     rcx, WPP_GLOBAL_Control
0x140015dff  mov     r10, cs:WPP_GLOBAL_Control
0x140015e06  cmp     r10, rcx
0x140015e09  jz      short loc_140015E31
0x140015e0b  test    byte ptr [r10+1Ch], 4
0x140015e10  jz      short loc_140015E31
0x140015e12  cmp     byte ptr [r10+19h], 2
0x140015e17  jb      short loc_140015E31
0x140015e19  mov     edx, 25h ; '%'
0x140015e1e  mov     r9d, eax
0x140015e21  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140015e28  mov     rcx, [r10+10h]
0x140015e2c  call    WPP_SF_d
0x140015e31  lea     rax, word_14003838A
0x140015e38  mov     [rsp+140h+pExceptionObject], rax
0x140015e3d  mov     [rsp+140h+var_F8], r13
0x140015e42  mov     [rsp+140h+var_F0], r13
0x140015e47  mov     [rsp+140h+var_E8], ebx
0x140015e4b  mov     [rsp+140h+var_E4], 0FFFFFFFFFFFFFFFFh
0x140015e54  mov     [rsp+140h+var_DC], r13b
0x140015e59  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015e60  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x140015e65  call    _CxxThrowException_0
0x140015e6b  xor     edx, edx; Val
0x140015e6d  lea     r8d, [rdx+40h]; Size
0x140015e71  lea     rcx, [rbp+40h+var_C0]; void *
0x140015e75  call    memset_0
0x140015e7a  mov     byte ptr [rbp+40h+var_C0], r13b
0x140015e7e  mov     [rbp+40h+var_88], r13b
0x140015e82  mov     [rbp+40h+pcbData], r13d
0x140015e86  mov     [rbp+40h+arg_10], r13
0x140015e8a  lea     rax, [rbp+40h+arg_10]
0x140015e8e  mov     [rsp+140h+var_120], rax; __int64
0x140015e93  lea     r9, [rbp+40h+pcbData]; pcbData
0x140015e97  lea     r8, aSelectors; "Selectors"
0x140015e9e  lea     rdx, ValueName; lpSubKey
0x140015ea5  mov     rcx, [rbp+40h+hKey]; hkey
0x140015ea9  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x140015eae  test    eax, eax
0x140015eb0  jnz     loc_140015F38
0x140015eb6  mov     edx, [rbp+40h+pcbData]
0x140015eb9  shr     edx, 1
0x140015ebb  jz      loc_14001603C
0x140015ec1  mov     r15, [rbp+40h+arg_10]
0x140015ec5  lea     eax, [rdx-1]
0x140015ec8  cmp     [r15+rax*2], r13w
0x140015ecd  jnz     loc_14001603C
0x140015ed3  mov     rsi, r13
0x140015ed6  mov     r14d, edx
0x140015ed9  test    edx, edx
0x140015edb  jz      short loc_140015F38
0x140015edd  lea     r12, [r15+rsi*2]
0x140015ee1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140015ee5  inc     rbx
0x140015ee8  cmp     [r12+rbx*2], r13w
0x140015eed  jnz     short loc_140015EE5
0x140015eef  inc     rsi
0x140015ef2  add     rsi, rbx
0x140015ef5  cmp     [rbp+40h+var_88], r13b
0x140015ef9  jnz     short loc_140015F1B
0x140015efb  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140015f00  call    ??0QueryNode@@QEAA@XZ; QueryNode::QueryNode(void)
0x140015f05  mov     rdx, rax
0x140015f08  lea     rcx, [rbp+40h+var_C0]
0x140015f0c  call    ??$_AssignVal@UQueryNode@@@?$_OptionalData2@UQueryNode@@@utl@@QEAAX$$QEAUQueryNode@@@Z; utl::_OptionalData2<QueryNode>::_AssignVal<QueryNode>(QueryNode &&)
0x140015f11  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140015f16  call    ??1QueryNode@@QEAA@XZ; QueryNode::~QueryNode(void)
0x140015f1b  mov     [rsp+140h+var_110], r12
0x140015f20  mov     [rsp+140h+var_108], rbx
0x140015f25  lea     rdx, [rsp+140h+var_110]
0x140015f2a  lea     rcx, [rbp+40h+var_C0]
0x140015f2e  call    ?AddSelector@QueryNode@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; QueryNode::AddSelector(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015f33  cmp     rsi, r14
0x140015f36  jb      short loc_140015EDD
0x140015f38  lea     rax, [rbp+40h+arg_10]
0x140015f3c  mov     [rsp+140h+var_120], rax; __int64
0x140015f41  lea     r9, [rbp+40h+pcbData]; pcbData
0x140015f45  lea     r8, aSuppressors; "Suppressors"
0x140015f4c  lea     rdx, ValueName; lpSubKey
0x140015f53  mov     rcx, [rbp+40h+hKey]; hkey
0x140015f57  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x140015f5c  test    eax, eax
0x140015f5e  jnz     loc_140015FE6
0x140015f64  mov     edx, [rbp+40h+pcbData]
0x140015f67  shr     edx, 1
0x140015f69  jz      loc_14001609A
0x140015f6f  mov     r15, [rbp+40h+arg_10]
0x140015f73  lea     eax, [rdx-1]
0x140015f76  cmp     [r15+rax*2], r13w
0x140015f7b  jnz     loc_14001609A
0x140015f81  mov     rsi, r13
0x140015f84  mov     r14d, edx
0x140015f87  test    edx, edx
0x140015f89  jz      short loc_140015FE6
0x140015f8b  lea     r12, [r15+rsi*2]
0x140015f8f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140015f93  inc     rbx
0x140015f96  cmp     [r12+rbx*2], r13w
0x140015f9b  jnz     short loc_140015F93
0x140015f9d  inc     rsi
0x140015fa0  add     rsi, rbx
0x140015fa3  cmp     [rbp+40h+var_88], r13b
0x140015fa7  jnz     short loc_140015FC9
0x140015fa9  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140015fae  call    ??0QueryNode@@QEAA@XZ; QueryNode::QueryNode(void)
0x140015fb3  mov     rdx, rax
0x140015fb6  lea     rcx, [rbp+40h+var_C0]
0x140015fba  call    ??$_AssignVal@UQueryNode@@@?$_OptionalData2@UQueryNode@@@utl@@QEAAX$$QEAUQueryNode@@@Z; utl::_OptionalData2<QueryNode>::_AssignVal<QueryNode>(QueryNode &&)
0x140015fbf  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140015fc4  call    ??1QueryNode@@QEAA@XZ; QueryNode::~QueryNode(void)
0x140015fc9  mov     [rsp+140h+var_110], r12
0x140015fce  mov     [rsp+140h+var_108], rbx
0x140015fd3  lea     rdx, [rsp+140h+var_110]
0x140015fd8  lea     rcx, [rbp+40h+var_C0]
0x140015fdc  call    ?AddSuppressor@QueryNode@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; QueryNode::AddSuppressor(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015fe1  cmp     rsi, r14
0x140015fe4  jb      short loc_140015F8B
0x140015fe6  mov     rax, [rbp+40h+var_A0]
0x140015fea  cmp     rax, [rbp+40h+var_A8]
0x140015fee  jnz     loc_1400160F8
0x140015ff4  mov     rax, [rbp+40h+var_B8]
0x140015ff8  mov     rcx, [rbp+40h+var_C0]
0x140015ffc  sub     rax, rcx
0x140015fff  cmp     rax, 20h ; ' '
0x140016003  jnz     loc_1400160F8
0x140016009  lea     rdx, asc_14003879C; "*"
0x140016010  call    ??$?8_WU?$char_traits@_W@utl@@V?$allocator@_W@1@@utl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@PEB_W@Z; utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *)
0x140016015  test    al, al
0x140016017  jz      loc_1400160F8
0x14001601d  mov     al, [rbp+40h+var_88]
0x140016020  test    al, al
0x140016022  jz      loc_1400160FB
0x140016028  lea     rcx, [rbp+40h+var_C0]; this
0x14001602c  call    ??1QueryNode@@QEAA@XZ; QueryNode::~QueryNode(void)
0x140016031  mov     al, r13b
0x140016034  mov     [rbp+40h+var_88], al
0x140016037  jmp     loc_1400160FB
0x14001603c  lea     rcx, WPP_GLOBAL_Control
0x140016043  mov     ebx, 0Dh
0x140016048  mov     rax, cs:WPP_GLOBAL_Control
0x14001604f  cmp     rax, rcx
0x140016052  jz      short loc_140016076
0x140016054  test    byte ptr [rax+1Ch], 4
0x140016058  jz      short loc_140016076
0x14001605a  cmp     byte ptr [rax+19h], 2
0x14001605e  jb      short loc_140016076
0x140016060  lea     edx, [rbx+19h]
0x140016063  mov     r9d, ebx
0x140016066  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x14001606d  mov     rcx, [rax+10h]
0x140016071  call    WPP_SF_d
0x140016076  mov     r9d, 200h; int
0x14001607c  mov     edx, ebx; unsigned int
0x14001607e  lea     rcx, [rsp+140h+pExceptionObject]; this
0x140016083  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140016088  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001608f  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x140016094  call    _CxxThrowException_0
0x14001609a  lea     rcx, WPP_GLOBAL_Control
0x1400160a1  mov     ebx, 0Dh
0x1400160a6  mov     rax, cs:WPP_GLOBAL_Control
0x1400160ad  cmp     rax, rcx
0x1400160b0  jz      short loc_1400160D4
0x1400160b2  test    byte ptr [rax+1Ch], 4
0x1400160b6  jz      short loc_1400160D4
0x1400160b8  cmp     byte ptr [rax+19h], 2
0x1400160bc  jb      short loc_1400160D4
0x1400160be  lea     edx, [rbx+1Ah]
0x1400160c1  mov     r9d, ebx
0x1400160c4  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x1400160cb  mov     rcx, [rax+10h]
0x1400160cf  call    WPP_SF_d
0x1400160d4  mov     r9d, 218h; int
0x1400160da  mov     edx, ebx; unsigned int
0x1400160dc  lea     rcx, [rsp+140h+pExceptionObject]; this
0x1400160e1  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400160e6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400160ed  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x1400160f2  call    _CxxThrowException_0
0x1400160f8  mov     al, [rbp+40h+var_88]
0x1400160fb  mov     [rdi], r13b
0x1400160fe  mov     [rdi+38h], r13b
0x140016102  test    al, al
0x140016104  jz      short loc_140016116
0x140016106  lea     rdx, [rbp+40h+var_C0]
0x14001610a  mov     rcx, rdi
0x14001610d  call    ??0QueryNode@@QEAA@$$QEAU0@@Z; QueryNode::QueryNode(QueryNode &&)
0x140016112  mov     byte ptr [rdi+38h], 1
0x140016116  lea     rcx, [rbp+40h+arg_10]
0x14001611a  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x14001611f  nop
0x140016120  lea     rcx, [rbp+40h+var_C0]
0x140016124  call    ??1?$_OptionalData1@UQueryNode@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<QueryNode,0>::~_OptionalData1<QueryNode,0>(void)
0x140016129  nop
0x14001612a  mov     rcx, [rbp+40h+hKey]; hKey
0x14001612e  test    rcx, rcx
0x140016131  jz      short loc_14001613A
0x140016133  call    cs:__imp_RegCloseKey
0x140016139  nop
0x14001613a  lea     rcx, [rbp+40h+var_58]
0x14001613e  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140016143  nop
0x140016144  lea     rcx, [rbp+40h+var_78]
0x140016148  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001614d  jmp     loc_1400161D7
0x140016152  lea     rcx, WPP_GLOBAL_Control
0x140016159  mov     ebx, 0Eh
0x14001615e  mov     rax, cs:WPP_GLOBAL_Control
0x140016165  cmp     rax, rcx
0x140016168  jz      short loc_14001618C
0x14001616a  test    byte ptr [rax+1Ch], 4
0x14001616e  jz      short loc_14001618C
0x140016170  cmp     byte ptr [rax+19h], 2
0x140016174  jb      short loc_14001618C
0x140016176  lea     edx, [rbx+16h]
  ... truncated ...
```
