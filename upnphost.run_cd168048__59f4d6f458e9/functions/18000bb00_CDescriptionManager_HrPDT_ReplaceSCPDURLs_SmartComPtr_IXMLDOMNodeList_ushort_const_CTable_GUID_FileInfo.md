# CDescriptionManager::HrPDT_ReplaceSCPDURLs(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)

- ea: `0x18000bb00`
- end: `0x18000be74`
- name: `?HrPDT_ReplaceSCPDURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000a5f0`

## callees

- `0x18000413c`
- `0x1800056d8`
- `0x1800056f0`
- `0x180007920`
- `0x18000a060`
- `0x18000b2c8`
- `0x18000bb00`
- `0x18000d058`
- `0x18000f8a0`
- `0x180025190`
- `0x180025fa4`
- `0x180029e68`
- `0x180032220`
- `0x18003a798`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180045b90`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bcfb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdc3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bddc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdeb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bcfb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bd71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdc3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bddc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bdeb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bc2e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bc2e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bbb3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bbb3`

## string_xrefs

- `0x18000bd1f`: `REMOVE`
- `0x18000bd81`: `text/xml; charset="utf-8"`

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
  _BYTE v23[8]; // [rsp+40h] [rbp-40h] BYREF
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
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v23);
    Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(a2);
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)Key + 72LL))(Key, v23) )
    {
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v23);
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
      ContentURL = HrGetNodeText(v23, &Block);
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
            ContentURL = HrSetNodeText(v23, &Block);
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
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v23);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !v9 && v7 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 37, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)ContentURL);
  return (unsigned int)ContentURL;
}

