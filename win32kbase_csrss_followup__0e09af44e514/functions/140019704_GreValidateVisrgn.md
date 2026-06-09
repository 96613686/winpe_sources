# GreValidateVisrgn

- ea: `0x140019704`
- end: `0x140019c47`
- name: `GreValidateVisrgn`
- size: `1347`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400188d0`
- `0x14001e010`
- `0x1400456f0`
- `0x140066fe0`

## callees

- `0x140019540`
- `0x140019704`
- `0x140019d00`
- `0x140019d88`
- `0x140024930`
- `0x140024cc0`
- `0x140024f80`
- `0x140025990`
- `0x1400272d4`
- `0x140040ccc`
- `0x1400487d0`
- `0x140110520`
- `0x1401228cc`
- `0x140238160`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001981f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001981f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140019834`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140019834`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019771`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400198ab`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019771`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400198ab`
- `WIN32K!W32GetSessionState` at `0x14001973b`
- `WIN32K!W32GetSessionState` at `0x140019972`
- `WIN32K!W32GetSessionState` at `0x1400199c7`
- `WIN32K!W32GetSessionState` at `0x140019ae3`
- `WIN32K!W32GetSessionState` at `0x14001973b`
- `WIN32K!W32GetSessionState` at `0x140019972`
- `WIN32K!W32GetSessionState` at `0x1400199c7`
- `WIN32K!W32GetSessionState` at `0x140019ae3`

## pseudocode

```c
void __fastcall GreValidateVisrgn(__int64 a1, int a2)
{
  unsigned int v3; // ebx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // di
  DC *v9; // rax
  DC *v10; // rdx
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // eax
  DC *v14; // r15
  struct _GRETHREAD *v15; // rax
  unsigned __int64 v16; // rcx
  struct _GRETHREAD *v17; // rbx
  __int64 v18; // rdx
  DC *v19; // rbx
  __int64 v20; // r14
  _DWORD *v21; // rsi
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int *v28; // r9
  unsigned int *v29; // r10
  unsigned int *v30; // rax
  int v31; // eax
  int v32; // r11d
  LONG v33; // r8d
  LONG v34; // edx
  bool v35; // zf
  __int64 v36; // rax
  struct _GRETHREAD *v37; // rax
  __int64 v38; // rcx
  __int64 SessionState; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // r14d
  LONG v43; // ebx
  __int64 v44; // rax
  bool v45; // cc
  LONG v46; // r10d
  __int64 v47; // rax
  HSURF v48; // rdx
  int v49; // r8d
  int v50; // eax
  __int128 v51; // [rsp+20h] [rbp-79h] BYREF
  __int128 v52; // [rsp+30h] [rbp-69h]
  unsigned int *v53; // [rsp+40h] [rbp-59h]
  DC *v54; // [rsp+50h] [rbp-49h] BYREF
  int v55; // [rsp+58h] [rbp-41h]
  __int64 v56; // [rsp+60h] [rbp-39h]
  __int64 v57; // [rsp+68h] [rbp-31h]
  __int128 v58; // [rsp+70h] [rbp-29h] BYREF
  __int128 v59; // [rsp+80h] [rbp-19h]
  __int64 v60; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v61[16]; // [rsp+98h] [rbp-1h] BYREF
  struct _RECTL v62; // [rsp+A8h] [rbp+Fh] BYREF

  v54 = 0;
  v3 = a1;
  v55 = 0;
  v56 = *(_QWORD *)(W32GetSessionState(a1) + 88);
  v57 = 0;
  v54 = 0;
  v55 = 0;
  v58 = 0;
  v59 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v56);
  if ( CurrentThreadWin32Thread )
    v5 = *CurrentThreadWin32Thread;
  else
    v5 = 0;
  v6 = (v5 + 8) & -(__int64)(v5 != 0);
  *(_QWORD *)&v59 = &v54;
  *((_QWORD *)&v59 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v6 )
  {
    v7 = *(_QWORD *)(((v5 + 8) & -(__int64)(v5 != 0)) + 0x58);
    if ( *(_QWORD *)(v7 + 8) != v6 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v58 = *(_QWORD *)(v6 + 88);
    *((_QWORD *)&v58 + 1) = v6 + 88;
    *(_QWORD *)(v7 + 8) = &v58;
    *(_QWORD *)(v6 + 88) = &v58;
  }
  else
  {
    *((_QWORD *)&v58 + 1) = &v58;
    *(_QWORD *)&v58 = &v58;
  }
  v8 = 1;
  v9 = (DC *)HmgShareLock(v56, v3, 1, 1);
  v54 = v9;
  v10 = v9;
  if ( v9 )
  {
    v11 = *((_DWORD *)v9 + 9);
    v12 = v11 | 0x100000;
    v13 = v11 & 0xFFEFFFFF;
    if ( !a2 )
      v12 = v13;
    *((_DWORD *)v10 + 9) = v12;
    v14 = v54;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx((char *)v14 + 1112, 0);
    GrepAcquireLockValidate<37>();
    v15 = GreGetCurrentThreadCrossSessionCheck();
    v17 = v15;
    if ( v15 )
    {
      v18 = *(_QWORD *)v15;
      if ( (*(_QWORD *)v15 & 0xFFFFFFC000000000uLL) != 0 && (v18 & 0x4000000000LL) == 0 )
      {
        v16 = 0;
        v49 = 38;
        do
        {
          v50 = v16;
          if ( ((1LL << v16) & 0xFFFFFFDFFFFFFFFFuLL & v18) == 0 )
            v50 = v49;
          ++v16;
          v49 = v50;
        }
        while ( v16 < 0x40 );
        if ( v50 > 38 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v18);
      }
      *(_QWORD *)v17 |= 0x4000000000uLL;
    }
    v19 = v54;
    if ( (*((_DWORD *)v54 + 9) & 0x100000) == 0
      || (v20 = *((_QWORD *)v54 + 6)) == 0
      || (v21 = (_DWORD *)*((_QWORD *)v54 + 142)) == 0 )
    {
LABEL_33:
      v37 = GreGetCurrentThreadCrossSessionCheck();
      if ( v37 )
        *(_QWORD *)v37 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v14 + 1112));
      if ( !v8 )
      {
        DC::AcquireDcVisRgnExclusive(v54);
        v60 = *((_QWORD *)v54 + 142);
        if ( v60 )
          RGNOBJ::vSet((RGNOBJ *)&v60, &v62);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(v61);
      }
      if ( v54 )
      {
        SessionState = W32GetSessionState(v38);
        HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), (unsigned int *)v54);
        v54 = 0;
      }
      v40 = v58;
      if ( *(__int128 **)(v58 + 8) == &v58 )
      {
        v41 = *((_QWORD *)&v58 + 1);
        if ( **((__int128 ***)&v58 + 1) == &v58 )
        {
          **((_QWORD **)&v58 + 1) = v58;
          *(_QWORD *)(v40 + 8) = v41;
          return;
        }
      }
