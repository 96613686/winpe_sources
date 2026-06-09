# EngStretchBlt

- ea: `0x140077380`
- end: `0x140077919`
- name: `EngStretchBlt`
- size: `1433`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, SURFOBJ *psoMask, CLIPOBJ *pco, XLATEOBJ *pxlo, COLORADJUSTMENT *pca, POINTL *pptlHTOrg, RECTL *prclDest, RECTL *prclSrc, POINTL *pptlMask, ULONG iMode)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x140075ce4`
- `0x140147b60`
- `0x14014f330`
- `0x140150680`
- `0x1401611e0`
- `0x1402a6630`
- `0x140312200`
- `0x1403157a0`
- `0x140321620`

## callees

- `0x1400746e0`
- `0x140077380`
- `0x140077920`
- `0x14026723c`
- `0x140342fa0`
- `0x140343080`
- `0x140343500`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140077595`
- `ntoskrnl!DbgPrint` at `0x1400777ad`
- `ntoskrnl!DbgPrint` at `0x14007780c`
- `ntoskrnl!DbgPrint` at `0x140077595`
- `ntoskrnl!DbgPrint` at `0x1400777ad`
- `ntoskrnl!DbgPrint` at `0x14007780c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140077602`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140077602`
- `win32kbase!EngLockSurface` at `0x1400775a4`
- `win32kbase!EngLockSurface` at `0x1400775b6`
- `win32kbase!EngLockSurface` at `0x1400775c8`
- `win32kbase!EngLockSurface` at `0x1400775a4`
- `win32kbase!EngLockSurface` at `0x1400775b6`
- `win32kbase!EngLockSurface` at `0x1400775c8`
- `win32kbase!EngUnlockSurface` at `0x140077885`
- `win32kbase!EngUnlockSurface` at `0x140077899`
- `win32kbase!EngUnlockSurface` at `0x1400778ad`
- `win32kbase!EngUnlockSurface` at `0x140077885`
- `win32kbase!EngUnlockSurface` at `0x140077899`
- `win32kbase!EngUnlockSurface` at `0x1400778ad`
- `win32kbase!EngCreateBitmap` at `0x14007751e`
- `win32kbase!EngCreateBitmap` at `0x140077547`
- `win32kbase!EngCreateBitmap` at `0x14007756c`
- `win32kbase!EngCreateBitmap` at `0x14007751e`
- `win32kbase!EngCreateBitmap` at `0x140077547`
- `win32kbase!EngCreateBitmap` at `0x14007756c`
- `win32kbase!EngDeleteSurface` at `0x1400778c2`
- `win32kbase!EngDeleteSurface` at `0x1400778d6`
- `win32kbase!EngDeleteSurface` at `0x1400778ea`
- `win32kbase!EngDeleteSurface` at `0x1400778c2`
- `win32kbase!EngDeleteSurface` at `0x1400778d6`
- `win32kbase!EngDeleteSurface` at `0x1400778ea`
- `WIN32K!W32GetSessionState` at `0x140077403`
- `WIN32K!W32GetSessionState` at `0x140077403`

## pseudocode

```c
BOOL __stdcall EngStretchBlt(
        SURFOBJ *psoDest,
        SURFOBJ *psoSrc,
        SURFOBJ *psoMask,
        CLIPOBJ *pco,
        XLATEOBJ *pxlo,
        COLORADJUSTMENT *pca,
        POINTL *pptlHTOrg,
        RECTL *prclDest,
        RECTL *prclSrc,
        POINTL *pptlMask,
        ULONG iMode)
{
  CLIPOBJ *v11; // r12
  XLATEOBJ *v12; // r13
  SURFOBJ *v13; // r15
  RECTL *v14; // rbx
  SURFOBJ *v15; // r14
  RECTL *v16; // rsi
  __int64 v18; // rax
  RECTL v20; // xmm0
  RECTL v21; // xmm1
  SIZEL sizlBitmap; // rcx
  ULONG iBitmapFormat; // r8d
  HDEV hdev; // rbx
  LONG cy; // eax
  HSURF Bitmap; // rax
  SIZEL v27; // rcx
  ULONG v28; // r8d
  HSURF v29; // rsi
  HBITMAP v30; // r13
  HBITMAP v31; // rax
  HSURF v32; // r12
  SURFOBJ *v33; // rsi
  SURFOBJ *v34; // r14
  SURFOBJ *v35; // rax
  Gre::Base *v36; // rcx
  SURFOBJ *v37; // r15
  int v38; // r12d
  _BYTE *pvBits; // rdx
  __int64 v40; // r12
  _BYTE *v41; // rax
  int v42; // eax
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  POINTL pptlSrc; // [rsp+68h] [rbp-98h] BYREF
  struct _RECTL *v46; // [rsp+70h] [rbp-90h]
  struct _RECTL *v47; // [rsp+78h] [rbp-88h]
  struct _SURFOBJ *v48; // [rsp+80h] [rbp-80h]
  struct _SURFOBJ *v49; // [rsp+88h] [rbp-78h]
  struct _CLIPOBJ *v50; // [rsp+90h] [rbp-70h]
  struct _XLATEOBJ *v51; // [rsp+98h] [rbp-68h]
  struct _POINTL *v52; // [rsp+A0h] [rbp-60h]
  struct _POINTL *v53; // [rsp+A8h] [rbp-58h]
  struct tagCOLORADJUSTMENT *v54; // [rsp+B0h] [rbp-50h]
  XLATEOBJ *v55; // [rsp+B8h] [rbp-48h]
  HSURF v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  _BYTE *v58; // [rsp+D0h] [rbp-30h]
  _BYTE *v59; // [rsp+D8h] [rbp-28h]
  HSURF hsurf; // [rsp+E0h] [rbp-20h]
  RECTL v61; // [rsp+E8h] [rbp-18h] BYREF
  struct _RECTL v62; // [rsp+F8h] [rbp-8h] BYREF
  struct _RECTL v63; // [rsp+108h] [rbp+8h] BYREF

  v11 = pco;
  v12 = pxlo;
  v13 = psoMask;
  v14 = prclDest;
  v15 = psoSrc;
  v16 = prclSrc;
  v54 = pca;
  v53 = pptlHTOrg;
  v52 = pptlMask;
  v50 = pco;
  v49 = psoMask;
  v48 = psoSrc;
  v51 = pxlo;
  v46 = prclDest;
  v47 = prclSrc;
  v18 = *(_QWORD *)(W32GetSessionState(psoDest, psoSrc, psoMask, pco) + 96);
  v57 = v18;
  if ( *(_DWORD *)(v18 + 4744) )
  {
    v20 = *prclDest;
    v21 = *prclSrc;
    sizlBitmap = psoDest->sizlBitmap;
    iBitmapFormat = psoDest->iBitmapFormat;
    hdev = psoDest->hdev;
    v61.right = psoDest->sizlBitmap.cx;
    cy = psoDest->sizlBitmap.cy;
    v63 = v20;
    *(_QWORD *)&v61.left = 0;
    v62 = v21;
    v61.bottom = cy;
    Bitmap = (HSURF)EngCreateBitmap(sizlBitmap, 0, iBitmapFormat, 0, 0);
    v27 = psoDest->sizlBitmap;
    v28 = psoDest->iBitmapFormat;
    v29 = Bitmap;
    hsurf = Bitmap;
    v30 = EngCreateBitmap(v27, 0, v28, 0, 0);
    v31 = EngCreateBitmap(psoDest->sizlBitmap, 0, psoDest->iBitmapFormat, 0, 0);
    v56 = (HSURF)v31;
    v32 = (HSURF)v31;
    if ( !v29 || !v30 || !v31 )
      DbgPrint("hsurf1 == 0 || hsurf2 == 0 || hsurf3 == 0\n");
    v33 = EngLockSurface(v29);
    v34 = EngLockSurface((HSURF)v30);
    v35 = EngLockSurface(v32);
    v37 = v35;
    if ( v33 )
    {
      if ( v34 && v35 )
      {
        v43 = 0;
        v44 = 0;
        pptlSrc = 0;
        v55 = (XLATEOBJ *)((char *)Gre::Base::Globals(v36) + 4664);
        EngCopyBits(v37, psoDest, 0, v55, &v61, &pptlSrc);
LABEL_13:
        memset_0(v33->pvBits, 0, v33->cjBits);
        memset_0(v34->pvBits, 0, v33->cjBits);
        v44 = 0;
        v38 = EngStretchBltOld(psoDest, v48, v49, v50, v51, v54, v53, v46, v47, v52, iMode, &v44);
        if ( v44 )
        {
          EngCopyBits(v33, psoDest, 0, 0, &v61, &pptlSrc);
          if ( (psoDest[1].cjBits & 0x400) != 0 )
            (*((void (__fastcall **)(SURFOBJ *, SURFOBJ *, _QWORD, XLATEOBJ *, RECTL *, POINTL *))hdev + 354))(
              psoDest,
              v37,
              0,
              v55,
              &v61,
              &pptlSrc);
          else
            ((void (__fastcall *)(SURFOBJ *, SURFOBJ *, _QWORD, XLATEOBJ *, RECTL *, POINTL *))EngCopyBits)(
              psoDest,
              v37,
              0,
              v55,
              &v61,
              &pptlSrc);
          v46 = &v63;
          v47 = &v62;
          if ( (unsigned int)EngStretchBltNew(psoDest, v48, v49, v50, v51, v54, v53, &v63, &v62, v52, iMode) != v38 )
            DbgPrint("bOld ^ bNew\n");
          EngCopyBits(v34, psoDest, 0, v55, &v61, &pptlSrc);
          pvBits = v33->pvBits;
          v40 = 0;
          v41 = v34->pvBits;
          v58 = pvBits;
          v59 = v41;
          while ( (unsigned int)v40 < v33->cjBits )
          {
            if ( pvBits[v40] != v41[v40] )
            {
              DbgPrint("memcmp failed\n");
              v42 = v43 + 1;
              v43 = v42;
              if ( v42 == 1 )
              {
                __debugbreak();
                if ( (psoDest[1].cjBits & 0x400) != 0 )
                  (*((void (__fastcall **)(SURFOBJ *, SURFOBJ *, _QWORD, XLATEOBJ *, RECTL *, POINTL *))hdev + 354))(
                    psoDest,
                    v37,
                    0,
                    v55,
                    &v61,
                    &pptlSrc);
                else
                  ((void (__fastcall *)(SURFOBJ *, SURFOBJ *, _QWORD, XLATEOBJ *, RECTL *, POINTL *))EngCopyBits)(
                    psoDest,
                    v37,
                    0,
                    v55,
                    &v61,
                    &pptlSrc);
                goto LABEL_13;
              }
              if ( v42 == 2 )
              {
                __debugbreak();
                break;
              }
              pvBits = v58;
            }
            v41 = v59;
            v40 = (unsigned int)(v40 + 1);
          }
        }
        v32 = v56;
      }
      EngUnlockSurface(v33);
    }
    if ( v34 )
      EngUnlockSurface(v34);
    if ( v37 )
      EngUnlockSurface(v37);
    if ( hsurf )
      EngDeleteSurface(hsurf);
    if ( v30 )
      EngDeleteSurface((HSURF)v30);
    if ( v32 )
      EngDeleteSurface(v32);
    v18 = v57;
    v12 = v51;
    v11 = v50;
    v13 = v49;
    v15 = v48;
    v16 = v47;
    v14 = v46;
  }
  if ( *(_DWORD *)(v18 + 4740) )
    return EngStretchBltNew(psoDest, v15, v13, v11, v12, v54, v53, v14, v16, v52, iMode);
  v43 = 0;
  return EngStretchBltOld(psoDest, v15, v13, v11, v12, v54, v53, v14, v16, v52, iMode, &v43);
}

