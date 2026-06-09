# vSpUpdateSpriteVisRgn(HDEV__ *,ulong)

- ea: `0x14008caa0`
- end: `0x14008cf98`
- name: `?vSpUpdateSpriteVisRgn@@YAXPEAUHDEV__@@K@Z`
- size: `1272`
- prototype: `void __fastcall(HDEV, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400188f0`

## callees

- `0x1400184c0`
- `0x140075244`
- `0x14008c480`
- `0x14008caa0`
- `0x14008cfa0`
- `0x14008cfc0`
- `0x14008d000`
- `0x14009c914`
- `0x14009ca40`
- `0x1400fc340`
- `0x14011997c`
- `0x14030b688`
- `0x14030d048`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008cb3f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008cb3f`
- `win32kbase!PopThreadGuardedObject` at `0x14008cb98`
- `win32kbase!PopThreadGuardedObject` at `0x14008cb98`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008cb61`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008cb61`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14008ccef`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14008cd0c`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14008ccef`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14008cd0c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008cbd1`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008cbd1`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008cc17`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008cc17`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008cc4d`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008cc4d`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x14008cdae`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x14008cdae`
- `win32kbase!??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z` at `0x14008cd88`
- `win32kbase!??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z` at `0x14008cd88`
- `win32kbase!??1SPRITELOCK@@QEAA@XZ` at `0x14008ce02`
- `win32kbase!??1SPRITELOCK@@QEAA@XZ` at `0x14008ce02`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008cd6a`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008cd6a`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14008cbeb`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14008cbeb`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14008cb78`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14008cb78`
- `WIN32K!W32GetSessionState` at `0x14008cdd3`
- `WIN32K!W32GetSessionState` at `0x14008cdd3`

## pseudocode

