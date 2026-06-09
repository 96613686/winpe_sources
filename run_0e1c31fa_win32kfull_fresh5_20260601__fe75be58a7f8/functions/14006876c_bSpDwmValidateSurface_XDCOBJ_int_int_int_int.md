# bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)

- ea: `0x14006876c`
- end: `0x140068efd`
- name: `?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z`
- size: `1937`
- prototype: `__int64 __fastcall(struct XDCOBJ *, int, int, int, int)`
- caller_count: `13`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140064ba0`
- `0x1400663c0`
- `0x140069888`
- `0x14006a0c0`
- `0x14006a660`
- `0x14006b380`
- `0x14007be5c`
- `0x1401343b0`
- `0x140135194`
- `0x140135b04`
- `0x140137c54`
- `0x1402177c4`
- `0x14030f788`

## callees

- `0x14006876c`
- `0x14006b9d4`
- `0x14006ec10`
- `0x140080590`
- `0x14008c4c4`
- `0x14008eb28`
- `0x140093570`
- `0x1400dd838`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x140119048`
- `0x14013d844`
- `0x14016ca80`
- `0x140183ad8`
- `0x1401a56fc`
- `0x1401a5830`
- `0x1401b03a4`
- `0x1401ff604`
- `0x14021a74c`
- `0x140303af4`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!KeAreApcsDisabled` at `0x140068864`
- `ntoskrnl!KeAreApcsDisabled` at `0x140068864`
- `ntoskrnl!KeDelayExecutionThread` at `0x140068e32`
- `ntoskrnl!KeDelayExecutionThread` at `0x140068e32`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140068801`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140068801`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068ba3`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068c53`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068d58`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068ec4`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068ba3`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068c53`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068d58`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140068ec4`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140068b60`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140068b60`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140068b0d`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140068b0d`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140068c7e`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140068c9d`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140068c9d`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140068a3e`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140068a3e`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14006894f`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14006894f`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140068896`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140068de2`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140068896`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140068de2`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140068b7d`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140068b7d`
- `win32kbase!RecordCapabilityUsage` at `0x140068831`
- `win32kbase!RecordCapabilityUsage` at `0x140068831`

## pseudocode

