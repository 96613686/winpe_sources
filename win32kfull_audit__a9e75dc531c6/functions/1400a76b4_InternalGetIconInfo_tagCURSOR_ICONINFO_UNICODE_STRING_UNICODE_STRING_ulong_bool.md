# _InternalGetIconInfo(tagCURSOR *,_ICONINFO *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,bool)

- ea: `0x1400a76b4`
- end: `0x1400a7e49`
- name: `?_InternalGetIconInfo@@YA_NPEAUtagCURSOR@@PEAU_ICONINFO@@PEAU_UNICODE_STRING@@2PEAK_N@Z`
- size: `1941`
- prototype: `char __fastcall(struct tagCURSOR *, struct _ICONINFO *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140125788`
- `0x1401e2490`

## callees

- `0x140053cf0`
- `0x140060630`
- `0x140093fe8`
- `0x1400a76b4`
- `0x1400a7e50`
- `0x1400a8e1c`
- `0x1400a9a54`
- `0x1400bef18`
- `0x1400bfa8c`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400a7bba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400a7bba`
- `win32kbase!UserGetAtomName` at `0x1400a7b4f`
- `win32kbase!UserGetAtomName` at `0x1400a7b4f`
- `win32kbase!GreSelectBitmap` at `0x1400a78a4`
- `win32kbase!GreSelectBitmap` at `0x1400a78d3`
- `win32kbase!GreSelectBitmap` at `0x1400a79a1`
- `win32kbase!GreSelectBitmap` at `0x1400a79c3`
- `win32kbase!GreSelectBitmap` at `0x1400a7a5e`
- `win32kbase!GreSelectBitmap` at `0x1400a7a85`
- `win32kbase!GreSelectBitmap` at `0x1400a78a4`
- `win32kbase!GreSelectBitmap` at `0x1400a78d3`
- `win32kbase!GreSelectBitmap` at `0x1400a79a1`
- `win32kbase!GreSelectBitmap` at `0x1400a79c3`
- `win32kbase!GreSelectBitmap` at `0x1400a7a5e`
- `win32kbase!GreSelectBitmap` at `0x1400a7a85`
- `win32kbase!GreDeleteObject` at `0x1400a7bd2`
- `win32kbase!GreDeleteObject` at `0x1400a7be6`
- `win32kbase!GreDeleteObject` at `0x1400a7c1f`
- `win32kbase!GreDeleteObject` at `0x1400a7bd2`
- `win32kbase!GreDeleteObject` at `0x1400a7be6`
- `win32kbase!GreDeleteObject` at `0x1400a7c1f`
- `win32kbase!EngMulDiv` at `0x1400a7abe`
- `win32kbase!EngMulDiv` at `0x1400a7ae3`
- `win32kbase!EngMulDiv` at `0x1400a7c69`
- `win32kbase!EngMulDiv` at `0x1400a7c83`
- `win32kbase!EngMulDiv` at `0x1400a7abe`
- `win32kbase!EngMulDiv` at `0x1400a7ae3`
- `win32kbase!EngMulDiv` at `0x1400a7c69`
- `win32kbase!EngMulDiv` at `0x1400a7c83`
- `win32kbase!GreCreateBitmap` at `0x1400a778b`
- `win32kbase!GreCreateBitmap` at `0x1400a778b`
- `WIN32K!W32GetUserSessionState` at `0x1400a7822`
- `WIN32K!W32GetUserSessionState` at `0x1400a788e`
- `WIN32K!W32GetUserSessionState` at `0x1400a78b8`
- `WIN32K!W32GetUserSessionState` at `0x1400a78f2`
- `WIN32K!W32GetUserSessionState` at `0x1400a792e`
- `WIN32K!W32GetUserSessionState` at `0x1400a798b`
- `WIN32K!W32GetUserSessionState` at `0x1400a79ad`
- `WIN32K!W32GetUserSessionState` at `0x1400a79da`
- `WIN32K!W32GetUserSessionState` at `0x1400a79f6`
- `WIN32K!W32GetUserSessionState` at `0x1400a7a43`
- `WIN32K!W32GetUserSessionState` at `0x1400a7a6a`
- `WIN32K!W32GetUserSessionState` at `0x1400a7c9a`
- `WIN32K!W32GetUserSessionState` at `0x1400a7ce6`
- `WIN32K!W32GetUserSessionState` at `0x1400a7d06`
- `WIN32K!W32GetUserSessionState` at `0x1400a7d9d`
- `WIN32K!W32GetUserSessionState` at `0x1400a7dd3`
- `WIN32K!W32GetUserSessionState` at `0x1400a7822`
- `WIN32K!W32GetUserSessionState` at `0x1400a788e`
- `WIN32K!W32GetUserSessionState` at `0x1400a78b8`
- `WIN32K!W32GetUserSessionState` at `0x1400a78f2`
- `WIN32K!W32GetUserSessionState` at `0x1400a792e`
- `WIN32K!W32GetUserSessionState` at `0x1400a798b`
- `WIN32K!W32GetUserSessionState` at `0x1400a79ad`
- `WIN32K!W32GetUserSessionState` at `0x1400a79da`
- `WIN32K!W32GetUserSessionState` at `0x1400a79f6`
- `WIN32K!W32GetUserSessionState` at `0x1400a7a43`
- `WIN32K!W32GetUserSessionState` at `0x1400a7a6a`
- `WIN32K!W32GetUserSessionState` at `0x1400a7c9a`
- `WIN32K!W32GetUserSessionState` at `0x1400a7ce6`
- `WIN32K!W32GetUserSessionState` at `0x1400a7d06`
- `WIN32K!W32GetUserSessionState` at `0x1400a7d9d`
- `WIN32K!W32GetUserSessionState` at `0x1400a7dd3`

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
  __int64 v7; // rcx
  INT v8; // esi
  int v9; // r12d
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 Bitmap; // rbx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 UserSessionState; // rax
  __int64 DIBitmap; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdi
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  unsigned int DpiForSystem; // eax
  unsigned int CursorSizesIndexFromDpi; // eax
  INT CursorSizeFromIndex; // ebx
  __int64 v68; // rax
  int v69; // r14d
  int v70; // edi
  __int64 v71; // rsi
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rax
  struct tagCURSOR **v76; // r13
  int v77; // ebx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rax
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
  unsigned int v98[3]; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v99; // [rsp+ECh] [rbp-6Ch]
  int v100; // [rsp+F4h] [rbp-64h]
  __int64 v101; // [rsp+F8h] [rbp-60h]
  int v102; // [rsp+100h] [rbp-58h]
  __int64 v103; // [rsp+104h] [rbp-54h]

  v6 = a1;
  if ( (*((_DWORD *)a1 + 20) & 8) != 0 )
  {
    v76 = (struct tagCURSOR **)*((_QWORD *)a1 + 12);
    if ( !v76 )
      return 0;
    v6 = *v76;
  }
  b = *((_DWORD *)v6 + 35);
  a = *((_DWORD *)v6 + 36);
  if ( ShouldVirtualizeIconCursorSize(v6) )
  {
    DpiForSystem = GetDpiForSystem(v7);
    CursorSizesIndexFromDpi = GetCursorSizesIndexFromDpi(DpiForSystem);
    CursorSizeFromIndex = GetCursorSizeFromIndex(CursorSizesIndexFromDpi);
    b = EngMulDiv(b, CursorSizeFromIndex, *((_DWORD *)v6 + 19));
    a = EngMulDiv(a, CursorSizeFromIndex, *((_DWORD *)v6 + 19));
  }
  v8 = b;
  v87 = b != *((_DWORD *)v6 + 35);
  if ( !*((_QWORD *)v6 + 12) || a6 )
  {
    v9 = a;
    v10 = a;
  }
  else
  {
    v9 = a;
    v10 = a / 2;
  }
  Bitmap = GreCreateBitmap(b, v10, 1, 1, 0);
  v91 = Bitmap;
  if ( !Bitmap )
    return 0;
  v16 = 0;
  v90 = 0;
  if ( *((_QWORD *)v6 + 12) )
  {
    v17 = (unsigned int)(v9 >> 31);
    LODWORD(v17) = v9 % 2;
    if ( *((_DWORD *)v6 + 34) == 32 )
    {
      v101 = 0;
      v103 = 0;
      v98[0] = 40;
      v98[1] = b;
      v98[2] = v9 / 2;
      v99 = 2097153;
      v100 = 0;
      v102 = 0;
      UserSessionState = W32GetUserSessionState(32, v17, v14, v15);
      DIBitmap = GreCreateDIBitmap(
                   *(Gre::Base **)(*(_QWORD *)(UserSessionState + 56744) + 64LL),
                   0,
                   0,
                   v98,
                   0,
                   0x2Cu,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0);
    }
    else
    {
      v68 = W32GetUserSessionState(32, v17, v14, v15);
      DIBitmap = GreCreateCompatibleBitmapEx(
                   *(_QWORD *)(*(_QWORD *)(v68 + 56744) + 64LL),
                   b,
                   (unsigned int)(v9 / 2),
                   0,
                   0,
                   0);
    }
    v90 = DIBitmap;
    v16 = DIBitmap;
    if ( !DIBitmap )
    {
      GreDeleteObject(Bitmap);
      return 0;
    }
  }
  v20 = *((_QWORD *)v6 + 11);
  v21 = W32GetUserSessionState(v12, v11, v14, v15);
  v96 = GreSelectBitmap(*(_QWORD *)(v21 + 43032), v20);
  v26 = W32GetUserSessionState(v23, v22, v24, v25);
  v97 = GreSelectBitmap(*(_QWORD *)(v26 + 43024), v91);
  if ( v87 )
  {
    if ( !*((_QWORD *)v6 + 12) || a6 )
      v77 = *((_DWORD *)v6 + 36);
    else
      v77 = *((_DWORD *)v6 + 36) >> 1;
    v92 = *((_DWORD *)v6 + 35);
    v94 = *(_QWORD *)(W32GetUserSessionState(v28, v27, v29, v30) + 43032);
    if ( !*((_QWORD *)v6 + 12) || a6 )
    {
      aa = v9;
    }
    else
    {
      v78 = (unsigned int)(v9 >> 31);
      LODWORD(v78) = v9 % 2;
      aa = v9 / 2;
    }
    v82 = W32GetUserSessionState(v79, v78, v80, v81);
    GreStretchBlt(*(Gre::Base **)(v82 + 43024), 0, 0, b, aa, v94, 0, 0, v92, v77, 0xCC0020u, 0xFFFFFFu);
  }
  else
  {
    v93 = *(_QWORD *)(W32GetUserSessionState(v28, v27, v29, v30) + 43032);
    if ( !*((_QWORD *)v6 + 12) || a6 )
    {
      v35 = v9;
    }
    else
    {
      v31 = (unsigned int)(v9 >> 31);
      LODWORD(v31) = v9 % 2;
      v35 = v9 / 2;
    }
    v36 = W32GetUserSessionState(v32, v31, v33, v34);
    GreBitBltInternal(*(Gre::Base **)(v36 + 43024), 0, 0, b, v35, v93, 0, 0, 0xCC0020u, 0xFFFFFFu, 0);
  }
  if ( v16 )
  {
    v41 = *((_QWORD *)v6 + 12);
    v42 = W32GetUserSessionState(v38, v37, v39, v40);
    GreSelectBitmap(*(_QWORD *)(v42 + 43032), v41);
    v47 = W32GetUserSessionState(v44, v43, v45, v46);
    GreSelectBitmap(*(_QWORD *)(v47 + 43024), v16);
    if ( v87 )
    {
      v69 = *((_DWORD *)v6 + 36) >> 1;
      v70 = *((_DWORD *)v6 + 35);
      v71 = *(_QWORD *)(W32GetUserSessionState(v49, v48, v50, v51) + 43032);
      v72 = (unsigned int)(v9 >> 31);
      LODWORD(v72) = v9 % 2;
      v75 = W32GetUserSessionState(2, v72, v73, v74);
      v83 = v71;
      v8 = b;
      GreStretchBlt(*(Gre::Base **)(v75 + 43024), 0, 0, b, v9 / 2, v83, 0, 0, v70, v69, 0xCC0020u, 0);
    }
    else
    {
      v52 = *(_QWORD *)(W32GetUserSessionState(v49, v48, v50, v51) + 43032);
      v53 = (unsigned int)(v9 >> 31);
      LODWORD(v53) = v9 % 2;
      v57 = W32GetUserSessionState(v54, v53, v55, v56);
      GreBitBltInternal(*(Gre::Base **)(v57 + 43024), 0, 0, b, v9 / 2, v52, 0, 0, 0xCC0020u, 0, 0);
    }
    v16 = v90;
  }
  v58 = W32GetUserSessionState(v38, v37, v39, v40);
  GreSelectBitmap(*(_QWORD *)(v58 + 43032), v96);
  v63 = W32GetUserSessionState(v60, v59, v61, v62);
  GreSelectBitmap(*(_QWORD *)(v63 + 43024), v97);
  *(_DWORD *)a2 = *((_WORD *)v6 + 37) == 3;
  *((_DWORD *)a2 + 1) = EngMulDiv(*((__int16 *)v6 + 42), v8, *((_DWORD *)v6 + 35));
  *((_DWORD *)a2 + 2) = EngMulDiv(*((__int16 *)v6 + 43), v8, *((_DWORD *)v6 + 35));
  *((_QWORD *)a2 + 2) = v91;
  *((_QWORD *)a2 + 3) = v16;
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
0x1400a76b4  push    rbx
0x1400a76b6  push    rsi
0x1400a76b7  push    rdi
0x1400a76b8  push    r12
0x1400a76ba  push    r13
0x1400a76bc  push    r14
0x1400a76be  push    r15
0x1400a76c0  sub     rsp, 120h
0x1400a76c7  mov     rax, cs:__security_cookie
0x1400a76ce  xor     rax, rsp
0x1400a76d1  mov     [rsp+158h+var_48], rax
0x1400a76d9  mov     r13, rcx
0x1400a76dc  mov     [rsp+158h+var_D8], rdx
0x1400a76e4  mov     [rsp+158h+var_D0], r8
0x1400a76ec  mov     [rsp+158h+DestinationString], r9
0x1400a76f4  mov     rax, [rsp+158h+arg_20]
0x1400a76fc  mov     [rsp+158h+var_A0], rax
0x1400a7704  mov     eax, [rcx+50h]
0x1400a7707  xor     r15d, r15d
0x1400a770a  test    al, 8
0x1400a770c  jnz     loc_1400A7D58
0x1400a7712  mov     eax, [r13+8Ch]
0x1400a7719  mov     [rsp+158h+b], eax
0x1400a771d  mov     eax, [r13+90h]
0x1400a7724  mov     [rsp+158h+a], eax
0x1400a7728  mov     rcx, r13; struct tagCURSOR *
0x1400a772b  call    ?ShouldVirtualizeIconCursorSize@@YA_NPEAUtagCURSOR@@@Z; ShouldVirtualizeIconCursorSize(tagCURSOR *)
0x1400a7730  test    al, al
0x1400a7732  jnz     loc_1400A7C4A
0x1400a7738  mov     eax, r15d
0x1400a773b  mov     esi, [rsp+158h+b]
0x1400a773f  cmp     esi, [r13+8Ch]
0x1400a7746  setnz   al
0x1400a7749  mov     [rsp+158h+var_E0], eax
0x1400a774d  cmp     [r13+60h], r15
0x1400a7751  jz      loc_1400A7C2F
0x1400a7757  cmp     [rsp+158h+arg_28], r15b
0x1400a775f  jnz     loc_1400A7C2F
0x1400a7765  mov     r12d, [rsp+158h+a]
0x1400a776a  mov     eax, r12d
0x1400a776d  cdq
0x1400a776e  mov     r14d, 2
0x1400a7774  idiv    r14d
0x1400a7777  mov     [rsp+158h+var_138], r15
0x1400a777c  mov     ecx, 1
0x1400a7781  mov     r9d, ecx
0x1400a7784  mov     r8d, ecx
0x1400a7787  mov     edx, eax
0x1400a7789  mov     ecx, esi
0x1400a778b  call    cs:__imp_GreCreateBitmap
0x1400a7792  nop     dword ptr [rax+rax+00h]
0x1400a7797  mov     rbx, rax
0x1400a779a  mov     [rsp+158h+var_C0], rax
0x1400a77a2  test    rax, rax
0x1400a77a5  jz      loc_1400A7C2B
0x1400a77ab  mov     rdi, r15
0x1400a77ae  mov     [rsp+158h+var_C8], r15
0x1400a77b6  cmp     [r13+60h], r15
0x1400a77ba  jz      loc_1400A788A
0x1400a77c0  mov     ecx, 20h ; ' '
0x1400a77c5  mov     eax, r12d
0x1400a77c8  cdq
0x1400a77c9  idiv    r14d
0x1400a77cc  cmp     [r13+88h], ecx
0x1400a77d3  jnz     loc_1400A7C98
0x1400a77d9  mov     [rsp+158h+var_60], r15
0x1400a77e1  mov     [rsp+158h+var_54], 0
0x1400a77ed  mov     [rsp+158h+var_78], 28h ; '('
0x1400a77f8  mov     [rsp+158h+var_74], esi
0x1400a77ff  mov     [rsp+158h+var_70], eax
0x1400a7806  mov     [rsp+158h+var_6C], 200001h
0x1400a7812  mov     [rsp+158h+var_64], r15d
0x1400a781a  mov     [rsp+158h+var_58], r15d
0x1400a7822  call    cs:__imp_W32GetUserSessionState
0x1400a7829  nop     dword ptr [rax+rax+00h]
0x1400a782e  mov     rcx, [rax+0DDA8h]
0x1400a7835  mov     [rsp+158h+var_100], r15
0x1400a783a  mov     [rsp+158h+var_108], r15d
0x1400a783f  mov     [rsp+158h+var_110], r15
0x1400a7844  mov     [rsp+158h+var_118], r15d
0x1400a7849  mov     [rsp+158h+var_120], r15
0x1400a784e  mov     [rsp+158h+var_128], r15d
0x1400a7853  mov     dword ptr [rsp+158h+var_130], 2Ch ; ','
0x1400a785b  mov     dword ptr [rsp+158h+var_138], r15d
0x1400a7860  lea     r9, [rsp+158h+var_78]
0x1400a7868  xor     r8d, r8d
0x1400a786b  xor     edx, edx
0x1400a786d  mov     rcx, [rcx+40h]
0x1400a7871  call    GreCreateDIBitmap
0x1400a7876  mov     [rsp+158h+var_C8], rax
0x1400a787e  mov     rdi, rax
0x1400a7881  test    rax, rax
0x1400a7884  jz      loc_1400A7C1C
0x1400a788a  mov     rbx, [r13+58h]
0x1400a788e  call    cs:__imp_W32GetUserSessionState
0x1400a7895  nop     dword ptr [rax+rax+00h]
0x1400a789a  mov     rdx, rbx
0x1400a789d  mov     rcx, [rax+0A818h]
0x1400a78a4  call    cs:__imp_GreSelectBitmap
0x1400a78ab  nop     dword ptr [rax+rax+00h]
0x1400a78b0  mov     [rsp+158h+var_98], rax
0x1400a78b8  call    cs:__imp_W32GetUserSessionState
0x1400a78bf  nop     dword ptr [rax+rax+00h]
0x1400a78c4  mov     rdx, [rsp+158h+var_C0]
0x1400a78cc  mov     rcx, [rax+0A810h]
0x1400a78d3  call    cs:__imp_GreSelectBitmap
0x1400a78da  nop     dword ptr [rax+rax+00h]
0x1400a78df  mov     [rsp+158h+var_90], rax
0x1400a78e7  cmp     [rsp+158h+var_E0], r15d
0x1400a78ec  jnz     loc_1400A7D6E
0x1400a78f2  call    cs:__imp_W32GetUserSessionState
0x1400a78f9  nop     dword ptr [rax+rax+00h]
0x1400a78fe  mov     rax, [rax+0A818h]
0x1400a7905  mov     [rsp+158h+var_B0], rax
0x1400a790d  cmp     [r13+60h], r15
0x1400a7911  jz      loc_1400A7C42
0x1400a7917  cmp     [rsp+158h+arg_28], r15b
0x1400a791f  jnz     loc_1400A7C42
0x1400a7925  mov     eax, r12d
0x1400a7928  cdq
0x1400a7929  idiv    r14d
0x1400a792c  mov     ebx, eax
0x1400a792e  call    cs:__imp_W32GetUserSessionState
0x1400a7935  nop     dword ptr [rax+rax+00h]
0x1400a793a  mov     [rsp+158h+var_108], r15d
0x1400a793f  mov     dword ptr [rsp+158h+var_110], 0FFFFFFh
0x1400a7947  mov     [rsp+158h+var_118], 0CC0020h
0x1400a794f  mov     dword ptr [rsp+158h+var_120], r15d
0x1400a7954  mov     [rsp+158h+var_128], r15d
0x1400a7959  mov     rcx, [rsp+158h+var_B0]
0x1400a7961  mov     [rsp+158h+var_130], rcx
0x1400a7966  mov     dword ptr [rsp+158h+var_138], ebx
0x1400a796a  mov     r9d, esi
0x1400a796d  xor     r8d, r8d
0x1400a7970  xor     edx, edx
0x1400a7972  mov     rcx, [rax+0A810h]
0x1400a7979  call    GreBitBltInternal
0x1400a797e  test    rdi, rdi
0x1400a7981  jz      loc_1400A7A43
0x1400a7987  mov     rbx, [r13+60h]
0x1400a798b  call    cs:__imp_W32GetUserSessionState
0x1400a7992  nop     dword ptr [rax+rax+00h]
0x1400a7997  mov     rdx, rbx
0x1400a799a  mov     rcx, [rax+0A818h]
0x1400a79a1  call    cs:__imp_GreSelectBitmap
0x1400a79a8  nop     dword ptr [rax+rax+00h]
0x1400a79ad  call    cs:__imp_W32GetUserSessionState
0x1400a79b4  nop     dword ptr [rax+rax+00h]
0x1400a79b9  mov     rdx, rdi
0x1400a79bc  mov     rcx, [rax+0A810h]
0x1400a79c3  call    cs:__imp_GreSelectBitmap
0x1400a79ca  nop     dword ptr [rax+rax+00h]
0x1400a79cf  cmp     [rsp+158h+var_E0], r15d
0x1400a79d4  jnz     loc_1400A7CD5
0x1400a79da  call    cs:__imp_W32GetUserSessionState
0x1400a79e1  nop     dword ptr [rax+rax+00h]
0x1400a79e6  mov     rdi, [rax+0A818h]
0x1400a79ed  mov     eax, r12d
0x1400a79f0  cdq
0x1400a79f1  idiv    r14d
0x1400a79f4  mov     ebx, eax
0x1400a79f6  call    cs:__imp_W32GetUserSessionState
0x1400a79fd  nop     dword ptr [rax+rax+00h]
0x1400a7a02  mov     [rsp+158h+var_108], r15d
0x1400a7a07  mov     dword ptr [rsp+158h+var_110], r15d
0x1400a7a0c  mov     [rsp+158h+var_118], 0CC0020h
0x1400a7a14  mov     dword ptr [rsp+158h+var_120], r15d
0x1400a7a19  mov     [rsp+158h+var_128], r15d
0x1400a7a1e  mov     [rsp+158h+var_130], rdi
0x1400a7a23  mov     dword ptr [rsp+158h+var_138], ebx
0x1400a7a27  mov     r9d, esi
0x1400a7a2a  xor     r8d, r8d
0x1400a7a2d  xor     edx, edx
0x1400a7a2f  mov     rcx, [rax+0A810h]
0x1400a7a36  call    GreBitBltInternal
0x1400a7a3b  mov     rdi, [rsp+158h+var_C8]
0x1400a7a43  call    cs:__imp_W32GetUserSessionState
0x1400a7a4a  nop     dword ptr [rax+rax+00h]
0x1400a7a4f  mov     rdx, [rsp+158h+var_98]
0x1400a7a57  mov     rcx, [rax+0A818h]
0x1400a7a5e  call    cs:__imp_GreSelectBitmap
0x1400a7a65  nop     dword ptr [rax+rax+00h]
0x1400a7a6a  call    cs:__imp_W32GetUserSessionState
0x1400a7a71  nop     dword ptr [rax+rax+00h]
0x1400a7a76  mov     rdx, [rsp+158h+var_90]
0x1400a7a7e  mov     rcx, [rax+0A810h]
0x1400a7a85  call    cs:__imp_GreSelectBitmap
0x1400a7a8c  nop     dword ptr [rax+rax+00h]
0x1400a7a91  nop
0x1400a7a92  mov     ecx, r15d
0x1400a7a95  cmp     word ptr [r13+4Ah], 3
0x1400a7a9b  setz    cl
0x1400a7a9e  mov     rax, [rsp+158h+var_D8]
0x1400a7aa6  mov     [rax], ecx
0x1400a7aa8  mov     r8d, [r13+8Ch]; c
0x1400a7aaf  movsx   ecx, word ptr [r13+54h]; a
0x1400a7ab4  mov     rbx, [rsp+158h+var_D8]
0x1400a7abc  mov     edx, esi; b
0x1400a7abe  call    cs:__imp_EngMulDiv
0x1400a7ac5  nop     dword ptr [rax+rax+00h]
0x1400a7aca  mov     [rbx+4], eax
0x1400a7acd  mov     r8d, [r13+8Ch]; c
0x1400a7ad4  movsx   ecx, word ptr [r13+56h]; a
0x1400a7ad9  mov     rbx, [rsp+158h+var_D8]
0x1400a7ae1  mov     edx, esi; b
0x1400a7ae3  call    cs:__imp_EngMulDiv
0x1400a7aea  nop     dword ptr [rax+rax+00h]
0x1400a7aef  mov     [rbx+8], eax
0x1400a7af2  mov     rax, [rsp+158h+var_D8]
0x1400a7afa  mov     rcx, [rsp+158h+var_C0]
0x1400a7b02  mov     [rax+10h], rcx
0x1400a7b06  mov     rax, [rsp+158h+var_D8]
0x1400a7b0e  mov     [rax+18h], rdi
0x1400a7b12  mov     rax, [rsp+158h+var_D0]
0x1400a7b1a  test    rax, rax
0x1400a7b1d  jz      short loc_1400A7B5E
0x1400a7b1f  cmp     [r13+48h], r15w
0x1400a7b24  jz      short loc_1400A7BA0
0x1400a7b26  mov     rbx, [rsp+158h+var_D0]
0x1400a7b2e  mov     rax, [rsp+158h+var_D0]
0x1400a7b36  movzx   r8d, word ptr [rax+2]
0x1400a7b3b  shr     r8d, 1
0x1400a7b3e  mov     rax, [rsp+158h+var_D0]
0x1400a7b46  mov     rdx, [rax+8]
0x1400a7b4a  movzx   ecx, word ptr [r13+48h]
0x1400a7b4f  call    cs:__imp_UserGetAtomName
0x1400a7b56  nop     dword ptr [rax+rax+00h]
0x1400a7b5b  mov     [rbx], ax
0x1400a7b5e  mov     rax, [rsp+158h+DestinationString]
0x1400a7b66  test    rax, rax
0x1400a7b69  jnz     short loc_1400A7B8B
0x1400a7b6b  mov     rax, [rsp+158h+var_A0]
0x1400a7b73  test    rax, rax
0x1400a7b76  jz      short loc_1400A7BC8
0x1400a7b78  mov     ecx, [r13+88h]
0x1400a7b7f  mov     rax, [rsp+158h+var_A0]
0x1400a7b87  mov     [rax], ecx
0x1400a7b89  jmp     short loc_1400A7BC8
0x1400a7b8b  test    qword ptr [r13+40h], 0FFFFFFFFFFFF0000h
0x1400a7b93  jnz     short loc_1400A7BAE
0x1400a7b95  movups  xmm0, xmmword ptr [r13+38h]
0x1400a7b9a  movdqu  xmmword ptr [rax], xmm0
0x1400a7b9e  jmp     short loc_1400A7B6B
0x1400a7ba0  mov     rax, [rsp+158h+var_D0]
0x1400a7ba8  mov     [rax], r15w
0x1400a7bac  jmp     short loc_1400A7B5E
0x1400a7bae  lea     rdx, [r13+38h]; SourceString
0x1400a7bb2  mov     rcx, [rsp+158h+DestinationString]; DestinationString
0x1400a7bba  call    cs:__imp_RtlCopyUnicodeString
0x1400a7bc1  nop     dword ptr [rax+rax+00h]
0x1400a7bc6  jmp     short loc_1400A7B6B
0x1400a7bc8  jmp     short loc_1400A7BF6
0x1400a7bca  mov     rcx, [rsp+158h+var_C0]
0x1400a7bd2  call    cs:__imp_GreDeleteObject
0x1400a7bd9  nop     dword ptr [rax+rax+00h]
0x1400a7bde  mov     rcx, [rsp+158h+var_C8]
0x1400a7be6  call    cs:__imp_GreDeleteObject
0x1400a7bed  nop     dword ptr [rax+rax+00h]
0x1400a7bf2  xor     al, al
0x1400a7bf4  jmp     short loc_1400A7BF8
0x1400a7bf6  mov     al, 1
0x1400a7bf8  mov     rcx, [rsp+158h+var_48]
0x1400a7c00  xor     rcx, rsp; StackCookie
0x1400a7c03  call    __security_check_cookie
0x1400a7c08  add     rsp, 120h
0x1400a7c0f  pop     r15
0x1400a7c11  pop     r14
0x1400a7c13  pop     r13
0x1400a7c15  pop     r12
0x1400a7c17  pop     rdi
0x1400a7c18  pop     rsi
0x1400a7c19  pop     rbx
0x1400a7c1a  retn
0x1400a7c1c  mov     rcx, rbx
0x1400a7c1f  call    cs:__imp_GreDeleteObject
0x1400a7c26  nop     dword ptr [rax+rax+00h]
0x1400a7c2b  xor     al, al
0x1400a7c2d  jmp     short loc_1400A7BF8
0x1400a7c2f  mov     r12d, [rsp+158h+a]
0x1400a7c34  mov     eax, r12d
0x1400a7c37  mov     r14d, 2
0x1400a7c3d  jmp     loc_1400A7777
0x1400a7c42  mov     ebx, r12d
0x1400a7c45  jmp     loc_1400A792E
0x1400a7c4a  call    GetDpiForSystem
0x1400a7c4f  mov     ecx, eax
0x1400a7c51  call    GetCursorSizesIndexFromDpi
0x1400a7c56  mov     ecx, eax
0x1400a7c58  call    GetCursorSizeFromIndex
0x1400a7c5d  mov     ebx, eax
0x1400a7c5f  mov     r8d, [r13+4Ch]; c
0x1400a7c63  mov     edx, eax; b
0x1400a7c65  mov     ecx, [rsp+158h+b]; a
0x1400a7c69  call    cs:__imp_EngMulDiv
0x1400a7c70  nop     dword ptr [rax+rax+00h]
0x1400a7c75  mov     [rsp+158h+b], eax
0x1400a7c79  mov     r8d, [r13+4Ch]; c
0x1400a7c7d  mov     edx, ebx; b
0x1400a7c7f  mov     ecx, [rsp+158h+a]; a
0x1400a7c83  call    cs:__imp_EngMulDiv
  ... truncated ...
```
