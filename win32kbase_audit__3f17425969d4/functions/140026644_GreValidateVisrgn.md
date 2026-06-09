# GreValidateVisrgn

- ea: `0x140026644`
- end: `0x140026b87`
- name: `GreValidateVisrgn`
- size: `1347`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023440`
- `0x14002a870`
- `0x140036190`
- `0x140038210`

## callees

- `0x140026644`
- `0x140026c40`
- `0x140026cc8`
- `0x140031190`
- `0x140031520`
- `0x1400317e0`
- `0x140032300`
- `0x14003405c`
- `0x14003d28c`
- `0x14006f818`
- `0x14007a030`
- `0x140111520`
- `0x1401262ac`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002675f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002675f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026774`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026774`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400266b1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400267eb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400266b1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400267eb`
- `WIN32K!W32GetSessionState` at `0x14002667b`
- `WIN32K!W32GetSessionState` at `0x1400268b2`
- `WIN32K!W32GetSessionState` at `0x140026907`
- `WIN32K!W32GetSessionState` at `0x140026a23`
- `WIN32K!W32GetSessionState` at `0x14002667b`
- `WIN32K!W32GetSessionState` at `0x1400268b2`
- `WIN32K!W32GetSessionState` at `0x140026907`
- `WIN32K!W32GetSessionState` at `0x140026a23`

## pseudocode

