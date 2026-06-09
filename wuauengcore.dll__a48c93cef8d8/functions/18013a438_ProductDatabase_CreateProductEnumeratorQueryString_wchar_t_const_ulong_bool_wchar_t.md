# ProductDatabase::CreateProductEnumeratorQueryString(wchar_t * const *,ulong,bool,wchar_t * *)

- ea: `0x18013a438`
- end: `0x18013a8cd`
- name: `?CreateProductEnumeratorQueryString@ProductDatabase@@YAJPEBQEA_WK_NPEAPEA_W@Z`
- size: `1173`
- prototype: `__int64 __fastcall(ProductDatabase *__hidden this, wchar_t *const *, unsigned int, bool, wchar_t **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069dbc`
- `0x18013a8d4`

## callees

- `0x18000def4`
- `0x180079340`
- `0x18007ac24`
- `0x1800b0ea4`
- `0x18010f6b4`
- `0x180113ae8`
- `0x18013a438`
- `0x18013b25c`
- `0x1801f231c`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013a654`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013a654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a887`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a89e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a89e`
- `OLEAUT32!__imp_SysAllocString` at `0x18013a76d`
- `OLEAUT32!__imp_SysAllocString` at `0x18013a76d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProductDatabase::CreateProductEnumeratorQueryString(
        ProductDatabase *this,
        wchar_t *const *a2,
        __int64 a3,
        BSTR *a4)
{
  unsigned int v5; // r12d
  ProductDatabase *v6; // rdi
  unsigned int v7; // r14d
  OLECHAR *v8; // rbx
  int WUSystemInterface; // esi
  __int64 v10; // rdx
  unsigned int v11; // r15d
  WUSystemInterfaceHelper *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  wchar_t *v15; // rbx
  __int64 v16; // rcx
  const WCHAR *v17; // r8
  void *v18; // rdi
  int v19; // eax
  BSTR v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int *lpString2; // [rsp+20h] [rbp-79h]
  wchar_t *v27; // [rsp+40h] [rbp-59h] BYREF
  OLECHAR *psz[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v29; // [rsp+58h] [rbp-41h]
  void *lpMem; // [rsp+60h] [rbp-39h] BYREF
  ProductDatabase *v31; // [rsp+68h] [rbp-31h]
  _BYTE v32[4]; // [rsp+70h] [rbp-29h] BYREF
  int v33; // [rsp+74h] [rbp-25h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-21h]
  LPVOID v35; // [rsp+80h] [rbp-19h]
  void **v36; // [rsp+88h] [rbp-11h] BYREF
  __int64 v37; // [rsp+90h] [rbp-9h]
  __int64 v38; // [rsp+98h] [rbp-1h]
  void **v39; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+Fh]
  __int64 v41; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = (unsigned int)a2;
  v6 = this;
  v31 = this;
  v7 = 0;
  v8 = 0;
  psz[0] = 0;
  psz[1] = 0;
  v29 = 0;
  if ( !a4 )
  {
    WUSystemInterface = -2147467261;
    v10 = 24;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\productdb\\ProductDB.cpp",
      (const char *)(unsigned int)WUSystemInterface,
      (int)lpString2);
    goto LABEL_64;
  }
  *a4 = 0;
  if ( !(_DWORD)a2 )
  {
LABEL_63:
    WUSystemInterface = 0;
    goto LABEL_64;
  }
  v11 = 0;
  while ( 1 )
  {
    v32[0] = 0;
    v33 = 0;
    v35 = 0;
    pv = 0;
    v36 = &CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::`vftable';
    v37 = 0;
    v38 = 0;
    v39 = &CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::`vftable';
    v40 = 0;
    v41 = 0;
    if ( !*((_QWORD *)v6 + v11) )
    {
      WUSystemInterface = -2147024809;
      v14 = 39;
      goto LABEL_56;
    }
    WUSystemInterface = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(
                          psz,
                          L"%ws=%ws",
                          L"PN");
    if ( WUSystemInterface < 0 )
    {
      v14 = 41;
      goto LABEL_56;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v12 = (WUSystemInterfaceHelper *)v35;
    if ( v35 )
    {
      CoTaskMemFree(v35);
      v35 = 0;
    }
    v13 = *((_QWORD *)v6 + v11);
    WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v12);
    if ( WUSystemInterface < 0 )
    {
      v24 = 261;
      goto LABEL_53;
    }
    lpString2 = &v33;
    WUSystemInterface = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *))(*(_QWORD *)g_WUSystemInterface
                                                                                     + 200LL))(
                          g_WUSystemInterface,
                          v13,
                          0,
                          v32);
    if ( WUSystemInterface < 0 )
    {
      v24 = 268;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)(unsigned int)WUSystemInterface,
        (int)lpString2);
      v14 = 49;
      goto LABEL_56;
    }
    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::Add(&v36, v35, (unsigned int)v33);
    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::Add(&v39, pv, (unsigned int)v33);
    if ( !v32[0] )
    {
      WUSystemInterface = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(
                            psz,
                            L"&%ws=0.0.0.0",
                            L"V");
      if ( WUSystemInterface < 0 )
      {
        v14 = 56;
LABEL_56:
        v23 = (unsigned int)WUSystemInterface;
        goto LABEL_57;
      }
      goto LABEL_32;
    }
    if ( v33 )
      break;
