# CContentDropTarget::_TransferThumbnailResource(HBITMAP__ *,IPortableDeviceContent *,_GUID const &,ushort const *,CProgressUI *)

- ea: `0x18004123c`
- end: `0x180041aa7`
- name: `?_TransferThumbnailResource@CContentDropTarget@@AEAAJPEAUHBITMAP__@@PEAUIPortableDeviceContent@@AEBU_GUID@@PEBGPEAVCProgressUI@@@Z`
- size: `2155`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, HBITMAP, struct IPortableDeviceContent *, const struct _GUID *, const unsigned __int16 *, struct CProgressUI *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003f890`

## callees

- `0x1800177dc`
- `0x1800285c8`
- `0x18002ea3c`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x1800408e0`
- `0x18004123c`
- `0x180054524`
- `0x1800545c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800418b5`
- `KERNEL32!Sleep` at `0x1800419a8`
- `KERNEL32!Sleep` at `0x1800418b5`
- `KERNEL32!Sleep` at `0x1800419a8`
- `gdiplus!GdipSaveImageToStream` at `0x18004142f`
- `gdiplus!GdipSaveImageToStream` at `0x18004142f`
- `gdiplus!GdipDisposeImage` at `0x180041a41`
- `gdiplus!GdipDisposeImage` at `0x180041a41`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x1800412c0`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x1800412c0`
- `ole32!CreateStreamOnHGlobal` at `0x18004131c`
- `ole32!CreateStreamOnHGlobal` at `0x18004131c`
- `ole32!CoTaskMemFree` at `0x18004154b`
- `ole32!CoTaskMemFree` at `0x18004154b`
- `ole32!CoTaskMemAlloc` at `0x1800414aa`
- `ole32!CoTaskMemAlloc` at `0x1800414aa`
- `ole32!CoCreateInstance` at `0x180041591`
- `ole32!CoCreateInstance` at `0x1800416c5`
- `ole32!CoCreateInstance` at `0x180041591`
- `ole32!CoCreateInstance` at `0x1800416c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CContentDropTarget::_TransferThumbnailResource(
        CContentDropTarget *this,
        HBITMAP a2,
        struct IPortableDeviceContent *a3,
        const struct _GUID *a4,
        const unsigned __int16 *a5,
        struct CProgressUI *a6)
{
  __int64 v10; // r14
  int v11; // ebx
  HRESULT v12; // eax
  CContentDropTarget *v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // r14d
  void *v22; // rax
  void *v23; // rbx
  HRESULT v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  void *v28; // r12
  int v29; // r15d
  int v30; // edi
  int v31; // r15d
  int v32; // edi
  LPVOID pv; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v35; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  _QWORD v42[3]; // [rsp+78h] [rbp-88h] BYREF
  int BitmapFromHBITMAP; // [rsp+90h] [rbp-70h]
  struct _GUID v44; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  SIZE_T cb; // [rsp+C0h] [rbp-40h]

  if ( (int)StartGdiPlus() < 0 )
    return 2147500037LL;
  ppv = 0;
  v40 = 0;
  v39 = 0;
  ppstm = 0;
  v35 = 0;
  v42[1] = &Gdiplus::Image::`vftable';
  v42[0] = 0;
  BitmapFromHBITMAP = GdipCreateBitmapFromHBITMAP(a2, 0, v42);
  v10 = v42[0];
  v42[2] = v42[0];
  v41 = 0;
  memset_0(v45, 0, 0x50u);
  v44 = 0;
  v34 = 0;
  v38 = 0;
  if ( !a2 || !a3 || !a5 )
  {
    v11 = -2147024809;
    goto LABEL_124;
  }
  v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v11 = v12;
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 204;
LABEL_11:
      WPP_SF_d(v14[2], v15, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v12);
      goto LABEL_124;
    }
    goto LABEL_124;
  }
  v16 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&WPD_OBJECT_FORMAT_EXIF.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&WPD_OBJECT_FORMAT_EXIF.Data1 )
    v16 = *(_QWORD *)a4->Data4 - *(_QWORD *)WPD_OBJECT_FORMAT_EXIF.Data4;
  if ( !v16 )
    goto LABEL_26;
  v17 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&WPD_OBJECT_FORMAT_JFIF.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&WPD_OBJECT_FORMAT_JFIF.Data1 )
    v17 = *(_QWORD *)a4->Data4 - *(_QWORD *)WPD_OBJECT_FORMAT_JFIF.Data4;
  if ( v17 )
  {
    v18 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&WPD_OBJECT_FORMAT_BMP.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&WPD_OBJECT_FORMAT_BMP.Data1 )
      v18 = *(_QWORD *)a4->Data4 - *(_QWORD *)WPD_OBJECT_FORMAT_BMP.Data4;
    if ( v18 )
    {
      v20 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&WPD_OBJECT_FORMAT_PNG.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&WPD_OBJECT_FORMAT_PNG.Data1 )
        v20 = *(_QWORD *)a4->Data4 - *(_QWORD *)WPD_OBJECT_FORMAT_PNG.Data4;
      if ( v20 )
        goto LABEL_123;
      v19 = L"image/png";
    }
    else
    {
      v19 = L"image/bmp";
    }
  }
  else
  {
LABEL_26:
    v19 = L"image/jpeg";
  }
  if ( CContentDropTarget::_GetEncoderClsid(v13, v19, &v44) < 0 )
    goto LABEL_123;
  ((void (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v41, 0, 0);
  if ( (unsigned int)GdipSaveImageToStream(v10, ppstm, &v44, 0) )
    goto LABEL_123;
  v12 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v45, 1);
  v11 = v12;
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 205;
      goto LABEL_11;
    }
