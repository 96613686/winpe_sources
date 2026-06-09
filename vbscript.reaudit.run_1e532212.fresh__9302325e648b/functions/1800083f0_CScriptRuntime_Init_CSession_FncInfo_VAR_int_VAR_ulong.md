# CScriptRuntime::Init(CSession *,FncInfo *,VAR *,int,VAR *,ulong)

- ea: `0x1800083f0`
- end: `0x180008cb4`
- name: `?Init@CScriptRuntime@@QEAAJPEAVCSession@@PEAVFncInfo@@PEAVVAR@@H2K@Z`
- size: `2244`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct CSession *, struct FncInfo *, struct VAR *, int, struct VAR *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180009c90`

## callees

- `0x1800083f0`
- `0x180008fc0`
- `0x180020a50`
- `0x180022b20`
- `0x180022f20`
- `0x18002b490`
- `0x18002bc28`
- `0x18003c368`
- `0x180045490`
- `0x18005be54`
- `0x18006969c`
- `0x18007672e`
- `0x18007673a`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!malloc` at `0x180008a18`
- `msvcrt!malloc` at `0x180008a18`
- `msvcrt!free` at `0x1800089f0`
- `msvcrt!free` at `0x1800089f0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800089ba`
- `OLEAUT32!__imp_VariantCopy` at `0x1800089ba`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000891f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000891f`
- `KERNEL32!TlsGetValue` at `0x1800084a0`
- `KERNEL32!TlsGetValue` at `0x18000870a`
- `KERNEL32!TlsGetValue` at `0x1800084a0`
- `KERNEL32!TlsGetValue` at `0x18000870a`

## pseudocode

```c
__int64 __fastcall CScriptRuntime::Init(
        CScriptRuntime *this,
        struct CSession *a2,
        struct FncInfo *a3,
        struct VAR *a4,
        int a5,
        VARIANTARG *a6,
        __int16 a7)
{
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // edx
  _QWORD *Value; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // ecx
  struct CSession *v22; // rdi
  __int64 v23; // rax
  unsigned int v24; // esi
  LONGLONG llVal; // rax
  unsigned int v26; // ecx
  CScriptRuntime *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  VAR *v30; // r12
  int v31; // r15d
  VARIANTARG *v32; // rdi
  int vt; // eax
  VAR *v34; // r13
  int v35; // ecx
  __int64 v36; // rdx
  int v37; // r14d
  __int64 v38; // rdi
  _QWORD *v39; // rax
  __int64 v40; // rdx
  int v41; // esi
  __int64 v42; // r8
  _OWORD *v43; // r8
  _WORD *v44; // rax
  __int64 v45; // rcx
  size_t v46; // r8
  void *v47; // rcx
  __int64 v48; // rax
  __int64 result; // rax
  HRESULT v50; // esi
  __int64 v51; // rcx
  __int64 v52; // rcx
  LONGLONG v53; // rax
  _DWORD *v54; // rcx
  __int64 v55; // rdx
  IRecordInfo *pRecInfo; // xmm1_8
  int v57; // esi
  _DWORD *v58; // rax
  COleScript *v59; // rcx
  int v60; // eax
  int v61; // eax
  __int64 v62; // r15
  int v63; // edx
  int v64; // edi
  int v65; // edi
  char *v66; // rax
  __int64 v67; // r8
  _DWORD *v68; // rax
  int v69; // r13d
  int v70; // r9d
  int v71; // eax
  __int64 v72; // r10
  __int64 v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v75; // rax
  __int64 v76; // [rsp+20h] [rbp-68h] BYREF
  char *v77; // [rsp+28h] [rbp-60h]
  VARIANTARG pvargDest; // [rsp+30h] [rbp-58h] BYREF

  if ( !(unsigned int)FStackAvailable(0x10000u) )
    return 2148139036LL;
  v11 = *((_QWORD *)a2 + 4);
  *((_QWORD *)this + 1) = v11;
  if ( !v11 || !*(_DWORD *)(v11 + 256) )
  {
    result = 2147549183LL;
    *((_QWORD *)this + 1) = 0;
    return result;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 148));
  *(_QWORD *)this = a2;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  v12 = *(_QWORD *)this;
  v13 = *(_QWORD *)(*(_QWORD *)this + 72LL);
  *((_QWORD *)this + 2) = v13;
  if ( v13 )
    v14 = *(_DWORD *)(v13 + 24) + 1;
  else
    v14 = 1;
  *((_DWORD *)this + 6) = v14;
  *((_QWORD *)this + 4) = *(_QWORD *)(v12 + 192);
  *((_QWORD *)this + 5) = a3;
  Value = TlsGetValue(g_luTls);
  if ( !Value )
  {
    *((_QWORD *)this + 6) = 0;
    goto LABEL_60;
  }
  v16 = Value[4];
  *((_QWORD *)this + 6) = v16;
  if ( !v16 )
  {
LABEL_60:
    v50 = -2147467259;
    goto LABEL_40;
  }
  v17 = *((_QWORD *)this + 5);
  *((_DWORD *)this + 14) = *(_DWORD *)(v16 + 24);
  *((_QWORD *)this + 60) = *(_QWORD *)(v17 + 8) + *(int *)(*(_QWORD *)(v17 + 16) + 8LL);
  *((_QWORD *)this + 62) = *(_QWORD *)(v17 + 8);
  v18 = *((_QWORD *)this + 2);
  if ( v18 && (*(_BYTE *)(v18 + 504) & 3) != 0 )
    v19 = 2;
  else
    v19 = 0;
  *((_DWORD *)this + 126) &= 0xFFFFFFFC;
  *((_DWORD *)this + 126) |= v19;
  v20 = *((_DWORD *)this + 126) & 0xFFFFFFFB | ~(unsigned __int8)(*(_DWORD *)(*(_QWORD *)(v17 + 16) + 44LL) >> 11) & 4;
  *((_DWORD *)this + 126) = v20;
  v21 = v20 & 0xFFFFFFF7 | ~(8 * (unsigned __int8)*(_DWORD *)(*(_QWORD *)(v17 + 16) + 24LL)) & 8;
  *((_DWORD *)this + 126) = v21;
  if ( (v21 & 8) == 0 && (*(_DWORD *)(*(_QWORD *)(v17 + 16) + 44LL) & 0x8000) == 0 )
  {
    v59 = (COleScript *)*((_QWORD *)this + 1);
    v60 = *((_DWORD *)v59 + 66);
    if ( (v60 & 2) == 0 )
    {
      v61 = v60 | 2;
      *((_DWORD *)v59 + 66) = v61;
      if ( (v61 & 4) == 0 && (unsigned int)(*((_DWORD *)v59 + 39) - 2) <= 1 )
        COleScript::SinkEvents(v59);
    }
  }
  v22 = *(struct CSession **)this;
  if ( !*(_QWORD *)(*(_QWORD *)this + 32LL) )
    return (unsigned int)-2147418113;
  v23 = *((_QWORD *)this + 5);
  *(_OWORD *)&pvargDest.vt = 0;
  v24 = *(_DWORD *)(v23 + 24);
  if ( !v24 )
  {
    llVal = *((_QWORD *)v22 + 8);
    goto LABEL_16;
  }
  v67 = *((_QWORD *)v22 + 7);
  if ( v67 )
  {
    v70 = *(_DWORD *)(v67 + 28);
    v69 = 0;
    while ( v69 < v70 )
    {
      v71 = (v70 + v69) / 2;
      v72 = *(_DWORD *)(v67 + 12) * v71;
      v73 = *(_QWORD *)(v67 + 16);
      if ( *(_DWORD *)(v72 + v73) >= v24 )
      {
        if ( *(_DWORD *)(v72 + v73) <= v24 )
        {
          llVal = *(_QWORD *)(v72 + v73 + 8);
          goto LABEL_16;
        }
        v70 = (v70 + v69) / 2;
      }
      else
      {
        v69 = v71 + 1;
      }
    }
  }
  else
  {
    v68 = operator new(0x20u);
    if ( !v68 )
    {
      *((_QWORD *)v22 + 7) = 0;
      goto LABEL_91;
    }
    v68[2] = 1;
    *(_QWORD *)v68 = &GL::`vftable';
    v69 = 0;
    v68[3] = 16;
    *((_QWORD *)v68 + 2) = 0;
    *((_QWORD *)v68 + 3) = 0;
    *((_QWORD *)v22 + 7) = v68;
  }
  *(_DWORD *)&pvargDest.vt = v24;
  if ( ModuleBinder::Create((struct ModuleBinder **)&pvargDest.llVal, v22) < 0 )
  {
LABEL_91:
    *((_QWORD *)this + 13) = 0;
    return (unsigned int)-2147024882;
  }
  v62 = *((_QWORD *)v22 + 7);
  v63 = *(_DWORD *)(v62 + 12);
  v64 = *(_DWORD *)(v62 + 28) + 1;
  LODWORD(v76) = v63;
  v65 = v63 * v64;
  if ( v65 > *(_DWORD *)(v62 + 24) )
  {
    if ( !(unsigned int)GL::FEnsureSize((GL *)v62, v65) )
    {
      (*(void (__fastcall **)(LONGLONG))(*pvargDest.pllVal + 16))(pvargDest.llVal);
      *((_QWORD *)this + 13) = 0;
      return (unsigned int)-2147024882;
    }
    v63 = v76;
  }
  v66 = (char *)(v69 * v63 + *(_QWORD *)(v62 + 16));
  v77 = v66;
  if ( v69 < *(_DWORD *)(v62 + 28) )
  {
    memmove_0(&v66[v63], v66, v65 - v63 - v69 * v63);
    v63 = v76;
    v66 = v77;
  }
  memcpy_0(v66, &pvargDest, v63);
  ++*(_DWORD *)(v62 + 28);
  llVal = pvargDest.llVal;
LABEL_16:
  *((_QWORD *)this + 13) = llVal;
  if ( !llVal )
    return (unsigned int)-2147024882;
  if ( !v24
    || (result = CSession::GetNameTblForModule(*(CSession **)this, 0, (struct NameTbl **)this + 14), (int)result >= 0) )
  {
    v26 = ~(32 * a7) & 0x100 | *((_DWORD *)this + 126) & 0xFFFFFE7F ^ (unsigned __int8)((_BYTE)a7 << 7);
    v27 = (CScriptRuntime *)*((_QWORD *)this + 2);
    *((_DWORD *)this + 126) = v26;
    if ( v27 && (v26 & 0x80u) != 0 && (v26 & 0x100) != 0 )
    {
      v50 = CScriptRuntime::EnsureLocalsNameTbl(v27);
      if ( v50 < 0 )
        goto LABEL_40;
      v51 = *(_QWORD *)(*((_QWORD *)this + 2) + 88LL);
      *((_QWORD *)this + 11) = v51;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
      v52 = *(_QWORD *)(*((_QWORD *)this + 2) + 96LL);
      *((_QWORD *)this + 12) = v52;
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
    }
    if ( a4 )
    {
      v50 = AssignVar(*(struct CSession **)this, (CScriptRuntime *)((char *)this + 440), a4, 2u);
      if ( v50 < 0 )
        goto LABEL_40;
    }
    else
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 184LL))(*((_QWORD *)this + 13));
      *((_WORD *)this + 220) = 9;
      *((_QWORD *)this + 56) = v28;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
    }
    if ( (a7 & 2) == 0 )
      goto LABEL_23;
    v74 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 56);
    v75 = 0;
    v76 = 0;
    if ( !v74 )
    {
LABEL_106:
      *((_QWORD *)this + 12) = v75;
LABEL_23:
      v29 = *((_QWORD *)this + 5);
      memset(&pvargDest, 0, sizeof(pvargDest));
      if ( *(__int16 *)(*(_QWORD *)(v29 + 16) + 36LL) == a5 )
      {
        v30 = (VAR *)&a6[a5];
        *((_QWORD *)this + 10) = v30;
        if ( a5 )
        {
          v31 = -1;
          v32 = &a6[a5];
          while ( v32 > a6 )
          {
            vt = v32[-1].vt;
            v34 = (VAR *)v32--;
            if ( (vt & 0x4000) != 0 )
            {
              if ( (_WORD)vt != 16396
                || (v35 = ~v31, v31 >= 0)
                || (v36 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL), v35 >= *(__int16 *)(v36 + 36))
                || (*(_DWORD *)(v36 + 8LL * v35 + 52) & 0x200) == 0 )
              {
                v50 = VariantCopyInd(v32, v32);
                if ( v50 < 0 )
                {
LABEL_57:
                  while ( v34 < v30 )
                  {
                    VAR::Clear(v34);
                    v34 = (VAR *)((char *)v34 + 24);
                  }
                  *((_QWORD *)this + 10) = 0;
                  goto LABEL_40;
                }
              }
            }
            else if ( vt != 14 )
            {
              switch ( vt )
              {
                case 0:
                case 1:
                case 2:
                case 3:
                case 4:
                case 5:
                case 6:
                case 7:
                case 10:
                case 11:
                case 16:
                case 17:
                case 18:
                case 19:
                case 22:
                case 23:
                  break;
                case 8:
                case 9:
                case 12:
                case 13:
                case 14:
                case 15:
                case 20:
                case 21:
                  goto LABEL_65;
                default:
                  if ( vt == 74 )
                  {
                    v53 = v32->llVal;
                    --v31;
                    *(_OWORD *)&v32->vt = *(_OWORD *)v53;
                    v32->pRecInfo = *(IRecordInfo **)(v53 + 16);
                    *(_WORD *)v53 = 0;
                    continue;
                  }
LABEL_65:
                  pvargDest.vt = 0;
                  v50 = VariantCopy(&pvargDest, v32);
                  if ( v50 < 0 )
                    goto LABEL_57;
                  pRecInfo = pvargDest.pRecInfo;
                  *(_OWORD *)&v32->vt = *(_OWORD *)&pvargDest.vt;
                  v32->pRecInfo = pRecInfo;
                  break;
              }
            }
            --v31;
          }
        }
        v37 = *(__int16 *)(*(_QWORD *)(*((_QWORD *)this + 5) + 16LL) + 38LL)
            + *(__int16 *)(*(_QWORD *)(*((_QWORD *)this + 5) + 16LL) + 40LL)
            + *(__int16 *)(*(_QWORD *)(*((_QWORD *)this + 5) + 16LL) + 42LL);
        v38 = *(_QWORD *)(*(_QWORD *)this + 200LL);
        if ( !v38 )
        {
          v39 = TlsGetValue(g_luTls);
          v38 = 0;
          if ( v39 )
            v38 = v39[5];
        }
        v40 = *(_QWORD *)(v38 + 8);
        v41 = v37 + *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 16LL) + 4LL) + 7;
        if ( v40 )
        {
          v42 = **(_QWORD **)(v38 + 24);
          if ( (v42 - v40 - 16) / 24 >= v41 )
          {
LABEL_38:
            v43 = (_OWORD *)(v42 - 24);
            *((_QWORD *)this + 58) = v43;
            *v43 = *(_OWORD *)(v38 + 24);
            *(_QWORD *)(v38 + 24) = (char *)this + 464;
            *(_QWORD *)(v38 + 32) = v43;
            v44 = (_WORD *)(*((_QWORD *)this + 58) - 24LL);
            *((_QWORD *)this + 58) = v44;
            *v44 = 0;
            v45 = *((_QWORD *)this + 58);
            *((_QWORD *)this + 9) = v45;
            v46 = 24LL * v37;
            v47 = (void *)(v45 - v46);
            *((_QWORD *)this + 58) = v47;
            memset_0(v47, 0, v46);
            *((_QWORD *)this + 8) = *((_QWORD *)this + 58);
            v48 = *(_QWORD *)this;
            *((_QWORD *)this + 15) = 0;
            *((_QWORD *)this + 16) = 0;
            *((_QWORD *)this + 17) = 0;
            *((_DWORD *)this + 36) = -1;
            *((_DWORD *)this + 37) = 0;
            *((_QWORD *)this + 19) = 0;
            *((_DWORD *)this + 40) = 0;
            *(_QWORD *)(v48 + 72) = this;
            return 0;
          }
        }
        while ( 1 )
        {
          v54 = *(_DWORD **)(v38 + 16);
          if ( !v54 )
            break;
          if ( v54[2] >= v41 )
            goto LABEL_63;
          *(_QWORD *)(v38 + 16) = *(_QWORD *)v54;
          free(v54);
        }
        v57 = 2 * v41;
        if ( *(_DWORD *)v38 < v57 )
          *(_DWORD *)v38 = v57;
        else
          v57 = *(_DWORD *)v38;
        v58 = malloc(24LL * v57 + 40);
        *(_QWORD *)(v38 + 16) = v58;
        if ( v58 )
        {
          v58[2] = v57;
          **(_QWORD **)(v38 + 16) = 0;
          *(_DWORD *)v38 *= 2;
LABEL_63:
          v55 = *(_QWORD *)(v38 + 16);
          *(_QWORD *)(v38 + 16) = *(_QWORD *)v55;
          *(_QWORD *)v55 = *(_QWORD *)(v38 + 8);
          *(_QWORD *)(v38 + 8) = v55;
          v42 = v55 + 8 * (*(int *)(v55 + 8) + 2 * (*(int *)(v55 + 8) + 1LL));
          goto LABEL_38;
        }
        v50 = -2147024882;
        *((_QWORD *)this + 58) = 0;
      }
      else
      {
        v50 = -2146827838;
      }
      goto LABEL_40;
    }
    v50 = (**v74)(v74, &IID_INameTbl, &v76);
    if ( v50 >= 0 )
    {
      v75 = v76;
      goto LABEL_106;
    }
LABEL_40:
    CScriptRuntime::Cleanup(this);
    return (unsigned int)v50;
  }
  return result;
}

```

## disassembly

```asm
0x1800083f0  push    rbx
0x1800083f2  push    rsi
0x1800083f3  push    rdi
0x1800083f4  push    r12
0x1800083f6  push    r14
0x1800083f8  sub     rsp, 60h
0x1800083fc  mov     rax, cs:__security_cookie
0x180008403  xor     rax, rsp
0x180008406  mov     [rsp+88h+var_40], rax
0x18000840b  mov     r14, [rsp+88h+arg_28]
0x180008413  mov     rbx, rcx
0x180008416  mov     ecx, 10000h; unsigned int
0x18000841b  mov     r12, r9
0x18000841e  mov     rsi, r8
0x180008421  mov     rdi, rdx
0x180008424  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180008429  test    eax, eax
0x18000842b  jz      loc_180008B1A
0x180008431  mov     rax, [rdi+20h]
0x180008435  mov     [rsp+88h+arg_8], rbp
0x18000843d  mov     [rbx+8], rax
0x180008441  test    rax, rax
0x180008444  jz      loc_18000899D
0x18000844a  cmp     dword ptr [rax+100h], 0
0x180008451  jz      loc_18000899D
0x180008457  lock inc dword ptr [rax+94h]
0x18000845e  mov     [rbx], rdi
0x180008461  lock inc dword ptr [rdi+8]
0x180008465  mov     rcx, [rbx]
0x180008468  mov     rax, [rcx+48h]
0x18000846c  mov     [rbx+10h], rax
0x180008470  test    rax, rax
0x180008473  jz      loc_180008905
0x180008479  mov     edx, [rax+18h]
0x18000847c  inc     edx
0x18000847e  mov     [rsp+88h+var_30], r13
0x180008483  mov     [rsp+88h+var_38], r15
0x180008488  mov     [rbx+18h], edx
0x18000848b  mov     rax, [rcx+0C0h]
0x180008492  mov     [rbx+20h], rax
0x180008496  mov     [rbx+28h], rsi
0x18000849a  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800084a0  call    cs:__imp_TlsGetValue
0x1800084a6  test    rax, rax
0x1800084a9  jz      loc_180008949
0x1800084af  mov     rax, [rax+20h]
0x1800084b3  mov     [rbx+30h], rax
0x1800084b7  test    rax, rax
0x1800084ba  jz      loc_18000894F
0x1800084c0  mov     eax, [rax+18h]
0x1800084c3  xor     ebp, ebp
0x1800084c5  mov     r8, [rbx+28h]
0x1800084c9  mov     [rbx+38h], eax
0x1800084cc  mov     rax, [r8+10h]
0x1800084d0  movsxd  rcx, dword ptr [rax+8]
0x1800084d4  add     rcx, [r8+8]
0x1800084d8  mov     [rbx+1E0h], rcx
0x1800084df  mov     rax, [r8+8]
0x1800084e3  mov     [rbx+1F0h], rax
0x1800084ea  mov     rax, [rbx+10h]
0x1800084ee  test    rax, rax
0x1800084f1  jz      short loc_180008503
0x1800084f3  test    byte ptr [rax+1F8h], 3
0x1800084fa  jz      short loc_180008503
0x1800084fc  mov     eax, 2
0x180008501  jmp     short loc_180008505
0x180008503  mov     eax, ebp
0x180008505  and     dword ptr [rbx+1F8h], 0FFFFFFFCh
0x18000850c  or      [rbx+1F8h], eax
0x180008512  mov     rax, [r8+10h]
0x180008516  mov     ecx, [rbx+1F8h]
0x18000851c  and     ecx, 0FFFFFFFBh
0x18000851f  mov     edx, [rax+2Ch]
0x180008522  shr     edx, 0Bh
0x180008525  not     edx
0x180008527  and     edx, 4
0x18000852a  or      edx, ecx
0x18000852c  mov     [rbx+1F8h], edx
0x180008532  and     edx, 0FFFFFFF7h
0x180008535  mov     rax, [r8+10h]
0x180008539  mov     ecx, [rax+18h]
0x18000853c  shl     ecx, 3
0x18000853f  not     ecx
0x180008541  and     ecx, 8
0x180008544  or      ecx, edx
0x180008546  mov     [rbx+1F8h], ecx
0x18000854c  test    cl, 8
0x18000854f  jz      loc_180008A40
0x180008555  mov     rdi, [rbx]
0x180008558  cmp     [rdi+20h], rbp
0x18000855c  jz      loc_18000890F
0x180008562  mov     rax, [rbx+28h]
0x180008566  xorps   xmm0, xmm0
0x180008569  movups  xmmword ptr [rsp+88h+pvargDest], xmm0
0x18000856e  mov     esi, [rax+18h]
0x180008571  test    esi, esi
0x180008573  jnz     loc_180008B24
0x180008579  mov     rax, [rdi+40h]
0x18000857d  mov     [rbx+68h], rax
0x180008581  test    rax, rax
0x180008584  jz      loc_180008B85
0x18000858a  test    esi, esi
0x18000858c  jnz     loc_180008BE6
0x180008592  mov     eax, [rbx+1F8h]
0x180008598  mov     r15d, [rsp+88h+arg_30]
0x1800085a0  and     eax, 0FFFFFE7Fh
0x1800085a5  mov     ecx, r15d
0x1800085a8  shl     ecx, 7
0x1800085ab  and     ecx, 80h
0x1800085b1  xor     ecx, eax
0x1800085b3  mov     eax, r15d
0x1800085b6  shl     eax, 5
0x1800085b9  not     eax
0x1800085bb  and     eax, 100h
0x1800085c0  or      ecx, eax
0x1800085c2  mov     rax, [rbx+10h]
0x1800085c6  mov     [rbx+1F8h], ecx
0x1800085cc  test    rax, rax
0x1800085cf  jnz     loc_180008868
0x1800085d5  test    r12, r12
0x1800085d8  jnz     loc_180008811
0x1800085de  mov     rcx, [rbx+68h]
0x1800085e2  mov     rax, [rcx]
0x1800085e5  mov     rax, [rax+0B8h]
0x1800085ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085f1  mov     word ptr [rbx+1B8h], 9
0x1800085fa  mov     rdx, rax
0x1800085fd  mov     [rbx+1C0h], rax
0x180008604  test    rax, rax
0x180008607  jz      short loc_180008618
0x180008609  mov     rcx, [rax]
0x18000860c  mov     rax, [rcx+8]
0x180008610  mov     rcx, rdx
0x180008613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008618  test    r15b, 2
0x18000861c  jnz     loc_180008C01
0x180008622  movsxd  rdx, [rsp+88h+arg_20]
0x18000862a  xor     eax, eax
0x18000862c  mov     qword ptr [rsp+88h+pvargDest+10h], rax
0x180008631  xorps   xmm0, xmm0
0x180008634  mov     rax, [rbx+28h]
0x180008638  movups  xmmword ptr [rsp+88h+pvargDest], xmm0
0x18000863d  mov     rcx, [rax+10h]
0x180008641  movsx   eax, word ptr [rcx+24h]
0x180008645  cmp     eax, edx
0x180008647  jnz     loc_180008C44
0x18000864d  lea     rcx, [rdx+rdx*2]
0x180008651  lea     r12, [r14+rcx*8]
0x180008655  mov     [rbx+50h], r12
0x180008659  test    edx, edx
0x18000865b  jz      short loc_1800086DA
0x18000865d  mov     r15d, 0FFFFFFFFh
0x180008663  lea     r8, __ImageBase
0x18000866a  mov     rdi, r12
0x18000866d  mov     edx, 4000h
0x180008672  mov     ecx, 400Ch
0x180008677  cmp     rdi, r14
0x18000867a  jbe     short loc_1800086DA
0x18000867c  movzx   eax, word ptr [rdi-18h]
0x180008680  mov     r13, rdi
0x180008683  sub     rdi, 18h
0x180008687  test    dx, ax
0x18000868a  jz      loc_1800088CB
0x180008690  cmp     ax, cx
0x180008693  jnz     loc_180008919
0x180008699  mov     ecx, r15d
0x18000869c  not     ecx
0x18000869e  test    ecx, ecx
0x1800086a0  js      loc_180008919
0x1800086a6  mov     rax, [rbx+28h]
0x1800086aa  mov     rdx, [rax+10h]
0x1800086ae  movsx   eax, word ptr [rdx+24h]
0x1800086b2  cmp     ecx, eax
0x1800086b4  jge     loc_180008919
0x1800086ba  movsxd  rax, ecx
0x1800086bd  test    dword ptr [rdx+rax*8+34h], 200h
0x1800086c5  jz      loc_180008919
0x1800086cb  mov     edx, 4000h
0x1800086d0  mov     ecx, 400Ch; jumptable 0000000180008C62 cases 0-7,10,11,16-19,22,23
0x1800086d5  dec     r15d
0x1800086d8  jmp     short loc_180008677
0x1800086da  mov     rax, [rbx+28h]
0x1800086de  mov     rcx, [rax+10h]
0x1800086e2  movsx   eax, word ptr [rcx+28h]
0x1800086e6  movsx   r14d, word ptr [rcx+2Ah]
0x1800086eb  add     r14d, eax
0x1800086ee  movsx   eax, word ptr [rcx+26h]
0x1800086f2  add     r14d, eax
0x1800086f5  mov     rax, [rbx]
0x1800086f8  mov     rdi, [rax+0C8h]
0x1800086ff  test    rdi, rdi
0x180008702  jnz     short loc_18000871C
0x180008704  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000870a  call    cs:__imp_TlsGetValue
0x180008710  mov     rdi, rbp
0x180008713  test    rax, rax
0x180008716  jz      short loc_18000871C
0x180008718  mov     rdi, [rax+28h]
0x18000871c  mov     rax, [rbx+28h]
0x180008720  mov     rdx, [rdi+8]
0x180008724  mov     rcx, [rax+10h]
0x180008728  mov     esi, [rcx+4]
0x18000872b  add     esi, 7
0x18000872e  add     esi, r14d
0x180008731  test    rdx, rdx
0x180008734  jz      loc_180008960
0x18000873a  mov     rax, [rdi+18h]
0x18000873e  mov     r8, [rax]
0x180008741  mov     rax, 2AAAAAAAAAAAAAABh
0x18000874b  mov     rcx, r8
0x18000874e  sub     rcx, rdx
0x180008751  sub     rcx, 10h
0x180008755  imul    rcx
0x180008758  sar     rdx, 2
0x18000875c  mov     rax, rdx
0x18000875f  shr     rax, 3Fh
0x180008763  add     rdx, rax
0x180008766  movsxd  rax, esi
0x180008769  cmp     rdx, rax
0x18000876c  jl      loc_180008960
0x180008772  sub     r8, 18h
0x180008776  lea     rax, [rbx+1D0h]
0x18000877d  mov     [rax], r8
0x180008780  xor     edx, edx; Val
0x180008782  movups  xmm0, xmmword ptr [rdi+18h]
0x180008786  movups  xmmword ptr [r8], xmm0
0x18000878a  mov     [rdi+18h], rax
0x18000878e  mov     [rdi+20h], r8
0x180008792  mov     rax, [rbx+1D0h]
0x180008799  add     rax, 0FFFFFFFFFFFFFFE8h
0x18000879d  mov     [rbx+1D0h], rax
0x1800087a4  mov     [rax], bp
0x1800087a7  mov     rcx, [rbx+1D0h]
0x1800087ae  movsxd  rax, r14d
0x1800087b1  mov     [rbx+48h], rcx
0x1800087b5  lea     r8, [rax+rax*2]
0x1800087b9  shl     r8, 3; Size
0x1800087bd  sub     rcx, r8; void *
0x1800087c0  mov     [rbx+1D0h], rcx
0x1800087c7  call    memset_0
0x1800087cc  mov     rax, [rbx+1D0h]
0x1800087d3  mov     [rbx+40h], rax
0x1800087d7  mov     rax, [rbx]
0x1800087da  mov     [rbx+78h], rbp
0x1800087de  mov     [rbx+80h], rbp
0x1800087e5  mov     [rbx+88h], rbp
0x1800087ec  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x1800087f6  mov     [rbx+94h], ebp
0x1800087fc  mov     [rbx+98h], rbp
0x180008803  mov     [rbx+0A0h], ebp
0x180008809  mov     [rax+48h], rbx
0x18000880d  xor     eax, eax
0x18000880f  jmp     short loc_18000883D
0x180008811  mov     rcx, [rbx]; struct CSession *
0x180008814  lea     rdx, [rbx+1B8h]; struct VAR *
0x18000881b  mov     r9d, 2; unsigned int
0x180008821  mov     r8, r12; struct VAR *
0x180008824  call    ?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z; AssignVar(CSession *,VAR *,VAR *,ulong)
0x180008829  mov     esi, eax
0x18000882b  test    eax, eax
0x18000882d  jns     loc_180008618
0x180008833  mov     rcx, rbx; this
0x180008836  call    ?Cleanup@CScriptRuntime@@AEAAXXZ; CScriptRuntime::Cleanup(void)
0x18000883b  mov     eax, esi
0x18000883d  mov     r13, [rsp+88h+var_30]
0x180008842  mov     r15, [rsp+88h+var_38]
0x180008847  mov     rbp, [rsp+88h+arg_8]
0x18000884f  mov     rcx, [rsp+88h+var_40]
0x180008854  xor     rcx, rsp; StackCookie
0x180008857  call    __security_check_cookie
0x18000885c  add     rsp, 60h
0x180008860  pop     r14
0x180008862  pop     r12
0x180008864  pop     rdi
0x180008865  pop     rsi
0x180008866  pop     rbx
0x180008867  retn
0x180008868  test    cl, cl
0x18000886a  jns     loc_1800085D5
0x180008870  bt      ecx, 8
0x180008874  jnb     loc_1800085D5
0x18000887a  mov     rcx, rax; this
0x18000887d  call    ?EnsureLocalsNameTbl@CScriptRuntime@@AEAAJXZ; CScriptRuntime::EnsureLocalsNameTbl(void)
0x180008882  mov     esi, eax
0x180008884  test    eax, eax
0x180008886  js      short loc_180008833
0x180008888  mov     rax, [rbx+10h]
0x18000888c  mov     rcx, [rax+58h]
0x180008890  mov     [rbx+58h], rcx
0x180008894  test    rcx, rcx
0x180008897  jz      short loc_1800088A5
0x180008899  mov     rax, [rcx]
0x18000889c  mov     rax, [rax+8]
0x1800088a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088a5  mov     rax, [rbx+10h]
0x1800088a9  mov     rcx, [rax+60h]
0x1800088ad  mov     [rbx+60h], rcx
0x1800088b1  test    rcx, rcx
0x1800088b4  jz      loc_1800085D5
0x1800088ba  mov     rax, [rcx]
  ... truncated ...
```
