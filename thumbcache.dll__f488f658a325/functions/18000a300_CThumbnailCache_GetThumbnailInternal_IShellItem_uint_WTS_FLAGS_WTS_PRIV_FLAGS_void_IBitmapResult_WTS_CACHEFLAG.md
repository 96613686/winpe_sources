# CThumbnailCache::_GetThumbnailInternal(IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,void *,IBitmapResult * *,WTS_CACHEFLAGS *,WTS_THUMBNAILID *)

- ea: `0x18000a300`
- end: `0x18000ab93`
- name: `?_GetThumbnailInternal@CThumbnailCache@@AEAAJPEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAXPEAPEAUIBitmapResult@@PEAW4WTS_CACHEFLAGS@@PEAUWTS_THUMBNAILID@@@Z`
- size: `2195`
- prototype: `int __high(struct IShellItem *, unsigned int, enum WTS_FLAGS, enum WTS_PRIV_FLAGS, void *, struct IBitmapResult **, enum WTS_CACHEFLAGS *, struct WTS_THUMBNAILID *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009b60`
- `0x18002a5f0`
- `0x180040ef0`

## callees

- `0x180003624`
- `0x1800085c0`
- `0x1800089e8`
- `0x180008a70`
- `0x18000a300`
- `0x18000aba0`
- `0x18000bfd8`
- `0x18000bffc`
- `0x180014868`
- `0x180015868`
- `0x18002b024`
- `0x18002b07c`
- `0x18002b2e8`
- `0x18002d090`
- `0x180035830`
- `0x1800364ac`
- `0x180041270`
- `0x1800429b4`
- `0x180047568`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a64a`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a64a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a5ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a5ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a57a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a57a`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000a3c2`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000a3c2`

## string_xrefs

- `0x18000a723`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18000a73e`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18000a859`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18000a961`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18000ab10`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18000ab2d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CThumbnailCache::_GetThumbnailInternal(
        __int64 a1,
        struct IShellItem *a2,
        unsigned int a3,
        enum WTS_FLAGS a4,
        unsigned int a5,
        void *a6,
        _QWORD *a7,
        enum WTS_CACHEFLAGS *a8,
        _OWORD *a9)
{
  unsigned int v10; // esi
  enum WTS_CACHEFLAGS *v13; // rdi
  __int64 v14; // rcx
  int BitmapResultNoCache; // ebx
  int v16; // eax
  unsigned int v17; // eax
  void *v18; // rdi
  _WORD *v19; // rsi
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rbx
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, PROPERTYKEY *, __int64, __int64, GUID *, struct IPropertyStore **); // rbx
  LPVOID v23; // rcx
  unsigned __int16 *v24; // rdi
  int v25; // esi
  void *v26; // rcx
  void *v27; // rcx
  int v28; // eax
  unsigned int v29; // esi
  int v30; // edi
  void *v32; // rcx
  int v33; // eax
  unsigned int v34; // edx
  int i; // ecx
  int v36; // edx
  int v37; // eax
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // eax
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  _BYTE v44[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-ACh]
  enum WTS_CACHEFLAGS *v46; // [rsp+58h] [rbp-A8h]
  unsigned int v47; // [rsp+60h] [rbp-A0h]
  _QWORD *v48; // [rsp+68h] [rbp-98h]
  PROPERTYKEY v49; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v50; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v51; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v52; // [rsp+A0h] [rbp-60h] BYREF
  struct IPropertyStore *v53; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v54; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h]
  LPVOID pv; // [rsp+C0h] [rbp-40h]
  int v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+CCh] [rbp-34h]
  PROPVARIANT pvar; // [rsp+D0h] [rbp-30h] BYREF
  void *v60; // [rsp+D8h] [rbp-28h]
  PROPERTYKEY v61[2]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v10 = a3;
  v45 = a3;
  v48 = a9;
  v13 = a8;
  v46 = a8;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = WTS_DEFAULT;
  if ( a9 )
    *a9 = 0;
  if ( !(unsigned int)CThumbnailCache::_CheckValidGetThumbnailFlags((CThumbnailCache *)a1, a4) )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  if ( (*(_BYTE *)(a1 + 768) & 8) == 0 && *(_DWORD *)(a1 + 764) != GetCurrentThreadId() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1326,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)0x800705A4LL,
      v42);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126E,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)0x800705A4LL,
      v43);
    return 2147943844LL;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v50 = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetDisplayName)(
           a2,
           2147581953LL,
           &v50) < 0 )
    {
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v40, v39, &unk_1800509F8, v10);
    }
    else
    {
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v40, v39, v50, v10);
      CoTaskMemFree(v50);
    }
  }
  if ( !(unsigned int)EdpGetIsManaged()
    || IsProcessEDPExemptOrEnlightened(a6)
    || (BitmapResultNoCache = -2147175936, !(unsigned int)IsShellItemEncrypted(a2)) )
  {
    BitmapResultNoCache = -2147467259;
    if ( (a4 & 0x24) == 0x24 )
      goto LABEL_19;
    if ( *(_BYTE *)(a1 + 756) )
    {
      if ( *(_BYTE *)(a1 + 757) )
      {
        if ( *(_BYTE *)(a1 + 758) )
        {
          v41 = CThumbnailCache::ResetDestroyedCache((CThumbnailCache *)a1);
          BitmapResultNoCache = v41;
          if ( v41 >= 0 )
            goto LABEL_18;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73B,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
            (const char *)(unsigned int)v41,
            v42);
        }
        else
        {
          v16 = CThumbnailCache::ResetCache((CThumbnailCache *)a1);
          BitmapResultNoCache = v16;
          if ( v16 >= 0 )
          {
LABEL_18:
            BitmapResultNoCache = 0;
            goto LABEL_19;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73F,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
            (const char *)(unsigned int)v16,
            v42);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x733,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
          (const char *)0x8000FFFFLL,
          v42);
        BitmapResultNoCache = -2147418113;
      }
    }
    else
    {
      v33 = CThumbnailCache::AttemptInitialize((CThumbnailCache *)a1, a4, v10);
      BitmapResultNoCache = v33;
      if ( v33 >= 0 )
        goto LABEL_18;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x737,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)v33,
        v42);
    }
