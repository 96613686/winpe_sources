# CDescriptionManager::HrPDT_ReplaceIcons(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)

- ea: `0x180018f14`
- end: `0x18001930f`
- name: `?HrPDT_ReplaceIcons@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800162e0`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013870`
- `0x180015ab0`
- `0x180015d90`
- `0x180016f50`
- `0x180018c8c`
- `0x180018f14`
- `0x18001ab90`
- `0x180028968`
- `0x180030c30`
- `0x180038324`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x180043124`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001900f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019055`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001909e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019104`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019138`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019180`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001929d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001900f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019055`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001909e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800190f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019104`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019138`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019170`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019180`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001929d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018fca`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018fca`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180018fb4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180018fb4`

## string_xrefs

- `0x180018ff3`: `udhisapi.dll?content=`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrPDT_ReplaceIcons(__int64 a1, __int64 a2, const wchar_t *a3, __int64 a4)
{
  STRSAFE_PCNZWCH v5; // rcx
  void *v6; // r12
  HRESULT v7; // r14d
  bool v8; // zf
  __int64 v9; // rdx
  __int64 Key; // rax
  void *v11; // rsi
  unsigned __int16 *v12; // rdi
  _WORD *v13; // rbx
  size_t v14; // r8
  size_t v15; // rdx
  size_t *v16; // r8
  int v17; // eax
  HRESULT FullPath; // eax
  void *v19; // r15
  void *v20; // rbx
  HRESULT inserted; // eax
  STRSAFE_PCNZWCH v23; // rcx
  size_t v24; // [rsp+20h] [rbp-49h]
  void *Block; // [rsp+30h] [rbp-39h] BYREF
  void *v26; // [rsp+38h] [rbp-31h] BYREF
  __int64 v27; // [rsp+40h] [rbp-29h] BYREF
  void *v28; // [rsp+48h] [rbp-21h] BYREF
  void *v29; // [rsp+50h] [rbp-19h]
  _QWORD v30[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v31; // [rsp+68h] [rbp-1h]
  GUID pguid; // [rsp+70h] [rbp+7h] BYREF

  v31 = a4;
  v30[1] = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = v7 == 0;
    if ( v7 < 0 )
      break;
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v27);
    Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v9);
    if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Key + 72LL))(Key, &v27) )
    {
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v27);
      v5 = WPP_GLOBAL_Control;
      v8 = v7 == 0;
      break;
    }
    v30[0] = 0;
    v26 = 0;
    pguid = 0;
    v11 = 0;
    v12 = 0;
    v7 = CoCreateGuid(&pguid);
    if ( v7 < 0 )
      goto LABEL_16;
    v13 = malloc(0x2Cu);
    if ( v13 )
    {
      v7 = StringValidateDestW((STRSAFE_PCNZWCH)0x16, 0x16u, v14);
      if ( v7 < 0 )
      {
        *v13 = 0;
LABEL_39:
        free(v13);
        goto LABEL_30;
      }
      v7 = StringCopyWorkerW(v13, v15, v16, L"udhisapi.dll?content=", v24);
      if ( v7 < 0 )
        goto LABEL_39;
      free(0);
      v12 = v13;
      v26 = v13;
      if ( !v7 )
        goto LABEL_10;
    }
    else
    {
      v7 = -2147024882;
    }