LABEL_124:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        217,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v11);
    goto LABEL_127;
  }
  v21 = cb;
  if ( !cb || cb > 0xFFFFFFFF )
  {
LABEL_123:
    v11 = -2147467259;
    goto LABEL_124;
  }
  v22 = CoTaskMemAlloc((unsigned int)cb);
  v23 = v22;
  pv = v22;
  if ( !v22 )
  {
    v11 = -2147024882;
    goto LABEL_124;
  }
  memset_0(v22, 0, v21);
  ((void (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v41, 0, 0);
  v24 = ((__int64 (__fastcall *)(LPSTREAM, void *, _QWORD, int *))ppstm->lpVtbl->Read)(ppstm, v23, v21, &v34);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 206;
    goto LABEL_41;
  }
  if ( v34 != v21 )
  {
    v11 = -2147467259;
    goto LABEL_43;
  }
  v24 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &ppv);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 207;
    goto LABEL_41;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const struct _GUID *))(*(_QWORD *)ppv + 216LL))(
          ppv,
          &WPD_RESOURCE_ATTRIBUTE_FORMAT,
          a4);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 208;
    goto LABEL_41;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, _QWORD))(*(_QWORD *)ppv + 104LL))(
          ppv,
          &WPD_RESOURCE_ATTRIBUTE_TOTAL_SIZE,
          v21);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 209;
    goto LABEL_41;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(
          ppv,
          &WPD_OBJECT_ID,
          a5);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 210;
    goto LABEL_41;
  }
  v24 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &v39);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 211;
    goto LABEL_41;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v39 + 40LL))(v39, &WPD_RESOURCE_THUMBNAIL);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 212;
    goto LABEL_41;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, LPVOID))(*(_QWORD *)ppv + 200LL))(
          ppv,
          &WPD_RESOURCE_ATTRIBUTE_RESOURCE_KEY,
          v39);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 213;
    goto LABEL_41;
  }
  v24 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, __int64 *))a3->lpVtbl->Transfer)(a3, &v40);
  v11 = v24;
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v26 = 214;
LABEL_41:
    v27 = (unsigned int)v24;
LABEL_42:
    WPP_SF_d(v25[2], v26, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v27);
LABEL_43:
    v28 = pv;
    goto LABEL_44;
  }
  if ( a6 )
  {
    v29 = 0;
    v30 = 0;
    while ( !*((_DWORD *)a6 + 26) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, struct IUnknown **, int *, _QWORD))(*(_QWORD *)v40 + 64LL))(
              v40,
              ppv,
              &v35,
              &v38,
              0);
      if ( v11 != -2147024726 )
        goto LABEL_97;
      if ( v35 )
        ATL::AtlComPtrAssign(&v35, 0);
      if ( !v29 )
      {
        v29 = 1;
        v30 = 1;
        CProgressUI::_StartMarquee(a6);
      }
      if ( *((_DWORD *)a6 + 26) )
        break;
      Sleep(0x5DCu);
    }
    v11 = -2147023673;
