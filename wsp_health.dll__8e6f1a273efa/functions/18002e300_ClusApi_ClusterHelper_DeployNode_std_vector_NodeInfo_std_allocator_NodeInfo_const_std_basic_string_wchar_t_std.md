# ClusApi::ClusterHelper::DeployNode(std::vector<_NodeInfo,std::allocator<_NodeInfo>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_ClusterSecretInfo const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ClusterManagementType::Enum,std::vector<_IPAddressInfo,std::allocator<_IPAddressInfo>> const &,bool,ulong)

- ea: `0x18002e300`
- end: `0x18002e5f1`
- name: `?DeployNode@ClusterHelper@ClusApi@@UEAAJAEBV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBU_ClusterSecretInfo@@11111W4Enum@ClusterManagementType@@AEBV?$vector@U_IPAddressInfo@@V?$allocator@U_IPAddressInfo@@@std@@@4@_NK@Z`
- size: `753`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002b50`
- `0x1800035b4`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000cde0`
- `0x18000ce04`
- `0x18000daf8`
- `0x18000e4b8`
- `0x180011184`
- `0x1800124b4`
- `0x1800137cc`
- `0x180013810`
- `0x180014cd4`
- `0x180014e00`
- `0x180016cfc`
- `0x18002ba88`
- `0x18002be18`
- `0x18002c844`
- `0x18002caf0`
- `0x18002e300`
- `0x180034508`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18002e442`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18002e442`
- `CLUSAPI!CCHlpConfigureNode` at `0x18002e535`
- `CLUSAPI!CCHlpConfigureNode` at `0x18002e535`

## string_xrefs

- `0x18002e580`: `{0} Error in configuring node`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ClusApi::ClusterHelper::DeployNode(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        __int64 *a11,
        char a12,
        int a13)
{
  __int64 *v16; // rsi
  __int64 v17; // r14
  __int64 i; // rdi
  int v19; // ebx
  char *v20; // rdi
  char *v21; // rax
  size_t v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rsi
  struct cxl::TextWriter *v25; // rbx
  int *v26; // rbx
  int v27; // eax
  signed int v28; // edi
  struct cxl::TextWriter *v29; // rbx
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v32; // [rsp+80h] [rbp-80h] BYREF
  void *v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  _BYTE v39[24]; // [rsp+B8h] [rbp-48h] BYREF
  char v40[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v42[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v43[32]; // [rsp+130h] [rbp+30h] BYREF

  v38 = a6;
  v37 = a7;
  v36 = a8;
  v35 = a9;
  v16 = a11;
  v31 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy(&v31);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v32);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(v39);
  v17 = a2[1];
  for ( i = *a2; i != v17; i += 104 )
  {
    v19 = *(_DWORD *)(i + 64);
    *(_DWORD *)(*(_QWORD *)std::map<std::wstring,unsigned long>::_Try_emplace<std::wstring const &,>(&v31, Buffer, i)
              + 64LL) = v19;
  }
  cxl::Guid::Guid(Buffer, a4 + 32);
  v20 = (char *)v33;
  if ( (unsigned __int64)((_BYTE *)v33 - (_BYTE *)v32) > 0x10 )
  {
    v21 = (char *)(v32 + 1);
LABEL_10:
    v33 = v21;
    goto LABEL_11;
  }
  if ( (unsigned __int64)((_BYTE *)v33 - (_BYTE *)v32) < 0x10 )
  {
    if ( (unsigned __int64)(v34 - (_QWORD)v32) >= 0x10 )
    {
      v22 = 16 - ((_BYTE *)v33 - (_BYTE *)v32);
      memset_0(v33, 0, v22);
      v21 = &v20[v22];
      goto LABEL_10;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v32, 16);
  }
LABEL_11:
  *v32 = *(_OWORD *)Buffer;
  v23 = *v16;
  v24 = v16[1];
  while ( v23 != v24 )
  {
    _ultow(*(_DWORD *)(v23 + 32), Buffer, 10);
    std::wstring::wstring(v42);
    v25 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v40, v42);
    std::wstring::wstring(v43, Buffer);
    cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(v25, (wchar_t *)L"{0}/{1}");
    std::wstring::_Tidy_deallocate(v43);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(v39, v42);
    std::wstring::_Tidy_deallocate(v42);
    v23 += 40;
  }
  v26 = &a10;
  if ( a10 == 3 )
    v26 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
    Buffer,
    &v31);
  v27 = CCHlpConfigureNode(Buffer, a3, a4, &v32, a5, v38, v37, v36, v35, v26, v39, a12, a13);
  v28 = v27;
  if ( v27 > 0 )
    v28 = (unsigned __int16)v27 | 0x80070000;
  if ( v28 < 0 )
  {
    v29 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(Buffer, L"ClusApi::ClusterHelper::DeployNode");
    std::wstring::wstring(v42, Buffer);
    cxl::TextWriter::WriteLine<char,TraceFunction,>(v29, "{0} Error in configuring node");
    std::wstring::_Tidy_deallocate(v42);
    std::wstring::_Tidy_deallocate(Buffer);
  }
  std::vector<std::wstring>::_Tidy(v39);
  std::vector<unsigned char>::_Tidy(&v32);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    &v31,
    &v31);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18002e300  mov     [rsp-8+arg_0], rbx