```c
void __fastcall GreValidateVisrgn(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  char v11; // di
  DC *v12; // rax
  DC *v13; // rdx
  int v14; // eax
  int v15; // ecx
  unsigned int v16; // eax
  DC *v17; // r15
  struct _GRETHREAD *v18; // rax
  unsigned __int64 v19; // rcx
  struct _GRETHREAD *v20; // rbx
  __int64 v21; // rdx
  DC *v22; // rbx
  __int64 v23; // r14
  _DWORD *v24; // rsi
  __int64 *v25; // rax
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v29; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r9
  __int64 v34; // r10
  __int64 v35; // rax
  int v36; // eax
  int v37; // r11d
  bool v38; // zf
  __int64 v39; // rax
  struct _GRETHREAD *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 SessionState; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  int v48; // r14d
  LONG v49; // ebx
  __int64 v50; // rax
  bool v51; // cc
  LONG v52; // r10d
  __int64 v53; // rax
  int v54; // r8d
  int v55; // eax
  __int128 v56; // [rsp+20h] [rbp-79h] BYREF
  __int128 v57; // [rsp+30h] [rbp-69h]
  __int64 v58; // [rsp+40h] [rbp-59h]
  DC *v59; // [rsp+50h] [rbp-49h] BYREF
  int v60; // [rsp+58h] [rbp-41h]
  __int64 v61; // [rsp+60h] [rbp-39h]
  __int64 v62; // [rsp+68h] [rbp-31h]
  __int128 v63; // [rsp+70h] [rbp-29h] BYREF
  __int128 v64; // [rsp+80h] [rbp-19h]
  __int64 v65; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v66[16]; // [rsp+98h] [rbp-1h] BYREF
  struct _RECTL v67; // [rsp+A8h] [rbp+Fh] BYREF

  v4 = a2;
  v59 = 0;
  v60 = 0;
  v61 = *(_QWORD *)(W32GetSessionState(a1, a2, a3, a4) + 88);
  v62 = 0;
  v59 = 0;
  v60 = 0;
  v63 = 0;
  v64 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v61);
  if ( CurrentThreadWin32Thread )
    v8 = *CurrentThreadWin32Thread;
  else
    v8 = 0;
  v9 = (v8 + 8) & -(__int64)(v8 != 0);
  *(_QWORD *)&v64 = &v59;
  *((_QWORD *)&v64 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v9 )
  {
    v10 = *(_QWORD *)(((v8 + 8) & -(__int64)(v8 != 0)) + 0x58);
    if ( *(_QWORD *)(v10 + 8) != v9 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v63 = *(_QWORD *)(v9 + 88);
    *((_QWORD *)&v63 + 1) = v9 + 88;
    *(_QWORD *)(v10 + 8) = &v63;
    *(_QWORD *)(v9 + 88) = &v63;
  }
  else
  {
    *((_QWORD *)&v63 + 1) = &v63;
    *(_QWORD *)&v63 = &v63;
  }
  v11 = 1;
  LOBYTE(v7) = 1;
  v12 = (DC *)HmgShareLock(v61, a1, v7, 1);
  v59 = v12;
  v13 = v12;
  if ( v12 )
  {
    v14 = *((_DWORD *)v12 + 9);
    v15 = v14 | 0x100000;
    v16 = v14 & 0xFFEFFFFF;
    if ( !v4 )
      v15 = v16;
    *((_DWORD *)v13 + 9) = v15;
    v17 = v59;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx((char *)v17 + 1112, 0);
    GrepAcquireLockValidate<37>();
    v18 = GreGetCurrentThreadCrossSessionCheck();
    v20 = v18;
    if ( v18 )
    {
      v21 = *(_QWORD *)v18;
      if ( (*(_QWORD *)v18 & 0xFFFFFFC000000000uLL) != 0 && (v21 & 0x4000000000LL) == 0 )
      {
        v19 = 0;
        v54 = 38;
        do
        {
          v55 = v19;
          if ( ((1LL << v19) & 0xFFFFFFDFFFFFFFFFuLL & v21) == 0 )
            v55 = v54;
          ++v19;
          v54 = v55;
        }
        while ( v19 < 0x40 );
        if ( v55 > 38 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v21);
      }
      *(_QWORD *)v20 |= 0x4000000000uLL;
    }
    v22 = v59;
    if ( (*((_DWORD *)v59 + 9) & 0x100000) == 0
      || (v23 = *((_QWORD *)v59 + 6)) == 0
      || (v24 = (_DWORD *)*((_QWORD *)v59 + 142)) == 0 )
    {
LABEL_33:
      v40 = GreGetCurrentThreadCrossSessionCheck();
      if ( v40 )
        *(_QWORD *)v40 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v17 + 1112));
      if ( !v11 )
      {
        DC::AcquireDcVisRgnExclusive(v59);
        v65 = *((_QWORD *)v59 + 142);
        if ( v65 )
          RGNOBJ::vSet((RGNOBJ *)&v65, &v67);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(v66);
      }
      if ( v59 )
      {
        SessionState = W32GetSessionState(v42, v41, v43, v44);
        HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), v59);
        v59 = 0;
      }
      v46 = v63;
      if ( *(__int128 **)(v63 + 8) == &v63 )
      {
        v47 = *((_QWORD *)&v63 + 1);
        if ( **((__int128 ***)&v63 + 1) == &v63 )
        {
          **((_QWORD **)&v63 + 1) = v63;
          *(_QWORD *)(v46 + 8) = v47;
          return;
        }
      }
LABEL_5:
      __fastfail(3u);
    }
    v56 = 0;
    v57 = 0;
    v25 = (__int64 *)PsGetCurrentThreadWin32Thread(v19);
    if ( v25 )
      v27 = *v25;
    else
      v27 = 0;
    v28 = v27 + 8;
    v29 = -v27;
    v30 = v28 & -(__int64)(v29 != 0);
    *(_QWORD *)&v57 = &v56;
    *((_QWORD *)&v57 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v30 )
    {
      v31 = (_QWORD *)(v30 + 88);
      v32 = *(_QWORD *)(v30 + 88);
      if ( *(_QWORD *)(v32 + 8) != v30 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v56 = *(_QWORD *)(v30 + 88);
      v30 = (__int64)&v56;
      *((_QWORD *)&v56 + 1) = v31;
      *(_QWORD *)(v32 + 8) = &v56;
      v29 = (unsigned __int64)&v56;
      *v31 = &v56;
    }
    else
    {
      *((_QWORD *)&v56 + 1) = &v56;
      *(_QWORD *)&v56 = &v56;
    }
    v33 = 0;
    v38 = (*((_DWORD *)v22 + 9) & 0x40000) == 0;
    v58 = 0;
    if ( v38 )
    {
      v34 = *((_QWORD *)v22 + 62);
    }
    else
    {
      v30 = *((_QWORD *)v22 + 268);
      if ( v30 )
      {
        SURFREF::vLock((SURFREF *)&v56, (HSURF)v30);
        v33 = v58;
        v34 = v58;
        v35 = v58;
LABEL_24:
        if ( !v34 )
        {
          v38 = v35 == 0;
          goto LABEL_30;
        }
        if ( (*(_DWORD *)(v23 + 40) & 0x20000) != 0 && *(int *)(v34 + 144) < 0
          || (v36 = *((_DWORD *)v22 + 9), (v36 & 0x1000) != 0) && (v36 & 0x4000) == 0
          || (v37 = v24[13], v26 = (unsigned int)v24[15], v37 == (_DWORD)v26)
          || (v29 = (unsigned int)v24[14], v30 = (unsigned int)v24[16], (_DWORD)v29 == (_DWORD)v30)
          || v37 == 0x7FFFFFFF && (_DWORD)v30 == 0x80000000 && (_DWORD)v29 == 0x7FFFFFFF && (_DWORD)v26 == 0x80000000 )
        {
LABEL_29:
          v38 = v33 == 0;
LABEL_30:
          if ( !v38 )
          {
            v39 = W32GetSessionState(v29, v30, v26, v33);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v39 + 88), v58);
          }
          PopThreadGuardedObject(&v56);
          goto LABEL_33;
        }
        v48 = v24[13];
        v49 = v24[14];
        v50 = *(_QWORD *)(((*(_DWORD *)(v34 + 148) & 0x800) != 0 ? 0x284 : 0) + v34 + 56);
        if ( v37 >= (int)v26 )
        {
          if ( v37 > (int)v26 )
          {
            v48 = v24[15];
            v26 = (unsigned int)v37;
          }
          v51 = (int)v29 <= (int)v30;
        }
        else
        {
          v51 = (int)v29 <= (int)v30;
          if ( (int)v29 < (int)v30 )
          {
            if ( v37 >= 0 && (int)v50 >= (int)v26 && (v29 & 0x80000000) == 0LL && SHIDWORD(v50) >= (int)v30 )
              goto LABEL_29;
            goto LABEL_56;
          }
        }
        if ( !v51 )
        {
          v49 = v24[16];
          v30 = (unsigned int)v29;
        }
LABEL_56:
        v52 = 0;
        if ( v48 >= 0 )
          v52 = v48;
        if ( v49 < 0 )
          v49 = 0;
        if ( (int)v50 < (int)v26 )
          v26 = (unsigned int)v50;
        if ( SHIDWORD(v50) < (int)v30 )
          v30 = HIDWORD(v50);
        if ( (int)v26 < v52 )
        {
          v52 = v26;
        }
        else if ( (int)v30 < v49 )
        {
          v49 = v30;
        }
        v67.left = v52;
        v67.top = v49;
        v67.right = v26;
        v67.bottom = v30;
        if ( v33 )
        {
          v53 = W32GetSessionState(0, v30, v26, v33);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v53 + 88), v58);
        }
        PopThreadGuardedObject(&v56);
        v11 = 0;
        goto LABEL_33;
      }
      v34 = *(_QWORD *)(v23 + 2544);
    }
    v35 = 0;
    goto LABEL_24;
  }
  DCOBJA::~DCOBJA((DCOBJA *)&v59);
}

```

