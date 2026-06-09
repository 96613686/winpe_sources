# _InternalGetIconInfo(tagCURSOR *,_ICONINFO *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,bool)

- ea: `0x14000fafc`
- end: `0x140010291`
- name: `?_InternalGetIconInfo@@YA_NPEAUtagCURSOR@@PEAU_ICONINFO@@PEAU_UNICODE_STRING@@2PEAK_N@Z`
- size: `1941`
- prototype: `char __fastcall(struct tagCURSOR *, struct _ICONINFO *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000e5c0`
- `0x14010f1d8`

## callees

- `0x14000ece8`
- `0x14000ed28`
- `0x14000fafc`
- `0x140010298`
- `0x14001be68`
- `0x140060dd8`
- `0x140063fb4`
- `0x1400646b4`
- `0x140093450`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140010002`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010002`
- `win32kbase!UserGetAtomName` at `0x14000ff97`
- `win32kbase!UserGetAtomName` at `0x14000ff97`
- `win32kbase!GreSelectBitmap` at `0x14000fcec`
- `win32kbase!GreSelectBitmap` at `0x14000fd1b`
- `win32kbase!GreSelectBitmap` at `0x14000fde9`
- `win32kbase!GreSelectBitmap` at `0x14000fe0b`
- `win32kbase!GreSelectBitmap` at `0x14000fea6`
- `win32kbase!GreSelectBitmap` at `0x14000fecd`
- `win32kbase!GreSelectBitmap` at `0x14000fcec`
- `win32kbase!GreSelectBitmap` at `0x14000fd1b`
- `win32kbase!GreSelectBitmap` at `0x14000fde9`
- `win32kbase!GreSelectBitmap` at `0x14000fe0b`
- `win32kbase!GreSelectBitmap` at `0x14000fea6`
- `win32kbase!GreSelectBitmap` at `0x14000fecd`
- `win32kbase!GreDeleteObject` at `0x14001001a`
- `win32kbase!GreDeleteObject` at `0x14001002e`
- `win32kbase!GreDeleteObject` at `0x140010067`
- `win32kbase!GreDeleteObject` at `0x14001001a`
- `win32kbase!GreDeleteObject` at `0x14001002e`
- `win32kbase!GreDeleteObject` at `0x140010067`
- `win32kbase!EngMulDiv` at `0x14000ff06`
- `win32kbase!EngMulDiv` at `0x14000ff2b`
- `win32kbase!EngMulDiv` at `0x1400100b1`
- `win32kbase!EngMulDiv` at `0x1400100cb`
- `win32kbase!EngMulDiv` at `0x14000ff06`
- `win32kbase!EngMulDiv` at `0x14000ff2b`
- `win32kbase!EngMulDiv` at `0x1400100b1`
- `win32kbase!EngMulDiv` at `0x1400100cb`
- `win32kbase!GreCreateBitmap` at `0x14000fbd3`
- `win32kbase!GreCreateBitmap` at `0x14000fbd3`
- `WIN32K!W32GetUserSessionState` at `0x14000fc6a`
- `WIN32K!W32GetUserSessionState` at `0x14000fcd6`
- `WIN32K!W32GetUserSessionState` at `0x14000fd00`
- `WIN32K!W32GetUserSessionState` at `0x14000fd3a`
- `WIN32K!W32GetUserSessionState` at `0x14000fd76`
- `WIN32K!W32GetUserSessionState` at `0x14000fdd3`
- `WIN32K!W32GetUserSessionState` at `0x14000fdf5`
- `WIN32K!W32GetUserSessionState` at `0x14000fe22`
- `WIN32K!W32GetUserSessionState` at `0x14000fe3e`
- `WIN32K!W32GetUserSessionState` at `0x14000fe8b`
- `WIN32K!W32GetUserSessionState` at `0x14000feb2`
- `WIN32K!W32GetUserSessionState` at `0x1400100e2`
- `WIN32K!W32GetUserSessionState` at `0x14001012e`
- `WIN32K!W32GetUserSessionState` at `0x14001014e`
- `WIN32K!W32GetUserSessionState` at `0x1400101e5`
- `WIN32K!W32GetUserSessionState` at `0x14001021b`
- `WIN32K!W32GetUserSessionState` at `0x14000fc6a`
- `WIN32K!W32GetUserSessionState` at `0x14000fcd6`
- `WIN32K!W32GetUserSessionState` at `0x14000fd00`
- `WIN32K!W32GetUserSessionState` at `0x14000fd3a`
- `WIN32K!W32GetUserSessionState` at `0x14000fd76`
- `WIN32K!W32GetUserSessionState` at `0x14000fdd3`
- `WIN32K!W32GetUserSessionState` at `0x14000fdf5`
- `WIN32K!W32GetUserSessionState` at `0x14000fe22`
- `WIN32K!W32GetUserSessionState` at `0x14000fe3e`
- `WIN32K!W32GetUserSessionState` at `0x14000fe8b`
- `WIN32K!W32GetUserSessionState` at `0x14000feb2`
- `WIN32K!W32GetUserSessionState` at `0x1400100e2`
- `WIN32K!W32GetUserSessionState` at `0x14001012e`
- `WIN32K!W32GetUserSessionState` at `0x14001014e`
- `WIN32K!W32GetUserSessionState` at `0x1400101e5`
- `WIN32K!W32GetUserSessionState` at `0x14001021b`

