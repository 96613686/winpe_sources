# ClusApi::ClusterHelper::DeployNode(std::vector<_NodeInfo,std::allocator<_NodeInfo>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_ClusterSecretInfo const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ClusterManagementType::Enum,std::vector<_IPAddressInfo,std::allocator<_IPAddressInfo>> const &,bool,ulong)

- ea: `0x18002d3e0`
- end: `0x18002d6c0`
- name: `?DeployNode@ClusterHelper@ClusApi@@UEAAJAEBV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBU_ClusterSecretInfo@@11111W4Enum@ClusterManagementType@@AEBV?$vector@U_IPAddressInfo@@V?$allocator@U_IPAddressInfo@@@std@@@4@_NK@Z`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002ae0`
- `0x180003514`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000ca34`
- `0x18000ca58`
- `0x18000d6dc`
- `0x18000e044`
- `0x180010ca4`
- `0x180011f44`
- `0x180013110`
- `0x180013150`
- `0x180014530`
- `0x18001465c`
- `0x1800163dc`
- `0x18002acc8`
- `0x18002b050`
- `0x18002b9dc`
- `0x18002bc80`
- `0x18002d3e0`
- `0x180033368`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18002d522`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18002d522`
- `CLUSAPI!CCHlpConfigureNode` at `0x18002d60b`
- `CLUSAPI!CCHlpConfigureNode` at `0x18002d60b`

## string_xrefs

- `0x18002d650`: `{0} Error in configuring node`

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
  __int64 v26; // rax
  int *v27; // rbx
  int v28; // eax
  signed int v29; // edi
  struct cxl::TextWriter *v30; // rbx
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v33; // [rsp+80h] [rbp-80h] BYREF
  void *v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  _BYTE v40[24]; // [rsp+B8h] [rbp-48h] BYREF
  char v41[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v43[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v44[32]; // [rsp+130h] [rbp+30h] BYREF

  v39 = a6;
  v38 = a7;
  v37 = a8;
  v36 = a9;
  v16 = a11;
  v32 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy(&v32);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v33);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(v40);
  v17 = a2[1];
  for ( i = *a2; i != v17; i += 104 )
  {
    v19 = *(_DWORD *)(i + 64);
    *(_DWORD *)(*(_QWORD *)std::map<std::wstring,unsigned long>::_Try_emplace<std::wstring const &,>(&v32, Buffer, i)
              + 64LL) = v19;
  }
  cxl::Guid::Guid(Buffer, a4 + 32);
  v20 = (char *)v34;
  if ( (unsigned __int64)((_BYTE *)v34 - (_BYTE *)v33) > 0x10 )
  {
    v21 = (char *)(v33 + 1);
LABEL_10:
    v34 = v21;
    goto LABEL_11;
  }
  if ( (unsigned __int64)((_BYTE *)v34 - (_BYTE *)v33) < 0x10 )
  {
    if ( (unsigned __int64)(v35 - (_QWORD)v33) >= 0x10 )
    {
      v22 = 16 - ((_BYTE *)v34 - (_BYTE *)v33);
      memset_0(v34, 0, v22);
      v21 = &v20[v22];
      goto LABEL_10;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v33, 16);
  }
LABEL_11:
  *v33 = *(_OWORD *)Buffer;
  v23 = *v16;
  v24 = v16[1];
  while ( v23 != v24 )
  {
    _ultow(*(_DWORD *)(v23 + 32), Buffer, 10);
    std::wstring::wstring(v43);
    v25 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v41, v43);
    v26 = std::wstring::wstring(v44, Buffer);
    cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(v25, (wchar_t *)L"{0}/{1}", v23, v26);
    std::wstring::_Tidy_deallocate(v44);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(v40, v43);
    std::wstring::_Tidy_deallocate(v43);
    v23 += 40;
  }
  v27 = &a10;
  if ( a10 == 3 )
    v27 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
    Buffer,
    &v32);
  v28 = CCHlpConfigureNode(Buffer, a3, a4, &v33, a5, v39, v38, v37, v36, v27, v40, a12, a13);
  v29 = v28;
  if ( v28 > 0 )
    v29 = (unsigned __int16)v28 | 0x80070000;
  if ( v29 < 0 )
  {
    v30 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(Buffer, L"ClusApi::ClusterHelper::DeployNode");
    std::wstring::wstring(v43, Buffer);
    cxl::TextWriter::WriteLine<char,TraceFunction,>(v30, "{0} Error in configuring node");
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::_Tidy_deallocate(Buffer);
  }
  std::vector<std::wstring>::_Tidy(v40);
  std::vector<unsigned char>::_Tidy(&v33);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    &v32,
    &v32);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x18002d3e0  mov     [rsp-8+arg_0], rbx
