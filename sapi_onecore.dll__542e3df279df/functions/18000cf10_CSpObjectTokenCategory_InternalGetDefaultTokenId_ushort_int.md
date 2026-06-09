# CSpObjectTokenCategory::InternalGetDefaultTokenId(ushort * *,int)

- ea: `0x18000cf10`
- end: `0x18000d6cf`
- name: `?InternalGetDefaultTokenId@CSpObjectTokenCategory@@AEAAJPEAPEAGH@Z`
- size: `1983`
- prototype: `__int64 __fastcall(CSpObjectTokenCategory *__hidden this, unsigned __int16 **, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800eda20`
- `0x1800edad4`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000cf10`
- `0x18000e518`
- `0x18000f080`
- `0x180019a50`
- `0x18003cdc0`
- `0x180079e30`
- `0x1800ed474`
- `0x1800edad4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d03b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d3be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d646`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d03b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d3be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d638`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d300`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d682`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18000d457`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18000d457`

## string_xrefs

- `0x18000cf95`: `DefaultTokenId`
- `0x18000d098`: `DefaultTokenId`
- `0x18000d5f8`: `DefaultTokenId`
- `0x18000d0f0`: `DefaultDefaultTokenId`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CSpObjectTokenCategory::InternalGetDefaultTokenId(
        CSpObjectTokenCategory *this,
        unsigned __int16 **a2,
        int a3)
{
  CSpObjectTokenCategory *v4; // rsi
  __int64 v5; // rcx
  HRESULT Instance; // r14d
  struct IUnknown *v7; // rbx
  __int64 v8; // r15
  int v9; // eax
  struct IUnknown *v10; // rcx
  LPCVOID v11; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v13; // rcx
  unsigned __int64 v14; // rcx
  _WORD *v15; // rdi
  LPCVOID v16; // rdi
  int v17; // eax
  LPCVOID v18; // r12
  int v19; // eax
  int TokenFromId; // ecx
  struct ISpObjectToken *v21; // rdi
  struct IEnumSpObjectTokens *v22; // rax
  int v23; // esi
  int v24; // eax
  int v25; // edi
  struct IEnumSpObjectTokens *v26; // rsi
  struct IEnumSpObjectTokens *v27; // rdi
  struct IUnknown *v28; // rcx
  LPCVOID v29; // rdi
  HANDLE v30; // rax
  SIZE_T v31; // rax
  SIZE_T v32; // rax
  __int64 v33; // rcx
  _WORD *v34; // rdi
  unsigned __int16 *v35; // r12
  LANGID UserDefaultUILanguage; // ax
  int v37; // eax
  HANDLE v38; // rax
  SIZE_T v39; // rax
  unsigned __int64 v40; // rax
  _WORD *v41; // rdi
  __int64 i; // rcx
  struct IUnknown *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPCVOID v45; // [rsp+38h] [rbp-C8h] BYREF
  LPCVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  struct IEnumSpObjectTokens *v47; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+54h] [rbp-ACh] BYREF
  int v50; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+5Ch] [rbp-A4h]
  struct IEnumSpObjectTokens *v52; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v53; // [rsp+68h] [rbp-98h]
  CSpObjectTokenCategory *v54; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v55; // [rsp+78h] [rbp-88h]
  unsigned __int16 v56[264]; // [rsp+80h] [rbp-80h] BYREF

  v55 = a2;
  v4 = this;
  v54 = this;
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    Instance = -2147467261;
    if ( a2 )
      Instance = 0;
  }
  else
  {
    Instance = -2147201023;
  }
  v7 = 0;
  v53 = 0;
  v8 = 8;
  if ( Instance >= 0 )
  {
    lpMem = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCVOID *))(*(_QWORD *)v5 + 48LL))(
           v5,
           L"DefaultTokenId",
           &lpMem);
    Instance = v9;
    if ( v9 < 0 )
    {
      if ( v9 == -2147200966 )
      {
        ppv = 0;
        Instance = (*(__int64 (__fastcall **)(CSpObjectTokenCategory *, __int64, struct IUnknown **))(*(_QWORD *)v4 + 136LL))(
                     v4,
                     1,
                     &ppv);
        if ( Instance < 0 )
        {
          v10 = ppv;
        }
        else
        {
          v7 = ppv;
          v10 = 0;
          ppv = 0;
          v53 = v7;
          Instance = 0;
        }
        if ( v10 )
          ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      }
    }
    else
    {
      v7 = (struct IUnknown *)*((_QWORD *)v4 + 9);
      v53 = v7;
      ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->AddRef)(v7);
    }
    v11 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      v13 = HeapSize(ProcessHeap, 0, v11);
      if ( v13 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
      {
        v14 = (v13 >> 1) - 1;
        if ( v14 >= 8 )
        {
          v14 = 8;
          goto LABEL_19;
        }
        if ( v14 )
        {
LABEL_19:
          v15 = lpMem;
          while ( v14 )
          {
            *v15++ = -8531;
            --v14;
          }
        }
      }
      CoTaskMemFree((LPVOID)lpMem);
    }
  }
  v16 = 0;
  v45 = 0;
  if ( Instance < 0 )
    goto LABEL_104;
  v17 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, LPCVOID *))v7->lpVtbl[2].QueryInterface)(
          v7,
          L"DefaultTokenId",
          &v45);
  Instance = v17;
  if ( v17 != -2147200966 && v17 < 0 )
    goto LABEL_103;
  v51 = 0;
  v18 = v45;
  if ( v45 )
    goto LABEL_52;
  v51 = 1;
  v47 = 0;
  v19 = (*(__int64 (__fastcall **)(CSpObjectTokenCategory *, const wchar_t *, struct IEnumSpObjectTokens **))(*(_QWORD *)v4 + 48LL))(
          v4,
          L"DefaultDefaultTokenId",
          &v47);
  TokenFromId = 0;
  if ( v19 != -2147200966 )
    TokenFromId = v19;
  v21 = 0;
  ppv = 0;
  v22 = v47;
  if ( !v47 )
  {
LABEL_33:
    if ( TokenFromId < 0 )
      goto LABEL_51;
    goto LABEL_34;
  }
  TokenFromId = SpGetTokenFromId((const unsigned __int16 *)v47, (struct ISpObjectToken **)&ppv, 0);
  if ( TokenFromId != -2147200966 )
  {
    v22 = v47;
    v21 = (struct ISpObjectToken *)ppv;
    goto LABEL_33;
  }
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v47);
  v22 = v47;
  v21 = (struct ISpObjectToken *)ppv;