```c
__int64 __fastcall bSpDwmValidateSurface(struct XDCOBJ *a1, int a2, int a3, int a4, int a5)
{
  __int64 v5; // rax
  __int64 v7; // r14
  __int64 v8; // r15
  __int64 v9; // r13
  __int64 v10; // rcx
  __int64 CurrentProcessWin32Process; // rax
  unsigned int v12; // esi
  __int64 v13; // rax
  __int64 v14; // r9
  struct REGION *v15; // rax
  __int64 v16; // r12
  __int64 v17; // r11
  __int64 v18; // rax
  __int64 v19; // r11
  __int64 v20; // rcx
  __int64 v21; // r11
  struct _POINTL v22; // rdi
  int v23; // r15d
  __int64 v24; // r13
  __int64 v25; // r14
  __int64 v26; // rax
  LONG x; // ecx
  LONG y; // edx
  LONG v29; // eax
  __int64 v30; // r14
  LONG *v31; // r11
  __int64 v32; // rdx
  LONG v33; // r8d
  int v34; // ecx
  struct _POINTL *v35; // r11
  LONG left; // r13d
  int v38; // esi
  struct _POINTL *v39; // rdx
  int v40; // r15d
  HSURF v41; // r12
  __int64 v42; // r14
  __int64 v43; // rcx
  __int64 (__fastcall *v44)(_QWORD, unsigned __int64 *); // rax
  struct _POINTL v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h]
  int v47; // [rsp+5Ch] [rbp-A4h]
  struct _POINTL v48; // [rsp+60h] [rbp-A0h] BYREF
  struct _POINTL v49[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _POINTL v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  struct _POINTL v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v56[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  _BYTE v58[176]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v59[176]; // [rsp+180h] [rbp+80h] BYREF
  struct tagRECT v60; // [rsp+230h] [rbp+130h] BYREF
  struct tagRECT v61; // [rsp+240h] [rbp+140h] BYREF

  v5 = *(_QWORD *)a1;
  v7 = a4;
  v8 = a3;
  v9 = a2;
  v52 = 0;
  v55 = 0;
  if ( !v5 )
    return 0;
  if ( (*(_DWORD *)(v5 + 36) & 0x200) == 0 )
    return 0;
  if ( !(unsigned int)IsDwmActive() )
    return 0;
  v10 = *(_QWORD *)a1;
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x4001) != 0x4001 || !*(_QWORD *)(v10 + 472) )
    return 0;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v10);
  v12 = 1;
  if ( CurrentProcessWin32Process && *(_QWORD *)CurrentProcessWin32Process )
  {
    if ( (*(_DWORD *)(CurrentProcessWin32Process + 288) & 1) == 0 )
      return 0;
    RecordCapabilityUsage(CurrentProcessWin32Process, 1);
  }
  v13 = *(_QWORD *)a1;
  if ( !*(_QWORD *)(*(_QWORD *)a1 + 496LL) || !*(_DWORD *)(v13 + 488) && !*(_DWORD *)(v13 + 492) || KeAreApcsDisabled() )
    return 0;
  DEVLOCKOBJ::DEVLOCKOBJ(v59, 2);
  if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v59, a1, 0) )
    goto LABEL_63;
  v14 = *(_QWORD *)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 504LL) )
  {
LABEL_64:
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v59);
    return v12;
  }
  if ( !*(_DWORD *)(v14 + 492) )
  {
    v15 = DC::prgnVisSnap(*(DC **)a1);
    if ( !v15 )
      goto LABEL_63;
    v61 = *(struct tagRECT *)((char *)v15 + 52);
    if ( (unsigned int)IsRectEmptyInl(&v61) )
      goto LABEL_63;
  }
  if ( !(_DWORD)v7 )
    goto LABEL_63;
  if ( !a5 )
    goto LABEL_63;
  if ( (unsigned __int64)(v7 + v9 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_63;
  if ( (unsigned __int64)(a5 + v8 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_63;
  v16 = *(_QWORD *)(*(_QWORD *)(v14 + 48) + 24LL);
  DC::QuickInitXform(v14, &v54, 516);
  if ( (*(_DWORD *)(v54 + 32) & 2) == 0 )
    goto LABEL_63;
  v48.x = v9;
  v48.y = v8;
  EXFORMOBJ::bXform((EXFORMOBJ *)&v54, &v48, 1u);
  v17 = *(_QWORD *)a1;
  v18 = *(_DWORD *)(*(_QWORD *)a1 + 40LL) & 1LL;
  v48.x += *(_DWORD *)(*(_QWORD *)a1 + 8 * v18 + 1016);
  v60.top = *(_DWORD *)(v17 + 8 * v18 + 1020) + v48.y;
  v48.y = v60.top;
  v60.right = v48.x + v7;
  v60.left = v48.x;
  v60.bottom = v60.top + a5;
  ERECTL::vOrder((ERECTL *)&v60);
  v20 = *(_QWORD *)(v19 + 496);
  v45 = 0;
  v46 = *(_DWORD *)(v20 + 56);
  v47 = *(_DWORD *)(v20 + 60);
  ERECTL::operator*=(&v60, &v45);
  if ( (unsigned int)IsRectEmptyInl(&v60) )
    goto LABEL_63;
  v22 = 0;
  if ( !*(_DWORD *)(v21 + 492) )
  {
    if ( (*(_DWORD *)(v21 + 36) & 0x4000) != 0 )
      SURFACE::bUnMap(*(SURFACE **)(v21 + 496));
    v23 = 0;
    SEMOBJ<7>::SEMOBJ<7>(&v45, *((_QWORD *)a1 + 2));
    if ( !(unsigned int)IsDwmActive() )
    {
LABEL_51:
      if ( v45 )
        ((void (__fastcall *)(_QWORD, _QWORD))GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>)(
          GreReleaseSemaphoreExclusiveInternal,
          v45);
      if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x4000) != 0
        && (unsigned int)SURFACE::Map(*(_QWORD *)(*(_QWORD *)a1 + 496LL)) == 2 )
      {
        *(_DWORD *)(*(_QWORD *)a1 + 44LL) |= 1u;
LABEL_61:
        if ( v22 )
        {
          v45 = v22;
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v45);
        }
        goto LABEL_63;
      }
      if ( v23 )
        goto LABEL_57;
LABEL_63:
      v12 = 0;
      goto LABEL_64;
    }
    DWMSPRITEREF::DWMSPRITEREF((DWMSPRITEREF *)v56, *(HWND *)(*(_QWORD *)a1 + 472LL));
    v24 = v57;
    if ( v57 )
    {
      v25 = *(_QWORD *)(v57 + 144);
      if ( (*(_DWORD *)(v25 + 252) & 0x80u) == 0
        && *(_QWORD *)(v25 + 184) == ((*(_QWORD *)(*(_QWORD *)a1 + 496LL) + 24LL)
                                    & -(__int64)(*(_QWORD *)(*(_QWORD *)a1 + 496LL) != 0)) )
      {
        if ( *(_QWORD *)(v25 + 80) )
        {
          v53 = *(_QWORD *)(v25 + 80);
          RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v51);
          if ( v53 )
          {
            if ( v51 )
            {
              if ( !(unsigned int)RGNOBJ::bContain((RGNOBJ *)&v53, (struct _RECTL *)&v60) )
              {
                RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v50);
                if ( v50 )
                {
                  v61 = *(struct tagRECT *)(v24 + 56);
                  v49[0].x = v61.left;
                  v49[0].y = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v61, 4));
                  ERECTL::bOffsetSubtract((ERECTL *)&v61, v49, 0);
                  RGNOBJ::vSet((RGNOBJ *)&v51, (const struct _RECTL *const)&v61);
                  if ( RGNOBJ::iCombine((RGNOBJ *)&v50, (struct RGNOBJ *)&v51, (struct RGNOBJ *)&v53, 4) )
                  {
                    v22 = v50;
                    v23 = 1;
                  }
                  else if ( v50 )
                  {
                    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v50);
                  }
                }
              }
            }
          }
          RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v51);
          if ( !v23 )
            goto LABEL_50;
        }
        else
        {
          v23 = 1;
        }
        v26 = *(_QWORD *)(v25 + 184);
        v49[0] = 0;
        if ( v26 )
        {
          x = *(_DWORD *)(v26 + 32);
          y = *(_DWORD *)(v26 + 36);
        }
        else
        {
          y = v49[0].y;
          x = v49[0].x;
        }
        v52.x = *(_DWORD *)(v24 + 56);
        v29 = *(_DWORD *)(v24 + 60);
        *(_QWORD *)&v60.left = 0;
        v60.right = x;
        v60.bottom = y;
        *(_DWORD *)(v25 + 252) |= 0x80u;
        v52.y = v29;
        if ( v22 )
        {
          *(_OWORD *)&v49[0].x = *(_OWORD *)(*(_QWORD *)&v22 + 52LL);
          ERECTL::operator*=(&v60, v49);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v60) )
          {
            v49[0] = v22;
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)v49);
            *(_DWORD *)(v25 + 252) |= 0x80u;
            v23 = 0;
          }
        }
      }
    }
LABEL_50:
    DWMSPRITEREF::~DWMSPRITEREF((DWMSPRITEREF *)v56);
    goto LABEL_51;
  }
LABEL_57:
  v30 = *(_QWORD *)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 492LL) )
  {
    ERECTL::bOffsetAdd((ERECTL *)&v60, (const struct _POINTL *)(v16 + 2576), 0);
  }
  else
  {
    ERECTL::bOffsetAdd((ERECTL *)&v60, &v52, 0);
    v31 = (LONG *)(v16 + 2576);
  }
  v32 = *(_QWORD *)(v16 + 2544);
  v33 = *(_DWORD *)(v16 + 2580);
  v45.x = *v31;
  v46 = *(_DWORD *)(v32 + 56) + v45.x;
  v34 = *(_DWORD *)(v32 + 60);
  v45.y = v33;
  v47 = v33 + v34;
  ERECTL::operator*=(&v60, &v45);
  if ( (unsigned int)IsRectEmptyInl(&v60) )
    goto LABEL_61;
  left = v60.left;
  v38 = 0;
  v49[0].x = v60.top;
  v39 = v35;
  v40 = 8;
  if ( !*(_DWORD *)(v30 + 492) )
    v39 = &v52;
  ERECTL::bOffsetSubtract((ERECTL *)&v60, v39, 0);
  v41 = *(HSURF *)(*(_QWORD *)(v30 + 496) + 32LL);
  DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v59);
  v42 = *((_QWORD *)a1 + 2);
  while ( 1 )
  {
    DEVLOCKOBJ::DEVLOCKOBJ(v58, 2);
    if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v58, a1, 0) )
    {
      DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v58);
      goto LABEL_80;
    }
    v43 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
    if ( v43 )
    {
      v44 = *(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(v43 + 3456);
      if ( v44 )
      {
        v38 = v44(*(_QWORD *)(v43 + 1784), &v55);
        if ( v38 == 258 )
        {
          KeDelayExecutionThread(0, 0, *(PLARGE_INTEGER *)(v42 + 2280));
          --v40;
        }
      }
    }
    else
    {
      v38 = -1073741823;
    }
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v58);
    if ( v38 != 258 )
      break;
    if ( !v40 )
      goto LABEL_80;
  }
  if ( v38 >= 0 )
    return bSpDwmUpdateSurface(0, v55, a1, v41, 1.0, left, v49[0].x, (struct ERECTL *)&v60, *(struct REGION **)&v22);
LABEL_80:
  if ( v22 )
  {
    v45 = v22;
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v45);
  }
  return 0;
}

```

