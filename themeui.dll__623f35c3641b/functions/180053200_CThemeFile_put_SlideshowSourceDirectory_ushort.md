# CThemeFile::put_SlideshowSourceDirectory(ushort *)

- ea: `0x180053200`
- end: `0x1800533f9`
- name: `?put_SlideshowSourceDirectory@CThemeFile@@UEAAJPEAG@Z`
- size: `505`
- prototype: `int(CThemeFile *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007880`
- `0x1800089c0`
- `0x18000a9a0`
- `0x18000b328`
- `0x18000b78c`
- `0x1800358c0`
- `0x180042f84`
- `0x180053200`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800533a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800533a0`

## string_xrefs

- `0x1800533b7`: `ImagesRootPath`
- `0x18005333b`: `Item%uPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::put_SlideshowSourceDirectory(CThemeFile *this, unsigned __int16 *a2)
{
  CThemeFile *v3; // r14
  int v4; // esi
  struct ICachedPrivateProfile *v5; // rbx
  int v6; // edi
  unsigned int v7; // edi
  HRESULT ThemeSetting; // ebx
  unsigned int v9; // ebx
  unsigned __int16 **v11; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  struct ICachedPrivateProfile *v13; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 v14[24]; // [rsp+40h] [rbp-40h] BYREF

  v3 = (CThemeFile *)((char *)this - 16);
  CThemeFile::_putThemeSetting((CThemeFile *)((char *)this - 16), L"Slideshow", L"RssFeed", 0, 0);
  CThemeFile::_putThemeSetting(v3, L"Slideshow", L"ImagesRoot", 0, 0);
  CThemeFile::_putThemeSetting(v3, L"Slideshow", L"ImagesRootPIDL", 0, 0);
  ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v13);
  if ( (int)CThemeFile::_GetCachedProfile(v3, 0, &v13) >= 0 )
  {
    v4 = 1;
    v5 = v13;
    do
    {
      LODWORD(v11) = v4;
      v6 = StringCchPrintfW(v14, 0x15u, L"%s%u", L"Slideshow", v11);
      if ( v6 >= 0 )
      {
        pv = 0;
        v6 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, LPVOID *))(*(_QWORD *)v5 + 56LL))(
               v5,
               v14,
               &pv);
        if ( v6 >= 0 )
        {
          if ( pv )
          {
            v6 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, _QWORD))(*(_QWORD *)v5 + 88LL))(
                   v5,
                   v14,
                   0);
            CoTaskMemFree(pv);
          }
        }
      }
      ++v4;
    }
    while ( v6 >= 0 );
  }
  v7 = 0;
  do
  {
    ThemeSetting = StringCchPrintfW(v14, 0x10u, L"Item%uPath", v7);
    if ( ThemeSetting >= 0 )
    {
      pv = 0;
      ThemeSetting = CThemeFile::_getThemeSetting(v3, L"Slideshow", v14, 0, (unsigned __int16 **)&pv);
      if ( ThemeSetting >= 0 )
      {
        ThemeSetting = CThemeFile::_putThemeSetting(v3, L"Slideshow", v14, 0, 0);
        CoTaskMemFree(pv);
      }
    }
    ++v7;
  }
  while ( ThemeSetting >= 0 );
  v9 = CThemeFile::_putThemeSetting(v3, L"Slideshow", L"ImagesRootPath", 1, a2);
  ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v13);
  return v9;
}