LABEL_34:
  if ( v22 && v21 )
  {
    v52 = 0;
    v23 = CSpObjectTokenCategory::InternalEnumTokens(v4, 0, 0, &v52, 0);
    while ( v23 >= 0 )
    {
      lpMem = 0;
      v24 = ((__int64 (__fastcall *)(struct IEnumSpObjectTokens *, __int64, LPCVOID *, _QWORD))v52->lpVtbl->Next)(
              v52,
              1,
              &lpMem,
              0);
      v23 = v24;
      if ( v24 == 1 )
      {
        ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&lpMem);
        break;
      }
      v48 = 0;
      if ( v24 >= 0 )
      {
        v23 = (*(__int64 (__fastcall **)(LPCVOID, const wchar_t *, int *))(*(_QWORD *)lpMem + 192LL))(
                lpMem,
                L"VersionDefault",
                &v48);
        if ( v23 >= 0 )
        {
          if ( v48 )
          {
            v50 = 0;
            v49 = 0;
            v23 = CompareTokenVersions((struct ISpObjectToken *)lpMem, v21, &v50, &v49);
            if ( v23 >= 0 && v49 && v50 > 0 )
            {
              if ( v21 != lpMem )
              {
                ATL::AtlComPtrAssign(&ppv, (struct IUnknown *)lpMem);
                v21 = (struct ISpObjectToken *)ppv;
              }
              SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v47);
              v23 = ((__int64 (__fastcall *)(struct ISpObjectToken *, struct IEnumSpObjectTokens **))v21->lpVtbl->GetId)(
                      v21,
                      &v47);
            }
          }
        }
      }
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&lpMem);
    }
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v52);
    v4 = v54;
  }