LABEL_19:
    v17 = (unsigned int)BitmapResultNoCache >> 31;
    v47 = (unsigned int)BitmapResultNoCache >> 31;
    if ( BitmapResultNoCache < 0 )
    {
LABEL_54:
      if ( (_BYTE)v17 || BitmapResultNoCache == -2147216863 )
      {
        if ( (*(_BYTE *)(a1 + 768) & 1) != 0
          || (a4 & 1) != 0
          || BitmapResultNoCache == -2147024882
          || !a7
          || (v44[0] = 0,
              BitmapResultNoCache = CThumbnailCache::_ExtractBitmapResultNoCache(
                                      a1,
                                      a2,
                                      v10,
                                      (unsigned int)a4,
                                      a5,
                                      v44,
                                      a7),
              BitmapResultNoCache < 0) )
        {
          if ( BitmapResultNoCache == -2147216863 )
            BitmapResultNoCache = -2147418113;
        }
        else
        {
          CThumbnailCache::s_SetGetThumbnailOutFlags(0, v44[0], v13);
        }
      }
      goto LABEL_56;
    }
    v57 = *(_DWORD *)(a1 + 768) & 1;
    v54 = 0;
    pv = 0;
    CoTaskMemFree(0);
    v58 = 0;
    v55 = 0;
    v18 = 0;
    v50 = 0;
    v19 = 0;
    v52 = 0;
    v61[0] = PKEY_DateModified;
    v61[1] = PKEY_ThumbnailCacheId;
    v53 = 0;
    v51 = 0;
    QueryInterface = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    BitmapResultNoCache = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, LPVOID *))QueryInterface)(
                            a2,
                            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                            &v51);
    if ( BitmapResultNoCache >= 0 )
    {
      v21 = v51;
      v22 = *(__int64 (__fastcall **)(LPVOID, PROPERTYKEY *, __int64, __int64, GUID *, struct IPropertyStore **))(*(_QWORD *)v51 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      BitmapResultNoCache = v22(v21, v61, 2, 8, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v53);
      v18 = 0;
    }
    v23 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
    }
    if ( BitmapResultNoCache >= 0 )
    {
      LOWORD(pvar) = 0;
      v49 = PKEY_ThumbnailCacheId;
      BitmapResultNoCache = ((__int64 (__fastcall *)(struct IPropertyStore *, PROPERTYKEY *, PROPVARIANT *))v53->lpVtbl->GetValue)(
                              v53,
                              &v49,
                              &pvar);
      if ( BitmapResultNoCache >= 0 )
      {
        if ( (_WORD)pvar )
        {
          if ( (_WORD)pvar == 21 )
          {
            v18 = v60;
            v50 = v60;
          }
          else
          {
            BitmapResultNoCache = -2147352571;
          }
        }
        else
        {
          BitmapResultNoCache = -2147023728;
        }
      }
      PropVariantClear(&pvar);
      if ( BitmapResultNoCache >= 0 )
      {
        v52 = 0;
        v51 = 0;
        if ( !is_mul_ok(0x11u, 2u) )
        {
LABEL_43:
          BitmapResultNoCache = CThumbnailMoniker::_NonLocalFSInitFallback(
                                  (CThumbnailMoniker *)&v54,
                                  a2,
                                  v53,
                                  (unsigned __int64 *)&v50,
                                  &v52);
          if ( BitmapResultNoCache >= 0 )
          {
            v24 = v52;
LABEL_36:
            v25 = 2 - ((unsigned int)IsShellItemEncrypted(a2) != 0);
            v51 = 0;
            v26 = pv;
            pv = 0;
            CoTaskMemFree(v26);
            v27 = pv;
            pv = 0;
            CoTaskMemFree(v27);
            pv = v24;
            v58 = v25;
            v54 = v50;
            v55 = 0x1300000000LL;
            v19 = v51;
            goto LABEL_37;
          }
          v19 = v52;
LABEL_37:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
          CoTaskMemFree(v19);
          if ( BitmapResultNoCache < 0 )
            goto LABEL_52;
          v28 = *(_DWORD *)(a1 + 768);
          if ( (v28 & 1) != 0 || (a4 & 0x20) != 0 )
          {
            v29 = v45;
LABEL_41:
            v30 = 0;
            goto LABEL_50;
          }
          v29 = v45;
          if ( (v28 & 2) != 0 )
          {
            v34 = 5;
            for ( i = 0; i < 5; ++i )
            {
              if ( v45 == *((_DWORD *)&g_IconSize + i) )
              {
                v34 = i;
                break;
              }
            }
            if ( (unsigned int)MapIconSizeToThumbSize(v34) == -1 )
            {
              v30 = 0;
              goto LABEL_50;
            }
          }
          else if ( v45 > 0xA00 )
          {
            goto LABEL_41;
          }
          if ( v58 == 1 && !*(_DWORD *)(a1 + 752) )
            goto LABEL_41;
          v30 = 1;
LABEL_50:
          if ( (a4 & 8) == 0
            || !v30
            || (BitmapResultNoCache = CThumbnailCache::_AddSlowReclaimThumbnailToCache(
                                        a1,
                                        a2,
                                        (unsigned int)a4,
                                        a5,
                                        &v54),
                BitmapResultNoCache >= 0) )
          {
            LODWORD(v52) = 0;
            LODWORD(v51) = 0;
            BitmapResultNoCache = CThumbnailCache::_GetThumbnailImpl(a1, &v54, a2, v29, a4, a5, v30, a7, &v52, &v51);
            if ( BitmapResultNoCache >= 0 )
            {
              v36 = (int)v52;
              v13 = v46;
              if ( v46 )
              {
                *v46 = WTS_DEFAULT;
                v37 = 0;
                if ( v36 )
                {
                  *v13 = WTS_CACHED;
                  v37 = 2;
                }
                if ( (_DWORD)v51 )
                  *v13 = v37 | 1;
              }
              v38 = v48;
              if ( v48 )
              {
                if ( v36 )
                {
                  *v48 = v54;
                  v38[1] = 0;
                }
                else
                {
                  *(_OWORD *)v48 = 0;
                }
              }
              goto LABEL_53;
            }
          }
LABEL_52:
          v13 = v46;
LABEL_53:
          v32 = pv;
          pv = 0;
          CoTaskMemFree(v32);
          v10 = v45;
          LOBYTE(v17) = v47;
          goto LABEL_54;
        }
        v19 = CoTaskMemAlloc(0x22u);
        v52 = v19;
        BitmapResultNoCache = -2147024882;
        if ( v19 )
          BitmapResultNoCache = 0;
        if ( BitmapResultNoCache >= 0 )
        {
          if ( v19 )
          {
            *v19 = 0;
            memset_0(v19 + 1, 0, 0x20u);
          }
          else
          {
            MEMORY[0] = 0;
          }
          _o__ui64tow_s(v18, v19, 17, 16);
          v24 = v19;
          goto LABEL_36;
        }
      }
    }
    if ( BitmapResultNoCache == -2147024882 )
      goto LABEL_37;
    goto LABEL_43;
  }