LABEL_5:
      __fastfail(3u);
    }
    v51 = 0;
    v52 = 0;
    v22 = (__int64 *)PsGetCurrentThreadWin32Thread(v16);
    if ( v22 )
      v23 = *v22;
    else
      v23 = 0;
    v24 = v23 + 8;
    v25 = -v23;
    v26 = v24 & -(__int64)(v25 != 0);
    *(_QWORD *)&v52 = &v51;
    *((_QWORD *)&v52 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v26 )
    {
      v27 = *(_QWORD *)((v24 & -(__int64)(v25 != 0)) + 0x58);
      if ( *(_QWORD *)(v27 + 8) != v26 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v51 = *(_QWORD *)(v26 + 88);
      *((_QWORD *)&v51 + 1) = v26 + 88;
      *(_QWORD *)(v27 + 8) = &v51;
      v25 = (unsigned __int64)&v51;
      *(_QWORD *)(v26 + 88) = &v51;
    }
    else
    {
      *((_QWORD *)&v51 + 1) = &v51;
      *(_QWORD *)&v51 = &v51;
    }
    v28 = 0;
    v35 = (*((_DWORD *)v19 + 9) & 0x40000) == 0;
    v53 = 0;
    if ( v35 )
    {
      v29 = (unsigned int *)*((_QWORD *)v19 + 62);
    }
    else
    {
      v48 = (HSURF)*((_QWORD *)v19 + 268);
      if ( v48 )
      {
        SURFREF::vLock((SURFREF *)&v51, v48);
        v28 = v53;
        v29 = v53;
        v30 = v53;
LABEL_24:
        if ( !v29 )
        {
          v35 = v30 == 0;
          goto LABEL_30;
        }
        if ( (*(_DWORD *)(v20 + 40) & 0x20000) != 0 && (v29[40] & 0x80000000) != 0
          || (v31 = *((_DWORD *)v19 + 9), (v31 & 0x1000) != 0) && (v31 & 0x4000) == 0
          || (v32 = v21[13], v33 = v21[15], v32 == v33)
          || (v25 = (unsigned int)v21[14], v34 = v21[16], (_DWORD)v25 == v34)
          || v32 == 0x7FFFFFFF && v34 == 0x80000000 && (_DWORD)v25 == 0x7FFFFFFF && v33 == 0x80000000 )
        {
LABEL_29:
          v35 = v28 == 0;
LABEL_30:
          if ( !v35 )
          {
            v36 = W32GetSessionState(v25);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v36 + 88), v53);
          }
          PopThreadGuardedObject(&v51);
          goto LABEL_33;
        }
        v42 = v21[13];
        v43 = v21[14];
        v44 = *(_QWORD *)((char *)v29 + ((v29[41] & 0x800) != 0 ? 0x294 : 0) + 56);
        if ( v32 >= v33 )
        {
          if ( v32 > v33 )
          {
            v42 = v21[15];
            v33 = v21[13];
          }
          v45 = (int)v25 <= v34;
        }
        else
        {
          v45 = (int)v25 <= v34;
          if ( (int)v25 < v34 )
          {
            if ( v32 >= 0 && (int)v44 >= v33 && (v25 & 0x80000000) == 0LL && SHIDWORD(v44) >= v34 )
              goto LABEL_29;
            goto LABEL_56;
          }
        }
        if ( !v45 )
        {
          v43 = v21[16];
          v34 = v21[14];
        }
LABEL_56:
        v46 = 0;
        if ( v42 >= 0 )
          v46 = v42;
        if ( v43 < 0 )
          v43 = 0;
        if ( (int)v44 < v33 )
          v33 = v44;
        if ( SHIDWORD(v44) < v34 )
          v34 = HIDWORD(v44);
        if ( v33 < v46 )
        {
          v46 = v33;
        }
        else if ( v34 < v43 )
        {
          v43 = v34;
        }
        v62.left = v46;
        v62.top = v43;
        v62.right = v33;
        v62.bottom = v34;
        if ( v28 )
        {
          v47 = W32GetSessionState(0);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v47 + 88), v53);
        }
        PopThreadGuardedObject(&v51);
        v8 = 0;
        goto LABEL_33;
      }
      v29 = *(unsigned int **)(v20 + 2544);
    }
    v30 = 0;
    goto LABEL_24;
  }
  DCOBJA::~DCOBJA((DCOBJA *)&v54);
}

