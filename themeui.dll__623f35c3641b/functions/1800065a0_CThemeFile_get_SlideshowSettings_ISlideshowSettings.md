# CThemeFile::get_SlideshowSettings(ISlideshowSettings * *)

- ea: `0x1800065a0`
- end: `0x180006ad9`
- name: `?get_SlideshowSettings@CThemeFile@@UEAAJPEAPEAUISlideshowSettings@@@Z`
- size: `1337`
- prototype: `int(CThemeFile *__hidden this, struct ISlideshowSettings **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000646c`
- `0x1800064b0`
- `0x1800065a0`
- `0x180006ae0`
- `0x1800089c0`
- `0x18000a9a0`
- `0x18000dd60`
- `0x180014450`
- `0x1800358c0`
- `0x18003633c`
- `0x180049098`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006900`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ac0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006748`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006748`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006639`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006894`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006639`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006894`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_SlideshowSettings(CThemeFile *this, struct ISlideshowSettings **a2)
{
  int v2; // r12d
  char *v3; // rdi
  HRESULT v5; // r13d
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  HRESULT RSSSlideshow; // ebx
  __int64 v10; // rcx
  int (__fastcall *v11)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, PROPVARIANT *); // rax
  __int64 v12; // rax
  signed int v13; // r14d
  __int64 result; // rax
  int v15; // edi
  unsigned __int16 *v16; // rsi
  struct ICachedPrivateProfile *v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  HANDLE ProcessHeap; // rax
  struct ISlideshowSettings *v22; // rax
  struct ISlideshowSettings *v23; // rbx
  int v24; // eax
  struct ICachedPrivateProfile *v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  struct ICachedPrivateProfile *v29; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h]
  unsigned __int16 v34[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[528]; // [rsp+280h] [rbp+180h] BYREF

  v2 = 0;
  v3 = (char *)this - 16;
  *a2 = 0;
  v5 = -2147467259;
  LODWORD(v29) = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    RSSSlideshow = -2147467259;
    goto LABEL_14;
  }
  v6 = (__int64 *)*((_QWORD *)v3 + 7);
  if ( !v6 )
  {
LABEL_5:
    pv = 0;
    RSSSlideshow = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &pv);
    if ( RSSSlideshow >= 0 )
    {
      RSSSlideshow = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv + 24LL))(
                       pv,
                       *((_QWORD *)v3 + 6),
                       0x400000);
      if ( RSSSlideshow >= 0 )
      {
        v10 = *((_QWORD *)v3 + 7);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v6 = (__int64 *)pv;
        *((_QWORD *)v3 + 7) = pv;
        (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
        v3[64] = 0;
        goto LABEL_10;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
LABEL_14:
    v13 = 0;
    goto LABEL_15;
  }
  v7 = *((_QWORD *)v3 + 7);
  v8 = *v6;
  if ( v3[64] )
  {
    (*(void (__fastcall **)(__int64))(v8 + 96))(v7);
    goto LABEL_5;
  }
  (*(void (__fastcall **)(__int64))(v8 + 8))(v7);
LABEL_10:
  v33 = 0;
  LOWORD(ppv) = 3;
  v11 = *(int (__fastcall **)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, PROPVARIANT *))(*v6 + 40);
  *(_OWORD *)pvar = 0;
  if ( v11(v6, L"Slideshow", L"Interval", 0, ppv, pvar) >= 0 )
  {
    v13 = (signed int)pvar[1];
    LODWORD(v29) = pvar[1];
    PropVariantClear(pvar);
    (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
    if ( v13 >= 0 )
    {
      RSSSlideshow = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v12 = *v6;
    LODWORD(v29) = -1;
    (*(void (__fastcall **)(__int64 *))(v12 + 16))(v6);
  }
  RSSSlideshow = -2147024362;
  v13 = -1;
LABEL_15:
  if ( RSSSlideshow < 0 )
    return (unsigned int)RSSSlideshow;
  result = CThemeFile::_getIntSetting((CThemeFile *)v3, L"Slideshow", L"Shuffle", -1, &v29);
  if ( (_DWORD)v29 == -1 )
    return (unsigned int)v5;
  LOBYTE(v2) = (_DWORD)v29 != 0;
  if ( (int)result < 0 )
    return result;
  v16 = 0;
  v31 = 0;
  v29 = 0;
  if ( (int)CThemeFile::_GetCachedProfile((CThemeFile *)v3, 1, &v29) >= 0 )
  {
    pv = 0;
    v24 = StringCchPrintfW(v34, 0x104u, L"%s.MUI", L"RssFeed");
    v25 = v29;
    if ( v24 >= 0
      && (*(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPVOID *))(*(_QWORD *)v29 + 48LL))(
           v29,
           L"Slideshow",
           v34,
           0,
           1,
           &pv) >= 0
      || (LODWORD(v29) = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, const unsigned __int16 *, _QWORD, int, LPVOID *))(*(_QWORD *)v25 + 48LL))(
                           v25,
                           L"Slideshow",
                           L"RssFeed",
                           0,
                           1,
                           &pv),
          (int)v29 >= 0) )
    {
      memset_0(v35, 0, 0x208u);
      LODWORD(v29) = _AllocString<CTCoAllocPolicy>(v27, v26, pv, &v31);
      CoTaskMemFree(pv);
      v16 = v31;
    }
    (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( (int)v29 >= 0 )
    {
      RSSSlideshow = CSlideshowSettingsAdapter_CreateRSSSlideshow(v2, v13, v16, a2);
      CoTaskMemFree(v16);
      return (unsigned int)RSSSlideshow;
    }
  }
  if ( !*((_QWORD *)v3 + 6) )
    return (unsigned int)v5;
  v17 = (struct ICachedPrivateProfile *)*((_QWORD *)v3 + 7);
  if ( !v17 )
  {
LABEL_30:
    pv = 0;
    v5 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &pv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv + 24LL))(
             pv,
             *((_QWORD *)v3 + 6),
             0x400000);
      if ( v5 >= 0 )
      {
        v20 = *((_QWORD *)v3 + 7);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v17 = (struct ICachedPrivateProfile *)pv;
        *((_QWORD *)v3 + 7) = pv;
        (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v17 + 8LL))(v17);
        v3[64] = 0;
        goto LABEL_35;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    return (unsigned int)v5;
  }
  v18 = *((_QWORD *)v3 + 7);
  v19 = *(_QWORD *)v17;
  if ( v3[64] )
  {
    (*(void (__fastcall **)(__int64))(v19 + 96))(v18);
    goto LABEL_30;
  }
  (*(void (__fastcall **)(__int64))(v19 + 8))(v18);
LABEL_35:
  ProcessHeap = GetProcessHeap();
  v22 = (struct ISlideshowSettings *)HeapAlloc(ProcessHeap, 8u, 0x48u);
  v31 = (unsigned __int16 *)v22;
  v23 = v22;
  if ( v22 )
  {
    *((_DWORD *)v22 + 4) = 1;
    *(_QWORD *)v22 = &CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'};
    *((_QWORD *)v22 + 1) = &CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'};
    *((_QWORD *)v22 + 3) = 0;
    *((_QWORD *)v22 + 4) = 1800000;
    *((_DWORD *)v22 + 10) = 1000;
    *((_QWORD *)v22 + 6) = 0;
    *((_QWORD *)v22 + 7) = 0;
    *((_DWORD *)v22 + 16) = 0;
    v29 = 0;
    v15 = CFileSource::s_LoadFromProfile(v17, &v29, 0);
    if ( v15 < 0
      || (v15 = CSlideshowSettingsAdapter::_InitializeHelper(v23, v2, v13, v29), SafeRelease<CFileSource>(&v29), v15 < 0) )
    {
      (*(void (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    else
    {
      *a2 = v23;
      v15 = 0;
    }
  }
  else
  {
    v15 = -2147024882;
  }
  (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800065a0  mov     [rsp-8+arg_10], rbx
0x1800065a5  push    rbp
0x1800065a6  push    rsi
0x1800065a7  push    rdi
0x1800065a8  push    r12
0x1800065aa  push    r13
0x1800065ac  push    r14
0x1800065ae  push    r15
0x1800065b0  lea     rbp, [rsp-3A0h]
0x1800065b8  sub     rsp, 4A0h
0x1800065bf  mov     rax, cs:__security_cookie
0x1800065c6  xor     rax, rsp
0x1800065c9  mov     [rbp+3D0h+var_40], rax
0x1800065d0  xor     r12d, r12d
0x1800065d3  lea     rdi, [rcx-10h]
0x1800065d7  mov     [rdx], r12
0x1800065da  mov     r15, rdx
0x1800065dd  mov     r13d, 80004005h
0x1800065e3  mov     dword ptr [rsp+4D0h+var_490], r12d
0x1800065e8  cmp     [rdi+30h], r12
0x1800065ec  jz      loc_1800066FF
0x1800065f2  mov     rbx, [rdi+38h]
0x1800065f6  test    rbx, rbx
0x1800065f9  jz      short loc_180006614
0x1800065fb  mov     rcx, rbx
0x1800065fe  mov     rax, [rbx]
0x180006601  cmp     [rdi+40h], r12b
0x180006605  jz      loc_18000697A
0x18000660b  mov     rax, [rax+60h]
0x18000660f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006614  lea     rax, [rsp+4D0h+pv]
0x180006619  mov     [rsp+4D0h+pv], r12
0x18000661e  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180006625  mov     [rsp+4D0h+ppv], rax; ppv
0x18000662a  xor     edx, edx; pUnkOuter
0x18000662c  lea     rcx, CLSID_PrivateProfile; rclsid
0x180006633  mov     r8d, 1; dwClsContext
0x180006639  call    cs:__imp_CoCreateInstance
0x18000663f  mov     ebx, eax
0x180006641  test    eax, eax
0x180006643  js      loc_180006702
0x180006649  mov     rcx, [rsp+4D0h+pv]
0x18000664e  mov     r8d, 400000h
0x180006654  mov     rdx, [rdi+30h]
0x180006658  mov     rax, [rcx]
0x18000665b  mov     rax, [rax+18h]
0x18000665f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006664  mov     ebx, eax
0x180006666  test    eax, eax
0x180006668  js      loc_180006767
0x18000666e  mov     rcx, [rdi+38h]
0x180006672  test    rcx, rcx
0x180006675  jnz     loc_18000677A
0x18000667b  mov     rbx, [rsp+4D0h+pv]
0x180006680  mov     [rdi+38h], rbx
0x180006684  mov     rcx, rbx
0x180006687  mov     rax, [rbx]
0x18000668a  mov     rax, [rax+8]
0x18000668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006693  mov     [rdi+40h], r12b
0x180006697  xor     eax, eax
0x180006699  lea     rcx, [rsp+4D0h+pvar]
0x18000669e  mov     [rsp+4D0h+var_468], rax
0x1800066a3  lea     r8, aInterval; "Interval"
0x1800066aa  mov     rax, [rbx]
0x1800066ad  lea     rdx, aSlideshow; "Slideshow"
0x1800066b4  mov     [rsp+4D0h+var_4A8], rcx
0x1800066b9  xorps   xmm0, xmm0
0x1800066bc  xor     r9d, r9d
0x1800066bf  mov     word ptr [rsp+4D0h+ppv], 3
0x1800066c6  mov     rcx, rbx
0x1800066c9  mov     rax, [rax+28h]
0x1800066cd  movups  xmmword ptr [rsp+4D0h+pvar], xmm0
0x1800066d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d7  test    eax, eax
0x1800066d9  jns     short loc_180006739
0x1800066db  mov     rax, [rbx]
0x1800066de  mov     rcx, rbx
0x1800066e1  mov     dword ptr [rsp+4D0h+var_490], 0FFFFFFFFh
0x1800066e9  mov     rax, [rax+10h]
0x1800066ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f2  mov     ebx, 80070216h
0x1800066f7  mov     r14d, 0FFFFFFFFh
0x1800066fd  jmp     short loc_180006705
0x1800066ff  mov     ebx, r13d
0x180006702  mov     r14d, r12d
0x180006705  test    ebx, ebx
0x180006707  jns     loc_180006988
0x18000670d  mov     eax, ebx
0x18000670f  mov     rcx, [rbp+3D0h+var_40]
0x180006716  xor     rcx, rsp; StackCookie
0x180006719  call    __security_check_cookie
0x18000671e  mov     rbx, [rsp+4D0h+arg_10]
0x180006726  add     rsp, 4A0h
0x18000672d  pop     r15
0x18000672f  pop     r14
0x180006731  pop     r13
0x180006733  pop     r12
0x180006735  pop     rdi
0x180006736  pop     rsi
0x180006737  pop     rbp
0x180006738  retn
0x180006739  mov     r14d, dword ptr [rsp+4D0h+pvar+8]
0x18000673e  lea     rcx, [rsp+4D0h+pvar]; pvar
0x180006743  mov     dword ptr [rsp+4D0h+var_490], r14d
0x180006748  call    cs:__imp_PropVariantClear
0x18000674e  mov     rax, [rbx]
0x180006751  mov     rcx, rbx
0x180006754  mov     rax, [rax+10h]
0x180006758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000675d  test    r14d, r14d
0x180006760  js      short loc_1800066F2
0x180006762  mov     ebx, r12d
0x180006765  jmp     short loc_180006705
0x180006767  mov     rcx, [rsp+4D0h+pv]
0x18000676c  mov     rax, [rcx]
0x18000676f  mov     rax, [rax+10h]
0x180006773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006778  jmp     short loc_180006702
0x18000677a  mov     rax, [rcx]
0x18000677d  mov     rax, [rax+10h]
0x180006781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006786  jmp     loc_18000667B
0x18000678b  mov     dword ptr [rbx+10h], 1
0x180006792  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettings@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'}
0x180006799  mov     [rbx], rax
0x18000679c  lea     rdx, [rsp+4D0h+var_490]; struct CFileSource **
0x1800067a1  xor     r13d, r13d
0x1800067a4  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettingsInternal@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'}
0x1800067ab  mov     [rbx+8], rax
0x1800067af  xor     r8d, r8d; int
0x1800067b2  mov     [rbx+18h], r13
0x1800067b6  mov     rcx, rsi; struct ICachedPrivateProfile *
0x1800067b9  mov     qword ptr [rbx+20h], 1B7740h
0x1800067c1  mov     dword ptr [rbx+28h], 3E8h
0x1800067c8  mov     [rbx+30h], r13
0x1800067cc  mov     [rbx+38h], r13
0x1800067d0  mov     [rbx+40h], r13d
0x1800067d4  mov     [rsp+4D0h+var_490], r13
0x1800067d9  call    ?s_LoadFromProfile@CFileSource@@SAJPEAUICachedPrivateProfile@@PEAPEAV1@H@Z; CFileSource::s_LoadFromProfile(ICachedPrivateProfile *,CFileSource * *,int)
0x1800067de  mov     edi, eax
0x1800067e0  test    eax, eax
0x1800067e2  jns     loc_180006948
0x1800067e8  mov     rax, [rbx]
0x1800067eb  mov     rcx, rbx
0x1800067ee  mov     rax, [rax+10h]
0x1800067f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f7  mov     rdx, [rsi]
0x1800067fa  mov     rcx, rsi
0x1800067fd  mov     rax, [rdx+10h]
0x180006801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006806  mov     eax, edi
0x180006808  jmp     loc_18000670F
0x18000680d  test    ecx, ecx
0x18000680f  setnz   r12b
0x180006813  test    eax, eax
0x180006815  js      loc_18000670F
0x18000681b  xor     esi, esi
0x18000681d  lea     r8, [rsp+4D0h+var_490]; struct ICachedPrivateProfile **
0x180006822  mov     dl, 1; bool
0x180006824  mov     [rsp+4D0h+var_480], rsi
0x180006829  mov     rcx, rdi; this
0x18000682c  mov     [rsp+4D0h+var_490], rsi
0x180006831  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180006836  test    eax, eax
0x180006838  jns     loc_1800069C0
0x18000683e  cmp     qword ptr [rdi+30h], 0
0x180006843  jz      loc_180006932
0x180006849  mov     rsi, [rdi+38h]
0x18000684d  test    rsi, rsi
0x180006850  jz      short loc_18000686B
0x180006852  cmp     byte ptr [rdi+40h], 0
0x180006856  mov     rcx, rsi
0x180006859  mov     rax, [rsi]
0x18000685c  jz      loc_180006ACB
0x180006862  mov     rax, [rax+60h]
0x180006866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686b  lea     rax, [rsp+4D0h+pv]
0x180006870  mov     [rsp+4D0h+pv], 0
0x180006879  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180006880  mov     [rsp+4D0h+ppv], rax; ppv
0x180006885  xor     edx, edx; pUnkOuter
0x180006887  lea     rcx, CLSID_PrivateProfile; rclsid
0x18000688e  mov     r8d, 1; dwClsContext
0x180006894  call    cs:__imp_CoCreateInstance
0x18000689a  mov     r13d, eax
0x18000689d  test    eax, eax
0x18000689f  js      loc_180006932
0x1800068a5  mov     rcx, [rsp+4D0h+pv]
0x1800068aa  mov     r8d, 400000h
0x1800068b0  mov     rdx, [rdi+30h]
0x1800068b4  mov     rax, [rcx]
0x1800068b7  mov     rax, [rax+18h]
0x1800068bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c0  mov     r13d, eax
0x1800068c3  test    eax, eax
0x1800068c5  js      short loc_180006921
0x1800068c7  mov     rcx, [rdi+38h]
0x1800068cb  test    rcx, rcx
0x1800068ce  jnz     short loc_18000693A
0x1800068d0  mov     rsi, [rsp+4D0h+pv]
0x1800068d5  mov     [rdi+38h], rsi
0x1800068d9  mov     rcx, rsi
0x1800068dc  mov     rax, [rsi]
0x1800068df  mov     rax, [rax+8]
0x1800068e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e8  mov     byte ptr [rdi+40h], 0
0x1800068ec  call    cs:__imp_GetProcessHeap
0x1800068f2  mov     edx, 8; dwFlags
0x1800068f7  mov     r8d, 48h ; 'H'; dwBytes
0x1800068fd  mov     rcx, rax; hHeap
0x180006900  call    cs:__imp_HeapAlloc
0x180006906  mov     [rsp+4D0h+var_480], rax
0x18000690b  mov     rbx, rax
0x18000690e  test    rax, rax
0x180006911  jnz     loc_18000678B
0x180006917  mov     edi, 8007000Eh
0x18000691c  jmp     loc_1800067F7
0x180006921  mov     rcx, [rsp+4D0h+pv]
0x180006926  mov     rdx, [rcx]
0x180006929  mov     rax, [rdx+10h]
0x18000692d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006932  mov     eax, r13d
0x180006935  jmp     loc_18000670F
0x18000693a  mov     rax, [rcx]
0x18000693d  mov     rax, [rax+10h]
0x180006941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006946  jmp     short loc_1800068D0
0x180006948  mov     r9, [rsp+4D0h+var_490]; struct CFileSource *
0x18000694d  mov     r8d, r14d; unsigned int
0x180006950  mov     edx, r12d; int
0x180006953  mov     rcx, rbx; this
0x180006956  call    ?_InitializeHelper@CSlideshowSettingsAdapter@@AEAAJHKPEAVCFileSource@@@Z; CSlideshowSettingsAdapter::_InitializeHelper(int,ulong,CFileSource *)
0x18000695b  lea     rcx, [rsp+4D0h+var_490]
0x180006960  mov     edi, eax
0x180006962  call    ??$SafeRelease@VCFileSource@@@@YAXPEAPEAVCFileSource@@@Z; SafeRelease<CFileSource>(CFileSource * *)
0x180006967  test    edi, edi
0x180006969  js      loc_1800067E8
0x18000696f  mov     [r15], rbx
0x180006972  mov     edi, r13d
0x180006975  jmp     loc_1800067F7
0x18000697a  mov     rax, [rax+8]
0x18000697e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006983  jmp     loc_180006697
0x180006988  lea     rax, [rsp+4D0h+var_490]
0x18000698d  mov     r9d, 0FFFFFFFFh; int
0x180006993  lea     r8, aShuffle; "Shuffle"
0x18000699a  mov     [rsp+4D0h+ppv], rax; LPVOID
0x18000699f  lea     rdx, aSlideshow; "Slideshow"
0x1800069a6  mov     rcx, rdi; this
0x1800069a9  call    ?_getIntSetting@CThemeFile@@AEAAJPEBG0HPEAH@Z; CThemeFile::_getIntSetting(ushort const *,ushort const *,int,int *)
0x1800069ae  mov     ecx, dword ptr [rsp+4D0h+var_490]
0x1800069b2  cmp     ecx, 0FFFFFFFFh
0x1800069b5  jz      loc_180006932
0x1800069bb  jmp     loc_18000680D
0x1800069c0  lea     r9, aRssfeed; "RssFeed"
0x1800069c7  mov     [rsp+4D0h+pv], rsi
0x1800069cc  lea     r8, aSMui; "%s.MUI"
0x1800069d3  mov     edx, 104h; unsigned __int64
0x1800069d8  lea     rcx, [rsp+4D0h+var_460]; unsigned __int16 *
0x1800069dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800069e2  mov     rbx, [rsp+4D0h+var_490]
0x1800069e7  test    eax, eax
0x1800069e9  js      short loc_180006A1F
0x1800069eb  mov     rax, [rbx]
0x1800069ee  lea     rcx, [rsp+4D0h+pv]
0x1800069f3  mov     [rsp+4D0h+var_4A8], rcx
0x1800069f8  lea     r8, [rsp+4D0h+var_460]
0x1800069fd  xor     r9d, r9d
0x180006a00  mov     dword ptr [rsp+4D0h+ppv], 1
0x180006a08  lea     rdx, aSlideshow; "Slideshow"
0x180006a0f  mov     rcx, rbx
0x180006a12  mov     rax, [rax+30h]
0x180006a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1b  test    eax, eax
0x180006a1d  jns     short loc_180006A59
0x180006a1f  mov     rax, [rbx]
0x180006a22  lea     rcx, [rsp+4D0h+pv]
0x180006a27  mov     [rsp+4D0h+var_4A8], rcx
0x180006a2c  lea     r8, aRssfeed; "RssFeed"
0x180006a33  xor     r9d, r9d
0x180006a36  mov     dword ptr [rsp+4D0h+ppv], 1
0x180006a3e  lea     rdx, aSlideshow; "Slideshow"
0x180006a45  mov     rcx, rbx
0x180006a48  mov     rax, [rax+30h]
0x180006a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a51  mov     dword ptr [rsp+4D0h+var_490], eax
0x180006a55  test    eax, eax
0x180006a57  js      short loc_180006A90
0x180006a59  xor     edx, edx; Val
0x180006a5b  lea     rcx, [rbp+3D0h+var_250]; void *
0x180006a62  mov     r8d, 208h; Size
0x180006a68  call    memset_0
0x180006a6d  mov     r8, [rsp+4D0h+pv]
0x180006a72  lea     r9, [rsp+4D0h+var_480]
0x180006a77  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180006a7c  mov     rcx, [rsp+4D0h+pv]; pv
0x180006a81  mov     dword ptr [rsp+4D0h+var_490], eax
0x180006a85  call    cs:__imp_CoTaskMemFree
0x180006a8b  mov     rsi, [rsp+4D0h+var_480]
  ... truncated ...
```