LABEL_97:
    if ( v30 )
      CProgressUI::_StopMarquee(a6);
    if ( *((_DWORD *)a6 + 26) )
    {
      v11 = -2147023673;
LABEL_83:
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_43;
      v26 = 215;
      v27 = (unsigned int)v11;
      goto LABEL_42;
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, struct IUnknown **, int *, _QWORD))(*(_QWORD *)v40 + 64LL))(
            v40,
            ppv,
            &v35,
            &v38,
            0);
  }
  if ( v11 < 0 )
    goto LABEL_83;
  if ( a6 )
  {
    v31 = 0;
    v32 = 0;
    v28 = pv;
    while ( !*((_DWORD *)a6 + 26) )
    {
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, _QWORD, int *))v35->lpVtbl[1].AddRef)(
              v35,
              pv,
              v21,
              &v34);
      if ( v11 != -2147024726 )
        goto LABEL_116;
      if ( !v31 )
      {
        v31 = 1;
        v32 = 1;
        CProgressUI::_StartMarquee(a6);
      }
      if ( *((_DWORD *)a6 + 26) )
        break;
      Sleep(0x5DCu);
    }
    v11 = -2147023673;
LABEL_116:
    if ( v32 )
      CProgressUI::_StopMarquee(a6);
    if ( *((_DWORD *)a6 + 26) )
    {
      v11 = -2147023673;
      goto LABEL_104;
    }
  }
  else
  {
    v28 = pv;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, _QWORD, int *))v35->lpVtbl[1].AddRef)(v35, pv, v21, &v34);
  }
  if ( v11 < 0 )
  {
LABEL_104:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        216,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v11);
    goto LABEL_44;
  }
  ((void (__fastcall *)(struct IUnknown *, __int64))v35->lpVtbl[2].Release)(v35, 1);
  if ( v34 == v21 )
    v11 = -2147024662;
LABEL_44:
  CoTaskMemFree(v28);
  if ( v11 < 0 )
    goto LABEL_124;
LABEL_127:
  GdipDisposeImage(v42[0]);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004123c  mov     [rsp-8+arg_0], rbx
