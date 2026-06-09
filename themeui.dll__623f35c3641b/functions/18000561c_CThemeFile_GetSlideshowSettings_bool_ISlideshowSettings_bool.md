# CThemeFile::_GetSlideshowSettings(bool,ISlideshowSettings * *,bool)

- ea: `0x18000561c`
- end: `0x180005c1d`
- name: `?_GetSlideshowSettings@CThemeFile@@AEAAJ_NPEAPEAUISlideshowSettings@@0@Z`
- size: `1537`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, bool, struct ISlideshowSettings **, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800521b0`
- `0x180052460`

## callees

- `0x18000561c`
- `0x18000646c`
- `0x1800064b0`
- `0x180006ae0`
- `0x1800089c0`
- `0x18000dd60`
- `0x180014450`
- `0x1800358c0`
- `0x18003633c`
- `0x180049098`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005896`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800057d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800057d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800056b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005925`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800056b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005925`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a16`

## pseudocode

```c
__int64 __fastcall CThemeFile::_GetSlideshowSettings(
        CThemeFile *this,
        char a2,
        struct ISlideshowSettings **a3,
        unsigned __int8 a4)
{
  __int64 *v6; // rsi
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v9; // rax
  int IntSetting; // ebx
  __int64 v11; // rcx
  int (__fastcall *v12)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, PROPVARIANT *); // rax
  int v13; // ebx
  unsigned int v14; // r12d
  __int64 v16; // rax
  LPVOID v17; // rcx
  __int64 v18; // rcx
  struct ICachedPrivateProfile *v19; // rsi
  HANDLE ProcessHeap; // rax
  CSlideshowSettingsAdapter *v21; // rax
  CSlideshowSettingsAdapter *v22; // rdi
  BOOL v23; // r15d
  unsigned __int16 *v24; // r14
  struct CFileSource *v25; // rbx
  HRESULT Instance; // esi
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  struct CFileSource *v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct CFileSource *v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  unsigned __int16 v44[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[528]; // [rsp+290h] [rbp+190h] BYREF

  *a3 = 0;
  LODWORD(v40) = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    IntSetting = -2147467259;
    goto LABEL_18;
  }
  v6 = (__int64 *)*((_QWORD *)this + 7);
  if ( !v6 )
  {
LABEL_5:
    pv = 0;
    IntSetting = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &pv);
    if ( IntSetting >= 0 )
    {
      IntSetting = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv + 24LL))(
                     pv,
                     *((_QWORD *)this + 6),
                     0x400000);
      if ( IntSetting >= 0 )
      {
        v11 = *((_QWORD *)this + 7);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v6 = (__int64 *)pv;
        *((_QWORD *)this + 7) = pv;
        (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
        *((_BYTE *)this + 64) = 0;
        goto LABEL_10;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
LABEL_18:
    v14 = 0;
    goto LABEL_15;
  }
  v7 = *((_BYTE *)this + 64) == 0;
  v8 = *((_QWORD *)this + 7);
  v9 = *v6;
  if ( !v7 )
  {
    (*(void (__fastcall **)(__int64))(v9 + 96))(v8);
    goto LABEL_5;
  }
  (*(void (__fastcall **)(__int64))(v9 + 8))(v8);
LABEL_10:
  v43 = 0;
  LOWORD(ppv) = 3;
  v12 = *(int (__fastcall **)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, PROPVARIANT *))(*v6 + 40);
  *(_OWORD *)pvar = 0;
  if ( v12(v6, L"Slideshow", L"Interval", 0, ppv, pvar) >= 0 )
  {
    v13 = (int)pvar[1];
    LODWORD(v40) = pvar[1];
    PropVariantClear(pvar);
  }
  else
  {
    LODWORD(v40) = -1;
    v13 = -1;
  }
  (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
  v14 = -1;
  if ( v13 >= 0 )
    v14 = v13;
  IntSetting = (v13 >> 31) & 0x80070216;
LABEL_15:
  if ( IntSetting >= 0 )
  {
    IntSetting = CThemeFile::_getIntSetting(this, L"Slideshow", L"Shuffle", -1, &v40);
    if ( (_DWORD)v40 == -1 )
      return (unsigned int)-2147467259;
    v23 = (_DWORD)v40 != 0;
    if ( IntSetting < 0 )
      return (unsigned int)IntSetting;
    v24 = 0;
    v41 = 0;
    if ( !*((_QWORD *)this + 6) )
    {
      Instance = -2147467259;
      goto LABEL_45;
    }
    v25 = (struct CFileSource *)*((_QWORD *)this + 7);
    if ( v25 )
    {
      v28 = *((_QWORD *)this + 7);
      v29 = *(_QWORD *)v25;
      if ( !*((_BYTE *)this + 64) )
      {
        (*(void (__fastcall **)(__int64))(v29 + 8))(v28);
        goto LABEL_59;
      }
      (*(void (__fastcall **)(__int64))(v29 + 96))(v28);
    }
    v40 = 0;
    Instance = CoCreateInstance(
                 &CLSID_PrivateProfile,
                 0,
                 1u,
                 &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
                 (LPVOID *)&v40);
    if ( Instance < 0 )
      goto LABEL_45;
    Instance = (*(__int64 (__fastcall **)(struct CFileSource *, _QWORD, __int64))(*(_QWORD *)v40 + 24LL))(
                 v40,
                 *((_QWORD *)this + 6),
                 0x400000);
    if ( Instance < 0 )
    {
      v30 = *(_QWORD *)v40;
LABEL_44:
      (*(void (**)(void))(v30 + 16))();
LABEL_45:
      if ( Instance >= 0 )
      {
        IntSetting = CSlideshowSettingsAdapter_CreateRSSSlideshow(v23, v14, v24, a3);
        CoTaskMemFree(v24);
        return (unsigned int)IntSetting;
      }
      if ( !*((_QWORD *)this + 6) )
        return (unsigned int)-2147467259;
      v19 = (struct ICachedPrivateProfile *)*((_QWORD *)this + 7);
      if ( v19 )
      {
        v31 = *((_QWORD *)this + 7);
        v32 = *(_QWORD *)v19;
        if ( !*((_BYTE *)this + 64) )
        {
          (*(void (__fastcall **)(__int64))(v32 + 8))(v31);
          goto LABEL_29;
        }
        (*(void (__fastcall **)(__int64))(v32 + 96))(v31);
      }
      pv = 0;
      IntSetting = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &pv);
      if ( IntSetting < 0 )
        return (unsigned int)IntSetting;
      IntSetting = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv + 24LL))(
                     pv,
                     *((_QWORD *)this + 6),
                     0x400000);
      if ( IntSetting < 0 )
      {
        v17 = pv;
        v16 = *(_QWORD *)pv;
        goto LABEL_24;
      }
      v18 = *((_QWORD *)this + 7);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = (struct ICachedPrivateProfile *)pv;
      *((_QWORD *)this + 7) = pv;
      (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v19 + 8LL))(v19);
      *((_BYTE *)this + 64) = 0;
