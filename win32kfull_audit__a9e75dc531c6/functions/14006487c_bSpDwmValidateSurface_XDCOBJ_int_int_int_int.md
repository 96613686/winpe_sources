# bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)

- ea: `0x14006487c`
- end: `0x140064ff7`
- name: `?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z`
- size: `1915`
- prototype: `__int64 __fastcall(struct XDCOBJ *, int, int, int, int)`
- caller_count: `13`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140058784`
- `0x140060b1c`
- `0x140062340`
- `0x140065f80`
- `0x14006651c`
- `0x140066cd0`
- `0x14006d0d0`
- `0x14008826c`
- `0x140088bd4`
- `0x14008ad24`
- `0x14011178c`
- `0x140217410`
- `0x1403113e8`

## callees

- `0x140010a8c`
- `0x1400151b8`
- `0x1400411e8`
- `0x14005d010`
- `0x14006487c`
- `0x140066c94`
- `0x140067410`
- `0x14006bd2c`
- `0x140077348`
- `0x140079b44`
- `0x14008cfa0`
- `0x1400a9b80`
- `0x14011ee44`
- `0x1401233a0`
- `0x1401234d4`
- `0x140163094`
- `0x14018f558`
- `0x1401ab8c4`
- `0x140200004`
- `0x140219e20`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `ntoskrnl!KeAreApcsDisabled` at `0x140064974`
- `ntoskrnl!KeAreApcsDisabled` at `0x140064974`
- `ntoskrnl!KeDelayExecutionThread` at `0x140064f2c`
- `ntoskrnl!KeDelayExecutionThread` at `0x140064f2c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140064911`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140064911`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064ca8`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064d58`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064e5d`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064fbe`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064ca8`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064d58`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064e5d`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140064fbe`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140064c65`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140064c65`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140064c12`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140064c12`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140064d83`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140064da2`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140064da2`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140064b43`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140064b43`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140064a54`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140064a54`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14006499b`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140064edc`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14006499b`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140064edc`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140064c82`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140064c82`
- `win32kbase!RecordCapabilityUsage` at `0x140064941`
- `win32kbase!RecordCapabilityUsage` at `0x140064941`

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
  HSEMAPHORE v22; // rdi
  int v23; // r15d
  __int64 v24; // rcx
  __int64 v25; // r13
  __int64 v26; // r14
  __int64 v27; // rax
  LONG x; // ecx
  LONG y; // edx
  LONG v30; // eax
  __int64 v31; // r14
  _DWORD *v32; // r11
  __int64 v33; // rdx
  int v34; // r8d
  int v35; // ecx
  struct _POINTL *v36; // r11
  LONG left; // r13d
  int v39; // esi
  struct _POINTL *v40; // rdx
  int v41; // r15d
  HSURF v42; // r12
  __int64 v43; // r14
  __int64 v44; // rcx
  __int64 (__fastcall *v45)(_QWORD, unsigned __int64 *); // rax
  HSEMAPHORE v46; // [rsp+50h] [rbp-B0h] BYREF
  int v47; // [rsp+58h] [rbp-A8h]
  int v48; // [rsp+5Ch] [rbp-A4h]
  struct _POINTL v49; // [rsp+60h] [rbp-A0h] BYREF
  struct _POINTL v50[2]; // [rsp+68h] [rbp-98h] BYREF
  HSEMAPHORE v51; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  struct _POINTL v53; // [rsp+88h] [rbp-78h] BYREF
  __int64 v54; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v56; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v57[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h]
  HDC v59[20]; // [rsp+D0h] [rbp-30h] BYREF
  HDC v60[20]; // [rsp+170h] [rbp+70h] BYREF
  struct tagRECT v61; // [rsp+210h] [rbp+110h] BYREF
  struct tagRECT v62; // [rsp+220h] [rbp+120h] BYREF

  v5 = *(_QWORD *)a1;
  v7 = a4;
  v8 = a3;
  v9 = a2;
  v53 = 0;
  v56 = 0;
  if ( !v5 )
    return 0;
  if ( (*(_DWORD *)(v5 + 36) & 0x200) == 0 )
    return 0;
  if ( !(unsigned int)IsDwmActive(a1) )
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
  DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v60);
  if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v60, a1, 0) )
    goto LABEL_63;
  v14 = *(_QWORD *)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 504LL) )
  {
LABEL_64:
    DEVLOCKOBJ::~DEVLOCKOBJ(v60);
    return v12;
  }
  if ( !*(_DWORD *)(v14 + 492) )
  {
    v15 = DC::prgnVisSnap(*(DC **)a1);
    if ( !v15 )
      goto LABEL_63;
    v62 = *(struct tagRECT *)((char *)v15 + 52);
    if ( IsRectEmptyInl(&v62) )
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
  DC::QuickInitXform(v14, &v55, 516);
  if ( (*(_DWORD *)(v55 + 32) & 2) == 0 )
    goto LABEL_63;
  v49.x = v9;
  v49.y = v8;
  EXFORMOBJ::bXform((EXFORMOBJ *)&v55, &v49, 1u);
  v17 = *(_QWORD *)a1;
  v18 = *(_DWORD *)(*(_QWORD *)a1 + 40LL) & 1LL;
  v49.x += *(_DWORD *)(*(_QWORD *)a1 + 8 * v18 + 1016);
  v61.top = *(_DWORD *)(v17 + 8 * v18 + 1020) + v49.y;
  v49.y = v61.top;
  v61.right = v49.x + v7;
  v61.left = v49.x;
  v61.bottom = v61.top + a5;
  ERECTL::vOrder((ERECTL *)&v61);
  v20 = *(_QWORD *)(v19 + 496);
  v46 = 0;
  v47 = *(_DWORD *)(v20 + 56);
  v48 = *(_DWORD *)(v20 + 60);
  ERECTL::operator*=(&v61, &v46);
  if ( IsRectEmptyInl(&v61) )
    goto LABEL_63;
  v22 = 0;
  if ( !*(_DWORD *)(v21 + 492) )
  {
    if ( (*(_DWORD *)(v21 + 36) & 0x4000) != 0 )
      SURFACE::bUnMap(*(SURFACE **)(v21 + 496));
    v23 = 0;
    SEMOBJ<7>::SEMOBJ<7>(&v46, *((_QWORD **)a1 + 2));
    if ( !(unsigned int)IsDwmActive(v24) )
    {
LABEL_51:
      if ( v46 )
        GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal);
      if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x4000) != 0
        && (unsigned int)SURFACE::Map(*(_QWORD *)(*(_QWORD *)a1 + 496LL)) == 2 )
      {
        *(_DWORD *)(*(_QWORD *)a1 + 44LL) |= 1u;
LABEL_61:
        if ( v22 )
        {
          v46 = v22;
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v46);
        }
        goto LABEL_63;
      }
      if ( v23 )
        goto LABEL_57;
LABEL_63:
      v12 = 0;
      goto LABEL_64;
    }
    DWMSPRITEREF::DWMSPRITEREF((DWMSPRITEREF *)v57, *(HWND *)(*(_QWORD *)a1 + 472LL));
    v25 = v58;
    if ( v58 )
    {
      v26 = *(_QWORD *)(v58 + 144);
      if ( (*(_DWORD *)(v26 + 252) & 0x80u) == 0
        && *(_QWORD *)(v26 + 184) == ((*(_QWORD *)(*(_QWORD *)a1 + 496LL) + 24LL)
                                    & -(__int64)(*(_QWORD *)(*(_QWORD *)a1 + 496LL) != 0)) )
      {
        if ( *(_QWORD *)(v26 + 80) )
        {
          v54 = *(_QWORD *)(v26 + 80);
          RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v52);
          if ( v54 )
          {
            if ( v52 )
            {
              if ( !(unsigned int)RGNOBJ::bContain((RGNOBJ *)&v54, (struct _RECTL *)&v61) )
              {
                RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v51);
                if ( v51 )
                {
                  v62 = *(struct tagRECT *)(v25 + 56);
                  v50[0].x = v62.left;
                  v50[0].y = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v62, 4));
                  ERECTL::bOffsetSubtract((ERECTL *)&v62, v50, 0);
                  RGNOBJ::vSet((RGNOBJ *)&v52, (const struct _RECTL *const)&v62);
                  if ( RGNOBJ::iCombine((RGNOBJ *)&v51, (struct RGNOBJ *)&v52, (struct RGNOBJ *)&v54, 4) )
                  {
                    v22 = v51;
                    v23 = 1;
                  }
                  else if ( v51 )
                  {
                    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v51);
                  }
                }
              }
            }
          }
          RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v52);
          if ( !v23 )
            goto LABEL_50;
        }
        else
        {
          v23 = 1;
        }
        v27 = *(_QWORD *)(v26 + 184);
        v50[0] = 0;
        if ( v27 )
        {
          x = *(_DWORD *)(v27 + 32);
          y = *(_DWORD *)(v27 + 36);
        }
        else
        {
          y = v50[0].y;
          x = v50[0].x;
        }
        v53.x = *(_DWORD *)(v25 + 56);
        v30 = *(_DWORD *)(v25 + 60);
        *(_QWORD *)&v61.left = 0;
        v61.right = x;
        v61.bottom = y;
        *(_DWORD *)(v26 + 252) |= 0x80u;
        v53.y = v30;
        if ( v22 )
        {
          *(_OWORD *)&v50[0].x = *(_OWORD *)(v22 + 13);
          ERECTL::operator*=(&v61, v50);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v61) )
          {
            v50[0] = (struct _POINTL)v22;
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)v50);
            *(_DWORD *)(v26 + 252) |= 0x80u;
            v23 = 0;
          }
        }
      }
    }
LABEL_50:
    DWMSPRITEREF::~DWMSPRITEREF((DWMSPRITEREF *)v57);
    goto LABEL_51;
  }
LABEL_57:
  v31 = *(_QWORD *)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 492LL) )
  {
    ERECTL::bOffsetAdd((ERECTL *)&v61, (const struct _POINTL *)(v16 + 2576), 0);
  }
  else
  {
    ERECTL::bOffsetAdd((ERECTL *)&v61, &v53, 0);
    v32 = (_DWORD *)(v16 + 2576);
  }
  v33 = *(_QWORD *)(v16 + 2544);
  v34 = *(_DWORD *)(v16 + 2580);
  LODWORD(v46) = *v32;
  v47 = *(_DWORD *)(v33 + 56) + (_DWORD)v46;
  v35 = *(_DWORD *)(v33 + 60);
  HIDWORD(v46) = v34;
  v48 = v34 + v35;
  ERECTL::operator*=(&v61, &v46);
  if ( IsRectEmptyInl(&v61) )
    goto LABEL_61;
  left = v61.left;
  v39 = 0;
  v50[0].x = v61.top;
  v40 = v36;
  v41 = 8;
  if ( !*(_DWORD *)(v31 + 492) )
    v40 = &v53;
  ERECTL::bOffsetSubtract((ERECTL *)&v61, v40, 0);
  v42 = *(HSURF *)(*(_QWORD *)(v31 + 496) + 32LL);
  DEVLOCKOBJ::~DEVLOCKOBJ(v60);
  v43 = *((_QWORD *)a1 + 2);
  while ( 1 )
  {
    DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v59);
    if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v59, a1, 0) )
    {
      DEVLOCKOBJ::~DEVLOCKOBJ(v59);
      goto LABEL_80;
    }
    v44 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
    if ( v44 )
    {
      v45 = *(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(v44 + 3456);
      if ( v45 )
      {
        v39 = v45(*(_QWORD *)(v44 + 1784), &v56);
        if ( v39 == 258 )
        {
          KeDelayExecutionThread(0, 0, *(PLARGE_INTEGER *)(v43 + 2280));
          --v41;
        }
      }
    }
    else
    {
      v39 = -1073741823;
    }
    DEVLOCKOBJ::~DEVLOCKOBJ(v59);
    if ( v39 != 258 )
      break;
    if ( !v41 )
      goto LABEL_80;
  }
  if ( v39 >= 0 )
    return bSpDwmUpdateSurface(0, v56, a1, v42, 1.0, left, v50[0].x, (struct ERECTL *)&v61, (struct REGION *)v22);
LABEL_80:
  if ( v22 )
  {
    v46 = v22;
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v46);
  }
  return 0;
}

```

