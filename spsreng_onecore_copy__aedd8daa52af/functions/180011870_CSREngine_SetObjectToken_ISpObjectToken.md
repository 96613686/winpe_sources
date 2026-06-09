# CSREngine::SetObjectToken(ISpObjectToken *)

- ea: `0x180011870`
- end: `0x180011e3d`
- name: `?SetObjectToken@CSREngine@@UEAAJPEAUISpObjectToken@@@Z`
- size: `1485`
- prototype: `int(CSREngine *__hidden this, struct ISpObjectToken *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002470`
- `0x180002cb4`
- `0x180002db8`
- `0x1800034b0`
- `0x1800060c0`
- `0x1800061d0`
- `0x1800062a0`
- `0x180006cec`
- `0x180011870`
- `0x180012ebc`
- `0x180013acc`
- `0x180021744`
- `0x1800af888`
- `0x1800b04a4`
- `0x1800d39f0`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800119ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800119ba`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011925`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011925`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x1800119e7`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x1800119e7`

## string_xrefs

- `0x180011a65`: `FEConfigDataFile`
- `0x1800118f7`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSREngine::SetObjectToken(CSREngine *this, struct IUnknown *a2)
{
  struct ISpObjectToken **v3; // rsi
  unsigned __int64 v4; // rdx
  HRESULT DefinitionFiles; // ebx
  unsigned int v6; // eax
  UINT v7; // eax
  int v8; // eax
  OLECHAR *v9; // rax
  unsigned __int64 v10; // r8
  bool v11; // r9
  CHeap *v12; // rax
  bool v13; // bl
  CEngine *v14; // rax
  CEngine *v15; // rcx
  char *v16; // r14
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  struct ISpObjectToken *v20; // rcx
  __int64 v21; // rcx
  CEngine *v22; // rcx
  bool v24; // [rsp+20h] [rbp-E0h]
  LPCOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  _cpinfo CPInfo; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF

  v28 = 0;
  String = 0;
  v32 = 0;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  v26 = 0;
  v3 = (struct ISpObjectToken **)((char *)this + 96);
  DefinitionFiles = SpGenericSetObjectToken(a2, (struct IUnknown **)this + 12);
  if ( DefinitionFiles < 0 )
    goto LABEL_45;
  lpsz = 0;
  DefinitionFiles = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, LPCOLESTR *))(*v3)->lpVtbl->GetStringValue)(
                      *v3,
                      L"CLSID",
                      &lpsz);
  if ( DefinitionFiles < 0
    || (DefinitionFiles = CLSIDFromString(lpsz, (LPCLSID)((char *)this + 104)), DefinitionFiles < 0) )
  {
    CSpDynamicString::_free((CSpDynamicString *)&lpsz);
  }
  else
  {
    CSpDynamicString::_free((CSpDynamicString *)&lpsz);
    DefinitionFiles = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, __int64 *))(*v3)->lpVtbl->OpenKey)(
                        *v3,
                        L"Attributes",
                        &v28);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    DefinitionFiles = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **))(*(_QWORD *)v28 + 48LL))(
                        v28,
                        L"Language",
                        &String);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 48LL))(v28, L"UPSPhoneSet", &v32) < 0 )
      *((_DWORD *)this + 229) = 0;
    v6 = wcstol(String, 0, 16);
    *((_DWORD *)this + 62) = v6;
    memset(&CPInfo, 0, sizeof(CPInfo));
    v7 = NlsCodePageFromLcid(v6);
    if ( !v7 || !GetCPInfo(v7, &CPInfo) )
    {
      DefinitionFiles = -2147200935;
      goto LABEL_45;
    }
    DefinitionFiles = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, __int64 *))(*v3)->lpVtbl->OpenKey)(
                        *v3,
                        L"Models",
                        &v30);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    StringCchPrintfW(v34, 0x104u, L"%d", *((unsigned int *)this + 62));
    DefinitionFiles = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v30 + 72LL))(
                        v30,
                        v34,
                        &v27);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    v8 = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, unsigned __int16 **))(*v3)->lpVtbl->GetStringValue)(
           *v3,
           L"FEConfigDataFile",
           &v29);
    DefinitionFiles = v8;
    if ( v8 >= 0 )
    {
      DefinitionFiles = CFEManager::LoadDefinitionFiles(CFEManager::s_pFEManager, v29);
      if ( DefinitionFiles < 0 )
        goto LABEL_45;
    }
    else if ( v8 != -2147200966 )
    {
      goto LABEL_45;
    }
    DefinitionFiles = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v27 + 48LL))(
                        v27,
                        0,
                        (char *)this + 352);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    DefinitionFiles = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v27 + 72LL))(
                        v27,
                        *((_QWORD *)this + 44),
                        (char *)this + 256);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    DefinitionFiles = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 32) + 48LL))(
                        *((_QWORD *)this + 32),
                        0,
                        (char *)this + 264);
    if ( DefinitionFiles < 0 )
      goto LABEL_45;
    if ( ((int (__fastcall *)(struct ISpObjectToken *, const wchar_t *, int *))(*v3)->lpVtbl->GetDWORD)(
           *v3,
           L"Server Mode",
           &v26) >= 0 )
      *((_DWORD *)this + 217) = v26;
    v9 = (OLECHAR *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x10u, 0);
    lpsz = v9;
    if ( v9 )
      v12 = CHeap::CHeap((CHeap *)v9, v4, v10, v11, v24);
    else
      v12 = 0;
    *((_QWORD *)this + 15) = v12;
    if ( v12 )
    {
      v13 = 0;
      if ( ((int (__fastcall *)(struct ISpObjectToken *, const wchar_t *, int *))(*v3)->lpVtbl->GetDWORD)(
             *v3,
             L"LFH",
             &v26) >= 0 )
        v13 = v26 != 0;
      CWinHeap::SetServerMode((CWinHeap *)&g_heap, v13);
      CWinHeap::SetServerMode(*((CWinHeap **)this + 15), v13);
      v14 = (CEngine *)CAllocOnSpecificHeapBase::operator_new(0x340u, *((struct CHeap **)this + 15), 1);
      v15 = v14 ? CEngine::CEngine(v14, *((struct CHeap **)this + 15)) : 0LL;
      *((_QWORD *)this + 16) = v15;
      if ( v15 )
      {
        *(_QWORD *)v15 = *((_QWORD *)this + 11);
        v16 = (char *)this - 8;
        DefinitionFiles = CEngine::Initialize(
                            *((CEngine **)this + 16),
                            *((_DWORD *)this + 62),
                            *((_DWORD *)this + 217),
                            0,
                            *v3,
                            *((unsigned __int16 **)this + 33),
                            (CSREngine *)((char *)this + 136),
                            (struct IEngineDataFileName *)(((unsigned __int64)this + 8)
                                                         & ((unsigned __int128)-(__int128)((unsigned __int64)this - 8) >> 64)));
        if ( DefinitionFiles < 0 )
          goto LABEL_45;
        v17 = *(_QWORD *)(*((_QWORD *)this + 16) + 480LL);
        if ( v17 )
        {
          lpsz = 0;
          DefinitionFiles = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPCOLESTR *))(v17 + 24))(
                              *(_QWORD *)(v17 + 24),
                              &IID_ISpPhoneticAlphabetSelection,
                              &lpsz);
          if ( DefinitionFiles < 0 )
            goto LABEL_45;
          DefinitionFiles = (*(__int64 (__fastcall **)(LPCOLESTR, _QWORD))(*(_QWORD *)lpsz + 32LL))(
                              lpsz,
                              *((unsigned int *)this + 229));
          (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)lpsz + 16LL))(lpsz);
          if ( DefinitionFiles < 0 )
            goto LABEL_45;
        }
        v18 = CAllocOnSpecificHeapBase::operator_new(0x38u, *((struct CHeap **)this + 15), 0);
        v4 = (unsigned __int64)v18;
        if ( v18 )
        {
          *v18 = *((_QWORD *)this + 15);
          v18[1] = v16;
          v19 = *((_QWORD *)v16 + 17);
          v18[2] = v19;
          v18[3] = 0;
          v18[4] = 0;
          v18[5] = 0;
          if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v19 + 144) + 16LL) + 354LL) )
            *((_DWORD *)v18 + 12) = v16[786] == 0 ? 0x40000 : 0;
          else
            *((_DWORD *)v18 + 12) = 0x100000;
        }
        else
        {
          v4 = 0;
        }
        *((_QWORD *)this + 118) = v4;
        if ( v4 )
        {
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 16) + 64LL) + 64LL) = *((_DWORD *)this + 217);
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 16) + 64LL) + 7680LL) = *((_DWORD *)this + 229);
          goto LABEL_52;
        }
      }
    }
    DefinitionFiles = -2147024882;
  }
LABEL_45:
  v20 = *v3;
  if ( *v3 )
  {
    *v3 = 0;
    ((void (__fastcall *)(struct ISpObjectToken *))v20->lpVtbl->Release)(v20);
  }
  v21 = *((_QWORD *)this + 32);
  if ( v21 )
  {
    *((_QWORD *)this + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = (CEngine *)*((_QWORD *)this + 16);
  if ( v22 )
    CEngine::`scalar deleting destructor'(v22, v4);
  *((_QWORD *)this + 16) = 0;
