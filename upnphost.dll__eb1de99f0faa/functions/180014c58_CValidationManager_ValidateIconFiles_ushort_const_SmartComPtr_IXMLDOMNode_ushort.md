# CValidationManager::ValidateIconFiles(ushort const *,SmartComPtr<IXMLDOMNode>,ushort * *)

- ea: `0x180014c58`
- end: `0x1800150b4`
- name: `?ValidateIconFiles@CValidationManager@@AEAAJPEBGV?$SmartComPtr@UIXMLDOMNode@@@@PEAPEAG@Z`
- size: `1116`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800249e0`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013870`
- `0x180014c58`
- `0x180023500`
- `0x180025470`
- `0x18002564c`
- `0x180030c30`
- `0x180037ef8`
- `0x180038250`
- `0x180038324`
- `0x180038ce4`
- `0x180043124`
- `0x180046540`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014dcb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e13`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014fe6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001500e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014dcb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e13`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014e5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014fe6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001500e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014d86`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ec1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014ea9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014ea9`
- `OLEAUT32!__imp_SysAllocString` at `0x180014c9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180014c9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cf3`
- `OLEAUT32!__imp_SysFreeString` at `0x180014de5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cf3`
- `OLEAUT32!__imp_SysFreeString` at `0x180014de5`

## pseudocode