## pseudocode

```c
char __fastcall _InternalGetIconInfo(
        struct tagCURSOR *a1,
        struct _ICONINFO *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned int *a5,
        bool a6)
{
  struct tagCURSOR *v6; // r13
  INT v7; // esi
  int v8; // r12d
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 Bitmap; // rbx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 UserSessionState; // rax
  __int64 DIBitmap; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // ebx
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdi
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rax
  unsigned int DpiForSystem; // eax
  unsigned int CursorSizesIndexFromDpi; // eax
  INT CursorSizeFromIndex; // ebx
  __int64 v67; // rax
  int v68; // r14d
  int v69; // edi
  __int64 v70; // rsi
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // rax
  struct tagCURSOR **v75; // r13
  int v76; // ebx
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rax
  __int64 v82; // [rsp+20h] [rbp-138h]
  __int64 v83; // [rsp+28h] [rbp-130h]
  INT a; // [rsp+70h] [rbp-E8h]
  INT aa; // [rsp+70h] [rbp-E8h]
  unsigned int b; // [rsp+74h] [rbp-E4h]
  BOOL v87; // [rsp+78h] [rbp-E0h]
  __int64 v90; // [rsp+90h] [rbp-C8h]
  __int64 v91; // [rsp+98h] [rbp-C0h]
  int v92; // [rsp+A0h] [rbp-B8h]
  __int64 v93; // [rsp+A8h] [rbp-B0h]
  __int64 v94; // [rsp+A8h] [rbp-B0h]
  __int64 v96; // [rsp+C0h] [rbp-98h]
  __int64 v97; // [rsp+C8h] [rbp-90h]
  _DWORD v98[3]; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v99; // [rsp+ECh] [rbp-6Ch]
  int v100; // [rsp+F4h] [rbp-64h]
  __int64 v101; // [rsp+F8h] [rbp-60h]
  int v102; // [rsp+100h] [rbp-58h]
  __int64 v103; // [rsp+104h] [rbp-54h]

  v6 = a1;
  if ( (*((_DWORD *)a1 + 20) & 8) != 0 )
  {
    v75 = (struct tagCURSOR **)*((_QWORD *)a1 + 12);
    if ( !v75 )
      return 0;
    v6 = *v75;
  }
  b = *((_DWORD *)v6 + 35);
  a = *((_DWORD *)v6 + 36);
  if ( ShouldVirtualizeIconCursorSize(v6) )
  {
    DpiForSystem = GetDpiForSystem();
    CursorSizesIndexFromDpi = GetCursorSizesIndexFromDpi(DpiForSystem);
    CursorSizeFromIndex = GetCursorSizeFromIndex(CursorSizesIndexFromDpi);
    b = EngMulDiv(b, CursorSizeFromIndex, *((_DWORD *)v6 + 19));
    a = EngMulDiv(a, CursorSizeFromIndex, *((_DWORD *)v6 + 19));
  }
  v7 = b;
  v87 = b != *((_DWORD *)v6 + 35);
  if ( !*((_QWORD *)v6 + 12) || a6 )
  {
    v8 = a;
    v9 = a;
  }
  else
  {
    v8 = a;
    v9 = a / 2;
  }
  Bitmap = GreCreateBitmap(b, v9, 1, 1, 0);
  v91 = Bitmap;
  if ( !Bitmap )
    return 0;
  v15 = 0;
  v90 = 0;
  if ( *((_QWORD *)v6 + 12) )
  {
    v16 = (unsigned int)(v8 >> 31);
    LODWORD(v16) = v8 % 2;
    if ( *((_DWORD *)v6 + 34) == 32 )
    {
      v101 = 0;
      v103 = 0;
      v98[0] = 40;
      v98[1] = b;
      v98[2] = v8 / 2;
      v99 = 2097153;
      v100 = 0;
      v102 = 0;
      UserSessionState = W32GetUserSessionState(32, v16, v13, v14);
      LODWORD(v82) = 0;
      DIBitmap = GreCreateDIBitmap(
                   *(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 64LL),
                   0,
                   0,
                   v98,
                   v82,
                   44,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0);
    }
    else
    {
      v67 = W32GetUserSessionState(32, v16, v13, v14);
      DIBitmap = GreCreateCompatibleBitmapEx(
                   *(_QWORD *)(*(_QWORD *)(v67 + 56744) + 64LL),
                   b,
                   (unsigned int)(v8 / 2),
                   0,
                   0,
                   0);
    }
    v90 = DIBitmap;
    v15 = DIBitmap;
    if ( !DIBitmap )
    {
      GreDeleteObject(Bitmap);
      return 0;
    }
  }
  v19 = *((_QWORD *)v6 + 11);
  v20 = W32GetUserSessionState(v11, v10, v13, v14);
  v96 = GreSelectBitmap(*(_QWORD *)(v20 + 43032), v19);
  v25 = W32GetUserSessionState(v22, v21, v23, v24);
  v97 = GreSelectBitmap(*(_QWORD *)(v25 + 43024), v91);
  if ( v87 )
  {
    if ( !*((_QWORD *)v6 + 12) || a6 )
      v76 = *((_DWORD *)v6 + 36);
    else
      v76 = *((_DWORD *)v6 + 36) >> 1;
    v92 = *((_DWORD *)v6 + 35);
    v94 = *(_QWORD *)(W32GetUserSessionState(v27, v26, v28, v29) + 43032);
    if ( !*((_QWORD *)v6 + 12) || a6 )
    {
      aa = v8;
    }
    else
    {
      v77 = (unsigned int)(v8 >> 31);
      LODWORD(v77) = v8 % 2;
      aa = v8 / 2;
    }
    v81 = W32GetUserSessionState(v78, v77, v79, v80);
    GreStretchBlt(*(_QWORD *)(v81 + 43024), 0, 0, b, aa, v94, 0, 0, v92, v76, 13369376, 0xFFFFFF);
  }
  else
  {
    v93 = *(_QWORD *)(W32GetUserSessionState(v27, v26, v28, v29) + 43032);
    if ( !*((_QWORD *)v6 + 12) || a6 )
    {
      v34 = v8;
    }
    else
    {
      v30 = (unsigned int)(v8 >> 31);
      LODWORD(v30) = v8 % 2;
      v34 = v8 / 2;
    }
    v35 = W32GetUserSessionState(v31, v30, v32, v33);
    GreBitBltInternal(*(_QWORD *)(v35 + 43024), 0, 0, b, v34, v93, 0, 0, 13369376, 0xFFFFFF, 0);
  }
  if ( v15 )
  {
    v40 = *((_QWORD *)v6 + 12);
    v41 = W32GetUserSessionState(v37, v36, v38, v39);
    GreSelectBitmap(*(_QWORD *)(v41 + 43032), v40);
    v46 = W32GetUserSessionState(v43, v42, v44, v45);
    GreSelectBitmap(*(_QWORD *)(v46 + 43024), v15);
    if ( v87 )
    {
      v68 = *((_DWORD *)v6 + 36) >> 1;
      v69 = *((_DWORD *)v6 + 35);
      v70 = *(_QWORD *)(W32GetUserSessionState(v48, v47, v49, v50) + 43032);
      v71 = (unsigned int)(v8 >> 31);
      LODWORD(v71) = v8 % 2;
      v74 = W32GetUserSessionState(2, v71, v72, v73);
      v83 = v70;
      v7 = b;
      GreStretchBlt(*(_QWORD *)(v74 + 43024), 0, 0, b, v8 / 2, v83, 0, 0, v69, v68, 13369376, 0);
    }
    else
    {
      v51 = *(_QWORD *)(W32GetUserSessionState(v48, v47, v49, v50) + 43032);
      v52 = (unsigned int)(v8 >> 31);
      LODWORD(v52) = v8 % 2;
      v56 = W32GetUserSessionState(v53, v52, v54, v55);
      GreBitBltInternal(*(_QWORD *)(v56 + 43024), 0, 0, b, v8 / 2, v51, 0, 0, 13369376, 0, 0);
    }
    v15 = v90;
  }
  v57 = W32GetUserSessionState(v37, v36, v38, v39);
  GreSelectBitmap(*(_QWORD *)(v57 + 43032), v96);
  v62 = W32GetUserSessionState(v59, v58, v60, v61);
  GreSelectBitmap(*(_QWORD *)(v62 + 43024), v97);
  *(_DWORD *)a2 = *((_WORD *)v6 + 37) == 3;
  *((_DWORD *)a2 + 1) = EngMulDiv(*((__int16 *)v6 + 42), v7, *((_DWORD *)v6 + 35));
  *((_DWORD *)a2 + 2) = EngMulDiv(*((__int16 *)v6 + 43), v7, *((_DWORD *)v6 + 35));
  *((_QWORD *)a2 + 2) = v91;
  *((_QWORD *)a2 + 3) = v15;
  if ( a3 )
  {
    if ( *((_WORD *)v6 + 36) )
      a3->Length = UserGetAtomName(*((unsigned __int16 *)v6 + 36), a3->Buffer, a3->MaximumLength >> 1);
    else
      a3->Length = 0;
  }
  if ( a4 )
  {
    if ( (*((_QWORD *)v6 + 8) & 0xFFFFFFFFFFFF0000uLL) != 0 )
      RtlCopyUnicodeString(a4, (PCUNICODE_STRING)((char *)v6 + 56));
    else
      *a4 = *(struct _UNICODE_STRING *)((char *)v6 + 56);
  }
  if ( a5 )
    *a5 = *((_DWORD *)v6 + 34);
  return 1;
}

```

