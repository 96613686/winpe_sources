# CThemeThumbnail::_RenderDesktopBackground(void)

- ea: `0x1800581bc`
- end: `0x18005882d`
- name: `?_RenderDesktopBackground@CThemeThumbnail@@AEAAXXZ`
- size: `1649`
- prototype: `void __fastcall(CThemeThumbnail *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057750`
- `0x180057c90`

## callees

- `0x180003394`
- `0x18000ab00`
- `0x18000ab10`
- `0x18000b328`
- `0x180029324`
- `0x180031704`
- `0x1800358c0`
- `0x18003633c`
- `0x180042f84`
- `0x180043224`
- `0x1800578c0`
- `0x1800579b0`
- `0x180057aa4`
- `0x180057ad8`
- `0x1800581bc`
- `0x180058834`
- `0x180058954`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005832f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005832f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585b9`
- `GDI32!DeleteObject` at `0x18005875d`
- `GDI32!DeleteObject` at `0x1800587be`
- `GDI32!DeleteObject` at `0x18005875d`
- `GDI32!DeleteObject` at `0x1800587be`
- `GDI32!CreateRectRgn` at `0x180058738`
- `GDI32!CreateRectRgn` at `0x180058792`
- `GDI32!CreateRectRgn` at `0x180058738`
- `GDI32!CreateRectRgn` at `0x180058792`
- `GDI32!GetObjectW` at `0x18005864a`
- `GDI32!GetObjectW` at `0x18005864a`
- `USER32!InflateRect` at `0x18005877a`
- `USER32!InflateRect` at `0x18005877a`
- `USER32!GetSystemMetrics` at `0x18005845b`
- `USER32!GetSystemMetrics` at `0x18005845b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800584f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005861f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800584f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005861f`

## pseudocode

```c
void __fastcall CThemeThumbnail::_RenderDesktopBackground(CThemeThumbnail *this)
{
  int v2; // edi
  unsigned int v3; // esi
  int v4; // r12d
  int v5; // r13d
  CThemeThumbnail *v6; // rcx
  unsigned int v7; // r15d
  unsigned int i; // edi
  HBITMAP Image; // r14
  HBITMAP BitmapWithWic; // rax
  HBITMAP v11; // rdi
  void *p_rc; // rcx
  char v13; // r15
  CThemeThumbnail *v14; // rcx
  unsigned int SystemMetrics; // r14d
  unsigned int v16; // edi
  unsigned int v17; // r13d
  HBITMAP v18; // r8
  __int64 v19; // r8
  int v20; // edi
  HANDLE v21; // rcx
  HRGN RectRgn; // rax
  HRGN v23; // r15
  HRGN v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  HRGN v27; // r14
  unsigned __int16 *v28; // r9
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  struct ILayerComposer *v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE h; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT rc; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+68h] [rbp-98h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF

  v31 = 0;
  memset_0(v36, 0, 0x208u);
  h = 0;
  ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v33);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 9) + 280LL))(*((_QWORD *)this + 9), &v33);
  v3 = 3;
  if ( v2 >= 0 && v33 && !(unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow() )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 72LL))(v33);
    v5 = 1;
    v30 = 0;
    if ( CThemeThumbnail::_CreateThumbnailLayerComposer(this, &v30) < 0 )
      goto LABEL_44;
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&rc);
    if ( (*(int (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v33 + 88LL))(v33, &rc) < 0 )
    {
      if ( v4 )
      {
        BitmapWithWic = PremultiplyLoadBitmapWithWic((HINSTANCE)v6, 0x261u);
        v11 = BitmapWithWic;
        if ( BitmapWithWic )
        {
          CThemeThumbnail::_AddRssToImage(this, BitmapWithWic);
          (*(void (__fastcall **)(struct ILayerComposer *, _QWORD, HBITMAP, _QWORD))(*(_QWORD *)v30 + 40LL))(
            v30,
            0,
            v11,
            0);
        }
      }
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&rc.left + 24LL))(*(_QWORD *)&rc.left);
      for ( i = 0; i < v7; ++i )
      {
        if ( i >= 3 )
          break;
        pv = 0;
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, LPVOID *))(**(_QWORD **)&rc.left + 32LL))(
               *(_QWORD *)&rc.left,
               i,
               &pv) >= 0 )
        {
          if ( !i )
            StringCchCopyW(v36, 0x104u, (const unsigned __int16 *)pv);
          Image = ThumbnailLoadImage((LPCWSTR)pv);
          CoTaskMemFree(pv);
          if ( Image )
            (*(void (__fastcall **)(struct ILayerComposer *, _QWORD, HBITMAP, _QWORD))(*(_QWORD *)v30 + 40LL))(
              v30,
              i,
              Image,
              0);
        }
      }
      if ( v4 )
      {
        pv = 0;
        if ( (*(int (__fastcall **)(struct ILayerComposer *, _QWORD, LPVOID *))(*(_QWORD *)v30 + 72LL))(v30, 0, &pv) >= 0 )
          CThemeThumbnail::_AddRssToImage(this, (HBITMAP)pv);
      }
    }
    CThemeThumbnail::_BitmapFromLayerComposer(v6, v30, (HBITMAP *)&h);
    (*(void (__fastcall **)(struct ILayerComposer *))(*(_QWORD *)v30 + 16LL))(v30);
    p_rc = &rc;
    goto LABEL_40;
  }
  v4 = 0;
  v5 = 0;
  LODWORD(v30) = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 9) + 432LL))(*((_QWORD *)this + 9), &v31) >= 0 && v31 )
  {
    *(_QWORD *)&rc.left = 0;
    if ( CThemeThumbnail::_CreateThumbnailLayerComposer(this, (struct ILayerComposer **)&rc) >= 0 )
    {
      v13 = 1;
      SystemMetrics = GetSystemMetrics(80);
      v16 = 0;
      if ( SystemMetrics )
      {
        do
        {
          if ( v16 >= 3 )
            break;
          pv = 0;
          v17 = v16 + 1;
          (*(void (__fastcall **)(_QWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 9) + 448LL))(
            *((_QWORD *)this + 9),
            v16 + 1,
            &pv);
          if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pv) )
          {
            if ( v13 )
            {
              StringCchCopyW(v36, 0x104u, (const unsigned __int16 *)pv);
              v13 = 0;
            }
            v18 = ThumbnailLoadImage((LPCWSTR)pv);
            if ( v18 )
              (*(void (__fastcall **)(_QWORD, _QWORD, HBITMAP, _QWORD))(**(_QWORD **)&rc.left + 40LL))(
                *(_QWORD *)&rc.left,
                v16,
                v18,
                0);
          }
          SysFreeString((BSTR)pv);
          ++v16;
        }
        while ( v17 < SystemMetrics );
        v5 = (int)v30;
      }
      CThemeThumbnail::_BitmapFromLayerComposer(v14, *(struct ILayerComposer **)&rc.left, (HBITMAP *)&h);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rc.left + 16LL))(*(_QWORD *)&rc.left);
    }
  }
  else
  {
    if ( v2 >= 0 && v33 )
    {
      ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&pv);
      if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 88LL))(v19, &pv) >= 0 )
      {
        *(_QWORD *)&rc.left = 0;
        if ( (*(int (__fastcall **)(LPVOID, _QWORD, struct tagRECT *))(*(_QWORD *)pv + 32LL))(pv, 0, &rc) >= 0 )
        {
          h = ThumbnailLoadImage(*(LPCWSTR *)&rc.left);
          StringCchCopyW(v36, 0x104u, *(const unsigned __int16 **)&rc.left);
          CoTaskMemFree(*(LPVOID *)&rc.left);
        }
      }
      p_rc = &pv;
