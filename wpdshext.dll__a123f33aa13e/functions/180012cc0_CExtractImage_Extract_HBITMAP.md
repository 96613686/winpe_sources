# CExtractImage::Extract(HBITMAP__ * *)

- ea: `0x180012cc0`
- end: `0x180013164`
- name: `?Extract@CExtractImage@@UEAAJPEAPEAUHBITMAP__@@@Z`
- size: `1188`
- prototype: `__int64 __fastcall(CExtractImage *__hidden this, HBITMAP *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180012cc0`
- `0x180014748`
- `0x1800147ec`
- `0x180014b60`
- `0x180014dd0`
- `0x180014e88`
- `0x1800177dc`
- `0x18002386c`
- `0x18002ea3c`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x18005b288`
- `0x18005b59c`
- `0x18006ecb8`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013035`
- `KERNEL32!GetLastError` at `0x180013035`
- `KERNEL32!DeleteFileW` at `0x180012f31`
- `KERNEL32!DeleteFileW` at `0x180012f31`
- `KERNEL32!QueryPerformanceCounter` at `0x180012d2f`
- `KERNEL32!QueryPerformanceCounter` at `0x180012d2f`
- `USER32!CopyImage` at `0x18001301e`
- `USER32!CopyImage` at `0x18001301e`
- `gdiplus!GdipDisposeImage` at `0x180012f28`
- `gdiplus!GdipDisposeImage` at `0x180012faa`
- `gdiplus!GdipDisposeImage` at `0x180012f28`
- `gdiplus!GdipDisposeImage` at `0x180012faa`
- `ole32!CreateStreamOnHGlobal` at `0x180012f51`
- `ole32!CreateStreamOnHGlobal` at `0x180012f51`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CExtractImage::Extract(CExtractImage *this, HBITMAP *a2)
{
  signed int v4; // ebx
  struct IStream *v5; // rbx
  const WCHAR *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  GUID *v9; // r14
  __int64 v10; // rax
  int ResourceStream; // eax
  int v12; // r8d
  __int64 v13; // rax
  int v14; // r8d
  void *v15; // rcx
  HBITMAP v16; // rax
  signed int LastError; // eax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  int v20; // edx
  struct IStream *v22; // [rsp+30h] [rbp-D0h] BYREF
  struct IPortableDevice *v23; // [rsp+38h] [rbp-C8h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  char v33; // [rsp+A8h] [rbp-58h]
  struct _tagpropertykey Buf1; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v35[264]; // [rsp+D0h] [rbp-30h] BYREF

  v28 = 0;
  v29 = 0;
  v33 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v31 = 0;
  v32 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    v28 = 13;
    v29 = 0;
    v31 = 0;
    v33 = 1;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_63;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 12) && *((_WORD *)this + 32) && (int)StartGdiPlus() >= 0 )
  {
    v23 = 0;
    ppstm = 0;
    v5 = 0;
    v22 = 0;
    v6 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    lpFileName = v6;
    if ( (int)SHBindToIDList(*((_QWORD *)this + 73), v7, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v23) >= 0
      && (int)GetObjectID(v23, (unsigned __int16 *)this + 32, v35, 0x104u) >= 0 )
    {
      v9 = (GUID *)((char *)this + 28);
      if ( *((_DWORD *)this + 11) )
        goto LABEL_33;
      v10 = *(_QWORD *)&v9->Data1 - *(_QWORD *)&WPD_PROPERTY_NULL.fmtid.Data1;
      if ( *(_QWORD *)&v9->Data1 == *(_QWORD *)&WPD_PROPERTY_NULL.fmtid.Data1 )
        v10 = *(_QWORD *)((char *)this + 36) - *(_QWORD *)WPD_PROPERTY_NULL.fmtid.Data4;
      if ( v10 )
      {
LABEL_33:
        if ( CreateStreamOnHGlobal(0, 1, &ppstm) >= 0
          && GetResourceStream(v23, v35, (const struct _tagpropertykey *)((char *)this + 28), 0, ppstm) >= 0 )
        {
          Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v26, ppstm, v14);
          if ( (int)CExtractImage::_GetHBitmap(this, (struct Gdiplus::Bitmap *)v26, (HBITMAP *)this + 7) >= 0 )
            *((_DWORD *)this + 12) = 0;
          GdipDisposeImage(v27);
        }
      }
      else if ( (int)CTempFileStream::CreateInstance(0, &lpFileName, v8, &v22) < 0 )
      {
        v5 = v22;
        v6 = lpFileName;
      }
      else
      {
        Buf1.fmtid = *v9;
        Buf1.pid = *((_DWORD *)this + 11);
        if ( !Buf1.pid && !memcmp_0(&Buf1, &WPD_PROPERTY_NULL, 0x10u) )
        {
          Buf1.fmtid = WPD_RESOURCE_DEFAULT.fmtid;
          Buf1.pid = 0;
        }
        v5 = v22;
        ResourceStream = GetResourceStream(v23, v35, &Buf1, 0, v22);
        v6 = lpFileName;
        if ( ResourceStream >= 0 )
        {
          Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v26, v5, v12);
          if ( (int)CExtractImage::_GetHBitmap(this, (struct Gdiplus::Bitmap *)v26, (HBITMAP *)this + 7) >= 0 )
            *((_DWORD *)this + 12) = 0;
          if ( !*((_QWORD *)this + 7) && !*((_DWORD *)this + 11) )
          {
            v13 = *(_QWORD *)&v9->Data1 - *(_QWORD *)&WPD_PROPERTY_NULL.fmtid.Data1;
            if ( *(_QWORD *)&v9->Data1 == *(_QWORD *)&WPD_PROPERTY_NULL.fmtid.Data1 )
              v13 = *(_QWORD *)((char *)this + 36) - *(_QWORD *)WPD_PROPERTY_NULL.fmtid.Data4;
            if ( !v13 )
            {
              if ( v5 )
              {
                ATL::AtlComPtrAssign((struct IUnknown **)&v22, 0);
                v5 = v22;
              }
              GetVideoThumbnail(v6, *((unsigned int *)this + 3), *((unsigned int *)this + 4), (char *)this + 56);
            }
          }
          GdipDisposeImage(v27);
        }
        DeleteFileW(v6);
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
    if ( v5 )
      ((void (__fastcall *)(struct IStream *))v5->lpVtbl->Release)(v5);
    if ( ppstm )
      ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    if ( v23 )
      ((void (__fastcall *)(struct IPortableDevice *))v23->lpVtbl->Release)(v23);
  }
  v15 = (void *)*((_QWORD *)this + 7);
  if ( !v15 )
  {
    v4 = -2147467263;
    if ( *((_DWORD *)this + 11) )
      goto LABEL_59;
    v18 = *(_QWORD *)((char *)this + 28) - *(_QWORD *)&WPD_PROPERTY_NULL.fmtid.Data1;
    if ( !v18 )
      v18 = *(_QWORD *)((char *)this + 36) - *(_QWORD *)WPD_PROPERTY_NULL.fmtid.Data4;
    if ( v18 )
    {
LABEL_59:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_63;
      v20 = 16;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_63;
      v20 = 15;
    }
    WPP_SF_Sd(v19[2], v20, (unsigned int)&WPP_2bf1e1e543723493952e6379efc1215e_Traceguids, (_DWORD)this + 64, 1);
    goto LABEL_63;
  }
  v16 = (HBITMAP)CopyImage(v15, 0, 0, 0, 0x4004u);
  *a2 = v16;
  if ( v16 )
  {
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_2bf1e1e543723493952e6379efc1215e_Traceguids,
        (unsigned int)v4);
  }
