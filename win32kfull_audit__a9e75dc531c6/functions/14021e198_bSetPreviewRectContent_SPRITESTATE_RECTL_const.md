# bSetPreviewRectContent(_SPRITESTATE *,_RECTL const *)

- ea: `0x14021e198`
- end: `0x14021e697`
- name: `?bSetPreviewRectContent@@YAHPEAU_SPRITESTATE@@PEBU_RECTL@@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(struct _SPRITESTATE *, const struct _RECTL *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14021de8c`

## callees

- `0x140016e74`
- `0x14005b820`
- `0x14005b938`
- `0x1400a4eb4`
- `0x1400a7100`
- `0x1401150d0`
- `0x14021e198`
- `0x1402330e0`
- `0x140298e04`
- `0x140308388`
- `0x140342fa0`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x14021e206`
- `win32kbase!GreCreateCompatibleDC` at `0x14021e206`
- `win32kbase!GreDeleteDC` at `0x14021e65d`
- `win32kbase!GreDeleteDC` at `0x14021e65d`
- `win32kbase!UserGetHDEV` at `0x14021e518`
- `win32kbase!UserGetHDEV` at `0x14021e518`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14021e215`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14021e215`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021e5e6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021e606`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021e5e6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021e606`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021e35e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021e404`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021e35e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021e404`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021e4ba`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021e5b1`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021e4ba`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14021e5b1`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021e616`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021e626`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021e616`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021e626`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021e29f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021e2ec`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021e29f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021e2ec`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021e5f6`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021e5f6`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021e23d`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021e64e`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021e23d`
- `win32kbase!?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z` at `0x14021e64e`
- `WIN32K!W32GetUserSessionState` at `0x14021e1ef`
- `WIN32K!W32GetUserSessionState` at `0x14021e1ef`

## pseudocode