## disassembly

```asm
0x14000fafc  push    rbx
0x14000fafe  push    rsi
0x14000faff  push    rdi
0x14000fb00  push    r12
0x14000fb02  push    r13
0x14000fb04  push    r14
0x14000fb06  push    r15
0x14000fb08  sub     rsp, 120h
0x14000fb0f  mov     rax, cs:__security_cookie
0x14000fb16  xor     rax, rsp
0x14000fb19  mov     [rsp+158h+var_48], rax
0x14000fb21  mov     r13, rcx
0x14000fb24  mov     [rsp+158h+var_D8], rdx
0x14000fb2c  mov     [rsp+158h+var_D0], r8
0x14000fb34  mov     [rsp+158h+DestinationString], r9
0x14000fb3c  mov     rax, [rsp+158h+arg_20]
0x14000fb44  mov     [rsp+158h+var_A0], rax
0x14000fb4c  mov     eax, [rcx+50h]
0x14000fb4f  xor     r15d, r15d
0x14000fb52  test    al, 8
0x14000fb54  jnz     loc_1400101A0
0x14000fb5a  mov     eax, [r13+8Ch]
0x14000fb61  mov     [rsp+158h+b], eax
0x14000fb65  mov     eax, [r13+90h]
0x14000fb6c  mov     [rsp+158h+a], eax
0x14000fb70  mov     rcx, r13; struct tagCURSOR *
0x14000fb73  call    ?ShouldVirtualizeIconCursorSize@@YA_NPEAUtagCURSOR@@@Z; ShouldVirtualizeIconCursorSize(tagCURSOR *)
0x14000fb78  test    al, al
0x14000fb7a  jnz     loc_140010092
0x14000fb80  mov     eax, r15d
0x14000fb83  mov     esi, [rsp+158h+b]
0x14000fb87  cmp     esi, [r13+8Ch]
0x14000fb8e  setnz   al
0x14000fb91  mov     [rsp+158h+var_E0], eax
0x14000fb95  cmp     [r13+60h], r15
0x14000fb99  jz      loc_140010077
0x14000fb9f  cmp     [rsp+158h+arg_28], r15b
0x14000fba7  jnz     loc_140010077
0x14000fbad  mov     r12d, [rsp+158h+a]
0x14000fbb2  mov     eax, r12d
0x14000fbb5  cdq
0x14000fbb6  mov     r14d, 2
0x14000fbbc  idiv    r14d
0x14000fbbf  mov     [rsp+158h+var_138], r15
0x14000fbc4  mov     ecx, 1
0x14000fbc9  mov     r9d, ecx
0x14000fbcc  mov     r8d, ecx
0x14000fbcf  mov     edx, eax
0x14000fbd1  mov     ecx, esi
0x14000fbd3  call    cs:__imp_GreCreateBitmap
0x14000fbda  nop     dword ptr [rax+rax+00h]
0x14000fbdf  mov     rbx, rax
0x14000fbe2  mov     [rsp+158h+var_C0], rax
0x14000fbea  test    rax, rax
0x14000fbed  jz      loc_140010073
0x14000fbf3  mov     rdi, r15
0x14000fbf6  mov     [rsp+158h+var_C8], r15
0x14000fbfe  cmp     [r13+60h], r15
0x14000fc02  jz      loc_14000FCD2
0x14000fc08  mov     ecx, 20h ; ' '
0x14000fc0d  mov     eax, r12d
0x14000fc10  cdq
0x14000fc11  idiv    r14d
0x14000fc14  cmp     [r13+88h], ecx
0x14000fc1b  jnz     loc_1400100E0
0x14000fc21  mov     [rsp+158h+var_60], r15
0x14000fc29  mov     [rsp+158h+var_54], 0
0x14000fc35  mov     [rsp+158h+var_78], 28h ; '('
0x14000fc40  mov     [rsp+158h+var_74], esi
0x14000fc47  mov     [rsp+158h+var_70], eax
0x14000fc4e  mov     [rsp+158h+var_6C], 200001h
0x14000fc5a  mov     [rsp+158h+var_64], r15d
0x14000fc62  mov     [rsp+158h+var_58], r15d
0x14000fc6a  call    cs:__imp_W32GetUserSessionState
0x14000fc71  nop     dword ptr [rax+rax+00h]
0x14000fc76  mov     rcx, [rax+0DDA8h]
0x14000fc7d  mov     [rsp+158h+var_100], r15
0x14000fc82  mov     [rsp+158h+var_108], r15d
0x14000fc87  mov     [rsp+158h+var_110], r15
0x14000fc8c  mov     [rsp+158h+var_118], r15d
0x14000fc91  mov     [rsp+158h+var_120], r15
0x14000fc96  mov     [rsp+158h+var_128], r15d
0x14000fc9b  mov     dword ptr [rsp+158h+var_130], 2Ch ; ','
0x14000fca3  mov     dword ptr [rsp+158h+var_138], r15d
0x14000fca8  lea     r9, [rsp+158h+var_78]
0x14000fcb0  xor     r8d, r8d
0x14000fcb3  xor     edx, edx
0x14000fcb5  mov     rcx, [rcx+40h]
0x14000fcb9  call    GreCreateDIBitmap
0x14000fcbe  mov     [rsp+158h+var_C8], rax
0x14000fcc6  mov     rdi, rax
0x14000fcc9  test    rax, rax
0x14000fccc  jz      loc_140010064
0x14000fcd2  mov     rbx, [r13+58h]
0x14000fcd6  call    cs:__imp_W32GetUserSessionState
0x14000fcdd  nop     dword ptr [rax+rax+00h]
0x14000fce2  mov     rdx, rbx
0x14000fce5  mov     rcx, [rax+0A818h]
0x14000fcec  call    cs:__imp_GreSelectBitmap
0x14000fcf3  nop     dword ptr [rax+rax+00h]
0x14000fcf8  mov     [rsp+158h+var_98], rax
0x14000fd00  call    cs:__imp_W32GetUserSessionState
0x14000fd07  nop     dword ptr [rax+rax+00h]
0x14000fd0c  mov     rdx, [rsp+158h+var_C0]
0x14000fd14  mov     rcx, [rax+0A810h]
0x14000fd1b  call    cs:__imp_GreSelectBitmap
0x14000fd22  nop     dword ptr [rax+rax+00h]
0x14000fd27  mov     [rsp+158h+var_90], rax
0x14000fd2f  cmp     [rsp+158h+var_E0], r15d
0x14000fd34  jnz     loc_1400101B6
0x14000fd3a  call    cs:__imp_W32GetUserSessionState
0x14000fd41  nop     dword ptr [rax+rax+00h]
0x14000fd46  mov     rax, [rax+0A818h]
0x14000fd4d  mov     [rsp+158h+var_B0], rax
0x14000fd55  cmp     [r13+60h], r15
0x14000fd59  jz      loc_14001008A
0x14000fd5f  cmp     [rsp+158h+arg_28], r15b
0x14000fd67  jnz     loc_14001008A
0x14000fd6d  mov     eax, r12d
0x14000fd70  cdq
0x14000fd71  idiv    r14d
0x14000fd74  mov     ebx, eax
0x14000fd76  call    cs:__imp_W32GetUserSessionState
0x14000fd7d  nop     dword ptr [rax+rax+00h]
0x14000fd82  mov     [rsp+158h+var_108], r15d
0x14000fd87  mov     dword ptr [rsp+158h+var_110], 0FFFFFFh
0x14000fd8f  mov     [rsp+158h+var_118], 0CC0020h
0x14000fd97  mov     dword ptr [rsp+158h+var_120], r15d
0x14000fd9c  mov     [rsp+158h+var_128], r15d
0x14000fda1  mov     rcx, [rsp+158h+var_B0]
0x14000fda9  mov     [rsp+158h+var_130], rcx
0x14000fdae  mov     dword ptr [rsp+158h+var_138], ebx
0x14000fdb2  mov     r9d, esi
0x14000fdb5  xor     r8d, r8d
0x14000fdb8  xor     edx, edx
0x14000fdba  mov     rcx, [rax+0A810h]
0x14000fdc1  call    GreBitBltInternal
0x14000fdc6  test    rdi, rdi
0x14000fdc9  jz      loc_14000FE8B
0x14000fdcf  mov     rbx, [r13+60h]
0x14000fdd3  call    cs:__imp_W32GetUserSessionState
0x14000fdda  nop     dword ptr [rax+rax+00h]
0x14000fddf  mov     rdx, rbx
0x14000fde2  mov     rcx, [rax+0A818h]
0x14000fde9  call    cs:__imp_GreSelectBitmap
0x14000fdf0  nop     dword ptr [rax+rax+00h]
0x14000fdf5  call    cs:__imp_W32GetUserSessionState
0x14000fdfc  nop     dword ptr [rax+rax+00h]
0x14000fe01  mov     rdx, rdi
0x14000fe04  mov     rcx, [rax+0A810h]
0x14000fe0b  call    cs:__imp_GreSelectBitmap
0x14000fe12  nop     dword ptr [rax+rax+00h]
0x14000fe17  cmp     [rsp+158h+var_E0], r15d
0x14000fe1c  jnz     loc_14001011D
0x14000fe22  call    cs:__imp_W32GetUserSessionState
0x14000fe29  nop     dword ptr [rax+rax+00h]
0x14000fe2e  mov     rdi, [rax+0A818h]
0x14000fe35  mov     eax, r12d
0x14000fe38  cdq
0x14000fe39  idiv    r14d
0x14000fe3c  mov     ebx, eax
0x14000fe3e  call    cs:__imp_W32GetUserSessionState
0x14000fe45  nop     dword ptr [rax+rax+00h]
0x14000fe4a  mov     [rsp+158h+var_108], r15d
0x14000fe4f  mov     dword ptr [rsp+158h+var_110], r15d
0x14000fe54  mov     [rsp+158h+var_118], 0CC0020h
0x14000fe5c  mov     dword ptr [rsp+158h+var_120], r15d
0x14000fe61  mov     [rsp+158h+var_128], r15d
0x14000fe66  mov     [rsp+158h+var_130], rdi
0x14000fe6b  mov     dword ptr [rsp+158h+var_138], ebx
0x14000fe6f  mov     r9d, esi
0x14000fe72  xor     r8d, r8d
0x14000fe75  xor     edx, edx
0x14000fe77  mov     rcx, [rax+0A810h]
0x14000fe7e  call    GreBitBltInternal
0x14000fe83  mov     rdi, [rsp+158h+var_C8]
0x14000fe8b  call    cs:__imp_W32GetUserSessionState
0x14000fe92  nop     dword ptr [rax+rax+00h]
0x14000fe97  mov     rdx, [rsp+158h+var_98]
0x14000fe9f  mov     rcx, [rax+0A818h]
0x14000fea6  call    cs:__imp_GreSelectBitmap
0x14000fead  nop     dword ptr [rax+rax+00h]
0x14000feb2  call    cs:__imp_W32GetUserSessionState
0x14000feb9  nop     dword ptr [rax+rax+00h]
0x14000febe  mov     rdx, [rsp+158h+var_90]
0x14000fec6  mov     rcx, [rax+0A810h]
0x14000fecd  call    cs:__imp_GreSelectBitmap
0x14000fed4  nop     dword ptr [rax+rax+00h]
0x14000fed9  nop
0x14000feda  mov     ecx, r15d
0x14000fedd  cmp     word ptr [r13+4Ah], 3
0x14000fee3  setz    cl
0x14000fee6  mov     rax, [rsp+158h+var_D8]
0x14000feee  mov     [rax], ecx
0x14000fef0  mov     r8d, [r13+8Ch]; c
0x14000fef7  movsx   ecx, word ptr [r13+54h]; a
0x14000fefc  mov     rbx, [rsp+158h+var_D8]
0x14000ff04  mov     edx, esi; b
0x14000ff06  call    cs:__imp_EngMulDiv
0x14000ff0d  nop     dword ptr [rax+rax+00h]
0x14000ff12  mov     [rbx+4], eax
0x14000ff15  mov     r8d, [r13+8Ch]; c
0x14000ff1c  movsx   ecx, word ptr [r13+56h]; a
0x14000ff21  mov     rbx, [rsp+158h+var_D8]
0x14000ff29  mov     edx, esi; b
0x14000ff2b  call    cs:__imp_EngMulDiv
0x14000ff32  nop     dword ptr [rax+rax+00h]
0x14000ff37  mov     [rbx+8], eax
0x14000ff3a  mov     rax, [rsp+158h+var_D8]
0x14000ff42  mov     rcx, [rsp+158h+var_C0]
0x14000ff4a  mov     [rax+10h], rcx
0x14000ff4e  mov     rax, [rsp+158h+var_D8]
0x14000ff56  mov     [rax+18h], rdi
0x14000ff5a  mov     rax, [rsp+158h+var_D0]
0x14000ff62  test    rax, rax
0x14000ff65  jz      short loc_14000FFA6
0x14000ff67  cmp     [r13+48h], r15w
0x14000ff6c  jz      short loc_14000FFE8
0x14000ff6e  mov     rbx, [rsp+158h+var_D0]
0x14000ff76  mov     rax, [rsp+158h+var_D0]
0x14000ff7e  movzx   r8d, word ptr [rax+2]
0x14000ff83  shr     r8d, 1
0x14000ff86  mov     rax, [rsp+158h+var_D0]
0x14000ff8e  mov     rdx, [rax+8]
0x14000ff92  movzx   ecx, word ptr [r13+48h]
0x14000ff97  call    cs:__imp_UserGetAtomName
0x14000ff9e  nop     dword ptr [rax+rax+00h]
0x14000ffa3  mov     [rbx], ax
0x14000ffa6  mov     rax, [rsp+158h+DestinationString]
0x14000ffae  test    rax, rax
0x14000ffb1  jnz     short loc_14000FFD3
0x14000ffb3  mov     rax, [rsp+158h+var_A0]
0x14000ffbb  test    rax, rax
0x14000ffbe  jz      short loc_140010010
0x14000ffc0  mov     ecx, [r13+88h]
0x14000ffc7  mov     rax, [rsp+158h+var_A0]
0x14000ffcf  mov     [rax], ecx
0x14000ffd1  jmp     short loc_140010010
0x14000ffd3  test    qword ptr [r13+40h], 0FFFFFFFFFFFF0000h
0x14000ffdb  jnz     short loc_14000FFF6
0x14000ffdd  movups  xmm0, xmmword ptr [r13+38h]
0x14000ffe2  movdqu  xmmword ptr [rax], xmm0
0x14000ffe6  jmp     short loc_14000FFB3
0x14000ffe8  mov     rax, [rsp+158h+var_D0]
0x14000fff0  mov     [rax], r15w
0x14000fff4  jmp     short loc_14000FFA6
0x14000fff6  lea     rdx, [r13+38h]; SourceString
0x14000fffa  mov     rcx, [rsp+158h+DestinationString]; DestinationString
0x140010002  call    cs:__imp_RtlCopyUnicodeString
0x140010009  nop     dword ptr [rax+rax+00h]
0x14001000e  jmp     short loc_14000FFB3
0x140010010  jmp     short loc_14001003E
0x140010012  mov     rcx, [rsp+158h+var_C0]
0x14001001a  call    cs:__imp_GreDeleteObject
0x140010021  nop     dword ptr [rax+rax+00h]
0x140010026  mov     rcx, [rsp+158h+var_C8]
0x14001002e  call    cs:__imp_GreDeleteObject
0x140010035  nop     dword ptr [rax+rax+00h]
0x14001003a  xor     al, al
0x14001003c  jmp     short loc_140010040
0x14001003e  mov     al, 1
0x140010040  mov     rcx, [rsp+158h+var_48]
0x140010048  xor     rcx, rsp; StackCookie
0x14001004b  call    __security_check_cookie
0x140010050  add     rsp, 120h
0x140010057  pop     r15
0x140010059  pop     r14
0x14001005b  pop     r13
0x14001005d  pop     r12
0x14001005f  pop     rdi
0x140010060  pop     rsi
0x140010061  pop     rbx
0x140010062  retn
0x140010064  mov     rcx, rbx
0x140010067  call    cs:__imp_GreDeleteObject
0x14001006e  nop     dword ptr [rax+rax+00h]
0x140010073  xor     al, al
0x140010075  jmp     short loc_140010040
0x140010077  mov     r12d, [rsp+158h+a]
0x14001007c  mov     eax, r12d
0x14001007f  mov     r14d, 2
0x140010085  jmp     loc_14000FBBF
0x14001008a  mov     ebx, r12d
0x14001008d  jmp     loc_14000FD76
0x140010092  call    GetDpiForSystem
0x140010097  mov     ecx, eax
0x140010099  call    GetCursorSizesIndexFromDpi
0x14001009e  mov     ecx, eax
0x1400100a0  call    GetCursorSizeFromIndex
0x1400100a5  mov     ebx, eax
0x1400100a7  mov     r8d, [r13+4Ch]; c
0x1400100ab  mov     edx, eax; b
0x1400100ad  mov     ecx, [rsp+158h+b]; a
0x1400100b1  call    cs:__imp_EngMulDiv
0x1400100b8  nop     dword ptr [rax+rax+00h]
0x1400100bd  mov     [rsp+158h+b], eax
0x1400100c1  mov     r8d, [r13+4Ch]; c
0x1400100c5  mov     edx, ebx; b
0x1400100c7  mov     ecx, [rsp+158h+a]; a
0x1400100cb  call    cs:__imp_EngMulDiv
  ... truncated ...
```