```c
void __fastcall vSpUpdateSpriteVisRgn(HDEV a1, char a2)
{
  HDEV v3; // rsi
  int v4; // r12d
  Gre::Base *v5; // rcx
  HDEV v6; // r14
  int v7; // r13d
  __int64 i; // rdi
  struct REGION *v9; // rdx
  _DWORD *v10; // rbx
  struct REGION *v11; // rsi
  int v12; // r9d
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // esi
  REGION *v18; // rcx
  __int64 v19; // rcx
  int v20; // r15d
  unsigned int v21; // esi
  int v22; // eax
  int v23; // eax
  unsigned int j; // edx
  struct _POINTL v25; // [rsp+30h] [rbp-D0h] BYREF
  struct _POINTL v26; // [rsp+38h] [rbp-C8h] BYREF
  struct _POINTL v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  HDEV v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[40]; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[192]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v35[4]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v36[4]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v37[16]; // [rsp+174h] [rbp+74h] BYREF
  char v38; // [rsp+184h] [rbp+84h]
  __int64 v39; // [rsp+1A8h] [rbp+A8h]
  __int64 v40; // [rsp+1C0h] [rbp+C0h]
  int v41; // [rsp+1C8h] [rbp+C8h]
  int v42; // [rsp+1F0h] [rbp+F0h]
  __int64 v43; // [rsp+200h] [rbp+100h]
  _BYTE v44[4]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v45[16]; // [rsp+214h] [rbp+114h] BYREF
  char v46; // [rsp+224h] [rbp+124h]
  __int64 v47; // [rsp+248h] [rbp+148h]
  __int64 v48; // [rsp+260h] [rbp+160h]
  int v49; // [rsp+268h] [rbp+168h]
  int v50; // [rsp+290h] [rbp+190h]
  __int64 v51; // [rsp+2A0h] [rbp+1A0h]
  _DWORD v52[84]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _DWORD v53[84]; // [rsp+400h] [rbp+300h] BYREF

  v30 = a1;
  v3 = a1;
  v4 = 0;
  v26 = 0;
  memset_0(v52, 0, 0x144u);
  memset_0(v53, 0, 0x144u);
  v6 = v3 + 20;
  if ( *((_QWORD *)v3 + 11) )
  {
    v7 = 1;
    if ( (a2 & 4) != 0 )
    {
      Gre::Base::Globals(v5);
      vSpComputeNoPresentRegion((struct _SPRITESTATE *)(v3 + 20), 1);
    }
    for ( i = *((_QWORD *)v3 + 11); ; i = *(_QWORD *)(i + 24) )
    {
      if ( !i )
        return;
      if ( *(_QWORD *)(i + 72) )
        break;
LABEL_12:
      ;
    }
    UserVisrgnFromHwnd((HRGN *)v6 + 133);
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v25);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v31, *((HRGN *)v6 + 133), 0, 0);
    if ( !v31 || !*(_QWORD *)&v25 || !RGNOBJ::bCopy((RGNOBJ *)&v25, (struct RGNOBJ *)&v31) )
    {
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v25);
LABEL_7:
      if ( !v33 )
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v31);
      if ( v31 )
        _InterlockedDecrement16((volatile signed __int16 *)(v31 + 12));
      PopThreadGuardedObject(v32);
      goto LABEL_12;
    }
    v26.x = -*((_DWORD *)v3 + 644);
    v26.y = -*((_DWORD *)v3 + 645);
    RGNOBJ::bOffset((RGNOBJ *)&v25, &v26);
    v9 = *(struct REGION **)(i + 184);
    v10 = (_DWORD *)(i + 112);
    v11 = (struct REGION *)v25;
    v27 = v25;
    if ( v9 )
    {
      v12 = *(_DWORD *)(i + 116);
      v13 = *v10 + *(_DWORD *)(i + 104) - *(_DWORD *)(i + 96);
      v35[0] = *v10;
      v35[2] = v13;
      v14 = v12 + *(_DWORD *)(i + 108) - *(_DWORD *)(i + 100);
      v35[1] = v12;
      v35[3] = v14;
      v40 = 0;
      v41 = 0;
      v42 = 1;
      v43 = 0;
      v39 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 1;
      v51 = 0;
      v47 = 0;
      XCLIPOBJ::vSetup((XCLIPOBJ *)v36, v9, (const struct ERECTL *)v35, 0);
      XCLIPOBJ::vSetup((XCLIPOBJ *)v44, v11, (const struct ERECTL *)v35, 0);
      ERECTL::bEmpty((ERECTL *)v45);
      v15 = ERECTL::bEmpty((ERECTL *)v37);
      if ( v16 == v15 )
      {
        if ( !v38 && !v46 )
        {
          v17 = 1;
LABEL_23:
          vSpFreeClipResources((struct SPRITE *)i);
          v18 = (REGION *)v27;
          *(struct _POINTL *)(i + 184) = v27;
          REGION::vStamp(v18);
          v28 = *(_QWORD *)v6;
          SPRITELOCK::SPRITELOCK((SPRITELOCK *)v29, (struct PDEVOBJ *)&v28);
          SPRITEDDIACCESS::SPRITEDDIACCESS((SPRITEDDIACCESS *)v34, (struct PDEVOBJ *)&v28);
          *(_DWORD *)i &= ~1u;
          if ( RGNOBJ::bInside((RGNOBJ *)&v25, (struct _RECTL *)(v6 + 10)) != 2 )
            *(_DWORD *)i |= 1u;
          bSpUpdatePosition((struct SPRITE *)i, (struct _POINTL *)(i + 112), 0, 0);
          if ( *(_QWORD *)(*(_QWORD *)(W32GetSessionState(v19) + 96) + 4816LL) )
            vSpCheckForWndobjOverlap((struct _SPRITESTATE *)v6, (struct _RECTL *)(i + 80), (struct _RECTL *)(i + 80));
          if ( !v17 )
          {
            if ( *((_QWORD *)v6 + 130) )
            {
              v27 = 0;
              vSpUpdateLockedScreenAreas((struct _SPRITESTATE *)v6, &v27, (struct _RECTL *)(i + 80), 0, 1);
            }
            vSpRedrawSprite((struct SPRITE *)i);
          }
          SPRITEDDIACCESS::~SPRITEDDIACCESS((SPRITEDDIACCESS *)v34);
          SPRITELOCK::~SPRITELOCK((SPRITELOCK *)v29);
          v3 = v30;
          goto LABEL_7;
        }
        if ( v38 == v46 )
        {
          XCLIPOBJ::cEnumStart((XCLIPOBJ *)v36, 0, 0, 4u, 0x64u);
          XCLIPOBJ::cEnumStart((XCLIPOBJ *)v44, 0, 0, 4u, 0x64u);
          v20 = 1;
          while ( 1 )
          {
            v52[0] = 0;
            v21 = 0;
            v53[0] = 0;
            if ( v20 )
            {
              v22 = XCLIPOBJ::bEnum((XCLIPOBJ *)v36, 0x144u, v52, 0);
              v21 = v52[0];
              v20 = v22;
            }
            if ( v7 )
            {
              v23 = XCLIPOBJ::bEnum((XCLIPOBJ *)v44, 0x144u, v53, 0);
              v4 = v53[0];
              v7 = v23;
            }
            if ( v21 != v4 )
              break;
            v4 = 0;
            for ( j = 0; j < v21; ++j )
            {
              if ( v53[4 * j + 1] != v52[4 * j + 1]
                || v53[4 * j + 2] != v52[4 * j + 2]
                || v53[4 * j + 3] != v52[4 * j + 3]
                || v53[4 * j + 4] != v52[4 * j + 4] )
              {
                goto LABEL_41;
              }
            }
            if ( !v20 )
            {
              v17 = 1;
              if ( !v7 )
              {
                v7 = 1;
                goto LABEL_23;
              }
            }
          }
          v4 = 0;
LABEL_41:
          v17 = 0;
          v7 = 1;
          goto LABEL_23;
        }
      }
    }
    v17 = 0;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x14008caa0  push    rbp
0x14008caa2  push    rbx
0x14008caa3  push    rsi
0x14008caa4  push    rdi
0x14008caa5  push    r12
0x14008caa7  push    r13
0x14008caa9  push    r14
0x14008caab  push    r15
0x14008caad  lea     rbp, [rsp-468h]
0x14008cab5  sub     rsp, 568h
0x14008cabc  mov     rax, cs:__security_cookie
0x14008cac3  xor     rax, rsp
0x14008cac6  mov     [rbp+4A0h+var_50], rax
0x14008cacd  mov     ebx, edx
0x14008cacf  mov     [rsp+5A0h+var_548], rcx
0x14008cad4  mov     rsi, rcx
0x14008cad7  mov     edi, 144h
0x14008cadc  xor     r12d, r12d
0x14008cadf  lea     rcx, [rbp+4A0h+var_2F0]; void *
0x14008cae6  mov     r8d, edi; Size
0x14008cae9  mov     [rsp+5A0h+var_568], r12
0x14008caee  xor     edx, edx; Val
0x14008caf0  call    memset_0
0x14008caf5  mov     r8d, edi; Size
0x14008caf8  lea     rcx, [rbp+4A0h+var_1A0]; void *
0x14008caff  xor     edx, edx; Val
0x14008cb01  call    memset_0
0x14008cb06  lea     r14, [rsi+50h]
0x14008cb0a  cmp     [r14+8], r12
0x14008cb0e  jnz     short loc_14008CB34
0x14008cb10  mov     rcx, [rbp+4A0h+var_50]
0x14008cb17  xor     rcx, rsp; StackCookie
0x14008cb1a  call    __security_check_cookie
0x14008cb1f  add     rsp, 568h
0x14008cb26  pop     r15
0x14008cb28  pop     r14
0x14008cb2a  pop     r13
0x14008cb2c  pop     r12
0x14008cb2e  pop     rdi
0x14008cb2f  pop     rsi
0x14008cb30  pop     rbx
0x14008cb31  pop     rbp
0x14008cb32  retn
0x14008cb34  mov     r13d, 1
0x14008cb3a  test    bl, 4
0x14008cb3d  jz      short loc_14008CB56
0x14008cb3f  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008cb46  nop     dword ptr [rax+rax+00h]
0x14008cb4b  mov     edx, r13d; int
0x14008cb4e  mov     rcx, r14; struct _SPRITESTATE *
0x14008cb51  call    ?vSpComputeNoPresentRegion@@YAXPEAU_SPRITESTATE@@H@Z; vSpComputeNoPresentRegion(_SPRITESTATE *,int)
0x14008cb56  mov     rdi, [r14+8]
0x14008cb5a  jmp     short loc_14008CBA8
0x14008cb5c  lea     rcx, [rsp+5A0h+var_570]
0x14008cb61  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008cb68  nop     dword ptr [rax+rax+00h]
0x14008cb6d  cmp     [rbp+4A0h+var_510], r12d
0x14008cb71  jnz     short loc_14008CB84
0x14008cb73  lea     rcx, [rsp+5A0h+var_540]
0x14008cb78  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14008cb7f  nop     dword ptr [rax+rax+00h]
0x14008cb84  mov     rax, [rsp+5A0h+var_540]
0x14008cb89  test    rax, rax
0x14008cb8c  jz      short loc_14008CB93
0x14008cb8e  lock dec word ptr [rax+0Ch]
0x14008cb93  lea     rcx, [rsp+5A0h+var_538]
0x14008cb98  call    cs:__imp_PopThreadGuardedObject
0x14008cb9f  nop     dword ptr [rax+rax+00h]
0x14008cba4  mov     rdi, [rdi+18h]
0x14008cba8  test    rdi, rdi
0x14008cbab  jz      loc_14008CB10
0x14008cbb1  mov     rdx, [rdi+48h]
0x14008cbb5  test    rdx, rdx
0x14008cbb8  jz      short loc_14008CBA4
0x14008cbba  lea     rbx, [r14+428h]
0x14008cbc1  xor     r8d, r8d
0x14008cbc4  mov     rcx, rbx; HRGN *
0x14008cbc7  call    UserVisrgnFromHwnd
0x14008cbcc  lea     rcx, [rsp+5A0h+var_570]
0x14008cbd1  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14008cbd8  nop     dword ptr [rax+rax+00h]
0x14008cbdd  mov     rdx, [rbx]
0x14008cbe0  lea     rcx, [rsp+5A0h+var_540]
0x14008cbe5  xor     r9d, r9d
0x14008cbe8  xor     r8d, r8d
0x14008cbeb  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14008cbf2  nop     dword ptr [rax+rax+00h]
0x14008cbf7  cmp     [rsp+5A0h+var_540], r12
0x14008cbfc  jz      loc_14008CB5C
0x14008cc02  cmp     [rsp+5A0h+var_570], r12
0x14008cc07  jz      loc_14008CB5C
0x14008cc0d  lea     rdx, [rsp+5A0h+var_540]
0x14008cc12  lea     rcx, [rsp+5A0h+var_570]
0x14008cc17  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14008cc1e  nop     dword ptr [rax+rax+00h]
0x14008cc23  test    eax, eax
0x14008cc25  jz      loc_14008CB5C
0x14008cc2b  mov     eax, [rsi+0A10h]
0x14008cc31  lea     rdx, [rsp+5A0h+var_568]
0x14008cc36  neg     eax
0x14008cc38  lea     rcx, [rsp+5A0h+var_570]
0x14008cc3d  mov     dword ptr [rsp+5A0h+var_568], eax
0x14008cc41  mov     eax, [rsi+0A14h]
0x14008cc47  neg     eax
0x14008cc49  mov     dword ptr [rsp+5A0h+var_568+4], eax
0x14008cc4d  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14008cc54  nop     dword ptr [rax+rax+00h]
0x14008cc59  mov     rdx, [rdi+0B8h]
0x14008cc60  lea     rbx, [rdi+70h]
0x14008cc64  mov     rsi, [rsp+5A0h+var_570]
0x14008cc69  mov     qword ptr [rsp+5A0h+var_560.x], rsi
0x14008cc6e  test    rdx, rdx
0x14008cc71  jz      loc_14008CE18
0x14008cc77  mov     r8d, [rbx]
0x14008cc7a  mov     r9d, [rdi+74h]
0x14008cc7e  mov     ecx, [rdi+68h]
0x14008cc81  sub     ecx, [rdi+60h]
0x14008cc84  add     ecx, r8d
0x14008cc87  mov     [rbp+4A0h+var_440], r8d
0x14008cc8b  mov     [rbp+4A0h+var_438], ecx
0x14008cc8e  lea     r8, [rbp+4A0h+var_440]
0x14008cc92  mov     ecx, [rdi+6Ch]
0x14008cc95  sub     ecx, [rdi+64h]
0x14008cc98  add     ecx, r9d
0x14008cc9b  mov     [rbp+4A0h+var_43C], r9d
0x14008cc9f  mov     [rbp+4A0h+var_434], ecx
0x14008cca2  xor     r9d, r9d
0x14008cca5  lea     rcx, [rbp+4A0h+var_430]
0x14008cca9  mov     [rbp+4A0h+var_3E0], r12
0x14008ccb0  mov     [rbp+4A0h+var_3D8], r12d
0x14008ccb7  mov     [rbp+4A0h+var_3B0], r13d
0x14008ccbe  mov     [rbp+4A0h+var_3A0], r12
0x14008ccc5  mov     [rbp+4A0h+var_3F8], r12
0x14008cccc  mov     [rbp+4A0h+var_340], r12
0x14008ccd3  mov     [rbp+4A0h+var_338], r12d
0x14008ccda  mov     [rbp+4A0h+var_310], r13d
0x14008cce1  mov     [rbp+4A0h+var_300], r12
0x14008cce8  mov     [rbp+4A0h+var_358], r12
0x14008ccef  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14008ccf6  nop     dword ptr [rax+rax+00h]
0x14008ccfb  xor     r9d, r9d
0x14008ccfe  lea     r8, [rbp+4A0h+var_440]
0x14008cd02  mov     rdx, rsi
0x14008cd05  lea     rcx, [rbp+4A0h+var_390]
0x14008cd0c  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14008cd13  nop     dword ptr [rax+rax+00h]
0x14008cd18  lea     rcx, [rbp+4A0h+var_38C]; this
0x14008cd1f  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14008cd24  lea     rcx, [rbp+4A0h+var_42C]; this
0x14008cd28  mov     edx, eax
0x14008cd2a  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14008cd2f  cmp     edx, eax
0x14008cd31  jnz     loc_14008CE18
0x14008cd37  mov     cl, [rbp+4A0h+var_41C]
0x14008cd3d  mov     al, [rbp+4A0h+var_37C]
0x14008cd43  test    cl, cl
0x14008cd45  jnz     loc_14008CE37
0x14008cd4b  test    al, al
0x14008cd4d  jnz     loc_14008CE37
0x14008cd53  mov     esi, r13d
0x14008cd56  mov     rcx, rdi; struct SPRITE *
0x14008cd59  call    ?vSpFreeClipResources@@YAXPEAVSPRITE@@@Z; vSpFreeClipResources(SPRITE *)
0x14008cd5e  mov     rcx, qword ptr [rsp+5A0h+var_560.x]
0x14008cd63  mov     [rdi+0B8h], rcx
0x14008cd6a  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14008cd71  nop     dword ptr [rax+rax+00h]
0x14008cd76  mov     rax, [r14]
0x14008cd79  lea     rdx, [rsp+5A0h+var_558]
0x14008cd7e  lea     rcx, [rsp+5A0h+var_550]
0x14008cd83  mov     [rsp+5A0h+var_558], rax
0x14008cd88  call    cs:__imp_??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z; SPRITELOCK::SPRITELOCK(PDEVOBJ &)
0x14008cd8f  nop     dword ptr [rax+rax+00h]
0x14008cd94  lea     rdx, [rsp+5A0h+var_558]; struct PDEVOBJ *
0x14008cd99  lea     rcx, [rbp+4A0h+var_500]; this
0x14008cd9d  call    ??0SPRITEDDIACCESS@@QEAA@AEAVPDEVOBJ@@@Z; SPRITEDDIACCESS::SPRITEDDIACCESS(PDEVOBJ &)
0x14008cda2  and     dword ptr [rdi], 0FFFFFFFEh
0x14008cda5  lea     rdx, [r14+28h]
0x14008cda9  lea     rcx, [rsp+5A0h+var_570]
0x14008cdae  call    cs:__imp_?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z; RGNOBJ::bInside(_RECTL *)
0x14008cdb5  nop     dword ptr [rax+rax+00h]
0x14008cdba  cmp     eax, 2
0x14008cdbd  jz      short loc_14008CDC2
0x14008cdbf  or      [rdi], r13d
0x14008cdc2  xor     r9d, r9d; int
0x14008cdc5  xor     r8d, r8d; int
0x14008cdc8  mov     rdx, rbx; struct _POINTL *
0x14008cdcb  mov     rcx, rdi; struct SPRITE *
0x14008cdce  call    ?bSpUpdatePosition@@YAHPEAVSPRITE@@PEAU_POINTL@@HH@Z; bSpUpdatePosition(SPRITE *,_POINTL *,int,int)
0x14008cdd3  call    cs:__imp_W32GetSessionState
0x14008cdda  nop     dword ptr [rax+rax+00h]
0x14008cddf  mov     rcx, [rax+60h]
0x14008cde3  cmp     [rcx+12D0h], r12
0x14008cdea  jnz     loc_14008CF61
0x14008cdf0  test    esi, esi
0x14008cdf2  jz      short loc_14008CE20
0x14008cdf4  lea     rcx, [rbp+4A0h+var_500]; this
0x14008cdf8  call    ??1SPRITEDDIACCESS@@QEAA@XZ; SPRITEDDIACCESS::~SPRITEDDIACCESS(void)
0x14008cdfd  lea     rcx, [rsp+5A0h+var_550]
0x14008ce02  call    cs:__imp_??1SPRITELOCK@@QEAA@XZ; SPRITELOCK::~SPRITELOCK(void)
0x14008ce09  nop     dword ptr [rax+rax+00h]
0x14008ce0e  mov     rsi, [rsp+5A0h+var_548]
0x14008ce13  jmp     loc_14008CB6D
0x14008ce18  mov     esi, r12d
0x14008ce1b  jmp     loc_14008CD56
0x14008ce20  cmp     [r14+410h], r12
0x14008ce27  jnz     loc_14008CF75
0x14008ce2d  mov     rcx, rdi; struct SPRITE *
0x14008ce30  call    ?vSpRedrawSprite@@YAXPEAVSPRITE@@@Z; vSpRedrawSprite(SPRITE *)
0x14008ce35  jmp     short loc_14008CDF4
0x14008ce37  cmp     cl, al
0x14008ce39  jnz     short loc_14008CE18
0x14008ce3b  mov     r9d, 4; unsigned int
0x14008ce41  mov     [rsp+5A0h+var_580], 64h ; 'd'; unsigned int
0x14008ce49  xor     r8d, r8d; unsigned int
0x14008ce4c  lea     rcx, [rbp+4A0h+var_430]; this
0x14008ce50  xor     edx, edx; int
0x14008ce52  call    ?cEnumStart@XCLIPOBJ@@QEAAKHKKK@Z; XCLIPOBJ::cEnumStart(int,ulong,ulong,ulong)
0x14008ce57  mov     r9d, 4; unsigned int
0x14008ce5d  mov     [rsp+5A0h+var_580], 64h ; 'd'; unsigned int
0x14008ce65  xor     r8d, r8d; unsigned int
0x14008ce68  lea     rcx, [rbp+4A0h+var_390]; this
0x14008ce6f  xor     edx, edx; int
0x14008ce71  call    ?cEnumStart@XCLIPOBJ@@QEAAKHKKK@Z; XCLIPOBJ::cEnumStart(int,ulong,ulong,ulong)
0x14008ce76  mov     r15d, r13d
0x14008ce79  mov     [rbp+4A0h+var_2F0], r12d
0x14008ce80  mov     esi, r12d
0x14008ce83  mov     [rbp+4A0h+var_1A0], r12d
0x14008ce8a  test    r15d, r15d
0x14008ce8d  jz      short loc_14008CEB0
0x14008ce8f  xor     r9d, r9d; unsigned int *
0x14008ce92  lea     r8, [rbp+4A0h+var_2F0]; void *
0x14008ce99  mov     edx, 144h; unsigned int
0x14008ce9e  lea     rcx, [rbp+4A0h+var_430]; this
0x14008cea2  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x14008cea7  mov     esi, [rbp+4A0h+var_2F0]
0x14008cead  mov     r15d, eax
0x14008ceb0  test    r13d, r13d
0x14008ceb3  jz      short loc_14008CEDA
0x14008ceb5  xor     r9d, r9d; unsigned int *
0x14008ceb8  lea     r8, [rbp+4A0h+var_1A0]; void *
0x14008cebf  mov     edx, 144h; unsigned int
0x14008cec4  lea     rcx, [rbp+4A0h+var_390]; this
0x14008cecb  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x14008ced0  mov     r12d, [rbp+4A0h+var_1A0]
0x14008ced7  mov     r13d, eax
0x14008ceda  cmp     esi, r12d
0x14008cedd  jz      short loc_14008CEF0
0x14008cedf  xor     r12d, r12d
0x14008cee2  mov     esi, r12d
0x14008cee5  mov     r13d, 1
0x14008ceeb  jmp     loc_14008CD56
0x14008cef0  xor     r12d, r12d
0x14008cef3  mov     edx, r12d
0x14008cef6  cmp     edx, esi
0x14008cef8  jnb     short loc_14008CF43
0x14008cefa  mov     ecx, edx
0x14008cefc  add     rcx, rcx
0x14008ceff  mov     eax, [rbp+rcx*8+4A0h+var_2EC]
0x14008cf06  cmp     [rbp+rcx*8+4A0h+var_19C], eax
0x14008cf0d  jnz     short loc_14008CEE2
0x14008cf0f  mov     eax, [rbp+rcx*8+4A0h+var_2E8]
0x14008cf16  cmp     [rbp+rcx*8+4A0h+var_198], eax
0x14008cf1d  jnz     short loc_14008CEE2
0x14008cf1f  mov     eax, [rbp+rcx*8+4A0h+var_2E4]
0x14008cf26  cmp     [rbp+rcx*8+4A0h+var_194], eax
0x14008cf2d  jnz     short loc_14008CEE2
0x14008cf2f  mov     eax, [rbp+rcx*8+4A0h+var_2E0]
0x14008cf36  cmp     [rbp+rcx*8+4A0h+var_190], eax
0x14008cf3d  jnz     short loc_14008CEE2
0x14008cf3f  inc     edx
0x14008cf41  jmp     short loc_14008CEF6
0x14008cf43  test    r15d, r15d
0x14008cf46  jnz     loc_14008CE79
0x14008cf4c  lea     esi, [r15+1]
0x14008cf50  test    r13d, r13d
0x14008cf53  jnz     loc_14008CE79
0x14008cf59  mov     r13d, esi
0x14008cf5c  jmp     loc_14008CD56
0x14008cf61  lea     rdx, [rdi+50h]; struct _RECTL *
0x14008cf65  mov     rcx, r14; struct _SPRITESTATE *
0x14008cf68  mov     r8, rdx; struct _RECTL *
0x14008cf6b  call    ?vSpCheckForWndobjOverlap@@YAXPEAU_SPRITESTATE@@PEAU_RECTL@@1@Z; vSpCheckForWndobjOverlap(_SPRITESTATE *,_RECTL *,_RECTL *)
0x14008cf70  jmp     loc_14008CDF0
0x14008cf75  lea     r8, [rdi+50h]; struct _RECTL *
0x14008cf79  mov     qword ptr [rsp+5A0h+var_560.x], r12
0x14008cf7e  xor     r9d, r9d; struct _CLIPOBJ *
0x14008cf81  mov     [rsp+5A0h+var_580], r13d; int
0x14008cf86  lea     rdx, [rsp+5A0h+var_560]; struct _POINTL *
0x14008cf8b  mov     rcx, r14; struct _SPRITESTATE *
0x14008cf8e  call    ?vSpUpdateLockedScreenAreas@@YAXPEAU_SPRITESTATE@@PEAU_POINTL@@PEAU_RECTL@@PEAU_CLIPOBJ@@H@Z; vSpUpdateLockedScreenAreas(_SPRITESTATE *,_POINTL *,_RECTL *,_CLIPOBJ *,int)
0x14008cf93  jmp     loc_14008CE2D
```
