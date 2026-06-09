# CValidationManager::ValidateIconFiles(ushort const *,SmartComPtr<IXMLDOMNode>,ushort * *)

- ea: `0x180008e1c`
- end: `0x1800092c5`
- name: `?ValidateIconFiles@CValidationManager@@AEAAJPEBGV?$SmartComPtr@UIXMLDOMNode@@@@PEAPEAG@Z`
- size: `1193`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003f30`

## callees

- `0x1800056d8`
- `0x1800056f0`
- `0x180007920`
- `0x180008e1c`
- `0x1800240b0`
- `0x18002623c`
- `0x180026420`
- `0x180032220`
- `0x18003a30c`
- `0x18003a6c4`
- `0x18003a798`
- `0x18003b1cc`
- `0x180045b90`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fa1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008ff9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009008`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000904d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800091eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009219`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fa1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008ff9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009008`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000904d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800091eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009219`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f56`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800090a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800090a2`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e61`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e61`
- `OLEAUT32!__imp_SysFreeString` at `0x180008ebd`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180008ebd`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fc1`

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
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v36);
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
                StringPcch = WszLoadStringPcch(qword_180075D50, 0xCEu, (int *)&Block);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v34);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v5);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008e1c  mov     rax, rsp
0x180008e1f  mov     [rax+20h], r9
0x180008e23  mov     [rax+18h], r8
0x180008e27  mov     [rax+10h], rdx
0x180008e2b  mov     [rax+8], rcx
0x180008e2f  push    rbp
0x180008e30  push    rbx
0x180008e31  push    rsi
0x180008e32  push    rdi
0x180008e33  push    r12
0x180008e35  push    r13
0x180008e37  push    r14
0x180008e39  push    r15
0x180008e3b  mov     rbp, rsp
0x180008e3e  sub     rsp, 68h
0x180008e42  lea     rcx, [rbp+var_20]; void *
0x180008e46  mov     r15, r9
0x180008e49  mov     r13, r8
0x180008e4c  mov     r14, rdx
0x180008e4f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180008e54  xor     ebx, ebx
0x180008e56  lea     rcx, aDddDeviceDddIc; "//ddd:device/ddd:iconList/ddd:icon/ddd:"...
0x180008e5d  mov     [rbp+var_28], rbx
0x180008e61  call    cs:__imp_SysAllocString
0x180008e68  nop     dword ptr [rax+rax+00h]
0x180008e6d  lea     r12, WPP_GLOBAL_Control
0x180008e74  mov     rdi, rax
0x180008e77  test    rax, rax
0x180008e7a  jz      loc_180009149
0x180008e80  lea     rcx, [rbp+var_20]
0x180008e84  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180008e89  mov     rcx, r13
0x180008e8c  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x180008e91  mov     r9, rax
0x180008e94  lea     r8, [rbp+var_20]
0x180008e98  mov     rdx, rdi
0x180008e9b  mov     rcx, [rax]
0x180008e9e  mov     rax, [rcx+120h]
0x180008ea5  mov     rcx, r9
0x180008ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ead  mov     esi, eax
0x180008eaf  mov     rcx, rdi; bstrString
0x180008eb2  mov     eax, 80004005h
0x180008eb7  cmp     esi, 1
0x180008eba  cmovz   esi, eax
0x180008ebd  call    cs:__imp_SysFreeString
0x180008ec4  nop     dword ptr [rax+rax+00h]
0x180008ec9  test    esi, esi
0x180008ecb  jnz     loc_1800091B0
0x180008ed1  lea     r12, WPP_GLOBAL_Control
0x180008ed8  mov     esi, 8007000Eh
0x180008edd  xor     r13d, r13d
0x180008ee0  lea     rcx, [rbp+var_10]; void *
0x180008ee4  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180008ee9  mov     rcx, [rbp+var_20]
0x180008eed  lea     rdx, [rbp+var_10]
0x180008ef1  mov     rbx, r13
0x180008ef4  mov     rax, [rcx]
0x180008ef7  mov     rax, [rax+48h]
0x180008efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f00  mov     edi, eax
0x180008f02  test    eax, eax
0x180008f04  jnz     loc_180009005
0x180008f0a  mov     rcx, [rbp+var_10]
0x180008f0e  lea     rdx, [rbp+pszSrc]
0x180008f12  mov     [rbp+pszSrc], r13
0x180008f16  mov     rax, [rcx]
0x180008f19  mov     rax, [rax+0D0h]
0x180008f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f25  mov     edi, eax
0x180008f27  test    eax, eax
0x180008f29  js      loc_180008FCD
0x180008f2f  mov     r15, [rbp+pszSrc]
0x180008f33  test    r15, r15
0x180008f36  jz      loc_1800091E9
0x180008f3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f40  inc     rax
0x180008f43  cmp     [r15+rax*2], r13w
0x180008f48  jnz     short loc_180008F40
0x180008f4a  lea     r13, [rax+1]
0x180008f4e  lea     rcx, ds:0[r13*2]; Size
0x180008f56  call    cs:__imp_malloc
0x180008f5d  nop     dword ptr [rax+rax+00h]
0x180008f62  xor     ecx, ecx; pszDest
0x180008f64  mov     r14, rax
0x180008f67  test    rax, rax
0x180008f6a  jz      loc_1800091FF
0x180008f70  mov     rdx, r13; cchDest
0x180008f73  call    StringValidateDestW
0x180008f78  mov     edi, eax
0x180008f7a  test    eax, eax
0x180008f7c  js      loc_180009206
0x180008f82  mov     r9, r15; pszSrc
0x180008f85  mov     rcx, r14; pszDest
0x180008f88  call    StringCopyWorkerW
0x180008f8d  mov     r15d, eax
0x180008f90  xor     r13d, r13d
0x180008f93  mov     edi, r15d
0x180008f96  test    r15d, r15d
0x180008f99  js      loc_180009216
0x180008f9f  xor     ecx, ecx; Block
0x180008fa1  call    cs:__imp_free
0x180008fa8  nop     dword ptr [rax+rax+00h]
0x180008fad  mov     rbx, r14
0x180008fb0  test    r15d, r15d
0x180008fb3  jnz     loc_180009117
0x180008fb9  mov     r14, [rbp+arg_8]
0x180008fbd  mov     rcx, [rbp+pszSrc]; bstrString
0x180008fc1  call    cs:__imp_SysFreeString
0x180008fc8  nop     dword ptr [rax+rax+00h]
0x180008fcd  test    edi, edi
0x180008fcf  jnz     loc_18000922A
0x180008fd5  lea     r8, [rbp+Block]; struct CUString *
0x180008fd9  mov     [rbp+Block], r13
0x180008fdd  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180008fe0  mov     rcx, r14; pszSrc
0x180008fe3  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180008fe8  mov     r14, [rbp+Block]
0x180008fec  mov     edi, eax
0x180008fee  test    eax, eax
0x180008ff0  jns     loc_18000907E
0x180008ff6  mov     rcx, r14; Block
0x180008ff9  call    cs:__imp_free
0x180009000  nop     dword ptr [rax+rax+00h]
0x180009005  mov     rcx, rbx; Block
0x180009008  call    cs:__imp_free
0x18000900f  nop     dword ptr [rax+rax+00h]
0x180009014  lea     rcx, [rbp+var_10]
0x180009018  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000901d  mov     r14, [rbp+arg_8]
0x180009021  test    edi, edi
0x180009023  jz      loc_180008EE0
0x180009029  mov     rbx, [rbp+var_28]
0x18000902d  mov     r10, cs:WPP_GLOBAL_Control
0x180009034  mov     r15, [rbp+arg_18]
0x180009038  mov     r13, [rbp+arg_10]
0x18000903c  xor     r8d, r8d
0x18000903f  test    edi, edi
0x180009041  js      loc_180009261
0x180009047  mov     edi, r8d
0x18000904a  mov     rcx, rbx; Block
0x18000904d  call    cs:__imp_free
0x180009054  nop     dword ptr [rax+rax+00h]
0x180009059  lea     rcx, [rbp+var_20]
0x18000905d  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180009062  mov     rcx, r13
0x180009065  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000906a  mov     eax, edi
0x18000906c  add     rsp, 68h
0x180009070  pop     r15
0x180009072  pop     r14
0x180009074  pop     r13
0x180009076  pop     r12
0x180009078  pop     rdi
0x180009079  pop     rsi
0x18000907a  pop     rbx
0x18000907b  pop     rbp
0x18000907c  retn
0x18000907e  xor     r9d, r9d; lpSecurityAttributes
0x180009081  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x180009086  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000908e  mov     edx, 80000000h; dwDesiredAccess
0x180009093  mov     rcx, r14; lpFileName
0x180009096  mov     dword ptr [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000909e  lea     r8d, [r9+3]; dwShareMode
0x1800090a2  call    cs:__imp_CreateFileW
0x1800090a9  nop     dword ptr [rax+rax+00h]
0x1800090ae  test    rax, rax
0x1800090b1  jz      loc_180008FF6
0x1800090b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800090bb  jz      short loc_1800090D1
0x1800090bd  mov     rcx, rax; hObject
0x1800090c0  call    cs:__imp_CloseHandle
0x1800090c7  nop     dword ptr [rax+rax+00h]
0x1800090cc  jmp     loc_180008FF6
0x1800090d1  mov     rcx, cs:qword_180075D50; hModule
0x1800090d8  lea     r8, [rbp+Block]; int *
0x1800090dc  mov     edx, 0CEh; unsigned int
0x1800090e1  mov     dword ptr [rbp+Block], r13d
0x1800090e5  call    ?WszLoadStringPcch@@YAPEBGPEAUHINSTANCE__@@IPEAH@Z; WszLoadStringPcch(HINSTANCE__ *,uint,int *)
0x1800090ea  mov     r8, r14
0x1800090ed  lea     rcx, [rbp+var_28]; this
0x1800090f1  mov     rdx, rax; unsigned __int16 *
0x1800090f4  call    ?HrPrintf@CUString@@QEAAJPEBGZZ; CUString::HrPrintf(ushort const *,...)
0x1800090f9  mov     edi, eax
0x1800090fb  mov     eax, 8004A025h
0x180009100  test    edi, edi
0x180009102  cmovns  edi, eax
0x180009105  jmp     loc_180008FF6
0x18000910a  test    edi, edi
0x18000910c  jns     loc_180008FD5
0x180009112  jmp     loc_180009005
0x180009117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000911e  cmp     rcx, r12
0x180009121  jz      short loc_180009141
0x180009123  test    byte ptr [rcx+1Ch], 1
0x180009127  jz      short loc_180009141
0x180009129  mov     rcx, [rcx+10h]
0x18000912d  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180009134  mov     edx, 0Ah
0x180009139  mov     r9d, edi
0x18000913c  call    WPP_SF_d
0x180009141  xor     r13d, r13d
0x180009144  jmp     loc_180008FB9
0x180009149  mov     r10, cs:WPP_GLOBAL_Control
0x180009150  mov     esi, 8007000Eh
0x180009155  cmp     r10, r12
0x180009158  jz      loc_1800091E2
0x18000915e  test    byte ptr [r10+1Ch], 1
0x180009163  jz      short loc_18000918C
0x180009165  mov     rcx, [r10+10h]
0x180009169  lea     r9, aDddDeviceDddIc; "//ddd:device/ddd:iconList/ddd:icon/ddd:"...
0x180009170  mov     edx, 0Eh
0x180009175  mov     dword ptr [rsp+68h+dwCreationDisposition], esi
0x180009179  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180009180  call    WPP_SF_Sd
0x180009185  mov     r10, cs:WPP_GLOBAL_Control
0x18000918c  cmp     r10, r12
0x18000918f  jz      short loc_1800091E2
0x180009191  test    byte ptr [r10+1Ch], 1
0x180009196  jz      short loc_1800091B7
0x180009198  mov     rcx, [r10+10h]
0x18000919c  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x1800091a3  mov     edx, 0Fh
0x1800091a8  mov     r9d, esi
0x1800091ab  call    WPP_SF_d
0x1800091b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800091b7  cmp     r10, r12
0x1800091ba  jz      short loc_1800091E2
0x1800091bc  test    byte ptr [r10+1Ch], 1
0x1800091c1  jz      short loc_1800091E2
0x1800091c3  mov     rcx, [r10+10h]
0x1800091c7  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x1800091ce  mov     edx, 10h
0x1800091d3  mov     r9d, esi
0x1800091d6  call    WPP_SF_d
0x1800091db  mov     r10, cs:WPP_GLOBAL_Control
0x1800091e2  mov     edi, esi
0x1800091e4  jmp     loc_18000903C
0x1800091e9  xor     ecx, ecx; Block
0x1800091eb  call    cs:__imp_free
0x1800091f2  nop     dword ptr [rax+rax+00h]
0x1800091f7  mov     edi, r13d
0x1800091fa  jmp     loc_180008FBD
0x1800091ff  mov     edi, esi
0x180009201  jmp     loc_180009117
0x180009206  mov     r15d, eax
0x180009209  test    r13, r13
0x18000920c  jz      loc_180008F90
0x180009212  mov     [r14], cx
0x180009216  mov     rcx, r14; Block
0x180009219  call    cs:__imp_free
0x180009220  nop     dword ptr [rax+rax+00h]
0x180009225  jmp     loc_180009117
0x18000922a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009231  cmp     rcx, r12
0x180009234  jz      loc_18000910A
0x18000923a  test    byte ptr [rcx+1Ch], 1
0x18000923e  jz      loc_18000910A
0x180009244  mov     rcx, [rcx+10h]
0x180009248  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x18000924f  mov     edx, 14h
0x180009254  mov     r9d, edi
0x180009257  call    WPP_SF_d
0x18000925c  jmp     loc_18000910A
0x180009261  lea     rcx, [rbp+var_28]; this
0x180009265  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x18000926a  test    rax, rax
0x18000926d  jz      short loc_180009285
0x18000926f  mov     rdx, r15; unsigned __int16 **
0x180009272  lea     rcx, [rbp+var_28]; this
0x180009276  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18000927b  mov     r10, cs:WPP_GLOBAL_Control
0x180009282  xor     r8d, r8d
0x180009285  cmp     r10, r12
0x180009288  jz      loc_18000904A
0x18000928e  test    byte ptr [r10+1Ch], 1
0x180009293  jz      loc_18000904A
0x180009299  cmp     [r15], r8
0x18000929c  lea     r9, aUnspecified; "Unspecified"
0x1800092a3  mov     rcx, [r10+10h]
0x1800092a7  lea     r8, WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids
0x1800092ae  cmovnz  r9, [r15]
0x1800092b2  mov     edx, 1Ch
0x1800092b7  mov     dword ptr [rsp+68h+dwCreationDisposition], edi
0x1800092bb  call    WPP_SF_Sd
0x1800092c0  jmp     loc_18000904A
```