LABEL_51:
  CSpDynamicString::operator=(&v45, &v47);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v47);
  v18 = v45;
  v25 = v51;
  if ( !v45 )
  {
LABEL_79:
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    StringCchPrintfW(v56, 0x104u, L"Language=%x;VendorPreferred", UserDefaultUILanguage);
    v47 = 0;
    Instance = CSpObjectTokenCategory::InternalEnumTokens(v4, 0, v56, &v47, 0);
    lpMem = 0;
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct IEnumSpObjectTokens *, __int64, LPCVOID *, _QWORD))v47->lpVtbl->Next)(
                   v47,
                   1,
                   &lpMem,
                   0);
      if ( Instance == 1 )
        Instance = -2147200966;
    }
    while ( Instance >= 0 )
    {
      ppv = 0;
      v37 = ((__int64 (__fastcall *)(struct IEnumSpObjectTokens *, __int64, struct IUnknown **, _QWORD))v47->lpVtbl->Next)(
              v47,
              1,
              &ppv,
              0);
      Instance = v37;
      if ( v37 == 1 )
      {
        Instance = 0;
        ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
        break;
      }
      v50 = 0;
      if ( v37 >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, int *))ppv->lpVtbl[8].QueryInterface)(
                     ppv,
                     L"VersionDefault",
                     &v50);
        if ( Instance >= 0 )
        {
          if ( v50 )
          {
            v49 = 0;
            v48 = 0;
            Instance = CompareTokenVersions((struct ISpObjectToken *)ppv, (struct ISpObjectToken *)lpMem, &v48, &v49);
            if ( Instance >= 0 && v49 && v48 > 0 && lpMem != ppv )
              ATL::AtlComPtrAssign((struct IUnknown **)&lpMem, ppv);
          }
        }
      }
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
    }
    if ( lpMem )
      Instance = (*(__int64 (__fastcall **)(LPCVOID, LPCVOID *))(*(_QWORD *)lpMem + 128LL))(lpMem, &v45);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&lpMem);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v47);
    if ( Instance < 0 )
      goto LABEL_103;
    v35 = (unsigned __int16 *)v45;
    goto LABEL_98;
  }
LABEL_52:
  v26 = 0;
  v52 = 0;
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_SpObjectToken,
               0,
               0x17u,
               &GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0,
               (LPVOID *)&ppv);
  v27 = 0;
  if ( Instance < 0
    || (Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, LPCVOID, _QWORD))ppv->lpVtbl[5].QueryInterface)(
                     ppv,
                     0,
                     v18,
                     0),
        Instance < 0) )
  {
    v28 = ppv;
  }
  else
  {
    v26 = (struct IEnumSpObjectTokens *)ppv;
    v28 = 0;
    ppv = 0;
    v52 = v26;
    v27 = v26;
  }
  if ( v28 )
    ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
  if ( Instance == -2147200966 || (unsigned int)(Instance + 2147200960) <= 1 )
  {
    v51 = 1;
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v45);
    Instance = 0;
  }
  else if ( Instance < 0 )
  {
    goto LABEL_75;
  }
  if ( v27 && a3 )
  {
    v29 = v45;
    if ( !v45 )
    {
LABEL_74:
      v27 = v26;
      Instance = ((__int64 (__fastcall *)(struct IEnumSpObjectTokens *, LPCVOID *))v26->lpVtbl[1].Item)(v26, &v45);
      goto LABEL_75;
    }
    v30 = GetProcessHeap();
    v31 = HeapSize(v30, 0, v29);
    if ( v31 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v32 = v31 >> 1;
      v33 = v32 - 1;
      if ( v32 - 1 >= 8 )
      {
        v33 = 8;
        goto LABEL_70;
      }
      if ( v32 != 1 )
      {
LABEL_70:
        v34 = v45;
        while ( v33 )
        {
          *v34++ = -8531;
          --v33;
        }
      }
    }
    CoTaskMemFree((LPVOID)v45);
    v45 = 0;
    goto LABEL_74;
  }
LABEL_75:
  if ( v27 )
    ((void (__fastcall *)(struct IEnumSpObjectTokens *))v26->lpVtbl->Release)(v26);
  if ( Instance < 0 )
    goto LABEL_103;
  v35 = (unsigned __int16 *)v45;
  v4 = v54;
  v25 = v51;
  if ( !v45 )
    goto LABEL_79;
LABEL_98:
  if ( !v25 || !v35 )
    goto LABEL_102;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, unsigned __int16 *))v7->lpVtbl[1].Release)(
               v7,
               L"DefaultTokenId",
               v35);
  if ( Instance >= 0 )
  {
    v35 = (unsigned __int16 *)v45;
LABEL_102:
    v16 = 0;
    v45 = 0;
    *v55 = v35;
    goto LABEL_104;
  }