0x18002e305  push    rbp
0x18002e306  push    rsi
0x18002e307  push    rdi
0x18002e308  push    r12
0x18002e30a  push    r13
0x18002e30c  push    r14
0x18002e30e  push    r15
0x18002e310  lea     rbp, [rsp-60h]
0x18002e315  sub     rsp, 160h
0x18002e31c  mov     rax, cs:__security_cookie
0x18002e323  xor     rax, rsp
0x18002e326  mov     [rbp+90h+var_40], rax
0x18002e32a  mov     r15, r9
0x18002e32d  mov     r12, r8
0x18002e330  mov     rbx, rdx
0x18002e333  mov     r13, [rbp+90h+arg_20]
0x18002e33a  mov     rax, [rbp+90h+arg_28]
0x18002e341  mov     [rbp+90h+var_E0], rax
0x18002e345  mov     rax, [rbp+90h+arg_30]
0x18002e34c  mov     [rbp+90h+var_E8], rax
0x18002e350  mov     rax, [rbp+90h+arg_38]
0x18002e357  mov     [rbp+90h+var_F0], rax
0x18002e35b  mov     rax, [rbp+90h+arg_40]
0x18002e362  mov     [rbp+90h+var_F8], rax
0x18002e366  mov     rsi, [rbp+90h+arg_50]
0x18002e36d  xorps   xmm0, xmm0
0x18002e370  movdqu  [rsp+190h+var_120], xmm0
0x18002e376  lea     rcx, [rsp+190h+var_120]
0x18002e37b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002e380  nop
0x18002e381  lea     rcx, [rbp+90h+var_110]
0x18002e385  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18002e38a  nop
0x18002e38b  lea     rcx, [rbp+90h+var_D8]
0x18002e38f  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18002e394  nop
0x18002e395  mov     r14, [rbx+8]
0x18002e399  mov     rdi, [rbx]
0x18002e39c  jmp     short loc_18002E3BC
0x18002e39e  mov     ebx, [rdi+40h]
0x18002e3a1  mov     r8, rdi
0x18002e3a4  lea     rdx, [rbp+90h+Buffer]
0x18002e3a8  lea     rcx, [rsp+190h+var_120]
0x18002e3ad  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,ulong>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002e3b2  mov     rcx, [rax]
0x18002e3b5  mov     [rcx+40h], ebx
0x18002e3b8  add     rdi, 68h ; 'h'
0x18002e3bc  cmp     rdi, r14
0x18002e3bf  jnz     short loc_18002E39E
0x18002e3c1  lea     rdx, [r15+20h]
0x18002e3c5  lea     rcx, [rbp+90h+Buffer]
0x18002e3c9  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x18002e3ce  mov     rdx, [rbp+90h+var_110]
0x18002e3d2  mov     rdi, [rbp+90h+var_108]
0x18002e3d6  mov     rcx, rdi
0x18002e3d9  sub     rcx, rdx
0x18002e3dc  mov     ebx, 10h
0x18002e3e1  cmp     rcx, rbx
0x18002e3e4  jbe     short loc_18002E3EC
0x18002e3e6  lea     rax, [rdx+10h]
0x18002e3ea  jmp     short loc_18002E41C
0x18002e3ec  jnb     short loc_18002E420
0x18002e3ee  mov     rax, [rbp+90h+var_100]
0x18002e3f2  sub     rax, rdx
0x18002e3f5  cmp     rax, rbx
0x18002e3f8  jnb     short loc_18002E408
0x18002e3fa  mov     rdx, rbx
0x18002e3fd  lea     rcx, [rbp+90h+var_110]
0x18002e401  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002e406  jmp     short loc_18002E420
0x18002e408  sub     rbx, rcx
0x18002e40b  mov     r8, rbx; Size
0x18002e40e  xor     edx, edx; Val
0x18002e410  mov     rcx, rdi; void *
0x18002e413  call    memset_0
0x18002e418  lea     rax, [rbx+rdi]
0x18002e41c  mov     [rbp+90h+var_108], rax
0x18002e420  movups  xmm0, xmmword ptr [rbp+90h+Buffer]
0x18002e424  mov     rax, [rbp+90h+var_110]
0x18002e428  movdqu  xmmword ptr [rax], xmm0
0x18002e42c  mov     rdi, [rsi]
0x18002e42f  mov     rsi, [rsi+8]
0x18002e433  jmp     short loc_18002E4B1
0x18002e435  mov     r8d, 0Ah; Radix
0x18002e43b  lea     rdx, [rbp+90h+Buffer]; Buffer
0x18002e43f  mov     ecx, [rdi+20h]; Value
0x18002e442  call    cs:__imp__ultow
0x18002e449  nop     dword ptr [rax+rax+00h]
0x18002e44e  lea     rcx, [rbp+90h+var_80]
0x18002e452  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e457  nop
0x18002e458  lea     rdx, [rbp+90h+var_80]
0x18002e45c  lea     rcx, [rbp+90h+var_C0]
0x18002e460  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18002e465  mov     rbx, rax
0x18002e468  lea     rdx, [rbp+90h+Buffer]
0x18002e46c  lea     rcx, [rbp+90h+var_60]
0x18002e470  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002e475  nop
0x18002e476  mov     r9, rax
0x18002e479  mov     r8, rdi
0x18002e47c  lea     rdx, a01; "{0}/{1}"
0x18002e483  mov     rcx, rbx; struct cxl::TextWriter *
0x18002e486  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(wchar_t const *,std::wstring const &,std::wstring const &)
0x18002e48b  nop
0x18002e48c  lea     rcx, [rbp+90h+var_60]
0x18002e490  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e495  nop
0x18002e496  lea     rdx, [rbp+90h+var_80]
0x18002e49a  lea     rcx, [rbp+90h+var_D8]
0x18002e49e  call    ??$_Emplace_one_at_back@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x18002e4a3  nop
0x18002e4a4  lea     rcx, [rbp+90h+var_80]
0x18002e4a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e4ad  add     rdi, 28h ; '('
0x18002e4b1  cmp     rdi, rsi
0x18002e4b4  jnz     loc_18002E435
0x18002e4ba  lea     rbx, [rbp+90h+arg_48]
0x18002e4c1  xor     eax, eax
0x18002e4c3  cmp     [rbp+90h+arg_48], 3
0x18002e4ca  cmovz   rbx, rax
0x18002e4ce  lea     rdx, [rsp+190h+var_120]
0x18002e4d3  lea     rcx, [rbp+90h+Buffer]
0x18002e4d7  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &&)
0x18002e4dc  mov     eax, [rbp+90h+arg_60]
0x18002e4e2  mov     [rsp+190h+var_130], eax
0x18002e4e6  mov     al, [rbp+90h+arg_58]
0x18002e4ec  mov     [rsp+190h+var_138], al
0x18002e4f0  lea     rax, [rbp+90h+var_D8]
0x18002e4f4  mov     [rsp+190h+var_140], rax
0x18002e4f9  mov     [rsp+190h+var_148], rbx
0x18002e4fe  mov     rax, [rbp+90h+var_F8]
0x18002e502  mov     [rsp+190h+var_150], rax
0x18002e507  mov     rax, [rbp+90h+var_F0]
0x18002e50b  mov     [rsp+190h+var_158], rax
0x18002e510  mov     rax, [rbp+90h+var_E8]
0x18002e514  mov     [rsp+190h+var_160], rax
0x18002e519  mov     rax, [rbp+90h+var_E0]
0x18002e51d  mov     [rsp+190h+var_168], rax
0x18002e522  mov     [rsp+190h+var_170], r13
0x18002e527  lea     r9, [rbp+90h+var_110]
0x18002e52b  mov     r8, r15
0x18002e52e  mov     rdx, r12
0x18002e531  lea     rcx, [rbp+90h+Buffer]
0x18002e535  call    cs:__imp_?CCHlpConfigureNode@@YAKV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1AEAV?$vector@EV?$allocator@E@std@@@2@11111PEAKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@_NK@Z; CCHlpConfigureNode(std::map<std::wstring,ulong>,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,ulong *,std::vector<std::wstring> &,bool,ulong)
0x18002e53c  nop     dword ptr [rax+rax+00h]
0x18002e541  mov     edi, eax
0x18002e543  test    eax, eax
0x18002e545  jle     short loc_18002E550
0x18002e547  movzx   edi, ax
0x18002e54a  or      edi, 80070000h
0x18002e550  test    edi, edi
0x18002e552  jns     short loc_18002E5A4
0x18002e554  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002e559  lea     rbx, [rax+28h]
0x18002e55d  lea     rdx, aClusapiCluster_1; "ClusApi::ClusterHelper::DeployNode"
0x18002e564  lea     rcx, [rbp+90h+Buffer]
0x18002e568  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002e56d  nop
0x18002e56e  lea     rdx, [rbp+90h+Buffer]
0x18002e572  lea     rcx, [rbp+90h+var_80]
0x18002e576  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002e57b  nop
0x18002e57c  lea     r8, [rbp+90h+var_80]
0x18002e580  lea     rdx, a0ErrorInConfig; "{0} Error in configuring node"
0x18002e587  mov     rcx, rbx; struct cxl::TextWriter *
0x18002e58a  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x18002e58f  nop
0x18002e590  lea     rcx, [rbp+90h+var_80]
0x18002e594  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e599  nop
0x18002e59a  lea     rcx, [rbp+90h+Buffer]
0x18002e59e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e5a3  nop
0x18002e5a4  lea     rcx, [rbp+90h+var_D8]
0x18002e5a8  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002e5ad  nop
0x18002e5ae  lea     rcx, [rbp+90h+var_110]
0x18002e5b2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002e5b7  nop
0x18002e5b8  lea     rdx, [rsp+190h+var_120]
0x18002e5bd  lea     rcx, [rsp+190h+var_120]
0x18002e5c2  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &)
0x18002e5c7  mov     eax, edi
0x18002e5c9  mov     rcx, [rbp+90h+var_40]
0x18002e5cd  xor     rcx, rsp; StackCookie
0x18002e5d0  call    __security_check_cookie
0x18002e5d5  mov     rbx, [rsp+190h+arg_0]
0x18002e5dd  add     rsp, 160h
0x18002e5e4  pop     r15
0x18002e5e6  pop     r14
0x18002e5e8  pop     r13
0x18002e5ea  pop     r12
0x18002e5ec  pop     rdi
0x18002e5ed  pop     rsi
0x18002e5ee  pop     rbp
0x18002e5ef  retn
```