## disassembly

```asm
0x14006487c  mov     [rsp-8+arg_10], rbx
0x140064881  push    rbp
0x140064882  push    rsi
0x140064883  push    rdi
0x140064884  push    r12
0x140064886  push    r13
0x140064888  push    r14
0x14006488a  push    r15
0x14006488c  lea     rbp, [rsp-140h]
0x140064894  sub     rsp, 240h
0x14006489b  mov     rax, cs:__security_cookie
0x1400648a2  xor     rax, rsp
0x1400648a5  mov     [rbp+170h+var_40], rax
0x1400648ac  mov     rax, [rcx]
0x1400648af  mov     rbx, rcx
0x1400648b2  movsxd  r14, r9d
0x1400648b5  movsxd  r15, r8d
0x1400648b8  movsxd  r13, edx
0x1400648bb  mov     qword ptr [rbp+170h+var_1E8.x], 0
0x1400648c3  mov     [rbp+170h+var_1D0], 0
0x1400648cb  test    rax, rax
0x1400648ce  jz      loc_140064FCA
0x1400648d4  test    dword ptr [rax+24h], 200h
0x1400648db  jz      loc_140064FCA
0x1400648e1  call    IsDwmActive
0x1400648e6  test    eax, eax
0x1400648e8  jz      loc_140064FCA
0x1400648ee  mov     rcx, [rbx]
0x1400648f1  mov     edx, 4001h
0x1400648f6  mov     eax, [rcx+24h]
0x1400648f9  and     eax, edx
0x1400648fb  cmp     eax, edx
0x1400648fd  jnz     loc_140064FCA
0x140064903  cmp     qword ptr [rcx+1D8h], 0
0x14006490b  jz      loc_140064FCA
0x140064911  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140064918  nop     dword ptr [rax+rax+00h]
0x14006491d  mov     esi, 1
0x140064922  test    rax, rax
0x140064925  jz      short loc_14006494D
0x140064927  cmp     qword ptr [rax], 0
0x14006492b  jz      short loc_14006494D
0x14006492d  mov     ecx, [rax+120h]
0x140064933  test    sil, cl
0x140064936  jz      loc_140064FCA
0x14006493c  mov     edx, esi
0x14006493e  mov     rcx, rax
0x140064941  call    cs:__imp_RecordCapabilityUsage
0x140064948  nop     dword ptr [rax+rax+00h]
0x14006494d  mov     rax, [rbx]
0x140064950  cmp     qword ptr [rax+1F0h], 0
0x140064958  jz      loc_140064FCA
0x14006495e  cmp     dword ptr [rax+1E8h], 0
0x140064965  jnz     short loc_140064974
0x140064967  cmp     dword ptr [rax+1ECh], 0
0x14006496e  jz      loc_140064FCA
0x140064974  call    cs:__imp_KeAreApcsDisabled
0x14006497b  nop     dword ptr [rax+rax+00h]
0x140064980  test    al, al
0x140064982  jnz     loc_140064FCA
0x140064988  lea     rcx, [rbp+170h+var_100]; this
0x14006498c  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x140064991  xor     r8d, r8d
0x140064994  lea     rcx, [rbp+170h+var_100]
0x140064998  mov     rdx, rbx
0x14006499b  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x1400649a2  nop     dword ptr [rax+rax+00h]
0x1400649a7  test    eax, eax
0x1400649a9  jz      loc_140064E69
0x1400649af  mov     r9, [rbx]
0x1400649b2  cmp     qword ptr [r9+1F8h], 0
0x1400649ba  jnz     loc_140064E6B
0x1400649c0  cmp     dword ptr [r9+1ECh], 0
0x1400649c8  jnz     short loc_1400649FB
0x1400649ca  mov     rcx, r9; this
0x1400649cd  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x1400649d2  test    rax, rax
0x1400649d5  jz      loc_140064E69
0x1400649db  movups  xmm0, xmmword ptr [rax+34h]
0x1400649df  lea     rcx, [rbp+170h+var_50]; struct tagRECT *
0x1400649e6  movdqu  xmmword ptr [rbp+170h+var_50.left], xmm0
0x1400649ee  call    ?IsRectEmptyInl@@YAHPEBUtagRECT@@@Z; IsRectEmptyInl(tagRECT const *)
0x1400649f3  test    eax, eax
0x1400649f5  jnz     loc_140064E69
0x1400649fb  test    r14d, r14d
0x1400649fe  jz      loc_140064E69
0x140064a04  movsxd  rdi, [rbp+170h+arg_20]
0x140064a0b  test    edi, edi
0x140064a0d  jz      loc_140064E69
0x140064a13  mov     r8d, 80000000h
0x140064a19  mov     r10d, 0FFFFFFFFh
0x140064a1f  lea     rcx, [r8+r13]
0x140064a23  add     rcx, r14
0x140064a26  cmp     rcx, r10
0x140064a29  ja      loc_140064E69
0x140064a2f  lea     rdx, [r8+r15]
0x140064a33  add     rdx, rdi
0x140064a36  cmp     rdx, r10
0x140064a39  ja      loc_140064E69
0x140064a3f  mov     rax, [r9+30h]
0x140064a43  lea     rdx, [rbp+170h+var_1D8]
0x140064a47  mov     r8d, 204h
0x140064a4d  mov     rcx, r9
0x140064a50  mov     r12, [rax+18h]
0x140064a54  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140064a5b  nop     dword ptr [rax+rax+00h]
0x140064a60  mov     rax, [rbp+170h+var_1D8]
0x140064a64  mov     ecx, [rax+20h]
0x140064a67  test    cl, 2
0x140064a6a  jz      loc_140064E69
0x140064a70  mov     r8, rsi; unsigned __int64
0x140064a73  mov     [rsp+270h+var_210.x], r13d
0x140064a78  lea     rdx, [rsp+270h+var_210]; struct _POINTL *
0x140064a7d  mov     [rsp+270h+var_210.y], r15d
0x140064a82  lea     rcx, [rbp+170h+var_1D8]; this
0x140064a86  call    ?bXform@EXFORMOBJ@@QEBA_NPEAU_POINTL@@_K@Z; EXFORMOBJ::bXform(_POINTL *,unsigned __int64)
0x140064a8b  mov     r11, [rbx]
0x140064a8e  mov     edx, [rsp+270h+var_210.x]
0x140064a92  mov     ecx, [rsp+270h+var_210.y]
0x140064a96  mov     eax, [r11+28h]
0x140064a9a  and     rax, rsi
0x140064a9d  add     edx, [r11+rax*8+3F8h]
0x140064aa5  mov     [rsp+270h+var_210.x], edx
0x140064aa9  add     ecx, [r11+rax*8+3FCh]
0x140064ab1  mov     [rbp+170h+var_60.top], ecx
0x140064ab7  lea     eax, [rdx+r14]
0x140064abb  mov     [rsp+270h+var_210.y], ecx
0x140064abf  mov     [rbp+170h+var_60.right], eax
0x140064ac5  lea     eax, [rcx+rdi]
0x140064ac8  mov     [rbp+170h+var_60.left], edx
0x140064ace  lea     rcx, [rbp+170h+var_60]; this
0x140064ad5  mov     [rbp+170h+var_60.bottom], eax
0x140064adb  call    ?vOrder@ERECTL@@QEAAXXZ; ERECTL::vOrder(void)
0x140064ae0  mov     rcx, [r11+1F0h]
0x140064ae7  lea     rdx, [rsp+270h+var_220]
0x140064aec  mov     [rsp+270h+var_220], 0
0x140064af5  mov     eax, [rcx+38h]
0x140064af8  mov     [rsp+270h+var_218], eax
0x140064afc  mov     eax, [rcx+3Ch]
0x140064aff  lea     rcx, [rbp+170h+var_60]
0x140064b06  mov     [rsp+270h+var_214], eax
0x140064b0a  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x140064b0f  lea     rcx, [rbp+170h+var_60]; struct tagRECT *
0x140064b16  call    ?IsRectEmptyInl@@YAHPEBUtagRECT@@@Z; IsRectEmptyInl(tagRECT const *)
0x140064b1b  test    eax, eax
0x140064b1d  jnz     loc_140064E69
0x140064b23  xor     edi, edi
0x140064b25  cmp     [r11+1ECh], edi
0x140064b2c  jnz     loc_140064DC7
0x140064b32  test    dword ptr [r11+24h], 4000h
0x140064b3a  jz      short loc_140064B4F
0x140064b3c  mov     rcx, [r11+1F0h]
0x140064b43  call    cs:__imp_?bUnMap@SURFACE@@QEAAHXZ; SURFACE::bUnMap(void)
0x140064b4a  nop     dword ptr [rax+rax+00h]
0x140064b4f  mov     rdx, [rbx+10h]
0x140064b53  lea     rcx, [rsp+270h+var_220]
0x140064b58  xor     r15d, r15d
0x140064b5b  call    ??0?$SEMOBJ@$06@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJ<7>::SEMOBJ<7>(Gre::Base::SESSION_GLOBALS &)
0x140064b60  call    IsDwmActive
0x140064b65  test    eax, eax
0x140064b67  jz      loc_140064D79
0x140064b6d  mov     rdx, [rbx]
0x140064b70  lea     rcx, [rbp+170h+var_1C8]; this
0x140064b74  mov     rdx, [rdx+1D8h]; HWND
0x140064b7b  call    ??0DWMSPRITEREF@@QEAA@PEAUHWND__@@@Z; DWMSPRITEREF::DWMSPRITEREF(HWND__ *)
0x140064b80  mov     r13, [rbp+170h+var_1A8]
0x140064b84  test    r13, r13
0x140064b87  jz      loc_140064D70
0x140064b8d  mov     r14, [r13+90h]
0x140064b94  mov     eax, [r14+0FCh]
0x140064b9b  test    al, al
0x140064b9d  js      loc_140064D70
0x140064ba3  mov     rax, [rbx]
0x140064ba6  mov     rdx, [rax+1F0h]
0x140064bad  lea     rcx, [rdx+18h]
0x140064bb1  neg     rdx
0x140064bb4  sbb     rax, rax
0x140064bb7  and     rax, rcx
0x140064bba  cmp     [r14+0B8h], rax
0x140064bc1  jnz     loc_140064D70
0x140064bc7  mov     rax, [r14+50h]
0x140064bcb  test    rax, rax
0x140064bce  jz      loc_140064CC8
0x140064bd4  lea     rcx, [rbp+170h+var_1F0]; this
0x140064bd8  mov     [rbp+170h+var_1E0], rax
0x140064bdc  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140064be1  cmp     [rbp+170h+var_1E0], rdi
0x140064be5  jz      loc_140064CB4
0x140064beb  cmp     [rbp+170h+var_1F0], rdi
0x140064bef  jz      loc_140064CB4
0x140064bf5  lea     rdx, [rbp+170h+var_60]; struct _RECTL *
0x140064bfc  lea     rcx, [rbp+170h+var_1E0]; this
0x140064c00  call    ?bContain@RGNOBJ@@QEAAHAEAU_RECTL@@@Z; RGNOBJ::bContain(_RECTL &)
0x140064c05  test    eax, eax
0x140064c07  jnz     loc_140064CB4
0x140064c0d  lea     rcx, [rsp+270h+var_1F8]
0x140064c12  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140064c19  nop     dword ptr [rax+rax+00h]
0x140064c1e  cmp     [rsp+270h+var_1F8], rdi
0x140064c23  jz      loc_140064CB4
0x140064c29  movups  xmm0, xmmword ptr [r13+38h]
0x140064c2e  xor     r8d, r8d; int
0x140064c31  lea     rdx, [rsp+270h+var_208]; struct _POINTL *
0x140064c36  lea     rcx, [rbp+170h+var_50]; this
0x140064c3d  movups  xmmword ptr [rbp+170h+var_50.left], xmm0
0x140064c44  movss   [rsp+270h+var_208.x], xmm0
0x140064c4a  psrldq  xmm0, 4
0x140064c4f  movd    [rsp+270h+var_208.y], xmm0
0x140064c55  call    ?bOffsetSubtract@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetSubtract(_POINTL const &,int)
0x140064c5a  lea     rdx, [rbp+170h+var_50]
0x140064c61  lea     rcx, [rbp+170h+var_1F0]
0x140064c65  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140064c6c  nop     dword ptr [rax+rax+00h]
0x140064c71  lea     r9d, [r15+4]
0x140064c75  lea     r8, [rbp+170h+var_1E0]
0x140064c79  lea     rdx, [rbp+170h+var_1F0]
0x140064c7d  lea     rcx, [rsp+270h+var_1F8]
0x140064c82  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x140064c89  nop     dword ptr [rax+rax+00h]
0x140064c8e  test    eax, eax
0x140064c90  jz      short loc_140064C9C
0x140064c92  mov     rdi, [rsp+270h+var_1F8]
0x140064c97  mov     r15d, esi
0x140064c9a  jmp     short loc_140064CB4
0x140064c9c  cmp     [rsp+270h+var_1F8], rdi
0x140064ca1  jz      short loc_140064CB4
0x140064ca3  lea     rcx, [rsp+270h+var_1F8]
0x140064ca8  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140064caf  nop     dword ptr [rax+rax+00h]
0x140064cb4  lea     rcx, [rbp+170h+var_1F0]; this
0x140064cb8  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x140064cbd  test    r15d, r15d
0x140064cc0  jz      loc_140064D70
0x140064cc6  jmp     short loc_140064CCB
0x140064cc8  mov     r15d, esi
0x140064ccb  mov     rax, [r14+0B8h]
0x140064cd2  mov     qword ptr [rsp+270h+var_208.x], 0
0x140064cdb  test    rax, rax
0x140064cde  jz      short loc_140064CE8
0x140064ce0  mov     ecx, [rax+20h]
0x140064ce3  mov     edx, [rax+24h]
0x140064ce6  jmp     short loc_140064CF0
0x140064ce8  mov     edx, [rsp+270h+var_208.y]
0x140064cec  mov     ecx, [rsp+270h+var_208.x]
0x140064cf0  mov     eax, [r13+38h]
0x140064cf4  mov     [rbp+170h+var_1E8.x], eax
0x140064cf7  mov     eax, [r13+3Ch]
0x140064cfb  mov     qword ptr [rbp+170h+var_60.left], 0
0x140064d06  mov     [rbp+170h+var_60.right], ecx
0x140064d0c  mov     [rbp+170h+var_60.bottom], edx
0x140064d12  bts     dword ptr [r14+0FCh], 7
0x140064d1b  mov     [rbp+170h+var_1E8.y], eax
0x140064d1e  test    rdi, rdi
0x140064d21  jz      short loc_140064D70
0x140064d23  movups  xmm0, xmmword ptr [rdi+34h]
0x140064d27  lea     rdx, [rsp+270h+var_208]
0x140064d2c  lea     rcx, [rbp+170h+var_60]
0x140064d33  movdqu  xmmword ptr [rsp+270h+var_208.x], xmm0
0x140064d39  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x140064d3e  lea     rcx, [rbp+170h+var_60]; this
0x140064d45  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x140064d4a  test    eax, eax
0x140064d4c  jz      short loc_140064D70
0x140064d4e  lea     rcx, [rsp+270h+var_208]
0x140064d53  mov     qword ptr [rsp+270h+var_208.x], rdi
0x140064d58  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140064d5f  nop     dword ptr [rax+rax+00h]
0x140064d64  bts     dword ptr [r14+0FCh], 7
0x140064d6d  xor     r15d, r15d
0x140064d70  lea     rcx, [rbp+170h+var_1C8]; this
0x140064d74  call    ??1DWMSPRITEREF@@QEAA@XZ; DWMSPRITEREF::~DWMSPRITEREF(void)
0x140064d79  mov     rdx, [rsp+270h+var_220]
0x140064d7e  test    rdx, rdx
0x140064d81  jz      short loc_140064D8F
0x140064d83  mov     rcx, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x140064d8a  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140064d8f  mov     rcx, [rbx]
0x140064d92  test    dword ptr [rcx+24h], 4000h
0x140064d99  jz      short loc_140064DBE
0x140064d9b  mov     rcx, [rcx+1F0h]
0x140064da2  call    cs:__imp_?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ; SURFACE::Map(void)
0x140064da9  nop     dword ptr [rax+rax+00h]
0x140064dae  cmp     eax, 2
0x140064db1  jnz     short loc_140064DBE
0x140064db3  mov     rax, [rbx]
0x140064db6  or      [rax+2Ch], esi
0x140064db9  jmp     loc_140064E4E
0x140064dbe  test    r15d, r15d
0x140064dc1  jz      loc_140064E69
0x140064dc7  mov     r14, [rbx]
0x140064dca  lea     rcx, [rbp+170h+var_60]; this
0x140064dd1  xor     r8d, r8d; int
0x140064dd4  cmp     [r14+1ECh], r8d
0x140064ddb  jz      short loc_140064DEF
0x140064ddd  lea     r11, [r12+0A10h]
0x140064de5  mov     rdx, r11; struct _POINTL *
0x140064de8  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x140064ded  jmp     short loc_140064E00
0x140064def  lea     rdx, [rbp+170h+var_1E8]; struct _POINTL *
0x140064df3  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
  ... truncated ...
```
