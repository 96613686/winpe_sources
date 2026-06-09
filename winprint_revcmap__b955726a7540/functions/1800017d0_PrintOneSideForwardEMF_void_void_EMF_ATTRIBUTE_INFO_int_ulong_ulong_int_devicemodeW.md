# PrintOneSideForwardEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,ulong,int *,_devicemodeW *)

- ea: `0x1800017d0`
- end: `0x180001d52`
- name: `?PrintOneSideForwardEMF@@YAKPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKKPEAHPEAU_devicemodeW@@@Z`
- size: `1410`
- prototype: `__int64 __fastcall(HANDLE SpoolFileHandle, HDC hdc, struct _EMF_ATTRIBUTE_INFO *, int, DWORD dwOptimization, DWORD Page, int *, struct _devicemodeW *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800017d0`
- `0x180001fc0`
- `0x180003cf0`
- `0x1800044a0`
- `0x180004c80`
- `0x1800062f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001beb`
- `GDI32!GdiPlayPageEMF` at `0x180001bdd`
- `GDI32!GdiPlayPageEMF` at `0x180001bdd`
- `GDI32!ModifyWorldTransform` at `0x180001b21`
- `GDI32!ModifyWorldTransform` at `0x180001b84`
- `GDI32!ModifyWorldTransform` at `0x180001bb3`
- `GDI32!ModifyWorldTransform` at `0x180001cac`
- `GDI32!ModifyWorldTransform` at `0x180001b21`
- `GDI32!ModifyWorldTransform` at `0x180001b84`
- `GDI32!ModifyWorldTransform` at `0x180001bb3`
- `GDI32!ModifyWorldTransform` at `0x180001cac`
- `GDI32!GdiGetDevmodeForPage` at `0x18000190c`
- `GDI32!GdiGetDevmodeForPage` at `0x180001a0d`
- `GDI32!GdiGetDevmodeForPage` at `0x18000190c`
- `GDI32!GdiGetDevmodeForPage` at `0x180001a0d`
- `GDI32!SetGraphicsMode` at `0x1800019bb`
- `GDI32!SetGraphicsMode` at `0x1800019bb`
- `GDI32!GdiResetDCEMF` at `0x1800019ad`
- `GDI32!GdiResetDCEMF` at `0x1800019ad`
- `GDI32!GdiGetPageHandle` at `0x1800018d3`
- `GDI32!GdiGetPageHandle` at `0x1800018d3`
- `GDI32!GdiStartPageEMF` at `0x1800019e1`
- `GDI32!GdiStartPageEMF` at `0x180001c6f`
- `GDI32!GdiStartPageEMF` at `0x180001cee`
- `GDI32!GdiStartPageEMF` at `0x1800019e1`
- `GDI32!GdiStartPageEMF` at `0x180001c6f`
- `GDI32!GdiStartPageEMF` at `0x180001cee`
- `GDI32!GdiEndPageEMF` at `0x180001c1e`
- `GDI32!GdiEndPageEMF` at `0x180001c82`
- `GDI32!GdiEndPageEMF` at `0x180001d01`
- `GDI32!GdiEndPageEMF` at `0x180001c1e`
- `GDI32!GdiEndPageEMF` at `0x180001c82`
- `GDI32!GdiEndPageEMF` at `0x180001d01`
- `GDI32!SetWorldTransform` at `0x180001b06`
- `GDI32!SetWorldTransform` at `0x180001b65`
- `GDI32!SetWorldTransform` at `0x180001b06`
- `GDI32!SetWorldTransform` at `0x180001b65`

## pseudocode