LABEL_63:
  CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)&v28, 0xDu, v4, (const unsigned __int16 *)this + 32);
  if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_2bf1e1e543723493952e6379efc1215e_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012cc0  mov     [rsp-8+arg_10], rbx
0x180012cc5  push    rbp
0x180012cc6  push    rsi
0x180012cc7  push    rdi
0x180012cc8  push    r12
0x180012cca  push    r13
0x180012ccc  push    r14
0x180012cce  push    r15
0x180012cd0  lea     rbp, [rsp-1F0h]
0x180012cd8  sub     rsp, 2F0h
0x180012cdf  mov     rax, cs:__security_cookie
0x180012ce6  xor     rax, rsp
0x180012ce9  mov     [rbp+220h+var_40], rax
0x180012cf0  mov     r12, rdx
0x180012cf3  mov     rsi, rcx
0x180012cf6  xor     r13d, r13d
0x180012cf9  mov     [rsp+320h+var_2B0], r13
0x180012cfe  mov     [rsp+320h+var_2A8], r13
0x180012d03  mov     [rbp+220h+var_278], r13b
0x180012d07  xorps   xmm0, xmm0
0x180012d0a  movdqa  xmmword ptr [rbp+220h+PerformanceCount], xmm0
0x180012d0f  xorps   xmm1, xmm1
0x180012d12  movdqa  [rbp+220h+var_290], xmm1
0x180012d17  mov     [rbp+220h+var_280], r13
0x180012d1b  mov     rax, cs:WPP_GLOBAL_Control
0x180012d22  test    dword ptr [rax+1Ch], 800h
0x180012d29  jz      short loc_180012D4F
0x180012d2b  lea     rcx, [rbp+220h+PerformanceCount]; lpPerformanceCount
0x180012d2f  call    cs:__imp_QueryPerformanceCounter
0x180012d35  mov     [rsp+320h+var_2B0], 0Dh
0x180012d3e  mov     [rsp+320h+var_2A8], r13
0x180012d43  xorps   xmm0, xmm0
0x180012d46  movdqa  [rbp+220h+var_290], xmm0
0x180012d4b  mov     [rbp+220h+var_278], 1
0x180012d4f  lea     rdi, WPP_GLOBAL_Control
0x180012d56  test    r12, r12
0x180012d59  jnz     short loc_180012D65
0x180012d5b  mov     ebx, 80070057h
0x180012d60  jmp     loc_1800130F4
0x180012d65  mov     [r12], r13
0x180012d69  cmp     [rsi+30h], r13d
0x180012d6d  jz      loc_180013005
0x180012d73  cmp     [rsi+40h], r13w
0x180012d78  jz      loc_180013005
0x180012d7e  call    ?StartGdiPlus@@YAJXZ; StartGdiPlus(void)
0x180012d83  test    eax, eax
0x180012d85  js      loc_180013005
0x180012d8b  mov     [rsp+320h+var_2E8], r13
0x180012d90  mov     [rsp+320h+ppstm], r13
0x180012d95  mov     rbx, r13
0x180012d98  mov     [rsp+320h+var_2F0], rbx
0x180012d9d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012da4  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012dab  mov     rax, [rax+18h]
0x180012daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db4  lea     rdi, [rax+18h]
0x180012db8  mov     [rsp+320h+lpFileName], rdi
0x180012dbd  lea     r9, [rsp+320h+var_2E8]
0x180012dc2  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x180012dc9  mov     rcx, [rsi+248h]
0x180012dd0  call    SHBindToIDList
0x180012dd5  test    eax, eax
0x180012dd7  js      loc_180012FB1
0x180012ddd  mov     r9d, 104h; unsigned int
0x180012de3  lea     r8, [rbp+220h+var_250]; unsigned __int16 *
0x180012de7  lea     rdx, [rsi+40h]; unsigned __int16 *
0x180012deb  mov     rcx, [rsp+320h+var_2E8]; struct IPortableDevice *
0x180012df0  call    ?GetObjectID@@YAJPEAUIPortableDevice@@PEAG1I@Z; GetObjectID(IPortableDevice *,ushort *,ushort *,uint)
0x180012df5  test    eax, eax
0x180012df7  js      loc_180012FB1
0x180012dfd  lea     r14, [rsi+1Ch]
0x180012e01  cmp     [r14+10h], r13d
0x180012e05  jnz     loc_180012F45
0x180012e0b  mov     rax, [r14]
0x180012e0e  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x180012e15  jnz     short loc_180012E22
0x180012e17  mov     rax, [r14+8]
0x180012e1b  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data4
0x180012e22  test    rax, rax
0x180012e25  jnz     loc_180012F45
0x180012e2b  lea     r9, [rsp+320h+var_2F0]
0x180012e30  lea     rdx, [rsp+320h+lpFileName]
0x180012e35  xor     ecx, ecx
0x180012e37  call    ?CreateInstance@CTempFileStream@@SAJHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAUIStream@@@Z; CTempFileStream::CreateInstance(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,IStream * *)
0x180012e3c  test    eax, eax
0x180012e3e  js      loc_180012F39
0x180012e44  movups  xmm0, xmmword ptr [r14]
0x180012e48  movups  [rbp+220h+Buf1], xmm0
0x180012e4c  mov     eax, [r14+10h]
0x180012e50  mov     [rbp+220h+var_260], eax
0x180012e53  test    eax, eax
0x180012e55  jnz     short loc_180012E7F
0x180012e57  lea     r8d, [rax+10h]; Size
0x180012e5b  lea     rdx, WPD_PROPERTY_NULL; Buf2
0x180012e62  lea     rcx, [rbp+220h+Buf1]; Buf1
0x180012e66  call    memcmp_0
0x180012e6b  test    eax, eax
0x180012e6d  jnz     short loc_180012E7F
0x180012e6f  movups  xmm0, xmmword ptr cs:WPD_RESOURCE_DEFAULT.fmtid.Data1
0x180012e76  movdqu  [rbp+220h+Buf1], xmm0
0x180012e7b  mov     [rbp+220h+var_260], r13d
0x180012e7f  mov     rbx, [rsp+320h+var_2F0]
0x180012e84  mov     qword ptr [rsp+320h+flags], rbx; struct IStream *
0x180012e89  xor     r9d, r9d; struct CProgressUI *
0x180012e8c  lea     r8, [rbp+220h+Buf1]; struct _tagpropertykey *
0x180012e90  lea     rdx, [rbp+220h+var_250]; unsigned __int16 *
0x180012e94  mov     rcx, [rsp+320h+var_2E8]; struct IPortableDevice *
0x180012e99  call    ?GetResourceStream@@YAJPEAUIPortableDevice@@PEBGAEBU_tagpropertykey@@PEAVCProgressUI@@PEAUIStream@@@Z; GetResourceStream(IPortableDevice *,ushort const *,_tagpropertykey const &,CProgressUI *,IStream *)
0x180012e9e  mov     rdi, [rsp+320h+lpFileName]
0x180012ea3  test    eax, eax
0x180012ea5  js      loc_180012F2E
0x180012eab  mov     rdx, rbx; struct IStream *
0x180012eae  lea     rcx, [rsp+320h+var_2D0]; this
0x180012eb3  call    ??0Bitmap@Gdiplus@@QEAA@PEAUIStream@@H@Z; Gdiplus::Bitmap::Bitmap(IStream *,int)
0x180012eb8  lea     r15, [rsi+38h]
0x180012ebc  mov     r8, r15; HBITMAP *
0x180012ebf  lea     rdx, [rsp+320h+var_2D0]; struct Gdiplus::Bitmap *
0x180012ec4  mov     rcx, rsi; this
0x180012ec7  call    ?_GetHBitmap@CExtractImage@@AEAAJPEAVBitmap@Gdiplus@@PEAPEAUHBITMAP__@@@Z; CExtractImage::_GetHBitmap(Gdiplus::Bitmap *,HBITMAP__ * *)
0x180012ecc  test    eax, eax
0x180012ece  js      short loc_180012ED4
0x180012ed0  mov     [rsi+30h], r13d
0x180012ed4  cmp     [r15], r13
0x180012ed7  jnz     short loc_180012F23
0x180012ed9  cmp     [rsi+2Ch], r13d
0x180012edd  jnz     short loc_180012F23
0x180012edf  mov     rax, [r14]
0x180012ee2  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x180012ee9  jnz     short loc_180012EF6
0x180012eeb  mov     rax, [r14+8]
0x180012eef  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data4
0x180012ef6  test    rax, rax
0x180012ef9  jnz     short loc_180012F23
0x180012efb  test    rbx, rbx
0x180012efe  jz      short loc_180012F11
0x180012f00  xor     edx, edx; struct IUnknown *
0x180012f02  lea     rcx, [rsp+320h+var_2F0]; struct IUnknown **
0x180012f07  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180012f0c  mov     rbx, [rsp+320h+var_2F0]
0x180012f11  mov     r9, r15
0x180012f14  mov     r8d, [rsi+10h]
0x180012f18  mov     edx, [rsi+0Ch]
0x180012f1b  mov     rcx, rdi
0x180012f1e  call    GetVideoThumbnail
0x180012f23  mov     rcx, [rsp+320h+var_2C8]
0x180012f28  call    cs:__imp_GdipDisposeImage
0x180012f2e  mov     rcx, rdi; lpFileName
0x180012f31  call    cs:__imp_DeleteFileW
0x180012f37  jmp     short loc_180012FB1
0x180012f39  mov     rbx, [rsp+320h+var_2F0]
0x180012f3e  mov     rdi, [rsp+320h+lpFileName]
0x180012f43  jmp     short loc_180012FB1
0x180012f45  lea     r8, [rsp+320h+ppstm]; ppstm
0x180012f4a  mov     edx, 1; fDeleteOnRelease
0x180012f4f  xor     ecx, ecx; hGlobal
0x180012f51  call    cs:__imp_CreateStreamOnHGlobal
0x180012f57  test    eax, eax
0x180012f59  js      short loc_180012FB1
0x180012f5b  mov     rax, [rsp+320h+ppstm]
0x180012f60  mov     qword ptr [rsp+320h+flags], rax; struct IStream *
0x180012f65  xor     r9d, r9d; struct CProgressUI *
0x180012f68  mov     r8, r14; struct _tagpropertykey *
0x180012f6b  lea     rdx, [rbp+220h+var_250]; unsigned __int16 *
0x180012f6f  mov     rcx, [rsp+320h+var_2E8]; struct IPortableDevice *
0x180012f74  call    ?GetResourceStream@@YAJPEAUIPortableDevice@@PEBGAEBU_tagpropertykey@@PEAVCProgressUI@@PEAUIStream@@@Z; GetResourceStream(IPortableDevice *,ushort const *,_tagpropertykey const &,CProgressUI *,IStream *)
0x180012f79  test    eax, eax
0x180012f7b  js      short loc_180012FB1
0x180012f7d  mov     rdx, [rsp+320h+ppstm]; struct IStream *
0x180012f82  lea     rcx, [rsp+320h+var_2D0]; this
0x180012f87  call    ??0Bitmap@Gdiplus@@QEAA@PEAUIStream@@H@Z; Gdiplus::Bitmap::Bitmap(IStream *,int)
0x180012f8c  lea     r8, [rsi+38h]; HBITMAP *
0x180012f90  lea     rdx, [rsp+320h+var_2D0]; struct Gdiplus::Bitmap *
0x180012f95  mov     rcx, rsi; this
0x180012f98  call    ?_GetHBitmap@CExtractImage@@AEAAJPEAVBitmap@Gdiplus@@PEAPEAUHBITMAP__@@@Z; CExtractImage::_GetHBitmap(Gdiplus::Bitmap *,HBITMAP__ * *)
0x180012f9d  test    eax, eax
0x180012f9f  js      short loc_180012FA5
0x180012fa1  mov     [rsi+30h], r13d
0x180012fa5  mov     rcx, [rsp+320h+var_2C8]
0x180012faa  call    cs:__imp_GdipDisposeImage
0x180012fb0  nop
0x180012fb1  lea     rcx, [rdi-18h]; this
0x180012fb5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012fba  nop
0x180012fbb  test    rbx, rbx
0x180012fbe  jz      short loc_180012FD0
0x180012fc0  mov     rax, [rbx]
0x180012fc3  mov     rcx, rbx
0x180012fc6  mov     rax, [rax+10h]
0x180012fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fcf  nop
0x180012fd0  mov     rcx, [rsp+320h+ppstm]
0x180012fd5  test    rcx, rcx
0x180012fd8  jz      short loc_180012FE7
0x180012fda  mov     rax, [rcx]
0x180012fdd  mov     rax, [rax+10h]
0x180012fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fe6  nop
0x180012fe7  mov     rcx, [rsp+320h+var_2E8]
0x180012fec  test    rcx, rcx
0x180012fef  jz      short loc_180012FFE
0x180012ff1  mov     rax, [rcx]
0x180012ff4  mov     rax, [rax+10h]
0x180012ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffd  nop
0x180012ffe  lea     rdi, WPP_GLOBAL_Control
0x180013005  mov     rcx, [rsi+38h]; h
0x180013009  test    rcx, rcx
0x18001300c  jz      short loc_180013086
0x18001300e  mov     [rsp+320h+flags], 4004h; flags
0x180013016  xor     r9d, r9d; cy
0x180013019  xor     r8d, r8d; cx
0x18001301c  xor     edx, edx; type
0x18001301e  call    cs:__imp_CopyImage
0x180013024  mov     [r12], rax
0x180013028  test    rax, rax
0x18001302b  jz      short loc_180013035
0x18001302d  mov     ebx, r13d
0x180013030  jmp     loc_1800130F4
0x180013035  call    cs:__imp_GetLastError
0x18001303b  mov     ebx, eax
0x18001303d  test    eax, eax
0x18001303f  jle     short loc_18001304A
0x180013041  movzx   ebx, ax
0x180013044  or      ebx, 80070000h
0x18001304a  test    ebx, ebx
0x18001304c  jns     loc_1800130F4
0x180013052  mov     rcx, cs:WPP_GLOBAL_Control
0x180013059  cmp     rcx, rdi
0x18001305c  jz      loc_1800130F4
0x180013062  test    byte ptr [rcx+1Ch], 2
0x180013066  jz      loc_1800130F4
0x18001306c  mov     edx, 0Eh
0x180013071  mov     r9d, ebx
0x180013074  lea     r8, WPP_2bf1e1e543723493952e6379efc1215e_Traceguids
0x18001307b  mov     rcx, [rcx+10h]
0x18001307f  call    WPP_SF_d
0x180013084  jmp     short loc_1800130F4
0x180013086  mov     ebx, 80004001h
0x18001308b  cmp     [rsi+2Ch], r13d
0x18001308f  jnz     short loc_1800130C5
0x180013091  mov     rax, [rsi+1Ch]
0x180013095  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x18001309c  jnz     short loc_1800130A9
0x18001309e  mov     rax, [rsi+24h]
0x1800130a2  sub     rax, qword ptr cs:WPD_PROPERTY_NULL.fmtid.Data4
0x1800130a9  test    rax, rax
0x1800130ac  jnz     short loc_1800130C5
0x1800130ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130b5  cmp     rcx, rdi
0x1800130b8  jz      short loc_1800130F4
0x1800130ba  test    byte ptr [rcx+1Ch], 2
0x1800130be  jz      short loc_1800130F4
0x1800130c0  lea     edx, [rax+0Fh]
0x1800130c3  jmp     short loc_1800130DC
0x1800130c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130cc  cmp     rcx, rdi
0x1800130cf  jz      short loc_1800130F4
0x1800130d1  test    byte ptr [rcx+1Ch], 2
0x1800130d5  jz      short loc_1800130F4
0x1800130d7  mov     edx, 10h
0x1800130dc  mov     [rsp+320h+flags], ebx
0x1800130e0  lea     r9, [rsi+40h]
0x1800130e4  lea     r8, WPP_2bf1e1e543723493952e6379efc1215e_Traceguids
0x1800130eb  mov     rcx, [rcx+10h]
0x1800130ef  call    WPP_SF_Sd
0x1800130f4  lea     r9, [rsi+40h]; unsigned __int16 *
0x1800130f8  mov     r8d, ebx; int
0x1800130fb  mov     edx, 0Dh; unsigned int
0x180013100  lea     rcx, [rsp+320h+var_2B0]; this
0x180013105  call    ?ProcessPerformanceData@CPerfTraceHelper@@QEAAXKJPEBG@Z; CPerfTraceHelper::ProcessPerformanceData(ulong,long,ushort const *)
0x18001310a  test    ebx, ebx
0x18001310c  jns     short loc_180013138
0x18001310e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013115  cmp     rcx, rdi
0x180013118  jz      short loc_180013138
0x18001311a  test    byte ptr [rcx+1Ch], 2
0x18001311e  jz      short loc_180013138
0x180013120  mov     edx, 11h
0x180013125  mov     r9d, ebx
0x180013128  lea     r8, WPP_2bf1e1e543723493952e6379efc1215e_Traceguids
0x18001312f  mov     rcx, [rcx+10h]
0x180013133  call    WPP_SF_d
0x180013138  mov     eax, ebx
0x18001313a  mov     rcx, [rbp+220h+var_40]
0x180013141  xor     rcx, rsp; StackCookie
0x180013144  call    __security_check_cookie
0x180013149  mov     rbx, [rsp+320h+arg_10]
0x180013151  add     rsp, 2F0h
0x180013158  pop     r15
0x18001315a  pop     r14
0x18001315c  pop     r13
0x18001315e  pop     r12
0x180013160  pop     rdi
0x180013161  pop     rsi
0x180013162  pop     rbp
0x180013163  retn
```