0x180041241  push    rbp
0x180041242  push    rsi
0x180041243  push    rdi
0x180041244  push    r12
0x180041246  push    r13
0x180041248  push    r14
0x18004124a  push    r15
0x18004124c  lea     rbp, [rsp-10h]
0x180041251  sub     rsp, 110h
0x180041258  mov     rax, cs:__security_cookie
0x18004125f  xor     rax, rsp
0x180041262  mov     [rbp+40h+var_40], rax
0x180041266  mov     rdi, r9
0x180041269  mov     r12, r8
0x18004126c  mov     rbx, rdx
0x18004126f  mov     r13, [rbp+40h+arg_20]
0x180041273  mov     rsi, [rbp+40h+arg_28]
0x180041277  call    ?StartGdiPlus@@YAJXZ; StartGdiPlus(void)
0x18004127c  xor     r15d, r15d
0x18004127f  test    eax, eax
0x180041281  jns     short loc_18004128D
0x180041283  mov     eax, 80004005h
0x180041288  jmp     loc_180041A80
0x18004128d  mov     [rsp+140h+var_F8], r15
0x180041292  mov     [rsp+140h+var_D8], r15
0x180041297  mov     [rsp+140h+var_E0], r15
0x18004129c  mov     [rsp+140h+ppstm], r15
0x1800412a1  mov     [rsp+140h+var_100], r15
0x1800412a6  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x1800412ad  mov     [rbp+40h+var_C0], rax
0x1800412b1  mov     [rsp+140h+var_C8], r15
0x1800412b6  lea     r8, [rsp+140h+var_C8]
0x1800412bb  xor     edx, edx
0x1800412bd  mov     rcx, rbx
0x1800412c0  call    cs:__imp_GdipCreateBitmapFromHBITMAP
0x1800412c6  mov     [rbp+40h+var_B0], eax
0x1800412c9  mov     r14, [rsp+140h+var_C8]
0x1800412ce  mov     [rbp+40h+var_B8], r14
0x1800412d2  mov     [rsp+140h+var_D0], r15
0x1800412d7  xor     edx, edx; Val
0x1800412d9  lea     r8d, [rdx+50h]; Size
0x1800412dd  lea     rcx, [rbp+40h+var_90]; void *
0x1800412e1  call    memset_0
0x1800412e6  xorps   xmm0, xmm0
0x1800412e9  movups  xmmword ptr [rbp+40h+var_A8.Data1], xmm0
0x1800412ed  mov     [rsp+140h+var_108], r15d
0x1800412f2  mov     [rsp+140h+var_E8], r15d
0x1800412f7  test    rbx, rbx
0x1800412fa  jnz     short loc_180041306
0x1800412fc  mov     ebx, 80070057h
0x180041301  jmp     loc_180041A0A
0x180041306  test    r12, r12
0x180041309  jz      short loc_1800412FC
0x18004130b  test    r13, r13
0x18004130e  jz      short loc_1800412FC
0x180041310  lea     r8, [rsp+140h+ppstm]; ppstm
0x180041315  mov     edx, 1; fDeleteOnRelease
0x18004131a  xor     ecx, ecx; hGlobal
0x18004131c  call    cs:__imp_CreateStreamOnHGlobal
0x180041322  mov     ebx, eax
0x180041324  test    eax, eax
0x180041326  jns     short loc_180041366
0x180041328  mov     rcx, cs:WPP_GLOBAL_Control
0x18004132f  lea     rdi, WPP_GLOBAL_Control
0x180041336  cmp     rcx, rdi
0x180041339  jz      loc_180041A11
0x18004133f  test    byte ptr [rcx+1Ch], 2
0x180041343  jz      loc_180041A11
0x180041349  mov     edx, 0CCh
0x18004134e  mov     r9d, eax
0x180041351  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180041358  mov     rcx, [rcx+10h]
0x18004135c  call    WPP_SF_d
0x180041361  jmp     loc_180041A11
0x180041366  mov     rax, [rdi]
0x180041369  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_EXIF.Data1
0x180041370  jnz     short loc_18004137D
0x180041372  mov     rax, [rdi+8]
0x180041376  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_EXIF.Data4
0x18004137d  test    rax, rax
0x180041380  jz      short loc_1800413EC
0x180041382  mov     rax, [rdi]
0x180041385  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_JFIF.Data1
0x18004138c  jnz     short loc_180041399
0x18004138e  mov     rax, [rdi+8]
0x180041392  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_JFIF.Data4
0x180041399  test    rax, rax
0x18004139c  jz      short loc_1800413EC
0x18004139e  mov     rax, [rdi]
0x1800413a1  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_BMP.Data1
0x1800413a8  jnz     short loc_1800413B5
0x1800413aa  mov     rax, [rdi+8]
0x1800413ae  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_BMP.Data4
0x1800413b5  test    rax, rax
0x1800413b8  jnz     short loc_1800413C3
0x1800413ba  lea     rdx, aImageBmp; "image/bmp"
0x1800413c1  jmp     short loc_1800413F3
0x1800413c3  mov     rax, [rdi]
0x1800413c6  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_PNG.Data1
0x1800413cd  jnz     short loc_1800413DA
0x1800413cf  mov     rax, [rdi+8]
0x1800413d3  sub     rax, qword ptr cs:WPD_OBJECT_FORMAT_PNG.Data4
0x1800413da  test    rax, rax
0x1800413dd  jnz     loc_180041A05
0x1800413e3  lea     rdx, aImagePng; "image/png"
0x1800413ea  jmp     short loc_1800413F3
0x1800413ec  lea     rdx, aImageJpeg; "image/jpeg"
0x1800413f3  lea     r8, [rbp+40h+var_A8]; struct _GUID *
0x1800413f7  call    ?_GetEncoderClsid@CContentDropTarget@@AEAAHPEBGPEAU_GUID@@@Z; CContentDropTarget::_GetEncoderClsid(ushort const *,_GUID *)
0x1800413fc  test    eax, eax
0x1800413fe  js      loc_180041A05
0x180041404  mov     rcx, [rsp+140h+ppstm]
0x180041409  mov     rax, [rcx]
0x18004140c  xor     r9d, r9d
0x18004140f  xor     r8d, r8d
0x180041412  mov     rdx, [rsp+140h+var_D0]
0x180041417  mov     rax, [rax+28h]
0x18004141b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041420  xor     r9d, r9d
0x180041423  lea     r8, [rbp+40h+var_A8]
0x180041427  mov     rdx, [rsp+140h+ppstm]
0x18004142c  mov     rcx, r14
0x18004142f  call    cs:__imp_GdipSaveImageToStream
0x180041435  test    eax, eax
0x180041437  jnz     loc_180041A05
0x18004143d  mov     rcx, [rsp+140h+ppstm]
0x180041442  mov     rax, [rcx]
0x180041445  mov     r8d, 1
0x18004144b  lea     rdx, [rbp+40h+var_90]
0x18004144f  mov     rax, [rax+60h]
0x180041453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041458  mov     ebx, eax
0x18004145a  test    eax, eax
0x18004145c  jns     short loc_180041489
0x18004145e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041465  lea     rdi, WPP_GLOBAL_Control
0x18004146c  cmp     rcx, rdi
0x18004146f  jz      loc_180041A11
0x180041475  test    byte ptr [rcx+1Ch], 2
0x180041479  jz      loc_180041A11
0x18004147f  mov     edx, 0CDh
0x180041484  jmp     loc_18004134E
0x180041489  mov     r14, [rbp+40h+cb]
0x18004148d  test    r14, r14
0x180041490  jz      loc_180041A05
0x180041496  mov     eax, 0FFFFFFFFh
0x18004149b  cmp     r14, rax
0x18004149e  ja      loc_180041A05
0x1800414a4  mov     r15d, r14d
0x1800414a7  mov     ecx, r14d; cb
0x1800414aa  call    cs:__imp_CoTaskMemAlloc
0x1800414b0  mov     rbx, rax
0x1800414b3  mov     [rsp+140h+pv], rax
0x1800414b8  test    rax, rax
0x1800414bb  jnz     short loc_1800414C7
0x1800414bd  mov     ebx, 8007000Eh
0x1800414c2  jmp     loc_180041A0A
0x1800414c7  mov     r8, r15; Size
0x1800414ca  xor     edx, edx; Val
0x1800414cc  mov     rcx, rbx; void *
0x1800414cf  call    memset_0
0x1800414d4  mov     rcx, [rsp+140h+ppstm]
0x1800414d9  mov     rax, [rcx]
0x1800414dc  xor     r9d, r9d
0x1800414df  xor     r8d, r8d
0x1800414e2  mov     rdx, [rsp+140h+var_D0]
0x1800414e7  mov     rax, [rax+28h]
0x1800414eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414f0  mov     rcx, [rsp+140h+ppstm]
0x1800414f5  mov     rax, [rcx]
0x1800414f8  lea     r9, [rsp+140h+var_108]
0x1800414fd  mov     r8d, r14d
0x180041500  mov     rdx, rbx
0x180041503  mov     rax, [rax+18h]
0x180041507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004150c  mov     ebx, eax
0x18004150e  test    eax, eax
0x180041510  jns     short loc_18004155E
0x180041512  mov     rcx, cs:WPP_GLOBAL_Control
0x180041519  lea     rdi, WPP_GLOBAL_Control
0x180041520  cmp     rcx, rdi
0x180041523  jz      short loc_180041543
0x180041525  test    byte ptr [rcx+1Ch], 2
0x180041529  jz      short loc_180041543
0x18004152b  mov     edx, 0CEh
0x180041530  mov     r9d, eax
0x180041533  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18004153a  mov     rcx, [rcx+10h]
0x18004153e  call    WPP_SF_d
0x180041543  mov     r12, [rsp+140h+pv]
0x180041548  mov     rcx, r12; pv
0x18004154b  call    cs:__imp_CoTaskMemFree
0x180041551  test    ebx, ebx
0x180041553  jns     loc_180041A3C
0x180041559  jmp     loc_180041A11
0x18004155e  cmp     [rsp+140h+var_108], r14d
0x180041563  jz      short loc_180041573
0x180041565  mov     ebx, 80004005h
0x18004156a  lea     rdi, WPP_GLOBAL_Control
0x180041571  jmp     short loc_180041543
0x180041573  lea     rax, [rsp+140h+var_F8]
0x180041578  mov     [rsp+140h+ppv], rax; ppv
0x18004157d  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180041584  xor     edx, edx; pUnkOuter
0x180041586  lea     r8d, [rdx+1]; dwClsContext
0x18004158a  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180041591  call    cs:__imp_CoCreateInstance
0x180041597  mov     ebx, eax
0x180041599  test    eax, eax
0x18004159b  jns     short loc_1800415C0
0x18004159d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415a4  lea     rdi, WPP_GLOBAL_Control
0x1800415ab  cmp     rcx, rdi
0x1800415ae  jz      short loc_180041543
0x1800415b0  test    byte ptr [rcx+1Ch], 2
0x1800415b4  jz      short loc_180041543
0x1800415b6  mov     edx, 0CFh
0x1800415bb  jmp     loc_180041530
0x1800415c0  mov     rcx, [rsp+140h+var_F8]
0x1800415c5  mov     rax, [rcx]
0x1800415c8  mov     r8, rdi
0x1800415cb  lea     rdx, WPD_RESOURCE_ATTRIBUTE_FORMAT
0x1800415d2  mov     rax, [rax+0D8h]
0x1800415d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415de  mov     ebx, eax
0x1800415e0  test    eax, eax
0x1800415e2  jns     short loc_18004160F
0x1800415e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415eb  lea     rdi, WPP_GLOBAL_Control
0x1800415f2  cmp     rcx, rdi
0x1800415f5  jz      loc_180041543
0x1800415fb  test    byte ptr [rcx+1Ch], 2
0x1800415ff  jz      loc_180041543
0x180041605  mov     edx, 0D0h
0x18004160a  jmp     loc_180041530
0x18004160f  mov     rcx, [rsp+140h+var_F8]
0x180041614  mov     rax, [rcx]
0x180041617  mov     r8, r15
0x18004161a  lea     rdx, WPD_RESOURCE_ATTRIBUTE_TOTAL_SIZE
0x180041621  mov     rax, [rax+68h]
0x180041625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004162a  mov     ebx, eax
0x18004162c  test    eax, eax
0x18004162e  jns     short loc_18004165B
0x180041630  mov     rcx, cs:WPP_GLOBAL_Control
0x180041637  lea     rdi, WPP_GLOBAL_Control
0x18004163e  cmp     rcx, rdi
0x180041641  jz      loc_180041543
0x180041647  test    byte ptr [rcx+1Ch], 2
0x18004164b  jz      loc_180041543
0x180041651  mov     edx, 0D1h
0x180041656  jmp     loc_180041530
0x18004165b  mov     rcx, [rsp+140h+var_F8]
0x180041660  mov     rax, [rcx]
0x180041663  mov     r8, r13
0x180041666  lea     rdx, WPD_OBJECT_ID
0x18004166d  mov     rax, [rax+38h]
0x180041671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041676  mov     ebx, eax
0x180041678  test    eax, eax
0x18004167a  jns     short loc_1800416A7
0x18004167c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041683  lea     rdi, WPP_GLOBAL_Control
0x18004168a  cmp     rcx, rdi
0x18004168d  jz      loc_180041543
0x180041693  test    byte ptr [rcx+1Ch], 2
0x180041697  jz      loc_180041543
0x18004169d  mov     edx, 0D2h
0x1800416a2  jmp     loc_180041530
0x1800416a7  lea     rax, [rsp+140h+var_E0]
0x1800416ac  mov     [rsp+140h+ppv], rax; ppv
0x1800416b1  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x1800416b8  xor     edx, edx; pUnkOuter
0x1800416ba  lea     r8d, [rdx+1]; dwClsContext
0x1800416be  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x1800416c5  call    cs:__imp_CoCreateInstance
0x1800416cb  mov     ebx, eax
0x1800416cd  test    eax, eax
0x1800416cf  jns     short loc_1800416FC
0x1800416d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416d8  lea     rdi, WPP_GLOBAL_Control
0x1800416df  cmp     rcx, rdi
0x1800416e2  jz      loc_180041543
0x1800416e8  test    byte ptr [rcx+1Ch], 2
0x1800416ec  jz      loc_180041543
0x1800416f2  mov     edx, 0D3h
0x1800416f7  jmp     loc_180041530
0x1800416fc  mov     rcx, [rsp+140h+var_E0]
0x180041701  mov     rax, [rcx]
0x180041704  lea     rdx, WPD_RESOURCE_THUMBNAIL
0x18004170b  mov     rax, [rax+28h]
0x18004170f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041714  mov     ebx, eax
0x180041716  test    eax, eax
0x180041718  jns     short loc_180041745
0x18004171a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041721  lea     rdi, WPP_GLOBAL_Control
0x180041728  cmp     rcx, rdi
0x18004172b  jz      loc_180041543
  ... truncated ...
```