## disassembly

```asm
0x140026644  push    rbp
0x140026646  push    rbx
0x140026647  push    rsi
0x140026648  push    rdi
0x140026649  push    r14
0x14002664b  push    r15
0x14002664d  lea     rbp, [rsp-2Fh]
0x140026652  sub     rsp, 0C8h
0x140026659  mov     rax, cs:__security_cookie
0x140026660  xor     rax, rsp
0x140026663  mov     [rbp+57h+var_38], rax
0x140026667  mov     esi, edx
0x140026669  mov     [rbp+57h+var_A0], 0
0x140026671  mov     rbx, rcx
0x140026674  mov     [rbp+57h+var_98], 0
0x14002667b  call    cs:__imp_W32GetSessionState
0x140026682  nop     dword ptr [rax+rax+00h]
0x140026687  xorps   xmm0, xmm0
0x14002668a  mov     rcx, [rax+58h]
0x14002668e  mov     [rbp+57h+var_90], rcx
0x140026692  mov     [rbp+57h+var_88], 0
0x14002669a  mov     [rbp+57h+var_A0], 0
0x1400266a2  mov     [rbp+57h+var_98], 0
0x1400266a9  movups  [rbp+57h+var_80], xmm0
0x1400266ad  movups  [rbp+57h+var_70], xmm0
0x1400266b1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400266b8  nop     dword ptr [rax+rax+00h]
0x1400266bd  test    rax, rax
0x1400266c0  jz      loc_140026A88
0x1400266c6  mov     rcx, [rax]
0x1400266c9  lea     rax, [rcx+8]
0x1400266cd  neg     rcx
0x1400266d0  sbb     rdx, rdx
0x1400266d3  and     rdx, rax
0x1400266d6  lea     rax, [rbp+57h+var_A0]
0x1400266da  mov     qword ptr [rbp+57h+var_70], rax
0x1400266de  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x1400266e5  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400266e9  jz      loc_140026AAE
0x1400266ef  lea     rax, [rdx+58h]
0x1400266f3  mov     rcx, [rax]
0x1400266f6  cmp     [rcx+8], rax
0x1400266fa  jz      short loc_140026703
0x1400266fc  mov     ecx, 3
0x140026701  int     29h; Win8: RtlFailFast(ecx)
0x140026703  mov     qword ptr [rbp+57h+var_80], rcx
0x140026707  lea     rdx, [rbp+57h+var_80]
0x14002670b  mov     qword ptr [rbp+57h+var_80+8], rax
0x14002670f  mov     [rcx+8], rdx
0x140026713  lea     rcx, [rbp+57h+var_80]
0x140026717  mov     [rax], rcx
0x14002671a  mov     rcx, [rbp+57h+var_90]
0x14002671e  mov     edi, 1
0x140026723  mov     r9d, edi
0x140026726  mov     r8b, dil
0x140026729  mov     rdx, rbx
0x14002672c  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140026731  mov     [rbp+57h+var_A0], rax
0x140026735  mov     rdx, rax
0x140026738  test    rax, rax
0x14002673b  jz      loc_14002696F
0x140026741  mov     ecx, [rax+24h]
0x140026744  mov     r14d, 100000h
0x14002674a  mov     eax, ecx
0x14002674c  or      ecx, r14d
0x14002674f  btr     eax, 14h
0x140026753  test    esi, esi
0x140026755  cmovz   ecx, eax
0x140026758  mov     [rdx+24h], ecx
0x14002675b  mov     r15, [rbp+57h+var_A0]
0x14002675f  call    cs:__imp_KeEnterCriticalRegion
0x140026766  nop     dword ptr [rax+rax+00h]
0x14002676b  xor     edx, edx
0x14002676d  lea     rcx, [r15+458h]
0x140026774  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002677b  nop     dword ptr [rax+rax+00h]
0x140026780  call    ??$GrepAcquireLockValidate@$0CF@@@YAXXZ; GrepAcquireLockValidate<37>(void)
0x140026785  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14002678a  mov     rbx, rax
0x14002678d  test    rax, rax
0x140026790  jz      short loc_1400267B5
0x140026792  mov     rdx, [rax]
0x140026795  mov     rsi, 4000000000h
0x14002679f  mov     rax, 0FFFFFFC000000000h
0x1400267a9  test    rax, rdx
0x1400267ac  jnz     loc_140026B1F
0x1400267b2  or      [rbx], rsi
0x1400267b5  mov     rbx, [rbp+57h+var_A0]
0x1400267b9  test    [rbx+24h], r14d
0x1400267bd  jz      loc_1400268D4
0x1400267c3  mov     r14, [rbx+30h]
0x1400267c7  test    r14, r14
0x1400267ca  jz      loc_1400268D4
0x1400267d0  mov     rsi, [rbx+470h]
0x1400267d7  test    rsi, rsi
0x1400267da  jz      loc_1400268D4
0x1400267e0  xorps   xmm0, xmm0
0x1400267e3  movups  [rbp+57h+var_D0], xmm0
0x1400267e7  movups  [rbp+57h+var_C0], xmm0
0x1400267eb  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400267f2  nop     dword ptr [rax+rax+00h]
0x1400267f7  test    rax, rax
0x1400267fa  jz      loc_140026A8F
0x140026800  mov     rcx, [rax]
0x140026803  lea     rax, [rcx+8]
0x140026807  neg     rcx
0x14002680a  sbb     rdx, rdx
0x14002680d  and     rdx, rax
0x140026810  lea     rax, [rbp+57h+var_D0]
0x140026814  mov     qword ptr [rbp+57h+var_C0], rax
0x140026818  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14002681f  mov     qword ptr [rbp+57h+var_C0+8], rax
0x140026823  jz      loc_140026ADB
0x140026829  lea     rax, [rdx+58h]
0x14002682d  mov     rcx, [rax]
0x140026830  cmp     [rcx+8], rax
0x140026834  jnz     loc_1400266FC
0x14002683a  mov     qword ptr [rbp+57h+var_D0], rcx
0x14002683e  lea     rdx, [rbp+57h+var_D0]
0x140026842  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140026846  mov     [rcx+8], rdx
0x14002684a  lea     rcx, [rbp+57h+var_D0]
0x14002684e  mov     [rax], rcx
0x140026851  xor     r9d, r9d
0x140026854  test    dword ptr [rbx+24h], 40000h
0x14002685b  mov     [rbp+57h+var_B0], r9
0x14002685f  jnz     loc_140026A96
0x140026865  mov     r10, [rbx+1F0h]
0x14002686c  xor     eax, eax
0x14002686e  test    r10, r10
0x140026871  jz      loc_14002697A
0x140026877  test    dword ptr [r14+28h], 20000h
0x14002687f  jnz     loc_140026A4D
0x140026885  mov     eax, [rbx+24h]
0x140026888  bt      eax, 0Ch
0x14002688c  jb      loc_140026B69
0x140026892  mov     r11d, [rsi+34h]
0x140026896  mov     r8d, [rsi+3Ch]
0x14002689a  cmp     r11d, r8d
0x14002689d  jz      short loc_1400268AD
0x14002689f  mov     ecx, [rsi+38h]
0x1400268a2  mov     edx, [rsi+40h]
0x1400268a5  cmp     ecx, edx
0x1400268a7  jnz     loc_140026982
0x1400268ad  test    r9, r9
0x1400268b0  jz      short loc_1400268CB
0x1400268b2  call    cs:__imp_W32GetSessionState
0x1400268b9  nop     dword ptr [rax+rax+00h]
0x1400268be  mov     rdx, [rbp+57h+var_B0]
0x1400268c2  mov     rcx, [rax+58h]
0x1400268c6  call    HmgDecrementShareReferenceCount
0x1400268cb  lea     rcx, [rbp+57h+var_D0]
0x1400268cf  call    PopThreadGuardedObject
0x1400268d4  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400268d9  test    rax, rax
0x1400268dc  jz      short loc_1400268EB
0x1400268de  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x1400268e8  and     [rax], rcx
0x1400268eb  lea     rcx, [r15+458h]; this
0x1400268f2  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x1400268f7  test    dil, dil
0x1400268fa  jz      loc_140026AF0
0x140026900  cmp     [rbp+57h+var_A0], 0
0x140026905  jz      short loc_140026928
0x140026907  call    cs:__imp_W32GetSessionState
0x14002690e  nop     dword ptr [rax+rax+00h]
0x140026913  mov     rdx, [rbp+57h+var_A0]
0x140026917  mov     rcx, [rax+58h]
0x14002691b  call    HmgDecrementShareReferenceCount
0x140026920  mov     [rbp+57h+var_A0], 0
0x140026928  mov     rax, qword ptr [rbp+57h+var_80]
0x14002692c  lea     rcx, [rbp+57h+var_80]
0x140026930  cmp     [rax+8], rcx
0x140026934  jnz     loc_1400266FC
0x14002693a  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x14002693e  lea     rdx, [rbp+57h+var_80]
0x140026942  cmp     [rcx], rdx
0x140026945  jnz     loc_1400266FC
0x14002694b  mov     [rcx], rax
0x14002694e  mov     [rax+8], rcx
0x140026952  mov     rcx, [rbp+57h+var_38]
0x140026956  xor     rcx, rsp; StackCookie
0x140026959  call    __security_check_cookie
0x14002695e  add     rsp, 0C8h
0x140026965  pop     r15
0x140026967  pop     r14
0x140026969  pop     rdi
0x14002696a  pop     rsi
0x14002696b  pop     rbx
0x14002696c  pop     rbp
0x14002696d  retn
0x14002696f  lea     rcx, [rbp+57h+var_A0]; this
0x140026973  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x140026978  jmp     short loc_140026952
0x14002697a  test    rax, rax
0x14002697d  jmp     loc_1400268B0
0x140026982  mov     eax, 7FFFFFFFh
0x140026987  cmp     r11d, eax
0x14002698a  jz      loc_140026A65
0x140026990  mov     eax, [r10+94h]
0x140026997  mov     r14d, r11d
0x14002699a  and     eax, 800h
0x14002699f  mov     ebx, ecx
0x1400269a1  neg     eax
0x1400269a3  sbb     rax, rax
0x1400269a6  and     eax, 284h
0x1400269ab  mov     rax, [rax+r10+38h]
0x1400269b0  mov     rsi, rax
0x1400269b3  shr     rsi, 20h
0x1400269b7  cmp     r11d, r8d
0x1400269ba  jge     short loc_1400269D8
0x1400269bc  cmp     ecx, edx
0x1400269be  jge     short loc_1400269E2
0x1400269c0  test    r11d, r11d
0x1400269c3  js      short loc_1400269E8
0x1400269c5  cmp     eax, r8d
0x1400269c8  jl      short loc_1400269E8
0x1400269ca  test    ecx, ecx
0x1400269cc  js      short loc_1400269E8
0x1400269ce  cmp     esi, edx
0x1400269d0  jge     loc_1400268AD
0x1400269d6  jmp     short loc_1400269E8
0x1400269d8  jle     short loc_1400269E0
0x1400269da  mov     r14d, r8d
0x1400269dd  mov     r8d, r11d
0x1400269e0  cmp     ecx, edx
0x1400269e2  jle     short loc_1400269E8
0x1400269e4  mov     ebx, edx
0x1400269e6  mov     edx, ecx
0x1400269e8  xor     r10d, r10d
0x1400269eb  test    r14d, r14d
0x1400269ee  cmovns  r10d, r14d
0x1400269f2  xor     ecx, ecx
0x1400269f4  test    ebx, ebx
0x1400269f6  cmovs   ebx, ecx
0x1400269f9  cmp     eax, r8d
0x1400269fc  cmovl   r8d, eax
0x140026a00  cmp     esi, edx
0x140026a02  cmovl   edx, esi
0x140026a05  cmp     r8d, r10d
0x140026a08  jl      short loc_140026A60
0x140026a0a  cmp     edx, ebx
0x140026a0c  jge     short loc_140026A10
0x140026a0e  mov     ebx, edx
0x140026a10  mov     [rbp+57h+var_48.left], r10d
0x140026a14  mov     [rbp+57h+var_48.top], ebx
0x140026a17  mov     [rbp+57h+var_48.right], r8d
0x140026a1b  mov     [rbp+57h+var_48.bottom], edx
0x140026a1e  test    r9, r9
0x140026a21  jz      short loc_140026A3C
0x140026a23  call    cs:__imp_W32GetSessionState
0x140026a2a  nop     dword ptr [rax+rax+00h]
0x140026a2f  mov     rdx, [rbp+57h+var_B0]
0x140026a33  mov     rcx, [rax+58h]
0x140026a37  call    HmgDecrementShareReferenceCount
0x140026a3c  lea     rcx, [rbp+57h+var_D0]
0x140026a40  call    PopThreadGuardedObject
0x140026a45  xor     dil, dil
0x140026a48  jmp     loc_1400268D4
0x140026a4d  cmp     dword ptr [r10+90h], 0
0x140026a55  jge     loc_140026885
0x140026a5b  jmp     loc_1400268AD
0x140026a60  mov     r10d, r8d
0x140026a63  jmp     short loc_140026A10
0x140026a65  mov     ebx, 80000000h
0x140026a6a  cmp     edx, ebx
0x140026a6c  jnz     loc_140026990
0x140026a72  cmp     ecx, eax
0x140026a74  jnz     loc_140026990
0x140026a7a  cmp     r8d, ebx
0x140026a7d  jnz     loc_140026990
0x140026a83  jmp     loc_1400268AD
0x140026a88  xor     ecx, ecx
0x140026a8a  jmp     loc_1400266C9
0x140026a8f  xor     ecx, ecx
0x140026a91  jmp     loc_140026803
0x140026a96  mov     rdx, [rbx+860h]; HSURF
0x140026a9d  test    rdx, rdx
0x140026aa0  jnz     short loc_140026AC3
0x140026aa2  mov     r10, [r14+9F0h]
0x140026aa9  jmp     loc_14002686C
0x140026aae  lea     rax, [rbp+57h+var_80]
0x140026ab2  mov     qword ptr [rbp+57h+var_80+8], rax
0x140026ab6  lea     rax, [rbp+57h+var_80]
0x140026aba  mov     qword ptr [rbp+57h+var_80], rax
0x140026abe  jmp     loc_14002671A
0x140026ac3  lea     rcx, [rbp+57h+var_D0]; this
0x140026ac7  call    ?vLock@SURFREF@@QEAAXPEAUHSURF__@@@Z; SURFREF::vLock(HSURF__ *)
0x140026acc  mov     r9, [rbp+57h+var_B0]
0x140026ad0  mov     r10, r9
0x140026ad3  mov     rax, r9
0x140026ad6  jmp     loc_14002686E
0x140026adb  lea     rax, [rbp+57h+var_D0]
0x140026adf  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140026ae3  lea     rax, [rbp+57h+var_D0]
0x140026ae7  mov     qword ptr [rbp+57h+var_D0], rax
0x140026aeb  jmp     loc_140026851
0x140026af0  mov     rcx, [rbp+57h+var_A0]; this
0x140026af4  lea     rdx, [rbp+57h+var_58]
0x140026af8  call    ?AcquireDcVisRgnExclusive@DC@@QEAA@XZ; DC::AcquireDcVisRgnExclusive(void)
  ... truncated ...
```