0x18002d3e5  push    rbp
0x18002d3e6  push    rsi
0x18002d3e7  push    rdi
0x18002d3e8  push    r12
0x18002d3ea  push    r13
0x18002d3ec  push    r14
0x18002d3ee  push    r15
0x18002d3f0  lea     rbp, [rsp-60h]
0x18002d3f5  sub     rsp, 160h
0x18002d3fc  mov     rax, cs:__security_cookie
0x18002d403  xor     rax, rsp
0x18002d406  mov     [rbp+90h+var_40], rax
0x18002d40a  mov     r15, r9
0x18002d40d  mov     r12, r8
0x18002d410  mov     rbx, rdx
0x18002d413  mov     r13, [rbp+90h+arg_20]
0x18002d41a  mov     rax, [rbp+90h+arg_28]
0x18002d421  mov     [rbp+90h+var_E0], rax
0x18002d425  mov     rax, [rbp+90h+arg_30]
0x18002d42c  mov     [rbp+90h+var_E8], rax
0x18002d430  mov     rax, [rbp+90h+arg_38]
0x18002d437  mov     [rbp+90h+var_F0], rax
0x18002d43b  mov     rax, [rbp+90h+arg_40]
0x18002d442  mov     [rbp+90h+var_F8], rax
0x18002d446  mov     rsi, [rbp+90h+arg_50]
0x18002d44d  xorps   xmm0, xmm0
0x18002d450  movdqu  [rsp+190h+var_120], xmm0
0x18002d456  lea     rcx, [rsp+190h+var_120]
0x18002d45b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002d460  nop
0x18002d461  lea     rcx, [rbp+90h+var_110]
0x18002d465  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18002d46a  nop
0x18002d46b  lea     rcx, [rbp+90h+var_D8]
0x18002d46f  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18002d474  nop
0x18002d475  mov     r14, [rbx+8]
0x18002d479  mov     rdi, [rbx]
0x18002d47c  jmp     short loc_18002D49C
0x18002d47e  mov     ebx, [rdi+40h]
0x18002d481  mov     r8, rdi
0x18002d484  lea     rdx, [rbp+90h+Buffer]
0x18002d488  lea     rcx, [rsp+190h+var_120]
0x18002d48d  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,ulong>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002d492  mov     rcx, [rax]
0x18002d495  mov     [rcx+40h], ebx
0x18002d498  add     rdi, 68h ; 'h'
0x18002d49c  cmp     rdi, r14
0x18002d49f  jnz     short loc_18002D47E
0x18002d4a1  lea     rdx, [r15+20h]
0x18002d4a5  lea     rcx, [rbp+90h+Buffer]
0x18002d4a9  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x18002d4ae  mov     rdx, [rbp+90h+var_110]
0x18002d4b2  mov     rdi, [rbp+90h+var_108]
0x18002d4b6  mov     rcx, rdi
0x18002d4b9  sub     rcx, rdx
0x18002d4bc  mov     ebx, 10h
0x18002d4c1  cmp     rcx, rbx
0x18002d4c4  jbe     short loc_18002D4CC
0x18002d4c6  lea     rax, [rdx+10h]
0x18002d4ca  jmp     short loc_18002D4FC
0x18002d4cc  jnb     short loc_18002D500
0x18002d4ce  mov     rax, [rbp+90h+var_100]
0x18002d4d2  sub     rax, rdx
0x18002d4d5  cmp     rax, rbx
0x18002d4d8  jnb     short loc_18002D4E8
0x18002d4da  mov     rdx, rbx
0x18002d4dd  lea     rcx, [rbp+90h+var_110]
0x18002d4e1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002d4e6  jmp     short loc_18002D500
0x18002d4e8  sub     rbx, rcx
0x18002d4eb  mov     r8, rbx; Size
0x18002d4ee  xor     edx, edx; Val
0x18002d4f0  mov     rcx, rdi; void *
0x18002d4f3  call    memset_0
0x18002d4f8  lea     rax, [rbx+rdi]
0x18002d4fc  mov     [rbp+90h+var_108], rax
0x18002d500  movups  xmm0, xmmword ptr [rbp+90h+Buffer]
0x18002d504  mov     rax, [rbp+90h+var_110]
0x18002d508  movdqu  xmmword ptr [rax], xmm0
0x18002d50c  mov     rdi, [rsi]
0x18002d50f  mov     rsi, [rsi+8]
0x18002d513  jmp     short loc_18002D58B
0x18002d515  mov     r8d, 0Ah; Radix
0x18002d51b  lea     rdx, [rbp+90h+Buffer]; Buffer
0x18002d51f  mov     ecx, [rdi+20h]; Value
0x18002d522  call    cs:__imp__ultow
0x18002d528  lea     rcx, [rbp+90h+var_80]
0x18002d52c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d531  nop
0x18002d532  lea     rdx, [rbp+90h+var_80]
0x18002d536  lea     rcx, [rbp+90h+var_C0]
0x18002d53a  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18002d53f  mov     rbx, rax
0x18002d542  lea     rdx, [rbp+90h+Buffer]
0x18002d546  lea     rcx, [rbp+90h+var_60]
0x18002d54a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002d54f  nop
0x18002d550  mov     r9, rax
0x18002d553  mov     r8, rdi
0x18002d556  lea     rdx, a01; "{0}/{1}"
0x18002d55d  mov     rcx, rbx; struct cxl::TextWriter *
0x18002d560  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(wchar_t const *,std::wstring const &,std::wstring const &)
0x18002d565  nop
0x18002d566  lea     rcx, [rbp+90h+var_60]
0x18002d56a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d56f  nop
0x18002d570  lea     rdx, [rbp+90h+var_80]
0x18002d574  lea     rcx, [rbp+90h+var_D8]
0x18002d578  call    ??$_Emplace_one_at_back@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x18002d57d  nop
0x18002d57e  lea     rcx, [rbp+90h+var_80]
0x18002d582  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d587  add     rdi, 28h ; '('
0x18002d58b  cmp     rdi, rsi
0x18002d58e  jnz     short loc_18002D515
0x18002d590  lea     rbx, [rbp+90h+arg_48]
0x18002d597  xor     eax, eax
0x18002d599  cmp     [rbp+90h+arg_48], 3
0x18002d5a0  cmovz   rbx, rax
0x18002d5a4  lea     rdx, [rsp+190h+var_120]
0x18002d5a9  lea     rcx, [rbp+90h+Buffer]
0x18002d5ad  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &&)
0x18002d5b2  mov     eax, [rbp+90h+arg_60]
0x18002d5b8  mov     [rsp+190h+var_130], eax
0x18002d5bc  mov     al, [rbp+90h+arg_58]
0x18002d5c2  mov     [rsp+190h+var_138], al
0x18002d5c6  lea     rax, [rbp+90h+var_D8]
0x18002d5ca  mov     [rsp+190h+var_140], rax
0x18002d5cf  mov     [rsp+190h+var_148], rbx
0x18002d5d4  mov     rax, [rbp+90h+var_F8]
0x18002d5d8  mov     [rsp+190h+var_150], rax
0x18002d5dd  mov     rax, [rbp+90h+var_F0]
0x18002d5e1  mov     [rsp+190h+var_158], rax
0x18002d5e6  mov     rax, [rbp+90h+var_E8]
0x18002d5ea  mov     [rsp+190h+var_160], rax
0x18002d5ef  mov     rax, [rbp+90h+var_E0]
0x18002d5f3  mov     [rsp+190h+var_168], rax
0x18002d5f8  mov     [rsp+190h+var_170], r13
0x18002d5fd  lea     r9, [rbp+90h+var_110]
0x18002d601  mov     r8, r15
0x18002d604  mov     rdx, r12
0x18002d607  lea     rcx, [rbp+90h+Buffer]
0x18002d60b  call    cs:__imp_?CCHlpConfigureNode@@YAKV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1AEAV?$vector@EV?$allocator@E@std@@@2@11111PEAKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@_NK@Z; CCHlpConfigureNode(std::map<std::wstring,ulong>,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,ulong *,std::vector<std::wstring> &,bool,ulong)
0x18002d611  mov     edi, eax
0x18002d613  test    eax, eax
0x18002d615  jle     short loc_18002D620
0x18002d617  movzx   edi, ax
0x18002d61a  or      edi, 80070000h
0x18002d620  test    edi, edi
0x18002d622  jns     short loc_18002D674
0x18002d624  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002d629  lea     rbx, [rax+28h]
0x18002d62d  lea     rdx, aClusapiCluster_1; "ClusApi::ClusterHelper::DeployNode"
0x18002d634  lea     rcx, [rbp+90h+Buffer]
0x18002d638  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002d63d  nop
0x18002d63e  lea     rdx, [rbp+90h+Buffer]
0x18002d642  lea     rcx, [rbp+90h+var_80]
0x18002d646  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002d64b  nop
0x18002d64c  lea     r8, [rbp+90h+var_80]
0x18002d650  lea     rdx, a0ErrorInConfig; "{0} Error in configuring node"
0x18002d657  mov     rcx, rbx; struct cxl::TextWriter *
0x18002d65a  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x18002d65f  nop
0x18002d660  lea     rcx, [rbp+90h+var_80]
0x18002d664  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d669  nop
0x18002d66a  lea     rcx, [rbp+90h+Buffer]
0x18002d66e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d673  nop
0x18002d674  lea     rcx, [rbp+90h+var_D8]
0x18002d678  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002d67d  nop
0x18002d67e  lea     rcx, [rbp+90h+var_110]
0x18002d682  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002d687  nop
0x18002d688  lea     rdx, [rsp+190h+var_120]
0x18002d68d  lea     rcx, [rsp+190h+var_120]
0x18002d692  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &)
0x18002d697  mov     eax, edi
0x18002d699  mov     rcx, [rbp+90h+var_40]
0x18002d69d  xor     rcx, rsp; StackCookie
0x18002d6a0  call    __security_check_cookie
0x18002d6a5  mov     rbx, [rsp+190h+arg_0]
0x18002d6ad  add     rsp, 160h
0x18002d6b4  pop     r15
0x18002d6b6  pop     r14
0x18002d6b8  pop     r13
0x18002d6ba  pop     r12
0x18002d6bc  pop     rdi
0x18002d6bd  pop     rsi
0x18002d6be  pop     rbp
0x18002d6bf  retn
```
