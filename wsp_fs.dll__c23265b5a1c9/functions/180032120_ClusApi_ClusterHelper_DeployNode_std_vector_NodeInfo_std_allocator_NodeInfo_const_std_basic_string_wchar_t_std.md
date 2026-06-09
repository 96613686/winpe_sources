# ClusApi::ClusterHelper::DeployNode(std::vector<_NodeInfo,std::allocator<_NodeInfo>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_ClusterSecretInfo const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ClusterManagementType::Enum,std::vector<_IPAddressInfo,std::allocator<_IPAddressInfo>> const &,bool,ulong)

- ea: `0x180032120`
- end: `0x18003242a`
- name: `?DeployNode@ClusterHelper@ClusApi@@UEAAJAEBV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBU_ClusterSecretInfo@@11111W4Enum@ClusterManagementType@@AEBV?$vector@U_IPAddressInfo@@V?$allocator@U_IPAddressInfo@@@std@@@4@_NK@Z`
- size: `778`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003528`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000d5b8`
- `0x18000d600`
- `0x18000d624`
- `0x18000eb18`
- `0x1800124ac`
- `0x18001382c`
- `0x180013e34`
- `0x180014bfc`
- `0x180014c40`
- `0x180016764`
- `0x180016890`
- `0x180019ea0`
- `0x18002f8c8`
- `0x18002fc58`
- `0x180030658`
- `0x180030904`
- `0x180032120`
- `0x180038348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180032265`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180032265`
- `CLUSAPI!CCHlpConfigureNode` at `0x18003236e`
- `CLUSAPI!CCHlpConfigureNode` at `0x18003236e`

## string_xrefs

- `0x1800323b9`: `{0} Error in configuring node`

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
  __int64 v26; // rcx
  int *v27; // rbx
  int v28; // eax
  signed int v29; // edi
  struct cxl::TextWriter *v30; // rbx
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v33; // [rsp+80h] [rbp-80h] BYREF
  void *v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  char v36[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  __int64 v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  char v43[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v45[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v46[32]; // [rsp+130h] [rbp+30h] BYREF

  v42 = a6;
  v41 = a7;
  v40 = a8;
  v39 = a9;
  v16 = a11;
  v32 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy(&v32);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v33);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(v36);
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
    std::wstring::wstring(v45);
    v25 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v43, v45);
    std::wstring::wstring(v46, Buffer);
    cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(v25, (wchar_t *)L"{0}/{1}");
    std::wstring::_Tidy_deallocate(v46);
    if ( v37 == v38 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v36, v37, v45);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring &>(
        v26,
        v37,
        v45);
      v37 += 32;
    }
    std::wstring::_Tidy_deallocate(v45);
    v23 += 40;
  }
  v27 = &a10;
  if ( a10 == 3 )
    v27 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
    Buffer,
    &v32);
  v28 = CCHlpConfigureNode(Buffer, a3, a4, &v33, a5, v42, v41, v40, v39, v27, v36, a12, a13);
  v29 = v28;
  if ( v28 > 0 )
    v29 = (unsigned __int16)v28 | 0x80070000;
  if ( v29 < 0 )
  {
    v30 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(Buffer, L"ClusApi::ClusterHelper::DeployNode");
    std::wstring::wstring(v45, Buffer);
    cxl::TextWriter::WriteLine<char,TraceFunction,>(v30, "{0} Error in configuring node");
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(Buffer);
  }
  std::vector<std::wstring>::_Tidy(v36);
  std::vector<unsigned char>::_Tidy(&v33);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    &v32,
    &v32);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180032120  mov     [rsp-8+arg_0], rbx
0x180032125  push    rbp
0x180032126  push    rsi
0x180032127  push    rdi
0x180032128  push    r12
0x18003212a  push    r13
0x18003212c  push    r14
0x18003212e  push    r15
0x180032130  lea     rbp, [rsp-60h]
0x180032135  sub     rsp, 160h
0x18003213c  mov     rax, cs:__security_cookie
0x180032143  xor     rax, rsp
0x180032146  mov     [rbp+90h+var_40], rax
0x18003214a  mov     r15, r9
0x18003214d  mov     r12, r8
0x180032150  mov     rbx, rdx
0x180032153  mov     r13, [rbp+90h+arg_20]
0x18003215a  mov     rax, [rbp+90h+arg_28]
0x180032161  mov     [rbp+90h+var_C8], rax
0x180032165  mov     rax, [rbp+90h+arg_30]
0x18003216c  mov     [rbp+90h+var_D0], rax
0x180032170  mov     rax, [rbp+90h+arg_38]
0x180032177  mov     [rbp+90h+var_D8], rax
0x18003217b  mov     rax, [rbp+90h+arg_40]
0x180032182  mov     [rbp+90h+var_E0], rax
0x180032186  mov     rsi, [rbp+90h+arg_50]
0x18003218d  xorps   xmm0, xmm0
0x180032190  movdqu  [rsp+190h+var_120], xmm0
0x180032196  lea     rcx, [rsp+190h+var_120]
0x18003219b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800321a0  nop
0x1800321a1  lea     rcx, [rbp+90h+var_110]
0x1800321a5  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x1800321aa  nop
0x1800321ab  lea     rcx, [rbp+90h+var_F8]
0x1800321af  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x1800321b4  nop
0x1800321b5  mov     r14, [rbx+8]
0x1800321b9  mov     rdi, [rbx]
0x1800321bc  jmp     short loc_1800321DC
0x1800321be  mov     ebx, [rdi+40h]
0x1800321c1  mov     r8, rdi
0x1800321c4  lea     rdx, [rbp+90h+Buffer]
0x1800321c8  lea     rcx, [rsp+190h+var_120]
0x1800321cd  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,ulong>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800321d2  mov     rcx, [rax]
0x1800321d5  mov     [rcx+40h], ebx
0x1800321d8  add     rdi, 68h ; 'h'
0x1800321dc  cmp     rdi, r14
0x1800321df  jnz     short loc_1800321BE
0x1800321e1  lea     rdx, [r15+20h]
0x1800321e5  lea     rcx, [rbp+90h+Buffer]
0x1800321e9  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x1800321ee  mov     rdx, [rbp+90h+var_110]
0x1800321f2  mov     rdi, [rbp+90h+var_108]
0x1800321f6  mov     rcx, rdi
0x1800321f9  sub     rcx, rdx
0x1800321fc  mov     ebx, 10h
0x180032201  cmp     rcx, rbx
0x180032204  jbe     short loc_18003220C
0x180032206  lea     rax, [rdx+10h]
0x18003220a  jmp     short loc_18003223C
0x18003220c  jnb     short loc_180032240
0x18003220e  mov     rax, [rbp+90h+var_100]
0x180032212  sub     rax, rdx
0x180032215  cmp     rax, rbx
0x180032218  jnb     short loc_180032228
0x18003221a  mov     rdx, rbx
0x18003221d  lea     rcx, [rbp+90h+var_110]
0x180032221  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180032226  jmp     short loc_180032240
0x180032228  sub     rbx, rcx
0x18003222b  mov     r8, rbx; Size
0x18003222e  xor     edx, edx; Val
0x180032230  mov     rcx, rdi; void *
0x180032233  call    memset_0
0x180032238  lea     rax, [rbx+rdi]
0x18003223c  mov     [rbp+90h+var_108], rax
0x180032240  movups  xmm0, xmmword ptr [rbp+90h+Buffer]
0x180032244  mov     rax, [rbp+90h+var_110]
0x180032248  movdqu  xmmword ptr [rax], xmm0
0x18003224c  mov     rdi, [rsi]
0x18003224f  mov     rsi, [rsi+8]
0x180032253  jmp     loc_1800322EA
0x180032258  mov     r8d, 0Ah; Radix
0x18003225e  lea     rdx, [rbp+90h+Buffer]; Buffer
0x180032262  mov     ecx, [rdi+20h]; Value
0x180032265  call    cs:__imp__ultow
0x18003226c  nop     dword ptr [rax+rax+00h]
0x180032271  lea     rcx, [rbp+90h+var_80]
0x180032275  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003227a  nop
0x18003227b  lea     rdx, [rbp+90h+var_80]
0x18003227f  lea     rcx, [rbp+90h+var_C0]
0x180032283  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180032288  mov     rbx, rax
0x18003228b  lea     rdx, [rbp+90h+Buffer]
0x18003228f  lea     rcx, [rbp+90h+var_60]
0x180032293  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180032298  nop
0x180032299  mov     r9, rax
0x18003229c  mov     r8, rdi
0x18003229f  lea     rdx, a01; "{0}/{1}"
0x1800322a6  mov     rcx, rbx; struct cxl::TextWriter *
0x1800322a9  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(wchar_t const *,std::wstring const &,std::wstring const &)
0x1800322ae  nop
0x1800322af  lea     rcx, [rbp+90h+var_60]
0x1800322b3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800322b8  nop
0x1800322b9  mov     rdx, [rbp+90h+var_F0]
0x1800322bd  lea     r8, [rbp+90h+var_80]
0x1800322c1  cmp     rdx, [rbp+90h+var_E8]
0x1800322c5  jz      short loc_1800322D3
0x1800322c7  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring &>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::wstring * const,std::wstring &)
0x1800322cc  add     [rbp+90h+var_F0], 20h ; ' '
0x1800322d1  jmp     short loc_1800322DD
0x1800322d3  lea     rcx, [rbp+90h+var_F8]
0x1800322d7  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800322dc  nop
0x1800322dd  lea     rcx, [rbp+90h+var_80]
0x1800322e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800322e6  add     rdi, 28h ; '('
0x1800322ea  cmp     rdi, rsi
0x1800322ed  jnz     loc_180032258
0x1800322f3  lea     rbx, [rbp+90h+arg_48]
0x1800322fa  xor     eax, eax
0x1800322fc  cmp     [rbp+90h+arg_48], 3
0x180032303  cmovz   rbx, rax
0x180032307  lea     rdx, [rsp+190h+var_120]
0x18003230c  lea     rcx, [rbp+90h+Buffer]
0x180032310  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &&)
0x180032315  mov     eax, [rbp+90h+arg_60]
0x18003231b  mov     [rsp+190h+var_130], eax
0x18003231f  mov     al, [rbp+90h+arg_58]
0x180032325  mov     [rsp+190h+var_138], al
0x180032329  lea     rax, [rbp+90h+var_F8]
0x18003232d  mov     [rsp+190h+var_140], rax
0x180032332  mov     [rsp+190h+var_148], rbx
0x180032337  mov     rax, [rbp+90h+var_E0]
0x18003233b  mov     [rsp+190h+var_150], rax
0x180032340  mov     rax, [rbp+90h+var_D8]
0x180032344  mov     [rsp+190h+var_158], rax
0x180032349  mov     rax, [rbp+90h+var_D0]
0x18003234d  mov     [rsp+190h+var_160], rax
0x180032352  mov     rax, [rbp+90h+var_C8]
0x180032356  mov     [rsp+190h+var_168], rax
0x18003235b  mov     [rsp+190h+var_170], r13
0x180032360  lea     r9, [rbp+90h+var_110]
0x180032364  mov     r8, r15
0x180032367  mov     rdx, r12
0x18003236a  lea     rcx, [rbp+90h+Buffer]
0x18003236e  call    cs:__imp_?CCHlpConfigureNode@@YAKV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1AEAV?$vector@EV?$allocator@E@std@@@2@11111PEAKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@_NK@Z; CCHlpConfigureNode(std::map<std::wstring,ulong>,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,ulong *,std::vector<std::wstring> &,bool,ulong)
0x180032375  nop     dword ptr [rax+rax+00h]
0x18003237a  mov     edi, eax
0x18003237c  test    eax, eax
0x18003237e  jle     short loc_180032389
0x180032380  movzx   edi, ax
0x180032383  or      edi, 80070000h
0x180032389  test    edi, edi
0x18003238b  jns     short loc_1800323DD
0x18003238d  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180032392  lea     rbx, [rax+28h]
0x180032396  lea     rdx, aClusapiCluster_1; "ClusApi::ClusterHelper::DeployNode"
0x18003239d  lea     rcx, [rbp+90h+Buffer]
0x1800323a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800323a6  nop
0x1800323a7  lea     rdx, [rbp+90h+Buffer]
0x1800323ab  lea     rcx, [rbp+90h+var_80]
0x1800323af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800323b4  nop
0x1800323b5  lea     r8, [rbp+90h+var_80]
0x1800323b9  lea     rdx, a0ErrorInConfig; "{0} Error in configuring node"
0x1800323c0  mov     rcx, rbx; struct cxl::TextWriter *
0x1800323c3  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x1800323c8  nop
0x1800323c9  lea     rcx, [rbp+90h+var_80]
0x1800323cd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800323d2  nop
0x1800323d3  lea     rcx, [rbp+90h+Buffer]
0x1800323d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800323dc  nop
0x1800323dd  lea     rcx, [rbp+90h+var_F8]
0x1800323e1  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800323e6  nop
0x1800323e7  lea     rcx, [rbp+90h+var_110]
0x1800323eb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800323f0  nop
0x1800323f1  lea     rdx, [rsp+190h+var_120]
0x1800323f6  lea     rcx, [rsp+190h+var_120]
0x1800323fb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &)
0x180032400  mov     eax, edi
0x180032402  mov     rcx, [rbp+90h+var_40]
0x180032406  xor     rcx, rsp; StackCookie
0x180032409  call    __security_check_cookie
0x18003240e  mov     rbx, [rsp+190h+arg_0]
0x180032416  add     rsp, 160h
0x18003241d  pop     r15
0x18003241f  pop     r14
0x180032421  pop     r13
0x180032423  pop     r12
0x180032425  pop     rdi
0x180032426  pop     rsi
0x180032427  pop     rbp
0x180032428  retn
```
