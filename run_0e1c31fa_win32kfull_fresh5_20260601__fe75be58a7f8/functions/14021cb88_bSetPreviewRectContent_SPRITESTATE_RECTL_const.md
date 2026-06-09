# bSetPreviewRectContent(_SPRITESTATE *,_RECTL const *)

- ea: `0x14021cb88`
- end: `0x14021d087`
- name: `?bSetPreviewRectContent@@YAHPEAU_SPRITESTATE@@PEBU_RECTL@@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(struct _SPRITESTATE *, const struct _RECTL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14021c87c`

## callees

- `0x14006c84c`
- `0x14007eef8`
- `0x14007f010`
- `0x140086434`
- `0x140091e34`
- `0x1401683b8`
- `0x14021cb88`
- `0x140232900`
- `0x140296924`
- `0x140306698`
- `0x140341ff0`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x14021cbf6`
- `win32kbase!GreCreateCompatibleDC` at `0x14021cbf6`
- `win32kbase!GreDeleteDC` at `0x14021d04d`
- `win32kbase!GreDeleteDC` at `0x14021d04d`
- `win32kbase!UserGetHDEV` at `0x14021cf08`
- `win32kbase!UserGetHDEV` at `0x14021cf08`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14021cc05`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14021cc05`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021cfd6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021cff6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021cfd6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021cff6`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021cd4e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021cdf4`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021cd4e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021cdf4`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021ceaa`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021cfa1`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021ceaa`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021cfa1`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021d006`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021d016`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021d006`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021d016`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021cc8f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021ccdc`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021cc8f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021ccdc`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021cfe6`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021cfe6`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021cc2d`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021d03e`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021cc2d`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021d03e`
- `WIN32K!W32GetUserSessionState` at `0x14021cbdf`
- `WIN32K!W32GetUserSessionState` at `0x14021cbdf`

## pseudocode