LABEL_29:
      ProcessHeap = GetProcessHeap();
      v21 = (CSlideshowSettingsAdapter *)HeapAlloc(ProcessHeap, 8u, 0x48u);
      v41 = (unsigned __int16 *)v21;
      v22 = v21;
      if ( !v21 )
      {
        IntSetting = -2147024882;
        goto LABEL_23;
      }
      *((_DWORD *)v21 + 4) = 1;
      *(_QWORD *)v21 = &CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'};
      *((_QWORD *)v21 + 1) = &CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'};
      *((_QWORD *)v21 + 3) = 0;
      *((_QWORD *)v21 + 4) = 1800000;
      *((_DWORD *)v21 + 10) = 1000;
      *((_QWORD *)v21 + 6) = 0;
      *((_QWORD *)v21 + 7) = 0;
      *((_DWORD *)v21 + 16) = 0;
      v33 = 0;
      v40 = 0;
      if ( a2 )
      {
        IntSetting = CFileSource::s_LoadFromProfile(v19, &v40, a4);
        if ( IntSetting < 0 )
        {
LABEL_22:
          (*(void (__fastcall **)(CSlideshowSettingsAdapter *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_23:
          v16 = *(_QWORD *)v19;
          v17 = v19;
LABEL_24:
          (*(void (__fastcall **)(LPVOID))(v16 + 16))(v17);
          return (unsigned int)IntSetting;
        }
        v33 = v40;
      }
      IntSetting = CSlideshowSettingsAdapter::_InitializeHelper(v22, v23, v14, v33);
      SafeRelease<CFileSource>(&v40);
      if ( IntSetting >= 0 )
      {
        *a3 = v22;
        IntSetting = 0;
        goto LABEL_23;
      }
      goto LABEL_22;
    }
    v27 = *((_QWORD *)this + 7);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v25 = v40;
    *((_QWORD *)this + 7) = v40;
    (*(void (__fastcall **)(struct CFileSource *))(*(_QWORD *)v25 + 8LL))(v25);
    *((_BYTE *)this + 64) = 0;
LABEL_59:
    pv = 0;
    if ( (int)StringCchPrintfW(v44, 0x104u, L"%s.MUI", L"RssFeed") >= 0
      && (*(int (__fastcall **)(struct CFileSource *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPVOID *))(*(_QWORD *)v25 + 48LL))(
           v25,
           L"Slideshow",
           v44,
           0,
           1,
           &pv) >= 0
      || (Instance = (*(__int64 (__fastcall **)(struct CFileSource *, const WCHAR *, const unsigned __int16 *, _QWORD, int, LPVOID *))(*(_QWORD *)v25 + 48LL))(
                       v25,
                       L"Slideshow",
                       L"RssFeed",
                       0,
                       1,
                       &pv),
          Instance >= 0) )
    {
      memset_0(v45, 0, 0x208u);
      Instance = _AllocString<CTCoAllocPolicy>(v35, v34, pv, &v41);
      CoTaskMemFree(pv);
      v24 = v41;
    }
    v30 = *(_QWORD *)v25;
    goto LABEL_44;
  }
  return (unsigned int)IntSetting;
}

