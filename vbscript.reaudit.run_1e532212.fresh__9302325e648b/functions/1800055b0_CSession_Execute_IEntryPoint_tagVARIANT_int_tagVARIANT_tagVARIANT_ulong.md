# CSession::Execute(IEntryPoint *,tagVARIANT *,int,tagVARIANT *,tagVARIANT *,ulong)

- ea: `0x1800055b0`
- end: `0x180005deb`
- name: `?Execute@CSession@@QEAAJPEAVIEntryPoint@@PEAUtagVARIANT@@H11K@Z`
- size: `2107`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct IEntryPoint *, struct tagVARIANT *, int, struct tagVARIANT *, struct tagVARIANT *, unsigned int)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180018778`
- `0x1800385d0`
- `0x180058870`
- `0x180069010`

## callees

- `0x18000499c`
- `0x18000524c`
- `0x1800055b0`
- `0x180005e00`
- `0x180022b20`
- `0x180023868`
- `0x180028090`
- `0x180035468`
- `0x180035d84`
- `0x180045478`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!_controlfp` at `0x180005678`
- `msvcrt!_controlfp` at `0x18000568f`
- `msvcrt!_controlfp` at `0x180005960`
- `msvcrt!_controlfp` at `0x180005678`
- `msvcrt!_controlfp` at `0x18000568f`
- `msvcrt!_controlfp` at `0x180005960`
- `msvcrt!malloc` at `0x180005b3e`
- `msvcrt!malloc` at `0x180005b3e`
- `msvcrt!free` at `0x180005b15`
- `msvcrt!free` at `0x180005b15`
- `OLEAUT32!__imp_VariantCopy` at `0x1800057fa`
- `OLEAUT32!__imp_VariantCopy` at `0x18000584e`
- `OLEAUT32!__imp_VariantCopy` at `0x1800057fa`
- `OLEAUT32!__imp_VariantCopy` at `0x18000584e`
- `KERNEL32!TlsGetValue` at `0x1800056a8`
- `KERNEL32!TlsGetValue` at `0x180005753`
- `KERNEL32!TlsGetValue` at `0x1800058cc`
- `KERNEL32!TlsGetValue` at `0x1800056a8`
- `KERNEL32!TlsGetValue` at `0x180005753`
- `KERNEL32!TlsGetValue` at `0x1800058cc`

## pseudocode