```

## disassembly

```asm
0x140019704  push    rbp
0x140019706  push    rbx
0x140019707  push    rsi
0x140019708  push    rdi
0x140019709  push    r14
0x14001970b  push    r15
0x14001970d  lea     rbp, [rsp-2Fh]
0x140019712  sub     rsp, 0C8h
0x140019719  mov     rax, cs:__security_cookie
0x140019720  xor     rax, rsp
0x140019723  mov     [rbp+57h+var_38], rax
0x140019727  mov     esi, edx
0x140019729  mov     [rbp+57h+var_A0], 0
0x140019731  mov     rbx, rcx
0x140019734  mov     [rbp+57h+var_98], 0
0x14001973b  call    cs:__imp_W32GetSessionState
0x140019742  nop     dword ptr [rax+rax+00h]
0x140019747  xorps   xmm0, xmm0
0x14001974a  mov     rcx, [rax+58h]
0x14001974e  mov     [rbp+57h+var_90], rcx
0x140019752  mov     [rbp+57h+var_88], 0
0x14001975a  mov     [rbp+57h+var_A0], 0
0x140019762  mov     [rbp+57h+var_98], 0
0x140019769  movups  [rbp+57h+var_80], xmm0
0x14001976d  movups  [rbp+57h+var_70], xmm0
0x140019771  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019778  nop     dword ptr [rax+rax+00h]
0x14001977d  test    rax, rax
0x140019780  jz      loc_140019B48
0x140019786  mov     rcx, [rax]
0x140019789  lea     rax, [rcx+8]
0x14001978d  neg     rcx
0x140019790  sbb     rdx, rdx
0x140019793  and     rdx, rax
0x140019796  lea     rax, [rbp+57h+var_A0]
0x14001979a  mov     qword ptr [rbp+57h+var_70], rax
0x14001979e  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x1400197a5  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400197a9  jz      loc_140019B6E
0x1400197af  lea     rax, [rdx+58h]
0x1400197b3  mov     rcx, [rax]
0x1400197b6  cmp     [rcx+8], rax
0x1400197ba  jz      short loc_1400197C3
0x1400197bc  mov     ecx, 3
0x1400197c1  int     29h; Win8: RtlFailFast(ecx)
0x1400197c3  mov     qword ptr [rbp+57h+var_80], rcx
0x1400197c7  lea     rdx, [rbp+57h+var_80]
0x1400197cb  mov     qword ptr [rbp+57h+var_80+8], rax
0x1400197cf  mov     [rcx+8], rdx
0x1400197d3  lea     rcx, [rbp+57h+var_80]
0x1400197d7  mov     [rax], rcx
0x1400197da  mov     rcx, [rbp+57h+var_90]
0x1400197de  mov     edi, 1
0x1400197e3  mov     r9d, edi
0x1400197e6  mov     r8b, dil
0x1400197e9  mov     rdx, rbx
0x1400197ec  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400197f1  mov     [rbp+57h+var_A0], rax
0x1400197f5  mov     rdx, rax
0x1400197f8  test    rax, rax
0x1400197fb  jz      loc_140019A2F
0x140019801  mov     ecx, [rax+24h]
0x140019804  mov     r14d, 100000h
0x14001980a  mov     eax, ecx
0x14001980c  or      ecx, r14d
0x14001980f  btr     eax, 14h
0x140019813  test    esi, esi
0x140019815  cmovz   ecx, eax
0x140019818  mov     [rdx+24h], ecx
0x14001981b  mov     r15, [rbp+57h+var_A0]
0x14001981f  call    cs:__imp_KeEnterCriticalRegion
0x140019826  nop     dword ptr [rax+rax+00h]
0x14001982b  xor     edx, edx
0x14001982d  lea     rcx, [r15+458h]
0x140019834  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001983b  nop     dword ptr [rax+rax+00h]
0x140019840  call    ??$GrepAcquireLockValidate@$0CF@@@YAXXZ; GrepAcquireLockValidate<37>(void)
0x140019845  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14001984a  mov     rbx, rax
0x14001984d  test    rax, rax
0x140019850  jz      short loc_140019875
0x140019852  mov     rdx, [rax]
0x140019855  mov     rsi, 4000000000h
0x14001985f  mov     rax, 0FFFFFFC000000000h
0x140019869  test    rax, rdx
0x14001986c  jnz     loc_140019BDF
0x140019872  or      [rbx], rsi
0x140019875  mov     rbx, [rbp+57h+var_A0]
0x140019879  test    [rbx+24h], r14d
0x14001987d  jz      loc_140019994
0x140019883  mov     r14, [rbx+30h]
0x140019887  test    r14, r14
0x14001988a  jz      loc_140019994
0x140019890  mov     rsi, [rbx+470h]
0x140019897  test    rsi, rsi
0x14001989a  jz      loc_140019994
0x1400198a0  xorps   xmm0, xmm0
0x1400198a3  movups  [rbp+57h+var_D0], xmm0
0x1400198a7  movups  [rbp+57h+var_C0], xmm0
0x1400198ab  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400198b2  nop     dword ptr [rax+rax+00h]
0x1400198b7  test    rax, rax
0x1400198ba  jz      loc_140019B4F
0x1400198c0  mov     rcx, [rax]
0x1400198c3  lea     rax, [rcx+8]
0x1400198c7  neg     rcx
0x1400198ca  sbb     rdx, rdx
0x1400198cd  and     rdx, rax
0x1400198d0  lea     rax, [rbp+57h+var_D0]
0x1400198d4  mov     qword ptr [rbp+57h+var_C0], rax
0x1400198d8  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400198df  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1400198e3  jz      loc_140019B9B
0x1400198e9  lea     rax, [rdx+58h]
0x1400198ed  mov     rcx, [rax]
0x1400198f0  cmp     [rcx+8], rax
0x1400198f4  jnz     loc_1400197BC
0x1400198fa  mov     qword ptr [rbp+57h+var_D0], rcx
0x1400198fe  lea     rdx, [rbp+57h+var_D0]
0x140019902  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140019906  mov     [rcx+8], rdx
0x14001990a  lea     rcx, [rbp+57h+var_D0]
0x14001990e  mov     [rax], rcx
0x140019911  xor     r9d, r9d
0x140019914  test    dword ptr [rbx+24h], 40000h
0x14001991b  mov     [rbp+57h+var_B0], r9
0x14001991f  jnz     loc_140019B56
0x140019925  mov     r10, [rbx+1F0h]
0x14001992c  xor     eax, eax
0x14001992e  test    r10, r10
0x140019931  jz      loc_140019A3A
0x140019937  test    dword ptr [r14+28h], 20000h
0x14001993f  jnz     loc_140019B0D
0x140019945  mov     eax, [rbx+24h]
0x140019948  bt      eax, 0Ch
0x14001994c  jb      loc_140019C29
0x140019952  mov     r11d, [rsi+34h]
0x140019956  mov     r8d, [rsi+3Ch]
0x14001995a  cmp     r11d, r8d
0x14001995d  jz      short loc_14001996D
0x14001995f  mov     ecx, [rsi+38h]
0x140019962  mov     edx, [rsi+40h]
0x140019965  cmp     ecx, edx
0x140019967  jnz     loc_140019A42
0x14001996d  test    r9, r9
0x140019970  jz      short loc_14001998B
0x140019972  call    cs:__imp_W32GetSessionState
0x140019979  nop     dword ptr [rax+rax+00h]
0x14001997e  mov     rdx, [rbp+57h+var_B0]
0x140019982  mov     rcx, [rax+58h]
0x140019986  call    HmgDecrementShareReferenceCount
0x14001998b  lea     rcx, [rbp+57h+var_D0]
0x14001998f  call    PopThreadGuardedObject
0x140019994  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140019999  test    rax, rax
0x14001999c  jz      short loc_1400199AB
0x14001999e  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x1400199a8  and     [rax], rcx
0x1400199ab  lea     rcx, [r15+458h]; this
0x1400199b2  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x1400199b7  test    dil, dil
0x1400199ba  jz      loc_140019BB0
0x1400199c0  cmp     [rbp+57h+var_A0], 0
0x1400199c5  jz      short loc_1400199E8
0x1400199c7  call    cs:__imp_W32GetSessionState
0x1400199ce  nop     dword ptr [rax+rax+00h]
0x1400199d3  mov     rdx, [rbp+57h+var_A0]
0x1400199d7  mov     rcx, [rax+58h]
0x1400199db  call    HmgDecrementShareReferenceCount
0x1400199e0  mov     [rbp+57h+var_A0], 0
0x1400199e8  mov     rax, qword ptr [rbp+57h+var_80]
0x1400199ec  lea     rcx, [rbp+57h+var_80]
0x1400199f0  cmp     [rax+8], rcx
0x1400199f4  jnz     loc_1400197BC
0x1400199fa  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1400199fe  lea     rdx, [rbp+57h+var_80]
0x140019a02  cmp     [rcx], rdx
0x140019a05  jnz     loc_1400197BC
0x140019a0b  mov     [rcx], rax
0x140019a0e  mov     [rax+8], rcx
0x140019a12  mov     rcx, [rbp+57h+var_38]
0x140019a16  xor     rcx, rsp; StackCookie
0x140019a19  call    __security_check_cookie
0x140019a1e  add     rsp, 0C8h
0x140019a25  pop     r15
0x140019a27  pop     r14
0x140019a29  pop     rdi
0x140019a2a  pop     rsi
0x140019a2b  pop     rbx
0x140019a2c  pop     rbp
0x140019a2d  retn
0x140019a2f  lea     rcx, [rbp+57h+var_A0]; this
0x140019a33  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x140019a38  jmp     short loc_140019A12
0x140019a3a  test    rax, rax
0x140019a3d  jmp     loc_140019970
0x140019a42  mov     eax, 7FFFFFFFh
0x140019a47  cmp     r11d, eax
0x140019a4a  jz      loc_140019B25
0x140019a50  mov     eax, [r10+0A4h]
0x140019a57  mov     r14d, r11d
0x140019a5a  and     eax, 800h
0x140019a5f  mov     ebx, ecx
0x140019a61  neg     eax
0x140019a63  sbb     rax, rax
0x140019a66  and     eax, 294h
0x140019a6b  mov     rax, [rax+r10+38h]
0x140019a70  mov     rsi, rax
0x140019a73  shr     rsi, 20h
0x140019a77  cmp     r11d, r8d
0x140019a7a  jge     short loc_140019A98
0x140019a7c  cmp     ecx, edx
0x140019a7e  jge     short loc_140019AA2
0x140019a80  test    r11d, r11d
0x140019a83  js      short loc_140019AA8
0x140019a85  cmp     eax, r8d
0x140019a88  jl      short loc_140019AA8
0x140019a8a  test    ecx, ecx
0x140019a8c  js      short loc_140019AA8
0x140019a8e  cmp     esi, edx
0x140019a90  jge     loc_14001996D
0x140019a96  jmp     short loc_140019AA8
0x140019a98  jle     short loc_140019AA0
0x140019a9a  mov     r14d, r8d
0x140019a9d  mov     r8d, r11d
0x140019aa0  cmp     ecx, edx
0x140019aa2  jle     short loc_140019AA8
0x140019aa4  mov     ebx, edx
0x140019aa6  mov     edx, ecx
0x140019aa8  xor     r10d, r10d
0x140019aab  test    r14d, r14d
0x140019aae  cmovns  r10d, r14d
0x140019ab2  xor     ecx, ecx
0x140019ab4  test    ebx, ebx
0x140019ab6  cmovs   ebx, ecx
0x140019ab9  cmp     eax, r8d
0x140019abc  cmovl   r8d, eax
0x140019ac0  cmp     esi, edx
0x140019ac2  cmovl   edx, esi
0x140019ac5  cmp     r8d, r10d
0x140019ac8  jl      short loc_140019B20
0x140019aca  cmp     edx, ebx
0x140019acc  jge     short loc_140019AD0
0x140019ace  mov     ebx, edx
0x140019ad0  mov     [rbp+57h+var_48.left], r10d
0x140019ad4  mov     [rbp+57h+var_48.top], ebx
0x140019ad7  mov     [rbp+57h+var_48.right], r8d
0x140019adb  mov     [rbp+57h+var_48.bottom], edx
0x140019ade  test    r9, r9
0x140019ae1  jz      short loc_140019AFC
0x140019ae3  call    cs:__imp_W32GetSessionState
0x140019aea  nop     dword ptr [rax+rax+00h]
0x140019aef  mov     rdx, [rbp+57h+var_B0]
0x140019af3  mov     rcx, [rax+58h]
0x140019af7  call    HmgDecrementShareReferenceCount
0x140019afc  lea     rcx, [rbp+57h+var_D0]
0x140019b00  call    PopThreadGuardedObject
0x140019b05  xor     dil, dil
0x140019b08  jmp     loc_140019994
0x140019b0d  cmp     dword ptr [r10+0A0h], 0
0x140019b15  jge     loc_140019945
0x140019b1b  jmp     loc_14001996D
0x140019b20  mov     r10d, r8d
0x140019b23  jmp     short loc_140019AD0
0x140019b25  mov     ebx, 80000000h
0x140019b2a  cmp     edx, ebx
0x140019b2c  jnz     loc_140019A50
0x140019b32  cmp     ecx, eax
0x140019b34  jnz     loc_140019A50
0x140019b3a  cmp     r8d, ebx
0x140019b3d  jnz     loc_140019A50
0x140019b43  jmp     loc_14001996D
0x140019b48  xor     ecx, ecx
0x140019b4a  jmp     loc_140019789
0x140019b4f  xor     ecx, ecx
0x140019b51  jmp     loc_1400198C3
0x140019b56  mov     rdx, [rbx+860h]; HSURF
0x140019b5d  test    rdx, rdx
0x140019b60  jnz     short loc_140019B83
0x140019b62  mov     r10, [r14+9F0h]
0x140019b69  jmp     loc_14001992C
0x140019b6e  lea     rax, [rbp+57h+var_80]
0x140019b72  mov     qword ptr [rbp+57h+var_80+8], rax
0x140019b76  lea     rax, [rbp+57h+var_80]
0x140019b7a  mov     qword ptr [rbp+57h+var_80], rax
0x140019b7e  jmp     loc_1400197DA
0x140019b83  lea     rcx, [rbp+57h+var_D0]; this
0x140019b87  call    ?vLock@SURFREF@@QEAAXPEAUHSURF__@@@Z; SURFREF::vLock(HSURF__ *)
0x140019b8c  mov     r9, [rbp+57h+var_B0]
0x140019b90  mov     r10, r9
0x140019b93  mov     rax, r9
0x140019b96  jmp     loc_14001992E
0x140019b9b  lea     rax, [rbp+57h+var_D0]
0x140019b9f  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140019ba3  lea     rax, [rbp+57h+var_D0]
0x140019ba7  mov     qword ptr [rbp+57h+var_D0], rax
0x140019bab  jmp     loc_140019911
0x140019bb0  mov     rcx, [rbp+57h+var_A0]; this
0x140019bb4  lea     rdx, [rbp+57h+var_58]
0x140019bb8  call    ?AcquireDcVisRgnExclusive@DC@@QEAA@XZ; DC::AcquireDcVisRgnExclusive(void)
  ... truncated ...
```