```

## disassembly

```asm
0x18000bb00  mov     [rsp-38h+arg_0], rbx
0x18000bb05  push    rbp
0x18000bb06  push    rsi
0x18000bb07  push    rdi
0x18000bb08  push    r12
0x18000bb0a  push    r13
0x18000bb0c  push    r14
0x18000bb0e  push    r15
0x18000bb10  mov     rbp, rsp
0x18000bb13  sub     rsp, 80h
0x18000bb1a  mov     rax, cs:__security_cookie
0x18000bb21  xor     rax, rsp
0x18000bb24  mov     [rbp+var_10], rax
0x18000bb28  mov     r12, r9
0x18000bb2b  mov     r15, r8
0x18000bb2e  mov     r13, rdx
0x18000bb31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb38  lea     rbx, WPP_GLOBAL_Control
0x18000bb3f  cmp     rcx, rbx
0x18000bb42  jz      short loc_18000BB66
0x18000bb44  test    byte ptr [rcx+1Ch], 40h
0x18000bb48  jz      short loc_18000BB66
0x18000bb4a  mov     rcx, [rcx+10h]
0x18000bb4e  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000bb55  mov     edx, 24h ; '$'
0x18000bb5a  call    WPP_SF_
0x18000bb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb66  xor     esi, esi
0x18000bb68  test    esi, esi
0x18000bb6a  js      loc_18000BE1E
0x18000bb70  lea     rcx, [rbp+var_40]; void *
0x18000bb74  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000bb79  mov     rcx, r13
0x18000bb7c  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000bb81  mov     rcx, rax
0x18000bb84  lea     rdx, [rbp+var_40]
0x18000bb88  mov     rax, [rax]
0x18000bb8b  mov     rax, [rax+48h]
0x18000bb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb94  test    eax, eax
0x18000bb96  jnz     loc_18000BE0C
0x18000bb9c  xorps   xmm0, xmm0
0x18000bb9f  lea     rcx, [rbp+pguid]; pguid
0x18000bba3  xor     edi, edi
0x18000bba5  xor     ebx, ebx
0x18000bba7  mov     [rbp+var_48], rdi
0x18000bbab  mov     [rbp+var_38], rbx
0x18000bbaf  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x18000bbb3  call    cs:__imp_CoCreateGuid
0x18000bbba  nop     dword ptr [rax+rax+00h]
0x18000bbbf  mov     esi, eax
0x18000bbc1  test    eax, eax
0x18000bbc3  js      loc_18000BDD9
0x18000bbc9  lea     rdx, [rbp+var_38]; this
0x18000bbcd  lea     rcx, [rbp+pguid]; Uuid
0x18000bbd1  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x18000bbd6  mov     esi, eax
0x18000bbd8  test    eax, eax
0x18000bbda  js      loc_18000BDD5
0x18000bbe0  lea     rdx, [rbp+Block]
0x18000bbe4  mov     [rbp+Block], rbx
0x18000bbe8  lea     rcx, [rbp+var_40]
0x18000bbec  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000bbf1  mov     esi, eax
0x18000bbf3  test    eax, eax
0x18000bbf5  js      short loc_18000BC0D
0x18000bbf7  mov     rdx, [rbp+Block]; STRSAFE_PCNZWCH
0x18000bbfb  lea     r8, [rbp+var_48]; struct CUString *
0x18000bbff  mov     rcx, r15; pszSrc
0x18000bc02  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x18000bc07  mov     rdi, [rbp+var_48]
0x18000bc0b  mov     esi, eax
0x18000bc0d  mov     rcx, [rbp+Block]; Block
0x18000bc11  call    cs:__imp_free
0x18000bc18  nop     dword ptr [rax+rax+00h]
0x18000bc1d  test    esi, esi
0x18000bc1f  js      loc_18000BDD5
0x18000bc25  mov     ecx, 16h; Size
0x18000bc2a  mov     [rbp+Block], rbx
0x18000bc2e  call    cs:__imp_malloc
0x18000bc35  nop     dword ptr [rax+rax+00h]
0x18000bc3a  mov     rbx, [rbp+var_38]
0x18000bc3e  mov     r14, rax
0x18000bc41  test    rax, rax
0x18000bc44  jnz     short loc_18000BC4D
0x18000bc46  mov     esi, 8007000Eh
0x18000bc4b  jmp     short loc_18000BCA1
0x18000bc4d  mov     ecx, 0Bh; pszDest
0x18000bc52  mov     edx, ecx; cchDest
0x18000bc54  call    StringValidateDestW
0x18000bc59  mov     esi, eax
0x18000bc5b  test    eax, eax
0x18000bc5d  js      short loc_18000BC8C
0x18000bc5f  lea     r9, aUpnphost; "/upnphost/"
0x18000bc66  mov     rcx, r14; pszDest
0x18000bc69  call    StringCopyWorkerW
0x18000bc6e  mov     esi, eax
0x18000bc70  test    eax, eax
0x18000bc72  js      short loc_18000BC92
0x18000bc74  xor     ecx, ecx; Block
0x18000bc76  call    cs:__imp_free
0x18000bc7d  nop     dword ptr [rax+rax+00h]
0x18000bc82  mov     [rbp+Block], r14
0x18000bc86  test    esi, esi
0x18000bc88  jnz     short loc_18000BCA1
0x18000bc8a  jmp     short loc_18000BCD6
0x18000bc8c  xor     eax, eax
0x18000bc8e  mov     [r14], ax
0x18000bc92  mov     rcx, r14; Block
0x18000bc95  call    cs:__imp_free
0x18000bc9c  nop     dword ptr [rax+rax+00h]
0x18000bca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bca8  lea     rax, WPP_GLOBAL_Control
0x18000bcaf  cmp     rcx, rax
0x18000bcb2  jz      short loc_18000BCD2
0x18000bcb4  test    byte ptr [rcx+1Ch], 1
0x18000bcb8  jz      short loc_18000BCD2
0x18000bcba  mov     rcx, [rcx+10h]
0x18000bcbe  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x18000bcc5  mov     edx, 0Ah
0x18000bcca  mov     r9d, esi
0x18000bccd  call    WPP_SF_d
0x18000bcd2  test    esi, esi
0x18000bcd4  js      short loc_18000BCF7
0x18000bcd6  mov     rdx, rbx; unsigned __int16 *
0x18000bcd9  lea     rcx, [rbp+Block]; this
0x18000bcdd  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000bce2  mov     esi, eax
0x18000bce4  test    eax, eax
0x18000bce6  js      short loc_18000BCF7
0x18000bce8  lea     rdx, [rbp+Block]
0x18000bcec  lea     rcx, [rbp+var_40]
0x18000bcf0  call    ?HrSetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSetNodeText(SmartComPtr<IXMLDOMNode> &,CUString const &)
0x18000bcf5  mov     esi, eax
0x18000bcf7  mov     rcx, [rbp+Block]; Block
0x18000bcfb  call    cs:__imp_free
0x18000bd02  nop     dword ptr [rax+rax+00h]
0x18000bd07  test    esi, esi
0x18000bd09  js      loc_18000BDD9
0x18000bd0f  lea     rcx, [rbp+var_48]; struct CUString *
0x18000bd13  call    ?HrCheckForEventedVariables@@YAJAEAVCUString@@@Z; HrCheckForEventedVariables(CUString &)
0x18000bd18  mov     esi, eax
0x18000bd1a  cmp     eax, 1
0x18000bd1d  jnz     short loc_18000BD63
0x18000bd1f  lea     rdx, aRemove; "REMOVE"
0x18000bd26  mov     [rbp+var_48], 0
0x18000bd2e  lea     rcx, [rbp+var_48]; this
0x18000bd32  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000bd37  mov     esi, eax
0x18000bd39  test    eax, eax
0x18000bd3b  js      short loc_18000BD53
0x18000bd3d  lea     r8, [rbp+var_48]
0x18000bd41  lea     rdx, [rbp+var_40]
0x18000bd45  lea     rcx, aDddEventsuburl; "../ddd:eventSubURL"
0x18000bd4c  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x18000bd51  mov     esi, eax
0x18000bd53  mov     rcx, [rbp+var_48]; Block
0x18000bd57  call    cs:__imp_free
0x18000bd5e  nop     dword ptr [rax+rax+00h]
0x18000bd63  test    esi, esi
0x18000bd65  js      short loc_18000BDD9
0x18000bd67  xor     ecx, ecx; Block
0x18000bd69  mov     [rbp+var_28], 0
0x18000bd71  call    cs:__imp_free
0x18000bd78  nop     dword ptr [rax+rax+00h]
0x18000bd7d  mov     [rbp+var_30], rdi
0x18000bd81  lea     rdx, aTextXmlCharset; "text/xml; charset=\"utf-8\""
0x18000bd88  lea     rcx, [rbp+var_28]; this
0x18000bd8c  xor     edi, edi
0x18000bd8e  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000bd93  mov     esi, eax
0x18000bd95  test    eax, eax
0x18000bd97  js      short loc_18000BDAB
0x18000bd99  lea     r8, [rbp+var_30]
0x18000bd9d  mov     rcx, r12
0x18000bda0  lea     rdx, [rbp+pguid]
0x18000bda4  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x18000bda9  mov     esi, eax
0x18000bdab  mov     rcx, [rbp+var_28]; Block
0x18000bdaf  call    cs:__imp_free
0x18000bdb6  nop     dword ptr [rax+rax+00h]
0x18000bdbb  mov     rcx, [rbp+var_30]; Block
0x18000bdbf  mov     [rbp+var_28], rdi
0x18000bdc3  call    cs:__imp_free
0x18000bdca  nop     dword ptr [rax+rax+00h]
0x18000bdcf  mov     [rbp+var_30], rdi
0x18000bdd3  jmp     short loc_18000BDD9
0x18000bdd5  mov     rbx, [rbp+var_38]
0x18000bdd9  mov     rcx, rbx; Block
0x18000bddc  call    cs:__imp_free
0x18000bde3  nop     dword ptr [rax+rax+00h]
0x18000bde8  mov     rcx, rdi; Block
0x18000bdeb  call    cs:__imp_free
0x18000bdf2  nop     dword ptr [rax+rax+00h]
0x18000bdf7  lea     rcx, [rbp+var_40]
0x18000bdfb  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000be00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be07  jmp     loc_18000BB68
0x18000be0c  lea     rcx, [rbp+var_40]
0x18000be10  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000be15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be1c  test    esi, esi
0x18000be1e  jz      short loc_18000BE4A
0x18000be20  lea     rax, WPP_GLOBAL_Control
0x18000be27  cmp     rcx, rax
0x18000be2a  jz      short loc_18000BE4A
0x18000be2c  test    byte ptr [rcx+1Ch], 1
0x18000be30  jz      short loc_18000BE4A
0x18000be32  mov     rcx, [rcx+10h]
0x18000be36  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000be3d  mov     edx, 25h ; '%'
0x18000be42  mov     r9d, esi
0x18000be45  call    WPP_SF_d
0x18000be4a  mov     eax, esi
0x18000be4c  mov     rcx, [rbp+var_10]
0x18000be50  xor     rcx, rsp; StackCookie
0x18000be53  call    __security_check_cookie
0x18000be58  mov     rbx, [rsp+80h+arg_0]
0x18000be60  add     rsp, 80h
0x18000be67  pop     r15
0x18000be69  pop     r14
0x18000be6b  pop     r13
0x18000be6d  pop     r12
0x18000be6f  pop     rdi
0x18000be70  pop     rsi
0x18000be71  pop     rbp
0x18000be72  retn
```