```c
__int64 __fastcall CSession::Execute(
        CSession *this,
        struct IEntryPoint *a2,
        struct tagVARIANT *a3,
        int a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6,
        unsigned int a7)
{
  __int64 v10; // r14
  void (__fastcall **v11)(struct IEntryPoint *); // rax
  __int64 v12; // rax
  unsigned int v13; // ecx
  unsigned int v14; // r15d
  __int128 *v15; // rsi
  _QWORD *Value; // rax
  __int64 v17; // rbx
  unsigned int v18; // edi
  VARIANTARG *v19; // r8
  _OWORD *llVal; // rdx
  LONGLONG v21; // r9
  __int64 v22; // r15
  _QWORD *v23; // rax
  __int64 v24; // rdx
  signed int v25; // edi
  __int64 v26; // r10
  _OWORD *v27; // r9
  __int64 v28; // r8
  const VARIANTARG *v29; // rdx
  VARIANTARG *v30; // r8
  HRESULT v31; // edi
  struct tagVARIANT *v32; // rax
  const VARIANTARG *v33; // r15
  VARIANTARG *v34; // r8
  _OWORD *v35; // rdx
  LONGLONG v36; // r9
  int v37; // r14d
  GcBlockFactory *v38; // rax
  GcBlockFactory *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rbx
  int v42; // eax
  void *v43; // rsi
  struct VAR **v44; // rdx
  __int64 v46; // r10
  __int64 v47; // r11
  HRESULT v48; // eax
  __int64 v49; // r10
  __int64 v50; // r11
  struct tagVARIANT *v51; // rax
  struct VAR **v52; // rdx
  _DWORD *v53; // rcx
  __int64 v54; // rdx
  int v55; // edi
  _DWORD *v56; // rax
  int v57; // eax
  __int64 v58; // rsi
  __int64 v59; // r14
  __int64 v60; // rax
  __int64 v61; // xmm1_8
  bool v62; // zf
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rdx
  unsigned int v66; // edi
  unsigned int v67; // r9d
  FncInfo *v68; // rcx
  __int64 v69; // rax
  VARIANTARG *v70; // r8
  __int64 v71; // rax
  int v72; // edx
  void (__fastcall *v73)(__int64, _QWORD, VARIANTARG **, _QWORD, unsigned int, unsigned int, _QWORD); // rax
  __int64 v74; // rdx
  unsigned int v75; // r14d
  int v76; // r9d
  FncInfo *v77; // rcx
  __int64 v78; // rax
  VARIANTARG *v79; // r8
  __int64 v80; // rax
  int v81; // edx
  void (__fastcall *v82)(__int64, __int64, VARIANTARG **, _QWORD, int, unsigned int, _QWORD); // rax
  unsigned int NewValue[2]; // [rsp+40h] [rbp-91h] BYREF
  int v84; // [rsp+48h] [rbp-89h]
  CSession *v85; // [rsp+50h] [rbp-81h]
  VARIANTARG *pvargDest[2]; // [rsp+58h] [rbp-79h] BYREF
  VARIANTARG *v87; // [rsp+68h] [rbp-69h]
  struct tagVARIANT *v88; // [rsp+70h] [rbp-61h]
  __int64 v89; // [rsp+78h] [rbp-59h] BYREF
  __int64 v90; // [rsp+80h] [rbp-51h]
  struct tagVARIANT *v91; // [rsp+88h] [rbp-49h]
  VARIANTARG *pvargSrc[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v93; // [rsp+A0h] [rbp-31h]
  __int128 v94; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v95; // [rsp+C0h] [rbp-11h]

  v91 = a3;
  v88 = a5;
  pvargSrc[0] = a6;
  v10 = a4;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v85 = this;
  v95 = 0;
  v11 = *(void (__fastcall ***)(struct IEntryPoint *))a2;
  *(_OWORD *)pvargDest = 0;
  v87 = 0;
  v94 = 0;
  (*v11)(a2);
  v12 = *((_QWORD *)this + 4);
  v13 = (a7 >> 1) & 2 | 4;
  if ( (a7 & 8) == 0 )
    v13 = (a7 >> 1) & 2;
  LODWORD(v89) = v13;
  if ( v12 )
  {
    if ( *(_QWORD *)(v12 + 928) && v12 != -200 )
      JAmsi::JAmsiInitialize((JAmsi *)(v12 + 200));
    v14 = _controlfp(0, 0);
    NewValue[0] = v14;
    _controlfp(0x1Fu, 0x30F031Fu);
    v15 = &v94;
    if ( !a3 )
      v15 = 0;
    Value = TlsGetValue(g_luTls);
    if ( Value )
    {
      v17 = Value[4];
      v90 = v17;
      if ( v17 )
        v84 = *(_DWORD *)(v17 + 24);
      else
        v84 = 0;
    }
    else
    {
      v17 = 0;
      v90 = 0;
      v84 = 0;
    }
    if ( (int)v10 < 0 )
    {
      v31 = -2147024809;
      goto LABEL_35;
    }
    v18 = (a6 != 0) + (_DWORD)v10;
    if ( v18 < (unsigned int)v10 )
    {
      v31 = -2147467259;
      goto LABEL_35;
    }
    v19 = pvargDest[0];
    if ( pvargDest[0] )
    {
      llVal = (_OWORD *)pvargDest[0][1].llVal;
      v21 = pvargDest[0]->llVal;
      *(_OWORD *)&pvargDest[0][1].vt = *llVal;
      if ( llVal == (_OWORD *)(v21 + 8 * (3LL * *(int *)(v21 + 8) - 1)) )
      {
        v19->llVal = *(_QWORD *)v21;
        *(_QWORD *)v21 = v19->pRecInfo;
        v19->pRecInfo = (IRecordInfo *)v21;
      }
      v87 = 0;
      *(_OWORD *)pvargDest = 0;
    }
    if ( v18 )
    {
      v22 = *((_QWORD *)v85 + 25);
      if ( v22 || ((v23 = TlsGetValue(g_luTls)) == 0 ? (v22 = 0) : (v22 = v23[5]), v22) )
      {
        v24 = *(_QWORD *)(v22 + 8);
        v25 = v18 + 1;
        v26 = v22;
        if ( v24 )
        {
          v27 = (_OWORD *)(v22 + 24);
          v28 = **(_QWORD **)(v22 + 24);
          if ( (v28 - v24 - 16) / 24 >= v25 )
          {
LABEL_25:
            v29 = pvargSrc[0];
            v30 = (VARIANTARG *)(v28 - 24);
            pvargDest[1] = v30;
            *(_OWORD *)&v30->vt = *v27;
            *(_QWORD *)v27 = &pvargDest[1];
            *(_QWORD *)(v22 + 32) = v30;
            pvargDest[0] = (VARIANTARG *)v22;
            if ( !v29 )
              goto LABEL_29;
            --pvargDest[1];
            pvargDest[1]->vt = 0;
            v31 = VariantCopy(pvargDest[1], v29);
            if ( v31 >= 0 )
            {
              v31 = VAR::Import((VAR *)pvargDest[1]);
              if ( v31 >= 0 )
              {
                v87 = pvargDest[1];
LABEL_29:
                v32 = v88;
                v33 = &v88[v10];
                while ( v33 > v32 )
                {
                  --v33;
                  --pvargDest[1];
                  pvargDest[1]->vt = 0;
                  v31 = VariantCopy(pvargDest[1], v33);
                  if ( v31 < 0 )
                    goto LABEL_34;
                  v31 = VAR::Import((VAR *)pvargDest[1]);
                  if ( v31 < 0 )
                    goto LABEL_34;
                  v32 = v88;
                }
                v14 = NewValue[0];
                goto LABEL_57;
              }
            }
LABEL_34:
            v14 = NewValue[0];
LABEL_35:
            v34 = pvargDest[0];
            if ( pvargDest[0] )
            {
              v35 = (_OWORD *)pvargDest[0][1].llVal;
              v36 = pvargDest[0]->llVal;
              *(_OWORD *)&pvargDest[0][1].vt = *v35;
              if ( v35 == (_OWORD *)(v36 + 8 * (3LL * *(int *)(v36 + 8) - 1)) )
              {
                v34->llVal = *(_QWORD *)v36;
                *(_QWORD *)v36 = v34->pRecInfo;
                v34->pRecInfo = (IRecordInfo *)v36;
              }
              v87 = 0;
              *(_OWORD *)pvargDest = 0;
            }
            if ( v17 )
            {
              v37 = v84;
              if ( v84 < *(_DWORD *)(v17 + 24) )
              {
                v38 = (GcBlockFactory *)TlsGetValue(g_luTls);
                v39 = *(GcBlockFactory **)(v17 + 32);
                if ( v38 == v39 )
                {
                  if ( v39 )
                  {
                    v57 = *(_DWORD *)(v17 + 24);
                    v58 = *(_QWORD *)(v17 + 8) + 1200LL;
                    if ( v37 < v57 )
                    {
                      v59 = v90;
                      do
                      {
                        if ( *(_QWORD *)(v59 + 16) == v58 )
                        {
                          v62 = *(_QWORD *)v17 == 0;
                          v63 = *(_QWORD *)(v17 + 8);
                          v64 = *(_QWORD *)(v63 + 1200);
                          *(_QWORD *)(v17 + 8) = v64;
                          *(_QWORD *)(v59 + 16) = v64;
                          v58 = v64 + 1200;
                          if ( v62 )
                          {
                            *(_QWORD *)(v63 + 1200) = 0;
                            *(_QWORD *)v17 = v63;
                          }
                          else
                          {
                            GcBlockFactory::FreeBlk(v39, (struct GcBlock *)v63);
                          }
                        }
                        v60 = *(_QWORD *)(v59 + 16);
                        *(_OWORD *)pvargSrc = *(_OWORD *)v60;
                        v61 = *(_QWORD *)(v60 + 16);
                        --*(_DWORD *)(v17 + 24);
                        *(_QWORD *)(v59 + 16) = v60 + 24;
                        v93 = v61;
                        VAR::Clear((VAR *)pvargSrc);
                        v57 = *(_DWORD *)(v17 + 24);
                      }
                      while ( v84 < v57 );
                    }
                    if ( !v57 )
                      _InterlockedDecrement(&g_cLibRef);
                  }
                }
              }
            }
            v40 = *((_QWORD *)this + 4);
            if ( v40 )
            {
              if ( *(_QWORD *)(v40 + 928) )
              {
                v41 = v40 + 200;
                if ( v40 != -200 )
                {
                  v42 = *(_DWORD *)(v40 + 204);
                  if ( v42 )
                  {
                    if ( v42 == 1 )
                    {
                      v43 = *(void **)(v41 + 8);
                      if ( v43 )
                      {
                        RollingBuffer::~RollingBuffer(*(RollingBuffer **)(v41 + 8));
                        operator delete(v43);
                        v42 = *(_DWORD *)(v41 + 4);
                      }
                      *(_QWORD *)(v41 + 8) = 0;
                    }
                    *(_DWORD *)(v41 + 4) = v42 - 1;
                  }
                }
              }
            }
            (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)a2 + 8LL))(a2);
            if ( v31 < 0 && v91 )
              v91->vt = 0;
            _controlfp(v14, 0xFFFFFFFF);
            CSession::Release(v85);
            if ( pvargDest[0] )
              VarStack::PopMasterSp((VarStack *)pvargDest[0], v44);
            return (unsigned int)v31;
          }
        }
        while ( 1 )
        {
          v53 = *(_DWORD **)(v26 + 16);
          if ( !v53 )
            break;
          if ( v53[2] >= v25 )
            goto LABEL_73;
          *(_QWORD *)(v26 + 16) = *(_QWORD *)v53;
          free(v53);
          v26 = v22;
        }
        v55 = 2 * v25;
        if ( *(_DWORD *)v22 < v55 )
          *(_DWORD *)v22 = v55;
        else
          v55 = *(_DWORD *)v22;
        v56 = malloc(24LL * v55 + 40);
        *(_QWORD *)(v22 + 16) = v56;
        v26 = v22;
        if ( v56 )
        {
          v56[2] = v55;
          **(_QWORD **)(v22 + 16) = 0;
          *(_DWORD *)v22 *= 2;
LABEL_73:
          v54 = *(_QWORD *)(v26 + 16);
          v27 = (_OWORD *)(v22 + 24);
          *(_QWORD *)(v26 + 16) = *(_QWORD *)v54;
          *(_QWORD *)v54 = *(_QWORD *)(v22 + 8);
          *(_QWORD *)(v22 + 8) = v54;
          v28 = v54 + 8 * (*(int *)(v54 + 8) + 2 * (*(int *)(v54 + 8) + 1LL));
          goto LABEL_25;
        }
        pvargDest[1] = 0;
        v31 = -2147024882;
      }
      else
      {
        v31 = -2147467259;
      }
      v14 = NewValue[0];
    }
    else
    {
      v31 = 0;
    }
    if ( v31 >= 0 )
    {
LABEL_57:
      v46 = *((_QWORD *)this + 4);
      if ( v46 )
      {
        v47 = *(_QWORD *)(v46 + 904);
        if ( v47 )
        {
          v65 = *((_QWORD *)this + 9);
          v66 = 0;
          v67 = 0;
          NewValue[0] = 0;
          if ( v65 )
          {
            if ( *(_QWORD *)(v65 + 464) )
            {
              v68 = *(FncInfo **)(v65 + 40);
              if ( v68 )
              {
                v69 = *(_QWORD *)v68;
                if ( *(_QWORD *)v68 )
                {
                  v70 = *(VARIANTARG **)(v69 + 64);
                  v71 = *(_QWORD *)(v69 + 72);
                  pvargSrc[0] = v70;
                  v88 = (struct tagVARIANT *)(*(int *)&v70->vt + v71);
                  if ( v88 )
                  {
                    if ( pvargSrc[0]->decVal.Hi32 == 32 )
                    {
                      v72 = *(_DWORD *)(v65 + 488);
                      *(_QWORD *)NewValue = 0;
                      FncInfo::GetBos(v68, v72, (struct BOS *)NewValue);
                      v67 = NewValue[0];
                      NewValue[0] += NewValue[1];
                      v66 = *(_DWORD *)&v88->vt;
                    }
                  }
                }
              }
            }
          }
          v73 = *(void (__fastcall **)(__int64, _QWORD, VARIANTARG **, _QWORD, unsigned int, unsigned int, _QWORD))(*(_QWORD *)v47 + 24LL);
          *(_OWORD *)pvargSrc = *(_OWORD *)(v46 + 912);
          v73(v47, 0, pvargSrc, v66, v67, NewValue[0], 0);
        }
      }
      v48 = (*(__int64 (__fastcall **)(struct IEntryPoint *, __int128 *, _QWORD, VARIANTARG *, VARIANTARG *, _DWORD))(*(_QWORD *)a2 + 32LL))(
              a2,
              v15,
              (unsigned int)v10,
              pvargDest[1],
              v87,
              v89);
      v49 = *((_QWORD *)this + 4);
      v31 = v48;
      if ( v49 )
      {
        v50 = *(_QWORD *)(v49 + 904);
        if ( v50 )
        {
          v74 = *((_QWORD *)this + 9);
          v75 = 0;
          v76 = 0;
          if ( v74 )
          {
            NewValue[0] = 0;
            if ( *(_QWORD *)(v74 + 464) )
            {
              v77 = *(FncInfo **)(v74 + 40);
              if ( v77 )
              {
                v78 = *(_QWORD *)v77;
                if ( *(_QWORD *)v77 )
                {
                  v79 = *(VARIANTARG **)(v78 + 64);
                  v80 = *(_QWORD *)(v78 + 72);
                  pvargSrc[0] = v79;
                  v88 = (struct tagVARIANT *)(*(int *)&v79->vt + v80);
                  if ( v88 )
                  {
                    if ( pvargSrc[0]->decVal.Hi32 == 32 )
                    {
                      v81 = *(_DWORD *)(v74 + 488);
                      v89 = 0;
                      FncInfo::GetBos(v77, v81, (struct BOS *)&v89);
                      v76 = v89;
                      NewValue[0] = v89 + HIDWORD(v89);
                      v75 = *(_DWORD *)&v88->vt;
                    }
                  }
                }
              }
            }
          }
          else
          {
            NewValue[0] = 0;
          }
          v82 = *(void (__fastcall **)(__int64, __int64, VARIANTARG **, _QWORD, int, unsigned int, _QWORD))(*(_QWORD *)v50 + 24LL);
          *(_OWORD *)pvargSrc = *(_OWORD *)(v49 + 912);
          v82(v50, 1, pvargSrc, v75, v76, NewValue[0], 0);
        }
      }
      if ( v31 >= 0 )
      {
        v51 = v91;
        if ( v91 )
        {
          if ( *(_WORD *)v15 == 74 )
            v15 = (__int128 *)*((_QWORD *)v15 + 1);
          *(_OWORD *)&v91->vt = *v15;
          v51->pRecInfo = (IRecordInfo *)*((_QWORD *)v15 + 2);
          *(_WORD *)v15 = 0;
        }
      }
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)a2 + 8LL))(a2);
  CSession::Release(v85);
  if ( pvargDest[0] )
    VarStack::PopMasterSp((VarStack *)pvargDest[0], v52);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800055b0  push    rbp
0x1800055b2  push    rbx
0x1800055b3  push    rdi
0x1800055b4  push    r12
0x1800055b6  push    r13
0x1800055b8  push    r14
0x1800055ba  lea     rbp, [rsp-17h]
0x1800055bf  sub     rsp, 0E8h
0x1800055c6  mov     rax, cs:__security_cookie
0x1800055cd  xor     rax, rsp
0x1800055d0  mov     [rbp+3Fh+var_48], rax
0x1800055d4  mov     rax, [rbp+3Fh+arg_20]
0x1800055d8  mov     rbx, r8
0x1800055db  mov     rdi, [rbp+3Fh+arg_28]
0x1800055df  mov     r12, rdx
0x1800055e2  mov     [rbp+3Fh+var_88], rbx
0x1800055e6  mov     r13, rcx
0x1800055e9  mov     [rbp+3Fh+var_A0], rax
0x1800055ed  mov     [rbp+3Fh+pvargSrc], rdi
0x1800055f1  movsxd  r14, r9d
0x1800055f4  lock inc dword ptr [rcx+8]
0x1800055f8  xor     eax, eax
0x1800055fa  mov     [rsp+110h+var_C0], rcx
0x1800055ff  mov     [rbp+3Fh+var_50], rax
0x180005603  xorps   xmm0, xmm0
0x180005606  mov     rax, [rdx]
0x180005609  mov     rcx, rdx
0x18000560c  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x180005611  mov     [rbp+3Fh+var_A8], 0
0x180005619  movups  [rbp+3Fh+var_60], xmm0
0x18000561d  mov     rax, [rax]
0x180005620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005625  mov     edx, [rbp+3Fh+arg_30]
0x180005628  mov     rax, [r13+20h]
0x18000562c  shr     edx, 1
0x18000562e  and     edx, 2
0x180005631  mov     ecx, edx
0x180005633  or      ecx, 4
0x180005636  test    byte ptr [rbp+3Fh+arg_30], 8
0x18000563a  cmovz   ecx, edx
0x18000563d  mov     dword ptr [rbp+3Fh+var_98], ecx
0x180005640  test    rax, rax
0x180005643  jz      loc_180005A63
0x180005649  cmp     qword ptr [rax+3A0h], 0
0x180005651  mov     [rsp+110h+var_30], rsi
0x180005659  mov     [rsp+110h+var_38], r15
0x180005661  jz      short loc_180005674
0x180005663  lea     rcx, [rax+0C8h]; this
0x18000566a  test    rcx, rcx
0x18000566d  jz      short loc_180005674
0x18000566f  call    ?JAmsiInitialize@JAmsi@@QEAA_NXZ; JAmsi::JAmsiInitialize(void)
0x180005674  xor     edx, edx; Mask
0x180005676  xor     ecx, ecx; NewValue
0x180005678  call    cs:__imp__controlfp
0x18000567e  mov     edx, 30F031Fh; Mask
0x180005683  mov     ecx, 1Fh; NewValue
0x180005688  mov     r15d, eax
0x18000568b  mov     [rsp+110h+NewValue], eax
0x18000568f  call    cs:__imp__controlfp
0x180005695  xor     ecx, ecx
0x180005697  lea     rsi, [rbp+3Fh+var_60]
0x18000569b  test    rbx, rbx
0x18000569e  cmovz   rsi, rcx
0x1800056a2  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800056a8  call    cs:__imp_TlsGetValue
0x1800056ae  test    rax, rax
0x1800056b1  jz      loc_180005A94
0x1800056b7  mov     rbx, [rax+20h]
0x1800056bb  mov     [rbp+3Fh+var_90], rbx
0x1800056bf  test    rbx, rbx
0x1800056c2  jz      loc_180005AF7
0x1800056c8  mov     eax, [rbx+18h]
0x1800056cb  mov     [rsp+110h+var_C8], eax
0x1800056cf  test    r14d, r14d
0x1800056d2  js      loc_180005B04
0x1800056d8  xor     eax, eax
0x1800056da  test    rdi, rdi
0x1800056dd  setnz   al
0x1800056e0  lea     edi, [rax+r14]
0x1800056e4  cmp     edi, r14d
0x1800056e7  jb      loc_180005C20
0x1800056ed  mov     r8, [rbp+3Fh+pvargDest]
0x1800056f1  test    r8, r8
0x1800056f4  jz      short loc_180005734
0x1800056f6  mov     rdx, [r8+20h]
0x1800056fa  mov     r9, [r8+8]
0x1800056fe  movups  xmm0, xmmword ptr [rdx]
0x180005701  movups  xmmword ptr [r8+18h], xmm0
0x180005706  movsxd  rax, dword ptr [r9+8]
0x18000570a  lea     rax, [rax+rax*2]
0x18000570e  lea     rax, [rax-1]
0x180005712  lea     rax, [r9+rax*8]
0x180005716  cmp     rdx, rax
0x180005719  jz      loc_180005A4C
0x18000571f  xorps   xmm0, xmm0
0x180005722  mov     [rbp+3Fh+var_A8], 0
0x18000572a  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x18000572f  movq    [rbp+3Fh+pvargDest], xmm0
0x180005734  test    edi, edi
0x180005736  jz      loc_180005C2A
0x18000573c  mov     rax, [rsp+110h+var_C0]
0x180005741  mov     r15, [rax+0C8h]
0x180005748  test    r15, r15
0x18000574b  jnz     short loc_18000576F
0x18000574d  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180005753  call    cs:__imp_TlsGetValue
0x180005759  test    rax, rax
0x18000575c  jz      loc_180005A44
0x180005762  mov     r15, [rax+28h]
0x180005766  test    r15, r15
0x180005769  jz      loc_180005C2E
0x18000576f  mov     rdx, [r15+8]
0x180005773  inc     edi
0x180005775  mov     r10, r15
0x180005778  test    rdx, rdx
0x18000577b  jz      loc_180005AA3
0x180005781  mov     rax, [r15+18h]
0x180005785  lea     r9, [r15+18h]
0x180005789  mov     r8, [rax]
0x18000578c  mov     rax, 2AAAAAAAAAAAAAABh
0x180005796  mov     rcx, r8
0x180005799  sub     rcx, rdx
0x18000579c  sub     rcx, 10h
0x1800057a0  imul    rcx
0x1800057a3  sar     rdx, 2
0x1800057a7  mov     rax, rdx
0x1800057aa  shr     rax, 3Fh
0x1800057ae  add     rdx, rax
0x1800057b1  movsxd  rax, edi
0x1800057b4  cmp     rdx, rax
0x1800057b7  jl      loc_180005AA3
0x1800057bd  mov     rdx, [rbp+3Fh+pvargSrc]; pvargSrc
0x1800057c1  lea     rax, [rbp+3Fh+pvargDest+8]
0x1800057c5  sub     r8, 18h
0x1800057c9  mov     [rbp+3Fh+pvargDest+8], r8
0x1800057cd  movups  xmm0, xmmword ptr [r9]
0x1800057d1  movups  xmmword ptr [r8], xmm0
0x1800057d5  mov     [r9], rax
0x1800057d8  mov     [r15+20h], r8
0x1800057dc  mov     [rbp+3Fh+pvargDest], r15
0x1800057e0  test    rdx, rdx
0x1800057e3  jz      short loc_18000581D
0x1800057e5  mov     rcx, [rbp+3Fh+pvargDest+8]
0x1800057e9  xor     eax, eax
0x1800057eb  sub     rcx, 18h
0x1800057ef  mov     [rbp+3Fh+pvargDest+8], rcx
0x1800057f3  mov     [rcx], ax
0x1800057f6  mov     rcx, [rbp+3Fh+pvargDest+8]; pvargDest
0x1800057fa  call    cs:__imp_VariantCopy
0x180005800  mov     edi, eax
0x180005802  test    eax, eax
0x180005804  js      short loc_18000586F
0x180005806  mov     rcx, [rbp+3Fh+pvargDest+8]; this
0x18000580a  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18000580f  mov     edi, eax
0x180005811  test    eax, eax
0x180005813  js      short loc_18000586F
0x180005815  mov     rax, [rbp+3Fh+pvargDest+8]
0x180005819  mov     [rbp+3Fh+var_A8], rax
0x18000581d  mov     rax, [rbp+3Fh+var_A0]
0x180005821  lea     rcx, [r14+r14*2]
0x180005825  lea     r15, [rax+rcx*8]
0x180005829  cmp     r15, rax
0x18000582c  jbe     loc_1800059A4
0x180005832  mov     rcx, [rbp+3Fh+pvargDest+8]
0x180005836  xor     eax, eax
0x180005838  sub     rcx, 18h
0x18000583c  sub     r15, 18h
0x180005840  mov     [rbp+3Fh+pvargDest+8], rcx
0x180005844  mov     rdx, r15; pvargSrc
0x180005847  mov     [rcx], ax
0x18000584a  mov     rcx, [rbp+3Fh+pvargDest+8]; pvargDest
0x18000584e  call    cs:__imp_VariantCopy
0x180005854  mov     edi, eax
0x180005856  test    eax, eax
0x180005858  js      short loc_18000586F
0x18000585a  mov     rcx, [rbp+3Fh+pvargDest+8]; this
0x18000585e  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x180005863  mov     edi, eax
0x180005865  test    eax, eax
0x180005867  js      short loc_18000586F
0x180005869  mov     rax, [rbp+3Fh+var_A0]
0x18000586d  jmp     short loc_180005829
0x18000586f  mov     r15d, [rsp+110h+NewValue]
0x180005874  mov     r8, [rbp+3Fh+pvargDest]
0x180005878  test    r8, r8
0x18000587b  jz      short loc_1800058B6
0x18000587d  mov     rdx, [r8+20h]
0x180005881  mov     r9, [r8+8]
0x180005885  movups  xmm0, xmmword ptr [rdx]
0x180005888  movups  xmmword ptr [r8+18h], xmm0
0x18000588d  movsxd  rax, dword ptr [r9+8]
0x180005891  lea     rax, [rax+rax*2]
0x180005895  lea     rax, [rax-1]
0x180005899  lea     rax, [r9+rax*8]
0x18000589d  cmp     rdx, rax
0x1800058a0  jz      loc_180005AE0
0x1800058a6  xorps   xmm0, xmm0
0x1800058a9  mov     [rbp+3Fh+var_A8], 0
0x1800058b1  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x1800058b6  test    rbx, rbx
0x1800058b9  jz      short loc_1800058E4
0x1800058bb  mov     r14d, [rsp+110h+var_C8]
0x1800058c0  cmp     r14d, [rbx+18h]
0x1800058c4  jge     short loc_1800058E4
0x1800058c6  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800058cc  call    cs:__imp_TlsGetValue
0x1800058d2  mov     rcx, [rbx+20h]; this
0x1800058d6  cmp     rax, rcx
0x1800058d9  jnz     short loc_1800058E4
0x1800058db  test    rcx, rcx
0x1800058de  jnz     loc_180005B6F
0x1800058e4  mov     rax, [r13+20h]
0x1800058e8  test    rax, rax
0x1800058eb  jz      short loc_180005938
0x1800058ed  cmp     qword ptr [rax+3A0h], 0
0x1800058f5  jz      short loc_180005938
0x1800058f7  lea     rbx, [rax+0C8h]
0x1800058fe  test    rbx, rbx
0x180005901  jz      short loc_180005938
0x180005903  mov     eax, [rbx+4]
0x180005906  test    eax, eax
0x180005908  jz      short loc_180005938
0x18000590a  cmp     eax, 1
0x18000590d  jnz     short loc_180005933
0x18000590f  mov     rsi, [rbx+8]
0x180005913  test    rsi, rsi
0x180005916  jz      short loc_18000592B
0x180005918  mov     rcx, rsi; this
0x18000591b  call    ??1RollingBuffer@@QEAA@XZ; RollingBuffer::~RollingBuffer(void)
0x180005920  mov     rcx, rsi; Block
0x180005923  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005928  mov     eax, [rbx+4]
0x18000592b  mov     qword ptr [rbx+8], 0
0x180005933  dec     eax
0x180005935  mov     [rbx+4], eax
0x180005938  mov     rax, [r12]
0x18000593c  mov     rcx, r12
0x18000593f  mov     rax, [rax+8]
0x180005943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005948  mov     rsi, [rsp+110h+var_30]
0x180005950  test    edi, edi
0x180005952  js      loc_180005DCA
0x180005958  mov     edx, 0FFFFFFFFh; Mask
0x18000595d  mov     ecx, r15d; NewValue
0x180005960  call    cs:__imp__controlfp
0x180005966  mov     rcx, [rsp+110h+var_C0]; this
0x18000596b  call    ?Release@CSession@@QEAAXXZ; CSession::Release(void)
0x180005970  mov     rcx, [rbp+3Fh+pvargDest]; this
0x180005974  mov     r15, [rsp+110h+var_38]
0x18000597c  test    rcx, rcx
0x18000597f  jnz     loc_180005DE1
0x180005985  mov     eax, edi
0x180005987  mov     rcx, [rbp+3Fh+var_48]
0x18000598b  xor     rcx, rsp; StackCookie
0x18000598e  call    __security_check_cookie
0x180005993  add     rsp, 0E8h
0x18000599a  pop     r14
0x18000599c  pop     r13
0x18000599e  pop     r12
0x1800059a0  pop     rdi
0x1800059a1  pop     rbx
0x1800059a2  pop     rbp
0x1800059a3  retn
0x1800059a4  mov     r15d, [rsp+110h+NewValue]
0x1800059a9  mov     r10, [r13+20h]
0x1800059ad  test    r10, r10
0x1800059b0  jz      short loc_1800059C2
0x1800059b2  mov     r11, [r10+388h]
0x1800059b9  test    r11, r11
0x1800059bc  jnz     loc_180005C51
0x1800059c2  mov     rax, [r12]
0x1800059c6  mov     r8d, r14d
0x1800059c9  mov     ecx, dword ptr [rbp+3Fh+var_98]
0x1800059cc  mov     rdx, rsi
0x1800059cf  mov     r9, [rbp+3Fh+pvargDest+8]
0x1800059d3  mov     [rsp+110h+var_E8], ecx
0x1800059d7  mov     rcx, [rbp+3Fh+var_A8]
0x1800059db  mov     rax, [rax+20h]
0x1800059df  mov     [rsp+110h+var_F0], rcx
0x1800059e4  mov     rcx, r12
0x1800059e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ec  mov     r10, [r13+20h]
0x1800059f0  mov     edi, eax
0x1800059f2  test    r10, r10
0x1800059f5  jz      short loc_180005A07
0x1800059f7  mov     r11, [r10+388h]
0x1800059fe  test    r11, r11
0x180005a01  jnz     loc_180005D09
0x180005a07  test    edi, edi
0x180005a09  js      loc_180005874
0x180005a0f  mov     rax, [rbp+3Fh+var_88]
0x180005a13  test    rax, rax
0x180005a16  jz      loc_180005874
0x180005a1c  mov     ecx, 4Ah ; 'J'
0x180005a21  cmp     cx, [rsi]
0x180005a24  jnz     short loc_180005A2A
0x180005a26  mov     rsi, [rsi+8]
0x180005a2a  movups  xmm0, xmmword ptr [rsi]
0x180005a2d  movups  xmmword ptr [rax], xmm0
  ... truncated ...
```