LABEL_56:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v14, &Thumbnails_GetThumbnail_Stop, (unsigned int)BitmapResultNoCache);
  return (unsigned int)BitmapResultNoCache;
}

```

## disassembly

```asm
0x18000a300  push    rbp
0x18000a302  push    rbx
0x18000a303  push    rsi
0x18000a304  push    rdi
0x18000a305  push    r12
0x18000a307  push    r13
0x18000a309  push    r14
0x18000a30b  push    r15
0x18000a30d  lea     rbp, [rsp-28h]
0x18000a312  sub     rsp, 128h
0x18000a319  mov     rax, cs:__security_cookie
0x18000a320  xor     rax, rsp
0x18000a323  mov     [rbp+60h+var_50], rax
0x18000a327  mov     r15d, r9d
0x18000a32a  mov     esi, r8d
0x18000a32d  mov     [rsp+160h+var_10C], r8d
0x18000a332  mov     r13, rdx
0x18000a335  mov     r14, rcx
0x18000a338  mov     rax, [rbp+60h+arg_40]
0x18000a33f  mov     [rsp+160h+var_F8], rax
0x18000a344  mov     rbx, [rbp+60h+arg_28]
0x18000a34b  mov     r12, [rbp+60h+arg_30]
0x18000a352  mov     rdi, [rbp+60h+arg_38]
0x18000a359  mov     [rsp+160h+var_108], rdi
0x18000a35e  test    r12, r12
0x18000a361  jz      short loc_18000A36B
0x18000a363  mov     qword ptr [r12], 0
0x18000a36b  test    rdi, rdi
0x18000a36e  jz      short loc_18000A376
0x18000a370  mov     dword ptr [rdi], 0
0x18000a376  test    rax, rax
0x18000a379  jnz     loc_18000A939
0x18000a37f  mov     edx, r15d; enum WTS_FLAGS
0x18000a382  call    ?_CheckValidGetThumbnailFlags@CThumbnailCache@@AEAAHW4WTS_FLAGS@@@Z; CThumbnailCache::_CheckValidGetThumbnailFlags(WTS_FLAGS)
0x18000a387  test    eax, eax
0x18000a389  jz      loc_18000A97C
0x18000a38f  test    r13, r13
0x18000a392  jz      loc_18000AAB5
0x18000a398  test    byte ptr [r14+300h], 8
0x18000a3a0  jnz     short loc_18000A3B5
0x18000a3a2  call    cs:__imp_GetCurrentThreadId
0x18000a3a8  cmp     [r14+2FCh], eax
0x18000a3af  jnz     loc_18000A719
0x18000a3b5  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18000a3bc  jnz     loc_18000A986
0x18000a3c2  call    cs:__imp_EdpGetIsManaged
0x18000a3c8  test    eax, eax
0x18000a3ca  jnz     loc_18000AAD0
0x18000a3d0  mov     ebx, 80004005h
0x18000a3d5  mov     eax, r15d
0x18000a3d8  and     eax, 24h
0x18000a3db  cmp     al, 24h ; '$'
0x18000a3dd  jz      short loc_18000A41D
0x18000a3df  cmp     byte ptr [r14+2F4h], 0
0x18000a3e7  jz      loc_18000A83A
0x18000a3ed  cmp     byte ptr [r14+2F5h], 0
0x18000a3f5  jz      loc_18000A957
0x18000a3fb  mov     rcx, r14; this
0x18000a3fe  cmp     byte ptr [r14+2F6h], 0
0x18000a406  jnz     loc_18000AAFA
0x18000a40c  call    ?ResetCache@CThumbnailCache@@AEAAJXZ; CThumbnailCache::ResetCache(void)
0x18000a411  mov     ebx, eax
0x18000a413  test    eax, eax
0x18000a415  js      loc_18000AB26
0x18000a41b  xor     ebx, ebx
0x18000a41d  mov     eax, ebx
0x18000a41f  shr     eax, 1Fh
0x18000a422  mov     [rsp+160h+var_100], eax
0x18000a426  test    ebx, ebx
0x18000a428  js      loc_18000A7F7
0x18000a42e  mov     eax, [r14+300h]
0x18000a435  and     eax, 1
0x18000a438  mov     [rbp+60h+var_98], eax
0x18000a43b  xor     ebx, ebx
0x18000a43d  mov     [rbp+60h+var_B0], rbx
0x18000a441  mov     [rbp+60h+pv], rbx
0x18000a445  xor     ecx, ecx; pv
0x18000a447  call    cs:__imp_CoTaskMemFree
0x18000a44d  mov     [rbp+60h+var_94], ebx
0x18000a450  mov     [rbp+60h+var_A8], rbx
0x18000a454  mov     edi, ebx
0x18000a456  mov     [rbp+60h+var_D0], rbx
0x18000a45a  mov     esi, ebx
0x18000a45c  mov     [rbp+60h+var_C0], rbx
0x18000a460  movups  xmm0, xmmword ptr cs:PKEY_DateModified.fmtid.Data1
0x18000a467  movups  [rbp+60h+var_78], xmm0
0x18000a46b  mov     eax, cs:PKEY_DateModified.pid
0x18000a471  mov     [rbp+60h+var_68], eax
0x18000a474  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x18000a47b  movups  [rbp+60h+var_64], xmm0
0x18000a47f  mov     eax, cs:PKEY_ThumbnailCacheId.pid
0x18000a485  mov     [rbp+60h+var_54], eax
0x18000a488  mov     [rbp+60h+var_B8], rbx
0x18000a48c  mov     [rbp+60h+var_C8], rbx
0x18000a490  mov     rax, [r13+0]
0x18000a494  mov     rbx, [rax]
0x18000a497  lea     rcx, [rbp+60h+var_C8]
0x18000a49b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a4a0  lea     r8, [rbp+60h+var_C8]
0x18000a4a4  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18000a4ab  mov     rcx, r13
0x18000a4ae  mov     rax, rbx
0x18000a4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b6  mov     ebx, eax
0x18000a4b8  test    eax, eax
0x18000a4ba  js      short loc_18000A504
0x18000a4bc  mov     rdi, [rbp+60h+var_C8]
0x18000a4c0  mov     rax, [rdi]
0x18000a4c3  mov     rbx, [rax+50h]
0x18000a4c7  lea     rcx, [rbp+60h+var_B8]
0x18000a4cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a4d0  lea     rax, [rbp+60h+var_B8]
0x18000a4d4  mov     [rsp+160h+var_138], rax
0x18000a4d9  lea     rax, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18000a4e0  mov     [rsp+160h+var_140], rax
0x18000a4e5  mov     r9d, 8
0x18000a4eb  mov     r8d, 2
0x18000a4f1  lea     rdx, [rbp+60h+var_78]
0x18000a4f5  mov     rcx, rdi
0x18000a4f8  mov     rax, rbx
0x18000a4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a500  mov     ebx, eax
0x18000a502  mov     edi, esi
0x18000a504  mov     rcx, [rbp+60h+var_C8]
0x18000a508  test    rcx, rcx
0x18000a50b  jz      short loc_18000A522
0x18000a50d  mov     [rbp+60h+var_C8], 0
0x18000a515  mov     rax, [rcx]
0x18000a518  mov     rax, [rax+10h]
0x18000a51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a521  nop
0x18000a522  test    ebx, ebx
0x18000a524  js      loc_18000A6E4
0x18000a52a  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x18000a531  mov     ecx, cs:PKEY_ThumbnailCacheId.pid
0x18000a537  xor     eax, eax
0x18000a539  mov     word ptr [rbp+60h+pvar], ax
0x18000a53d  movaps  [rsp+160h+var_F0], xmm0
0x18000a542  mov     [rbp+60h+var_E0], ecx
0x18000a545  mov     rcx, [rbp+60h+var_B8]
0x18000a549  mov     rax, [rcx]
0x18000a54c  lea     r8, [rbp+60h+pvar]
0x18000a550  lea     rdx, [rsp+160h+var_F0]
0x18000a555  mov     rax, [rax+28h]
0x18000a559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a55e  mov     ebx, eax
0x18000a560  movzx   eax, word ptr [rbp+60h+pvar]
0x18000a564  test    ebx, ebx
0x18000a566  js      short loc_18000A576
0x18000a568  test    ax, ax
0x18000a56b  jnz     loc_18000AA90
0x18000a571  mov     ebx, 80070490h
0x18000a576  lea     rcx, [rbp+60h+pvar]; pvar
0x18000a57a  call    cs:__imp_PropVariantClear
0x18000a580  test    ebx, ebx
0x18000a582  js      loc_18000A6E4
0x18000a588  xor     ebx, ebx
0x18000a58a  mov     [rbp+60h+var_C0], rbx
0x18000a58e  mov     [rbp+60h+var_C8], rbx
0x18000a592  mov     ecx, 11h
0x18000a597  mov     eax, 2
0x18000a59c  mul     rcx
0x18000a59f  test    rdx, rdx
0x18000a5a2  jnz     loc_18000A6EC
0x18000a5a8  mov     rcx, rax; cb
0x18000a5ab  call    cs:__imp_CoTaskMemAlloc
0x18000a5b1  mov     rsi, rax
0x18000a5b4  mov     [rbp+60h+var_C0], rax
0x18000a5b8  mov     eax, ebx
0x18000a5ba  mov     ebx, 8007000Eh
0x18000a5bf  test    rsi, rsi
0x18000a5c2  cmovnz  ebx, eax
0x18000a5c5  test    ebx, ebx
0x18000a5c7  js      loc_18000A6E4
0x18000a5cd  test    rsi, rsi
0x18000a5d0  jz      loc_18000AB43
0x18000a5d6  xor     ecx, ecx
0x18000a5d8  mov     edx, 11h
0x18000a5dd  mov     rax, rsi
0x18000a5e0  xor     r9d, r9d
0x18000a5e3  lea     r10, unk_1800509F8
0x18000a5ea  nop     word ptr [rax+rax+00h]
0x18000a5f0  test    rcx, rcx
0x18000a5f3  jz      short loc_18000A617
0x18000a5f5  movzx   r8d, word ptr [r10]
0x18000a5f9  test    r8w, r8w
0x18000a5fd  jz      short loc_18000A617
0x18000a5ff  add     r10, 2
0x18000a603  mov     [rax], r8w
0x18000a607  add     rax, 2
0x18000a60b  dec     rcx
0x18000a60e  inc     r9
0x18000a611  sub     rdx, 1
0x18000a615  jnz     short loc_18000A5F0
0x18000a617  lea     r10, [r9-1]
0x18000a61b  test    rdx, rdx
0x18000a61e  cmovnz  r10, r9
0x18000a622  lea     rcx, [rax-2]
0x18000a626  cmovnz  rcx, rax
0x18000a62a  xor     eax, eax
0x18000a62c  mov     [rcx], ax
0x18000a62f  test    rdx, rdx
0x18000a632  jnz     loc_18000A902
0x18000a638  mov     r9d, 10h
0x18000a63e  mov     r8d, 11h
0x18000a644  mov     rdx, rsi
0x18000a647  mov     rcx, rdi
0x18000a64a  call    cs:__imp__o__ui64tow_s
0x18000a650  mov     rdi, rsi
0x18000a653  mov     rcx, r13; struct IShellItem *
0x18000a656  call    ?IsShellItemEncrypted@@YAHPEAUIShellItem@@@Z; IsShellItemEncrypted(IShellItem *)
0x18000a65b  neg     eax
0x18000a65d  sbb     esi, esi
0x18000a65f  add     esi, 2
0x18000a662  xor     eax, eax
0x18000a664  mov     [rbp+60h+var_C8], rax
0x18000a668  mov     rcx, [rbp+60h+pv]; pv
0x18000a66c  mov     [rbp+60h+pv], rax
0x18000a670  call    cs:__imp_CoTaskMemFree
0x18000a676  mov     rcx, [rbp+60h+pv]; pv
0x18000a67a  mov     [rbp+60h+pv], 0
0x18000a682  call    cs:__imp_CoTaskMemFree
0x18000a688  mov     [rbp+60h+pv], rdi
0x18000a68c  mov     [rbp+60h+var_94], esi
0x18000a68f  mov     rax, [rbp+60h+var_D0]
0x18000a693  mov     [rbp+60h+var_B0], rax
0x18000a697  mov     dword ptr [rbp+60h+var_A8], 0
0x18000a69e  mov     dword ptr [rbp+60h+var_A8+4], 13h
0x18000a6a5  mov     rsi, [rbp+60h+var_C8]
0x18000a6a9  lea     rcx, [rbp+60h+var_B8]
0x18000a6ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a6b2  nop
0x18000a6b3  mov     rcx, rsi; pv
0x18000a6b6  call    cs:__imp_CoTaskMemFree
0x18000a6bc  test    ebx, ebx
0x18000a6be  js      loc_18000A7D8
0x18000a6c4  mov     eax, [r14+300h]
0x18000a6cb  test    al, 1
0x18000a6cd  jnz     short loc_18000A6D9
0x18000a6cf  test    r15b, 20h
0x18000a6d3  jz      loc_18000A759
0x18000a6d9  mov     esi, [rsp+160h+var_10C]
0x18000a6dd  xor     edi, edi
0x18000a6df  jmp     loc_18000A780
0x18000a6e4  cmp     ebx, 8007000Eh
0x18000a6ea  jz      short loc_18000A6A9
0x18000a6ec  lea     rax, [rbp+60h+var_C0]
0x18000a6f0  mov     [rsp+160h+var_140], rax; unsigned __int16 **
0x18000a6f5  lea     r9, [rbp+60h+var_D0]; unsigned __int64 *
0x18000a6f9  mov     r8, [rbp+60h+var_B8]; struct IPropertyStore *
0x18000a6fd  mov     rdx, r13; struct IShellItem *
0x18000a700  lea     rcx, [rbp+60h+var_B0]; this
0x18000a704  call    ?_NonLocalFSInitFallback@CThumbnailMoniker@@AEBAJPEAUIShellItem@@PEAUIPropertyStore@@PEA_KPEAPEAG@Z; CThumbnailMoniker::_NonLocalFSInitFallback(IShellItem *,IPropertyStore *,unsigned __int64 *,ushort * *)
0x18000a709  mov     ebx, eax
0x18000a70b  test    eax, eax
0x18000a70d  jns     loc_18000AB4B
0x18000a713  mov     rsi, [rbp+60h+var_C0]
0x18000a717  jmp     short loc_18000A6A9
0x18000a719  mov     rcx, [rbp+68h]; this
0x18000a71d  mov     r9d, 800705A4h; char *
0x18000a723  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000a72a  mov     edx, 1326h; void *
0x18000a72f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a734  mov     rcx, [rbp+68h]; this
0x18000a738  mov     r9d, 800705A4h; char *
0x18000a73e  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000a745  mov     edx, 126Eh; void *
0x18000a74a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a74f  mov     eax, 800705A4h
0x18000a754  jmp     loc_18000A81A
0x18000a759  mov     esi, [rsp+160h+var_10C]
0x18000a75d  test    al, 2
0x18000a75f  jnz     loc_18000A86F
0x18000a765  cmp     esi, 0A00h
0x18000a76b  ja      loc_18000A6DD
0x18000a771  cmp     [rbp+60h+var_94], 1
0x18000a775  jz      loc_18000A944
0x18000a77b  mov     edi, 1
0x18000a780  test    r15b, 8
0x18000a784  jnz     loc_18000AB54
0x18000a78a  xor     eax, eax
0x18000a78c  mov     dword ptr [rbp+60h+var_C0], eax
0x18000a78f  mov     dword ptr [rbp+60h+var_C8], eax
0x18000a792  lea     rax, [rbp+60h+var_C8]
0x18000a796  mov     [rsp+160h+var_118], rax
0x18000a79b  lea     rax, [rbp+60h+var_C0]
0x18000a79f  mov     [rsp+160h+var_120], rax
0x18000a7a4  mov     [rsp+160h+var_128], r12
0x18000a7a9  mov     dword ptr [rsp+160h+var_130], edi
0x18000a7ad  mov     eax, [rbp+60h+arg_20]
0x18000a7b3  mov     dword ptr [rsp+160h+var_138], eax
0x18000a7b7  mov     dword ptr [rsp+160h+var_140], r15d
0x18000a7bc  mov     r9d, esi
0x18000a7bf  mov     r8, r13
0x18000a7c2  lea     rdx, [rbp+60h+var_B0]
0x18000a7c6  mov     rcx, r14
0x18000a7c9  call    ?_GetThumbnailImpl@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@PEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@HPEAPEAUIBitmapResult@@PEAH5@Z; CThumbnailCache::_GetThumbnailImpl(CThumbnailMoniker &,IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,int,IBitmapResult * *,int *,int *)
0x18000a7ce  mov     ebx, eax
0x18000a7d0  test    eax, eax
0x18000a7d2  jns     loc_18000A8A3
  ... truncated ...
```
