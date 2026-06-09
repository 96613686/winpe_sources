# ClusApi::ClusterHelper::DeployNode(std::vector<_NodeInfo,std::allocator<_NodeInfo>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_ClusterSecretInfo const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ClusterManagementType::Enum,std::vector<_IPAddressInfo,std::allocator<_IPAddressInfo>> const &,bool,ulong)

- ea: `0x1800310f0`
- end: `0x1800313ed`
- name: `?DeployNode@ClusterHelper@ClusApi@@UEAAJAEBV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBU_ClusterSecretInfo@@11111W4Enum@ClusterManagementType@@AEBV?$vector@U_IPAddressInfo@@V?$allocator@U_IPAddressInfo@@@std@@@4@_NK@Z`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a70`
- `0x180003498`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000d250`
- `0x18000d298`
- `0x18000d2bc`
- `0x18000e6f4`
- `0x180012028`
- `0x180013328`
- `0x1800138d0`
- `0x1800145a0`
- `0x1800145e0`
- `0x180015fe0`
- `0x18001610c`
- `0x18001948c`
- `0x18002ea08`
- `0x18002ed90`
- `0x18002f6dc`
- `0x18002f980`
- `0x1800310f0`
- `0x180037098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180031235`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180031235`
- `CLUSAPI!CCHlpConfigureNode` at `0x180031338`
- `CLUSAPI!CCHlpConfigureNode` at `0x180031338`

## string_xrefs

- `0x18003137d`: `{0} Error in configuring node`

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
  __int64 v27; // rcx
  int *v28; // rbx
  int v29; // eax
  signed int v30; // edi
  struct cxl::TextWriter *v31; // rbx
  __int128 v33; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v34; // [rsp+80h] [rbp-80h] BYREF
  void *v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  char v37[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  char v44[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v46[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v47[32]; // [rsp+130h] [rbp+30h] BYREF

  v43 = a6;
  v42 = a7;
  v41 = a8;
  v40 = a9;
  v16 = a11;
  v33 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy(&v33);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v34);
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(v37);
  v17 = a2[1];
  for ( i = *a2; i != v17; i += 104 )
  {
    v19 = *(_DWORD *)(i + 64);
    *(_DWORD *)(*(_QWORD *)std::map<std::wstring,unsigned long>::_Try_emplace<std::wstring const &,>(&v33, Buffer, i)
              + 64LL) = v19;
  }
  cxl::Guid::Guid(Buffer, a4 + 32);
  v20 = (char *)v35;
  if ( (unsigned __int64)((_BYTE *)v35 - (_BYTE *)v34) > 0x10 )
  {
    v21 = (char *)(v34 + 1);
LABEL_10:
    v35 = v21;
    goto LABEL_11;
  }
  if ( (unsigned __int64)((_BYTE *)v35 - (_BYTE *)v34) < 0x10 )
  {
    if ( (unsigned __int64)(v36 - (_QWORD)v34) >= 0x10 )
    {
      v22 = 16 - ((_BYTE *)v35 - (_BYTE *)v34);
      memset_0(v35, 0, v22);
      v21 = &v20[v22];
      goto LABEL_10;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v34, 16);
  }
LABEL_11:
  *v34 = *(_OWORD *)Buffer;
  v23 = *v16;
  v24 = v16[1];
  while ( v23 != v24 )
  {
    _ultow(*(_DWORD *)(v23 + 32), Buffer, 10);
    std::wstring::wstring(v46);
    v25 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v44, v46);
    v26 = std::wstring::wstring(v47, Buffer);
    cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(v25, (wchar_t *)L"{0}/{1}", v23, v26);
    std::wstring::_Tidy_deallocate(v47);
    if ( v38 == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v37, v38, v46);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring &>(
        v27,
        v38,
        v46);
      v38 += 32;
    }
    std::wstring::_Tidy_deallocate(v46);
    v23 += 40;
  }
  v28 = &a10;
  if ( a10 == 3 )
    v28 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
    Buffer,
    &v33);
  v29 = CCHlpConfigureNode(Buffer, a3, a4, &v34, a5, v43, v42, v41, v40, v28, v37, a12, a13);
  v30 = v29;
  if ( v29 > 0 )
    v30 = (unsigned __int16)v29 | 0x80070000;
  if ( v30 < 0 )
  {
    v31 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(Buffer, L"ClusApi::ClusterHelper::DeployNode");
    std::wstring::wstring(v46);
    cxl::TextWriter::WriteLine<char,TraceFunction,>(v31, "{0} Error in configuring node");
    std::wstring::_Tidy_deallocate(v46);
    std::wstring::_Tidy_deallocate(Buffer);
  }
  std::vector<std::wstring>::_Tidy(v37);
  std::vector<unsigned char>::_Tidy(&v34);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    &v33,
    &v33);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1800310f0  mov     [rsp-8+arg_0], rbx
0x1800310f5  push    rbp
0x1800310f6  push    rsi
0x1800310f7  push    rdi
0x1800310f8  push    r12
0x1800310fa  push    r13
0x1800310fc  push    r14
0x1800310fe  push    r15
0x180031100  lea     rbp, [rsp-60h]
0x180031105  sub     rsp, 160h
0x18003110c  mov     rax, cs:__security_cookie
0x180031113  xor     rax, rsp
0x180031116  mov     [rbp+90h+var_40], rax
0x18003111a  mov     r15, r9
0x18003111d  mov     r12, r8
0x180031120  mov     rbx, rdx
0x180031123  mov     r13, [rbp+90h+arg_20]
0x18003112a  mov     rax, [rbp+90h+arg_28]
0x180031131  mov     [rbp+90h+var_C8], rax
0x180031135  mov     rax, [rbp+90h+arg_30]
0x18003113c  mov     [rbp+90h+var_D0], rax
0x180031140  mov     rax, [rbp+90h+arg_38]
0x180031147  mov     [rbp+90h+var_D8], rax
0x18003114b  mov     rax, [rbp+90h+arg_40]
0x180031152  mov     [rbp+90h+var_E0], rax
0x180031156  mov     rsi, [rbp+90h+arg_50]
0x18003115d  xorps   xmm0, xmm0
0x180031160  movdqu  [rsp+190h+var_120], xmm0
0x180031166  lea     rcx, [rsp+190h+var_120]
0x18003116b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180031170  nop
0x180031171  lea     rcx, [rbp+90h+var_110]
0x180031175  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18003117a  nop
0x18003117b  lea     rcx, [rbp+90h+var_F8]
0x18003117f  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180031184  nop
0x180031185  mov     r14, [rbx+8]
0x180031189  mov     rdi, [rbx]
0x18003118c  jmp     short loc_1800311AC
0x18003118e  mov     ebx, [rdi+40h]
0x180031191  mov     r8, rdi
0x180031194  lea     rdx, [rbp+90h+Buffer]
0x180031198  lea     rcx, [rsp+190h+var_120]
0x18003119d  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,ulong>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800311a2  mov     rcx, [rax]
0x1800311a5  mov     [rcx+40h], ebx
0x1800311a8  add     rdi, 68h ; 'h'
0x1800311ac  cmp     rdi, r14
0x1800311af  jnz     short loc_18003118E
0x1800311b1  lea     rdx, [r15+20h]
0x1800311b5  lea     rcx, [rbp+90h+Buffer]
0x1800311b9  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x1800311be  mov     rdx, [rbp+90h+var_110]
0x1800311c2  mov     rdi, [rbp+90h+var_108]
0x1800311c6  mov     rcx, rdi
0x1800311c9  sub     rcx, rdx
0x1800311cc  mov     ebx, 10h
0x1800311d1  cmp     rcx, rbx
0x1800311d4  jbe     short loc_1800311DC
0x1800311d6  lea     rax, [rdx+10h]
0x1800311da  jmp     short loc_18003120C
0x1800311dc  jnb     short loc_180031210
0x1800311de  mov     rax, [rbp+90h+var_100]
0x1800311e2  sub     rax, rdx
0x1800311e5  cmp     rax, rbx
0x1800311e8  jnb     short loc_1800311F8
0x1800311ea  mov     rdx, rbx
0x1800311ed  lea     rcx, [rbp+90h+var_110]
0x1800311f1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800311f6  jmp     short loc_180031210
0x1800311f8  sub     rbx, rcx
0x1800311fb  mov     r8, rbx; Size
0x1800311fe  xor     edx, edx; Val
0x180031200  mov     rcx, rdi; void *
0x180031203  call    memset_0
0x180031208  lea     rax, [rbx+rdi]
0x18003120c  mov     [rbp+90h+var_108], rax
0x180031210  movups  xmm0, xmmword ptr [rbp+90h+Buffer]
0x180031214  mov     rax, [rbp+90h+var_110]
0x180031218  movdqu  xmmword ptr [rax], xmm0
0x18003121c  mov     rdi, [rsi]
0x18003121f  mov     rsi, [rsi+8]
0x180031223  jmp     loc_1800312B4
0x180031228  mov     r8d, 0Ah; Radix
0x18003122e  lea     rdx, [rbp+90h+Buffer]; Buffer
0x180031232  mov     ecx, [rdi+20h]; Value
0x180031235  call    cs:__imp__ultow
0x18003123b  lea     rcx, [rbp+90h+var_80]
0x18003123f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180031244  nop
0x180031245  lea     rdx, [rbp+90h+var_80]
0x180031249  lea     rcx, [rbp+90h+var_C0]
0x18003124d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180031252  mov     rbx, rax
0x180031255  lea     rdx, [rbp+90h+Buffer]
0x180031259  lea     rcx, [rbp+90h+var_60]
0x18003125d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180031262  nop
0x180031263  mov     r9, rax
0x180031266  mov     r8, rdi
0x180031269  lea     rdx, a01; "{0}/{1}"
0x180031270  mov     rcx, rbx; struct cxl::TextWriter *
0x180031273  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::TextWriter::Write<wchar_t,std::wstring,std::wstring>(wchar_t const *,std::wstring const &,std::wstring const &)
0x180031278  nop
0x180031279  lea     rcx, [rbp+90h+var_60]
0x18003127d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031282  nop
0x180031283  mov     rdx, [rbp+90h+var_F0]
0x180031287  lea     r8, [rbp+90h+var_80]
0x18003128b  cmp     rdx, [rbp+90h+var_E8]
0x18003128f  jz      short loc_18003129D
0x180031291  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring &>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::wstring * const,std::wstring &)
0x180031296  add     [rbp+90h+var_F0], 20h ; ' '
0x18003129b  jmp     short loc_1800312A7
0x18003129d  lea     rcx, [rbp+90h+var_F8]
0x1800312a1  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800312a6  nop
0x1800312a7  lea     rcx, [rbp+90h+var_80]
0x1800312ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800312b0  add     rdi, 28h ; '('
0x1800312b4  cmp     rdi, rsi
0x1800312b7  jnz     loc_180031228
0x1800312bd  lea     rbx, [rbp+90h+arg_48]
0x1800312c4  xor     eax, eax
0x1800312c6  cmp     [rbp+90h+arg_48], 3
0x1800312cd  cmovz   rbx, rax
0x1800312d1  lea     rdx, [rsp+190h+var_120]
0x1800312d6  lea     rcx, [rbp+90h+Buffer]
0x1800312da  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &&)
0x1800312df  mov     eax, [rbp+90h+arg_60]
0x1800312e5  mov     [rsp+190h+var_130], eax
0x1800312e9  mov     al, [rbp+90h+arg_58]
0x1800312ef  mov     [rsp+190h+var_138], al
0x1800312f3  lea     rax, [rbp+90h+var_F8]
0x1800312f7  mov     [rsp+190h+var_140], rax
0x1800312fc  mov     [rsp+190h+var_148], rbx
0x180031301  mov     rax, [rbp+90h+var_E0]
0x180031305  mov     [rsp+190h+var_150], rax
0x18003130a  mov     rax, [rbp+90h+var_D8]
0x18003130e  mov     [rsp+190h+var_158], rax
0x180031313  mov     rax, [rbp+90h+var_D0]
0x180031317  mov     [rsp+190h+var_160], rax
0x18003131c  mov     rax, [rbp+90h+var_C8]
0x180031320  mov     [rsp+190h+var_168], rax
0x180031325  mov     [rsp+190h+var_170], r13
0x18003132a  lea     r9, [rbp+90h+var_110]
0x18003132e  mov     r8, r15
0x180031331  mov     rdx, r12
0x180031334  lea     rcx, [rbp+90h+Buffer]
0x180031338  call    cs:__imp_?CCHlpConfigureNode@@YAKV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1AEAV?$vector@EV?$allocator@E@std@@@2@11111PEAKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@_NK@Z; CCHlpConfigureNode(std::map<std::wstring,ulong>,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,ulong *,std::vector<std::wstring> &,bool,ulong)
0x18003133e  mov     edi, eax
0x180031340  test    eax, eax
0x180031342  jle     short loc_18003134D
0x180031344  movzx   edi, ax
0x180031347  or      edi, 80070000h
0x18003134d  test    edi, edi
0x18003134f  jns     short loc_1800313A1
0x180031351  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180031356  lea     rbx, [rax+28h]
0x18003135a  lea     rdx, aClusapiCluster_1; "ClusApi::ClusterHelper::DeployNode"
0x180031361  lea     rcx, [rbp+90h+Buffer]
0x180031365  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003136a  nop
0x18003136b  lea     rdx, [rbp+90h+Buffer]
0x18003136f  lea     rcx, [rbp+90h+var_80]
0x180031373  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031378  nop
0x180031379  lea     r8, [rbp+90h+var_80]
0x18003137d  lea     rdx, a0ErrorInConfig; "{0} Error in configuring node"
0x180031384  mov     rcx, rbx; struct cxl::TextWriter *
0x180031387  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x18003138c  nop
0x18003138d  lea     rcx, [rbp+90h+var_80]
0x180031391  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031396  nop
0x180031397  lea     rcx, [rbp+90h+Buffer]
0x18003139b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800313a0  nop
0x1800313a1  lea     rcx, [rbp+90h+var_F8]
0x1800313a5  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800313aa  nop
0x1800313ab  lea     rcx, [rbp+90h+var_110]
0x1800313af  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800313b4  nop
0x1800313b5  lea     rdx, [rsp+190h+var_120]
0x1800313ba  lea     rcx, [rsp+190h+var_120]
0x1800313bf  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &)
0x1800313c4  mov     eax, edi
0x1800313c6  mov     rcx, [rbp+90h+var_40]
0x1800313ca  xor     rcx, rsp; StackCookie
0x1800313cd  call    __security_check_cookie
0x1800313d2  mov     rbx, [rsp+190h+arg_0]
0x1800313da  add     rsp, 160h
0x1800313e1  pop     r15
0x1800313e3  pop     r14
0x1800313e5  pop     r13
0x1800313e7  pop     r12
0x1800313e9  pop     rdi
0x1800313ea  pop     rsi
0x1800313eb  pop     rbp
0x1800313ec  retn
```