LABEL_52:
  CSpDynamicString::_free((CSpDynamicString *)&v29);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v27);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v30);
  CSpDynamicString::_free((CSpDynamicString *)&v32);
  CSpDynamicString::_free((CSpDynamicString *)&String);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v28);
  return (unsigned int)DefinitionFiles;
}

```

## disassembly

```asm
0x180011870  mov     [rsp-8+arg_10], rbx
0x180011875  mov     [rsp-8+arg_18], rsi
0x18001187a  push    rbp
0x18001187b  push    rdi
0x18001187c  push    r12
0x18001187e  push    r14
0x180011880  push    r15
0x180011882  lea     rbp, [rsp-1C0h]
0x18001188a  sub     rsp, 2C0h
0x180011891  mov     rax, cs:__security_cookie
0x180011898  xor     rax, rsp
0x18001189b  mov     [rbp+1E0h+var_30], rax
0x1800118a2  mov     rax, rdx
0x1800118a5  mov     rdi, rcx
0x1800118a8  xor     r12d, r12d
0x1800118ab  mov     [rsp+2E0h+var_288], r12
0x1800118b0  mov     [rsp+2E0h+String], r12
0x1800118b5  mov     [rsp+2E0h+var_268], r12
0x1800118ba  mov     [rsp+2E0h+var_278], r12
0x1800118bf  mov     [rsp+2E0h+var_290], r12
0x1800118c4  mov     [rsp+2E0h+var_280], r12
0x1800118c9  mov     [rsp+2E0h+var_298], r12d
0x1800118ce  lea     rsi, [rcx+60h]
0x1800118d2  mov     rdx, rsi; struct IUnknown **
0x1800118d5  mov     rcx, rax; struct IUnknown *
0x1800118d8  call    ?SpGenericSetObjectToken@@YAJPEAUISpObjectToken@@AEAV?$CComPtr@UISpObjectToken@@@ATL@@@Z; SpGenericSetObjectToken(ISpObjectToken *,ATL::CComPtr<ISpObjectToken> &)
0x1800118dd  mov     ebx, eax
0x1800118df  test    eax, eax
0x1800118e1  js      loc_180011D7F
0x1800118e7  mov     [rsp+2E0h+lpsz], r12
0x1800118ec  mov     rcx, [rsi]
0x1800118ef  mov     rax, [rcx]
0x1800118f2  lea     r8, [rsp+2E0h+lpsz]
0x1800118f7  lea     rdx, aClsid_0; "CLSID"
0x1800118fe  mov     rax, [rax+30h]
0x180011902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011907  mov     ebx, eax
0x180011909  test    eax, eax
0x18001190b  jns     short loc_18001191C
0x18001190d  lea     rcx, [rsp+2E0h+lpsz]; this
0x180011912  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180011917  jmp     loc_180011D7F
0x18001191c  lea     rdx, [rdi+68h]; pclsid
0x180011920  mov     rcx, [rsp+2E0h+lpsz]; lpsz
0x180011925  call    cs:__imp_CLSIDFromString
0x18001192b  mov     ebx, eax
0x18001192d  lea     rcx, [rsp+2E0h+lpsz]; this
0x180011932  test    eax, eax
0x180011934  js      short loc_180011912
0x180011936  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18001193b  mov     rcx, [rsi]
0x18001193e  mov     rax, [rcx]
0x180011941  lea     r8, [rsp+2E0h+var_288]
0x180011946  lea     rdx, aAttributes; "Attributes"
0x18001194d  mov     rax, [rax+48h]
0x180011951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011956  mov     ebx, eax
0x180011958  test    eax, eax
0x18001195a  js      loc_180011D7F
0x180011960  mov     rcx, [rsp+2E0h+var_288]
0x180011965  mov     rax, [rcx]
0x180011968  lea     r8, [rsp+2E0h+String]
0x18001196d  lea     rdx, aLanguage; "Language"
0x180011974  mov     rax, [rax+30h]
0x180011978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001197d  mov     ebx, eax
0x18001197f  test    eax, eax
0x180011981  js      loc_180011D7F
0x180011987  mov     rcx, [rsp+2E0h+var_288]
0x18001198c  mov     rax, [rcx]
0x18001198f  lea     r8, [rsp+2E0h+var_268]
0x180011994  lea     rdx, aUpsphoneset; "UPSPhoneSet"
0x18001199b  mov     rax, [rax+30h]
0x18001199f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a4  test    eax, eax
0x1800119a6  jns     short loc_1800119AF
0x1800119a8  mov     [rdi+394h], r12d
0x1800119af  xor     edx, edx; EndPtr
0x1800119b1  lea     r8d, [rdx+10h]; Radix
0x1800119b5  mov     rcx, [rsp+2E0h+String]; String
0x1800119ba  call    cs:__imp_wcstol
0x1800119c0  mov     [rdi+0F8h], eax
0x1800119c6  xorps   xmm0, xmm0
0x1800119c9  xor     ecx, ecx
0x1800119cb  movups  xmmword ptr [rbp+1E0h+CPInfo.MaxCharSize], xmm0
0x1800119cf  mov     dword ptr [rbp+1E0h+CPInfo.LeadByte+0Ah], ecx
0x1800119d2  mov     ecx, eax; unsigned int
0x1800119d4  call    ?NlsCodePageFromLcid@@YAIK@Z; NlsCodePageFromLcid(ulong)
0x1800119d9  test    eax, eax
0x1800119db  jz      loc_180011D7A
0x1800119e1  lea     rdx, [rbp+1E0h+CPInfo]; lpCPInfo
0x1800119e5  mov     ecx, eax; CodePage
0x1800119e7  call    cs:__imp_GetCPInfo
0x1800119ed  test    eax, eax
0x1800119ef  jz      loc_180011D7A
0x1800119f5  mov     rcx, [rsi]
0x1800119f8  mov     rax, [rcx]
0x1800119fb  lea     r8, [rsp+2E0h+var_278]
0x180011a00  lea     rdx, aModels; "Models"
0x180011a07  mov     rax, [rax+48h]
0x180011a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a10  mov     ebx, eax
0x180011a12  test    eax, eax
0x180011a14  js      loc_180011D7F
0x180011a1a  mov     r9d, [rdi+0F8h]
0x180011a21  lea     r8, aD; "%d"
0x180011a28  mov     edx, 104h; unsigned __int64
0x180011a2d  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x180011a31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011a36  mov     rcx, [rsp+2E0h+var_278]
0x180011a3b  mov     rax, [rcx]
0x180011a3e  lea     r8, [rsp+2E0h+var_290]
0x180011a43  lea     rdx, [rbp+1E0h+var_240]
0x180011a47  mov     rax, [rax+48h]
0x180011a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a50  mov     ebx, eax
0x180011a52  test    eax, eax
0x180011a54  js      loc_180011D7F
0x180011a5a  mov     rcx, [rsi]
0x180011a5d  mov     rax, [rcx]
0x180011a60  lea     r8, [rsp+2E0h+var_280]
0x180011a65  lea     rdx, aFeconfigdatafi; "FEConfigDataFile"
0x180011a6c  mov     rax, [rax+30h]
0x180011a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a75  mov     ebx, eax
0x180011a77  test    eax, eax
0x180011a79  jns     short loc_180011A88
0x180011a7b  cmp     eax, 8004503Ah
0x180011a80  jnz     loc_180011D7F
0x180011a86  jmp     short loc_180011AA3
0x180011a88  mov     rdx, [rsp+2E0h+var_280]; unsigned __int16 *
0x180011a8d  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; lpCriticalSection
0x180011a94  call    ?LoadDefinitionFiles@CFEManager@@QEAAJPEBG@Z; CFEManager::LoadDefinitionFiles(ushort const *)
0x180011a99  mov     ebx, eax
0x180011a9b  test    eax, eax
0x180011a9d  js      loc_180011D7F
0x180011aa3  mov     rcx, [rsp+2E0h+var_290]
0x180011aa8  lea     r14, [rdi+160h]
0x180011aaf  mov     rax, [rcx]
0x180011ab2  mov     r8, r14
0x180011ab5  xor     edx, edx
0x180011ab7  mov     rax, [rax+30h]
0x180011abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ac0  mov     ebx, eax
0x180011ac2  test    eax, eax
0x180011ac4  js      loc_180011D7F
0x180011aca  mov     rcx, [rsp+2E0h+var_290]
0x180011acf  lea     r15, [rdi+100h]
0x180011ad6  mov     rax, [rcx]
0x180011ad9  mov     r8, r15
0x180011adc  mov     rdx, [r14]
0x180011adf  mov     rax, [rax+48h]
0x180011ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae8  mov     ebx, eax
0x180011aea  test    eax, eax
0x180011aec  js      loc_180011D7F
0x180011af2  mov     rcx, [r15]
0x180011af5  lea     r15, [rdi+108h]
0x180011afc  mov     rax, [rcx]
0x180011aff  mov     r8, r15
0x180011b02  xor     edx, edx
0x180011b04  mov     rax, [rax+30h]
0x180011b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0d  mov     ebx, eax
0x180011b0f  test    eax, eax
0x180011b11  js      loc_180011D7F
0x180011b17  mov     rcx, [rsi]
0x180011b1a  mov     rax, [rcx]
0x180011b1d  lea     r8, [rsp+2E0h+var_298]
0x180011b22  lea     rdx, aServerMode; "Server Mode"
0x180011b29  mov     rax, [rax+40h]
0x180011b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b32  test    eax, eax
0x180011b34  js      short loc_180011B40
0x180011b36  mov     eax, [rsp+2E0h+var_298]
0x180011b3a  mov     [rdi+364h], eax
0x180011b40  xor     r8d, r8d; bool
0x180011b43  lea     edx, [r8+10h]; unsigned __int64
0x180011b47  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180011b4e  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x180011b53  mov     [rsp+2E0h+lpsz], rax
0x180011b58  test    rax, rax
0x180011b5b  jz      short loc_180011B67
0x180011b5d  mov     rcx, rax; this
0x180011b60  call    ??0CHeap@@QEAA@_K0_N1@Z; CHeap::CHeap(unsigned __int64,unsigned __int64,bool,bool)
0x180011b65  jmp     short loc_180011B6A
0x180011b67  mov     rax, r12
0x180011b6a  mov     [rdi+78h], rax
0x180011b6e  test    rax, rax
0x180011b71  jnz     short loc_180011B7D
0x180011b73  mov     ebx, 8007000Eh
0x180011b78  jmp     loc_180011D7F
0x180011b7d  mov     bl, r12b
0x180011b80  mov     rcx, [rsi]
0x180011b83  mov     rax, [rcx]
0x180011b86  lea     r8, [rsp+2E0h+var_298]
0x180011b8b  lea     rdx, aLfh; "LFH"
0x180011b92  mov     rax, [rax+40h]
0x180011b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b9b  test    eax, eax
0x180011b9d  js      short loc_180011BA7
0x180011b9f  cmp     [rsp+2E0h+var_298], r12d
0x180011ba4  setnz   bl
0x180011ba7  mov     dl, bl; bool
0x180011ba9  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180011bb0  call    ?SetServerMode@CWinHeap@@QEAA_N_N@Z; CWinHeap::SetServerMode(bool)
0x180011bb5  mov     dl, bl; bool
0x180011bb7  mov     rcx, [rdi+78h]; this
0x180011bbb  call    ?SetServerMode@CWinHeap@@QEAA_N_N@Z; CWinHeap::SetServerMode(bool)
0x180011bc0  mov     r8b, 1; bool
0x180011bc3  mov     rdx, [rdi+78h]; struct CHeap *
0x180011bc7  mov     ecx, 340h; unsigned __int64
0x180011bcc  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180011bd1  test    rax, rax
0x180011bd4  jz      short loc_180011BE7
0x180011bd6  mov     rdx, [rdi+78h]; struct CHeap *
0x180011bda  mov     rcx, rax; this
0x180011bdd  call    ??0CEngine@@QEAA@PEAVCHeap@@@Z; CEngine::CEngine(CHeap *)
0x180011be2  mov     rcx, rax
0x180011be5  jmp     short loc_180011BEA
0x180011be7  mov     rcx, r12
0x180011bea  mov     [rdi+80h], rcx
0x180011bf1  test    rcx, rcx
0x180011bf4  jz      loc_180011B73
0x180011bfa  mov     rax, [rdi+58h]
0x180011bfe  mov     [rcx], rax
0x180011c01  lea     r14, [rdi-8]
0x180011c05  mov     rax, r14
0x180011c08  lea     rcx, [rdi+8]
0x180011c0c  neg     rax
0x180011c0f  sbb     rdx, rdx
0x180011c12  and     rdx, rcx
0x180011c15  lea     rax, [rdi+88h]
0x180011c1c  mov     [rsp+2E0h+var_2A8], rdx; struct IEngineDataFileName *
0x180011c21  mov     [rsp+2E0h+var_2B0], rax; struct IDecoderCallback *
0x180011c26  mov     rax, [r15]
0x180011c29  mov     [rsp+2E0h+Src], rax; Src
0x180011c2e  mov     rax, [rsi]
0x180011c31  mov     [rsp+2E0h+var_2C0], rax; struct ISpObjectToken *
0x180011c36  xor     r9d, r9d; struct CSRThreadPool *
0x180011c39  mov     r8d, [rdi+364h]; int
0x180011c40  mov     edx, [rdi+0F8h]; unsigned int
0x180011c46  mov     rcx, [rdi+80h]; this
0x180011c4d  call    ?Initialize@CEngine@@QEAAJKHPEAVCSRThreadPool@@PEAUISpObjectToken@@PEAGPEAVIDecoderCallback@@PEAVIEngineDataFileName@@@Z; CEngine::Initialize(ulong,int,CSRThreadPool *,ISpObjectToken *,ushort *,IDecoderCallback *,IEngineDataFileName *)
0x180011c52  mov     ebx, eax
0x180011c54  test    eax, eax
0x180011c56  js      loc_180011D7F
0x180011c5c  mov     rax, [rdi+80h]
0x180011c63  mov     rcx, [rax+1E0h]
0x180011c6a  test    rcx, rcx
0x180011c6d  jz      short loc_180011CCB
0x180011c6f  mov     [rsp+2E0h+lpsz], r12
0x180011c74  mov     rcx, [rcx+18h]
0x180011c78  mov     rax, [rcx]
0x180011c7b  lea     r8, [rsp+2E0h+lpsz]
0x180011c80  lea     rdx, IID_ISpPhoneticAlphabetSelection
0x180011c87  mov     rax, [rax]
0x180011c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c8f  mov     ebx, eax
0x180011c91  test    eax, eax
0x180011c93  js      loc_180011D7F
0x180011c99  mov     rcx, [rsp+2E0h+lpsz]
0x180011c9e  mov     rax, [rcx]
0x180011ca1  mov     edx, [rdi+394h]
0x180011ca7  mov     rax, [rax+20h]
0x180011cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb0  mov     ebx, eax
0x180011cb2  mov     rcx, [rsp+2E0h+lpsz]
0x180011cb7  mov     rax, [rcx]
0x180011cba  mov     rax, [rax+10h]
0x180011cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc3  test    ebx, ebx
0x180011cc5  js      loc_180011D7F
0x180011ccb  xor     r8d, r8d; bool
0x180011cce  mov     rdx, [rdi+78h]; struct CHeap *
0x180011cd2  lea     ecx, [r8+38h]; unsigned __int64
0x180011cd6  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180011cdb  mov     rdx, rax
0x180011cde  test    rax, rax
0x180011ce1  jz      short loc_180011D3A
0x180011ce3  mov     rcx, [rdi+78h]
0x180011ce7  mov     [rax], rcx
0x180011cea  mov     [rax+8], r14
0x180011cee  mov     rcx, [r14+88h]
0x180011cf5  mov     [rax+10h], rcx
0x180011cf9  mov     [rax+18h], r12
0x180011cfd  mov     [rax+20h], r12
0x180011d01  mov     [rax+28h], r12
0x180011d05  mov     rcx, [rcx+90h]
0x180011d0c  mov     rax, [rcx+10h]
0x180011d10  cmp     [rax+162h], r12b
0x180011d17  jnz     short loc_180011D22
0x180011d19  mov     dword ptr [rdx+30h], 100000h
0x180011d20  jmp     short loc_180011D3D
0x180011d22  mov     al, [r14+312h]
0x180011d29  neg     al
0x180011d2b  sbb     ecx, ecx
0x180011d2d  not     ecx
0x180011d2f  and     ecx, 40000h
0x180011d35  mov     [rdx+30h], ecx
  ... truncated ...
```
