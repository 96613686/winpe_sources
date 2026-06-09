# CSession::Execute(IEntryPoint *,tagVARIANT *,int,tagVARIANT *,tagVARIANT *,ulong)

- ea: `0x1800033b0`
- end: `0x180003c2b`
- name: `?Execute@CSession@@QEAAJPEAVIEntryPoint@@PEAUtagVARIANT@@H11K@Z`
- size: `2171`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct IEntryPoint *, struct tagVARIANT *, int, struct tagVARIANT *, struct tagVARIANT *, unsigned int)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180001cb0`
- `0x180013328`
- `0x18005a370`
- `0x18006b150`

## callees

- `0x180001970`
- `0x180002e84`
- `0x180003028`
- `0x1800033b0`
- `0x180003c40`
- `0x18001ec7c`
- `0x18001ed10`
- `0x180036970`
- `0x180036c18`
- `0x18004686c`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!_controlfp` at `0x180003478`
- `msvcrt!_controlfp` at `0x180003495`
- `msvcrt!_controlfp` at `0x18000378a`
- `msvcrt!_controlfp` at `0x180003478`
- `msvcrt!_controlfp` at `0x180003495`
- `msvcrt!_controlfp` at `0x18000378a`
- `msvcrt!malloc` at `0x180003978`
- `msvcrt!malloc` at `0x180003978`
- `msvcrt!free` at `0x180003946`
- `msvcrt!free` at `0x180003946`
- `OLEAUT32!__imp_VariantCopy` at `0x180003612`
- `OLEAUT32!__imp_VariantCopy` at `0x18000366c`
- `OLEAUT32!__imp_VariantCopy` at `0x180003612`
- `OLEAUT32!__imp_VariantCopy` at `0x18000366c`
- `KERNEL32!TlsGetValue` at `0x1800034b4`
- `KERNEL32!TlsGetValue` at `0x180003565`
- `KERNEL32!TlsGetValue` at `0x1800036f0`
- `KERNEL32!TlsGetValue` at `0x1800034b4`
- `KERNEL32!TlsGetValue` at `0x180003565`
- `KERNEL32!TlsGetValue` at `0x1800036f0`

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
0x1800033b0  push    rbp
0x1800033b2  push    rbx
0x1800033b3  push    rdi
0x1800033b4  push    r12
0x1800033b6  push    r13
0x1800033b8  push    r14
0x1800033ba  lea     rbp, [rsp-17h]
0x1800033bf  sub     rsp, 0E8h
0x1800033c6  mov     rax, cs:__security_cookie
0x1800033cd  xor     rax, rsp
0x1800033d0  mov     [rbp+3Fh+var_48], rax
0x1800033d4  mov     rax, [rbp+3Fh+arg_20]
0x1800033d8  mov     rbx, r8
0x1800033db  mov     rdi, [rbp+3Fh+arg_28]
0x1800033df  mov     r12, rdx
0x1800033e2  mov     [rbp+3Fh+var_88], rbx
0x1800033e6  mov     r13, rcx
0x1800033e9  mov     [rbp+3Fh+var_A0], rax
0x1800033ed  mov     [rbp+3Fh+pvargSrc], rdi
0x1800033f1  movsxd  r14, r9d
0x1800033f4  lock inc dword ptr [rcx+8]
0x1800033f8  xor     eax, eax
0x1800033fa  mov     [rsp+110h+var_C0], rcx
0x1800033ff  mov     [rbp+3Fh+var_50], rax
0x180003403  xorps   xmm0, xmm0
0x180003406  mov     rax, [rdx]
0x180003409  mov     rcx, rdx
0x18000340c  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x180003411  mov     [rbp+3Fh+var_A8], 0
0x180003419  movups  [rbp+3Fh+var_60], xmm0
0x18000341d  mov     rax, [rax]
0x180003420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003425  mov     edx, [rbp+3Fh+arg_30]
0x180003428  mov     rax, [r13+20h]
0x18000342c  shr     edx, 1
0x18000342e  and     edx, 2
0x180003431  mov     ecx, edx
0x180003433  or      ecx, 4
0x180003436  test    byte ptr [rbp+3Fh+arg_30], 8
0x18000343a  cmovz   ecx, edx
0x18000343d  mov     dword ptr [rbp+3Fh+var_98], ecx
0x180003440  test    rax, rax
0x180003443  jz      loc_180003894
0x180003449  cmp     qword ptr [rax+3A0h], 0
0x180003451  mov     [rsp+110h+var_30], rsi
0x180003459  mov     [rsp+110h+var_38], r15
0x180003461  jz      short loc_180003474
0x180003463  lea     rcx, [rax+0C8h]; this
0x18000346a  test    rcx, rcx
0x18000346d  jz      short loc_180003474
0x18000346f  call    ?JAmsiInitialize@JAmsi@@QEAA_NXZ; JAmsi::JAmsiInitialize(void)
0x180003474  xor     edx, edx; Mask
0x180003476  xor     ecx, ecx; NewValue
0x180003478  call    cs:__imp__controlfp
0x18000347f  nop     dword ptr [rax+rax+00h]
0x180003484  mov     edx, 30F031Fh; Mask
0x180003489  mov     ecx, 1Fh; NewValue
0x18000348e  mov     r15d, eax
0x180003491  mov     [rsp+110h+NewValue], eax
0x180003495  call    cs:__imp__controlfp
0x18000349c  nop     dword ptr [rax+rax+00h]
0x1800034a1  xor     ecx, ecx
0x1800034a3  lea     rsi, [rbp+3Fh+var_60]
0x1800034a7  test    rbx, rbx
0x1800034aa  cmovz   rsi, rcx
0x1800034ae  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800034b4  call    cs:__imp_TlsGetValue
0x1800034bb  nop     dword ptr [rax+rax+00h]
0x1800034c0  test    rax, rax
0x1800034c3  jz      loc_1800038C5
0x1800034c9  mov     rbx, [rax+20h]
0x1800034cd  mov     [rbp+3Fh+var_90], rbx
0x1800034d1  test    rbx, rbx
0x1800034d4  jz      loc_180003928
0x1800034da  mov     eax, [rbx+18h]
0x1800034dd  mov     [rsp+110h+var_C8], eax
0x1800034e1  test    r14d, r14d
0x1800034e4  js      loc_180003935
0x1800034ea  xor     eax, eax
0x1800034ec  test    rdi, rdi
0x1800034ef  setnz   al
0x1800034f2  lea     edi, [rax+r14]
0x1800034f6  cmp     edi, r14d
0x1800034f9  jb      loc_180003A60
0x1800034ff  mov     r8, [rbp+3Fh+pvargDest]
0x180003503  test    r8, r8
0x180003506  jz      short loc_180003546
0x180003508  mov     rdx, [r8+20h]
0x18000350c  mov     r9, [r8+8]
0x180003510  movups  xmm0, xmmword ptr [rdx]
0x180003513  movups  xmmword ptr [r8+18h], xmm0
0x180003518  movsxd  rax, dword ptr [r9+8]
0x18000351c  lea     rax, [rax+rax*2]
0x180003520  lea     rax, [rax-1]
0x180003524  lea     rax, [r9+rax*8]
0x180003528  cmp     rdx, rax
0x18000352b  jz      loc_18000387D
0x180003531  xorps   xmm0, xmm0
0x180003534  mov     [rbp+3Fh+var_A8], 0
0x18000353c  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x180003541  movq    [rbp+3Fh+pvargDest], xmm0
0x180003546  test    edi, edi
0x180003548  jz      loc_180003A6A
0x18000354e  mov     rax, [rsp+110h+var_C0]
0x180003553  mov     r15, [rax+0C8h]
0x18000355a  test    r15, r15
0x18000355d  jnz     short loc_180003587
0x18000355f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180003565  call    cs:__imp_TlsGetValue
0x18000356c  nop     dword ptr [rax+rax+00h]
0x180003571  test    rax, rax
0x180003574  jz      loc_180003875
0x18000357a  mov     r15, [rax+28h]
0x18000357e  test    r15, r15
0x180003581  jz      loc_180003A6E
0x180003587  mov     rdx, [r15+8]
0x18000358b  inc     edi
0x18000358d  mov     r10, r15
0x180003590  test    rdx, rdx
0x180003593  jz      loc_1800038D4
0x180003599  mov     rax, [r15+18h]
0x18000359d  lea     r9, [r15+18h]
0x1800035a1  mov     r8, [rax]
0x1800035a4  mov     rax, 2AAAAAAAAAAAAAABh
0x1800035ae  mov     rcx, r8
0x1800035b1  sub     rcx, rdx
0x1800035b4  sub     rcx, 10h
0x1800035b8  imul    rcx
0x1800035bb  sar     rdx, 2
0x1800035bf  mov     rax, rdx
0x1800035c2  shr     rax, 3Fh
0x1800035c6  add     rdx, rax
0x1800035c9  movsxd  rax, edi
0x1800035cc  cmp     rdx, rax
0x1800035cf  jl      loc_1800038D4
0x1800035d5  mov     rdx, [rbp+3Fh+pvargSrc]; pvargSrc
0x1800035d9  lea     rax, [rbp+3Fh+pvargDest+8]
0x1800035dd  sub     r8, 18h
0x1800035e1  mov     [rbp+3Fh+pvargDest+8], r8
0x1800035e5  movups  xmm0, xmmword ptr [r9]
0x1800035e9  movups  xmmword ptr [r8], xmm0
0x1800035ed  mov     [r9], rax
0x1800035f0  mov     [r15+20h], r8
0x1800035f4  mov     [rbp+3Fh+pvargDest], r15
0x1800035f8  test    rdx, rdx
0x1800035fb  jz      short loc_18000363B
0x1800035fd  mov     rcx, [rbp+3Fh+pvargDest+8]
0x180003601  xor     eax, eax
0x180003603  sub     rcx, 18h
0x180003607  mov     [rbp+3Fh+pvargDest+8], rcx
0x18000360b  mov     [rcx], ax
0x18000360e  mov     rcx, [rbp+3Fh+pvargDest+8]; pvargDest
0x180003612  call    cs:__imp_VariantCopy
0x180003619  nop     dword ptr [rax+rax+00h]
0x18000361e  mov     edi, eax
0x180003620  test    eax, eax
0x180003622  js      short loc_180003693
0x180003624  mov     rcx, [rbp+3Fh+pvargDest+8]; this
0x180003628  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18000362d  mov     edi, eax
0x18000362f  test    eax, eax
0x180003631  js      short loc_180003693
0x180003633  mov     rax, [rbp+3Fh+pvargDest+8]
0x180003637  mov     [rbp+3Fh+var_A8], rax
0x18000363b  mov     rax, [rbp+3Fh+var_A0]
0x18000363f  lea     rcx, [r14+r14*2]
0x180003643  lea     r15, [rax+rcx*8]
0x180003647  cmp     r15, rax
0x18000364a  jbe     loc_1800037D5
0x180003650  mov     rcx, [rbp+3Fh+pvargDest+8]
0x180003654  xor     eax, eax
0x180003656  sub     rcx, 18h
0x18000365a  sub     r15, 18h
0x18000365e  mov     [rbp+3Fh+pvargDest+8], rcx
0x180003662  mov     rdx, r15; pvargSrc
0x180003665  mov     [rcx], ax
0x180003668  mov     rcx, [rbp+3Fh+pvargDest+8]; pvargDest
0x18000366c  call    cs:__imp_VariantCopy
0x180003673  nop     dword ptr [rax+rax+00h]
0x180003678  mov     edi, eax
0x18000367a  test    eax, eax
0x18000367c  js      short loc_180003693
0x18000367e  mov     rcx, [rbp+3Fh+pvargDest+8]; this
0x180003682  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x180003687  mov     edi, eax
0x180003689  test    eax, eax
0x18000368b  js      short loc_180003693
0x18000368d  mov     rax, [rbp+3Fh+var_A0]
0x180003691  jmp     short loc_180003647
0x180003693  mov     r15d, [rsp+110h+NewValue]
0x180003698  mov     r8, [rbp+3Fh+pvargDest]
0x18000369c  test    r8, r8
0x18000369f  jz      short loc_1800036DA
0x1800036a1  mov     rdx, [r8+20h]
0x1800036a5  mov     r9, [r8+8]
0x1800036a9  movups  xmm0, xmmword ptr [rdx]
0x1800036ac  movups  xmmword ptr [r8+18h], xmm0
0x1800036b1  movsxd  rax, dword ptr [r9+8]
0x1800036b5  lea     rax, [rax+rax*2]
0x1800036b9  lea     rax, [rax-1]
0x1800036bd  lea     rax, [r9+rax*8]
0x1800036c1  cmp     rdx, rax
0x1800036c4  jz      loc_180003911
0x1800036ca  xorps   xmm0, xmm0
0x1800036cd  mov     [rbp+3Fh+var_A8], 0
0x1800036d5  movdqu  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x1800036da  test    rbx, rbx
0x1800036dd  jz      short loc_18000370E
0x1800036df  mov     r14d, [rsp+110h+var_C8]
0x1800036e4  cmp     r14d, [rbx+18h]
0x1800036e8  jge     short loc_18000370E
0x1800036ea  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800036f0  call    cs:__imp_TlsGetValue
0x1800036f7  nop     dword ptr [rax+rax+00h]
0x1800036fc  mov     rcx, [rbx+20h]; this
0x180003700  cmp     rax, rcx
0x180003703  jnz     short loc_18000370E
0x180003705  test    rcx, rcx
0x180003708  jnz     loc_1800039AF
0x18000370e  mov     rax, [r13+20h]
0x180003712  test    rax, rax
0x180003715  jz      short loc_180003762
0x180003717  cmp     qword ptr [rax+3A0h], 0
0x18000371f  jz      short loc_180003762
0x180003721  lea     rbx, [rax+0C8h]
0x180003728  test    rbx, rbx
0x18000372b  jz      short loc_180003762
0x18000372d  mov     eax, [rbx+4]
0x180003730  test    eax, eax
0x180003732  jz      short loc_180003762
0x180003734  cmp     eax, 1
0x180003737  jnz     short loc_18000375D
0x180003739  mov     rsi, [rbx+8]
0x18000373d  test    rsi, rsi
0x180003740  jz      short loc_180003755
0x180003742  mov     rcx, rsi; this
0x180003745  call    ??1RollingBuffer@@QEAA@XZ; RollingBuffer::~RollingBuffer(void)
0x18000374a  mov     rcx, rsi; Block
0x18000374d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003752  mov     eax, [rbx+4]
0x180003755  mov     qword ptr [rbx+8], 0
0x18000375d  dec     eax
0x18000375f  mov     [rbx+4], eax
0x180003762  mov     rax, [r12]
0x180003766  mov     rcx, r12
0x180003769  mov     rax, [rax+8]
0x18000376d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003772  mov     rsi, [rsp+110h+var_30]
0x18000377a  test    edi, edi
0x18000377c  js      loc_180003C0A
0x180003782  mov     edx, 0FFFFFFFFh; Mask
0x180003787  mov     ecx, r15d; NewValue
0x18000378a  call    cs:__imp__controlfp
0x180003791  nop     dword ptr [rax+rax+00h]
0x180003796  mov     rcx, [rsp+110h+var_C0]; this
0x18000379b  call    ?Release@CSession@@QEAAXXZ; CSession::Release(void)
0x1800037a0  mov     rcx, [rbp+3Fh+pvargDest]; this
0x1800037a4  mov     r15, [rsp+110h+var_38]
0x1800037ac  test    rcx, rcx
0x1800037af  jnz     loc_180003C21
0x1800037b5  mov     eax, edi
0x1800037b7  mov     rcx, [rbp+3Fh+var_48]
0x1800037bb  xor     rcx, rsp; StackCookie
0x1800037be  call    __security_check_cookie
0x1800037c3  add     rsp, 0E8h
0x1800037ca  pop     r14
0x1800037cc  pop     r13
0x1800037ce  pop     r12
0x1800037d0  pop     rdi
0x1800037d1  pop     rbx
0x1800037d2  pop     rbp
0x1800037d3  retn
0x1800037d5  mov     r15d, [rsp+110h+NewValue]
0x1800037da  mov     r10, [r13+20h]
0x1800037de  test    r10, r10
0x1800037e1  jz      short loc_1800037F3
0x1800037e3  mov     r11, [r10+388h]
0x1800037ea  test    r11, r11
0x1800037ed  jnz     loc_180003A91
0x1800037f3  mov     rax, [r12]
0x1800037f7  mov     r8d, r14d
0x1800037fa  mov     ecx, dword ptr [rbp+3Fh+var_98]
0x1800037fd  mov     rdx, rsi
0x180003800  mov     r9, [rbp+3Fh+pvargDest+8]
0x180003804  mov     [rsp+110h+var_E8], ecx
0x180003808  mov     rcx, [rbp+3Fh+var_A8]
0x18000380c  mov     rax, [rax+20h]
0x180003810  mov     [rsp+110h+var_F0], rcx
0x180003815  mov     rcx, r12
0x180003818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381d  mov     r10, [r13+20h]
0x180003821  mov     edi, eax
0x180003823  test    r10, r10
0x180003826  jz      short loc_180003838
0x180003828  mov     r11, [r10+388h]
0x18000382f  test    r11, r11
0x180003832  jnz     loc_180003B49
0x180003838  test    edi, edi
0x18000383a  js      loc_180003698
0x180003840  mov     rax, [rbp+3Fh+var_88]
  ... truncated ...
```
