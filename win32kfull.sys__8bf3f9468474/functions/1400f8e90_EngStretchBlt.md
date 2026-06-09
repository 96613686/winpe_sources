# EngStretchBlt

- ea: `0x1400f8e90`
- end: `0x1400f942f`
- name: `EngStretchBlt`
- size: `1439`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, SURFOBJ *psoMask, CLIPOBJ *pco, XLATEOBJ *pxlo, COLORADJUSTMENT *pca, POINTL *pptlHTOrg, RECTL *prclDest, RECTL *prclSrc, POINTL *pptlMask, ULONG iMode)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x14006ac20`
- `0x1400f77f4`
- `0x14013b990`
- `0x140156f80`
- `0x14015e7f0`
- `0x1402a41f0`
- `0x1403105a0`
- `0x140313c50`
- `0x1403201f0`

## callees

- `0x1400f61f0`
- `0x1400f8e90`
- `0x1400f9438`
- `0x140263d18`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400f90a5`
- `ntoskrnl!DbgPrint` at `0x1400f92c0`
- `ntoskrnl!DbgPrint` at `0x1400f931f`
- `ntoskrnl!DbgPrint` at `0x1400f90a5`
- `ntoskrnl!DbgPrint` at `0x1400f92c0`
- `ntoskrnl!DbgPrint` at `0x1400f931f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400f9112`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400f9112`
- `win32kbase!EngLockSurface` at `0x1400f90b4`
- `win32kbase!EngLockSurface` at `0x1400f90c6`
- `win32kbase!EngLockSurface` at `0x1400f90d8`
- `win32kbase!EngLockSurface` at `0x1400f90b4`
- `win32kbase!EngLockSurface` at `0x1400f90c6`
- `win32kbase!EngLockSurface` at `0x1400f90d8`
- `win32kbase!EngUnlockSurface` at `0x1400f939b`
- `win32kbase!EngUnlockSurface` at `0x1400f93af`
- `win32kbase!EngUnlockSurface` at `0x1400f93c3`
- `win32kbase!EngUnlockSurface` at `0x1400f939b`
- `win32kbase!EngUnlockSurface` at `0x1400f93af`
- `win32kbase!EngUnlockSurface` at `0x1400f93c3`
- `win32kbase!EngCreateBitmap` at `0x1400f902e`
- `win32kbase!EngCreateBitmap` at `0x1400f9057`
- `win32kbase!EngCreateBitmap` at `0x1400f907c`
- `win32kbase!EngCreateBitmap` at `0x1400f902e`
- `win32kbase!EngCreateBitmap` at `0x1400f9057`
- `win32kbase!EngCreateBitmap` at `0x1400f907c`
- `win32kbase!EngDeleteSurface` at `0x1400f93d8`
- `win32kbase!EngDeleteSurface` at `0x1400f93ec`
- `win32kbase!EngDeleteSurface` at `0x1400f9400`
- `win32kbase!EngDeleteSurface` at `0x1400f93d8`
- `win32kbase!EngDeleteSurface` at `0x1400f93ec`
- `win32kbase!EngDeleteSurface` at `0x1400f9400`
- `WIN32K!W32GetSessionState` at `0x1400f8f13`
- `WIN32K!W32GetSessionState` at `0x1400f8f13`

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
  v18 = *(_QWORD *)(W32GetSessionState(psoDest) + 96);
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
          if ( ((__int64)psoDest[1].pvScan0 & 0x400) != 0 )
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
                if ( ((__int64)psoDest[1].pvScan0 & 0x400) != 0 )
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
0x1400f8e90  push    rbp
0x1400f8e92  push    rbx
0x1400f8e93  push    rsi
0x1400f8e94  push    rdi
0x1400f8e95  push    r12
0x1400f8e97  push    r13
0x1400f8e99  push    r14
0x1400f8e9b  push    r15
0x1400f8e9d  lea     rbp, [rsp-28h]
0x1400f8ea2  sub     rsp, 128h
0x1400f8ea9  mov     rax, cs:__security_cookie
0x1400f8eb0  xor     rax, rsp
0x1400f8eb3  mov     [rbp+60h+var_48], rax
0x1400f8eb7  mov     rax, [rbp+60h+pca]
0x1400f8ebe  mov     r12, r9
0x1400f8ec1  mov     r13, [rbp+60h+pxlo]
0x1400f8ec8  mov     r15, r8
0x1400f8ecb  mov     rbx, [rbp+60h+prclDest]
0x1400f8ed2  mov     r14, rdx
0x1400f8ed5  mov     rsi, [rbp+60h+prclSrc]
0x1400f8edc  mov     rdi, rcx
0x1400f8edf  mov     [rbp+60h+var_B0], rax
0x1400f8ee3  mov     rax, [rbp+60h+pptlHTOrg]
0x1400f8eea  mov     [rbp+60h+var_B8], rax
0x1400f8eee  mov     rax, [rbp+60h+pptlMask]
0x1400f8ef5  mov     [rbp+60h+var_C0], rax
0x1400f8ef9  mov     [rbp+60h+var_D0], r9
0x1400f8efd  mov     [rbp+60h+var_D8], r8
0x1400f8f01  mov     [rbp+60h+var_E0], rdx
0x1400f8f05  mov     [rbp+60h+var_C8], r13
0x1400f8f09  mov     [rsp+160h+var_F0], rbx
0x1400f8f0e  mov     [rsp+160h+var_E8], rsi
0x1400f8f13  call    cs:__imp_W32GetSessionState
0x1400f8f1a  nop     dword ptr [rax+rax+00h]
0x1400f8f1f  mov     rax, [rax+60h]
0x1400f8f23  mov     [rbp+60h+var_98], rax
0x1400f8f27  cmp     dword ptr [rax+1288h], 0
0x1400f8f2e  jnz     loc_1400F8FF0
0x1400f8f34  cmp     dword ptr [rax+1284h], 0
0x1400f8f3b  mov     r9, r12; struct _CLIPOBJ *
0x1400f8f3e  mov     r8, r15; struct _SURFOBJ *
0x1400f8f41  mov     rdx, r14; struct _SURFOBJ *
0x1400f8f44  mov     rcx, rdi; struct _SURFOBJ *
0x1400f8f47  jz      short loc_1400F8FA3
0x1400f8f49  mov     eax, [rbp+60h+iMode]
0x1400f8f4f  mov     [rsp+160h+var_110], eax; unsigned int
0x1400f8f53  mov     rax, [rbp+60h+var_C0]
0x1400f8f57  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x1400f8f5c  mov     rax, [rbp+60h+var_B8]
0x1400f8f60  mov     [rsp+160h+var_120], rsi; struct _RECTL *
0x1400f8f65  mov     [rsp+160h+var_128], rbx; struct _RECTL *
0x1400f8f6a  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400f8f6f  mov     rax, [rbp+60h+var_B0]
0x1400f8f73  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400f8f78  mov     [rsp+160h+pvBits], r13; struct _XLATEOBJ *
0x1400f8f7d  call    ?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z; EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)
0x1400f8f82  mov     rcx, [rbp+60h+var_48]
0x1400f8f86  xor     rcx, rsp; StackCookie
0x1400f8f89  call    __security_check_cookie
0x1400f8f8e  add     rsp, 128h
0x1400f8f95  pop     r15
0x1400f8f97  pop     r14
0x1400f8f99  pop     r13
0x1400f8f9b  pop     r12
0x1400f8f9d  pop     rdi
0x1400f8f9e  pop     rsi
0x1400f8f9f  pop     rbx
0x1400f8fa0  pop     rbp
0x1400f8fa1  retn
0x1400f8fa3  lea     rax, [rsp+160h+var_100]
0x1400f8fa8  mov     [rsp+160h+var_100], 0
0x1400f8fb0  mov     [rsp+160h+var_108], rax; int *
0x1400f8fb5  mov     eax, [rbp+60h+iMode]
0x1400f8fbb  mov     [rsp+160h+var_110], eax; unsigned int
0x1400f8fbf  mov     rax, [rbp+60h+var_C0]
0x1400f8fc3  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x1400f8fc8  mov     rax, [rbp+60h+var_B8]
0x1400f8fcc  mov     [rsp+160h+var_120], rsi; struct _RECTL *
0x1400f8fd1  mov     [rsp+160h+var_128], rbx; struct _RECTL *
0x1400f8fd6  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400f8fdb  mov     rax, [rbp+60h+var_B0]
0x1400f8fdf  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400f8fe4  mov     [rsp+160h+pvBits], r13; struct _XLATEOBJ *
0x1400f8fe9  call    ?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z; EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)
0x1400f8fee  jmp     short loc_1400F8F82
0x1400f8ff0  movups  xmm0, xmmword ptr [rbx]
0x1400f8ff3  mov     eax, [rdi+20h]
0x1400f8ff6  xor     r9d, r9d; fl
0x1400f8ff9  movups  xmm1, xmmword ptr [rsi]
0x1400f8ffc  mov     rcx, [rdi+20h]; sizl
0x1400f9000  xor     edx, edx; lWidth
0x1400f9002  mov     r8d, [rdi+48h]; iFormat
0x1400f9006  mov     rbx, [rdi+18h]
0x1400f900a  mov     [rbp+60h+var_78.right], eax
0x1400f900d  mov     eax, [rdi+24h]
0x1400f9010  movdqu  xmmword ptr [rbp+60h+var_58.left], xmm0
0x1400f9015  mov     qword ptr [rbp+60h+var_78.left], 0
0x1400f901d  movdqu  xmmword ptr [rbp+60h+var_68.left], xmm1
0x1400f9022  mov     [rbp+60h+var_78.bottom], eax
0x1400f9025  mov     [rsp+160h+pvBits], 0; pvBits
0x1400f902e  call    cs:__imp_EngCreateBitmap
0x1400f9035  nop     dword ptr [rax+rax+00h]
0x1400f903a  mov     rcx, [rdi+20h]; sizl
0x1400f903e  xor     r9d, r9d; fl
0x1400f9041  mov     r8d, [rdi+48h]; iFormat
0x1400f9045  xor     edx, edx; lWidth
0x1400f9047  mov     rsi, rax
0x1400f904a  mov     [rbp+60h+hsurf], rax
0x1400f904e  mov     [rsp+160h+pvBits], 0; pvBits
0x1400f9057  call    cs:__imp_EngCreateBitmap
0x1400f905e  nop     dword ptr [rax+rax+00h]
0x1400f9063  mov     rcx, [rdi+20h]; sizl
0x1400f9067  xor     r9d, r9d; fl
0x1400f906a  mov     r8d, [rdi+48h]; iFormat
0x1400f906e  xor     edx, edx; lWidth
0x1400f9070  mov     r13, rax
0x1400f9073  mov     [rsp+160h+pvBits], 0; pvBits
0x1400f907c  call    cs:__imp_EngCreateBitmap
0x1400f9083  nop     dword ptr [rax+rax+00h]
0x1400f9088  mov     [rbp+60h+var_A0], rax
0x1400f908c  mov     r12, rax
0x1400f908f  test    rsi, rsi
0x1400f9092  jz      short loc_1400F909E
0x1400f9094  test    r13, r13
0x1400f9097  jz      short loc_1400F909E
0x1400f9099  test    rax, rax
0x1400f909c  jnz     short loc_1400F90B1
0x1400f909e  lea     rcx, aHsurf10Hsurf20; "hsurf1 == 0 || hsurf2 == 0 || hsurf3 =="...
0x1400f90a5  call    cs:__imp_DbgPrint
0x1400f90ac  nop     dword ptr [rax+rax+00h]
0x1400f90b1  mov     rcx, rsi; hsurf
0x1400f90b4  call    cs:__imp_EngLockSurface
0x1400f90bb  nop     dword ptr [rax+rax+00h]
0x1400f90c0  mov     rcx, r13; hsurf
0x1400f90c3  mov     rsi, rax
0x1400f90c6  call    cs:__imp_EngLockSurface
0x1400f90cd  nop     dword ptr [rax+rax+00h]
0x1400f90d2  mov     rcx, r12; hsurf
0x1400f90d5  mov     r14, rax
0x1400f90d8  call    cs:__imp_EngLockSurface
0x1400f90df  nop     dword ptr [rax+rax+00h]
0x1400f90e4  mov     r15, rax
0x1400f90e7  test    rsi, rsi
0x1400f90ea  jz      loc_1400F93A7
0x1400f90f0  test    r14, r14
0x1400f90f3  jz      loc_1400F9398
0x1400f90f9  test    rax, rax
0x1400f90fc  jz      loc_1400F9398
0x1400f9102  mov     [rsp+160h+var_100], 0
0x1400f910a  mov     [rsp+160h+var_FC], 0
0x1400f9112  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400f9119  nop     dword ptr [rax+rax+00h]
0x1400f911e  lea     rcx, [rsp+160h+var_F8]
0x1400f9123  mov     qword ptr [rsp+160h+var_F8.x], 0
0x1400f912c  mov     [rsp+160h+pptlSrc], rcx; pptlSrc
0x1400f9131  add     rax, 1238h
0x1400f9137  lea     rcx, [rbp+60h+var_78]
0x1400f913b  mov     [rbp+60h+var_A8], rax
0x1400f913f  mov     [rsp+160h+pvBits], rcx; prclDest
0x1400f9144  mov     r9, rax; pxlo
0x1400f9147  mov     rcx, r15; psoDest
0x1400f914a  xor     r8d, r8d; pco
0x1400f914d  mov     rdx, rdi; psoSrc
0x1400f9150  call    EngCopyBits
0x1400f9155  mov     r8d, [rsi+28h]; Size
0x1400f9159  xor     edx, edx; Val
0x1400f915b  mov     rcx, [rsi+30h]; void *
0x1400f915f  call    memset_0
0x1400f9164  mov     r8d, [rsi+28h]; Size
0x1400f9168  xor     edx, edx; Val
0x1400f916a  mov     rcx, [r14+30h]; void *
0x1400f916e  call    memset_0
0x1400f9173  mov     r9, [rbp+60h+var_D0]; struct _CLIPOBJ *
0x1400f9177  lea     rax, [rsp+160h+var_FC]
0x1400f917c  mov     r8, [rbp+60h+var_D8]; struct _SURFOBJ *
0x1400f9180  mov     rcx, rdi; struct _SURFOBJ *
0x1400f9183  mov     rdx, [rbp+60h+var_E0]; struct _SURFOBJ *
0x1400f9187  mov     [rsp+160h+var_108], rax; int *
0x1400f918c  mov     eax, [rbp+60h+iMode]
0x1400f9192  mov     [rsp+160h+var_110], eax; unsigned int
0x1400f9196  mov     rax, [rbp+60h+var_C0]
0x1400f919a  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x1400f919f  mov     rax, [rsp+160h+var_E8]
0x1400f91a4  mov     [rsp+160h+var_120], rax; struct _RECTL *
0x1400f91a9  mov     rax, [rsp+160h+var_F0]
0x1400f91ae  mov     [rsp+160h+var_128], rax; struct _RECTL *
0x1400f91b3  mov     rax, [rbp+60h+var_B8]
0x1400f91b7  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400f91bc  mov     rax, [rbp+60h+var_B0]
0x1400f91c0  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400f91c5  mov     rax, [rbp+60h+var_C8]
0x1400f91c9  mov     [rsp+160h+pvBits], rax; struct _XLATEOBJ *
0x1400f91ce  mov     [rsp+160h+var_FC], 0
0x1400f91d6  call    ?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z; EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)
0x1400f91db  cmp     [rsp+160h+var_FC], 0
0x1400f91e0  mov     r12d, eax
0x1400f91e3  jz      loc_1400F9394
0x1400f91e9  lea     rax, [rsp+160h+var_F8]
0x1400f91ee  xor     r9d, r9d; pxlo
0x1400f91f1  mov     [rsp+160h+pptlSrc], rax; pptlSrc
0x1400f91f6  xor     r8d, r8d; pco
0x1400f91f9  lea     rax, [rbp+60h+var_78]
0x1400f91fd  mov     rdx, rdi; psoSrc
0x1400f9200  mov     rcx, rsi; psoDest
0x1400f9203  mov     [rsp+160h+pvBits], rax; prclDest
0x1400f9208  call    EngCopyBits
0x1400f920d  test    dword ptr [rdi+88h], 400h
0x1400f9217  jz      short loc_1400F9222
0x1400f9219  mov     rax, [rbx+0B10h]
0x1400f9220  jmp     short loc_1400F9229
0x1400f9222  lea     rax, EngCopyBits
0x1400f9229  mov     r9, [rbp+60h+var_A8]
0x1400f922d  lea     rcx, [rsp+160h+var_F8]
0x1400f9232  mov     [rsp+160h+pptlSrc], rcx
0x1400f9237  xor     r8d, r8d
0x1400f923a  lea     rcx, [rbp+60h+var_78]
0x1400f923e  mov     rdx, r15
0x1400f9241  mov     [rsp+160h+pvBits], rcx
0x1400f9246  mov     rcx, rdi
0x1400f9249  call    _guard_dispatch_icall
0x1400f924e  mov     r9, [rbp+60h+var_D0]; struct _CLIPOBJ *
0x1400f9252  lea     rax, [rbp+60h+var_58]
0x1400f9256  mov     r8, [rbp+60h+var_D8]; struct _SURFOBJ *
0x1400f925a  mov     rcx, rdi; struct _SURFOBJ *
0x1400f925d  mov     rdx, [rbp+60h+var_E0]; struct _SURFOBJ *
0x1400f9261  mov     [rsp+160h+var_F0], rax
0x1400f9266  lea     rax, [rbp+60h+var_68]
0x1400f926a  mov     [rsp+160h+var_E8], rax
0x1400f926f  mov     eax, [rbp+60h+iMode]
0x1400f9275  mov     [rsp+160h+var_110], eax; unsigned int
0x1400f9279  mov     rax, [rbp+60h+var_C0]
0x1400f927d  mov     [rsp+160h+var_118], rax; struct _POINTL *
0x1400f9282  lea     rax, [rbp+60h+var_68]
0x1400f9286  mov     [rsp+160h+var_120], rax; struct _RECTL *
0x1400f928b  lea     rax, [rbp+60h+var_58]
0x1400f928f  mov     [rsp+160h+var_128], rax; struct _RECTL *
0x1400f9294  mov     rax, [rbp+60h+var_B8]
0x1400f9298  mov     [rsp+160h+var_130], rax; struct _POINTL *
0x1400f929d  mov     rax, [rbp+60h+var_B0]
0x1400f92a1  mov     [rsp+160h+pptlSrc], rax; struct tagCOLORADJUSTMENT *
0x1400f92a6  mov     rax, [rbp+60h+var_C8]
0x1400f92aa  mov     [rsp+160h+pvBits], rax; struct _XLATEOBJ *
0x1400f92af  call    ?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z; EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)
0x1400f92b4  cmp     eax, r12d
0x1400f92b7  jz      short loc_1400F92CC
0x1400f92b9  lea     rcx, aBoldBnew; "bOld ^ bNew\n"
0x1400f92c0  call    cs:__imp_DbgPrint
0x1400f92c7  nop     dword ptr [rax+rax+00h]
0x1400f92cc  mov     r9, [rbp+60h+var_A8]; pxlo
0x1400f92d0  lea     rax, [rsp+160h+var_F8]
0x1400f92d5  mov     [rsp+160h+pptlSrc], rax; pptlSrc
0x1400f92da  xor     r8d, r8d; pco
0x1400f92dd  lea     rax, [rbp+60h+var_78]
0x1400f92e1  mov     rdx, rdi; psoSrc
0x1400f92e4  mov     rcx, r14; psoDest
0x1400f92e7  mov     [rsp+160h+pvBits], rax; prclDest
0x1400f92ec  call    EngCopyBits
0x1400f92f1  mov     rdx, [rsi+30h]
0x1400f92f5  xor     r12d, r12d
0x1400f92f8  mov     rax, [r14+30h]
0x1400f92fc  mov     [rbp+60h+var_90], rdx
0x1400f9300  mov     [rbp+60h+var_88], rax
0x1400f9304  cmp     r12d, [rsi+28h]
0x1400f9308  jnb     loc_1400F9394
0x1400f930e  mov     al, [r12+rax]
0x1400f9312  cmp     [r12+rdx], al
0x1400f9316  jz      short loc_1400F9343
0x1400f9318  lea     rcx, aMemcmpFailed; "memcmp failed\n"
0x1400f931f  call    cs:__imp_DbgPrint
0x1400f9326  nop     dword ptr [rax+rax+00h]
0x1400f932b  mov     eax, [rsp+160h+var_100]
0x1400f932f  inc     eax
0x1400f9331  mov     [rsp+160h+var_100], eax
0x1400f9335  cmp     eax, 1
0x1400f9338  jz      short loc_1400F934C
0x1400f933a  cmp     eax, 2
0x1400f933d  jz      short loc_1400F9393
0x1400f933f  mov     rdx, [rbp+60h+var_90]
0x1400f9343  mov     rax, [rbp+60h+var_88]
0x1400f9347  inc     r12d
0x1400f934a  jmp     short loc_1400F9304
0x1400f934c  int     3; Trap to Debugger
0x1400f934d  test    dword ptr [rdi+88h], 400h
0x1400f9357  jz      short loc_1400F9362
0x1400f9359  mov     rax, [rbx+0B10h]
0x1400f9360  jmp     short loc_1400F9369
0x1400f9362  lea     rax, EngCopyBits
0x1400f9369  mov     r9, [rbp+60h+var_A8]
0x1400f936d  lea     rcx, [rsp+160h+var_F8]
0x1400f9372  mov     [rsp+160h+pptlSrc], rcx
0x1400f9377  xor     r8d, r8d
0x1400f937a  lea     rcx, [rbp+60h+var_78]
0x1400f937e  mov     rdx, r15
0x1400f9381  mov     [rsp+160h+pvBits], rcx
0x1400f9386  mov     rcx, rdi
0x1400f9389  call    _guard_dispatch_icall
0x1400f938e  jmp     loc_1400F9155
0x1400f9393  int     3; Trap to Debugger
0x1400f9394  mov     r12, [rbp+60h+var_A0]
0x1400f9398  mov     rcx, rsi; pso
  ... truncated ...
```