```c
__int64 __fastcall PrintOneSideForwardEMF(
        HANDLE SpoolFileHandle,
        HDC hdc,
        struct _EMF_ATTRIBUTE_INFO *a3,
        int a4,
        DWORD dwOptimization,
        DWORD Page,
        int *a7,
        struct _devicemodeW *a8)
{
  int *v8; // rbx
  __m128i si128; // xmm6
  __m128i v11; // xmm7
  int dmOrientation; // eax
  HDC v13; // r15
  RECT v14; // xmm8
  HANDLE v15; // rsi
  struct _EMF_ATTRIBUTE_INFO *v16; // r12
  int v17; // edx
  int v18; // r13d
  unsigned int v19; // ecx
  int v20; // r8d
  int v21; // eax
  unsigned int j; // edi
  HANDLE PageHandle; // r13
  __int16 v24; // bx
  PDEVMODEW v25; // rdx
  PDEVMODEW v26; // rcx
  struct _devicemodeW *v27; // rdx
  __int16 dmCollate; // ax
  __int64 v29; // rcx
  int v30; // r12d
  int v31; // r15d
  int v32; // ecx
  int v33; // esi
  HDC v34; // rbx
  PDEVMODEW *prectClip; // rbx
  BOOL v36; // eax
  int v37; // ecx
  bool v38; // zf
  PDEVMODEW *v39; // r8
  int v40; // edi
  DWORD v41; // edx
  DWORD i; // edi
  unsigned int v44; // [rsp+3Ch] [rbp-CCh]
  int v45; // [rsp+40h] [rbp-C8h]
  int v46; // [rsp+44h] [rbp-C4h]
  PDEVMODEW pCurrDM; // [rsp+48h] [rbp-C0h] BYREF
  int v48; // [rsp+50h] [rbp-B8h]
  int v49; // [rsp+54h] [rbp-B4h]
  PDEVMODEW v50; // [rsp+58h] [rbp-B0h] BYREF
  HDC hdca; // [rsp+60h] [rbp-A8h]
  HANDLE SpoolFileHandlea; // [rsp+68h] [rbp-A0h]
  DWORD pdwPageType; // [rsp+70h] [rbp-98h] BYREF
  int v54; // [rsp+74h] [rbp-94h]
  __int64 v55; // [rsp+78h] [rbp-90h]
  struct _EMF_ATTRIBUTE_INFO *v56; // [rsp+80h] [rbp-88h]
  int *v57; // [rsp+88h] [rbp-80h]
  PDEVMODEW pLastDM[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v59; // [rsp+A0h] [rbp-68h] BYREF
  XFORM v60; // [rsp+B0h] [rbp-58h] BYREF
  RECT prectBorder; // [rsp+C8h] [rbp-40h] BYREF
  XFORM v62; // [rsp+D8h] [rbp-30h] BYREF
  XFORM xf; // [rsp+F0h] [rbp-18h] BYREF

  v8 = a7;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v11 = _mm_load_si128((const __m128i *)&_xmm);
  dmOrientation = a8->dmOrientation;
  v13 = hdc;
  v14 = (RECT)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v15 = SpoolFileHandle;
  hdca = hdc;
  v16 = a3;
  v17 = *((_DWORD *)a3 + 9);
  v18 = (a4 != 0) + 1;
  SpoolFileHandlea = SpoolFileHandle;
  v19 = *((_DWORD *)a3 + 8);
  v56 = a3;
  v20 = *((_DWORD *)a3 + 11);
  v49 = v18;
  v45 = v18;
  v54 = a4;
  v57 = a7;
  pdwPageType = 0;
  v50 = 0;
  v48 = dmOrientation;
  v44 = v19;
  v46 = v17;
  LODWORD(v55) = v20;
  *a7 = 0;
LABEL_2:
  v21 = *v8;
  if ( !v18 )
  {
    if ( !v21 )
      return Page;
    goto LABEL_71;
  }
  if ( v21 )
  {
LABEL_71:
    if ( v19 == 1 && v17 != 1 && (_DWORD)v55 != 1 )
    {
      v40 = v17 * v49;
      v41 = (Page - 1) % (v17 * v49);
      if ( v41 )
      {
        for ( i = v40 - v41; i; --i )
        {
          if ( !GdiStartPageEMF(v15) || !GdiEndPageEMF(v15, dwOptimization) )
            return 0;
        }
      }
    }
    if ( !*v8 )
      return Page;
    return 0;
  }
  for ( j = 1; ; ++j )
  {
    if ( j > v19 )
    {
      v8 = v57;
      goto LABEL_53;
    }
    PageHandle = GdiGetPageHandle(v15, Page, &pdwPageType);
    if ( !PageHandle )
    {
      if ( GetLastError() != 259 )
        return 0;
      v8 = v57;
      v19 = v44;
      *v57 = 1;
LABEL_53:
      if ( j != 1 )
      {
        if ( !GdiEndPageEMF(v15, dwOptimization) )
        {
LABEL_69:
          *v8 = 0;
          return 0;
        }
        v19 = v44;
      }
      v17 = v46;
      if ( !*v8 || !v54 || v46 != 1 )
        goto LABEL_67;
      if ( j == 1 )
      {
        if ( v45 != 1 )
        {
LABEL_67:
          v18 = --v45;
          goto LABEL_2;
        }
      }
      else if ( v45 != 2 )
      {
        goto LABEL_67;
      }
      if ( (unsigned int)BAnyReasonNotToPrintBlankPage(v16, Page - 1)
        || GdiStartPageEMF(v15) && GdiEndPageEMF(v15, dwOptimization) )
      {
        v17 = v46;
        v19 = v44;
        goto LABEL_67;
      }
      goto LABEL_69;
    }
    v24 = 1;
    if ( j == 1 )
    {
      pCurrDM = 0;
      pLastDM[0] = 0;
      if ( !GdiGetDevmodeForPage(v15, Page, &pCurrDM, pLastDM) )
        return 0;
      if ( !pCurrDM )
        return 0;
      if ( !(unsigned int)BIsDevmodeOfLeastAcceptableSize(pCurrDM) )
        return 0;
      v26 = pLastDM[0];
      if ( pLastDM[0] )
      {
        if ( !(unsigned int)BIsDevmodeOfLeastAcceptableSize(pLastDM[0]) )
          return 0;
      }
      v50 = v25;
      if ( v26 != v25 )
      {
        v25->dmPrintQuality = a8->dmPrintQuality;
        pCurrDM->dmYResolution = a8->dmYResolution;
        pCurrDM->dmCopies = a8->dmCopies;
        v27 = pCurrDM;
        if ( pCurrDM->dmSize >= 0x66u )
        {
          if ( a8->dmSize < 0x66u )
            dmCollate = 0;
          else
            dmCollate = a8->dmCollate;
          pCurrDM->dmCollate = dmCollate;
          v27 = pCurrDM;
        }
        GdiResetDCEMF(v15, v27);
        SetGraphicsMode(v13, 2);
        BUpdateAttributes(v13, v16);
        v25 = v50;
      }
      if ( v25 )
        v48 = v25->dmOrientation;
      if ( !GdiStartPageEMF(v15) )
        return 0;
    }
    else if ( v44 > 1 )
    {
      v50 = 0;
      if ( GdiGetDevmodeForPage(v15, Page, &v50, 0) )
      {
        if ( v50 && (unsigned int)BIsDevmodeOfLeastAcceptableSize(v50) && *(__int16 *)(v29 + 76) != v48 )
        {
          v24 = -32767;
          BUpdateAttributes(v13, v16);
        }
      }
    }
    v30 = 0;
    LODWORD(pCurrDM) = 0;
    v31 = *((_DWORD *)v56 + 8);
    *(_QWORD *)&v62.eDx = 0;
    *(_QWORD *)&xf.eDx = 0;
    *(_OWORD *)pLastDM = 0;
    *(_QWORD *)&v60.eDx = 0;
    v59 = 0;
    prectBorder = v14;
    *(__m128i *)&v62.eM11 = si128;
    *(__m128i *)&xf.eM11 = v11;
    *(__m128i *)&v60.eM11 = si128;
    if ( !(unsigned int)GetPageCoordinatesForNUp(hdca, v56, (struct tagRECT *)pLastDM, &prectBorder, j, (int *)&pCurrDM) )
      goto LABEL_42;
    v32 = 0;
    v33 = v24 < 0 ? (_DWORD)pCurrDM == 0 : (int)pCurrDM;
    if ( v33 )
      break;
LABEL_38:
    prectClip = pLastDM;
    if ( v31 == 1 )
    {
      prectClip = 0;
      v60.eM11 = *((FLOAT *)v56 + 22);
      v60.eM22 = v60.eM11;
      if ( v32 )
      {
        if ( !ModifyWorldTransform(hdca, &v60, 3u) )
        {
LABEL_41:
          v15 = SpoolFileHandlea;
          goto LABEL_42;
        }
      }
      else if ( !SetWorldTransform(hdca, &v60) )
      {
        goto LABEL_41;
      }
    }
    v38 = v33 == 0;
    v15 = SpoolFileHandlea;
    v39 = (PDEVMODEW *)&v59;
    if ( v38 )
      v39 = pLastDM;
    GdiPlayPageEMF(SpoolFileHandlea, PageHandle, (RECT *)v39, &prectBorder, (RECT *)prectClip);
    v30 = 1;
LABEL_42:
    v13 = hdca;
    v36 = ModifyWorldTransform(hdca, 0, 1u);
    v37 = 0;
    if ( v36 )
      v37 = v30;
    if ( !v37 )
      return 0;
    v16 = v56;
    v19 = v44;
    ++Page;
  }
  v34 = hdca;
  *(_QWORD *)&v59 = 0;
  HIDWORD(v59) = LODWORD(pLastDM[1]) - LODWORD(pLastDM[0]);
  DWORD2(v59) = HIDWORD(pLastDM[1]) - HIDWORD(pLastDM[0]);
  v62.eDy = (float)SHIDWORD(pLastDM[1]);
  v62.eDx = (float)SLODWORD(pLastDM[0]);
  if ( SetWorldTransform(hdca, &xf) && ModifyWorldTransform(v34, &v62, 3u) )
  {
    v32 = 1;
    goto LABEL_38;
  }
  ModifyWorldTransform(v34, 0, 1u);
  return 0;
}

```

