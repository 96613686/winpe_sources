# CDescriptionManager::HrPDT_ReplaceIcons(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)

- ea: `0x18000de40`
- end: `0x18000e290`
- name: `?HrPDT_ReplaceIcons@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a5f0`

## callees

- `0x1800056d8`
- `0x1800056f0`
- `0x180007920`
- `0x180009d50`
- `0x18000a060`
- `0x18000b2c8`
- `0x18000d1bc`
- `0x18000de40`
- `0x18000f8a0`
- `0x180029e68`
- `0x180032220`
- `0x18003a798`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180045b90`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000df47`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000df93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dfe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dff6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e005`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e04d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e060`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e09a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e218`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000df47`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000df93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dfe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dff6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e005`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e04d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e060`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e09a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e218`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000defc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000defc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000dee0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000dee0`

## string_xrefs

- `0x18000df2b`: `udhisapi.dll?content=`

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
  _BYTE v27[8]; // [rsp+40h] [rbp-29h] BYREF
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
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v27);
    Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v9);
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)Key + 72LL))(Key, v27) )
    {
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v27);
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
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v27);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !v8 && v5 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v5[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 39, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000de40  mov     [rsp-8+arg_0], rbx
0x18000de45  push    rbp
0x18000de46  push    rsi
0x18000de47  push    rdi
0x18000de48  push    r12
0x18000de4a  push    r13
0x18000de4c  push    r14
0x18000de4e  push    r15
0x18000de50  lea     rbp, [rsp-27h]
0x18000de55  sub     rsp, 90h
0x18000de5c  mov     rax, cs:__security_cookie
0x18000de63  xor     rax, rsp
0x18000de66  mov     [rbp+57h+var_40], rax
0x18000de6a  mov     [rbp+57h+var_58], r9
0x18000de6e  mov     r13, r8
0x18000de71  mov     [rbp+57h+var_60], rdx
0x18000de75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de7c  lea     r15, WPP_GLOBAL_Control
0x18000de83  cmp     rcx, r15
0x18000de86  jnz     loc_18000E1DA
0x18000de8c  xor     r12d, r12d
0x18000de8f  mov     r14d, r12d
0x18000de92  test    r14d, r14d
0x18000de95  js      loc_18000E156
0x18000de9b  lea     rcx, [rbp+57h+var_80]; void *
0x18000de9f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000dea4  mov     rcx, rdx
0x18000dea7  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000deac  mov     rcx, rax
0x18000deaf  lea     rdx, [rbp+57h+var_80]
0x18000deb3  mov     rax, [rax]
0x18000deb6  mov     rax, [rax+48h]
0x18000deba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000debf  test    eax, eax
0x18000dec1  jnz     loc_18000E143
0x18000dec7  xorps   xmm0, xmm0
0x18000deca  mov     [rbp+57h+var_68], r12
0x18000dece  lea     rcx, [rbp+57h+pguid]; pguid
0x18000ded2  mov     [rbp+57h+var_88], r12
0x18000ded6  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18000deda  mov     rsi, r12
0x18000dedd  mov     rdi, r12
0x18000dee0  call    cs:__imp_CoCreateGuid
0x18000dee7  nop     dword ptr [rax+rax+00h]
0x18000deec  mov     r14d, eax
0x18000deef  test    eax, eax
0x18000def1  js      loc_18000DFF3
0x18000def7  mov     ecx, 2Ch ; ','; Size
0x18000defc  call    cs:__imp_malloc
0x18000df03  nop     dword ptr [rax+rax+00h]
0x18000df08  mov     rbx, rax
0x18000df0b  test    rax, rax
0x18000df0e  jz      loc_18000E209
0x18000df14  mov     ecx, 16h; pszDest
0x18000df19  mov     edx, ecx; cchDest
0x18000df1b  call    StringValidateDestW
0x18000df20  mov     r14d, eax
0x18000df23  test    eax, eax
0x18000df25  js      loc_18000E211
0x18000df2b  lea     r9, aUdhisapiDllCon_0; "udhisapi.dll?content="
0x18000df32  mov     rcx, rbx; pszDest
0x18000df35  call    StringCopyWorkerW
0x18000df3a  mov     r14d, eax
0x18000df3d  test    eax, eax
0x18000df3f  js      loc_18000E215
0x18000df45  xor     ecx, ecx; Block
0x18000df47  call    cs:__imp_free
0x18000df4e  nop     dword ptr [rax+rax+00h]
0x18000df53  mov     rdi, rbx
0x18000df56  mov     [rbp+57h+var_88], rbx
0x18000df5a  test    r14d, r14d
0x18000df5d  jnz     loc_18000E19E
0x18000df63  lea     rdx, [rbp+57h+Block]; struct CUString *
0x18000df67  mov     [rbp+57h+Block], r12
0x18000df6b  lea     rcx, [rbp+57h+pguid]; Uuid
0x18000df6f  call    ?HrGUIDToUDNString@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGUIDToUDNString(_GUID const &,CUString &)
0x18000df74  mov     r14d, eax
0x18000df77  test    eax, eax
0x18000df79  js      short loc_18000DF8F
0x18000df7b  mov     rdx, [rbp+57h+Block]; unsigned __int16 *
0x18000df7f  lea     rcx, [rbp+57h+var_88]; this
0x18000df83  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000df88  mov     rdi, [rbp+57h+var_88]
0x18000df8c  mov     r14d, eax
0x18000df8f  mov     rcx, [rbp+57h+Block]; Block
0x18000df93  call    cs:__imp_free
0x18000df9a  nop     dword ptr [rax+rax+00h]
0x18000df9f  test    r14d, r14d
0x18000dfa2  jnz     loc_18000E229
0x18000dfa8  lea     r8, [rbp+57h+Block]
0x18000dfac  mov     [rbp+57h+Block], r12
0x18000dfb0  lea     rdx, [rbp+57h+var_80]
0x18000dfb4  lea     rcx, aDddUrl; "ddd:url"
0x18000dfbb  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000dfc0  mov     r14d, eax
0x18000dfc3  test    eax, eax
0x18000dfc5  js      short loc_18000DFDE
0x18000dfc7  mov     rdx, [rbp+57h+Block]; STRSAFE_PCNZWCH
0x18000dfcb  lea     r8, [rbp+57h+var_68]; struct CUString *
0x18000dfcf  mov     rcx, r13; pszSrc
0x18000dfd2  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x18000dfd7  mov     rsi, [rbp+57h+var_68]
0x18000dfdb  mov     r14d, eax
0x18000dfde  mov     rcx, [rbp+57h+Block]; Block
0x18000dfe2  call    cs:__imp_free
0x18000dfe9  nop     dword ptr [rax+rax+00h]
0x18000dfee  test    r14d, r14d
0x18000dff1  jns     short loc_18000E02A
0x18000dff3  mov     rcx, rdi; Block
0x18000dff6  call    cs:__imp_free
0x18000dffd  nop     dword ptr [rax+rax+00h]
0x18000e002  mov     rcx, rsi; Block
0x18000e005  call    cs:__imp_free
0x18000e00c  nop     dword ptr [rax+rax+00h]
0x18000e011  lea     rcx, [rbp+57h+var_80]
0x18000e015  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000e01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e021  mov     rdx, [rbp+57h+var_60]
0x18000e025  jmp     loc_18000DE92
0x18000e02a  lea     rdx, aUpnphost; "/upnphost/"
0x18000e031  mov     [rbp+57h+var_88], r12
0x18000e035  lea     rcx, [rbp+57h+var_88]; this
0x18000e039  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000e03e  mov     r14d, eax
0x18000e041  test    eax, eax
0x18000e043  jns     loc_18000E110
0x18000e049  mov     rcx, [rbp+57h+var_88]; Block
0x18000e04d  call    cs:__imp_free
0x18000e054  nop     dword ptr [rax+rax+00h]
0x18000e059  test    r14d, r14d
0x18000e05c  js      short loc_18000DFF3
0x18000e05e  xor     ecx, ecx; Block
0x18000e060  call    cs:__imp_free
0x18000e067  nop     dword ptr [rax+rax+00h]
0x18000e06c  mov     r15, rsi
0x18000e06f  mov     [rbp+57h+var_78], rsi
0x18000e073  xor     esi, esi
0x18000e075  lea     r8, [rbp+57h+Block]
0x18000e079  lea     rdx, [rbp+57h+var_80]
0x18000e07d  mov     [rbp+57h+Block], rsi
0x18000e081  lea     rcx, aDddMimetype; "ddd:mimetype"
0x18000e088  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000e08d  mov     r14d, eax
0x18000e090  test    eax, eax
0x18000e092  js      loc_18000E187
0x18000e098  xor     ecx, ecx; Block
0x18000e09a  call    cs:__imp_free
0x18000e0a1  nop     dword ptr [rax+rax+00h]
0x18000e0a6  mov     rax, [rbp+57h+Block]
0x18000e0aa  lea     r8, [rbp+57h+var_78]
0x18000e0ae  mov     rcx, [rbp+57h+var_58]
0x18000e0b2  lea     rdx, [rbp+57h+pguid]
0x18000e0b6  xor     ebx, ebx
0x18000e0b8  mov     [rbp+57h+var_70], rax
0x18000e0bc  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x18000e0c1  mov     r12, [rbp+57h+var_70]
0x18000e0c5  mov     r14d, eax
0x18000e0c8  mov     r15, [rbp+57h+var_78]
0x18000e0cc  mov     rcx, rbx; Block
0x18000e0cf  call    cs:__imp_free
0x18000e0d6  nop     dword ptr [rax+rax+00h]
0x18000e0db  mov     rcx, r12; Block
0x18000e0de  call    cs:__imp_free
0x18000e0e5  nop     dword ptr [rax+rax+00h]
0x18000e0ea  xor     r12d, r12d
0x18000e0ed  mov     rcx, r15; Block
0x18000e0f0  mov     [rbp+57h+var_70], r12
0x18000e0f4  call    cs:__imp_free
0x18000e0fb  nop     dword ptr [rax+rax+00h]
0x18000e100  mov     [rbp+57h+var_78], r12
0x18000e104  lea     r15, WPP_GLOBAL_Control
0x18000e10b  jmp     loc_18000DFF3
0x18000e110  mov     rdx, rdi; unsigned __int16 *
0x18000e113  lea     rcx, [rbp+57h+var_88]; this
0x18000e117  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000e11c  mov     r14d, eax
0x18000e11f  test    eax, eax
0x18000e121  js      loc_18000E049
0x18000e127  lea     r8, [rbp+57h+var_88]
0x18000e12b  lea     rdx, [rbp+57h+var_80]
0x18000e12f  lea     rcx, aDddUrl; "ddd:url"
0x18000e136  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x18000e13b  mov     r14d, eax
0x18000e13e  jmp     loc_18000E049
0x18000e143  lea     rcx, [rbp+57h+var_80]
0x18000e147  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000e14c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e153  test    r14d, r14d
0x18000e156  jnz     loc_18000E260
0x18000e15c  mov     eax, r14d
0x18000e15f  mov     rcx, [rbp+57h+var_40]
0x18000e163  xor     rcx, rsp; StackCookie
0x18000e166  call    __security_check_cookie
0x18000e16b  mov     rbx, [rsp+0C0h+arg_0]
0x18000e173  add     rsp, 90h
0x18000e17a  pop     r15
0x18000e17c  pop     r14
0x18000e17e  pop     r13
0x18000e180  pop     r12
0x18000e182  pop     rdi
0x18000e183  pop     rsi
0x18000e184  pop     rbp
0x18000e185  retn
0x18000e187  mov     rbx, [rbp+57h+Block]
0x18000e18b  jmp     loc_18000E0CC
0x18000e190  test    r14d, r14d
0x18000e193  jns     loc_18000DFA8
0x18000e199  jmp     loc_18000DFF3
0x18000e19e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1a5  cmp     rcx, r15
0x18000e1a8  jz      short loc_18000E1CF
0x18000e1aa  test    byte ptr [rcx+1Ch], 1
0x18000e1ae  jz      short loc_18000E1CF
0x18000e1b0  mov     rcx, [rcx+10h]
0x18000e1b4  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x18000e1bb  mov     edx, 0Ah
0x18000e1c0  mov     r9d, r14d
0x18000e1c3  call    WPP_SF_d
0x18000e1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1cf  test    r14d, r14d
0x18000e1d2  jns     loc_18000DF63
0x18000e1d8  jmp     short loc_18000E230
0x18000e1da  test    byte ptr [rcx+1Ch], 40h
0x18000e1de  jz      loc_18000DE8C
0x18000e1e4  mov     rcx, [rcx+10h]
0x18000e1e8  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e1ef  mov     edx, 26h ; '&'
0x18000e1f4  call    WPP_SF_
0x18000e1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e200  mov     rdx, [rbp+57h+var_60]
0x18000e204  jmp     loc_18000DE8C
0x18000e209  mov     r14d, 8007000Eh
0x18000e20f  jmp     short loc_18000E19E
0x18000e211  mov     [rbx], r12w
0x18000e215  mov     rcx, rbx; Block
0x18000e218  call    cs:__imp_free
0x18000e21f  nop     dword ptr [rax+rax+00h]
0x18000e224  jmp     loc_18000E19E
0x18000e229  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e230  cmp     rcx, r15
0x18000e233  jz      loc_18000E190
0x18000e239  test    byte ptr [rcx+1Ch], 1
0x18000e23d  jz      loc_18000E190
0x18000e243  mov     rcx, [rcx+10h]
0x18000e247  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e24e  mov     edx, 0Dh
0x18000e253  mov     r9d, r14d
0x18000e256  call    WPP_SF_d
0x18000e25b  jmp     loc_18000E190
0x18000e260  cmp     rcx, r15
0x18000e263  jz      loc_18000E15C
0x18000e269  test    byte ptr [rcx+1Ch], 1
0x18000e26d  jz      loc_18000E15C
0x18000e273  mov     rcx, [rcx+10h]
0x18000e277  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000e27e  mov     edx, 27h ; '''
0x18000e283  mov     r9d, r14d
0x18000e286  call    WPP_SF_d
0x18000e28b  jmp     loc_18000E15C
```