LABEL_30:
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
        (unsigned int)v7);
      v23 = WPP_GLOBAL_Control;
    }
    if ( v7 >= 0 )
    {
LABEL_10:
      Block = 0;
      v7 = HrGUIDToUDNString(&pguid, (struct CUString *)&Block);
      if ( v7 >= 0 )
      {
        v17 = CUString::HrAppend((CUString *)&v26, (const unsigned __int16 *)Block);
        v12 = (unsigned __int16 *)v26;
        v7 = v17;
      }
      free(Block);
      if ( !v7 )
      {
LABEL_13:
        Block = 0;
        v7 = HrSelectNodeText((OLECHAR *)L"ddd:url");
        if ( v7 >= 0 )
        {
          FullPath = HrMakeFullPath(a3, (STRSAFE_PCNZWCH)Block, (struct CUString *)v30);
          v11 = (void *)v30[0];
          v7 = FullPath;
        }
        free(Block);
        if ( v7 >= 0 )
        {
          v26 = 0;
          v7 = CUString::HrAssign((CUString *)&v26, L"/upnphost/");
          if ( v7 >= 0 )
          {
            v7 = CUString::HrAppend((CUString *)&v26, v12);
            if ( v7 >= 0 )
              v7 = HrSelectAndSetNodeText((OLECHAR *)L"ddd:url");
          }
          free(v26);
          if ( v7 >= 0 )
          {
            free(0);
            v19 = v11;
            v28 = v11;
            v11 = 0;
            Block = 0;
            v7 = HrSelectNodeText((OLECHAR *)L"ddd:mimetype");
            if ( v7 < 0 )
            {
              v20 = Block;
            }
            else
            {
              free(0);
              v20 = 0;
              v29 = Block;
              inserted = CTable<_GUID,FileInfo>::HrInsertTransfer(v31, &pguid, &v28);
              v6 = v29;
              v7 = inserted;
              v19 = v28;
            }
            free(v20);
            free(v6);
            v6 = 0;
            v29 = 0;
            free(v19);
            v28 = 0;
          }
        }
        goto LABEL_16;
      }
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v23[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v23 + 2), 13, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v7);
    if ( v7 >= 0 )
      goto LABEL_13;