## disassembly

```asm
0x14006876c  mov     [rsp-8+arg_10], rbx
0x140068771  push    rbp
0x140068772  push    rsi
0x140068773  push    rdi
0x140068774  push    r12
0x140068776  push    r13
0x140068778  push    r14
0x14006877a  push    r15
0x14006877c  lea     rbp, [rsp-160h]
0x140068784  sub     rsp, 260h
0x14006878b  mov     rax, cs:__security_cookie
0x140068792  xor     rax, rsp
0x140068795  mov     [rbp+190h+var_40], rax
0x14006879c  mov     rax, [rcx]
0x14006879f  mov     rbx, rcx
0x1400687a2  movsxd  r14, r9d
0x1400687a5  movsxd  r15, r8d
0x1400687a8  movsxd  r13, edx
0x1400687ab  mov     qword ptr [rbp+190h+var_208.x], 0
0x1400687b3  mov     [rbp+190h+var_1F0], 0
0x1400687bb  test    rax, rax
0x1400687be  jz      loc_140068ED0
0x1400687c4  test    dword ptr [rax+24h], 200h
0x1400687cb  jz      loc_140068ED0
0x1400687d1  call    IsDwmActive
0x1400687d6  test    eax, eax
0x1400687d8  jz      loc_140068ED0
0x1400687de  mov     rcx, [rbx]
0x1400687e1  mov     edx, 4001h
0x1400687e6  mov     eax, [rcx+24h]
0x1400687e9  and     eax, edx
0x1400687eb  cmp     eax, edx
0x1400687ed  jnz     loc_140068ED0
0x1400687f3  cmp     qword ptr [rcx+1D8h], 0
0x1400687fb  jz      loc_140068ED0
0x140068801  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140068808  nop     dword ptr [rax+rax+00h]
0x14006880d  mov     esi, 1
0x140068812  test    rax, rax
0x140068815  jz      short loc_14006883D
0x140068817  cmp     qword ptr [rax], 0
0x14006881b  jz      short loc_14006883D
0x14006881d  mov     ecx, [rax+120h]
0x140068823  test    sil, cl
0x140068826  jz      loc_140068ED0
0x14006882c  mov     edx, esi
0x14006882e  mov     rcx, rax
0x140068831  call    cs:__imp_RecordCapabilityUsage
0x140068838  nop     dword ptr [rax+rax+00h]
0x14006883d  mov     rax, [rbx]
0x140068840  cmp     qword ptr [rax+1F0h], 0
0x140068848  jz      loc_140068ED0
0x14006884e  cmp     dword ptr [rax+1E8h], 0
0x140068855  jnz     short loc_140068864
0x140068857  cmp     dword ptr [rax+1ECh], 0
0x14006885e  jz      loc_140068ED0
0x140068864  call    cs:__imp_KeAreApcsDisabled
0x14006886b  nop     dword ptr [rax+rax+00h]
0x140068870  test    al, al
0x140068872  jnz     loc_140068ED0
0x140068878  mov     edx, 2
0x14006887d  lea     rcx, [rbp+190h+var_110]
0x140068884  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x140068889  xor     r8d, r8d
0x14006888c  lea     rcx, [rbp+190h+var_110]
0x140068893  mov     rdx, rbx
0x140068896  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14006889d  nop     dword ptr [rax+rax+00h]
0x1400688a2  test    eax, eax
0x1400688a4  jz      loc_140068D64
0x1400688aa  mov     r9, [rbx]
0x1400688ad  cmp     qword ptr [r9+1F8h], 0
0x1400688b5  jnz     loc_140068D66
0x1400688bb  cmp     dword ptr [r9+1ECh], 0
0x1400688c3  jnz     short loc_1400688F6
0x1400688c5  mov     rcx, r9; this
0x1400688c8  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x1400688cd  test    rax, rax
0x1400688d0  jz      loc_140068D64
0x1400688d6  movups  xmm0, xmmword ptr [rax+34h]
0x1400688da  lea     rcx, [rbp+190h+var_50]; struct tagRECT *
0x1400688e1  movdqu  xmmword ptr [rbp+190h+var_50.left], xmm0
0x1400688e9  call    ?IsRectEmptyInl@@YAHPEBUtagRECT@@@Z; IsRectEmptyInl(tagRECT const *)
0x1400688ee  test    eax, eax
0x1400688f0  jnz     loc_140068D64
0x1400688f6  test    r14d, r14d
0x1400688f9  jz      loc_140068D64
0x1400688ff  movsxd  rdi, [rbp+190h+arg_20]
0x140068906  test    edi, edi
0x140068908  jz      loc_140068D64
0x14006890e  mov     r8d, 80000000h
0x140068914  mov     r10d, 0FFFFFFFFh
0x14006891a  lea     rcx, [r8+r13]
0x14006891e  add     rcx, r14
0x140068921  cmp     rcx, r10
0x140068924  ja      loc_140068D64
0x14006892a  lea     rdx, [r8+r15]
0x14006892e  add     rdx, rdi
0x140068931  cmp     rdx, r10
0x140068934  ja      loc_140068D64
0x14006893a  mov     rax, [r9+30h]
0x14006893e  lea     rdx, [rbp+190h+var_1F8]
0x140068942  mov     r8d, 204h
0x140068948  mov     rcx, r9
0x14006894b  mov     r12, [rax+18h]
0x14006894f  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140068956  nop     dword ptr [rax+rax+00h]
0x14006895b  mov     rax, [rbp+190h+var_1F8]
0x14006895f  mov     ecx, [rax+20h]
0x140068962  test    cl, 2
0x140068965  jz      loc_140068D64
0x14006896b  mov     r8, rsi; unsigned __int64
0x14006896e  mov     [rsp+290h+var_230.x], r13d
0x140068973  lea     rdx, [rsp+290h+var_230]; struct _POINTL *
0x140068978  mov     [rsp+290h+var_230.y], r15d
0x14006897d  lea     rcx, [rbp+190h+var_1F8]; this
0x140068981  call    ?bXform@EXFORMOBJ@@QEBA_NPEAU_POINTL@@_K@Z; EXFORMOBJ::bXform(_POINTL *,unsigned __int64)
0x140068986  mov     r11, [rbx]
0x140068989  mov     edx, [rsp+290h+var_230.x]
0x14006898d  mov     ecx, [rsp+290h+var_230.y]
0x140068991  mov     eax, [r11+28h]
0x140068995  and     rax, rsi
0x140068998  add     edx, [r11+rax*8+3F8h]
0x1400689a0  mov     [rsp+290h+var_230.x], edx
0x1400689a4  add     ecx, [r11+rax*8+3FCh]
0x1400689ac  mov     [rbp+190h+var_60.top], ecx
0x1400689b2  lea     eax, [rdx+r14]
0x1400689b6  mov     [rsp+290h+var_230.y], ecx
0x1400689ba  mov     [rbp+190h+var_60.right], eax
0x1400689c0  lea     eax, [rcx+rdi]
0x1400689c3  mov     [rbp+190h+var_60.left], edx
0x1400689c9  lea     rcx, [rbp+190h+var_60]; this
0x1400689d0  mov     [rbp+190h+var_60.bottom], eax
0x1400689d6  call    ?vOrder@ERECTL@@QEAAXXZ; ERECTL::vOrder(void)
0x1400689db  mov     rcx, [r11+1F0h]
0x1400689e2  lea     rdx, [rsp+290h+var_240]
0x1400689e7  mov     [rsp+290h+var_240], 0
0x1400689f0  mov     eax, [rcx+38h]
0x1400689f3  mov     [rsp+290h+var_238], eax
0x1400689f7  mov     eax, [rcx+3Ch]
0x1400689fa  lea     rcx, [rbp+190h+var_60]
0x140068a01  mov     [rsp+290h+var_234], eax
0x140068a05  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x140068a0a  lea     rcx, [rbp+190h+var_60]; struct tagRECT *
0x140068a11  call    ?IsRectEmptyInl@@YAHPEBUtagRECT@@@Z; IsRectEmptyInl(tagRECT const *)
0x140068a16  test    eax, eax
0x140068a18  jnz     loc_140068D64
0x140068a1e  xor     edi, edi
0x140068a20  cmp     [r11+1ECh], edi
0x140068a27  jnz     loc_140068CC2
0x140068a2d  test    dword ptr [r11+24h], 4000h
0x140068a35  jz      short loc_140068A4A
0x140068a37  mov     rcx, [r11+1F0h]
0x140068a3e  call    cs:__imp_?bUnMap@SURFACE@@QEAAHXZ; SURFACE::bUnMap(void)
0x140068a45  nop     dword ptr [rax+rax+00h]
0x140068a4a  mov     rdx, [rbx+10h]
0x140068a4e  lea     rcx, [rsp+290h+var_240]
0x140068a53  xor     r15d, r15d
0x140068a56  call    ??0?$SEMOBJ@$06@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJ<7>::SEMOBJ<7>(Gre::Base::SESSION_GLOBALS &)
0x140068a5b  call    IsDwmActive
0x140068a60  test    eax, eax
0x140068a62  jz      loc_140068C74
0x140068a68  mov     rdx, [rbx]
0x140068a6b  lea     rcx, [rbp+190h+var_1E8]; this
0x140068a6f  mov     rdx, [rdx+1D8h]; HWND
0x140068a76  call    ??0DWMSPRITEREF@@QEAA@PEAUHWND__@@@Z; DWMSPRITEREF::DWMSPRITEREF(HWND__ *)
0x140068a7b  mov     r13, [rbp+190h+var_1C8]
0x140068a7f  test    r13, r13
0x140068a82  jz      loc_140068C6B
0x140068a88  mov     r14, [r13+90h]
0x140068a8f  mov     eax, [r14+0FCh]
0x140068a96  test    al, al
0x140068a98  js      loc_140068C6B
0x140068a9e  mov     rax, [rbx]
0x140068aa1  mov     rdx, [rax+1F0h]
0x140068aa8  lea     rcx, [rdx+18h]
0x140068aac  neg     rdx
0x140068aaf  sbb     rax, rax
0x140068ab2  and     rax, rcx
0x140068ab5  cmp     [r14+0B8h], rax
0x140068abc  jnz     loc_140068C6B
0x140068ac2  mov     rax, [r14+50h]
0x140068ac6  test    rax, rax
0x140068ac9  jz      loc_140068BC3
0x140068acf  lea     rcx, [rbp+190h+var_210]; this
0x140068ad3  mov     [rbp+190h+var_200], rax
0x140068ad7  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140068adc  cmp     [rbp+190h+var_200], rdi
0x140068ae0  jz      loc_140068BAF
0x140068ae6  cmp     [rbp+190h+var_210], rdi
0x140068aea  jz      loc_140068BAF
0x140068af0  lea     rdx, [rbp+190h+var_60]; struct _RECTL *
0x140068af7  lea     rcx, [rbp+190h+var_200]; this
0x140068afb  call    ?bContain@RGNOBJ@@QEAAHAEAU_RECTL@@@Z; RGNOBJ::bContain(_RECTL &)
0x140068b00  test    eax, eax
0x140068b02  jnz     loc_140068BAF
0x140068b08  lea     rcx, [rsp+290h+var_218]
0x140068b0d  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140068b14  nop     dword ptr [rax+rax+00h]
0x140068b19  cmp     [rsp+290h+var_218], rdi
0x140068b1e  jz      loc_140068BAF
0x140068b24  movups  xmm0, xmmword ptr [r13+38h]
0x140068b29  xor     r8d, r8d; int
0x140068b2c  lea     rdx, [rsp+290h+var_228]; struct _POINTL *
0x140068b31  lea     rcx, [rbp+190h+var_50]; this
0x140068b38  movups  xmmword ptr [rbp+190h+var_50.left], xmm0
0x140068b3f  movss   [rsp+290h+var_228.x], xmm0
0x140068b45  psrldq  xmm0, 4
0x140068b4a  movd    [rsp+290h+var_228.y], xmm0
0x140068b50  call    ?bOffsetSubtract@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetSubtract(_POINTL const &,int)
0x140068b55  lea     rdx, [rbp+190h+var_50]
0x140068b5c  lea     rcx, [rbp+190h+var_210]
0x140068b60  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140068b67  nop     dword ptr [rax+rax+00h]
0x140068b6c  lea     r9d, [r15+4]
0x140068b70  lea     r8, [rbp+190h+var_200]
0x140068b74  lea     rdx, [rbp+190h+var_210]
0x140068b78  lea     rcx, [rsp+290h+var_218]
0x140068b7d  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x140068b84  nop     dword ptr [rax+rax+00h]
0x140068b89  test    eax, eax
0x140068b8b  jz      short loc_140068B97
0x140068b8d  mov     rdi, [rsp+290h+var_218]
0x140068b92  mov     r15d, esi
0x140068b95  jmp     short loc_140068BAF
0x140068b97  cmp     [rsp+290h+var_218], rdi
0x140068b9c  jz      short loc_140068BAF
0x140068b9e  lea     rcx, [rsp+290h+var_218]
0x140068ba3  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140068baa  nop     dword ptr [rax+rax+00h]
0x140068baf  lea     rcx, [rbp+190h+var_210]; this
0x140068bb3  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x140068bb8  test    r15d, r15d
0x140068bbb  jz      loc_140068C6B
0x140068bc1  jmp     short loc_140068BC6
0x140068bc3  mov     r15d, esi
0x140068bc6  mov     rax, [r14+0B8h]
0x140068bcd  mov     qword ptr [rsp+290h+var_228.x], 0
0x140068bd6  test    rax, rax
0x140068bd9  jz      short loc_140068BE3
0x140068bdb  mov     ecx, [rax+20h]
0x140068bde  mov     edx, [rax+24h]
0x140068be1  jmp     short loc_140068BEB
0x140068be3  mov     edx, [rsp+290h+var_228.y]
0x140068be7  mov     ecx, [rsp+290h+var_228.x]
0x140068beb  mov     eax, [r13+38h]
0x140068bef  mov     [rbp+190h+var_208.x], eax
0x140068bf2  mov     eax, [r13+3Ch]
0x140068bf6  mov     qword ptr [rbp+190h+var_60.left], 0
0x140068c01  mov     [rbp+190h+var_60.right], ecx
0x140068c07  mov     [rbp+190h+var_60.bottom], edx
0x140068c0d  bts     dword ptr [r14+0FCh], 7
0x140068c16  mov     [rbp+190h+var_208.y], eax
0x140068c19  test    rdi, rdi
0x140068c1c  jz      short loc_140068C6B
0x140068c1e  movups  xmm0, xmmword ptr [rdi+34h]
0x140068c22  lea     rdx, [rsp+290h+var_228]
0x140068c27  lea     rcx, [rbp+190h+var_60]
0x140068c2e  movdqu  xmmword ptr [rsp+290h+var_228.x], xmm0
0x140068c34  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x140068c39  lea     rcx, [rbp+190h+var_60]; this
0x140068c40  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x140068c45  test    eax, eax
0x140068c47  jz      short loc_140068C6B
0x140068c49  lea     rcx, [rsp+290h+var_228]
0x140068c4e  mov     qword ptr [rsp+290h+var_228.x], rdi
0x140068c53  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140068c5a  nop     dword ptr [rax+rax+00h]
0x140068c5f  bts     dword ptr [r14+0FCh], 7
0x140068c68  xor     r15d, r15d
0x140068c6b  lea     rcx, [rbp+190h+var_1E8]; this
0x140068c6f  call    ??1DWMSPRITEREF@@QEAA@XZ; DWMSPRITEREF::~DWMSPRITEREF(void)
0x140068c74  mov     rdx, [rsp+290h+var_240]
0x140068c79  test    rdx, rdx
0x140068c7c  jz      short loc_140068C8A
0x140068c7e  mov     rcx, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x140068c85  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140068c8a  mov     rcx, [rbx]
0x140068c8d  test    dword ptr [rcx+24h], 4000h
0x140068c94  jz      short loc_140068CB9
0x140068c96  mov     rcx, [rcx+1F0h]
0x140068c9d  call    cs:__imp_?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ; SURFACE::Map(void)
0x140068ca4  nop     dword ptr [rax+rax+00h]
0x140068ca9  cmp     eax, 2
0x140068cac  jnz     short loc_140068CB9
0x140068cae  mov     rax, [rbx]
0x140068cb1  or      [rax+2Ch], esi
0x140068cb4  jmp     loc_140068D49
0x140068cb9  test    r15d, r15d
0x140068cbc  jz      loc_140068D64
0x140068cc2  mov     r14, [rbx]
0x140068cc5  lea     rcx, [rbp+190h+var_60]; this
0x140068ccc  xor     r8d, r8d; int
0x140068ccf  cmp     [r14+1ECh], r8d
0x140068cd6  jz      short loc_140068CEA
0x140068cd8  lea     r11, [r12+0A10h]
0x140068ce0  mov     rdx, r11; struct _POINTL *
0x140068ce3  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x140068ce8  jmp     short loc_140068CFB
0x140068cea  lea     rdx, [rbp+190h+var_208]; struct _POINTL *
  ... truncated ...
```
