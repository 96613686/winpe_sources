# vSpUpdateSpriteVisRgn(HDEV__ *,ulong)

- ea: `0x14006e710`
- end: `0x14006ec08`
- name: `?vSpUpdateSpriteVisRgn@@YAXPEAUHDEV__@@K@Z`
- size: `1272`
- prototype: `void __fastcall(HDEV, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400850c0`

## callees

- `0x14006dc00`
- `0x14006e6d0`
- `0x14006e710`
- `0x14006ec10`
- `0x14006fc24`
- `0x14006fd50`
- `0x140084c94`
- `0x1400f6d54`
- `0x14012a770`
- `0x1401a3348`
- `0x1401a3a3c`
- `0x1403099a4`
- `0x14030b3a0`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006e7af`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006e7af`
- `win32kbase!PopThreadGuardedObject` at `0x14006e808`
- `win32kbase!PopThreadGuardedObject` at `0x14006e808`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006e7d1`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006e7d1`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006e95f`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006e97c`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006e95f`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006e97c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14006e841`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14006e841`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14006e887`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14006e887`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14006e8bd`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14006e8bd`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x14006ea1e`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x14006ea1e`
- `win32kbase!??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z` at `0x14006e9f8`
- `win32kbase!??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z` at `0x14006e9f8`
- `win32kbase!??1SPRITELOCK@@QEAA@XZ` at `0x14006ea72`
- `win32kbase!??1SPRITELOCK@@QEAA@XZ` at `0x14006ea72`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14006e9da`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14006e9da`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14006e85b`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14006e85b`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006e7e8`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006e7e8`
- `WIN32K!W32GetSessionState` at `0x14006ea43`
- `WIN32K!W32GetSessionState` at `0x14006ea43`

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
0x14006e710  push    rbp
0x14006e712  push    rbx
0x14006e713  push    rsi
0x14006e714  push    rdi
0x14006e715  push    r12
0x14006e717  push    r13
0x14006e719  push    r14
0x14006e71b  push    r15
0x14006e71d  lea     rbp, [rsp-468h]
0x14006e725  sub     rsp, 568h
0x14006e72c  mov     rax, cs:__security_cookie
0x14006e733  xor     rax, rsp
0x14006e736  mov     [rbp+4A0h+var_50], rax
0x14006e73d  mov     ebx, edx
0x14006e73f  mov     [rsp+5A0h+var_548], rcx
0x14006e744  mov     rsi, rcx
0x14006e747  mov     edi, 144h
0x14006e74c  xor     r12d, r12d
0x14006e74f  lea     rcx, [rbp+4A0h+var_2F0]; void *
0x14006e756  mov     r8d, edi; Size
0x14006e759  mov     [rsp+5A0h+var_568], r12
0x14006e75e  xor     edx, edx; Val
0x14006e760  call    memset_0
0x14006e765  mov     r8d, edi; Size
0x14006e768  lea     rcx, [rbp+4A0h+var_1A0]; void *
0x14006e76f  xor     edx, edx; Val
0x14006e771  call    memset_0
0x14006e776  lea     r14, [rsi+50h]
0x14006e77a  cmp     [r14+8], r12
0x14006e77e  jnz     short loc_14006E7A4
0x14006e780  mov     rcx, [rbp+4A0h+var_50]
0x14006e787  xor     rcx, rsp; StackCookie
0x14006e78a  call    __security_check_cookie
0x14006e78f  add     rsp, 568h
0x14006e796  pop     r15
0x14006e798  pop     r14
0x14006e79a  pop     r13
0x14006e79c  pop     r12
0x14006e79e  pop     rdi
0x14006e79f  pop     rsi
0x14006e7a0  pop     rbx
0x14006e7a1  pop     rbp
0x14006e7a2  retn
0x14006e7a4  mov     r13d, 1
0x14006e7aa  test    bl, 4
0x14006e7ad  jz      short loc_14006E7C6
0x14006e7af  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14006e7b6  nop     dword ptr [rax+rax+00h]
0x14006e7bb  mov     edx, r13d; int
0x14006e7be  mov     rcx, r14; struct _SPRITESTATE *
0x14006e7c1  call    ?vSpComputeNoPresentRegion@@YAXPEAU_SPRITESTATE@@H@Z; vSpComputeNoPresentRegion(_SPRITESTATE *,int)
0x14006e7c6  mov     rdi, [r14+8]
0x14006e7ca  jmp     short loc_14006E818
0x14006e7cc  lea     rcx, [rsp+5A0h+var_570]
0x14006e7d1  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006e7d8  nop     dword ptr [rax+rax+00h]
0x14006e7dd  cmp     [rbp+4A0h+var_510], r12d
0x14006e7e1  jnz     short loc_14006E7F4
0x14006e7e3  lea     rcx, [rsp+5A0h+var_540]
0x14006e7e8  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006e7ef  nop     dword ptr [rax+rax+00h]
0x14006e7f4  mov     rax, [rsp+5A0h+var_540]
0x14006e7f9  test    rax, rax
0x14006e7fc  jz      short loc_14006E803
0x14006e7fe  lock dec word ptr [rax+0Ch]
0x14006e803  lea     rcx, [rsp+5A0h+var_538]
0x14006e808  call    cs:__imp_PopThreadGuardedObject
0x14006e80f  nop     dword ptr [rax+rax+00h]
0x14006e814  mov     rdi, [rdi+18h]
0x14006e818  test    rdi, rdi
0x14006e81b  jz      loc_14006E780
0x14006e821  mov     rdx, [rdi+48h]
0x14006e825  test    rdx, rdx
0x14006e828  jz      short loc_14006E814
0x14006e82a  lea     rbx, [r14+428h]
0x14006e831  xor     r8d, r8d
0x14006e834  mov     rcx, rbx; HRGN *
0x14006e837  call    UserVisrgnFromHwnd
0x14006e83c  lea     rcx, [rsp+5A0h+var_570]
0x14006e841  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14006e848  nop     dword ptr [rax+rax+00h]
0x14006e84d  mov     rdx, [rbx]
0x14006e850  lea     rcx, [rsp+5A0h+var_540]
0x14006e855  xor     r9d, r9d
0x14006e858  xor     r8d, r8d
0x14006e85b  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14006e862  nop     dword ptr [rax+rax+00h]
0x14006e867  cmp     [rsp+5A0h+var_540], r12
0x14006e86c  jz      loc_14006E7CC
0x14006e872  cmp     [rsp+5A0h+var_570], r12
0x14006e877  jz      loc_14006E7CC
0x14006e87d  lea     rdx, [rsp+5A0h+var_540]
0x14006e882  lea     rcx, [rsp+5A0h+var_570]
0x14006e887  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14006e88e  nop     dword ptr [rax+rax+00h]
0x14006e893  test    eax, eax
0x14006e895  jz      loc_14006E7CC
0x14006e89b  mov     eax, [rsi+0A10h]
0x14006e8a1  lea     rdx, [rsp+5A0h+var_568]
0x14006e8a6  neg     eax
0x14006e8a8  lea     rcx, [rsp+5A0h+var_570]
0x14006e8ad  mov     dword ptr [rsp+5A0h+var_568], eax
0x14006e8b1  mov     eax, [rsi+0A14h]
0x14006e8b7  neg     eax
0x14006e8b9  mov     dword ptr [rsp+5A0h+var_568+4], eax
0x14006e8bd  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14006e8c4  nop     dword ptr [rax+rax+00h]
0x14006e8c9  mov     rdx, [rdi+0B8h]
0x14006e8d0  lea     rbx, [rdi+70h]
0x14006e8d4  mov     rsi, [rsp+5A0h+var_570]
0x14006e8d9  mov     qword ptr [rsp+5A0h+var_560.x], rsi
0x14006e8de  test    rdx, rdx
0x14006e8e1  jz      loc_14006EA88
0x14006e8e7  mov     r8d, [rbx]
0x14006e8ea  mov     r9d, [rdi+74h]
0x14006e8ee  mov     ecx, [rdi+68h]
0x14006e8f1  sub     ecx, [rdi+60h]
0x14006e8f4  add     ecx, r8d
0x14006e8f7  mov     [rbp+4A0h+var_440], r8d
0x14006e8fb  mov     [rbp+4A0h+var_438], ecx
0x14006e8fe  lea     r8, [rbp+4A0h+var_440]
0x14006e902  mov     ecx, [rdi+6Ch]
0x14006e905  sub     ecx, [rdi+64h]
0x14006e908  add     ecx, r9d
0x14006e90b  mov     [rbp+4A0h+var_43C], r9d
0x14006e90f  mov     [rbp+4A0h+var_434], ecx
0x14006e912  xor     r9d, r9d
0x14006e915  lea     rcx, [rbp+4A0h+var_430]
0x14006e919  mov     [rbp+4A0h+var_3E0], r12
0x14006e920  mov     [rbp+4A0h+var_3D8], r12d
0x14006e927  mov     [rbp+4A0h+var_3B0], r13d
0x14006e92e  mov     [rbp+4A0h+var_3A0], r12
0x14006e935  mov     [rbp+4A0h+var_3F8], r12
0x14006e93c  mov     [rbp+4A0h+var_340], r12
0x14006e943  mov     [rbp+4A0h+var_338], r12d
0x14006e94a  mov     [rbp+4A0h+var_310], r13d
0x14006e951  mov     [rbp+4A0h+var_300], r12
0x14006e958  mov     [rbp+4A0h+var_358], r12
0x14006e95f  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14006e966  nop     dword ptr [rax+rax+00h]
0x14006e96b  xor     r9d, r9d
0x14006e96e  lea     r8, [rbp+4A0h+var_440]
0x14006e972  mov     rdx, rsi
0x14006e975  lea     rcx, [rbp+4A0h+var_390]
0x14006e97c  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14006e983  nop     dword ptr [rax+rax+00h]
0x14006e988  lea     rcx, [rbp+4A0h+var_38C]; this
0x14006e98f  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14006e994  lea     rcx, [rbp+4A0h+var_42C]; this
0x14006e998  mov     edx, eax
0x14006e99a  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14006e99f  cmp     edx, eax
0x14006e9a1  jnz     loc_14006EA88
0x14006e9a7  mov     cl, [rbp+4A0h+var_41C]
0x14006e9ad  mov     al, [rbp+4A0h+var_37C]
0x14006e9b3  test    cl, cl
0x14006e9b5  jnz     loc_14006EAA7
0x14006e9bb  test    al, al
0x14006e9bd  jnz     loc_14006EAA7
0x14006e9c3  mov     esi, r13d
0x14006e9c6  mov     rcx, rdi; struct SPRITE *
0x14006e9c9  call    ?vSpFreeClipResources@@YAXPEAVSPRITE@@@Z; vSpFreeClipResources(SPRITE *)
0x14006e9ce  mov     rcx, qword ptr [rsp+5A0h+var_560.x]
0x14006e9d3  mov     [rdi+0B8h], rcx
0x14006e9da  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14006e9e1  nop     dword ptr [rax+rax+00h]
0x14006e9e6  mov     rax, [r14]
0x14006e9e9  lea     rdx, [rsp+5A0h+var_558]
0x14006e9ee  lea     rcx, [rsp+5A0h+var_550]
0x14006e9f3  mov     [rsp+5A0h+var_558], rax
0x14006e9f8  call    cs:__imp_??0SPRITELOCK@@QEAA@AEAVPDEVOBJ@@@Z; SPRITELOCK::SPRITELOCK(PDEVOBJ &)
0x14006e9ff  nop     dword ptr [rax+rax+00h]
0x14006ea04  lea     rdx, [rsp+5A0h+var_558]; struct PDEVOBJ *
0x14006ea09  lea     rcx, [rbp+4A0h+var_500]; this
0x14006ea0d  call    ??0SPRITEDDIACCESS@@QEAA@AEAVPDEVOBJ@@@Z; SPRITEDDIACCESS::SPRITEDDIACCESS(PDEVOBJ &)
0x14006ea12  and     dword ptr [rdi], 0FFFFFFFEh
0x14006ea15  lea     rdx, [r14+28h]
0x14006ea19  lea     rcx, [rsp+5A0h+var_570]
0x14006ea1e  call    cs:__imp_?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z; RGNOBJ::bInside(_RECTL *)
0x14006ea25  nop     dword ptr [rax+rax+00h]
0x14006ea2a  cmp     eax, 2
0x14006ea2d  jz      short loc_14006EA32
0x14006ea2f  or      [rdi], r13d
0x14006ea32  xor     r9d, r9d; int
0x14006ea35  xor     r8d, r8d; int
0x14006ea38  mov     rdx, rbx; struct _POINTL *
0x14006ea3b  mov     rcx, rdi; struct SPRITE *
0x14006ea3e  call    ?bSpUpdatePosition@@YAHPEAVSPRITE@@PEAU_POINTL@@HH@Z; bSpUpdatePosition(SPRITE *,_POINTL *,int,int)
0x14006ea43  call    cs:__imp_W32GetSessionState
0x14006ea4a  nop     dword ptr [rax+rax+00h]
0x14006ea4f  mov     rcx, [rax+60h]
0x14006ea53  cmp     [rcx+12D0h], r12
0x14006ea5a  jnz     loc_14006EBD1
0x14006ea60  test    esi, esi
0x14006ea62  jz      short loc_14006EA90
0x14006ea64  lea     rcx, [rbp+4A0h+var_500]; this
0x14006ea68  call    ??1SPRITEDDIACCESS@@QEAA@XZ; SPRITEDDIACCESS::~SPRITEDDIACCESS(void)
0x14006ea6d  lea     rcx, [rsp+5A0h+var_550]
0x14006ea72  call    cs:__imp_??1SPRITELOCK@@QEAA@XZ; SPRITELOCK::~SPRITELOCK(void)
0x14006ea79  nop     dword ptr [rax+rax+00h]
0x14006ea7e  mov     rsi, [rsp+5A0h+var_548]
0x14006ea83  jmp     loc_14006E7DD
0x14006ea88  mov     esi, r12d
0x14006ea8b  jmp     loc_14006E9C6
0x14006ea90  cmp     [r14+410h], r12
0x14006ea97  jnz     loc_14006EBE5
0x14006ea9d  mov     rcx, rdi; struct SPRITE *
0x14006eaa0  call    ?vSpRedrawSprite@@YAXPEAVSPRITE@@@Z; vSpRedrawSprite(SPRITE *)
0x14006eaa5  jmp     short loc_14006EA64
0x14006eaa7  cmp     cl, al
0x14006eaa9  jnz     short loc_14006EA88
0x14006eaab  mov     r9d, 4; unsigned int
0x14006eab1  mov     [rsp+5A0h+var_580], 64h ; 'd'; unsigned int
0x14006eab9  xor     r8d, r8d; unsigned int
0x14006eabc  lea     rcx, [rbp+4A0h+var_430]; this
0x14006eac0  xor     edx, edx; int
0x14006eac2  call    ?cEnumStart@XCLIPOBJ@@QEAAKHKKK@Z; XCLIPOBJ::cEnumStart(int,ulong,ulong,ulong)
0x14006eac7  mov     r9d, 4; unsigned int
0x14006eacd  mov     [rsp+5A0h+var_580], 64h ; 'd'; unsigned int
0x14006ead5  xor     r8d, r8d; unsigned int
0x14006ead8  lea     rcx, [rbp+4A0h+var_390]; this
0x14006eadf  xor     edx, edx; int
0x14006eae1  call    ?cEnumStart@XCLIPOBJ@@QEAAKHKKK@Z; XCLIPOBJ::cEnumStart(int,ulong,ulong,ulong)
0x14006eae6  mov     r15d, r13d
0x14006eae9  mov     [rbp+4A0h+var_2F0], r12d
0x14006eaf0  mov     esi, r12d
0x14006eaf3  mov     [rbp+4A0h+var_1A0], r12d
0x14006eafa  test    r15d, r15d
0x14006eafd  jz      short loc_14006EB20
0x14006eaff  xor     r9d, r9d; unsigned int *
0x14006eb02  lea     r8, [rbp+4A0h+var_2F0]; void *
0x14006eb09  mov     edx, 144h; unsigned int
0x14006eb0e  lea     rcx, [rbp+4A0h+var_430]; this
0x14006eb12  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x14006eb17  mov     esi, [rbp+4A0h+var_2F0]
0x14006eb1d  mov     r15d, eax
0x14006eb20  test    r13d, r13d
0x14006eb23  jz      short loc_14006EB4A
0x14006eb25  xor     r9d, r9d; unsigned int *
0x14006eb28  lea     r8, [rbp+4A0h+var_1A0]; void *
0x14006eb2f  mov     edx, 144h; unsigned int
0x14006eb34  lea     rcx, [rbp+4A0h+var_390]; this
0x14006eb3b  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x14006eb40  mov     r12d, [rbp+4A0h+var_1A0]
0x14006eb47  mov     r13d, eax
0x14006eb4a  cmp     esi, r12d
0x14006eb4d  jz      short loc_14006EB60
0x14006eb4f  xor     r12d, r12d
0x14006eb52  mov     esi, r12d
0x14006eb55  mov     r13d, 1
0x14006eb5b  jmp     loc_14006E9C6
0x14006eb60  xor     r12d, r12d
0x14006eb63  mov     edx, r12d
0x14006eb66  cmp     edx, esi
0x14006eb68  jnb     short loc_14006EBB3
0x14006eb6a  mov     ecx, edx
0x14006eb6c  add     rcx, rcx
0x14006eb6f  mov     eax, [rbp+rcx*8+4A0h+var_2EC]
0x14006eb76  cmp     [rbp+rcx*8+4A0h+var_19C], eax
0x14006eb7d  jnz     short loc_14006EB52
0x14006eb7f  mov     eax, [rbp+rcx*8+4A0h+var_2E8]
0x14006eb86  cmp     [rbp+rcx*8+4A0h+var_198], eax
0x14006eb8d  jnz     short loc_14006EB52
0x14006eb8f  mov     eax, [rbp+rcx*8+4A0h+var_2E4]
0x14006eb96  cmp     [rbp+rcx*8+4A0h+var_194], eax
0x14006eb9d  jnz     short loc_14006EB52
0x14006eb9f  mov     eax, [rbp+rcx*8+4A0h+var_2E0]
0x14006eba6  cmp     [rbp+rcx*8+4A0h+var_190], eax
0x14006ebad  jnz     short loc_14006EB52
0x14006ebaf  inc     edx
0x14006ebb1  jmp     short loc_14006EB66
0x14006ebb3  test    r15d, r15d
0x14006ebb6  jnz     loc_14006EAE9
0x14006ebbc  lea     esi, [r15+1]
0x14006ebc0  test    r13d, r13d
0x14006ebc3  jnz     loc_14006EAE9
0x14006ebc9  mov     r13d, esi
0x14006ebcc  jmp     loc_14006E9C6
0x14006ebd1  lea     rdx, [rdi+50h]; struct _RECTL *
0x14006ebd5  mov     rcx, r14; struct _SPRITESTATE *
0x14006ebd8  mov     r8, rdx; struct _RECTL *
0x14006ebdb  call    ?vSpCheckForWndobjOverlap@@YAXPEAU_SPRITESTATE@@PEAU_RECTL@@1@Z; vSpCheckForWndobjOverlap(_SPRITESTATE *,_RECTL *,_RECTL *)
0x14006ebe0  jmp     loc_14006EA60
0x14006ebe5  lea     r8, [rdi+50h]; struct _RECTL *
0x14006ebe9  mov     qword ptr [rsp+5A0h+var_560.x], r12
0x14006ebee  xor     r9d, r9d; struct _CLIPOBJ *
0x14006ebf1  mov     [rsp+5A0h+var_580], r13d; int
0x14006ebf6  lea     rdx, [rsp+5A0h+var_560]; struct _POINTL *
0x14006ebfb  mov     rcx, r14; struct _SPRITESTATE *
0x14006ebfe  call    ?vSpUpdateLockedScreenAreas@@YAXPEAU_SPRITESTATE@@PEAU_POINTL@@PEAU_RECTL@@PEAU_CLIPOBJ@@H@Z; vSpUpdateLockedScreenAreas(_SPRITESTATE *,_POINTL *,_RECTL *,_CLIPOBJ *,int)
0x14006ec03  jmp     loc_14006EA9D
```