LABEL_103:
  v16 = v45;
LABEL_104:
  if ( v16 )
  {
    v38 = GetProcessHeap();
    v39 = HeapSize(v38, 0, v16);
    if ( v39 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v40 = (v39 >> 1) - 1;
      if ( v40 >= 8 || (v8 = v40) != 0 )
      {
        v41 = v45;
        for ( i = v8; i; --i )
          *v41++ = -8531;
      }
    }
    CoTaskMemFree((LPVOID)v45);
    v45 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000cf10  mov     [rsp-8+arg_10], rbx
0x18000cf15  push    rbp
0x18000cf16  push    rsi
0x18000cf17  push    rdi
0x18000cf18  push    r12
0x18000cf1a  push    r13
0x18000cf1c  push    r14
0x18000cf1e  push    r15
0x18000cf20  lea     rbp, [rsp-1A0h]
0x18000cf28  sub     rsp, 2A0h
0x18000cf2f  mov     rax, cs:__security_cookie
0x18000cf36  xor     rax, rsp
0x18000cf39  mov     [rbp+1D0h+var_40], rax
0x18000cf40  mov     r13d, r8d
0x18000cf43  mov     [rsp+2D0h+var_258], rdx
0x18000cf48  mov     rsi, rcx
0x18000cf4b  mov     [rsp+2D0h+var_260], rcx
0x18000cf50  mov     rcx, [rcx+48h]
0x18000cf54  xor     r12d, r12d
0x18000cf57  test    rcx, rcx
0x18000cf5a  jnz     short loc_18000CF64
0x18000cf5c  mov     r14d, 80045001h
0x18000cf62  jmp     short loc_18000CF71
0x18000cf64  mov     r14d, 80004003h
0x18000cf6a  test    rdx, rdx
0x18000cf6d  cmovnz  r14d, r12d
0x18000cf71  mov     rbx, r12
0x18000cf74  mov     [rsp+2D0h+var_268], rbx
0x18000cf79  mov     r15d, 8
0x18000cf7f  test    r14d, r14d
0x18000cf82  js      loc_18000D07F
0x18000cf88  mov     [rsp+2D0h+lpMem], r12
0x18000cf8d  mov     rax, [rcx]
0x18000cf90  lea     r8, [rsp+2D0h+lpMem]
0x18000cf95  lea     rdx, aDefaulttokenid; "DefaultTokenId"
0x18000cf9c  mov     rax, [rax+30h]
0x18000cfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa5  mov     r14d, eax
0x18000cfa8  test    eax, eax
0x18000cfaa  js      short loc_18000CFC6
0x18000cfac  mov     rbx, [rsi+48h]
0x18000cfb0  mov     [rsp+2D0h+var_268], rbx
0x18000cfb5  mov     rax, [rbx]
0x18000cfb8  mov     rcx, rbx
0x18000cfbb  mov     rax, [rax+8]
0x18000cfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc4  jmp     short loc_18000D023
0x18000cfc6  cmp     eax, 8004503Ah
0x18000cfcb  jnz     short loc_18000D023
0x18000cfcd  mov     [rsp+2D0h+var_2A0], r12
0x18000cfd2  mov     rax, [rsi]
0x18000cfd5  lea     r8, [rsp+2D0h+var_2A0]
0x18000cfda  mov     edx, 1
0x18000cfdf  mov     rcx, rsi
0x18000cfe2  mov     rax, [rax+88h]
0x18000cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfee  mov     r14d, eax
0x18000cff1  test    eax, eax
0x18000cff3  js      short loc_18000D00C
0x18000cff5  mov     rbx, [rsp+2D0h+var_2A0]
0x18000cffa  mov     rcx, r12
0x18000cffd  mov     [rsp+2D0h+var_2A0], rcx
0x18000d002  mov     [rsp+2D0h+var_268], rbx
0x18000d007  mov     r14d, r12d
0x18000d00a  jmp     short loc_18000D011
0x18000d00c  mov     rcx, [rsp+2D0h+var_2A0]
0x18000d011  test    rcx, rcx
0x18000d014  jz      short loc_18000D023
0x18000d016  mov     rax, [rcx]
0x18000d019  mov     rax, [rax+10h]
0x18000d01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d022  nop
0x18000d023  mov     rdi, [rsp+2D0h+lpMem]
0x18000d028  test    rdi, rdi
0x18000d02b  jz      short loc_18000D07F
0x18000d02d  call    cs:__imp_GetProcessHeap
0x18000d033  mov     r8, rdi; lpMem
0x18000d036  xor     edx, edx; dwFlags
0x18000d038  mov     rcx, rax; hHeap
0x18000d03b  call    cs:__imp_HeapSize
0x18000d041  mov     rcx, rax
0x18000d044  add     rax, 0FFFFFFFFFFFFFFFDh
0x18000d048  cmp     rax, 0FFFFFFFFFFFFFFFBh
0x18000d04c  ja      short loc_18000D074
0x18000d04e  shr     rcx, 1
0x18000d051  dec     rcx
0x18000d054  cmp     rcx, 8
0x18000d058  jb      short loc_18000D05F
0x18000d05a  mov     rcx, r15
0x18000d05d  jmp     short loc_18000D064
0x18000d05f  test    rcx, rcx
0x18000d062  jz      short loc_18000D074
0x18000d064  mov     eax, 0DEADh
0x18000d069  movzx   eax, ax
0x18000d06c  mov     rdi, [rsp+2D0h+lpMem]
0x18000d071  rep stosw
0x18000d074  mov     rcx, [rsp+2D0h+lpMem]; pv
0x18000d079  call    cs:__imp_CoTaskMemFree
0x18000d07f  mov     rdi, r12
0x18000d082  mov     [rsp+2D0h+var_298], r12
0x18000d087  test    r14d, r14d
0x18000d08a  js      loc_18000D633
0x18000d090  mov     rax, [rbx]
0x18000d093  lea     r8, [rsp+2D0h+var_298]
0x18000d098  lea     rdx, aDefaulttokenid; "DefaultTokenId"
0x18000d09f  mov     rcx, rbx
0x18000d0a2  mov     rax, [rax+30h]
0x18000d0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ab  mov     r14d, eax
0x18000d0ae  cmp     eax, 8004503Ah
0x18000d0b3  jnz     short loc_18000D0BA
0x18000d0b5  mov     r14d, r12d
0x18000d0b8  jmp     short loc_18000D0C2
0x18000d0ba  test    eax, eax
0x18000d0bc  js      loc_18000D62E
0x18000d0c2  mov     edi, r12d
0x18000d0c5  mov     [rsp+2D0h+var_274], r12d
0x18000d0ca  mov     r12, [rsp+2D0h+var_298]
0x18000d0cf  test    r12, r12
0x18000d0d2  jnz     loc_18000D2D4
0x18000d0d8  mov     [rsp+2D0h+var_274], 1
0x18000d0e0  xor     r14d, r14d
0x18000d0e3  mov     [rsp+2D0h+var_288], r14
0x18000d0e8  mov     rax, [rsi]
0x18000d0eb  lea     r8, [rsp+2D0h+var_288]
0x18000d0f0  lea     rdx, aDefaultdefault_0; "DefaultDefaultTokenId"
0x18000d0f7  mov     rcx, rsi
0x18000d0fa  mov     rax, [rax+30h]
0x18000d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d103  mov     ecx, r14d
0x18000d106  mov     r12d, 8004503Ah
0x18000d10c  cmp     eax, r12d
0x18000d10f  cmovnz  ecx, eax
0x18000d112  mov     edi, r14d
0x18000d115  mov     [rsp+2D0h+var_2A0], r14
0x18000d11a  mov     rax, [rsp+2D0h+var_288]
0x18000d11f  test    rax, rax
0x18000d122  jz      short loc_18000D15B
0x18000d124  xor     r8d, r8d; int
0x18000d127  lea     rdx, [rsp+2D0h+var_2A0]; struct ISpObjectToken **
0x18000d12c  mov     rcx, rax; unsigned __int16 *
0x18000d12f  call    ?SpGetTokenFromId@@YAJPEBGPEAPEAUISpObjectToken@@H@Z; SpGetTokenFromId(ushort const *,ISpObjectToken * *,int)
0x18000d134  mov     ecx, eax
0x18000d136  cmp     eax, r12d
0x18000d139  jnz     short loc_18000D151
0x18000d13b  lea     rcx, [rsp+2D0h+var_288]; this
0x18000d140  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18000d145  mov     rax, [rsp+2D0h+var_288]
0x18000d14a  mov     rdi, [rsp+2D0h+var_2A0]
0x18000d14f  jmp     short loc_18000D163
0x18000d151  mov     rax, [rsp+2D0h+var_288]
0x18000d156  mov     rdi, [rsp+2D0h+var_2A0]
0x18000d15b  test    ecx, ecx
0x18000d15d  js      loc_18000D29D
0x18000d163  test    rax, rax
0x18000d166  jz      loc_18000D29D
0x18000d16c  test    rdi, rdi
0x18000d16f  jz      loc_18000D29D
0x18000d175  mov     [rsp+2D0h+var_270], r14
0x18000d17a  mov     dword ptr [rsp+2D0h+ppv], r14d; int
0x18000d17f  lea     r9, [rsp+2D0h+var_270]; struct IEnumSpObjectTokens **
0x18000d184  xor     r8d, r8d; unsigned __int16 *
0x18000d187  xor     edx, edx; unsigned __int16 *
0x18000d189  mov     rcx, rsi; this
0x18000d18c  call    ?InternalEnumTokens@CSpObjectTokenCategory@@AEAAJPEBG0PEAPEAUIEnumSpObjectTokens@@H@Z; CSpObjectTokenCategory::InternalEnumTokens(ushort const *,ushort const *,IEnumSpObjectTokens * *,int)
0x18000d191  mov     esi, eax
0x18000d193  test    esi, esi
0x18000d195  js      loc_18000D28E
0x18000d19b  mov     [rsp+2D0h+lpMem], r14
0x18000d1a0  mov     rcx, [rsp+2D0h+var_270]
0x18000d1a5  mov     rax, [rcx]
0x18000d1a8  xor     r9d, r9d
0x18000d1ab  lea     r8, [rsp+2D0h+lpMem]
0x18000d1b0  mov     edx, 1
0x18000d1b5  mov     rax, [rax+18h]
0x18000d1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1be  mov     esi, eax
0x18000d1c0  cmp     eax, 1
0x18000d1c3  jz      loc_18000D283
0x18000d1c9  mov     [rsp+2D0h+var_280], r14d
0x18000d1ce  test    eax, eax
0x18000d1d0  js      loc_18000D274
0x18000d1d6  mov     rcx, [rsp+2D0h+lpMem]
0x18000d1db  mov     rax, [rcx]
0x18000d1de  lea     r8, [rsp+2D0h+var_280]
0x18000d1e3  lea     rdx, aVersiondefault; "VersionDefault"
0x18000d1ea  mov     rax, [rax+0C0h]
0x18000d1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f6  mov     esi, eax
0x18000d1f8  test    eax, eax
0x18000d1fa  js      short loc_18000D274
0x18000d1fc  cmp     [rsp+2D0h+var_280], 0
0x18000d201  jz      short loc_18000D274
0x18000d203  mov     [rsp+2D0h+var_278], r14d
0x18000d208  mov     [rsp+2D0h+var_27C], r14d
0x18000d20d  lea     r9, [rsp+2D0h+var_27C]; int *
0x18000d212  lea     r8, [rsp+2D0h+var_278]; int *
0x18000d217  mov     rdx, rdi; struct ISpObjectToken *
0x18000d21a  mov     rcx, [rsp+2D0h+lpMem]; struct ISpObjectToken *
0x18000d21f  call    ?CompareTokenVersions@@YAJPEAUISpObjectToken@@0PEAJPEAH@Z; CompareTokenVersions(ISpObjectToken *,ISpObjectToken *,long *,int *)
0x18000d224  mov     esi, eax
0x18000d226  test    eax, eax
0x18000d228  js      short loc_18000D274
0x18000d22a  cmp     [rsp+2D0h+var_27C], 0
0x18000d22f  jz      short loc_18000D274
0x18000d231  cmp     [rsp+2D0h+var_278], 0
0x18000d236  jle     short loc_18000D274
0x18000d238  mov     rdx, [rsp+2D0h+lpMem]; struct IUnknown *
0x18000d23d  cmp     rdi, rdx
0x18000d240  jz      short loc_18000D251
0x18000d242  lea     rcx, [rsp+2D0h+var_2A0]; struct IUnknown **
0x18000d247  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000d24c  mov     rdi, [rsp+2D0h+var_2A0]
0x18000d251  lea     rcx, [rsp+2D0h+var_288]; this
0x18000d256  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18000d25b  mov     rax, [rdi]
0x18000d25e  lea     rdx, [rsp+2D0h+var_288]
0x18000d263  mov     rcx, rdi
0x18000d266  mov     rax, [rax+80h]
0x18000d26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d272  mov     esi, eax
0x18000d274  lea     rcx, [rsp+2D0h+lpMem]
0x18000d279  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18000d27e  jmp     loc_18000D193
0x18000d283  lea     rcx, [rsp+2D0h+lpMem]
0x18000d288  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18000d28d  nop
0x18000d28e  lea     rcx, [rsp+2D0h+var_270]
0x18000d293  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18000d298  mov     rsi, [rsp+2D0h+var_260]
0x18000d29d  lea     rdx, [rsp+2D0h+var_288]
0x18000d2a2  lea     rcx, [rsp+2D0h+var_298]
0x18000d2a7  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18000d2ac  nop
0x18000d2ad  lea     rcx, [rsp+2D0h+var_2A0]
0x18000d2b2  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18000d2b7  nop
0x18000d2b8  lea     rcx, [rsp+2D0h+var_288]; this
0x18000d2bd  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18000d2c2  mov     r12, [rsp+2D0h+var_298]
0x18000d2c7  mov     edi, [rsp+2D0h+var_274]
0x18000d2cb  test    r12, r12
0x18000d2ce  jz      loc_18000D457
0x18000d2d4  xor     esi, esi
0x18000d2d6  mov     [rsp+2D0h+var_270], rsi
0x18000d2db  mov     [rsp+2D0h+var_2A0], rsi
0x18000d2e0  lea     rax, [rsp+2D0h+var_2A0]
0x18000d2e5  mov     [rsp+2D0h+ppv], rax; ppv
0x18000d2ea  lea     r9, _GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0; riid
0x18000d2f1  xor     edx, edx; pUnkOuter
0x18000d2f3  mov     r8d, 17h; dwClsContext
0x18000d2f9  lea     rcx, CLSID_SpObjectToken; rclsid
0x18000d300  call    cs:__imp_CoCreateInstance
0x18000d306  mov     r14d, eax
0x18000d309  xor     edi, edi
0x18000d30b  test    eax, eax
0x18000d30d  js      short loc_18000D349
0x18000d30f  mov     rcx, [rsp+2D0h+var_2A0]
0x18000d314  mov     rax, [rcx]
0x18000d317  xor     r9d, r9d
0x18000d31a  mov     r8, r12
0x18000d31d  xor     edx, edx
0x18000d31f  mov     rax, [rax+78h]
0x18000d323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d328  mov     r14d, eax
0x18000d32b  xor     r12d, r12d
0x18000d32e  test    eax, eax
0x18000d330  js      short loc_18000D34C
0x18000d332  mov     rsi, [rsp+2D0h+var_2A0]
0x18000d337  mov     ecx, r12d
0x18000d33a  mov     [rsp+2D0h+var_2A0], rcx
0x18000d33f  mov     [rsp+2D0h+var_270], rsi
0x18000d344  mov     rdi, rsi
0x18000d347  jmp     short loc_18000D351
0x18000d349  xor     r12d, r12d
0x18000d34c  mov     rcx, [rsp+2D0h+var_2A0]
0x18000d351  test    rcx, rcx
0x18000d354  jz      short loc_18000D363
0x18000d356  mov     rax, [rcx]
0x18000d359  mov     rax, [rax+10h]
0x18000d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d362  nop
0x18000d363  cmp     r14d, 8004503Ah
0x18000d36a  jz      short loc_18000D383
0x18000d36c  lea     eax, [r14+7FFBAFC0h]
0x18000d373  cmp     eax, 1
0x18000d376  jbe     short loc_18000D383
0x18000d378  test    r14d, r14d
0x18000d37b  js      loc_18000D422
0x18000d381  jmp     short loc_18000D398
0x18000d383  mov     [rsp+2D0h+var_274], 1
0x18000d38b  lea     rcx, [rsp+2D0h+var_298]; this
0x18000d390  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18000d395  mov     r14d, r12d
0x18000d398  test    rdi, rdi
0x18000d39b  jz      loc_18000D422
0x18000d3a1  test    r13d, r13d
0x18000d3a4  jz      short loc_18000D422
0x18000d3a6  mov     rdi, [rsp+2D0h+var_298]
0x18000d3ab  test    rdi, rdi
  ... truncated ...
```