```c
__int64 __fastcall bSetPreviewRectContent(struct _SPRITESTATE *a1, const struct _RECTL *a2)
{
  unsigned int updated; // r15d
  LONG v5; // edx
  __int64 UserSessionState; // rax
  struct HOBJ__ *CompatibleDC; // rsi
  Gre::Base *v8; // rcx
  struct Gre::Base::SESSION_GLOBALS *v9; // rax
  struct Gre::Base::SESSION_GLOBALS *v10; // r14
  unsigned int v11; // edx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdi
  void *v15; // rbx
  HDEV HDEV; // rax
  __int64 v17; // r9
  struct _BLENDFUNCTION v19; // [rsp+80h] [rbp-80h] BYREF
  struct tagSIZE v20; // [rsp+88h] [rbp-78h] BYREF
  struct PALETTE *v21; // [rsp+90h] [rbp-70h] BYREF
  int v22; // [rsp+98h] [rbp-68h]
  struct _RECTL v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-40h]
  _QWORD v26[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct tagPOINT v27[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct PALETTE *v28; // [rsp+F8h] [rbp-8h] BYREF
  int v29; // [rsp+100h] [rbp+0h]
  _QWORD v30[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v31[14]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v32[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v33[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v34[112]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v35[112]; // [rsp+220h] [rbp+120h] BYREF
  struct _RECTL v36; // [rsp+290h] [rbp+190h] BYREF
  __m128i si128; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v38; // [rsp+2B0h] [rbp+1B0h]
  __m128i v39; // [rsp+2B4h] [rbp+1B4h]

  updated = 0;
  v5 = a2->right - a2->left;
  v20.cy = a2->bottom - a2->top;
  v24 = 0;
  v20.cx = v5;
  v25 = 0;
  UserSessionState = W32GetUserSessionState((unsigned int)v20.cy);
  CompatibleDC = (struct HOBJ__ *)GreCreateCompatibleDC(*(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 56LL));
  v9 = Gre::Base::Globals(v8);
  v10 = v9;
  if ( CompatibleDC )
  {
    GrepSetDCOwnerEx(v9, CompatibleDC, 0, 0, 0);
    APIDCOBJ::APIDCOBJ((APIDCOBJ *)v31, (HDC)CompatibleDC, v10);
    if ( v31[0] )
    {
      v29 = 0;
      v28 = 0;
      if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v28, 8u, 0, 0, 0xFF0000u, 0xFF00u, 0xFFu, 0x300u, 1) )
      {
        v22 = 0;
        v21 = 0;
        if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v21, 8u, 0, 0, 0xFF0000u, 0xFF00u, 0xFFu, 0x200u, 1) )
        {
          *(struct tagSIZE *)((char *)&v24 + 4) = v20;
          v22 = 1;
          LODWORD(v24) = 6;
          HIDWORD(v24) = 0;
          *(_QWORD *)&v25 = *(_QWORD *)v21;
          DWORD2(v25) = 1;
          SURFMEM::SURFMEM(v26, 2);
          if ( SURFMEM::bCreateDIB((SURFMEM *)v26, (struct _DEVBITMAPINFO *)&v24, 0, 0, 0, 0, 0, 0, 1, 0) && v26[0] )
          {
            SURFMEM::vSetPID((SURFMEM *)v26, v11);
            *((_QWORD *)&v24 + 1) = 0x2400000003LL;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v38 = 1174412344;
            v39 = si128;
            *(_QWORD *)&v24 = 0x300000006LL;
            *(_QWORD *)&v25 = *(_QWORD *)v21;
            DWORD2(v25) = 1;
            SURFMEM::SURFMEM(v30, 2);
            if ( SURFMEM::bCreateDIB((SURFMEM *)v30, (struct _DEVBITMAPINFO *)&v24, &si128, 0, 0, 0, 0, 0, 1, 0) )
            {
              if ( v30[0] )
              {
                *(struct tagSIZE *)&v23.right = v20;
                *(_QWORD *)&v23.left = 0;
                v36 = (struct _RECTL)_mm_load_si128((const __m128i *)&_xmm);
                *(__m128i *)&v27[0].x = _mm_load_si128((const __m128i *)&_xmm);
                updated = EngNineGridHelper(
                            (struct XDCOBJ *)v31,
                            v21,
                            v28,
                            (struct _SURFOBJ *)(v26[0] + 24LL),
                            (struct _SURFOBJ *)(v30[0] + 24LL),
                            &v23,
                            &v36,
                            (struct _MARGINS *)v27);
                if ( updated )
                {
                  LOBYTE(v12) = 4;
                  v13 = *(_QWORD *)(v26[0] + 32LL);
                  *(_DWORD *)(v26[0] + 160LL) |= 0x4000000u;
                  v14 = *(_QWORD *)GrepSelectBitmap(v32, v31, v13, v12);
                  *(_DWORD *)(v26[0] + 160LL) &= ~0x4000000u;
                  v23.left = a2->left;
                  v23.top = a2->top;
                  v19 = (struct _BLENDFUNCTION)33488896;
                  v27[0] = 0;
                  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v35, 0);
                  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v34, (struct XDCOBJ *)v31);
                  v15 = (void *)*((_QWORD *)a1 + 146);
                  HDEV = (HDEV)UserGetHDEV();
                  updated = GrepUpdateSprite(
                              HDEV,
                              0,
                              v15,
                              (struct OPTAPIDCOBJ *)v35,
                              (struct tagPOINT *)&v23,
                              &v20,
                              (struct OPTAPIDCOBJ *)v34,
                              v27,
                              0,
                              &v19,
                              2u,
                              0,
                              0,
                              1,
                              0,
                              0);
                  LOBYTE(v17) = 4;
                  *(_DWORD *)(v26[0] + 160LL) |= 0x4000000u;
                  GrepSelectBitmap(v33, v31, v14, v17);
                  *(_DWORD *)(v26[0] + 160LL) &= ~0x4000000u;
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v34);
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v35);
                }
              }
            }
            SURFMEM::~SURFMEM((SURFMEM *)v30);
          }
          XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v21);
          SURFMEM::~SURFMEM((SURFMEM *)v26);
        }
        PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v21);
      }
      PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v28);
    }
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v31);
    GrepSetDCOwnerEx(v10, CompatibleDC, 0x80000002, 0, 0);
    GreDeleteDC(CompatibleDC);
  }
  return updated;
}

```