LABEL_40:
      ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(p_rc);
      goto LABEL_44;
    }
    pv = 0;
    (*(void (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 9) + 168LL))(*((_QWORD *)this + 9), &pv);
    if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pv) )
    {
      h = ThumbnailLoadImage((LPCWSTR)pv);
      StringCchCopyW(v36, 0x104u, (const unsigned __int16 *)pv);
    }
    SysFreeString((BSTR)pv);
  }
LABEL_44:
  if ( h )
  {
    rc = 0;
    v35 = 0;
    if ( GetObjectW(h, 32, &rc) )
    {
      *(_OWORD *)((char *)this + 376) = *(_OWORD *)((char *)this + 360);
      CThemeThumbnail::CThumbnailDimensions::s_ScaleAndCenterRect(
        (CThemeThumbnail *)((char *)this + 376),
        rc.top,
        rc.right);
      if ( v5 || v31 )
      {
        *((_DWORD *)this + 94) -= 40;
        *((_DWORD *)this + 97) += 40;
      }
      else
      {
        *((_DWORD *)this + 96) -= 20;
      }
      AlphaDrawImage(*((HDC *)this + 12), (HBITMAP)h, (struct tagRECT *)((char *)this + 376));
    }
    v20 = 1;
    v21 = h;
    goto LABEL_56;
  }
  v20 = 0;
  LODWORD(v30) = 0;
  (*(void (__fastcall **)(_QWORD, struct ILayerComposer **))(**((_QWORD **)this + 9) + 520LL))(
    *((_QWORD *)this + 9),
    &v30);
  LODWORD(v30) = BYTE2(v30) | ((((unsigned __int8)v30 << 8) | ((unsigned __int16)v30 >> 8)) << 8) | 0xFF000000;
  *(_OWORD *)((char *)this + 376) = *(_OWORD *)((char *)this + 360);
  CThemeThumbnail::CThumbnailDimensions::s_ScaleAndCenterRect((CThemeThumbnail *)((char *)this + 376), 0x780u, 0x4B0u);
  RectRgn = CreateRectRgn(
              *((_DWORD *)this + 94),
              *((_DWORD *)this + 95),
              *((_DWORD *)this + 96),
              *((_DWORD *)this + 97));
  v23 = RectRgn;
  if ( RectRgn )
  {
    AlphaFillRegion(*((HDC *)this + 12), 0xFF5B5B5B, RectRgn, (struct tagRECT *)((char *)this + 376));
    DeleteObject(v23);
  }
  rc = *(struct tagRECT *)((char *)this + 376);
  InflateRect(&rc, -4, -4);
  v24 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
  v27 = v24;
  if ( v24 )
  {
    AlphaFillRegion(*((HDC *)this + 12), (unsigned int)v30 | 0xFF000000, v24, &rc);
    v21 = v27;
LABEL_56:
    DeleteObject(v21);
  }
  if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
  {
    v28 = v36;
    if ( !v20 )
      v28 = (unsigned __int16 *)&Default;
    if ( !v4 )
    {
      if ( v5 )
        v3 = 2;
      else
        v3 = v20 != 0;
    }
    McTemplateU0qz_EtwEventWriteTransfer(v26, v25, v3, v28);
  }
  ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v33);
}