```c
__int64 __fastcall bSetPreviewRectContent(struct _SPRITESTATE *a1, const struct _RECTL *a2, __int64 a3, __int64 a4)
{
  unsigned int updated; // r15d
  __int64 v7; // rdx
  __int64 UserSessionState; // rax
  struct HOBJ__ *CompatibleDC; // rsi
  Gre::Base *v10; // rcx
  struct Gre::Base::SESSION_GLOBALS *v11; // rax
  struct Gre::Base::SESSION_GLOBALS *v12; // r14
  unsigned int v13; // edx
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdi
  void *v17; // rbx
  HDEV HDEV; // rax
  __int64 v19; // r9
  struct _BLENDFUNCTION v21; // [rsp+80h] [rbp-80h] BYREF
  struct tagSIZE v22; // [rsp+88h] [rbp-78h] BYREF
  struct PALETTE *v23; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+98h] [rbp-68h]
  struct _RECTL v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-40h]
  _QWORD v28[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct tagPOINT v29[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct PALETTE *v30; // [rsp+F8h] [rbp-8h] BYREF
  int v31; // [rsp+100h] [rbp+0h]
  _QWORD v32[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v33[14]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v34[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v35[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v36[112]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v37[112]; // [rsp+220h] [rbp+120h] BYREF
  struct _RECTL v38; // [rsp+290h] [rbp+190h] BYREF
  __m128i si128; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v40; // [rsp+2B0h] [rbp+1B0h]
  __m128i v41; // [rsp+2B4h] [rbp+1B4h]

  updated = 0;
  v7 = (unsigned int)(a2->right - a2->left);
  v22.cy = a2->bottom - a2->top;
  v26 = 0;
  v22.cx = v7;
  v27 = 0;
  UserSessionState = W32GetUserSessionState((unsigned int)v22.cy, v7, a3, a4);
  CompatibleDC = (struct HOBJ__ *)GreCreateCompatibleDC(*(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 56LL));
  v11 = Gre::Base::Globals(v10);
  v12 = v11;
  if ( CompatibleDC )
  {
    GrepSetDCOwnerEx(v11, CompatibleDC, 0, 0, 0);
    APIDCOBJ::APIDCOBJ((APIDCOBJ *)v33, (HDC)CompatibleDC, v12);
    if ( v33[0] )
    {
      v31 = 0;
      v30 = 0;
      if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v30, 8u, 0, 0, 0xFF0000u, 0xFF00u, 0xFFu, 0x300u, 1) )
      {
        v24 = 0;
        v23 = 0;
        if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v23, 8u, 0, 0, 0xFF0000u, 0xFF00u, 0xFFu, 0x200u, 1) )
        {
          *(struct tagSIZE *)((char *)&v26 + 4) = v22;
          v24 = 1;
          LODWORD(v26) = 6;
          HIDWORD(v26) = 0;
          *(_QWORD *)&v27 = *(_QWORD *)v23;
          DWORD2(v27) = 1;
          SURFMEM::SURFMEM(v28, 2);
          if ( SURFMEM::bCreateDIB((SURFMEM *)v28, (struct _DEVBITMAPINFO *)&v26, 0, 0, 0, 0, 0, 0, 1, 0) && v28[0] )
          {
            SURFMEM::vSetPID((SURFMEM *)v28, v13);
            *((_QWORD *)&v26 + 1) = 0x2400000003LL;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v40 = 1174412344;
            v41 = si128;
            *(_QWORD *)&v26 = 0x300000006LL;
            *(_QWORD *)&v27 = *(_QWORD *)v23;
            DWORD2(v27) = 1;
            SURFMEM::SURFMEM(v32, 2);
            if ( SURFMEM::bCreateDIB((SURFMEM *)v32, (struct _DEVBITMAPINFO *)&v26, &si128, 0, 0, 0, 0, 0, 1, 0) )
            {
              if ( v32[0] )
              {
                *(struct tagSIZE *)&v25.right = v22;
                *(_QWORD *)&v25.left = 0;
                v38 = (struct _RECTL)_mm_load_si128((const __m128i *)&_xmm);
                *(__m128i *)&v29[0].x = _mm_load_si128((const __m128i *)&_xmm);
                updated = EngNineGridHelper(
                            (struct XDCOBJ *)v33,
                            v23,
                            v30,
                            (struct _SURFOBJ *)(v28[0] + 24LL),
                            (struct _SURFOBJ *)(v32[0] + 24LL),
                            &v25,
                            &v38,
                            (struct _MARGINS *)v29);
                if ( updated )
                {
                  LOBYTE(v14) = 4;
                  v15 = *(_QWORD *)(v28[0] + 32LL);
                  *(_DWORD *)(v28[0] + 144LL) |= 0x4000000u;
                  v16 = *(_QWORD *)GrepSelectBitmap(v34, v33, v15, v14);
                  *(_DWORD *)(v28[0] + 144LL) &= ~0x4000000u;
                  v25.left = a2->left;
                  v25.top = a2->top;
                  v21 = (struct _BLENDFUNCTION)33488896;
                  v29[0] = 0;
                  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v37, 0);
                  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v36, (struct XDCOBJ *)v33);
                  v17 = (void *)*((_QWORD *)a1 + 146);
                  HDEV = (HDEV)UserGetHDEV();
                  updated = GrepUpdateSprite(
                              HDEV,
                              0,
                              v17,
                              (struct OPTAPIDCOBJ *)v37,
                              (struct tagPOINT *)&v25,
                              &v22,
                              (struct OPTAPIDCOBJ *)v36,
                              v29,
                              0,
                              &v21,
                              2u,
                              0,
                              0,
                              1,
                              0,
                              0);
                  LOBYTE(v19) = 4;
                  *(_DWORD *)(v28[0] + 144LL) |= 0x4000000u;
                  GrepSelectBitmap(v35, v33, v16, v19);
                  *(_DWORD *)(v28[0] + 144LL) &= ~0x4000000u;
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v36);
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v37);
                }
              }
            }
            SURFMEM::~SURFMEM((SURFMEM *)v32);
          }
          XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v23);
          SURFMEM::~SURFMEM((SURFMEM *)v28);
        }
        PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v23);
      }
      PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v30);
    }
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v33);
    GrepSetDCOwnerEx(v12, CompatibleDC, 0x80000002, 0, 0);
    GreDeleteDC(CompatibleDC);
  }
  return updated;
}

```

## disassembly