```c
__int64 __fastcall CValidationManager::ValidateIconFiles(
        void *a1,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // r15
  __int64 v5; // r13
  const wchar_t *v6; // r14
  void *v7; // rbx
  OLECHAR *v8; // rdi
  __int64 Key; // rax
  unsigned int v10; // esi
  wchar_t *v11; // rbx
  int v12; // edi
  const wchar_t *v13; // r15
  __int64 v14; // rax
  size_t v15; // r13
  size_t v16; // r8
  wchar_t *v17; // r14
  HRESULT v18; // eax
  size_t v19; // rdx
  wchar_t v20; // cx
  size_t *v21; // r8
  HRESULT v22; // r15d
  int FullPath; // eax
  void *v24; // r14
  HANDLE FileW; // rax
  const unsigned __int16 *StringPcch; // rax
  STRSAFE_PCNZWCH v28; // r10
  unsigned __int16 *v29; // r8
  STRSAFE_PCNZWCH v30; // r10
  const wchar_t *v31; // r9
  size_t dwCreationDisposition; // [rsp+20h] [rbp-48h]
  void *v33; // [rsp+40h] [rbp-28h] BYREF
  __int64 v34; // [rsp+48h] [rbp-20h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-10h] BYREF
  void *Block; // [rsp+B0h] [rbp+48h] BYREF
  const wchar_t *v38; // [rsp+B8h] [rbp+50h]
  __int64 v39; // [rsp+C0h] [rbp+58h]
  unsigned __int16 **v40; // [rsp+C8h] [rbp+60h]

  v40 = a4;
  v39 = a3;
  v38 = a2;
  Block = a1;
  v4 = a4;
  v5 = a3;
  v6 = a2;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v34);
  v7 = 0;
  v33 = 0;
  v8 = SysAllocString(L"//ddd:device/ddd:iconList/ddd:icon/ddd:url");
  if ( v8 )
  {
    ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v34);
    Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v5);
    v10 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)Key + 288LL))(Key, v8, &v34);
    if ( v10 == 1 )
      v10 = -2147467259;
    SysFreeString(v8);
    if ( !v10 )
    {
      while ( 1 )
      {
        SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v36);
        v11 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v34 + 72LL))(v34, v36);
        if ( !v12 )
          break;
LABEL_20:
        free(v11);
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)v36);
        v6 = v38;
        if ( v12 )
        {
          v7 = v33;
          v4 = v40;
          v5 = v39;
          goto LABEL_22;
        }
      }
      pszSrc = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD, STRSAFE_PCNZWCH *))(*(_QWORD *)v36[0] + 208LL))(v36[0], &pszSrc);
      if ( v12 < 0 )
      {
LABEL_17:
        if ( !v12 )
          goto LABEL_18;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
            (unsigned int)v12);
        if ( v12 >= 0 )
        {
LABEL_18:
          Block = 0;
          FullPath = HrMakeFullPath(v6, v11, (struct CUString *)&Block);
          v24 = Block;
          v12 = FullPath;
          if ( FullPath >= 0 )
          {
            FileW = CreateFileW((LPCWSTR)Block, 0x80000000, 3u, 0, 3u, 0x80u, 0);
            if ( FileW )
            {
              if ( FileW == (HANDLE)-1LL )
              {
                LODWORD(Block) = 0;
                StringPcch = WszLoadStringPcch(qword_180071C60, 0xCEu, (int *)&Block);
                v12 = CUString::HrPrintf((CUString *)&v33, StringPcch, v24);
                if ( v12 >= 0 )
                  v12 = -2147180507;
              }
              else
              {
                CloseHandle(FileW);
              }
            }
          }
          free(v24);
        }
        goto LABEL_20;
      }
      v13 = pszSrc;
      if ( !pszSrc )
      {
        free(0);
        v12 = 0;
        goto LABEL_16;
      }
      v14 = -1;
      do
        ++v14;
      while ( pszSrc[v14] );
      v15 = v14 + 1;
      v17 = (wchar_t *)malloc(2 * (v14 + 1));
      if ( !v17 )
      {
        v12 = -2147024882;
        goto LABEL_33;
      }
      v18 = StringValidateDestW(0, v15, v16);
      v12 = v18;
      if ( v18 < 0 )
      {
        v22 = v18;
        if ( v15 )
        {
          *v17 = v20;
          goto LABEL_52;
        }
      }
      else
      {
        v22 = StringCopyWorkerW(v17, v19, v21, v13, dwCreationDisposition);
      }
      v12 = v22;
      if ( v22 >= 0 )
      {
        free(0);
        v11 = v17;
        if ( !v22 )
        {
LABEL_15:
          v6 = v38;
LABEL_16:
          SysFreeString((BSTR)pszSrc);
          goto LABEL_17;
        }
LABEL_33:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
            (unsigned int)v12);
        goto LABEL_15;
      }
LABEL_52:
      free(v17);
      goto LABEL_33;
    }
    goto LABEL_43;
  }
  v28 = WPP_GLOBAL_Control;
  v10 = -2147024882;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    goto LABEL_47;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids,
      (unsigned int)L"//ddd:device/ddd:iconList/ddd:icon/ddd:url",
      14);
    v28 = WPP_GLOBAL_Control;
  }
  if ( v28 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    goto LABEL_47;
  if ( (v28[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v28 + 2), 15, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, 2147942414LL);
LABEL_43:
    v28 = WPP_GLOBAL_Control;
  }
  if ( v28 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v28[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v28 + 2), 16, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids, v10);
LABEL_47:
  v12 = v10;
LABEL_22:
  if ( v12 < 0 )
  {
    if ( CUString::GetLength((CUString *)&v33) )
    {
      CUString::HrGetCOM((CUString *)&v33, (LPVOID *)v4);
      v30 = WPP_GLOBAL_Control;
      v29 = 0;
    }
    if ( v30 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v30[14] & 1) != 0 )
    {
      v31 = L"Unspecified";
      if ( *v4 != v29 )
        v31 = *v4;
      WPP_SF_Sd(
        *((_QWORD *)v30 + 2),
        28,
        (unsigned int)WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids,
        (_DWORD)v31,
        v12);
    }
  }
  else
  {
    v12 = 0;
  }
  free(v7);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v34);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v5);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014c58  mov     rax, rsp
0x180014c5b  mov     [rax+20h], r9
0x180014c5f  mov     [rax+18h], r8
0x180014c63  mov     [rax+10h], rdx
0x180014c67  mov     [rax+8], rcx
0x180014c6b  push    rbp
0x180014c6c  push    rbx
0x180014c6d  push    rsi
0x180014c6e  push    rdi
0x180014c6f  push    r12
0x180014c71  push    r13
0x180014c73  push    r14
0x180014c75  push    r15
0x180014c77  mov     rbp, rsp
0x180014c7a  sub     rsp, 68h
0x180014c7e  lea     rcx, [rbp+var_20]; void *
0x180014c82  mov     r15, r9
0x180014c85  mov     r13, r8
0x180014c88  mov     r14, rdx
0x180014c8b  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180014c90  xor     ebx, ebx
0x180014c92  lea     rcx, aDddDeviceDddIc; "//ddd:device/ddd:iconList/ddd:icon/ddd:"...
0x180014c99  mov     [rbp+var_28], rbx
0x180014c9d  call    cs:__imp_SysAllocString
0x180014ca3  lea     r12, WPP_GLOBAL_Control
0x180014caa  mov     rdi, rax
0x180014cad  test    rax, rax
0x180014cb0  jz      loc_180014F44
0x180014cb6  lea     rcx, [rbp+var_20]
0x180014cba  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180014cbf  mov     rcx, r13
0x180014cc2  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x180014cc7  mov     r9, rax
0x180014cca  lea     r8, [rbp+var_20]
0x180014cce  mov     rdx, rdi
0x180014cd1  mov     rcx, [rax]
0x180014cd4  mov     rax, [rcx+120h]
0x180014cdb  mov     rcx, r9
0x180014cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ce3  mov     esi, eax
0x180014ce5  mov     rcx, rdi; bstrString
0x180014ce8  mov     eax, 80004005h
0x180014ced  cmp     esi, 1
0x180014cf0  cmovz   esi, eax
0x180014cf3  call    cs:__imp_SysFreeString
0x180014cf9  test    esi, esi
0x180014cfb  jnz     loc_180014FAB
0x180014d01  lea     r12, WPP_GLOBAL_Control
0x180014d08  mov     esi, 8007000Eh
0x180014d0d  xor     r13d, r13d
0x180014d10  lea     rcx, [rbp+var_10]; void *
0x180014d14  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180014d19  mov     rcx, [rbp+var_20]
0x180014d1d  lea     rdx, [rbp+var_10]
0x180014d21  mov     rbx, r13
0x180014d24  mov     rax, [rcx]
0x180014d27  mov     rax, [rax+48h]
0x180014d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d30  mov     edi, eax
0x180014d32  test    eax, eax
0x180014d34  jnz     loc_180014E19
0x180014d3a  mov     rcx, [rbp+var_10]
0x180014d3e  lea     rdx, [rbp+pszSrc]
0x180014d42  mov     [rbp+pszSrc], r13
0x180014d46  mov     rax, [rcx]
0x180014d49  mov     rax, [rax+0D0h]
0x180014d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d55  mov     edi, eax
0x180014d57  test    eax, eax
0x180014d59  js      loc_180014DEB
0x180014d5f  mov     r15, [rbp+pszSrc]
0x180014d63  test    r15, r15
0x180014d66  jz      loc_180014FE4
0x180014d6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014d70  inc     rax
0x180014d73  cmp     [r15+rax*2], r13w
0x180014d78  jnz     short loc_180014D70
0x180014d7a  lea     r13, [rax+1]
0x180014d7e  lea     rcx, ds:0[r13*2]; Size
0x180014d86  call    cs:__imp_malloc
0x180014d8c  xor     ecx, ecx; pszDest
0x180014d8e  mov     r14, rax
0x180014d91  test    rax, rax
0x180014d94  jz      loc_180014FF4
0x180014d9a  mov     rdx, r13; cchDest
0x180014d9d  call    StringValidateDestW
0x180014da2  mov     edi, eax
0x180014da4  test    eax, eax
0x180014da6  js      loc_180014FFB
0x180014dac  mov     r9, r15; pszSrc
0x180014daf  mov     rcx, r14; pszDest
0x180014db2  call    StringCopyWorkerW
0x180014db7  mov     r15d, eax
0x180014dba  xor     r13d, r13d
0x180014dbd  mov     edi, r15d
0x180014dc0  test    r15d, r15d
0x180014dc3  js      loc_18001500B
0x180014dc9  xor     ecx, ecx; Block
0x180014dcb  call    cs:__imp_free
0x180014dd1  mov     rbx, r14
0x180014dd4  test    r15d, r15d
0x180014dd7  jnz     loc_180014F12
0x180014ddd  mov     r14, [rbp+arg_8]
0x180014de1  mov     rcx, [rbp+pszSrc]; bstrString
0x180014de5  call    cs:__imp_SysFreeString
0x180014deb  test    edi, edi
0x180014ded  jnz     loc_180015019
0x180014df3  lea     r8, [rbp+Block]; struct CUString *
0x180014df7  mov     [rbp+Block], r13
0x180014dfb  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180014dfe  mov     rcx, r14; pszSrc
0x180014e01  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180014e06  mov     r14, [rbp+Block]
0x180014e0a  mov     edi, eax
0x180014e0c  test    eax, eax
0x180014e0e  jns     short loc_180014E85
0x180014e10  mov     rcx, r14; Block
0x180014e13  call    cs:__imp_free
0x180014e19  mov     rcx, rbx; Block
0x180014e1c  call    cs:__imp_free
0x180014e22  lea     rcx, [rbp+var_10]
0x180014e26  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180014e2b  mov     r14, [rbp+arg_8]
0x180014e2f  test    edi, edi
0x180014e31  jz      loc_180014D10
0x180014e37  mov     rbx, [rbp+var_28]
0x180014e3b  mov     r10, cs:WPP_GLOBAL_Control
0x180014e42  mov     r15, [rbp+arg_18]
0x180014e46  mov     r13, [rbp+arg_10]
0x180014e4a  xor     r8d, r8d
0x180014e4d  test    edi, edi
0x180014e4f  js      loc_180015050
0x180014e55  mov     edi, r8d
0x180014e58  mov     rcx, rbx; Block
0x180014e5b  call    cs:__imp_free
0x180014e61  lea     rcx, [rbp+var_20]
0x180014e65  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180014e6a  mov     rcx, r13
0x180014e6d  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180014e72  mov     eax, edi
0x180014e74  add     rsp, 68h
0x180014e78  pop     r15
0x180014e7a  pop     r14
0x180014e7c  pop     r13
0x180014e7e  pop     r12
0x180014e80  pop     rdi
0x180014e81  pop     rsi
0x180014e82  pop     rbx
0x180014e83  pop     rbp
0x180014e84  retn
0x180014e85  xor     r9d, r9d; lpSecurityAttributes
0x180014e88  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x180014e8d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014e95  mov     edx, 80000000h; dwDesiredAccess
0x180014e9a  mov     rcx, r14; lpFileName
0x180014e9d  mov     dword ptr [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180014ea5  lea     r8d, [r9+3]; dwShareMode
0x180014ea9  call    cs:__imp_CreateFileW
0x180014eaf  test    rax, rax
0x180014eb2  jz      loc_180014E10
0x180014eb8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014ebc  jz      short loc_180014ECC
0x180014ebe  mov     rcx, rax; hObject
0x180014ec1  call    cs:__imp_CloseHandle
0x180014ec7  jmp     loc_180014E10
0x180014ecc  mov     rcx, cs:qword_180071C60; hModule
0x180014ed3  lea     r8, [rbp+Block]; int *
0x180014ed7  mov     edx, 0CEh; unsigned int
0x180014edc  mov     dword ptr [rbp+Block], r13d
0x180014ee0  call    ?WszLoadStringPcch@@YAPEBGPEAUHINSTANCE__@@IPEAH@Z; WszLoadStringPcch(HINSTANCE__ *,uint,int *)
0x180014ee5  mov     r8, r14
0x180014ee8  lea     rcx, [rbp+var_28]; this
0x180014eec  mov     rdx, rax; unsigned __int16 *
0x180014eef  call    ?HrPrintf@CUString@@QEAAJPEBGZZ; CUString::HrPrintf(ushort const *,...)
0x180014ef4  mov     edi, eax
0x180014ef6  mov     eax, 8004A025h
0x180014efb  test    edi, edi
0x180014efd  cmovns  edi, eax
0x180014f00  jmp     loc_180014E10
0x180014f05  test    edi, edi
0x180014f07  jns     loc_180014DF3
0x180014f0d  jmp     loc_180014E19
0x180014f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f19  cmp     rcx, r12
0x180014f1c  jz      short loc_180014F3C
0x180014f1e  test    byte ptr [rcx+1Ch], 1
0x180014f22  jz      short loc_180014F3C
0x180014f24  mov     rcx, [rcx+10h]
0x180014f28  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180014f2f  mov     edx, 0Ah
0x180014f34  mov     r9d, edi
0x180014f37  call    WPP_SF_d
0x180014f3c  xor     r13d, r13d
0x180014f3f  jmp     loc_180014DDD
0x180014f44  mov     r10, cs:WPP_GLOBAL_Control
0x180014f4b  mov     esi, 8007000Eh
0x180014f50  cmp     r10, r12
0x180014f53  jz      loc_180014FDD
0x180014f59  test    byte ptr [r10+1Ch], 1
0x180014f5e  jz      short loc_180014F87
0x180014f60  mov     rcx, [r10+10h]
0x180014f64  lea     r9, aDddDeviceDddIc; "//ddd:device/ddd:iconList/ddd:icon/ddd:"...
0x180014f6b  mov     edx, 0Eh
0x180014f70  mov     dword ptr [rsp+68h+dwCreationDisposition], esi
0x180014f74  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180014f7b  call    WPP_SF_Sd
0x180014f80  mov     r10, cs:WPP_GLOBAL_Control
0x180014f87  cmp     r10, r12
0x180014f8a  jz      short loc_180014FDD
0x180014f8c  test    byte ptr [r10+1Ch], 1
0x180014f91  jz      short loc_180014FB2
0x180014f93  mov     rcx, [r10+10h]
0x180014f97  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180014f9e  mov     edx, 0Fh
0x180014fa3  mov     r9d, esi
0x180014fa6  call    WPP_SF_d
0x180014fab  mov     r10, cs:WPP_GLOBAL_Control
0x180014fb2  cmp     r10, r12
0x180014fb5  jz      short loc_180014FDD
0x180014fb7  test    byte ptr [r10+1Ch], 1
0x180014fbc  jz      short loc_180014FDD
0x180014fbe  mov     rcx, [r10+10h]
0x180014fc2  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180014fc9  mov     edx, 10h
0x180014fce  mov     r9d, esi
0x180014fd1  call    WPP_SF_d
0x180014fd6  mov     r10, cs:WPP_GLOBAL_Control
0x180014fdd  mov     edi, esi
0x180014fdf  jmp     loc_180014E4A
0x180014fe4  xor     ecx, ecx; Block
0x180014fe6  call    cs:__imp_free
0x180014fec  mov     edi, r13d
0x180014fef  jmp     loc_180014DE1
0x180014ff4  mov     edi, esi
0x180014ff6  jmp     loc_180014F12
0x180014ffb  mov     r15d, eax
0x180014ffe  test    r13, r13
0x180015001  jz      loc_180014DBA
0x180015007  mov     [r14], cx
0x18001500b  mov     rcx, r14; Block
0x18001500e  call    cs:__imp_free
0x180015014  jmp     loc_180014F12
0x180015019  mov     rcx, cs:WPP_GLOBAL_Control
0x180015020  cmp     rcx, r12
0x180015023  jz      loc_180014F05
0x180015029  test    byte ptr [rcx+1Ch], 1
0x18001502d  jz      loc_180014F05
0x180015033  mov     rcx, [rcx+10h]
0x180015037  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x18001503e  mov     edx, 14h
0x180015043  mov     r9d, edi
0x180015046  call    WPP_SF_d
0x18001504b  jmp     loc_180014F05
0x180015050  lea     rcx, [rbp+var_28]; this
0x180015054  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x180015059  test    rax, rax
0x18001505c  jz      short loc_180015074
0x18001505e  mov     rdx, r15; unsigned __int16 **
0x180015061  lea     rcx, [rbp+var_28]; this
0x180015065  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18001506a  mov     r10, cs:WPP_GLOBAL_Control
0x180015071  xor     r8d, r8d
0x180015074  cmp     r10, r12
0x180015077  jz      loc_180014E58
0x18001507d  test    byte ptr [r10+1Ch], 1
0x180015082  jz      loc_180014E58
0x180015088  cmp     [r15], r8
0x18001508b  lea     r9, aUnspecified; "Unspecified"
0x180015092  mov     rcx, [r10+10h]
0x180015096  lea     r8, WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids
0x18001509d  cmovnz  r9, [r15]
0x1800150a1  mov     edx, 1Ch
0x1800150a6  mov     dword ptr [rsp+68h+dwCreationDisposition], edi
0x1800150aa  call    WPP_SF_Sd
0x1800150af  jmp     loc_180014E58
```