```

## disassembly

```asm
0x180053200  mov     [rsp-28h+arg_10], rbx
0x180053205  push    rbp
0x180053206  push    rsi
0x180053207  push    rdi
0x180053208  push    r14
0x18005320a  push    r15
0x18005320c  mov     rbp, rsp
0x18005320f  sub     rsp, 80h
0x180053216  mov     rax, cs:__security_cookie
0x18005321d  xor     rax, rsp
0x180053220  mov     [rbp+var_10], rax
0x180053224  mov     r15, rdx
0x180053227  lea     r14, [rcx-10h]
0x18005322b  mov     [rsp+80h+var_60], 0; unsigned __int16 *
0x180053234  xor     r9d, r9d; unsigned int
0x180053237  lea     r8, aRssfeed; "RssFeed"
0x18005323e  lea     rsi, aSlideshow; "Slideshow"
0x180053245  mov     rdx, rsi; unsigned __int16 *
0x180053248  mov     rcx, r14; this
0x18005324b  call    ?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z; CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)
0x180053250  mov     [rsp+80h+var_60], 0; unsigned __int16 *
0x180053259  xor     r9d, r9d; unsigned int
0x18005325c  lea     r8, aImagesroot; "ImagesRoot"
0x180053263  mov     rdx, rsi; unsigned __int16 *
0x180053266  mov     rcx, r14; this
0x180053269  call    ?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z; CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)
0x18005326e  mov     [rsp+80h+var_60], 0; unsigned __int16 *
0x180053277  xor     r9d, r9d; unsigned int
0x18005327a  lea     r8, aImagesrootpidl; "ImagesRootPIDL"
0x180053281  mov     rdx, rsi; unsigned __int16 *
0x180053284  mov     rcx, r14; this
0x180053287  call    ?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z; CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)
0x18005328c  lea     rcx, [rbp+var_48]
0x180053290  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180053295  nop
0x180053296  lea     r8, [rbp+var_48]; struct ICachedPrivateProfile **
0x18005329a  xor     edx, edx; bool
0x18005329c  mov     rcx, r14; this
0x18005329f  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x1800532a4  test    eax, eax
0x1800532a6  js      loc_180053336
0x1800532ac  mov     esi, 1
0x1800532b1  mov     rbx, [rbp+var_48]
0x1800532b5  mov     dword ptr [rsp+80h+var_60], esi
0x1800532b9  lea     r9, aSlideshow; "Slideshow"
0x1800532c0  lea     r8, aSU; "%s%u"
0x1800532c7  mov     edx, 15h; unsigned __int64
0x1800532cc  lea     rcx, [rbp+var_40]; unsigned __int16 *
0x1800532d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800532d5  mov     edi, eax
0x1800532d7  test    eax, eax
0x1800532d9  js      short loc_180053329
0x1800532db  mov     [rbp+pv], 0
0x1800532e3  mov     rax, [rbx]
0x1800532e6  lea     r8, [rbp+pv]
0x1800532ea  lea     rdx, [rbp+var_40]
0x1800532ee  mov     rcx, rbx
0x1800532f1  mov     rax, [rax+38h]
0x1800532f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532fa  mov     edi, eax
0x1800532fc  test    eax, eax
0x1800532fe  js      short loc_180053329
0x180053300  cmp     [rbp+pv], 0
0x180053305  jz      short loc_180053329
0x180053307  mov     rax, [rbx]
0x18005330a  xor     r8d, r8d
0x18005330d  lea     rdx, [rbp+var_40]
0x180053311  mov     rcx, rbx
0x180053314  mov     rax, [rax+58h]
0x180053318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005331d  mov     edi, eax
0x18005331f  mov     rcx, [rbp+pv]; pv
0x180053323  call    cs:__imp_CoTaskMemFree
0x180053329  inc     esi
0x18005332b  test    edi, edi
0x18005332d  jns     short loc_1800532B5
0x18005332f  lea     rsi, aSlideshow; "Slideshow"
0x180053336  xor     edi, edi
0x180053338  mov     r9d, edi
0x18005333b  lea     r8, aItemUpath; "Item%uPath"
0x180053342  mov     edx, 10h; unsigned __int64
0x180053347  lea     rcx, [rbp+var_40]; unsigned __int16 *
0x18005334b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053350  mov     ebx, eax
0x180053352  test    eax, eax
0x180053354  js      short loc_1800533A6
0x180053356  mov     [rbp+pv], 0
0x18005335e  lea     rax, [rbp+pv]
0x180053362  mov     [rsp+80h+var_60], rax; unsigned __int16 **
0x180053367  xor     r9d, r9d; unsigned int
0x18005336a  lea     r8, [rbp+var_40]; unsigned __int16 *
0x18005336e  mov     rdx, rsi; unsigned __int16 *
0x180053371  mov     rcx, r14; this
0x180053374  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x180053379  mov     ebx, eax
0x18005337b  test    eax, eax
0x18005337d  js      short loc_1800533A6
0x18005337f  mov     [rsp+80h+var_60], 0; unsigned __int16 *
0x180053388  xor     r9d, r9d; unsigned int
0x18005338b  lea     r8, [rbp+var_40]; unsigned __int16 *
0x18005338f  mov     rdx, rsi; unsigned __int16 *
0x180053392  mov     rcx, r14; this
0x180053395  call    ?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z; CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)
0x18005339a  mov     ebx, eax
0x18005339c  mov     rcx, [rbp+pv]; pv
0x1800533a0  call    cs:__imp_CoTaskMemFree
0x1800533a6  inc     edi
0x1800533a8  test    ebx, ebx
0x1800533aa  jns     short loc_180053338
0x1800533ac  mov     [rsp+80h+var_60], r15; unsigned __int16 *
0x1800533b1  mov     r9d, 1; unsigned int
0x1800533b7  lea     r8, aImagesrootpath; "ImagesRootPath"
0x1800533be  mov     rdx, rsi; unsigned __int16 *
0x1800533c1  mov     rcx, r14; this
0x1800533c4  call    ?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z; CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)
0x1800533c9  mov     ebx, eax
0x1800533cb  lea     rcx, [rbp+var_48]
0x1800533cf  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x1800533d4  mov     eax, ebx
0x1800533d6  mov     rcx, [rbp+var_10]
0x1800533da  xor     rcx, rsp; StackCookie
0x1800533dd  call    __security_check_cookie
0x1800533e2  mov     rbx, [rsp+80h+arg_10]
0x1800533ea  add     rsp, 80h
0x1800533f1  pop     r15
0x1800533f3  pop     r14
0x1800533f5  pop     rdi
0x1800533f6  pop     rsi
0x1800533f7  pop     rbp
0x1800533f8  retn
```