```

## disassembly

```asm
0x18000561c  mov     [rsp-8+arg_8], rbx
0x180005621  push    rbp
0x180005622  push    rsi
0x180005623  push    rdi
0x180005624  push    r12
0x180005626  push    r13
0x180005628  push    r14
0x18000562a  push    r15
0x18000562c  lea     rbp, [rsp-3B0h]
0x180005634  sub     rsp, 4B0h
0x18000563b  mov     rax, cs:__security_cookie
0x180005642  xor     rax, rsp
0x180005645  mov     [rbp+3E0h+var_40], rax
0x18000564c  xor     esi, esi
0x18000564e  mov     [rsp+4E0h+var_49F], r9b
0x180005653  or      r15d, 0FFFFFFFFh
0x180005657  mov     [r8], rsi
0x18000565a  mov     r13, r8
0x18000565d  mov     [rsp+4E0h+var_4A0], dl
0x180005661  mov     rdi, rcx
0x180005664  mov     dword ptr [rsp+4E0h+var_490], esi
0x180005668  cmp     [rcx+30h], rsi
0x18000566c  jz      loc_1800057BB
0x180005672  mov     rsi, [rcx+38h]
0x180005676  test    rsi, rsi
0x180005679  jz      short loc_180005694
0x18000567b  cmp     byte ptr [rcx+40h], 0
0x18000567f  mov     rcx, rsi
0x180005682  mov     rax, [rsi]
0x180005685  jz      loc_180005AC1
0x18000568b  mov     rax, [rax+60h]
0x18000568f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005694  xor     esi, esi
0x180005696  lea     rax, [rsp+4E0h+pv]
0x18000569b  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x1800056a2  mov     [rsp+4E0h+pv], rsi
0x1800056a7  xor     edx, edx; pUnkOuter
0x1800056a9  mov     [rsp+4E0h+ppv], rax; ppv
0x1800056ae  lea     rcx, CLSID_PrivateProfile; rclsid
0x1800056b5  lea     r8d, [rsi+1]; dwClsContext
0x1800056b9  call    cs:__imp_CoCreateInstance
0x1800056bf  mov     ebx, eax
0x1800056c1  test    eax, eax
0x1800056c3  js      loc_1800057C0
0x1800056c9  mov     rcx, [rsp+4E0h+pv]
0x1800056ce  mov     r8d, 400000h
0x1800056d4  mov     rdx, [rdi+30h]
0x1800056d8  mov     rax, [rcx]
0x1800056db  mov     rax, [rax+18h]
0x1800056df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e4  mov     ebx, eax
0x1800056e6  test    eax, eax
0x1800056e8  js      loc_1800057DA
0x1800056ee  mov     rcx, [rdi+38h]
0x1800056f2  test    rcx, rcx
0x1800056f5  jnz     loc_1800057ED
0x1800056fb  mov     rsi, [rsp+4E0h+pv]
0x180005700  mov     [rdi+38h], rsi
0x180005704  mov     rcx, rsi
0x180005707  mov     rax, [rsi]
0x18000570a  mov     rax, [rax+8]
0x18000570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005713  mov     byte ptr [rdi+40h], 0
0x180005717  xor     eax, eax
0x180005719  lea     rcx, [rsp+4E0h+pvar]
0x18000571e  mov     [rsp+4E0h+var_470], rax
0x180005723  lea     r8, aInterval; "Interval"
0x18000572a  mov     rax, [rsi]
0x18000572d  lea     rdx, aSlideshow; "Slideshow"
0x180005734  mov     [rsp+4E0h+var_4B8], rcx
0x180005739  xorps   xmm0, xmm0
0x18000573c  xor     r9d, r9d
0x18000573f  mov     word ptr [rsp+4E0h+ppv], 3
0x180005746  mov     rcx, rsi
0x180005749  mov     rax, [rax+28h]
0x18000574d  movups  xmmword ptr [rsp+4E0h+pvar], xmm0
0x180005752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005757  test    eax, eax
0x180005759  jns     short loc_1800057C5
0x18000575b  mov     dword ptr [rsp+4E0h+var_490], r15d
0x180005760  mov     ebx, r15d
0x180005763  mov     rax, [rsi]
0x180005766  mov     rcx, rsi
0x180005769  mov     rax, [rax+10h]
0x18000576d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005772  or      r12d, 0FFFFFFFFh
0x180005776  xor     esi, esi
0x180005778  test    ebx, ebx
0x18000577a  cmovns  r12d, ebx
0x18000577e  sar     ebx, 1Fh
0x180005781  and     ebx, 80070216h
0x180005787  test    ebx, ebx
0x180005789  jns     loc_180005ACF
0x18000578f  mov     eax, ebx
0x180005791  mov     rcx, [rbp+3E0h+var_40]
0x180005798  xor     rcx, rsp; StackCookie
0x18000579b  call    __security_check_cookie
0x1800057a0  mov     rbx, [rsp+4E0h+arg_8]
0x1800057a8  add     rsp, 4B0h
0x1800057af  pop     r15
0x1800057b1  pop     r14
0x1800057b3  pop     r13
0x1800057b5  pop     r12
0x1800057b7  pop     rdi
0x1800057b8  pop     rsi
0x1800057b9  pop     rbp
0x1800057ba  retn
0x1800057bb  mov     ebx, 80004005h
0x1800057c0  mov     r12d, esi
0x1800057c3  jmp     short loc_180005787
0x1800057c5  mov     ebx, dword ptr [rsp+4E0h+pvar+8]
0x1800057c9  lea     rcx, [rsp+4E0h+pvar]; pvar
0x1800057ce  mov     dword ptr [rsp+4E0h+var_490], ebx
0x1800057d2  call    cs:__imp_PropVariantClear
0x1800057d8  jmp     short loc_180005763
0x1800057da  mov     rcx, [rsp+4E0h+pv]
0x1800057df  mov     rax, [rcx]
0x1800057e2  mov     rax, [rax+10h]
0x1800057e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057eb  jmp     short loc_1800057C0
0x1800057ed  mov     rax, [rcx]
0x1800057f0  mov     rax, [rax+10h]
0x1800057f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f9  jmp     loc_1800056FB
0x1800057fe  movzx   r8d, [rsp+4E0h+var_49F]; int
0x180005804  lea     rdx, [rsp+4E0h+var_490]; struct CFileSource **
0x180005809  mov     rcx, rsi; struct ICachedPrivateProfile *
0x18000580c  call    ?s_LoadFromProfile@CFileSource@@SAJPEAUICachedPrivateProfile@@PEAPEAV1@H@Z; CFileSource::s_LoadFromProfile(ICachedPrivateProfile *,CFileSource * *,int)
0x180005811  mov     ebx, eax
0x180005813  test    eax, eax
0x180005815  jns     loc_180005C13
0x18000581b  mov     rax, [rdi]
0x18000581e  mov     rcx, rdi
0x180005821  mov     rax, [rax+10h]
0x180005825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582a  mov     rax, [rsi]
0x18000582d  mov     rcx, rsi
0x180005830  mov     rax, [rax+10h]
0x180005834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005839  jmp     loc_18000578F
0x18000583e  mov     rcx, [rsp+4E0h+pv]
0x180005843  mov     r8d, 400000h
0x180005849  mov     rdx, [rdi+30h]
0x18000584d  mov     rax, [rcx]
0x180005850  mov     rax, [rax+18h]
0x180005854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005859  mov     ebx, eax
0x18000585b  test    eax, eax
0x18000585d  js      short loc_1800058B7
0x18000585f  mov     rcx, [rdi+38h]
0x180005863  test    rcx, rcx
0x180005866  jnz     short loc_1800058C4
0x180005868  mov     rsi, [rsp+4E0h+pv]
0x18000586d  mov     [rdi+38h], rsi
0x180005871  mov     rcx, rsi
0x180005874  mov     rax, [rsi]
0x180005877  mov     rax, [rax+8]
0x18000587b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005880  mov     [rdi+40h], r14b
0x180005884  call    cs:__imp_GetProcessHeap
0x18000588a  mov     edx, 8; dwFlags
0x18000588f  mov     rcx, rax; hHeap
0x180005892  lea     r8d, [rdx+40h]; dwBytes
0x180005896  call    cs:__imp_HeapAlloc
0x18000589c  mov     [rsp+4E0h+var_488], rax
0x1800058a1  mov     rdi, rax
0x1800058a4  test    rax, rax
0x1800058a7  jnz     loc_180005A3C
0x1800058ad  mov     ebx, 8007000Eh
0x1800058b2  jmp     loc_18000582A
0x1800058b7  mov     rcx, [rsp+4E0h+pv]
0x1800058bc  mov     rax, [rcx]
0x1800058bf  jmp     loc_180005830
0x1800058c4  mov     rax, [rcx]
0x1800058c7  mov     rax, [rax+10h]
0x1800058cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d0  jmp     short loc_180005868
0x1800058d2  test    eax, eax
0x1800058d4  mov     r15d, esi
0x1800058d7  setnz   r15b
0x1800058db  test    ebx, ebx
0x1800058dd  js      loc_18000578F
0x1800058e3  mov     r14, rsi
0x1800058e6  mov     [rsp+4E0h+var_488], rsi
0x1800058eb  cmp     [rdi+30h], rsi
0x1800058ef  jz      loc_1800059A4
0x1800058f5  mov     rbx, [rdi+38h]
0x1800058f9  test    rbx, rbx
0x1800058fc  jnz     loc_180005986
0x180005902  xor     edx, edx; pUnkOuter
0x180005904  mov     [rsp+4E0h+var_490], rsi
0x180005909  lea     rax, [rsp+4E0h+var_490]
0x18000590e  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180005915  mov     [rsp+4E0h+ppv], rax; ppv
0x18000591a  lea     rcx, CLSID_PrivateProfile; rclsid
0x180005921  lea     r8d, [rdx+1]; dwClsContext
0x180005925  call    cs:__imp_CoCreateInstance
0x18000592b  mov     esi, eax
0x18000592d  test    eax, eax
0x18000592f  js      loc_1800059BC
0x180005935  mov     rcx, [rsp+4E0h+var_490]
0x18000593a  mov     r8d, 400000h
0x180005940  mov     rdx, [rdi+30h]
0x180005944  mov     rax, [rcx]
0x180005947  mov     rax, [rax+18h]
0x18000594b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005950  mov     esi, eax
0x180005952  test    eax, eax
0x180005954  js      short loc_1800059AB
0x180005956  mov     rcx, [rdi+38h]
0x18000595a  xor     esi, esi
0x18000595c  test    rcx, rcx
0x18000595f  jnz     loc_180005A2B
0x180005965  mov     rbx, [rsp+4E0h+var_490]
0x18000596a  mov     [rdi+38h], rbx
0x18000596e  mov     rcx, rbx
0x180005971  mov     rax, [rbx]
0x180005974  mov     rax, [rax+8]
0x180005978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597d  mov     [rdi+40h], sil
0x180005981  jmp     loc_180005B14
0x180005986  mov     rcx, rbx
0x180005989  mov     rax, [rbx]
0x18000598c  cmp     [rdi+40h], sil
0x180005990  jz      loc_180005B0B
0x180005996  mov     rax, [rax+60h]
0x18000599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599f  jmp     loc_180005902
0x1800059a4  mov     esi, 80004005h
0x1800059a9  jmp     short loc_1800059BC
0x1800059ab  mov     rcx, [rsp+4E0h+var_490]
0x1800059b0  mov     rax, [rcx]
0x1800059b3  mov     rax, [rax+10h]
0x1800059b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059bc  test    esi, esi
0x1800059be  jns     loc_180005BE4
0x1800059c4  xor     r14d, r14d
0x1800059c7  cmp     [rdi+30h], r14
0x1800059cb  jz      loc_180005B01
0x1800059d1  mov     rsi, [rdi+38h]
0x1800059d5  test    rsi, rsi
0x1800059d8  jz      short loc_1800059F3
0x1800059da  mov     rcx, rsi
0x1800059dd  mov     rax, [rsi]
0x1800059e0  cmp     [rdi+40h], r14b
0x1800059e4  jz      loc_180005C05
0x1800059ea  mov     rax, [rax+60h]
0x1800059ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f3  xor     edx, edx; pUnkOuter
0x1800059f5  mov     [rsp+4E0h+pv], r14
0x1800059fa  lea     rax, [rsp+4E0h+pv]
0x1800059ff  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180005a06  mov     [rsp+4E0h+ppv], rax; ppv
0x180005a0b  lea     rcx, CLSID_PrivateProfile; rclsid
0x180005a12  lea     r8d, [rdx+1]; dwClsContext
0x180005a16  call    cs:__imp_CoCreateInstance
0x180005a1c  mov     ebx, eax
0x180005a1e  test    eax, eax
0x180005a20  jns     loc_18000583E
0x180005a26  jmp     loc_18000578F
0x180005a2b  mov     rax, [rcx]
0x180005a2e  mov     rax, [rax+10h]
0x180005a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a37  jmp     loc_180005965
0x180005a3c  mov     dword ptr [rdi+10h], 1
0x180005a43  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettings@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettings'}
0x180005a4a  mov     [rdi], rax
0x180005a4d  lea     rax, ??_7CSlideshowSettingsAdapter@@6BISlideshowSettingsInternal@@@; const CSlideshowSettingsAdapter::`vftable'{for `ISlideshowSettingsInternal'}
0x180005a54  mov     [rdi+8], rax
0x180005a58  mov     [rdi+18h], r14
0x180005a5c  mov     qword ptr [rdi+20h], 1B7740h
0x180005a64  mov     dword ptr [rdi+28h], 3E8h
0x180005a6b  mov     [rdi+30h], r14
0x180005a6f  mov     [rdi+38h], r14
0x180005a73  mov     [rdi+40h], r14d
0x180005a77  test    rdi, rdi
0x180005a7a  jz      loc_1800058AD
0x180005a80  mov     r9, r14; struct CFileSource *
0x180005a83  mov     [rsp+4E0h+var_490], r14
0x180005a88  cmp     [rsp+4E0h+var_4A0], r14b
0x180005a8d  jnz     loc_1800057FE
0x180005a93  mov     r8d, r12d; unsigned int
0x180005a96  mov     edx, r15d; int
0x180005a99  mov     rcx, rdi; this
0x180005a9c  call    ?_InitializeHelper@CSlideshowSettingsAdapter@@AEAAJHKPEAVCFileSource@@@Z; CSlideshowSettingsAdapter::_InitializeHelper(int,ulong,CFileSource *)
0x180005aa1  lea     rcx, [rsp+4E0h+var_490]
0x180005aa6  mov     ebx, eax
0x180005aa8  call    ??$SafeRelease@VCFileSource@@@@YAXPEAPEAVCFileSource@@@Z; SafeRelease<CFileSource>(CFileSource * *)
0x180005aad  test    ebx, ebx
0x180005aaf  js      loc_18000581B
0x180005ab5  mov     [r13+0], rdi
0x180005ab9  mov     ebx, r14d
0x180005abc  jmp     loc_18000582A
0x180005ac1  mov     rax, [rax+8]
0x180005ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aca  jmp     loc_180005717
0x180005acf  lea     rax, [rsp+4E0h+var_490]
0x180005ad4  mov     r9d, r15d; int
0x180005ad7  lea     r8, aShuffle; "Shuffle"
0x180005ade  mov     [rsp+4E0h+ppv], rax; LPVOID
  ... truncated ...
```
