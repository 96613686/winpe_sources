# CDeviceSettings::GetDeviceIcon(int,int,HBITMAP__ * *)

- ea: `0x18000449c`
- end: `0x1800049b9`
- name: `?GetDeviceIcon@CDeviceSettings@@QEAAJHHPEAPEAUHBITMAP__@@@Z`
- size: `1309`
- prototype: `__int64 __fastcall(CDeviceSettings *__hidden this, int, int, HBITMAP *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800059a8`
- `0x18000e760`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000449c`
- `0x180004a64`
- `0x180004da4`
- `0x18000553c`
- `0x18001e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180004536`
- `KERNEL32!CompareStringOrdinal` at `0x180004536`
- `KERNEL32!lstrcmpiW` at `0x180004568`
- `KERNEL32!lstrcmpiW` at `0x180004568`
- `ole32!CoTaskMemFree` at `0x180004542`
- `ole32!CoTaskMemFree` at `0x1800048de`
- `ole32!CoTaskMemFree` at `0x180004542`
- `ole32!CoTaskMemFree` at `0x1800048de`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x1800045d0`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x1800045d0`
- `gdiplus!GdiplusStartup` at `0x1800045b4`
- `gdiplus!GdiplusStartup` at `0x1800045b4`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18000460e`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18000460e`
- `gdiplus!GdipAlloc` at `0x1800045e7`
- `gdiplus!GdipAlloc` at `0x1800046af`
- `gdiplus!GdipAlloc` at `0x180004702`
- `gdiplus!GdipAlloc` at `0x180004749`
- `gdiplus!GdipAlloc` at `0x1800045e7`
- `gdiplus!GdipAlloc` at `0x1800046af`
- `gdiplus!GdipAlloc` at `0x180004702`
- `gdiplus!GdipAlloc` at `0x180004749`
- `gdiplus!GdipDeleteGraphics` at `0x180004851`
- `gdiplus!GdipDeleteGraphics` at `0x180004851`
- `gdiplus!GdipDisposeImageAttributes` at `0x180004828`
- `gdiplus!GdipDisposeImageAttributes` at `0x180004828`
- `gdiplus!GdiplusShutdown` at `0x1800048d4`
- `gdiplus!GdiplusShutdown` at `0x1800048d4`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180004884`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180004884`
- `gdiplus!GdipFree` at `0x180004831`
- `gdiplus!GdipFree` at `0x18000485a`
- `gdiplus!GdipFree` at `0x180004831`
- `gdiplus!GdipFree` at `0x18000485a`
- `gdiplus!GdipDrawImageRectRectI` at `0x180004811`
- `gdiplus!GdipDrawImageRectRectI` at `0x180004811`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18000477f`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18000477f`
- `gdiplus!GdipCreateImageAttributes` at `0x180004765`
- `gdiplus!GdipCreateImageAttributes` at `0x180004765`
- `gdiplus!GdipSetInterpolationMode` at `0x180004736`
- `gdiplus!GdipSetInterpolationMode` at `0x180004736`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180004720`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180004720`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800046ec`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800046ec`
- `gdiplus!GdipGetImageHeight` at `0x18000464d`
- `gdiplus!GdipGetImageHeight` at `0x18000468f`
- `gdiplus!GdipGetImageHeight` at `0x18000479c`
- `gdiplus!GdipGetImageHeight` at `0x18000464d`
- `gdiplus!GdipGetImageHeight` at `0x18000468f`
- `gdiplus!GdipGetImageHeight` at `0x18000479c`
- `gdiplus!GdipGetImageWidth` at `0x18000462a`
- `gdiplus!GdipGetImageWidth` at `0x180004670`
- `gdiplus!GdipGetImageWidth` at `0x1800047bb`
- `gdiplus!GdipGetImageWidth` at `0x18000462a`
- `gdiplus!GdipGetImageWidth` at `0x180004670`
- `gdiplus!GdipGetImageWidth` at `0x1800047bb`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::GetDeviceIcon(const WCHAR **this, __int64 a2, int a3, HBITMAP *a4)
{
  int v6; // r12d
  signed int DeviceProperty; // edi
  int v8; // ebx
  const WCHAR *v9; // rcx
  IStream *v10; // rsi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  int ImageWidth; // eax
  __int64 v15; // rcx
  int ImageHeight; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rsi
  _QWORD *v23; // r14
  __int64 v24; // rcx
  int ImageGraphicsContext; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  _QWORD *v29; // r15
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // edi
  __int64 v34; // rcx
  int v35; // eax
  int v36; // eax
  int v37; // edi
  int HBITMAPFromBitmap; // eax
  void (__fastcall **v39)(__int64, __int64); // rax
  __int64 v40; // rcx
  HICON v41; // rcx
  IStream *ppstm; // [rsp+70h] [rbp-9h] BYREF
  __int64 v44; // [rsp+78h] [rbp-1h] BYREF
  __int64 v45; // [rsp+80h] [rbp+7h] BYREF
  int v46; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v47; // [rsp+90h] [rbp+17h]
  __int64 v48; // [rsp+98h] [rbp+1Fh]
  int v49; // [rsp+F0h] [rbp+77h] BYREF
  LPCWCH lpString1; // [rsp+F8h] [rbp+7Fh] BYREF

  v49 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *a4 = 0;
  lpString1 = 0;
  v6 = 0;
  DeviceProperty = CDeviceSettings::GetDeviceProperty(
                     (CDeviceSettings *)this,
                     L"Description",
                     (unsigned __int16 **)&lpString1);
  if ( DeviceProperty
    || (v8 = CompareStringOrdinal(lpString1, -1, L"Windows Media Player Renderer", -1, 1),
        CoTaskMemFree((LPVOID)lpString1),
        LOBYTE(v6) = v8 == 2,
        v8 != 2) )
  {
    v9 = this[13];
    if ( v9 && !lstrcmpiW(v9, L"00-00-00-00-00-00") )
    {
      v6 = 1;
LABEL_53:
      if ( !DeviceProperty && !v6 )
        goto LABEL_60;
      goto LABEL_55;
    }
    if ( !CDeviceSettings::GetDeviceProperty((CDeviceSettings *)this, L"IconFileName", (unsigned __int16 **)&lpString1) )
    {
      v45 = 0;
      v46 = 1;
      v47 = 0;
      v48 = 0;
      DeviceProperty = -2147467259;
      if ( (unsigned int)GdiplusStartup(&v45, &v46, 0) )
      {
LABEL_52:
        CoTaskMemFree((LPVOID)lpString1);
        goto LABEL_53;
      }
      ppstm = 0;
      if ( SHCreateStreamOnFileW(lpString1, 0, &ppstm) < 0 )
      {
        DeviceProperty = 1;
        goto LABEL_51;
      }
      v10 = ppstm;
      v11 = GdipAlloc(24);
      if ( !v11 )
        goto LABEL_48;
      v44 = 0;
      *(_QWORD *)v11 = &Gdiplus::Image::`vftable';
      v12 = GdipCreateBitmapFromStream(v10, &v44);
      v49 = 0;
      *(_DWORD *)(v11 + 16) = v12;
      v13 = v44;
      *(_QWORD *)(v11 + 8) = v44;
      ImageWidth = GdipGetImageWidth(v13, &v49);
      if ( ImageWidth )
        *(_DWORD *)(v11 + 16) = ImageWidth;
      if ( !v49 )
        goto LABEL_48;
      v15 = *(_QWORD *)(v11 + 8);
      v49 = 0;
      ImageHeight = GdipGetImageHeight(v15, &v49);
      if ( ImageHeight )
        *(_DWORD *)(v11 + 16) = ImageHeight;
      if ( !v49 )
      {
LABEL_48:
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_51:
        GdiplusShutdown(v45);
        goto LABEL_52;
      }
      v17 = *(_QWORD *)(v11 + 8);
      v49 = 0;
      v18 = GdipGetImageWidth(v17, &v49);
      if ( v18 )
        *(_DWORD *)(v11 + 16) = v18;
      if ( v49 != 32 )
        goto LABEL_26;
      v19 = *(_QWORD *)(v11 + 8);
      v49 = 0;
      v20 = GdipGetImageHeight(v19, &v49);
      if ( v20 )
        *(_DWORD *)(v11 + 16) = v20;
      if ( v49 == 32 )
      {
        DeviceProperty = 0;
      }
      else
      {
LABEL_26:
        v21 = GdipAlloc(24);
        v22 = v21;
        if ( !v21 )
        {
LABEL_46:
          v39 = *(void (__fastcall ***)(__int64, __int64))v11;
          v40 = v11;
LABEL_47:
          (*v39)(v40, 1);
          goto LABEL_48;
        }
        v44 = 0;
        *(_QWORD *)v21 = &Gdiplus::Image::`vftable';
        *(_DWORD *)(v21 + 16) = GdipCreateBitmapFromScan0(32, 32, 0, 925707, 0, &v44);
        *(_QWORD *)(v22 + 8) = v44;
        v23 = (_QWORD *)GdipAlloc(16);
        if ( v23 )
        {
          v24 = *(_QWORD *)(v22 + 8);
          v44 = 0;
          ImageGraphicsContext = GdipGetImageGraphicsContext(v24, &v44);
          v26 = v44;
          *v23 = v44;
          *((_DWORD *)v23 + 2) = ImageGraphicsContext;
          v27 = GdipSetInterpolationMode(v26, 7);
          if ( v27 )
            *((_DWORD *)v23 + 2) = v27;
          v28 = GdipAlloc(16);
          v29 = (_QWORD *)v28;
          if ( v28 )
          {
            *(_QWORD *)v28 = 0;
            *(_DWORD *)(v28 + 8) = GdipCreateImageAttributes(v28);
            v30 = GdipSetImageAttributesWrapMode(*v29, 3, 4278190080LL);
            if ( v30 )
              *((_DWORD *)v29 + 2) = v30;
            v31 = *(_QWORD *)(v11 + 8);
            v49 = 0;
            v32 = GdipGetImageHeight(v31, &v49);
            if ( v32 )
              *(_DWORD *)(v11 + 16) = v32;
            v33 = v49;
            v34 = *(_QWORD *)(v11 + 8);
            v49 = 0;
            v35 = GdipGetImageWidth(v34, &v49);
            if ( v35 )
              *(_DWORD *)(v11 + 16) = v35;
            v36 = GdipDrawImageRectRectI(*v23, *(_QWORD *)(v11 + 8), 0, 0, 32, 32, 0, 0, v49, v33, 2, *v29, 0, 0);
            v37 = v36;
            if ( v36 )
              *((_DWORD *)v23 + 2) = v36;
            else
              v37 = 0;
            GdipDisposeImageAttributes(*v29);
            GdipFree(v29);
            DeviceProperty = v37 != 0 ? 0x80004005 : 0;
          }
          GdipDeleteGraphics(*v23);
          GdipFree(v23);
        }
        (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
        if ( DeviceProperty < 0 )
        {
          v39 = *(void (__fastcall ***)(__int64, __int64))v22;
          v40 = v22;
          goto LABEL_47;
        }
        v11 = v22;
      }
      HBITMAPFromBitmap = GdipCreateHBITMAPFromBitmap(*(_QWORD *)(v11 + 8), a4, 0);
      if ( HBITMAPFromBitmap )
      {
        *(_DWORD *)(v11 + 16) = HBITMAPFromBitmap;
        DeviceProperty = -2147467259;
        if ( !v11 )
          goto LABEL_48;
      }
      goto LABEL_46;
    }
  }
LABEL_55:
  ppstm = 0;
  if ( v6 )
    v41 = hIconWMPDMR;
  else
    v41 = hIconGenericDMR;
  if ( v41 )
  {
    ppstm = (IStream *)v41;
  }
  else
  {
    DeviceProperty = LoadIconFromModule(0, v6 != 0 ? 23304 : 2969, 32, 32, (HICON *)&ppstm);
    if ( DeviceProperty < 0 )
      goto LABEL_60;
    v41 = (HICON)ppstm;
    if ( v6 )
      hIconWMPDMR = (HICON)ppstm;
    else
      hIconGenericDMR = (HICON)ppstm;
  }
  DeviceProperty = HBITMAPFromHICON(v41, a4);
LABEL_60:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids,
      (unsigned int)DeviceProperty);
  return (unsigned int)DeviceProperty;
}

```

## disassembly

```asm
0x18000449c  mov     [rsp-8+arg_0], rbx
0x1800044a1  mov     [rsp-8+arg_10], r8d
0x1800044a6  push    rbp
0x1800044a7  push    rsi
0x1800044a8  push    rdi
0x1800044a9  push    r12
0x1800044ab  push    r13
0x1800044ad  push    r14
0x1800044af  push    r15
0x1800044b1  lea     rbp, [rsp-27h]
0x1800044b6  sub     rsp, 0A0h
0x1800044bd  mov     r13, r9
0x1800044c0  mov     rsi, rcx
0x1800044c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044ca  lea     rax, WPP_GLOBAL_Control
0x1800044d1  mov     r14d, 20h ; ' '
0x1800044d7  cmp     rcx, rax
0x1800044da  jz      short loc_1800044F6
0x1800044dc  test    [rcx+1Ch], r14b
0x1800044e0  jz      short loc_1800044F6
0x1800044e2  mov     rcx, [rcx+10h]
0x1800044e6  lea     edx, [r14+1Ah]
0x1800044ea  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800044f1  call    WPP_SF_
0x1800044f6  xor     r15d, r15d
0x1800044f9  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x1800044fd  lea     rdx, aDescription; "Description"
0x180004504  mov     [r13+0], r15
0x180004508  mov     rcx, rsi; this
0x18000450b  mov     [rbp+57h+lpString1], r15
0x18000450f  mov     r12d, r15d
0x180004512  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x180004517  lea     ebx, [r15+1]
0x18000451b  mov     edi, eax
0x18000451d  test    eax, eax
0x18000451f  jnz     short loc_180004558
0x180004521  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180004525  lea     r8, String2; "Windows Media Player Renderer"
0x18000452c  or      edx, 0FFFFFFFFh; cchCount1
0x18000452f  mov     [rsp+0D0h+bIgnoreCase], ebx; bIgnoreCase
0x180004533  mov     r9d, edx; cchCount2
0x180004536  call    cs:__imp_CompareStringOrdinal
0x18000453c  mov     rcx, [rbp+57h+lpString1]; pv
0x180004540  mov     ebx, eax
0x180004542  call    cs:__imp_CoTaskMemFree
0x180004548  cmp     ebx, 2
0x18000454b  setz    r12b
0x18000454f  jz      loc_1800048ED
0x180004555  lea     ebx, [rdi+1]
0x180004558  mov     rcx, [rsi+68h]; lpString1
0x18000455c  test    rcx, rcx
0x18000455f  jz      short loc_18000457A
0x180004561  lea     rdx, psz; "00-00-00-00-00-00"
0x180004568  call    cs:__imp_lstrcmpiW
0x18000456e  test    eax, eax
0x180004570  jnz     short loc_18000457A
0x180004572  mov     r12d, ebx
0x180004575  jmp     loc_1800048E4
0x18000457a  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x18000457e  mov     rcx, rsi; this
0x180004581  lea     rdx, aIconfilename; "IconFileName"
0x180004588  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x18000458d  test    eax, eax
0x18000458f  jnz     loc_1800048ED
0x180004595  xor     r8d, r8d
0x180004598  mov     [rbp+57h+var_50], r15
0x18000459c  lea     rdx, [rbp+57h+var_48]
0x1800045a0  mov     [rbp+57h+var_48], ebx
0x1800045a3  lea     rcx, [rbp+57h+var_50]
0x1800045a7  mov     [rbp+57h+var_40], r15
0x1800045ab  mov     [rbp+57h+var_38], r15
0x1800045af  mov     edi, 80004005h
0x1800045b4  call    cs:__imp_GdiplusStartup
0x1800045ba  test    eax, eax
0x1800045bc  jnz     loc_1800048DA
0x1800045c2  mov     rcx, [rbp+57h+lpString1]; pszFile
0x1800045c6  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800045ca  xor     edx, edx; grfMode
0x1800045cc  mov     [rbp+57h+ppstm], r15
0x1800045d0  call    cs:__imp_SHCreateStreamOnFileW
0x1800045d6  test    eax, eax
0x1800045d8  js      loc_1800048CE
0x1800045de  mov     rsi, [rbp+57h+ppstm]
0x1800045e2  mov     ecx, 18h
0x1800045e7  call    cs:__imp_GdipAlloc
0x1800045ed  mov     rbx, rax
0x1800045f0  test    rax, rax
0x1800045f3  jz      loc_1800048AE
0x1800045f9  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180004600  mov     [rbp+57h+var_58], r15
0x180004604  lea     rdx, [rbp+57h+var_58]
0x180004608  mov     [rbx], rax
0x18000460b  mov     rcx, rsi
0x18000460e  call    cs:__imp_GdipCreateBitmapFromStream
0x180004614  lea     rdx, [rbp+57h+arg_10]
0x180004618  mov     [rbp+57h+arg_10], r15d
0x18000461c  mov     [rbx+10h], eax
0x18000461f  mov     rax, [rbp+57h+var_58]
0x180004623  mov     rcx, rax
0x180004626  mov     [rbx+8], rax
0x18000462a  call    cs:__imp_GdipGetImageWidth
0x180004630  test    eax, eax
0x180004632  jz      short loc_180004637
0x180004634  mov     [rbx+10h], eax
0x180004637  cmp     [rbp+57h+arg_10], r15d
0x18000463b  jbe     loc_1800048AE
0x180004641  mov     rcx, [rbx+8]
0x180004645  lea     rdx, [rbp+57h+arg_10]
0x180004649  mov     [rbp+57h+arg_10], r15d
0x18000464d  call    cs:__imp_GdipGetImageHeight
0x180004653  test    eax, eax
0x180004655  jz      short loc_18000465A
0x180004657  mov     [rbx+10h], eax
0x18000465a  cmp     [rbp+57h+arg_10], r15d
0x18000465e  jbe     loc_1800048AE
0x180004664  mov     rcx, [rbx+8]
0x180004668  lea     rdx, [rbp+57h+arg_10]
0x18000466c  mov     [rbp+57h+arg_10], r15d
0x180004670  call    cs:__imp_GdipGetImageWidth
0x180004676  test    eax, eax
0x180004678  jz      short loc_18000467D
0x18000467a  mov     [rbx+10h], eax
0x18000467d  cmp     [rbp+57h+arg_10], r14d
0x180004681  jnz     short loc_1800046AA
0x180004683  mov     rcx, [rbx+8]
0x180004687  lea     rdx, [rbp+57h+arg_10]
0x18000468b  mov     [rbp+57h+arg_10], r15d
0x18000468f  call    cs:__imp_GdipGetImageHeight
0x180004695  test    eax, eax
0x180004697  jz      short loc_18000469C
0x180004699  mov     [rbx+10h], eax
0x18000469c  cmp     [rbp+57h+arg_10], r14d
0x1800046a0  jnz     short loc_1800046AA
0x1800046a2  mov     edi, r15d
0x1800046a5  jmp     loc_18000487A
0x1800046aa  mov     ecx, 18h
0x1800046af  call    cs:__imp_GdipAlloc
0x1800046b5  mov     rsi, rax
0x1800046b8  test    rax, rax
0x1800046bb  jz      loc_18000489B
0x1800046c1  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x1800046c8  mov     [rbp+57h+var_58], r15
0x1800046cc  mov     [rsi], rax
0x1800046cf  mov     r9d, 0E200Bh
0x1800046d5  lea     rax, [rbp+57h+var_58]
0x1800046d9  xor     r8d, r8d
0x1800046dc  mov     [rsp+0D0h+var_A8], rax
0x1800046e1  mov     edx, r14d
0x1800046e4  mov     ecx, r14d
0x1800046e7  mov     qword ptr [rsp+0D0h+bIgnoreCase], r15
0x1800046ec  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800046f2  mov     [rsi+10h], eax
0x1800046f5  mov     ecx, 10h
0x1800046fa  mov     rax, [rbp+57h+var_58]
0x1800046fe  mov     [rsi+8], rax
0x180004702  call    cs:__imp_GdipAlloc
0x180004708  mov     r14, rax
0x18000470b  test    rax, rax
0x18000470e  jz      loc_180004860
0x180004714  mov     rcx, [rsi+8]
0x180004718  lea     rdx, [rbp+57h+var_58]
0x18000471c  mov     [rbp+57h+var_58], r15
0x180004720  call    cs:__imp_GdipGetImageGraphicsContext
0x180004726  mov     rcx, [rbp+57h+var_58]
0x18000472a  mov     edx, 7
0x18000472f  mov     [r14], rcx
0x180004732  mov     [r14+8], eax
0x180004736  call    cs:__imp_GdipSetInterpolationMode
0x18000473c  test    eax, eax
0x18000473e  jz      short loc_180004744
0x180004740  mov     [r14+8], eax
0x180004744  mov     ecx, 10h
0x180004749  call    cs:__imp_GdipAlloc
0x18000474f  mov     r15, rax
0x180004752  test    rax, rax
0x180004755  jz      loc_18000484B
0x18000475b  mov     rcx, rax
0x18000475e  mov     qword ptr [rax], 0
0x180004765  call    cs:__imp_GdipCreateImageAttributes
0x18000476b  xor     r9d, r9d
0x18000476e  mov     [r15+8], eax
0x180004772  mov     rcx, [r15]
0x180004775  mov     r8d, 0FF000000h
0x18000477b  lea     edx, [r9+3]
0x18000477f  call    cs:__imp_GdipSetImageAttributesWrapMode
0x180004785  test    eax, eax
0x180004787  jz      short loc_18000478D
0x180004789  mov     [r15+8], eax
0x18000478d  mov     rcx, [rbx+8]
0x180004791  lea     rdx, [rbp+57h+arg_10]
0x180004795  mov     [rbp+57h+arg_10], 0
0x18000479c  call    cs:__imp_GdipGetImageHeight
0x1800047a2  test    eax, eax
0x1800047a4  jz      short loc_1800047A9
0x1800047a6  mov     [rbx+10h], eax
0x1800047a9  mov     edi, [rbp+57h+arg_10]
0x1800047ac  lea     rdx, [rbp+57h+arg_10]
0x1800047b0  mov     rcx, [rbx+8]
0x1800047b4  mov     [rbp+57h+arg_10], 0
0x1800047bb  call    cs:__imp_GdipGetImageWidth
0x1800047c1  xor     edx, edx
0x1800047c3  test    eax, eax
0x1800047c5  jz      short loc_1800047CA
0x1800047c7  mov     [rbx+10h], eax
0x1800047ca  mov     rax, [r15]
0x1800047cd  xor     r9d, r9d
0x1800047d0  mov     ecx, [rbp+57h+arg_10]
0x1800047d3  xor     r8d, r8d
0x1800047d6  mov     [rsp+0D0h+var_68], rdx
0x1800047db  mov     [rsp+0D0h+var_70], rdx
0x1800047e0  mov     [rsp+0D0h+var_78], rax
0x1800047e5  mov     eax, 20h ; ' '
0x1800047ea  mov     [rsp+0D0h+var_80], 2
0x1800047f2  mov     [rsp+0D0h+var_88], edi
0x1800047f6  mov     [rsp+0D0h+var_90], ecx
0x1800047fa  mov     rcx, [r14]
0x1800047fd  mov     [rsp+0D0h+var_98], edx
0x180004801  mov     [rsp+0D0h+var_A0], edx
0x180004805  mov     rdx, [rbx+8]
0x180004809  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18000480d  mov     [rsp+0D0h+bIgnoreCase], eax
0x180004811  call    cs:__imp_GdipDrawImageRectRectI
0x180004817  mov     edi, eax
0x180004819  test    eax, eax
0x18000481b  jz      short loc_180004823
0x18000481d  mov     [r14+8], eax
0x180004821  jmp     short loc_180004825
0x180004823  xor     edi, edi
0x180004825  mov     rcx, [r15]
0x180004828  call    cs:__imp_GdipDisposeImageAttributes
0x18000482e  mov     rcx, r15
0x180004831  call    cs:__imp_GdipFree
0x180004837  xor     r15d, r15d
0x18000483a  mov     eax, r15d
0x18000483d  sub     eax, edi
0x18000483f  neg     eax
0x180004841  sbb     edi, edi
0x180004843  and     edi, 80004005h
0x180004849  jmp     short loc_18000484E
0x18000484b  xor     r15d, r15d
0x18000484e  mov     rcx, [r14]
0x180004851  call    cs:__imp_GdipDeleteGraphics
0x180004857  mov     rcx, r14
0x18000485a  call    cs:__imp_GdipFree
0x180004860  mov     rax, [rbx]
0x180004863  mov     edx, 1
0x180004868  mov     rcx, rbx
0x18000486b  mov     rax, [rax]
0x18000486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004873  test    edi, edi
0x180004875  js      short loc_1800048C6
0x180004877  mov     rbx, rsi
0x18000487a  mov     rcx, [rbx+8]
0x18000487e  xor     r8d, r8d
0x180004881  mov     rdx, r13
0x180004884  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x18000488a  test    eax, eax
0x18000488c  jz      short loc_18000489B
0x18000488e  mov     [rbx+10h], eax
0x180004891  mov     edi, 80004005h
0x180004896  test    rbx, rbx
0x180004899  jz      short loc_1800048AE
0x18000489b  mov     rax, [rbx]
0x18000489e  mov     rcx, rbx
0x1800048a1  mov     rax, [rax]
0x1800048a4  mov     edx, 1
0x1800048a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ae  mov     rcx, [rbp+57h+ppstm]
0x1800048b2  mov     rax, [rcx]
0x1800048b5  mov     rax, [rax+10h]
0x1800048b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048be  mov     r14d, 20h ; ' '
0x1800048c4  jmp     short loc_1800048D0
0x1800048c6  mov     rax, [rsi]
0x1800048c9  mov     rcx, rsi
0x1800048cc  jmp     short loc_1800048A1
0x1800048ce  mov     edi, ebx
0x1800048d0  mov     rcx, [rbp+57h+var_50]
0x1800048d4  call    cs:__imp_GdiplusShutdown
0x1800048da  mov     rcx, [rbp+57h+lpString1]; pv
0x1800048de  call    cs:__imp_CoTaskMemFree
0x1800048e4  test    edi, edi
0x1800048e6  jnz     short loc_1800048ED
0x1800048e8  test    r12d, r12d
0x1800048eb  jz      short loc_180004910
0x1800048ed  mov     [rbp+57h+ppstm], r15
0x1800048f1  test    r12d, r12d
0x1800048f4  jz      short loc_18000495E
0x1800048f6  mov     rcx, cs:?hIconWMPDMR@@3PEAUHICON__@@EA; unsigned __int16 *
0x1800048fd  test    rcx, rcx
0x180004900  jz      short loc_180004967
0x180004902  mov     [rbp+57h+ppstm], rcx
0x180004906  mov     rdx, r13; HBITMAP *
0x180004909  call    ?HBITMAPFromHICON@@YAJPEAUHICON__@@PEAPEAUHBITMAP__@@@Z; HBITMAPFromHICON(HICON__ *,HBITMAP__ * *)
0x18000490e  mov     edi, eax
0x180004910  mov     rcx, cs:WPP_GLOBAL_Control
0x180004917  lea     rax, WPP_GLOBAL_Control
0x18000491e  cmp     rcx, rax
0x180004921  jz      short loc_180004941
0x180004923  test    [rcx+1Ch], r14b
  ... truncated ...
```