LABEL_31:
    v7 = 0;
LABEL_32:
    v19 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(psz, L";", 1);
    WUSystemInterface = v19;
    if ( v19 < 0 )
    {
      v23 = (unsigned int)v19;
      v14 = 87;
LABEL_57:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\productdb\\ProductDB.cpp",
        (const char *)v23,
        (int)lpString2);
      goto LABEL_58;
    }
    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&v39);
    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&v36);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v35 )
      CoTaskMemFree(v35);
    if ( ++v11 >= v5 )
    {
      v8 = psz[0];
      v20 = SysAllocString(psz[0]);
      *a4 = v20;
      if ( !v20 )
      {
        WUSystemInterface = -2147024882;
        v10 = 91;
        goto LABEL_40;
      }
      goto LABEL_63;
    }
  }
  while ( 1 )
  {
    v27 = 0;
    WUSystemInterface = EscapeAttributeForWU(*(const wchar_t **)(v40 + 8LL * v7), &v27, 0x7FFFFFFFu);
    v15 = v27;
    if ( WUSystemInterface < 0 )
    {
      v22 = 64;
      goto LABEL_47;
    }
    v16 = v37;
    v17 = *(const WCHAR **)(v37 + 8LL * v7);
    if ( v17 == L"Version" )
    {
LABEL_26:
      WUSystemInterface = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(
                            psz,
                            L"&%ws=%ws",
                            L"V");
      if ( WUSystemInterface < 0 )
      {
        v22 = 74;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\productdb\\ProductDB.cpp",
          (const char *)(unsigned int)WUSystemInterface,
          (int)lpString2);
        goto LABEL_48;
      }
      goto LABEL_27;
    }
    if ( v17 )
    {
      if ( CompareStringW(0x7Fu, 1u, v17, -1, L"Version", -1) == 2 )
        goto LABEL_26;
      v16 = v37;
    }
    lpMem = 0;
    WUSystemInterface = EscapeAttributeForWU(*(const wchar_t **)(v16 + 8LL * v7), (wchar_t **)&lpMem, 0x7FFFFFFFu);
    v15 = v27;
    v18 = lpMem;
    if ( WUSystemInterface < 0 )
      break;
    WUSystemInterface = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(
                          psz,
                          L"&%ws=%ws",
                          lpMem);
    if ( WUSystemInterface < 0 )
    {
      v21 = 82;
      goto LABEL_43;
    }
    if ( v18 )
      SusFree(v18);
LABEL_27:
    if ( v15 )
      SusFree(v15);
    if ( ++v7 >= v33 )
    {
      v6 = v31;
      goto LABEL_31;
    }
  }
  v21 = 80;
LABEL_43:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\productdb\\ProductDB.cpp",
    (const char *)(unsigned int)WUSystemInterface,
    (int)lpString2);
  if ( v18 )
    SusFree(v18);
LABEL_48:
  if ( v15 )
    SusFree(v15);
LABEL_58:
  CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&v39);
  CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&v36);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v35 )
    CoTaskMemFree(v35);
  v8 = psz[0];
LABEL_64:
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)WUSystemInterface;
}