LABEL_16:
    free(v12);
    free(v11);
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v27);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !v8 && v5 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v5[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 39, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018f14  mov     [rsp-8+arg_0], rbx
0x180018f19  push    rbp
0x180018f1a  push    rsi
0x180018f1b  push    rdi
0x180018f1c  push    r12
0x180018f1e  push    r13
0x180018f20  push    r14
0x180018f22  push    r15
0x180018f24  lea     rbp, [rsp-27h]
0x180018f29  sub     rsp, 90h
0x180018f30  mov     rax, cs:__security_cookie
0x180018f37  xor     rax, rsp
0x180018f3a  mov     [rbp+57h+var_40], rax
0x180018f3e  mov     [rbp+57h+var_58], r9
0x180018f42  mov     r13, r8
0x180018f45  mov     [rbp+57h+var_60], rdx
0x180018f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f50  lea     r15, WPP_GLOBAL_Control
0x180018f57  cmp     rcx, r15
0x180018f5a  jnz     loc_18001925F
0x180018f60  xor     r12d, r12d
0x180018f63  mov     r14d, r12d
0x180018f66  test    r14d, r14d
0x180018f69  js      loc_1800191DC
0x180018f6f  lea     rcx, [rbp+57h+var_80]; void *
0x180018f73  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180018f78  mov     rcx, rdx
0x180018f7b  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x180018f80  mov     rcx, rax
0x180018f83  lea     rdx, [rbp+57h+var_80]
0x180018f87  mov     rax, [rax]
0x180018f8a  mov     rax, [rax+48h]
0x180018f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f93  test    eax, eax
0x180018f95  jnz     loc_1800191C9
0x180018f9b  xorps   xmm0, xmm0
0x180018f9e  mov     [rbp+57h+var_68], r12
0x180018fa2  lea     rcx, [rbp+57h+pguid]; pguid
0x180018fa6  mov     [rbp+57h+var_88], r12
0x180018faa  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180018fae  mov     rsi, r12
0x180018fb1  mov     rdi, r12
0x180018fb4  call    cs:__imp_CoCreateGuid
0x180018fba  mov     r14d, eax
0x180018fbd  test    eax, eax
0x180018fbf  js      loc_1800190A9
0x180018fc5  mov     ecx, 2Ch ; ','; Size
0x180018fca  call    cs:__imp_malloc
0x180018fd0  mov     rbx, rax
0x180018fd3  test    rax, rax
0x180018fd6  jz      loc_18001928E
0x180018fdc  mov     ecx, 16h; pszDest
0x180018fe1  mov     edx, ecx; cchDest
0x180018fe3  call    StringValidateDestW
0x180018fe8  mov     r14d, eax
0x180018feb  test    eax, eax
0x180018fed  js      loc_180019296
0x180018ff3  lea     r9, aUdhisapiDllCon_0; "udhisapi.dll?content="
0x180018ffa  mov     rcx, rbx; pszDest
0x180018ffd  call    StringCopyWorkerW
0x180019002  mov     r14d, eax
0x180019005  test    eax, eax
0x180019007  js      loc_18001929A
0x18001900d  xor     ecx, ecx; Block
0x18001900f  call    cs:__imp_free
0x180019015  mov     rdi, rbx
0x180019018  mov     [rbp+57h+var_88], rbx
0x18001901c  test    r14d, r14d
0x18001901f  jnz     loc_180019223
0x180019025  lea     rdx, [rbp+57h+Block]; struct CUString *
0x180019029  mov     [rbp+57h+Block], r12
0x18001902d  lea     rcx, [rbp+57h+pguid]; Uuid
0x180019031  call    ?HrGUIDToUDNString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGUIDToUDNString(_GUID const &,CUString &)
0x180019036  mov     r14d, eax
0x180019039  test    eax, eax
0x18001903b  js      short loc_180019051
0x18001903d  mov     rdx, [rbp+57h+Block]; unsigned __int16 *
0x180019041  lea     rcx, [rbp+57h+var_88]; this
0x180019045  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001904a  mov     rdi, [rbp+57h+var_88]
0x18001904e  mov     r14d, eax
0x180019051  mov     rcx, [rbp+57h+Block]; Block
0x180019055  call    cs:__imp_free
0x18001905b  test    r14d, r14d
0x18001905e  jnz     loc_1800192A8
0x180019064  lea     r8, [rbp+57h+Block]
0x180019068  mov     [rbp+57h+Block], r12
0x18001906c  lea     rdx, [rbp+57h+var_80]
0x180019070  lea     rcx, aDddUrl; "ddd:url"
0x180019077  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18001907c  mov     r14d, eax
0x18001907f  test    eax, eax
0x180019081  js      short loc_18001909A
0x180019083  mov     rdx, [rbp+57h+Block]; STRSAFE_PCNZWCH
0x180019087  lea     r8, [rbp+57h+var_68]; struct CUString *
0x18001908b  mov     rcx, r13; pszSrc
0x18001908e  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180019093  mov     rsi, [rbp+57h+var_68]
0x180019097  mov     r14d, eax
0x18001909a  mov     rcx, [rbp+57h+Block]; Block
0x18001909e  call    cs:__imp_free
0x1800190a4  test    r14d, r14d
0x1800190a7  jns     short loc_1800190D4
0x1800190a9  mov     rcx, rdi; Block
0x1800190ac  call    cs:__imp_free
0x1800190b2  mov     rcx, rsi; Block
0x1800190b5  call    cs:__imp_free
0x1800190bb  lea     rcx, [rbp+57h+var_80]
0x1800190bf  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800190c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190cb  mov     rdx, [rbp+57h+var_60]
0x1800190cf  jmp     loc_180018F66
0x1800190d4  lea     rdx, aUpnphost; "/upnphost/"
0x1800190db  mov     [rbp+57h+var_88], r12
0x1800190df  lea     rcx, [rbp+57h+var_88]; this
0x1800190e3  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x1800190e8  mov     r14d, eax
0x1800190eb  test    eax, eax
0x1800190ed  jns     loc_180019196
0x1800190f3  mov     rcx, [rbp+57h+var_88]; Block
0x1800190f7  call    cs:__imp_free
0x1800190fd  test    r14d, r14d
0x180019100  js      short loc_1800190A9
0x180019102  xor     ecx, ecx; Block
0x180019104  call    cs:__imp_free
0x18001910a  mov     r15, rsi
0x18001910d  mov     [rbp+57h+var_78], rsi
0x180019111  xor     esi, esi
0x180019113  lea     r8, [rbp+57h+Block]
0x180019117  lea     rdx, [rbp+57h+var_80]
0x18001911b  mov     [rbp+57h+Block], rsi
0x18001911f  lea     rcx, aDddMimetype; "ddd:mimetype"
0x180019126  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18001912b  mov     r14d, eax
0x18001912e  test    eax, eax
0x180019130  js      loc_18001920C
0x180019136  xor     ecx, ecx; Block
0x180019138  call    cs:__imp_free
0x18001913e  mov     rax, [rbp+57h+Block]
0x180019142  lea     r8, [rbp+57h+var_78]
0x180019146  mov     rcx, [rbp+57h+var_58]
0x18001914a  lea     rdx, [rbp+57h+pguid]
0x18001914e  xor     ebx, ebx
0x180019150  mov     [rbp+57h+var_70], rax
0x180019154  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x180019159  mov     r12, [rbp+57h+var_70]
0x18001915d  mov     r14d, eax
0x180019160  mov     r15, [rbp+57h+var_78]
0x180019164  mov     rcx, rbx; Block
0x180019167  call    cs:__imp_free
0x18001916d  mov     rcx, r12; Block
0x180019170  call    cs:__imp_free
0x180019176  xor     r12d, r12d
0x180019179  mov     rcx, r15; Block
0x18001917c  mov     [rbp+57h+var_70], r12
0x180019180  call    cs:__imp_free
0x180019186  mov     [rbp+57h+var_78], r12
0x18001918a  lea     r15, WPP_GLOBAL_Control
0x180019191  jmp     loc_1800190A9
0x180019196  mov     rdx, rdi; unsigned __int16 *
0x180019199  lea     rcx, [rbp+57h+var_88]; this
0x18001919d  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800191a2  mov     r14d, eax
0x1800191a5  test    eax, eax
0x1800191a7  js      loc_1800190F3
0x1800191ad  lea     r8, [rbp+57h+var_88]
0x1800191b1  lea     rdx, [rbp+57h+var_80]
0x1800191b5  lea     rcx, aDddUrl; "ddd:url"
0x1800191bc  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x1800191c1  mov     r14d, eax
0x1800191c4  jmp     loc_1800190F3
0x1800191c9  lea     rcx, [rbp+57h+var_80]
0x1800191cd  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800191d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191d9  test    r14d, r14d
0x1800191dc  jnz     loc_1800192DF
0x1800191e2  mov     eax, r14d
0x1800191e5  mov     rcx, [rbp+57h+var_40]
0x1800191e9  xor     rcx, rsp; StackCookie
0x1800191ec  call    __security_check_cookie
0x1800191f1  mov     rbx, [rsp+0C0h+arg_0]
0x1800191f9  add     rsp, 90h
0x180019200  pop     r15
0x180019202  pop     r14
0x180019204  pop     r13
0x180019206  pop     r12
0x180019208  pop     rdi
0x180019209  pop     rsi
0x18001920a  pop     rbp
0x18001920b  retn
0x18001920c  mov     rbx, [rbp+57h+Block]
0x180019210  jmp     loc_180019164
0x180019215  test    r14d, r14d
0x180019218  jns     loc_180019064
0x18001921e  jmp     loc_1800190A9
0x180019223  mov     rcx, cs:WPP_GLOBAL_Control
0x18001922a  cmp     rcx, r15
0x18001922d  jz      short loc_180019254
0x18001922f  test    byte ptr [rcx+1Ch], 1
0x180019233  jz      short loc_180019254
0x180019235  mov     rcx, [rcx+10h]
0x180019239  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180019240  mov     edx, 0Ah
0x180019245  mov     r9d, r14d
0x180019248  call    WPP_SF_d
0x18001924d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019254  test    r14d, r14d
0x180019257  jns     loc_180019025
0x18001925d  jmp     short loc_1800192AF
0x18001925f  test    byte ptr [rcx+1Ch], 40h
0x180019263  jz      loc_180018F60
0x180019269  mov     rcx, [rcx+10h]
0x18001926d  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180019274  mov     edx, 26h ; '&'
0x180019279  call    WPP_SF_
0x18001927e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019285  mov     rdx, [rbp+57h+var_60]
0x180019289  jmp     loc_180018F60
0x18001928e  mov     r14d, 8007000Eh
0x180019294  jmp     short loc_180019223
0x180019296  mov     [rbx], r12w
0x18001929a  mov     rcx, rbx; Block
0x18001929d  call    cs:__imp_free
0x1800192a3  jmp     loc_180019223
0x1800192a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192af  cmp     rcx, r15
0x1800192b2  jz      loc_180019215
0x1800192b8  test    byte ptr [rcx+1Ch], 1
0x1800192bc  jz      loc_180019215
0x1800192c2  mov     rcx, [rcx+10h]
0x1800192c6  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800192cd  mov     edx, 0Dh
0x1800192d2  mov     r9d, r14d
0x1800192d5  call    WPP_SF_d
0x1800192da  jmp     loc_180019215
0x1800192df  cmp     rcx, r15
0x1800192e2  jz      loc_1800191E2
0x1800192e8  test    byte ptr [rcx+1Ch], 1
0x1800192ec  jz      loc_1800191E2
0x1800192f2  mov     rcx, [rcx+10h]
0x1800192f6  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800192fd  mov     edx, 27h ; '''
0x180019302  mov     r9d, r14d
0x180019305  call    WPP_SF_d
0x18001930a  jmp     loc_1800191E2
```
