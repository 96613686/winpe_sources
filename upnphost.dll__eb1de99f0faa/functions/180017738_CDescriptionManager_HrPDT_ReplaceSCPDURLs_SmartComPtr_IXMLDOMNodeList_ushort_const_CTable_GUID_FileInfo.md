# CDescriptionManager::HrPDT_ReplaceSCPDURLs(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)

- ea: `0x180017738`
- end: `0x180017a63`
- name: `?HrPDT_ReplaceSCPDURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800162e0`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013870`
- `0x180015d90`
- `0x180016f50`
- `0x180017738`
- `0x180018b40`
- `0x18001ab90`
- `0x180024910`
- `0x180025018`
- `0x18002518c`
- `0x180028968`
- `0x180030c30`
- `0x180038324`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x180043124`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017843`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001789c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800178b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017915`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001796b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001797f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179b7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017843`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001789c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800178b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017915`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001796b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001797f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179b7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179e1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001785a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001785a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800177eb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800177eb`

## string_xrefs

- `0x180017933`: `REMOVE`
- `0x180017989`: `text/xml; charset="utf-8"`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrPDT_ReplaceSCPDURLs(__int64 a1, __int64 a2, const wchar_t *a3, __int64 a4)
{
  STRSAFE_PCNZWCH v7; // rcx
  HRESULT ContentURL; // esi
  bool v9; // zf
  __int64 Key; // rax
  void *v11; // rdi
  unsigned __int16 *v12; // rbx
  HRESULT FullPath; // eax
  wchar_t *v14; // rax
  size_t v15; // r8
  wchar_t *v16; // r14
  size_t v17; // rdx
  size_t *v18; // r8
  size_t v20; // [rsp+20h] [rbp-60h]
  void *Block; // [rsp+30h] [rbp-50h] BYREF
  void *v22; // [rsp+38h] [rbp-48h] BYREF
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-38h] BYREF
  void *v25; // [rsp+50h] [rbp-30h] BYREF
  void *v26; // [rsp+58h] [rbp-28h] BYREF
  GUID pguid; // [rsp+60h] [rbp-20h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  ContentURL = 0;
  while ( 1 )
  {
    v9 = ContentURL == 0;
    if ( ContentURL < 0 )
      break;
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v23);
    Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(a2);
    if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Key + 72LL))(Key, &v23) )
    {
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v23);
      v7 = WPP_GLOBAL_Control;
      v9 = ContentURL == 0;
      break;
    }
    v11 = 0;
    v12 = 0;
    v22 = 0;
    v24 = 0;
    pguid = 0;
    ContentURL = CoCreateGuid(&pguid);
    if ( ContentURL >= 0 )
    {
      ContentURL = HrGetContentURL(&pguid, (struct CUString *)&v24);
      if ( ContentURL < 0 )
        goto LABEL_35;
      Block = 0;
      ContentURL = HrGetNodeText(&v23, &Block);
      if ( ContentURL >= 0 )
      {
        FullPath = HrMakeFullPath(a3, (STRSAFE_PCNZWCH)Block, (struct CUString *)&v22);
        v11 = v22;
        ContentURL = FullPath;
      }
      free(Block);
      if ( ContentURL < 0 )
      {
LABEL_35:
        v12 = v24;
        goto LABEL_36;
      }
      Block = 0;
      v14 = (wchar_t *)malloc(0x16u);
      v12 = v24;
      v16 = v14;
      if ( !v14 )
      {
        ContentURL = -2147024882;
LABEL_20:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
            (unsigned int)ContentURL);
        if ( ContentURL >= 0 )
        {
LABEL_24:
          ContentURL = CUString::HrAppend((CUString *)&Block, v12);
          if ( ContentURL >= 0 )
            ContentURL = HrSetNodeText(&v23, &Block);
        }
        free(Block);
        if ( ContentURL >= 0 )
        {
          ContentURL = HrCheckForEventedVariables((struct CUString *)&v22);
          if ( ContentURL == 1 )
          {
            v22 = 0;
            ContentURL = CUString::HrAssign((CUString *)&v22, L"REMOVE");
            if ( ContentURL >= 0 )
              ContentURL = HrSelectAndSetNodeText((OLECHAR *)L"../ddd:eventSubURL");
            free(v22);
          }
          if ( ContentURL >= 0 )
          {
            v26 = 0;
            free(0);
            v25 = v11;
            v11 = 0;
            ContentURL = CUString::HrAssign((CUString *)&v26, L"text/xml; charset=\"utf-8\"");
            if ( ContentURL >= 0 )
              ContentURL = CTable<_GUID,FileInfo>::HrInsertTransfer(a4, &pguid, &v25);
            free(v26);
            v26 = 0;
            free(v25);
            v25 = 0;
          }
        }
        goto LABEL_36;
      }
      ContentURL = StringValidateDestW((STRSAFE_PCNZWCH)0xB, 0xBu, v15);
      if ( ContentURL < 0 )
      {
        *v16 = 0;
      }
      else
      {
        ContentURL = StringCopyWorkerW(v16, v17, v18, L"/upnphost/", v20);
        if ( ContentURL >= 0 )
        {
          free(0);
          Block = v16;
          if ( ContentURL )
            goto LABEL_20;
          goto LABEL_24;
        }
      }
      free(v16);
      goto LABEL_20;
    }
LABEL_36:
    free(v12);
    free(v11);
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v23);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !v9 && v7 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 37, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)ContentURL);
  return (unsigned int)ContentURL;
}

```