```

## disassembly

```asm
0x18013a438  mov     [rsp-8+arg_8], rbx
0x18013a43d  push    rbp
0x18013a43e  push    rsi
0x18013a43f  push    rdi
0x18013a440  push    r12
0x18013a442  push    r13
0x18013a444  push    r14
0x18013a446  push    r15
0x18013a448  lea     rbp, [rsp-27h]
0x18013a44d  sub     rsp, 0C0h
0x18013a454  mov     rax, cs:__security_cookie
0x18013a45b  xor     rax, rsp
0x18013a45e  mov     [rbp+57h+var_38], rax
0x18013a462  mov     r13, r9
0x18013a465  mov     r12d, edx
0x18013a468  mov     rdi, rcx
0x18013a46b  mov     [rbp+57h+var_88], rcx
0x18013a46f  xorps   xmm0, xmm0
0x18013a472  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18013a476  xor     r14d, r14d
0x18013a479  mov     ebx, r14d
0x18013a47c  mov     [rbp+57h+psz], rbx
0x18013a480  mov     [rbp+57h+psz+8], r14
0x18013a484  mov     [rbp+57h+var_98], r14
0x18013a488  test    r9, r9
0x18013a48b  jnz     short loc_18013A49B
0x18013a48d  mov     esi, 80004003h
0x18013a492  lea     edx, [r9+18h]
0x18013a496  jmp     loc_18013A788
0x18013a49b  mov     [r9], r14
0x18013a49e  test    r12d, r12d
0x18013a4a1  jz      loc_18013A893
0x18013a4a7  mov     r15d, r14d
0x18013a4aa  lea     rcx, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::`vftable'
0x18013a4b1  mov     [rbp+57h+var_80], r14b
0x18013a4b5  mov     [rbp+57h+var_7C], r14d
0x18013a4b9  mov     [rbp+57h+var_70], r14
0x18013a4bd  mov     [rbp+57h+pv], r14
0x18013a4c1  xorps   xmm0, xmm0
0x18013a4c4  xor     eax, eax
0x18013a4c6  movups  [rbp+57h+var_68], xmm0
0x18013a4ca  mov     qword ptr [rbp+57h+var_68], rcx
0x18013a4ce  mov     qword ptr [rbp+57h+var_68+8], r14
0x18013a4d2  mov     [rbp+57h+var_58], rax
0x18013a4d6  movups  [rbp+57h+var_50], xmm0
0x18013a4da  mov     qword ptr [rbp+57h+var_50], rcx
0x18013a4de  mov     qword ptr [rbp+57h+var_50+8], r14
0x18013a4e2  mov     [rbp+57h+var_40], rax
0x18013a4e6  mov     ebx, r15d
0x18013a4e9  mov     r9, [rdi+rbx*8]
0x18013a4ed  test    r9, r9
0x18013a4f0  jz      loc_18013A839
0x18013a4f6  lea     r8, aPn; "PN"
0x18013a4fd  lea     rdx, aWsWs_2; "%ws=%ws"
0x18013a504  lea     rcx, [rbp+57h+psz]
0x18013a508  call    ?ConcatFormat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAAJPEB_WZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(wchar_t const *,...)
0x18013a50d  mov     esi, eax
0x18013a50f  test    eax, eax
0x18013a511  js      loc_18013A832
0x18013a517  mov     rcx, [rbp+57h+pv]; pv
0x18013a51b  test    rcx, rcx
0x18013a51e  jz      short loc_18013A52A
0x18013a520  call    cs:__imp_CoTaskMemFree
0x18013a526  mov     [rbp+57h+pv], r14
0x18013a52a  mov     rcx, [rbp+57h+var_70]; pv
0x18013a52e  test    rcx, rcx
0x18013a531  jz      short loc_18013A53D
0x18013a533  call    cs:__imp_CoTaskMemFree
0x18013a539  mov     [rbp+57h+var_70], r14
0x18013a53d  mov     rbx, [rdi+rbx*8]
0x18013a541  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18013a546  mov     esi, eax
0x18013a548  test    eax, eax
0x18013a54a  js      loc_18013A813
0x18013a550  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18013a557  mov     rax, [rcx]
0x18013a55a  lea     rdx, [rbp+57h+pv]
0x18013a55e  mov     [rsp+0F0h+var_C0], rdx
0x18013a563  lea     rdx, [rbp+57h+var_70]
0x18013a567  mov     qword ptr [rsp+0F0h+cchCount2], rdx
0x18013a56c  lea     rdx, [rbp+57h+var_7C]
0x18013a570  mov     [rsp+0F0h+lpString2], rdx; int
0x18013a575  lea     r9, [rbp+57h+var_80]
0x18013a579  xor     r8d, r8d
0x18013a57c  mov     rdx, rbx
0x18013a57f  mov     rax, [rax+0C8h]
0x18013a586  call    _guard_dispatch_icall
0x18013a58b  mov     esi, eax
0x18013a58d  test    eax, eax
0x18013a58f  js      loc_18013A80C
0x18013a595  mov     r8d, [rbp+57h+var_7C]
0x18013a599  mov     rdx, [rbp+57h+var_70]
0x18013a59d  lea     rcx, [rbp+57h+var_68]
0x18013a5a1  call    ?Add@?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@QEAAJPEBQEA_WK@Z; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::Add(wchar_t * const *,ulong)
0x18013a5a6  mov     r8d, [rbp+57h+var_7C]
0x18013a5aa  mov     rdx, [rbp+57h+pv]
0x18013a5ae  lea     rcx, [rbp+57h+var_50]
0x18013a5b2  call    ?Add@?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@QEAAJPEBQEA_WK@Z; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::Add(wchar_t * const *,ulong)
0x18013a5b7  cmp     [rbp+57h+var_80], r14b
0x18013a5bb  jnz     short loc_18013A5E8
0x18013a5bd  lea     r8, aV_0; "V"
0x18013a5c4  lea     rdx, aWs0000; "&%ws=0.0.0.0"
0x18013a5cb  lea     rcx, [rbp+57h+psz]
0x18013a5cf  call    ?ConcatFormat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAAJPEB_WZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(wchar_t const *,...)
0x18013a5d4  mov     esi, eax
0x18013a5d6  test    eax, eax
0x18013a5d8  jns     loc_18013A704
0x18013a5de  mov     edx, 38h ; '8'
0x18013a5e3  jmp     loc_18013A843
0x18013a5e8  cmp     [rbp+57h+var_7C], 0
0x18013a5ec  jbe     loc_18013A701
0x18013a5f2  mov     [rbp+57h+var_B0], 0
0x18013a5fa  mov     edi, r14d
0x18013a5fd  mov     r8d, 7FFFFFFFh; unsigned __int64
0x18013a603  lea     rdx, [rbp+57h+var_B0]; wchar_t **
0x18013a607  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x18013a60b  mov     rcx, [rcx+rdi*8]; wchar_t *
0x18013a60f  call    ?EscapeAttributeForWU@@YAJPEB_WPEAPEA_W_K@Z; EscapeAttributeForWU(wchar_t const *,wchar_t * *,unsigned __int64)
0x18013a614  mov     esi, eax
0x18013a616  mov     rbx, [rbp+57h+var_B0]
0x18013a61a  test    eax, eax
0x18013a61c  js      loc_18013A7D8
0x18013a622  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x18013a626  mov     r8, [rcx+rdi*8]; lpString1
0x18013a62a  lea     rax, aVersion_2; "Version"
0x18013a631  cmp     r8, rax
0x18013a634  jz      loc_18013A6BF
0x18013a63a  test    r8, r8
0x18013a63d  jz      short loc_18013A663
0x18013a63f  or      ecx, 0FFFFFFFFh
0x18013a642  mov     [rsp+0F0h+cchCount2], ecx; cchCount2
0x18013a646  mov     [rsp+0F0h+lpString2], rax; int
0x18013a64b  mov     r9d, ecx; cchCount1
0x18013a64e  lea     edx, [rcx+2]; dwCmpFlags
0x18013a651  lea     ecx, [rdx+7Eh]; Locale
0x18013a654  call    cs:__imp_CompareStringW
0x18013a65a  cmp     eax, 2
0x18013a65d  jz      short loc_18013A6BF
0x18013a65f  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x18013a663  mov     [rbp+57h+lpMem], 0
0x18013a66b  mov     r8d, 7FFFFFFFh; unsigned __int64
0x18013a671  lea     rdx, [rbp+57h+lpMem]; wchar_t **
0x18013a675  mov     rcx, [rcx+rdi*8]; wchar_t *
0x18013a679  call    ?EscapeAttributeForWU@@YAJPEB_WPEAPEA_W_K@Z; EscapeAttributeForWU(wchar_t const *,wchar_t * *,unsigned __int64)
0x18013a67e  mov     esi, eax
0x18013a680  mov     rbx, [rbp+57h+var_B0]
0x18013a684  mov     rdi, [rbp+57h+lpMem]
0x18013a688  test    eax, eax
0x18013a68a  js      loc_18013A7A7
0x18013a690  mov     r9, rbx
0x18013a693  mov     r8, rdi
0x18013a696  lea     rdx, aWsWs_0; "&%ws=%ws"
0x18013a69d  lea     rcx, [rbp+57h+psz]
0x18013a6a1  call    ?ConcatFormat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAAJPEB_WZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(wchar_t const *,...)
0x18013a6a6  mov     esi, eax
0x18013a6a8  test    eax, eax
0x18013a6aa  js      loc_18013A7A0
0x18013a6b0  test    rdi, rdi
0x18013a6b3  jz      short loc_18013A6E3
0x18013a6b5  mov     rcx, rdi; lpMem
0x18013a6b8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18013a6bd  jmp     short loc_18013A6E3
0x18013a6bf  mov     r9, rbx
0x18013a6c2  lea     r8, aV_0; "V"
0x18013a6c9  lea     rdx, aWsWs_0; "&%ws=%ws"
0x18013a6d0  lea     rcx, [rbp+57h+psz]
0x18013a6d4  call    ?ConcatFormat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAAJPEB_WZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::ConcatFormat(wchar_t const *,...)
0x18013a6d9  mov     esi, eax
0x18013a6db  test    eax, eax
0x18013a6dd  js      loc_18013A7D1
0x18013a6e3  test    rbx, rbx
0x18013a6e6  jz      short loc_18013A6F0
0x18013a6e8  mov     rcx, rbx; lpMem
0x18013a6eb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18013a6f0  inc     r14d
0x18013a6f3  cmp     r14d, [rbp+57h+var_7C]
0x18013a6f7  jb      loc_18013A5F2
0x18013a6fd  mov     rdi, [rbp+57h+var_88]
0x18013a701  xor     r14d, r14d
0x18013a704  mov     r8d, 1
0x18013a70a  lea     rdx, asc_18027A5D4; ";"
0x18013a711  lea     rcx, [rbp+57h+psz]
0x18013a715  call    ?_Concat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEB_W_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(wchar_t const *,unsigned __int64)
0x18013a71a  mov     esi, eax
0x18013a71c  test    eax, eax
0x18013a71e  js      loc_18013A802
0x18013a724  lea     rcx, [rbp+57h+var_50]
0x18013a728  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(void)
0x18013a72d  nop
0x18013a72e  lea     rcx, [rbp+57h+var_68]
0x18013a732  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(void)
0x18013a737  nop
0x18013a738  mov     rcx, [rbp+57h+pv]; pv
0x18013a73c  test    rcx, rcx
0x18013a73f  jz      short loc_18013A74B
0x18013a741  call    cs:__imp_CoTaskMemFree
0x18013a747  mov     [rbp+57h+pv], r14
0x18013a74b  mov     rcx, [rbp+57h+var_70]; pv
0x18013a74f  test    rcx, rcx
0x18013a752  jz      short loc_18013A75A
0x18013a754  call    cs:__imp_CoTaskMemFree
0x18013a75a  inc     r15d
0x18013a75d  cmp     r15d, r12d
0x18013a760  jb      loc_18013A4AA
0x18013a766  mov     rbx, [rbp+57h+psz]
0x18013a76a  mov     rcx, rbx; psz
0x18013a76d  call    cs:__imp_SysAllocString
0x18013a773  mov     [r13+0], rax
0x18013a777  test    rax, rax
0x18013a77a  jnz     loc_18013A893
0x18013a780  mov     esi, 8007000Eh
0x18013a785  lea     edx, [rax+5Bh]; void *
0x18013a788  lea     r8, aCW1SSrcClientL_48; "C:\\__w\\1\\s\\src\\Client\\lib\\produc"...
0x18013a78f  mov     r9d, esi; char *
0x18013a792  mov     rcx, [rbp+5Fh]; this
0x18013a796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a79b  jmp     loc_18013A896
0x18013a7a0  mov     edx, 52h ; 'R'
0x18013a7a5  jmp     short loc_18013A7AC
0x18013a7a7  mov     edx, 50h ; 'P'; void *
0x18013a7ac  mov     rcx, [rbp+5Fh]; this
0x18013a7b0  mov     r9d, esi; char *
0x18013a7b3  lea     r8, aCW1SSrcClientL_48; "C:\\__w\\1\\s\\src\\Client\\lib\\produc"...
0x18013a7ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a7bf  xor     r14d, r14d
0x18013a7c2  test    rdi, rdi
0x18013a7c5  jz      short loc_18013A7F3
0x18013a7c7  mov     rcx, rdi; lpMem
0x18013a7ca  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18013a7cf  jmp     short loc_18013A7F3
0x18013a7d1  mov     edx, 4Ah ; 'J'
0x18013a7d6  jmp     short loc_18013A7DD
0x18013a7d8  mov     edx, 40h ; '@'; void *
0x18013a7dd  mov     rcx, [rbp+5Fh]; this
0x18013a7e1  mov     r9d, esi; char *
0x18013a7e4  lea     r8, aCW1SSrcClientL_48; "C:\\__w\\1\\s\\src\\Client\\lib\\produc"...
0x18013a7eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a7f0  xor     r14d, r14d
0x18013a7f3  test    rbx, rbx
0x18013a7f6  jz      short loc_18013A857
0x18013a7f8  mov     rcx, rbx; lpMem
0x18013a7fb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18013a800  jmp     short loc_18013A857
0x18013a802  mov     r9d, eax
0x18013a805  mov     edx, 57h ; 'W'
0x18013a80a  jmp     short loc_18013A846
0x18013a80c  mov     edx, 10Ch
0x18013a811  jmp     short loc_18013A818
0x18013a813  mov     edx, 105h; void *
0x18013a818  mov     r9d, esi; char *
0x18013a81b  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18013a822  mov     rcx, [rbp+5Fh]; this
0x18013a826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a82b  mov     edx, 31h ; '1'
0x18013a830  jmp     short loc_18013A843
0x18013a832  mov     edx, 29h ; ')'
0x18013a837  jmp     short loc_18013A843
0x18013a839  mov     esi, 80070057h
0x18013a83e  mov     edx, 27h ; '''; void *
0x18013a843  mov     r9d, esi; char *
0x18013a846  mov     rcx, [rbp+5Fh]; this
0x18013a84a  lea     r8, aCW1SSrcClientL_48; "C:\\__w\\1\\s\\src\\Client\\lib\\produc"...
0x18013a851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a856  nop
0x18013a857  lea     rcx, [rbp+57h+var_50]
0x18013a85b  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(void)
0x18013a860  nop
0x18013a861  lea     rcx, [rbp+57h+var_68]
0x18013a865  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpCoTaskMemFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(void)
0x18013a86a  nop
0x18013a86b  mov     rcx, [rbp+57h+pv]; pv
0x18013a86f  test    rcx, rcx
0x18013a872  jz      short loc_18013A87E
0x18013a874  call    cs:__imp_CoTaskMemFree
0x18013a87a  mov     [rbp+57h+pv], r14
0x18013a87e  mov     rcx, [rbp+57h+var_70]; pv
0x18013a882  test    rcx, rcx
0x18013a885  jz      short loc_18013A88D
0x18013a887  call    cs:__imp_CoTaskMemFree
0x18013a88d  mov     rbx, [rbp+57h+psz]
0x18013a891  jmp     short loc_18013A896
0x18013a893  mov     esi, r14d
0x18013a896  test    rbx, rbx
0x18013a899  jz      short loc_18013A8A4
0x18013a89b  mov     rcx, rbx; hMem
0x18013a89e  call    cs:__imp_LocalFree
0x18013a8a4  mov     eax, esi
0x18013a8a6  mov     rcx, [rbp+57h+var_38]
0x18013a8aa  xor     rcx, rsp; StackCookie
0x18013a8ad  call    __security_check_cookie
0x18013a8b2  mov     rbx, [rsp+0F0h+arg_8]
0x18013a8ba  add     rsp, 0C0h
0x18013a8c1  pop     r15
0x18013a8c3  pop     r14
0x18013a8c5  pop     r13
0x18013a8c7  pop     r12
0x18013a8c9  pop     rdi
0x18013a8ca  pop     rsi
0x18013a8cb  pop     rbp
0x18013a8cc  retn
  ... truncated ...
```