## disassembly

```asm
0x1800017d0  mov     rax, rsp
0x1800017d3  mov     [rax+20h], rbx
0x1800017d7  push    rbp
0x1800017d8  push    rsi
0x1800017d9  push    rdi
0x1800017da  push    r12
0x1800017dc  push    r13
0x1800017de  push    r14
0x1800017e0  push    r15
0x1800017e2  lea     rbp, [rax-78h]
0x1800017e6  sub     rsp, 140h
0x1800017ed  movaps  xmmword ptr [rax-48h], xmm6
0x1800017f1  movaps  xmmword ptr [rax-58h], xmm7
0x1800017f5  movaps  xmmword ptr [rax-68h], xmm8
0x1800017fa  mov     rax, cs:__security_cookie
0x180001801  xor     rax, rsp
0x180001804  mov     [rbp+70h+var_70], rax
0x180001808  mov     rbx, [rbp+70h+arg_30]
0x18000180f  xor     r10d, r10d
0x180001812  mov     rax, [rbp+70h+arg_38]
0x180001819  test    r9d, r9d
0x18000181c  mov     r14d, [rbp+70h+Page]
0x180001823  mov     edi, r10d
0x180001826  movdqa  xmm6, cs:__xmm@3f80000000000000000000003f800000
0x18000182e  setnz   dil
0x180001832  movdqa  xmm7, cs:__xmm@000000003f800000bf80000000000000
0x18000183a  inc     edi
0x18000183c  movsx   eax, word ptr [rax+4Ch]
0x180001840  mov     r15, rdx
0x180001843  movdqa  xmm8, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000184c  mov     rsi, rcx
0x18000184f  mov     [rsp+170h+hdc], rdx
0x180001854  mov     r12, r8
0x180001857  mov     edx, [r8+24h]
0x18000185b  mov     r13d, edi
0x18000185e  mov     [rsp+170h+SpoolFileHandle], rcx
0x180001863  mov     ecx, [r8+20h]
0x180001867  mov     [rsp+170h+var_F8], r8
0x18000186c  mov     r8d, [r8+2Ch]
0x180001870  mov     dword ptr [rsp+170h+var_128+4], edi
0x180001874  mov     dword ptr [rsp+170h+var_138], edi
0x180001878  mov     [rsp+170h+var_104], r9d
0x18000187d  mov     [rbp+70h+var_F0], rbx
0x180001881  mov     [rsp+170h+pdwPageType], r10d
0x180001886  mov     [rsp+170h+var_140], r10d
0x18000188b  mov     [rsp+170h+var_120], r10
0x180001890  mov     dword ptr [rsp+170h+var_128], eax
0x180001894  mov     [rsp+170h+var_13C], ecx
0x180001898  mov     dword ptr [rsp+170h+var_138+4], edx
0x18000189c  mov     dword ptr [rsp+170h+var_100], r8d
0x1800018a1  mov     [rbx], r10d
0x1800018a4  mov     eax, [rbx]
0x1800018a6  test    r13d, r13d
0x1800018a9  jz      loc_180001CBF
0x1800018af  test    eax, eax
0x1800018b1  jnz     loc_180001CC3
0x1800018b7  mov     edi, 1
0x1800018bc  nop     dword ptr [rax+00h]
0x1800018c0  cmp     edi, ecx
0x1800018c2  ja      loc_180001C0C
0x1800018c8  lea     r8, [rsp+170h+pdwPageType]; pdwPageType
0x1800018cd  mov     edx, r14d; Page
0x1800018d0  mov     rcx, rsi; SpoolFileHandle
0x1800018d3  call    cs:__imp_GdiGetPageHandle
0x1800018d9  mov     r13, rax
0x1800018dc  test    rax, rax
0x1800018df  jz      loc_180001BEB
0x1800018e5  mov     ebx, 1
0x1800018ea  cmp     edi, ebx
0x1800018ec  jnz     loc_1800019F0
0x1800018f2  xor     eax, eax
0x1800018f4  lea     r9, [rbp+70h+pLastDM]; pLastDM
0x1800018f8  lea     r8, [rsp+170h+pCurrDM]; pCurrDM
0x1800018fd  mov     [rsp+170h+pCurrDM], rax
0x180001902  mov     edx, r14d; dwPageNumber
0x180001905  mov     [rbp+70h+pLastDM], rax
0x180001909  mov     rcx, rsi; SpoolFileHandle
0x18000190c  call    cs:__imp_GdiGetDevmodeForPage
0x180001912  test    eax, eax
0x180001914  jz      loc_180001D14
0x18000191a  mov     rdx, [rsp+170h+pCurrDM]
0x18000191f  test    rdx, rdx
0x180001922  jz      loc_180001D14
0x180001928  mov     rcx, rdx; struct _devicemodeW *
0x18000192b  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180001930  test    eax, eax
0x180001932  jz      loc_180001D14
0x180001938  mov     rcx, [rbp+70h+pLastDM]; struct _devicemodeW *
0x18000193c  test    rcx, rcx
0x18000193f  jz      short loc_18000194E
0x180001941  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180001946  test    eax, eax
0x180001948  jz      loc_180001D14
0x18000194e  mov     [rsp+170h+var_120], rdx
0x180001953  cmp     rcx, rdx
0x180001956  jz      short loc_1800019D1
0x180001958  mov     r8, [rbp+70h+arg_38]
0x18000195f  movzx   eax, word ptr [r8+5Ah]
0x180001964  mov     [rdx+5Ah], ax
0x180001968  mov     rax, [rsp+170h+pCurrDM]
0x18000196d  movzx   ecx, word ptr [r8+60h]
0x180001972  mov     [rax+60h], cx
0x180001976  mov     rax, [rsp+170h+pCurrDM]
0x18000197b  movzx   ecx, word ptr [r8+56h]
0x180001980  mov     [rax+56h], cx
0x180001984  mov     rdx, [rsp+170h+pCurrDM]
0x180001989  cmp     word ptr [rdx+44h], 66h ; 'f'
0x18000198e  jb      short loc_1800019AA
0x180001990  cmp     word ptr [r8+44h], 66h ; 'f'
0x180001996  jb      short loc_18000199F
0x180001998  movzx   eax, word ptr [r8+64h]
0x18000199d  jmp     short loc_1800019A1
0x18000199f  xor     eax, eax
0x1800019a1  mov     [rdx+64h], ax
0x1800019a5  mov     rdx, [rsp+170h+pCurrDM]; pCurrDM
0x1800019aa  mov     rcx, rsi; SpoolFileHandle
0x1800019ad  call    cs:__imp_GdiResetDCEMF
0x1800019b3  mov     edx, 2; iMode
0x1800019b8  mov     rcx, r15; hdc
0x1800019bb  call    cs:__imp_SetGraphicsMode
0x1800019c1  mov     rdx, r12; struct _EMF_ATTRIBUTE_INFO *
0x1800019c4  mov     rcx, r15; hdc
0x1800019c7  call    ?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z; BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)
0x1800019cc  mov     rdx, [rsp+170h+var_120]
0x1800019d1  test    rdx, rdx
0x1800019d4  jz      short loc_1800019DE
0x1800019d6  movsx   eax, word ptr [rdx+4Ch]
0x1800019da  mov     dword ptr [rsp+170h+var_128], eax
0x1800019de  mov     rcx, rsi; SpoolFileHandle
0x1800019e1  call    cs:__imp_GdiStartPageEMF
0x1800019e7  test    eax, eax
0x1800019e9  jnz     short loc_180001A44
0x1800019eb  jmp     loc_180001D14
0x1800019f0  cmp     [rsp+170h+var_13C], ebx
0x1800019f4  jbe     short loc_180001A44
0x1800019f6  xor     r9d, r9d; pLastDM
0x1800019f9  mov     [rsp+170h+var_120], 0
0x180001a02  lea     r8, [rsp+170h+var_120]; pCurrDM
0x180001a07  mov     edx, r14d; dwPageNumber
0x180001a0a  mov     rcx, rsi; SpoolFileHandle
0x180001a0d  call    cs:__imp_GdiGetDevmodeForPage
0x180001a13  test    eax, eax
0x180001a15  jz      short loc_180001A44
0x180001a17  mov     rcx, [rsp+170h+var_120]; struct _devicemodeW *
0x180001a1c  test    rcx, rcx
0x180001a1f  jz      short loc_180001A44
0x180001a21  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180001a26  test    eax, eax
0x180001a28  jz      short loc_180001A44
0x180001a2a  movsx   eax, word ptr [rcx+4Ch]
0x180001a2e  cmp     eax, dword ptr [rsp+170h+var_128]
0x180001a32  jz      short loc_180001A44
0x180001a34  mov     rdx, r12; struct _EMF_ATTRIBUTE_INFO *
0x180001a37  mov     rcx, r15; hdc
0x180001a3a  mov     ebx, 8001h
0x180001a3f  call    ?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z; BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)
0x180001a44  mov     rax, [rsp+170h+var_F8]
0x180001a49  lea     rcx, [rsp+170h+pCurrDM]
0x180001a4e  xor     r12d, r12d
0x180001a51  mov     [rsp+170h+var_148], rcx; int *
0x180001a56  mov     rcx, [rsp+170h+hdc]; hdc
0x180001a5b  lea     r9, [rbp+70h+prectBorder]; struct tagRECT *
0x180001a5f  xorps   xmm0, xmm0
0x180001a62  mov     dword ptr [rsp+170h+pCurrDM], r12d
0x180001a67  mov     r15d, [rax+20h]
0x180001a6b  lea     r8, [rbp+70h+pLastDM]; struct tagRECT *
0x180001a6f  xorps   xmm1, xmm1
0x180001a72  mov     qword ptr [rbp+70h+var_A0.eDx], r12
0x180001a76  mov     rdx, rax; struct _EMF_ATTRIBUTE_INFO *
0x180001a79  mov     qword ptr [rbp+70h+xf.eDx], r12
0x180001a7d  movups  xmmword ptr [rbp+70h+pLastDM], xmm0
0x180001a81  mov     qword ptr [rbp+70h+var_C8.eDx], r12
0x180001a85  movups  [rbp+70h+var_D8], xmm1
0x180001a89  mov     dword ptr [rsp+170h+prectClip], edi; unsigned int
0x180001a8d  movdqu  xmmword ptr [rbp+70h+prectBorder.left], xmm8
0x180001a93  movups  xmmword ptr [rbp+70h+var_A0.eM11], xmm6
0x180001a97  movups  xmmword ptr [rbp+70h+xf.eM11], xmm7
0x180001a9b  movups  xmmword ptr [rbp+70h+var_C8.eM11], xmm6
0x180001a9f  call    ?GetPageCoordinatesForNUp@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@PEAUtagRECT@@2IPEAH@Z; GetPageCoordinatesForNUp(void *,_EMF_ATTRIBUTE_INFO *,tagRECT *,tagRECT *,uint,int *)
0x180001aa4  test    eax, eax
0x180001aa6  jz      loc_180001B74
0x180001aac  xor     ecx, ecx
0x180001aae  bt      ebx, 0Fh
0x180001ab2  jnb     short loc_180001AC0
0x180001ab4  xor     esi, esi
0x180001ab6  cmp     dword ptr [rsp+170h+pCurrDM], ecx
0x180001aba  setz    sil
0x180001abe  jmp     short loc_180001AC4
0x180001ac0  mov     esi, dword ptr [rsp+170h+pCurrDM]
0x180001ac4  test    esi, esi
0x180001ac6  jz      short loc_180001B34
0x180001ac8  mov     edx, dword ptr [rbp+70h+pLastDM]
0x180001acb  mov     eax, dword ptr [rbp+70h+pLastDM+8]
0x180001ace  mov     rbx, [rsp+170h+hdc]
0x180001ad3  sub     eax, edx
0x180001ad5  mov     qword ptr [rbp+70h+var_D8], rcx
0x180001ad9  mov     ecx, dword ptr [rbp+70h+pLastDM+0Ch]
0x180001adc  movd    xmm0, edx
0x180001ae0  lea     rdx, [rbp+70h+xf]; lpxf
0x180001ae4  mov     dword ptr [rbp+70h+var_D8+0Ch], eax
0x180001ae7  mov     eax, ecx
0x180001ae9  sub     eax, dword ptr [rbp+70h+pLastDM+4]
0x180001aec  movd    xmm1, ecx
0x180001af0  mov     rcx, rbx; hdc
0x180001af3  cvtdq2ps xmm1, xmm1
0x180001af6  mov     dword ptr [rbp+70h+var_D8+8], eax
0x180001af9  cvtdq2ps xmm0, xmm0
0x180001afc  movss   [rbp+70h+var_A0.eDy], xmm1
0x180001b01  movss   [rbp+70h+var_A0.eDx], xmm0
0x180001b06  call    cs:__imp_SetWorldTransform
0x180001b0c  test    eax, eax
0x180001b0e  jz      loc_180001CA1
0x180001b14  mov     r8d, 3; mode
0x180001b1a  lea     rdx, [rbp+70h+var_A0]; lpxf
0x180001b1e  mov     rcx, rbx; hdc
0x180001b21  call    cs:__imp_ModifyWorldTransform
0x180001b27  test    eax, eax
0x180001b29  jz      loc_180001CA1
0x180001b2f  mov     ecx, 1
0x180001b34  xor     eax, eax
0x180001b36  lea     rbx, [rbp+70h+pLastDM]
0x180001b3a  cmp     r15d, 1
0x180001b3e  cmovz   rbx, rax
0x180001b42  jnz     short loc_180001BBD
0x180001b44  mov     rax, [rsp+170h+var_F8]
0x180001b49  lea     rdx, [rbp+70h+var_C8]; lpxf
0x180001b4d  test    ecx, ecx
0x180001b4f  mov     rcx, [rsp+170h+hdc]; hdc
0x180001b54  movss   xmm0, dword ptr [rax+58h]
0x180001b59  movss   [rbp+70h+var_C8.eM11], xmm0
0x180001b5e  movss   [rbp+70h+var_C8.eM22], xmm0
0x180001b63  jnz     short loc_180001BAD
0x180001b65  call    cs:__imp_SetWorldTransform
0x180001b6b  test    eax, eax
0x180001b6d  jnz     short loc_180001BBD
0x180001b6f  mov     rsi, [rsp+170h+SpoolFileHandle]
0x180001b74  mov     r15, [rsp+170h+hdc]
0x180001b79  xor     edx, edx; lpxf
0x180001b7b  mov     rcx, r15; hdc
0x180001b7e  mov     r8d, 1; mode
0x180001b84  call    cs:__imp_ModifyWorldTransform
0x180001b8a  xor     ecx, ecx
0x180001b8c  test    eax, eax
0x180001b8e  cmovnz  ecx, r12d
0x180001b92  test    ecx, ecx
0x180001b94  jz      loc_180001D14
0x180001b9a  mov     r12, [rsp+170h+var_F8]
0x180001b9f  inc     edi
0x180001ba1  mov     ecx, [rsp+170h+var_13C]
0x180001ba5  inc     r14d
0x180001ba8  jmp     loc_1800018C0
0x180001bad  mov     r8d, 3; mode
0x180001bb3  call    cs:__imp_ModifyWorldTransform
0x180001bb9  test    eax, eax
0x180001bbb  jz      short loc_180001B6F
0x180001bbd  test    esi, esi
0x180001bbf  mov     [rsp+170h+prectClip], rbx; prectClip
0x180001bc4  mov     rsi, [rsp+170h+SpoolFileHandle]
0x180001bc9  lea     r9, [rbp+70h+prectBorder]; prectBorder
0x180001bcd  mov     rcx, rsi; SpoolFileHandle
0x180001bd0  lea     r8, [rbp+70h+var_D8]
0x180001bd4  mov     rdx, r13; hemf
0x180001bd7  jnz     short loc_180001BDD
0x180001bd9  lea     r8, [rbp+70h+pLastDM]; prectDocument
0x180001bdd  call    cs:__imp_GdiPlayPageEMF
0x180001be3  mov     r12d, 1
0x180001be9  jmp     short loc_180001B74
0x180001beb  call    cs:__imp_GetLastError
0x180001bf1  cmp     eax, 103h
0x180001bf6  jnz     loc_180001D14
0x180001bfc  mov     rbx, [rbp+70h+var_F0]
0x180001c00  mov     ecx, [rsp+170h+var_13C]
0x180001c04  mov     dword ptr [rbx], 1
0x180001c0a  jmp     short loc_180001C10
0x180001c0c  mov     rbx, [rbp+70h+var_F0]
0x180001c10  cmp     edi, 1
0x180001c13  jz      short loc_180001C30
0x180001c15  mov     edx, [rbp+70h+dwOptimization]; dwOptimization
0x180001c1b  mov     rcx, rsi; SpoolFileHandle
0x180001c1e  call    cs:__imp_GdiEndPageEMF
0x180001c24  test    eax, eax
0x180001c26  jz      loc_180001CB7
0x180001c2c  mov     ecx, [rsp+170h+var_13C]
0x180001c30  cmp     dword ptr [rbx], 0
0x180001c33  mov     edx, dword ptr [rsp+170h+var_138+4]
0x180001c37  mov     r13d, dword ptr [rsp+170h+var_138]
0x180001c3c  jz      short loc_180001C94
0x180001c3e  cmp     [rsp+170h+var_104], 0
0x180001c43  jz      short loc_180001C94
0x180001c45  cmp     edx, 1
0x180001c48  jnz     short loc_180001C94
0x180001c4a  cmp     edi, edx
0x180001c4c  jz      short loc_180001C56
0x180001c4e  cmp     r13d, 2
0x180001c52  jz      short loc_180001C5C
0x180001c54  jmp     short loc_180001C94
0x180001c56  cmp     r13d, 1
0x180001c5a  jnz     short loc_180001C94
0x180001c5c  lea     edx, [r14-1]; unsigned int
0x180001c60  mov     rcx, r12; struct _EMF_ATTRIBUTE_INFO *
  ... truncated ...
```