```

## disassembly

```asm
0x1800581bc  push    rbp
0x1800581be  push    rbx
0x1800581bf  push    rsi
0x1800581c0  push    rdi
0x1800581c1  push    r12
0x1800581c3  push    r13
0x1800581c5  push    r14
0x1800581c7  push    r15
0x1800581c9  lea     rbp, [rsp-1A8h]
0x1800581d1  sub     rsp, 2A8h
0x1800581d8  mov     rax, cs:__security_cookie
0x1800581df  xor     rax, rsp
0x1800581e2  mov     [rbp+1E0h+var_50], rax
0x1800581e9  mov     rbx, rcx
0x1800581ec  mov     [rsp+2E0h+var_2A0], 0
0x1800581f4  xor     edx, edx; Val
0x1800581f6  mov     r8d, 208h; Size
0x1800581fc  lea     rcx, [rbp+1E0h+var_260]; void *
0x180058200  call    memset_0
0x180058205  mov     [rsp+2E0h+h], 0
0x18005820e  lea     rcx, [rsp+2E0h+var_290]
0x180058213  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180058218  nop
0x180058219  mov     rcx, [rbx+48h]
0x18005821d  mov     rax, [rcx]
0x180058220  lea     rdx, [rsp+2E0h+var_290]
0x180058225  mov     rax, [rax+118h]
0x18005822c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058231  mov     edi, eax
0x180058233  mov     esi, 3
0x180058238  test    eax, eax
0x18005823a  js      loc_180058403
0x180058240  cmp     [rsp+2E0h+var_290], 0
0x180058246  jz      loc_180058403
0x18005824c  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x180058251  test    eax, eax
0x180058253  jnz     loc_180058403
0x180058259  mov     rcx, [rsp+2E0h+var_290]
0x18005825e  mov     rax, [rcx]
0x180058261  mov     rax, [rax+48h]
0x180058265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005826a  mov     r12d, eax
0x18005826d  lea     r13d, [rsi-2]
0x180058271  mov     [rsp+2E0h+var_2A8], 0
0x18005827a  lea     rdx, [rsp+2E0h+var_2A8]; struct ILayerComposer **
0x18005827f  mov     rcx, rbx; this
0x180058282  call    ?_CreateThumbnailLayerComposer@CThemeThumbnail@@AEAAJPEAPEAUILayerComposer@@@Z; CThemeThumbnail::_CreateThumbnailLayerComposer(ILayerComposer * *)
0x180058287  test    eax, eax
0x180058289  js      loc_180058625
0x18005828f  lea     rcx, [rsp+2E0h+rc]
0x180058294  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180058299  nop
0x18005829a  mov     rcx, [rsp+2E0h+var_290]
0x18005829f  mov     rax, [rcx]
0x1800582a2  lea     rdx, [rsp+2E0h+rc]
0x1800582a7  mov     rax, [rax+58h]
0x1800582ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582b0  test    eax, eax
0x1800582b2  js      loc_18005839A
0x1800582b8  mov     rcx, qword ptr [rsp+2E0h+rc.left]
0x1800582bd  mov     rax, [rcx]
0x1800582c0  mov     rax, [rax+18h]
0x1800582c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582c9  mov     r15d, eax
0x1800582cc  xor     edi, edi
0x1800582ce  test    eax, eax
0x1800582d0  jz      loc_180058361
0x1800582d6  cmp     edi, esi
0x1800582d8  jnb     loc_180058361
0x1800582de  mov     [rsp+2E0h+pv], 0
0x1800582e7  mov     r9, qword ptr [rsp+2E0h+rc.left]
0x1800582ec  mov     rcx, [r9]
0x1800582ef  mov     rax, [rcx+20h]
0x1800582f3  lea     r8, [rsp+2E0h+pv]
0x1800582f8  mov     edx, edi
0x1800582fa  mov     rcx, r9
0x1800582fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058302  test    eax, eax
0x180058304  js      short loc_180058356
0x180058306  test    edi, edi
0x180058308  jnz     short loc_18005831D
0x18005830a  mov     r8, [rsp+2E0h+pv]; unsigned __int16 *
0x18005830f  mov     edx, 104h; unsigned __int64
0x180058314  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180058318  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005831d  mov     rcx, [rsp+2E0h+pv]; pszPath
0x180058322  call    ?ThumbnailLoadImage@@YAPEAUHBITMAP__@@PEBG@Z; ThumbnailLoadImage(ushort const *)
0x180058327  mov     r14, rax
0x18005832a  mov     rcx, [rsp+2E0h+pv]; pv
0x18005832f  call    cs:__imp_CoTaskMemFree
0x180058335  test    r14, r14
0x180058338  jz      short loc_180058356
0x18005833a  mov     r10, [rsp+2E0h+var_2A8]
0x18005833f  mov     rcx, [r10]
0x180058342  mov     rax, [rcx+28h]
0x180058346  xor     r9d, r9d
0x180058349  mov     r8, r14
0x18005834c  mov     edx, edi
0x18005834e  mov     rcx, r10
0x180058351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058356  inc     edi
0x180058358  cmp     edi, r15d
0x18005835b  jb      loc_1800582D6
0x180058361  test    r12d, r12d
0x180058364  jz      short loc_1800583D8
0x180058366  mov     [rsp+2E0h+pv], 0
0x18005836f  mov     rcx, [rsp+2E0h+var_2A8]
0x180058374  mov     rax, [rcx]
0x180058377  lea     r8, [rsp+2E0h+pv]
0x18005837c  xor     edx, edx
0x18005837e  mov     rax, [rax+48h]
0x180058382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058387  test    eax, eax
0x180058389  js      short loc_1800583D8
0x18005838b  mov     rdx, [rsp+2E0h+pv]; HBITMAP
0x180058390  mov     rcx, rbx; this
0x180058393  call    ?_AddRssToImage@CThemeThumbnail@@AEAAXPEAUHBITMAP__@@@Z; CThemeThumbnail::_AddRssToImage(HBITMAP__ *)
0x180058398  jmp     short loc_1800583D8
0x18005839a  test    r12d, r12d
0x18005839d  jz      short loc_1800583D8
0x18005839f  mov     edx, 261h; unsigned int
0x1800583a4  call    ?PremultiplyLoadBitmapWithWic@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@I@Z; PremultiplyLoadBitmapWithWic(HINSTANCE__ *,uint)
0x1800583a9  mov     rdi, rax
0x1800583ac  test    rax, rax
0x1800583af  jz      short loc_1800583D8
0x1800583b1  mov     rdx, rax; HBITMAP
0x1800583b4  mov     rcx, rbx; this
0x1800583b7  call    ?_AddRssToImage@CThemeThumbnail@@AEAAXPEAUHBITMAP__@@@Z; CThemeThumbnail::_AddRssToImage(HBITMAP__ *)
0x1800583bc  mov     r10, [rsp+2E0h+var_2A8]
0x1800583c1  mov     rcx, [r10]
0x1800583c4  mov     rax, [rcx+28h]
0x1800583c8  xor     r9d, r9d
0x1800583cb  mov     r8, rdi
0x1800583ce  xor     edx, edx
0x1800583d0  mov     rcx, r10
0x1800583d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583d8  lea     r8, [rsp+2E0h+h]; HBITMAP *
0x1800583dd  mov     rdx, [rsp+2E0h+var_2A8]; struct ILayerComposer *
0x1800583e2  call    ?_BitmapFromLayerComposer@CThemeThumbnail@@AEAAXPEAUILayerComposer@@PEAPEAUHBITMAP__@@@Z; CThemeThumbnail::_BitmapFromLayerComposer(ILayerComposer *,HBITMAP__ * *)
0x1800583e7  mov     rcx, [rsp+2E0h+var_2A8]
0x1800583ec  mov     rax, [rcx]
0x1800583ef  mov     rax, [rax+10h]
0x1800583f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583f8  nop
0x1800583f9  lea     rcx, [rsp+2E0h+rc]
0x1800583fe  jmp     loc_1800585C5
0x180058403  xor     r12d, r12d
0x180058406  xor     r13d, r13d
0x180058409  mov     dword ptr [rsp+2E0h+var_2A8], r13d
0x18005840e  mov     rcx, [rbx+48h]
0x180058412  mov     rax, [rcx]
0x180058415  lea     rdx, [rsp+2E0h+var_2A0]
0x18005841a  mov     rax, [rax+1B0h]
0x180058421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058426  test    eax, eax
0x180058428  js      loc_180058534
0x18005842e  cmp     [rsp+2E0h+var_2A0], r12d
0x180058433  jz      loc_180058534
0x180058439  mov     qword ptr [rsp+2E0h+rc.left], r12
0x18005843e  lea     rdx, [rsp+2E0h+rc]; struct ILayerComposer **
0x180058443  mov     rcx, rbx; this
0x180058446  call    ?_CreateThumbnailLayerComposer@CThemeThumbnail@@AEAAJPEAPEAUILayerComposer@@@Z; CThemeThumbnail::_CreateThumbnailLayerComposer(ILayerComposer * *)
0x18005844b  test    eax, eax
0x18005844d  js      loc_180058625
0x180058453  mov     r15b, 1
0x180058456  lea     ecx, [r12+50h]; nIndex
0x18005845b  call    cs:__imp_GetSystemMetrics
0x180058461  mov     r14d, eax
0x180058464  xor     edi, edi
0x180058466  test    eax, eax
0x180058468  jz      loc_18005850F
0x18005846e  cmp     edi, esi
0x180058470  jnb     loc_18005850A
0x180058476  mov     [rsp+2E0h+pv], 0
0x18005847f  mov     rcx, [rbx+48h]
0x180058483  lea     r13d, [rdi+1]
0x180058487  mov     rax, [rcx]
0x18005848a  lea     r8, [rsp+2E0h+pv]
0x18005848f  mov     edx, r13d
0x180058492  mov     rax, [rax+1C0h]
0x180058499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005849e  lea     rcx, [rsp+2E0h+pv]; this
0x1800584a3  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x1800584a8  test    eax, eax
0x1800584aa  jz      short loc_1800584F3
0x1800584ac  test    r15b, r15b
0x1800584af  jz      short loc_1800584C7
0x1800584b1  mov     r8, [rsp+2E0h+pv]; unsigned __int16 *
0x1800584b6  mov     edx, 104h; unsigned __int64
0x1800584bb  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x1800584bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800584c4  xor     r15b, r15b
0x1800584c7  mov     rcx, [rsp+2E0h+pv]; pszPath
0x1800584cc  call    ?ThumbnailLoadImage@@YAPEAUHBITMAP__@@PEBG@Z; ThumbnailLoadImage(ushort const *)
0x1800584d1  mov     r8, rax
0x1800584d4  test    rax, rax
0x1800584d7  jz      short loc_1800584F3
0x1800584d9  mov     r10, qword ptr [rsp+2E0h+rc.left]
0x1800584de  mov     rcx, [r10]
0x1800584e1  mov     rax, [rcx+28h]
0x1800584e5  xor     r9d, r9d
0x1800584e8  mov     edx, edi
0x1800584ea  mov     rcx, r10
0x1800584ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584f2  nop
0x1800584f3  mov     rcx, [rsp+2E0h+pv]; bstrString
0x1800584f8  call    cs:__imp_SysFreeString
0x1800584fe  mov     edi, r13d
0x180058501  cmp     r13d, r14d
0x180058504  jb      loc_18005846E
0x18005850a  mov     r13d, dword ptr [rsp+2E0h+var_2A8]
0x18005850f  lea     r8, [rsp+2E0h+h]; HBITMAP *
0x180058514  mov     rdx, qword ptr [rsp+2E0h+rc.left]; struct ILayerComposer *
0x180058519  call    ?_BitmapFromLayerComposer@CThemeThumbnail@@AEAAXPEAUILayerComposer@@PEAPEAUHBITMAP__@@@Z; CThemeThumbnail::_BitmapFromLayerComposer(ILayerComposer *,HBITMAP__ * *)
0x18005851e  mov     rcx, qword ptr [rsp+2E0h+rc.left]
0x180058523  mov     rax, [rcx]
0x180058526  mov     rax, [rax+10h]
0x18005852a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005852f  jmp     loc_180058625
0x180058534  test    edi, edi
0x180058536  js      loc_1800585CC
0x18005853c  mov     r8, [rsp+2E0h+var_290]
0x180058541  test    r8, r8
0x180058544  jz      loc_1800585CC
0x18005854a  lea     rcx, [rsp+2E0h+pv]
0x18005854f  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180058554  nop
0x180058555  mov     rax, [r8]
0x180058558  lea     rdx, [rsp+2E0h+pv]
0x18005855d  mov     rcx, r8
0x180058560  mov     rax, [rax+58h]
0x180058564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058569  test    eax, eax
0x18005856b  js      short loc_1800585C0
0x18005856d  mov     qword ptr [rsp+2E0h+rc.left], 0
0x180058576  mov     rcx, [rsp+2E0h+pv]
0x18005857b  mov     rax, [rcx]
0x18005857e  lea     r8, [rsp+2E0h+rc]
0x180058583  xor     edx, edx
0x180058585  mov     rax, [rax+20h]
0x180058589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005858e  test    eax, eax
0x180058590  js      short loc_1800585C0
0x180058592  mov     rcx, qword ptr [rsp+2E0h+rc.left]; pszPath
0x180058597  call    ?ThumbnailLoadImage@@YAPEAUHBITMAP__@@PEBG@Z; ThumbnailLoadImage(ushort const *)
0x18005859c  mov     [rsp+2E0h+h], rax
0x1800585a1  mov     r8, qword ptr [rsp+2E0h+rc.left]; unsigned __int16 *
0x1800585a6  mov     edx, 104h; unsigned __int64
0x1800585ab  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x1800585af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800585b4  mov     rcx, qword ptr [rsp+2E0h+rc.left]; pv
0x1800585b9  call    cs:__imp_CoTaskMemFree
0x1800585bf  nop
0x1800585c0  lea     rcx, [rsp+2E0h+pv]
0x1800585c5  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x1800585ca  jmp     short loc_180058625
0x1800585cc  mov     [rsp+2E0h+pv], r12
0x1800585d1  mov     rcx, [rbx+48h]
0x1800585d5  mov     rax, [rcx]
0x1800585d8  lea     rdx, [rsp+2E0h+pv]
0x1800585dd  mov     rax, [rax+0A8h]
0x1800585e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585e9  lea     rcx, [rsp+2E0h+pv]; this
0x1800585ee  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x1800585f3  test    eax, eax
0x1800585f5  jz      short loc_18005861A
0x1800585f7  mov     rcx, [rsp+2E0h+pv]; pszPath
0x1800585fc  call    ?ThumbnailLoadImage@@YAPEAUHBITMAP__@@PEBG@Z; ThumbnailLoadImage(ushort const *)
0x180058601  mov     [rsp+2E0h+h], rax
0x180058606  mov     r8, [rsp+2E0h+pv]; unsigned __int16 *
0x18005860b  mov     edx, 104h; unsigned __int64
0x180058610  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180058614  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058619  nop
0x18005861a  mov     rcx, [rsp+2E0h+pv]; bstrString
0x18005861f  call    cs:__imp_SysFreeString
0x180058625  mov     rcx, [rsp+2E0h+h]; h
0x18005862a  test    rcx, rcx
0x18005862d  jz      loc_1800586B6
0x180058633  xorps   xmm0, xmm0
0x180058636  movups  xmmword ptr [rsp+2E0h+rc.left], xmm0
0x18005863b  movups  [rsp+2E0h+var_278], xmm0
0x180058640  lea     r8, [rsp+2E0h+rc]; pv
0x180058645  mov     edx, 20h ; ' '; c
0x18005864a  call    cs:__imp_GetObjectW
0x180058650  test    eax, eax
0x180058652  jz      short loc_1800586A7
0x180058654  lea     rdi, [rbx+178h]
0x18005865b  movups  xmm0, xmmword ptr [rbx+168h]
0x180058662  movdqu  xmmword ptr [rdi], xmm0
0x180058666  mov     r8d, [rsp+2E0h+rc.right]; unsigned int
0x18005866b  mov     edx, [rsp+2E0h+rc.top]; unsigned int
0x18005866f  mov     rcx, rdi; struct WTL::CRect *
0x180058672  call    ?s_ScaleAndCenterRect@CThumbnailDimensions@CThemeThumbnail@@SAXPEAVCRect@WTL@@II@Z; CThemeThumbnail::CThumbnailDimensions::s_ScaleAndCenterRect(WTL::CRect *,uint,uint)
0x180058677  test    r13d, r13d
0x18005867a  jnz     short loc_18005868C
0x18005867c  cmp     [rsp+2E0h+var_2A0], r13d
0x180058681  jnz     short loc_18005868C
0x180058683  add     dword ptr [rbx+180h], 0FFFFFFECh
0x18005868a  jmp     short loc_180058696
  ... truncated ...
```