```

## disassembly

```asm
0x140077380  push    rbp
0x140077382  push    rbx
0x140077383  push    rsi
0x140077384  push    rdi
0x140077385  push    r12
0x140077387  push    r13
0x140077389  push    r14
0x14007738b  push    r15
0x14007738d  lea     rbp, [rsp-28h]
0x140077392  sub     rsp, 128h
0x140077399  mov     rax, cs:__security_cookie
0x1400773a0  xor     rax, rsp
0x1400773a3  mov     [rbp+60h+var_48], rax
0x1400773a7  mov     rax, [rbp+60h+pca]
0x1400773ae  mov     r12, r9
0x1400773b1  mov     r13, [rbp+60h+pxlo]
0x1400773b8  mov     r15, r8
0x1400773bb  mov     rbx, [rbp+60h+prclDest]
0x1400773c2  mov     r14, rdx
0x1400773c5  mov     rsi, [rbp+60h+prclSrc]
0x1400773cc  mov     rdi, rcx
0x1400773cf  mov     [rbp+60h+var_B0], rax
0x1400773d3  mov     rax, [rbp+60h+pptlHTOrg]
0x1400773da  mov     [rbp+60h+var_B8], rax
0x1400773de  mov     rax, [rbp+60h+pptlMask]
0x1400773e5  mov     [rbp+60h+var_C0], rax
0x1400773e9  mov     [rbp+60h+var_D0], r9
0x1400773ed  mov     [rbp+60h+var_D8], r8
0x1400773f1  mov     [rbp+60h+var_E0], rdx
0x1400773f5  mov     [rbp+60h+var_C8], r13
0x1400773f9  mov     [rsp+160h+var_F0], rbx
0x1400773fe  mov     [rsp+160h+var_E8], rsi
0x140077403  call    cs:__imp_W32GetSessionState
0x14007740a  nop     dword ptr [rax+rax+00h]
0x14007740f  mov     rax, [rax+60h]
0x140077413  mov     [rbp+60h+var_98], rax
0x140077417  cmp     dword ptr [rax+1288h], 0
0x14007741e  jnz     loc_1400774E0
0x140077424  cmp     dword ptr [rax+1284h], 0
0x14007742b  mov     r9, r12; struct _CLIPOBJ *
0x14007742e  mov     r8, r15; struct _SURFOBJ *
0x140077431  mov     rdx, r14; struct _SURFOBJ *
0x140077434  mov     rcx, rdi; struct _SURFOBJ *
0x140077437  jz      short loc_140077493
0x140077439  mov     eax, [rbp+60h+iMode]
0x14007743f  mov     [rsp+160h+var_110], eax; unsigned int
0x140077443  mov     rax, [rbp+60h+var_C0]
0x140077447  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x14007744c  mov     rax, [rbp+60h+var_B8]
0x140077450  mov     [rsp+160h+var_120], rsi; struct _RECTL *
0x140077455  mov     [rsp+160h+var_128], rbx; struct _RECTL *
0x14007745a  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x14007745f  mov     rax, [rbp+60h+var_B0]
0x140077463  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x140077468  mov     [rsp+160h+pvBits], r13; struct _XLATEOBJ *
0x14007746d  call    ?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z; EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)
0x140077472  mov     rcx, [rbp+60h+var_48]
0x140077476  xor     rcx, rsp; StackCookie
0x140077479  call    __security_check_cookie
0x14007747e  add     rsp, 128h
0x140077485  pop     r15
0x140077487  pop     r14
0x140077489  pop     r13
0x14007748b  pop     r12
0x14007748d  pop     rdi
0x14007748e  pop     rsi
0x14007748f  pop     rbx
0x140077490  pop     rbp
0x140077491  retn
0x140077493  lea     rax, [rsp+160h+var_100]
0x140077498  mov     [rsp+160h+var_100], 0
0x1400774a0  mov     [rsp+160h+var_108], rax; int *
0x1400774a5  mov     eax, [rbp+60h+iMode]
0x1400774ab  mov     [rsp+160h+var_110], eax; unsigned int
0x1400774af  mov     rax, [rbp+60h+var_C0]
0x1400774b3  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x1400774b8  mov     rax, [rbp+60h+var_B8]
0x1400774bc  mov     [rsp+160h+var_120], rsi; struct _RECTL *
0x1400774c1  mov     [rsp+160h+var_128], rbx; struct _RECTL *
0x1400774c6  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400774cb  mov     rax, [rbp+60h+var_B0]
0x1400774cf  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400774d4  mov     [rsp+160h+pvBits], r13; struct _XLATEOBJ *
0x1400774d9  call    ?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z; EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)
0x1400774de  jmp     short loc_140077472
0x1400774e0  movups  xmm0, xmmword ptr [rbx]
0x1400774e3  mov     eax, [rdi+20h]
0x1400774e6  xor     r9d, r9d; fl
0x1400774e9  movups  xmm1, xmmword ptr [rsi]
0x1400774ec  mov     rcx, [rdi+20h]; sizl
0x1400774f0  xor     edx, edx; lWidth
0x1400774f2  mov     r8d, [rdi+48h]; iFormat
0x1400774f6  mov     rbx, [rdi+18h]
0x1400774fa  mov     [rbp+60h+var_78.right], eax
0x1400774fd  mov     eax, [rdi+24h]
0x140077500  movdqu  xmmword ptr [rbp+60h+var_58.left], xmm0
0x140077505  mov     qword ptr [rbp+60h+var_78.left], 0
0x14007750d  movdqu  xmmword ptr [rbp+60h+var_68.left], xmm1
0x140077512  mov     [rbp+60h+var_78.bottom], eax
0x140077515  mov     [rsp+160h+pvBits], 0; pvBits
0x14007751e  call    cs:__imp_EngCreateBitmap
0x140077525  nop     dword ptr [rax+rax+00h]
0x14007752a  mov     rcx, [rdi+20h]; sizl
0x14007752e  xor     r9d, r9d; fl
0x140077531  mov     r8d, [rdi+48h]; iFormat
0x140077535  xor     edx, edx; lWidth
0x140077537  mov     rsi, rax
0x14007753a  mov     [rbp+60h+hsurf], rax
0x14007753e  mov     [rsp+160h+pvBits], 0; pvBits
0x140077547  call    cs:__imp_EngCreateBitmap
0x14007754e  nop     dword ptr [rax+rax+00h]
0x140077553  mov     rcx, [rdi+20h]; sizl
0x140077557  xor     r9d, r9d; fl
0x14007755a  mov     r8d, [rdi+48h]; iFormat
0x14007755e  xor     edx, edx; lWidth
0x140077560  mov     r13, rax
0x140077563  mov     [rsp+160h+pvBits], 0; pvBits
0x14007756c  call    cs:__imp_EngCreateBitmap
0x140077573  nop     dword ptr [rax+rax+00h]
0x140077578  mov     [rbp+60h+var_A0], rax
0x14007757c  mov     r12, rax
0x14007757f  test    rsi, rsi
0x140077582  jz      short loc_14007758E
0x140077584  test    r13, r13
0x140077587  jz      short loc_14007758E
0x140077589  test    rax, rax
0x14007758c  jnz     short loc_1400775A1
0x14007758e  lea     rcx, aHsurf10Hsurf20; "hsurf1 == 0 || hsurf2 == 0 || hsurf3 =="...
0x140077595  call    cs:__imp_DbgPrint
0x14007759c  nop     dword ptr [rax+rax+00h]
0x1400775a1  mov     rcx, rsi; hsurf
0x1400775a4  call    cs:__imp_EngLockSurface
0x1400775ab  nop     dword ptr [rax+rax+00h]
0x1400775b0  mov     rcx, r13; hsurf
0x1400775b3  mov     rsi, rax
0x1400775b6  call    cs:__imp_EngLockSurface
0x1400775bd  nop     dword ptr [rax+rax+00h]
0x1400775c2  mov     rcx, r12; hsurf
0x1400775c5  mov     r14, rax
0x1400775c8  call    cs:__imp_EngLockSurface
0x1400775cf  nop     dword ptr [rax+rax+00h]
0x1400775d4  mov     r15, rax
0x1400775d7  test    rsi, rsi
0x1400775da  jz      loc_140077891
0x1400775e0  test    r14, r14
0x1400775e3  jz      loc_140077882
0x1400775e9  test    rax, rax
0x1400775ec  jz      loc_140077882
0x1400775f2  mov     [rsp+160h+var_100], 0
0x1400775fa  mov     [rsp+160h+var_FC], 0
0x140077602  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140077609  nop     dword ptr [rax+rax+00h]
0x14007760e  lea     rcx, [rsp+160h+var_F8]
0x140077613  mov     qword ptr [rsp+160h+var_F8.x], 0
0x14007761c  mov     [rsp+160h+pptlSrc], rcx; pptlSrc
0x140077621  add     rax, 1238h
0x140077627  lea     rcx, [rbp+60h+var_78]
0x14007762b  mov     [rbp+60h+var_A8], rax
0x14007762f  mov     [rsp+160h+pvBits], rcx; prclDest
0x140077634  mov     r9, rax; pxlo
0x140077637  mov     rcx, r15; psoDest
0x14007763a  xor     r8d, r8d; pco
0x14007763d  mov     rdx, rdi; psoSrc
0x140077640  call    EngCopyBits
0x140077645  mov     r8d, [rsi+28h]; Size
0x140077649  xor     edx, edx; Val
0x14007764b  mov     rcx, [rsi+30h]; void *
0x14007764f  call    memset_0
0x140077654  mov     r8d, [rsi+28h]; Size
0x140077658  xor     edx, edx; Val
0x14007765a  mov     rcx, [r14+30h]; void *
0x14007765e  call    memset_0
0x140077663  mov     r9, [rbp+60h+var_D0]; struct _CLIPOBJ *
0x140077667  lea     rax, [rsp+160h+var_FC]
0x14007766c  mov     r8, [rbp+60h+var_D8]; struct _SURFOBJ *
0x140077670  mov     rcx, rdi; struct _SURFOBJ *
0x140077673  mov     rdx, [rbp+60h+var_E0]; struct _SURFOBJ *
0x140077677  mov     [rsp+160h+var_108], rax; int *
0x14007767c  mov     eax, [rbp+60h+iMode]
0x140077682  mov     [rsp+160h+var_110], eax; unsigned int
0x140077686  mov     rax, [rbp+60h+var_C0]
0x14007768a  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x14007768f  mov     rax, [rsp+160h+var_E8]
0x140077694  mov     [rsp+160h+var_120], rax; struct _RECTL *
0x140077699  mov     rax, [rsp+160h+var_F0]
0x14007769e  mov     [rsp+160h+var_128], rax; struct _RECTL *
0x1400776a3  mov     rax, [rbp+60h+var_B8]
0x1400776a7  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400776ac  mov     rax, [rbp+60h+var_B0]
0x1400776b0  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400776b5  mov     rax, [rbp+60h+var_C8]
0x1400776b9  mov     [rsp+160h+pvBits], rax; struct _XLATEOBJ *
0x1400776be  mov     [rsp+160h+var_FC], 0
0x1400776c6  call    ?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z; EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)
0x1400776cb  cmp     [rsp+160h+var_FC], 0
0x1400776d0  mov     r12d, eax
0x1400776d3  jz      loc_14007787E
0x1400776d9  lea     rax, [rsp+160h+var_F8]
0x1400776de  xor     r9d, r9d; pxlo
0x1400776e1  mov     [rsp+160h+pptlSrc], rax; pptlSrc
0x1400776e6  xor     r8d, r8d; pco
0x1400776e9  lea     rax, [rbp+60h+var_78]
0x1400776ed  mov     rdx, rdi; psoSrc
0x1400776f0  mov     rcx, rsi; psoDest
0x1400776f3  mov     [rsp+160h+pvBits], rax; prclDest
0x1400776f8  call    EngCopyBits
0x1400776fd  test    dword ptr [rdi+78h], 400h
0x140077704  jz      short loc_14007770F
0x140077706  mov     rax, [rbx+0B10h]
0x14007770d  jmp     short loc_140077716
0x14007770f  lea     rax, EngCopyBits
0x140077716  mov     r9, [rbp+60h+var_A8]
0x14007771a  lea     rcx, [rsp+160h+var_F8]
0x14007771f  mov     [rsp+160h+pptlSrc], rcx
0x140077724  xor     r8d, r8d
0x140077727  lea     rcx, [rbp+60h+var_78]
0x14007772b  mov     rdx, r15
0x14007772e  mov     [rsp+160h+pvBits], rcx
0x140077733  mov     rcx, rdi
0x140077736  call    _guard_dispatch_icall
0x14007773b  mov     r9, [rbp+60h+var_D0]; struct _CLIPOBJ *
0x14007773f  lea     rax, [rbp+60h+var_58]
0x140077743  mov     r8, [rbp+60h+var_D8]; struct _SURFOBJ *
0x140077747  mov     rcx, rdi; struct _SURFOBJ *
0x14007774a  mov     rdx, [rbp+60h+var_E0]; struct _SURFOBJ *
0x14007774e  mov     [rsp+160h+var_F0], rax
0x140077753  lea     rax, [rbp+60h+var_68]
0x140077757  mov     [rsp+160h+var_E8], rax
0x14007775c  mov     eax, [rbp+60h+iMode]
0x140077762  mov     [rsp+160h+var_110], eax; unsigned int
0x140077766  mov     rax, [rbp+60h+var_C0]
0x14007776a  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x14007776f  lea     rax, [rbp+60h+var_68]
0x140077773  mov     [rsp+160h+var_120], rax; struct _RECTL *
0x140077778  lea     rax, [rbp+60h+var_58]
0x14007777c  mov     [rsp+160h+var_128], rax; struct _RECTL *
0x140077781  mov     rax, [rbp+60h+var_B8]
0x140077785  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x14007778a  mov     rax, [rbp+60h+var_B0]
0x14007778e  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x140077793  mov     rax, [rbp+60h+var_C8]
0x140077797  mov     [rsp+160h+pvBits], rax; struct _XLATEOBJ *
0x14007779c  call    ?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z; EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)
0x1400777a1  cmp     eax, r12d
0x1400777a4  jz      short loc_1400777B9
0x1400777a6  lea     rcx, aBoldBnew; "bOld ^ bNew\n"
0x1400777ad  call    cs:__imp_DbgPrint
0x1400777b4  nop     dword ptr [rax+rax+00h]
0x1400777b9  mov     r9, [rbp+60h+var_A8]; pxlo
0x1400777bd  lea     rax, [rsp+160h+var_F8]
0x1400777c2  mov     [rsp+160h+pptlSrc], rax; pptlSrc
0x1400777c7  xor     r8d, r8d; pco
0x1400777ca  lea     rax, [rbp+60h+var_78]
0x1400777ce  mov     rdx, rdi; psoSrc
0x1400777d1  mov     rcx, r14; psoDest
0x1400777d4  mov     [rsp+160h+pvBits], rax; prclDest
0x1400777d9  call    EngCopyBits
0x1400777de  mov     rdx, [rsi+30h]
0x1400777e2  xor     r12d, r12d
0x1400777e5  mov     rax, [r14+30h]
0x1400777e9  mov     [rbp+60h+var_90], rdx
0x1400777ed  mov     [rbp+60h+var_88], rax
0x1400777f1  cmp     r12d, [rsi+28h]
0x1400777f5  jnb     loc_14007787E
0x1400777fb  mov     al, [r12+rax]
0x1400777ff  cmp     [r12+rdx], al
0x140077803  jz      short loc_140077830
0x140077805  lea     rcx, aMemcmpFailed; "memcmp failed\n"
0x14007780c  call    cs:__imp_DbgPrint
0x140077813  nop     dword ptr [rax+rax+00h]
0x140077818  mov     eax, [rsp+160h+var_100]
0x14007781c  inc     eax
0x14007781e  mov     [rsp+160h+var_100], eax
0x140077822  cmp     eax, 1
0x140077825  jz      short loc_140077839
0x140077827  cmp     eax, 2
0x14007782a  jz      short loc_14007787D
0x14007782c  mov     rdx, [rbp+60h+var_90]
0x140077830  mov     rax, [rbp+60h+var_88]
0x140077834  inc     r12d
0x140077837  jmp     short loc_1400777F1
0x140077839  int     3; Trap to Debugger
0x14007783a  test    dword ptr [rdi+78h], 400h
0x140077841  jz      short loc_14007784C
0x140077843  mov     rax, [rbx+0B10h]
0x14007784a  jmp     short loc_140077853
0x14007784c  lea     rax, EngCopyBits
0x140077853  mov     r9, [rbp+60h+var_A8]
0x140077857  lea     rcx, [rsp+160h+var_F8]
0x14007785c  mov     [rsp+160h+pptlSrc], rcx
0x140077861  xor     r8d, r8d
0x140077864  lea     rcx, [rbp+60h+var_78]
0x140077868  mov     rdx, r15
0x14007786b  mov     [rsp+160h+pvBits], rcx
0x140077870  mov     rcx, rdi
0x140077873  call    _guard_dispatch_icall
0x140077878  jmp     loc_140077645
0x14007787d  int     3; Trap to Debugger
0x14007787e  mov     r12, [rbp+60h+var_A0]
0x140077882  mov     rcx, rsi; pso
  ... truncated ...
```