## disassembly

```asm
0x180017738  mov     [rsp-38h+arg_0], rbx
0x18001773d  push    rbp
0x18001773e  push    rsi
0x18001773f  push    rdi
0x180017740  push    r12
0x180017742  push    r13
0x180017744  push    r14
0x180017746  push    r15
0x180017748  mov     rbp, rsp
0x18001774b  sub     rsp, 80h
0x180017752  mov     rax, cs:__security_cookie
0x180017759  xor     rax, rsp
0x18001775c  mov     [rbp+var_10], rax
0x180017760  mov     r12, r9
0x180017763  mov     r15, r8
0x180017766  mov     r13, rdx
0x180017769  mov     rcx, cs:WPP_GLOBAL_Control
0x180017770  lea     rbx, WPP_GLOBAL_Control
0x180017777  cmp     rcx, rbx
0x18001777a  jz      short loc_18001779E
0x18001777c  test    byte ptr [rcx+1Ch], 40h
0x180017780  jz      short loc_18001779E
0x180017782  mov     rcx, [rcx+10h]
0x180017786  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001778d  mov     edx, 24h ; '$'
0x180017792  call    WPP_SF_
0x180017797  mov     rcx, cs:WPP_GLOBAL_Control
0x18001779e  xor     esi, esi
0x1800177a0  test    esi, esi
0x1800177a2  js      loc_180017A0E
0x1800177a8  lea     rcx, [rbp+var_40]; void *
0x1800177ac  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800177b1  mov     rcx, r13
0x1800177b4  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x1800177b9  mov     rcx, rax
0x1800177bc  lea     rdx, [rbp+var_40]
0x1800177c0  mov     rax, [rax]
0x1800177c3  mov     rax, [rax+48h]
0x1800177c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177cc  test    eax, eax
0x1800177ce  jnz     loc_1800179FC
0x1800177d4  xorps   xmm0, xmm0
0x1800177d7  lea     rcx, [rbp+pguid]; pguid
0x1800177db  xor     edi, edi
0x1800177dd  xor     ebx, ebx
0x1800177df  mov     [rbp+var_48], rdi
0x1800177e3  mov     [rbp+var_38], rbx
0x1800177e7  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800177eb  call    cs:__imp_CoCreateGuid
0x1800177f1  mov     esi, eax
0x1800177f3  test    eax, eax
0x1800177f5  js      loc_1800179D5
0x1800177fb  lea     rdx, [rbp+var_38]; this
0x1800177ff  lea     rcx, [rbp+pguid]; Uuid
0x180017803  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x180017808  mov     esi, eax
0x18001780a  test    eax, eax
0x18001780c  js      loc_1800179D1
0x180017812  lea     rdx, [rbp+Block]
0x180017816  mov     [rbp+Block], rbx
0x18001781a  lea     rcx, [rbp+var_40]
0x18001781e  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x180017823  mov     esi, eax
0x180017825  test    eax, eax
0x180017827  js      short loc_18001783F
0x180017829  mov     rdx, [rbp+Block]; STRSAFE_PCNZWCH
0x18001782d  lea     r8, [rbp+var_48]; struct CUString *
0x180017831  mov     rcx, r15; pszSrc
0x180017834  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180017839  mov     rdi, [rbp+var_48]
0x18001783d  mov     esi, eax
0x18001783f  mov     rcx, [rbp+Block]; Block
0x180017843  call    cs:__imp_free
0x180017849  test    esi, esi
0x18001784b  js      loc_1800179D1
0x180017851  mov     ecx, 16h; Size
0x180017856  mov     [rbp+Block], rbx
0x18001785a  call    cs:__imp_malloc
0x180017860  mov     rbx, [rbp+var_38]
0x180017864  mov     r14, rax
0x180017867  test    rax, rax
0x18001786a  jnz     short loc_180017873
0x18001786c  mov     esi, 8007000Eh
0x180017871  jmp     short loc_1800178BB
0x180017873  mov     ecx, 0Bh; pszDest
0x180017878  mov     edx, ecx; cchDest
0x18001787a  call    StringValidateDestW
0x18001787f  mov     esi, eax
0x180017881  test    eax, eax
0x180017883  js      short loc_1800178AC
0x180017885  lea     r9, aUpnphost; "/upnphost/"
0x18001788c  mov     rcx, r14; pszDest
0x18001788f  call    StringCopyWorkerW
0x180017894  mov     esi, eax
0x180017896  test    eax, eax
0x180017898  js      short loc_1800178B2
0x18001789a  xor     ecx, ecx; Block
0x18001789c  call    cs:__imp_free
0x1800178a2  mov     [rbp+Block], r14
0x1800178a6  test    esi, esi
0x1800178a8  jnz     short loc_1800178BB
0x1800178aa  jmp     short loc_1800178F0
0x1800178ac  xor     eax, eax
0x1800178ae  mov     [r14], ax
0x1800178b2  mov     rcx, r14; Block
0x1800178b5  call    cs:__imp_free
0x1800178bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c2  lea     rax, WPP_GLOBAL_Control
0x1800178c9  cmp     rcx, rax
0x1800178cc  jz      short loc_1800178EC
0x1800178ce  test    byte ptr [rcx+1Ch], 1
0x1800178d2  jz      short loc_1800178EC
0x1800178d4  mov     rcx, [rcx+10h]
0x1800178d8  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800178df  mov     edx, 0Ah
0x1800178e4  mov     r9d, esi
0x1800178e7  call    WPP_SF_d
0x1800178ec  test    esi, esi
0x1800178ee  js      short loc_180017911
0x1800178f0  mov     rdx, rbx; unsigned __int16 *
0x1800178f3  lea     rcx, [rbp+Block]; this
0x1800178f7  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800178fc  mov     esi, eax
0x1800178fe  test    eax, eax
0x180017900  js      short loc_180017911
0x180017902  lea     rdx, [rbp+Block]
0x180017906  lea     rcx, [rbp+var_40]
0x18001790a  call    ?HrSetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSetNodeText(SmartComPtr<IXMLDOMNode> &,CUString const &)
0x18001790f  mov     esi, eax
0x180017911  mov     rcx, [rbp+Block]; Block
0x180017915  call    cs:__imp_free
0x18001791b  test    esi, esi
0x18001791d  js      loc_1800179D5
0x180017923  lea     rcx, [rbp+var_48]; struct CUString *
0x180017927  call    ?HrCheckForEventedVariables@@YAJAEAVCUString@@@Z; HrCheckForEventedVariables(CUString &)
0x18001792c  mov     esi, eax
0x18001792e  cmp     eax, 1
0x180017931  jnz     short loc_180017971
0x180017933  lea     rdx, aRemove; "REMOVE"
0x18001793a  mov     [rbp+var_48], 0
0x180017942  lea     rcx, [rbp+var_48]; this
0x180017946  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18001794b  mov     esi, eax
0x18001794d  test    eax, eax
0x18001794f  js      short loc_180017967
0x180017951  lea     r8, [rbp+var_48]
0x180017955  lea     rdx, [rbp+var_40]
0x180017959  lea     rcx, aDddEventsuburl; "../ddd:eventSubURL"
0x180017960  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x180017965  mov     esi, eax
0x180017967  mov     rcx, [rbp+var_48]; Block
0x18001796b  call    cs:__imp_free
0x180017971  test    esi, esi
0x180017973  js      short loc_1800179D5
0x180017975  xor     ecx, ecx; Block
0x180017977  mov     [rbp+var_28], 0
0x18001797f  call    cs:__imp_free
0x180017985  mov     [rbp+var_30], rdi
0x180017989  lea     rdx, aTextXmlCharset; "text/xml; charset=\"utf-8\""
0x180017990  lea     rcx, [rbp+var_28]; this
0x180017994  xor     edi, edi
0x180017996  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18001799b  mov     esi, eax
0x18001799d  test    eax, eax
0x18001799f  js      short loc_1800179B3
0x1800179a1  lea     r8, [rbp+var_30]
0x1800179a5  mov     rcx, r12
0x1800179a8  lea     rdx, [rbp+pguid]
0x1800179ac  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x1800179b1  mov     esi, eax
0x1800179b3  mov     rcx, [rbp+var_28]; Block
0x1800179b7  call    cs:__imp_free
0x1800179bd  mov     rcx, [rbp+var_30]; Block
0x1800179c1  mov     [rbp+var_28], rdi
0x1800179c5  call    cs:__imp_free
0x1800179cb  mov     [rbp+var_30], rdi
0x1800179cf  jmp     short loc_1800179D5
0x1800179d1  mov     rbx, [rbp+var_38]
0x1800179d5  mov     rcx, rbx; Block
0x1800179d8  call    cs:__imp_free
0x1800179de  mov     rcx, rdi; Block
0x1800179e1  call    cs:__imp_free
0x1800179e7  lea     rcx, [rbp+var_40]
0x1800179eb  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800179f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179f7  jmp     loc_1800177A0
0x1800179fc  lea     rcx, [rbp+var_40]
0x180017a00  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180017a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a0c  test    esi, esi
0x180017a0e  jz      short loc_180017A3A
0x180017a10  lea     rax, WPP_GLOBAL_Control
0x180017a17  cmp     rcx, rax
0x180017a1a  jz      short loc_180017A3A
0x180017a1c  test    byte ptr [rcx+1Ch], 1
0x180017a20  jz      short loc_180017A3A
0x180017a22  mov     rcx, [rcx+10h]
0x180017a26  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180017a2d  mov     edx, 25h ; '%'
0x180017a32  mov     r9d, esi
0x180017a35  call    WPP_SF_d
0x180017a3a  mov     eax, esi
0x180017a3c  mov     rcx, [rbp+var_10]
0x180017a40  xor     rcx, rsp; StackCookie
0x180017a43  call    __security_check_cookie
0x180017a48  mov     rbx, [rsp+80h+arg_0]
0x180017a50  add     rsp, 80h
0x180017a57  pop     r15
0x180017a59  pop     r14
0x180017a5b  pop     r13
0x180017a5d  pop     r12
0x180017a5f  pop     rdi
0x180017a60  pop     rsi
0x180017a61  pop     rbp
0x180017a62  retn
```