```asm
0x14021e198  mov     [rsp-8+arg_10], rbx
0x14021e19d  push    rbp
0x14021e19e  push    rsi
0x14021e19f  push    rdi
0x14021e1a0  push    r12
0x14021e1a2  push    r13
0x14021e1a4  push    r14
0x14021e1a6  push    r15
0x14021e1a8  lea     rbp, [rsp-1D0h]
0x14021e1b0  sub     rsp, 2D0h
0x14021e1b7  mov     rax, cs:__security_cookie
0x14021e1be  xor     rax, rsp
0x14021e1c1  mov     [rbp+200h+var_38], rax
0x14021e1c8  mov     rbx, rdx
0x14021e1cb  mov     r13, rcx
0x14021e1ce  mov     edx, [rdx+8]
0x14021e1d1  xorps   xmm0, xmm0
0x14021e1d4  xor     edi, edi
0x14021e1d6  mov     r15d, edi
0x14021e1d9  mov     ecx, [rbx+0Ch]
0x14021e1dc  sub     ecx, [rbx+4]
0x14021e1df  sub     edx, [rbx]
0x14021e1e1  mov     [rbp+200h+var_278.cy], ecx
0x14021e1e4  movups  [rbp+200h+var_250], xmm0
0x14021e1e8  mov     [rbp+200h+var_278.cx], edx
0x14021e1eb  movups  [rbp+200h+var_240], xmm0
0x14021e1ef  call    cs:__imp_W32GetUserSessionState
0x14021e1f6  nop     dword ptr [rax+rax+00h]
0x14021e1fb  mov     rcx, [rax+0DDA8h]
0x14021e202  mov     rcx, [rcx+38h]
0x14021e206  call    cs:__imp_GreCreateCompatibleDC
0x14021e20d  nop     dword ptr [rax+rax+00h]
0x14021e212  mov     rsi, rax
0x14021e215  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14021e21c  nop     dword ptr [rax+rax+00h]
0x14021e221  mov     r14, rax
0x14021e224  test    rsi, rsi
0x14021e227  jz      loc_14021E669
0x14021e22d  xor     r9d, r9d
0x14021e230  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021e234  xor     r8d, r8d
0x14021e237  mov     rdx, rsi
0x14021e23a  mov     rcx, rax
0x14021e23d  call    cs:__imp_?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z; GrepSetDCOwnerEx(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,ulong,int,int)
0x14021e244  nop     dword ptr [rax+rax+00h]
0x14021e249  mov     r8, r14; struct Gre::Base::SESSION_GLOBALS *
0x14021e24c  lea     rcx, [rbp+200h+var_1E0]; this
0x14021e250  mov     rdx, rsi; HDC
0x14021e253  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *,Gre::Base::SESSION_GLOBALS &)
0x14021e258  cmp     [rbp+200h+var_1E0], rdi
0x14021e25c  jz      loc_14021E632
0x14021e262  lea     r12d, [rdi+1]
0x14021e266  mov     [rbp+200h+var_200], edi
0x14021e269  mov     [rsp+300h+var_2C0], r12d
0x14021e26e  lea     edx, [rdi+8]
0x14021e271  mov     dword ptr [rsp+300h+var_2C8], 300h
0x14021e279  lea     rcx, [rbp+200h+var_208]
0x14021e27d  mov     dword ptr [rsp+300h+var_2D0], 0FFh
0x14021e285  xor     r9d, r9d
0x14021e288  mov     dword ptr [rsp+300h+var_2D8], 0FF00h
0x14021e290  xor     r8d, r8d
0x14021e293  mov     dword ptr [rsp+300h+var_2E0], 0FF0000h
0x14021e29b  mov     [rbp+200h+var_208], rdi
0x14021e29f  call    cs:__imp_?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z; PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)
0x14021e2a6  nop     dword ptr [rax+rax+00h]
0x14021e2ab  test    eax, eax
0x14021e2ad  jz      loc_14021E622
0x14021e2b3  mov     [rsp+300h+var_2C0], r12d
0x14021e2b8  lea     edx, [rdi+8]
0x14021e2bb  mov     dword ptr [rsp+300h+var_2C8], 200h
0x14021e2c3  lea     rcx, [rbp+200h+var_270]
0x14021e2c7  mov     dword ptr [rsp+300h+var_2D0], 0FFh
0x14021e2cf  xor     r9d, r9d
0x14021e2d2  mov     dword ptr [rsp+300h+var_2D8], 0FF00h
0x14021e2da  xor     r8d, r8d
0x14021e2dd  mov     dword ptr [rsp+300h+var_2E0], 0FF0000h
0x14021e2e5  mov     [rbp+200h+var_268], edi
0x14021e2e8  mov     [rbp+200h+var_270], rdi
0x14021e2ec  call    cs:__imp_?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z; PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)
0x14021e2f3  nop     dword ptr [rax+rax+00h]
0x14021e2f8  test    eax, eax
0x14021e2fa  jz      loc_14021E612
0x14021e300  mov     eax, [rbp+200h+var_278.cx]
0x14021e303  lea     edx, [rdi+2]
0x14021e306  mov     dword ptr [rbp+200h+var_250+4], eax
0x14021e309  mov     eax, [rbp+200h+var_278.cy]
0x14021e30c  mov     dword ptr [rbp+200h+var_250+8], eax
0x14021e30f  mov     rax, [rbp+200h+var_270]
0x14021e313  mov     [rbp+200h+var_268], r12d
0x14021e317  mov     dword ptr [rbp+200h+var_250], 6
0x14021e31e  mov     dword ptr [rbp+200h+var_250+0Ch], edi
0x14021e321  mov     rcx, [rax]
0x14021e324  mov     qword ptr [rbp+200h+var_240], rcx
0x14021e328  lea     rcx, [rbp+200h+var_230]
0x14021e32c  mov     dword ptr [rbp+200h+var_240+8], r12d
0x14021e330  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x14021e335  mov     dword ptr [rsp+300h+var_2B8], edi
0x14021e339  lea     rdx, [rbp+200h+var_250]
0x14021e33d  mov     [rsp+300h+var_2C0], r12d
0x14021e342  lea     rcx, [rbp+200h+var_230]
0x14021e346  mov     dword ptr [rsp+300h+var_2C8], edi
0x14021e34a  xor     r9d, r9d
0x14021e34d  mov     [rsp+300h+var_2D0], rdi
0x14021e352  xor     r8d, r8d
0x14021e355  mov     [rsp+300h+var_2D8], rdi
0x14021e35a  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021e35e  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x14021e365  nop     dword ptr [rax+rax+00h]
0x14021e36a  test    eax, eax
0x14021e36c  jz      loc_14021E5F2
0x14021e372  cmp     [rbp+200h+var_230], rdi
0x14021e376  jz      loc_14021E5F2
0x14021e37c  lea     rcx, [rbp+200h+var_230]; this
0x14021e380  call    ?vSetPID@SURFMEM@@QEAAXK@Z; SURFMEM::vSetPID(ulong)
0x14021e385  movdqa  xmm0, cs:__xmm@8c0038708c0038708c0038708c003870
0x14021e38d  lea     eax, [rdi+3]
0x14021e390  mov     dword ptr [rbp+200h+var_250+4], eax
0x14021e393  lea     edx, [rdi+2]
0x14021e396  mov     dword ptr [rbp+200h+var_250+8], eax
0x14021e399  mov     rax, [rbp+200h+var_270]
0x14021e39d  movups  [rbp+200h+var_60], xmm0
0x14021e3a4  mov     [rbp+200h+var_50], 46001C38h
0x14021e3ae  movups  [rbp+200h+var_4C], xmm0
0x14021e3b5  mov     dword ptr [rbp+200h+var_250], 6
0x14021e3bc  mov     dword ptr [rbp+200h+var_250+0Ch], 24h ; '$'
0x14021e3c3  mov     rcx, [rax]
0x14021e3c6  mov     qword ptr [rbp+200h+var_240], rcx
0x14021e3ca  lea     rcx, [rbp+200h+var_1F8]
0x14021e3ce  mov     dword ptr [rbp+200h+var_240+8], r12d
0x14021e3d2  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x14021e3d7  mov     dword ptr [rsp+300h+var_2B8], edi
0x14021e3db  lea     r8, [rbp+200h+var_60]
0x14021e3e2  mov     [rsp+300h+var_2C0], r12d
0x14021e3e7  lea     rdx, [rbp+200h+var_250]
0x14021e3eb  mov     dword ptr [rsp+300h+var_2C8], edi
0x14021e3ef  lea     rcx, [rbp+200h+var_1F8]
0x14021e3f3  mov     [rsp+300h+var_2D0], rdi
0x14021e3f8  xor     r9d, r9d
0x14021e3fb  mov     [rsp+300h+var_2D8], rdi
0x14021e400  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021e404  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x14021e40b  nop     dword ptr [rax+rax+00h]
0x14021e410  test    eax, eax
0x14021e412  jz      loc_14021E5E2
0x14021e418  mov     rcx, [rbp+200h+var_1F8]
0x14021e41c  test    rcx, rcx
0x14021e41f  jz      loc_14021E5E2
0x14021e425  mov     eax, [rbp+200h+var_278.cx]
0x14021e428  movdqa  xmm0, cs:__xmm@00000003000000030000000000000000
0x14021e430  mov     r9, [rbp+200h+var_230]
0x14021e434  mov     r8, [rbp+200h+var_208]; struct PALETTE *
0x14021e438  add     r9, 18h; struct _SURFOBJ *
0x14021e43c  mov     rdx, [rbp+200h+var_270]; struct PALETTE *
0x14021e440  mov     [rbp+200h+var_260.right], eax
0x14021e443  mov     eax, [rbp+200h+var_278.cy]
0x14021e446  mov     [rbp+200h+var_260.bottom], eax
0x14021e449  lea     rax, [rcx+18h]
0x14021e44d  lea     rcx, [rbp+200h+var_218]
0x14021e451  mov     qword ptr [rbp+200h+var_260.left], rdi
0x14021e455  mov     [rsp+300h+var_2C8], rcx; struct _MARGINS *
0x14021e45a  lea     rcx, [rbp+200h+var_70]
0x14021e461  mov     [rsp+300h+var_2D0], rcx; struct _RECTL *
0x14021e466  lea     rcx, [rbp+200h+var_260]
0x14021e46a  mov     [rsp+300h+var_2D8], rcx; struct _RECTL *
0x14021e46f  lea     rcx, [rbp+200h+var_1E0]; struct XDCOBJ *
0x14021e473  movdqu  xmmword ptr [rbp+200h+var_70.left], xmm0
0x14021e47b  mov     [rsp+300h+var_2E0], rax; struct _SURFOBJ *
0x14021e480  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x14021e488  movups  xmmword ptr [rbp+200h+var_218.x], xmm0
0x14021e48c  call    ?EngNineGridHelper@@YAHAEAVXDCOBJ@@PEAVPALETTE@@1PEAU_SURFOBJ@@2PEAU_RECTL@@3PEAU_MARGINS@@@Z; EngNineGridHelper(XDCOBJ &,PALETTE *,PALETTE *,_SURFOBJ *,_SURFOBJ *,_RECTL *,_RECTL *,_MARGINS *)
0x14021e491  mov     r15d, eax
0x14021e494  test    eax, eax
0x14021e496  jz      loc_14021E5E2
0x14021e49c  mov     rax, [rbp+200h+var_230]
0x14021e4a0  lea     rdx, [rbp+200h+var_1E0]
0x14021e4a4  mov     r9b, 4
0x14021e4a7  lea     rcx, [rbp+200h+var_170]
0x14021e4ae  mov     r8, [rax+20h]
0x14021e4b2  bts     dword ptr [rax+90h], 1Ah
0x14021e4ba  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14021e4c1  nop     dword ptr [rax+rax+00h]
0x14021e4c6  mov     r12d, 0FBFFFFFFh
0x14021e4cc  lea     rcx, [rbp+200h+var_E0]; this
0x14021e4d3  xor     r15d, r15d
0x14021e4d6  xor     edx, edx; HDC
0x14021e4d8  mov     rdi, [rax]
0x14021e4db  mov     rax, [rbp+200h+var_230]
0x14021e4df  and     [rax+90h], r12d
0x14021e4e6  mov     eax, [rbx]
0x14021e4e8  mov     [rbp+200h+var_260.left], eax
0x14021e4eb  mov     eax, [rbx+4]
0x14021e4ee  mov     [rbp+200h+var_260.top], eax
0x14021e4f1  mov     dword ptr [rbp+200h+var_280.BlendOp], 1FF0000h
0x14021e4f8  mov     qword ptr [rbp+200h+var_218.x], r15
0x14021e4fc  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x14021e501  lea     rdx, [rbp+200h+var_1E0]; struct XDCOBJ *
0x14021e505  lea     rcx, [rbp+200h+var_150]; this
0x14021e50c  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x14021e511  mov     rbx, [r13+490h]
0x14021e518  call    cs:__imp_UserGetHDEV
0x14021e51f  nop     dword ptr [rax+rax+00h]
0x14021e524  mov     [rsp+300h+var_288], r15d; unsigned int
0x14021e529  lea     rcx, [rbp+200h+var_280]
0x14021e52d  mov     [rsp+300h+var_290], r15d; int
0x14021e532  lea     r9, [rbp+200h+var_E0]; struct OPTAPIDCOBJ *
0x14021e539  mov     [rsp+300h+var_298], 1; int
0x14021e541  mov     r8, rbx; void *
0x14021e544  mov     [rsp+300h+var_2A0], r15; struct tagMINIWINDOWINFO *
0x14021e549  xor     edx, edx; HWND
0x14021e54b  mov     [rsp+300h+var_2A8], r15; struct tagRECT *
0x14021e550  mov     [rsp+300h+var_2B0], 2; unsigned int
0x14021e558  mov     [rsp+300h+var_2B8], rcx; struct _BLENDFUNCTION *
0x14021e55d  lea     rcx, [rbp+200h+var_218]
0x14021e561  mov     [rsp+300h+var_2C0], r15d; unsigned int
0x14021e566  mov     [rsp+300h+var_2C8], rcx; struct tagPOINT *
0x14021e56b  lea     rcx, [rbp+200h+var_150]
0x14021e572  mov     [rsp+300h+var_2D0], rcx; struct OPTAPIDCOBJ *
0x14021e577  lea     rcx, [rbp+200h+var_278]
0x14021e57b  mov     [rsp+300h+var_2D8], rcx; struct tagSIZE *
0x14021e580  lea     rcx, [rbp+200h+var_260]
0x14021e584  mov     [rsp+300h+var_2E0], rcx; struct tagPOINT *
0x14021e589  mov     rcx, rax; HDEV
0x14021e58c  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x14021e591  mov     r15d, eax
0x14021e594  lea     rdx, [rbp+200h+var_1E0]
0x14021e598  mov     rax, [rbp+200h+var_230]
0x14021e59c  lea     rcx, [rbp+200h+var_160]
0x14021e5a3  mov     r9b, 4
0x14021e5a6  mov     r8, rdi
0x14021e5a9  bts     dword ptr [rax+90h], 1Ah
0x14021e5b1  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14021e5b8  nop     dword ptr [rax+rax+00h]
0x14021e5bd  mov     rax, [rbp+200h+var_230]
0x14021e5c1  lea     rcx, [rbp+200h+var_150]; this
0x14021e5c8  and     [rax+90h], r12d
0x14021e5cf  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14021e5d4  lea     rcx, [rbp+200h+var_E0]; this
0x14021e5db  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14021e5e0  xor     edi, edi
0x14021e5e2  lea     rcx, [rbp+200h+var_1F8]
0x14021e5e6  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x14021e5ed  nop     dword ptr [rax+rax+00h]
0x14021e5f2  lea     rcx, [rbp+200h+var_270]
0x14021e5f6  call    cs:__imp_?vUnrefPalette@XEPALOBJ@@QEAAXXZ; XEPALOBJ::vUnrefPalette(void)
0x14021e5fd  nop     dword ptr [rax+rax+00h]
0x14021e602  lea     rcx, [rbp+200h+var_230]
0x14021e606  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x14021e60d  nop     dword ptr [rax+rax+00h]
0x14021e612  lea     rcx, [rbp+200h+var_270]
0x14021e616  call    cs:__imp_??1PALMEMOBJ@@QEAA@XZ; PALMEMOBJ::~PALMEMOBJ(void)
0x14021e61d  nop     dword ptr [rax+rax+00h]
0x14021e622  lea     rcx, [rbp+200h+var_208]
0x14021e626  call    cs:__imp_??1PALMEMOBJ@@QEAA@XZ; PALMEMOBJ::~PALMEMOBJ(void)
0x14021e62d  nop     dword ptr [rax+rax+00h]
0x14021e632  lea     rcx, [rbp+200h+var_1E0]; this
0x14021e636  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14021e63b  xor     r9d, r9d
0x14021e63e  mov     dword ptr [rsp+300h+var_2E0], edi
0x14021e642  mov     r8d, 80000002h
0x14021e648  mov     rdx, rsi
0x14021e64b  mov     rcx, r14
0x14021e64e  call    cs:__imp_?GrepSetDCOwnerEx@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@KHH@Z; GrepSetDCOwnerEx(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,ulong,int,int)
0x14021e655  nop     dword ptr [rax+rax+00h]
0x14021e65a  mov     rcx, rsi
0x14021e65d  call    cs:__imp_GreDeleteDC
0x14021e664  nop     dword ptr [rax+rax+00h]
0x14021e669  mov     eax, r15d
0x14021e66c  mov     rcx, [rbp+200h+var_38]
0x14021e673  xor     rcx, rsp; StackCookie
0x14021e676  call    __security_check_cookie
0x14021e67b  mov     rbx, [rsp+300h+arg_10]
0x14021e683  add     rsp, 2D0h
0x14021e68a  pop     r15
0x14021e68c  pop     r14
0x14021e68e  pop     r13
0x14021e690  pop     r12
0x14021e692  pop     rdi
0x14021e693  pop     rsi
0x14021e694  pop     rbp
0x14021e695  retn
```