## disassembly

```asm
0x14021cb88  mov     [rsp-8+arg_10], rbx
0x14021cb8d  push    rbp
0x14021cb8e  push    rsi
0x14021cb8f  push    rdi
0x14021cb90  push    r12
0x14021cb92  push    r13
0x14021cb94  push    r14
0x14021cb96  push    r15
0x14021cb98  lea     rbp, [rsp-1D0h]
0x14021cba0  sub     rsp, 2D0h
0x14021cba7  mov     rax, cs:__security_cookie
0x14021cbae  xor     rax, rsp
0x14021cbb1  mov     [rbp+200h+var_38], rax
0x14021cbb8  mov     rbx, rdx
0x14021cbbb  mov     r13, rcx
0x14021cbbe  mov     edx, [rdx+8]
0x14021cbc1  xorps   xmm0, xmm0
0x14021cbc4  xor     edi, edi
0x14021cbc6  mov     r15d, edi
0x14021cbc9  mov     ecx, [rbx+0Ch]
0x14021cbcc  sub     ecx, [rbx+4]
0x14021cbcf  sub     edx, [rbx]
0x14021cbd1  mov     [rbp+200h+var_278.cy], ecx
0x14021cbd4  movups  [rbp+200h+var_250], xmm0
0x14021cbd8  mov     [rbp+200h+var_278.cx], edx
0x14021cbdb  movups  [rbp+200h+var_240], xmm0
0x14021cbdf  call    cs:__imp_W32GetUserSessionState
0x14021cbe6  nop     dword ptr [rax+rax+00h]
0x14021cbeb  mov     rcx, [rax+0DDA8h]
0x14021cbf2  mov     rcx, [rcx+38h]
0x14021cbf6  call    cs:__imp_GreCreateCompatibleDC
0x14021cbfd  nop     dword ptr [rax+rax+00h]
0x14021cc02  mov     rsi, rax
0x14021cc05  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14021cc0c  nop     dword ptr [rax+rax+00h]
0x14021cc11  mov     r14, rax
0x14021cc14  test    rsi, rsi
0x14021cc17  jz      loc_14021D059
0x14021cc1d  xor     r9d, r9d
0x14021cc20  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021cc24  xor     r8d, r8d
0x14021cc27  mov     rdx, rsi
0x14021cc2a  mov     rcx, rax
0x14021cc2d  call    cs:__imp_?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z; GrepSetDCOwnerEx(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,ulong,int,int)
0x14021cc34  nop     dword ptr [rax+rax+00h]
0x14021cc39  mov     r8, r14; struct Gre::Base::SESSION_GLOBALS *
0x14021cc3c  lea     rcx, [rbp+200h+var_1E0]; this
0x14021cc40  mov     rdx, rsi; HDC
0x14021cc43  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *,Gre::Base::SESSION_GLOBALS &)
0x14021cc48  cmp     [rbp+200h+var_1E0], rdi
0x14021cc4c  jz      loc_14021D022
0x14021cc52  lea     r12d, [rdi+1]
0x14021cc56  mov     [rbp+200h+var_200], edi
0x14021cc59  mov     [rsp+300h+var_2C0], r12d
0x14021cc5e  lea     edx, [rdi+8]
0x14021cc61  mov     dword ptr [rsp+300h+var_2C8], 300h
0x14021cc69  lea     rcx, [rbp+200h+var_208]
0x14021cc6d  mov     dword ptr [rsp+300h+var_2D0], 0FFh
0x14021cc75  xor     r9d, r9d
0x14021cc78  mov     dword ptr [rsp+300h+var_2D8], 0FF00h
0x14021cc80  xor     r8d, r8d
0x14021cc83  mov     dword ptr [rsp+300h+var_2E0], 0FF0000h
0x14021cc8b  mov     [rbp+200h+var_208], rdi
0x14021cc8f  call    cs:__imp_?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z; PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)
0x14021cc96  nop     dword ptr [rax+rax+00h]
0x14021cc9b  test    eax, eax
0x14021cc9d  jz      loc_14021D012
0x14021cca3  mov     [rsp+300h+var_2C0], r12d
0x14021cca8  lea     edx, [rdi+8]
0x14021ccab  mov     dword ptr [rsp+300h+var_2C8], 200h
0x14021ccb3  lea     rcx, [rbp+200h+var_270]
0x14021ccb7  mov     dword ptr [rsp+300h+var_2D0], 0FFh
0x14021ccbf  xor     r9d, r9d
0x14021ccc2  mov     dword ptr [rsp+300h+var_2D8], 0FF00h
0x14021ccca  xor     r8d, r8d
0x14021cccd  mov     dword ptr [rsp+300h+var_2E0], 0FF0000h
0x14021ccd5  mov     [rbp+200h+var_268], edi
0x14021ccd8  mov     [rbp+200h+var_270], rdi
0x14021ccdc  call    cs:__imp_?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z; PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)
0x14021cce3  nop     dword ptr [rax+rax+00h]
0x14021cce8  test    eax, eax
0x14021ccea  jz      loc_14021D002
0x14021ccf0  mov     eax, [rbp+200h+var_278.cx]
0x14021ccf3  lea     edx, [rdi+2]
0x14021ccf6  mov     dword ptr [rbp+200h+var_250+4], eax
0x14021ccf9  mov     eax, [rbp+200h+var_278.cy]
0x14021ccfc  mov     dword ptr [rbp+200h+var_250+8], eax
0x14021ccff  mov     rax, [rbp+200h+var_270]
0x14021cd03  mov     [rbp+200h+var_268], r12d
0x14021cd07  mov     dword ptr [rbp+200h+var_250], 6
0x14021cd0e  mov     dword ptr [rbp+200h+var_250+0Ch], edi
0x14021cd11  mov     rcx, [rax]
0x14021cd14  mov     qword ptr [rbp+200h+var_240], rcx
0x14021cd18  lea     rcx, [rbp+200h+var_230]
0x14021cd1c  mov     dword ptr [rbp+200h+var_240+8], r12d
0x14021cd20  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x14021cd25  mov     dword ptr [rsp+300h+var_2B8], edi
0x14021cd29  lea     rdx, [rbp+200h+var_250]
0x14021cd2d  mov     [rsp+300h+var_2C0], r12d
0x14021cd32  lea     rcx, [rbp+200h+var_230]
0x14021cd36  mov     dword ptr [rsp+300h+var_2C8], edi
0x14021cd3a  xor     r9d, r9d
0x14021cd3d  mov     [rsp+300h+var_2D0], rdi
0x14021cd42  xor     r8d, r8d
0x14021cd45  mov     [rsp+300h+var_2D8], rdi
0x14021cd4a  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021cd4e  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x14021cd55  nop     dword ptr [rax+rax+00h]
0x14021cd5a  test    eax, eax
0x14021cd5c  jz      loc_14021CFE2
0x14021cd62  cmp     [rbp+200h+var_230], rdi
0x14021cd66  jz      loc_14021CFE2
0x14021cd6c  lea     rcx, [rbp+200h+var_230]; this
0x14021cd70  call    ?vSetPID@SURFMEM@@QEAAXK@Z; SURFMEM::vSetPID(ulong)
0x14021cd75  movdqa  xmm0, cs:__xmm@8c0038708c0038708c0038708c003870
0x14021cd7d  lea     eax, [rdi+3]
0x14021cd80  mov     dword ptr [rbp+200h+var_250+4], eax
0x14021cd83  lea     edx, [rdi+2]
0x14021cd86  mov     dword ptr [rbp+200h+var_250+8], eax
0x14021cd89  mov     rax, [rbp+200h+var_270]
0x14021cd8d  movups  [rbp+200h+var_60], xmm0
0x14021cd94  mov     [rbp+200h+var_50], 46001C38h
0x14021cd9e  movups  [rbp+200h+var_4C], xmm0
0x14021cda5  mov     dword ptr [rbp+200h+var_250], 6
0x14021cdac  mov     dword ptr [rbp+200h+var_250+0Ch], 24h ; '$'
0x14021cdb3  mov     rcx, [rax]
0x14021cdb6  mov     qword ptr [rbp+200h+var_240], rcx
0x14021cdba  lea     rcx, [rbp+200h+var_1F8]
0x14021cdbe  mov     dword ptr [rbp+200h+var_240+8], r12d
0x14021cdc2  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x14021cdc7  mov     dword ptr [rsp+300h+var_2B8], edi
0x14021cdcb  lea     r8, [rbp+200h+var_60]
0x14021cdd2  mov     [rsp+300h+var_2C0], r12d
0x14021cdd7  lea     rdx, [rbp+200h+var_250]
0x14021cddb  mov     dword ptr [rsp+300h+var_2C8], edi
0x14021cddf  lea     rcx, [rbp+200h+var_1F8]
0x14021cde3  mov     [rsp+300h+var_2D0], rdi
0x14021cde8  xor     r9d, r9d
0x14021cdeb  mov     [rsp+300h+var_2D8], rdi
0x14021cdf0  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021cdf4  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x14021cdfb  nop     dword ptr [rax+rax+00h]
0x14021ce00  test    eax, eax
0x14021ce02  jz      loc_14021CFD2
0x14021ce08  mov     rcx, [rbp+200h+var_1F8]
0x14021ce0c  test    rcx, rcx
0x14021ce0f  jz      loc_14021CFD2
0x14021ce15  mov     eax, [rbp+200h+var_278.cx]
0x14021ce18  movdqa  xmm0, cs:__xmm@00000003000000030000000000000000
0x14021ce20  mov     r9, [rbp+200h+var_230]
0x14021ce24  mov     r8, [rbp+200h+var_208]; struct PALETTE *
0x14021ce28  add     r9, 18h; struct _SURFOBJ *
0x14021ce2c  mov     rdx, [rbp+200h+var_270]; struct PALETTE *
0x14021ce30  mov     [rbp+200h+var_260.right], eax
0x14021ce33  mov     eax, [rbp+200h+var_278.cy]
0x14021ce36  mov     [rbp+200h+var_260.bottom], eax
0x14021ce39  lea     rax, [rcx+18h]
0x14021ce3d  lea     rcx, [rbp+200h+var_218]
0x14021ce41  mov     qword ptr [rbp+200h+var_260.left], rdi
0x14021ce45  mov     [rsp+300h+var_2C8], rcx; struct _MARGINS *
0x14021ce4a  lea     rcx, [rbp+200h+var_70]
0x14021ce51  mov     [rsp+300h+var_2D0], rcx; struct _RECTL *
0x14021ce56  lea     rcx, [rbp+200h+var_260]
0x14021ce5a  mov     [rsp+300h+var_2D8], rcx; struct _RECTL *
0x14021ce5f  lea     rcx, [rbp+200h+var_1E0]; struct XDCOBJ *
0x14021ce63  movdqu  xmmword ptr [rbp+200h+var_70.left], xmm0
0x14021ce6b  mov     [rsp+300h+var_2E0], rax; struct _SURFOBJ *
0x14021ce70  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x14021ce78  movups  xmmword ptr [rbp+200h+var_218.x], xmm0
0x14021ce7c  call    ?EngNineGridHelper@@YAHAEAVXDCOBJ@@PEAVPALETTE@@1PEAU_SURFOBJ@@2PEAU_RECTL@@3PEAU_MARGINS@@@Z; EngNineGridHelper(XDCOBJ &,PALETTE *,PALETTE *,_SURFOBJ *,_SURFOBJ *,_RECTL *,_RECTL *,_MARGINS *)
0x14021ce81  mov     r15d, eax
0x14021ce84  test    eax, eax
0x14021ce86  jz      loc_14021CFD2
0x14021ce8c  mov     rax, [rbp+200h+var_230]
0x14021ce90  lea     rdx, [rbp+200h+var_1E0]
0x14021ce94  mov     r9b, 4
0x14021ce97  lea     rcx, [rbp+200h+var_170]
0x14021ce9e  mov     r8, [rax+20h]
0x14021cea2  bts     dword ptr [rax+0A0h], 1Ah
0x14021ceaa  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14021ceb1  nop     dword ptr [rax+rax+00h]
0x14021ceb6  mov     r12d, 0FBFFFFFFh
0x14021cebc  lea     rcx, [rbp+200h+var_E0]; this
0x14021cec3  xor     r15d, r15d
0x14021cec6  xor     edx, edx; HDC
0x14021cec8  mov     rdi, [rax]
0x14021cecb  mov     rax, [rbp+200h+var_230]
0x14021cecf  and     [rax+0A0h], r12d
0x14021ced6  mov     eax, [rbx]
0x14021ced8  mov     [rbp+200h+var_260.left], eax
0x14021cedb  mov     eax, [rbx+4]
0x14021cede  mov     [rbp+200h+var_260.top], eax
0x14021cee1  mov     dword ptr [rbp+200h+var_280.BlendOp], 1FF0000h
0x14021cee8  mov     qword ptr [rbp+200h+var_218.x], r15
0x14021ceec  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x14021cef1  lea     rdx, [rbp+200h+var_1E0]; struct XDCOBJ *
0x14021cef5  lea     rcx, [rbp+200h+var_150]; this
0x14021cefc  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x14021cf01  mov     rbx, [r13+490h]
0x14021cf08  call    cs:__imp_UserGetHDEV
0x14021cf0f  nop     dword ptr [rax+rax+00h]
0x14021cf14  mov     [rsp+300h+var_288], r15d; unsigned int
0x14021cf19  lea     rcx, [rbp+200h+var_280]
0x14021cf1d  mov     [rsp+300h+var_290], r15d; int
0x14021cf22  lea     r9, [rbp+200h+var_E0]; struct OPTAPIDCOBJ *
0x14021cf29  mov     [rsp+300h+var_298], 1; int
0x14021cf31  mov     r8, rbx; void *
0x14021cf34  mov     [rsp+300h+var_2A0], r15; struct tagMINIWINDOWINFO *
0x14021cf39  xor     edx, edx; HWND
0x14021cf3b  mov     [rsp+300h+var_2A8], r15; struct tagRECT *
0x14021cf40  mov     [rsp+300h+var_2B0], 2; unsigned int
0x14021cf48  mov     [rsp+300h+var_2B8], rcx; struct _BLENDFUNCTION *
0x14021cf4d  lea     rcx, [rbp+200h+var_218]
0x14021cf51  mov     [rsp+300h+var_2C0], r15d; unsigned int
0x14021cf56  mov     [rsp+300h+var_2C8], rcx; struct tagPOINT *
0x14021cf5b  lea     rcx, [rbp+200h+var_150]
0x14021cf62  mov     [rsp+300h+var_2D0], rcx; struct OPTAPIDCOBJ *
0x14021cf67  lea     rcx, [rbp+200h+var_278]
0x14021cf6b  mov     [rsp+300h+var_2D8], rcx; struct tagSIZE *
0x14021cf70  lea     rcx, [rbp+200h+var_260]
0x14021cf74  mov     [rsp+300h+var_2E0], rcx; struct tagPOINT *
0x14021cf79  mov     rcx, rax; HDEV
0x14021cf7c  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x14021cf81  mov     r15d, eax
0x14021cf84  lea     rdx, [rbp+200h+var_1E0]
0x14021cf88  mov     rax, [rbp+200h+var_230]
0x14021cf8c  lea     rcx, [rbp+200h+var_160]
0x14021cf93  mov     r9b, 4
0x14021cf96  mov     r8, rdi
0x14021cf99  bts     dword ptr [rax+0A0h], 1Ah
0x14021cfa1  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14021cfa8  nop     dword ptr [rax+rax+00h]
0x14021cfad  mov     rax, [rbp+200h+var_230]
0x14021cfb1  lea     rcx, [rbp+200h+var_150]; this
0x14021cfb8  and     [rax+0A0h], r12d
0x14021cfbf  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14021cfc4  lea     rcx, [rbp+200h+var_E0]; this
0x14021cfcb  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14021cfd0  xor     edi, edi
0x14021cfd2  lea     rcx, [rbp+200h+var_1F8]
0x14021cfd6  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x14021cfdd  nop     dword ptr [rax+rax+00h]
0x14021cfe2  lea     rcx, [rbp+200h+var_270]
0x14021cfe6  call    cs:__imp_?vUnrefPalette@XEPALOBJ@@QEAAXXZ; XEPALOBJ::vUnrefPalette(void)
0x14021cfed  nop     dword ptr [rax+rax+00h]
0x14021cff2  lea     rcx, [rbp+200h+var_230]
0x14021cff6  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x14021cffd  nop     dword ptr [rax+rax+00h]
0x14021d002  lea     rcx, [rbp+200h+var_270]
0x14021d006  call    cs:__imp_??1PALMEMOBJ@@QEAA@XZ; PALMEMOBJ::~PALMEMOBJ(void)
0x14021d00d  nop     dword ptr [rax+rax+00h]
0x14021d012  lea     rcx, [rbp+200h+var_208]
0x14021d016  call    cs:__imp_??1PALMEMOBJ@@QEAA@XZ; PALMEMOBJ::~PALMEMOBJ(void)
0x14021d01d  nop     dword ptr [rax+rax+00h]
0x14021d022  lea     rcx, [rbp+200h+var_1E0]; this
0x14021d026  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14021d02b  xor     r9d, r9d
0x14021d02e  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021d032  mov     r8d, 80000002h
0x14021d038  mov     rdx, rsi
0x14021d03b  mov     rcx, r14
0x14021d03e  call    cs:__imp_?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z; GrepSetDCOwnerEx(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,ulong,int,int)
0x14021d045  nop     dword ptr [rax+rax+00h]
0x14021d04a  mov     rcx, rsi
0x14021d04d  call    cs:__imp_GreDeleteDC
0x14021d054  nop     dword ptr [rax+rax+00h]
0x14021d059  mov     eax, r15d
0x14021d05c  mov     rcx, [rbp+200h+var_38]
0x14021d063  xor     rcx, rsp; StackCookie
0x14021d066  call    __security_check_cookie
0x14021d06b  mov     rbx, [rsp+300h+arg_10]
0x14021d073  add     rsp, 2D0h
0x14021d07a  pop     r15
0x14021d07c  pop     r14
0x14021d07e  pop     r13
0x14021d080  pop     r12
0x14021d082  pop     rdi
0x14021d083  pop     rsi
0x14021d084  pop     rbp
0x14021d085  retn
```
