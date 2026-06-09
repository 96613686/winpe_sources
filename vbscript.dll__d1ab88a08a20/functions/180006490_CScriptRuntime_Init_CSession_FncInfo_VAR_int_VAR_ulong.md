# CScriptRuntime::Init(CSession *,FncInfo *,VAR *,int,VAR *,ulong)

- ea: `0x180006490`
- end: `0x180006d78`
- name: `?Init@CScriptRuntime@@QEAAJPEAVCSession@@PEAVFncInfo@@PEAVVAR@@H2K@Z`
- size: `2280`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct CSession *, struct FncInfo *, struct VAR *, int, struct VAR *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180007dd0`

## callees

- `0x180006490`
- `0x1800070c0`
- `0x180011a58`
- `0x18001b9e0`
- `0x18001e410`
- `0x18001ed10`
- `0x18002d1a4`
- `0x180031760`
- `0x180046884`
- `0x18005d9dc`
- `0x18006b7ec`
- `0x18007941e`
- `0x18007942a`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!malloc` at `0x180006ad4`
- `msvcrt!malloc` at `0x180006ad4`
- `msvcrt!free` at `0x180006aa6`
- `msvcrt!free` at `0x180006aa6`
- `OLEAUT32!__imp_VariantCopy` at `0x180006a6a`
- `OLEAUT32!__imp_VariantCopy` at `0x180006a6a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800069cc`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800069cc`
- `KERNEL32!TlsGetValue` at `0x180006540`
- `KERNEL32!TlsGetValue` at `0x1800067b0`
- `KERNEL32!TlsGetValue` at `0x180006540`
- `KERNEL32!TlsGetValue` at `0x1800067b0`

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
0x180006490  push    rbx
0x180006492  push    rsi
0x180006493  push    rdi
0x180006494  push    r12
0x180006496  push    r14
0x180006498  sub     rsp, 60h
0x18000649c  mov     rax, cs:__security_cookie
0x1800064a3  xor     rax, rsp
0x1800064a6  mov     [rsp+88h+var_40], rax
0x1800064ab  mov     r14, [rsp+88h+arg_28]
0x1800064b3  mov     rbx, rcx
0x1800064b6  mov     ecx, 10000h; unsigned int
0x1800064bb  mov     r12, r9
0x1800064be  mov     rsi, r8
0x1800064c1  mov     rdi, rdx
0x1800064c4  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x1800064c9  test    eax, eax
0x1800064cb  jz      loc_180006BDC
0x1800064d1  mov     rax, [rdi+20h]
0x1800064d5  mov     [rsp+88h+arg_8], rbp
0x1800064dd  mov     [rbx+8], rax
0x1800064e1  test    rax, rax
0x1800064e4  jz      loc_180006A4D
0x1800064ea  cmp     dword ptr [rax+100h], 0
0x1800064f1  jz      loc_180006A4D
0x1800064f7  lock inc dword ptr [rax+94h]
0x1800064fe  mov     [rbx], rdi
0x180006501  lock inc dword ptr [rdi+8]
0x180006505  mov     rcx, [rbx]
0x180006508  mov     rax, [rcx+48h]
0x18000650c  mov     [rbx+10h], rax
0x180006510  test    rax, rax
0x180006513  jz      loc_1800069B2
0x180006519  mov     edx, [rax+18h]
0x18000651c  inc     edx
0x18000651e  mov     [rsp+88h+var_30], r13
0x180006523  mov     [rsp+88h+var_38], r15
0x180006528  mov     [rbx+18h], edx
0x18000652b  mov     rax, [rcx+0C0h]
0x180006532  mov     [rbx+20h], rax
0x180006536  mov     [rbx+28h], rsi
0x18000653a  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180006540  call    cs:__imp_TlsGetValue
0x180006547  nop     dword ptr [rax+rax+00h]
0x18000654c  test    rax, rax
0x18000654f  jz      loc_1800069FC
0x180006555  mov     rax, [rax+20h]
0x180006559  mov     [rbx+30h], rax
0x18000655d  test    rax, rax
0x180006560  jz      loc_180006A02
0x180006566  mov     eax, [rax+18h]
0x180006569  xor     ebp, ebp
0x18000656b  mov     r8, [rbx+28h]
0x18000656f  mov     [rbx+38h], eax
0x180006572  mov     rax, [r8+10h]
0x180006576  movsxd  rcx, dword ptr [rax+8]
0x18000657a  add     rcx, [r8+8]
0x18000657e  mov     [rbx+1E0h], rcx
0x180006585  mov     rax, [r8+8]
0x180006589  mov     [rbx+1F0h], rax
0x180006590  mov     rax, [rbx+10h]
0x180006594  test    rax, rax
0x180006597  jz      short loc_1800065A9
0x180006599  test    byte ptr [rax+1F8h], 3
0x1800065a0  jz      short loc_1800065A9
0x1800065a2  mov     eax, 2
0x1800065a7  jmp     short loc_1800065AB
0x1800065a9  mov     eax, ebp
0x1800065ab  and     dword ptr [rbx+1F8h], 0FFFFFFFCh
0x1800065b2  or      [rbx+1F8h], eax
0x1800065b8  mov     rax, [r8+10h]
0x1800065bc  mov     ecx, [rbx+1F8h]
0x1800065c2  and     ecx, 0FFFFFFFBh
0x1800065c5  mov     edx, [rax+2Ch]
0x1800065c8  shr     edx, 0Bh
0x1800065cb  not     edx
0x1800065cd  and     edx, 4
0x1800065d0  or      edx, ecx
0x1800065d2  mov     [rbx+1F8h], edx
0x1800065d8  and     edx, 0FFFFFFF7h
0x1800065db  mov     rax, [r8+10h]
0x1800065df  mov     ecx, [rax+18h]
0x1800065e2  shl     ecx, 3
0x1800065e5  not     ecx
0x1800065e7  and     ecx, 8
0x1800065ea  or      ecx, edx
0x1800065ec  mov     [rbx+1F8h], ecx
0x1800065f2  test    cl, 8
0x1800065f5  jz      loc_180006B02
0x1800065fb  mov     rdi, [rbx]
0x1800065fe  cmp     [rdi+20h], rbp
0x180006602  jz      loc_1800069BC
0x180006608  mov     rax, [rbx+28h]
0x18000660c  xorps   xmm0, xmm0
0x18000660f  movups  xmmword ptr [rsp+88h+pvargDest], xmm0
0x180006614  mov     esi, [rax+18h]
0x180006617  test    esi, esi
0x180006619  jnz     loc_180006BE6
0x18000661f  mov     rax, [rdi+40h]
0x180006623  mov     [rbx+68h], rax
0x180006627  test    rax, rax
0x18000662a  jz      loc_180006C47
0x180006630  test    esi, esi
0x180006632  jnz     loc_180006CA8
0x180006638  mov     eax, [rbx+1F8h]
0x18000663e  mov     r15d, [rsp+88h+arg_30]
0x180006646  and     eax, 0FFFFFE7Fh
0x18000664b  mov     ecx, r15d
0x18000664e  shl     ecx, 7
0x180006651  and     ecx, 80h
0x180006657  xor     ecx, eax
0x180006659  mov     eax, r15d
0x18000665c  shl     eax, 5
0x18000665f  not     eax
0x180006661  and     eax, 100h
0x180006666  or      ecx, eax
0x180006668  mov     rax, [rbx+10h]
0x18000666c  mov     [rbx+1F8h], ecx
0x180006672  test    rax, rax
0x180006675  jnz     loc_180006915
0x18000667b  test    r12, r12
0x18000667e  jnz     loc_1800068BD
0x180006684  mov     rcx, [rbx+68h]
0x180006688  mov     rax, [rcx]
0x18000668b  mov     rax, [rax+0B8h]
0x180006692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006697  mov     word ptr [rbx+1B8h], 9
0x1800066a0  mov     rdx, rax
0x1800066a3  mov     [rbx+1C0h], rax
0x1800066aa  test    rax, rax
0x1800066ad  jz      short loc_1800066BE
0x1800066af  mov     rcx, [rax]
0x1800066b2  mov     rax, [rcx+8]
0x1800066b6  mov     rcx, rdx
0x1800066b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066be  test    r15b, 2
0x1800066c2  jnz     loc_180006CC3
0x1800066c8  movsxd  rdx, [rsp+88h+arg_20]
0x1800066d0  xor     eax, eax
0x1800066d2  mov     qword ptr [rsp+88h+pvargDest+10h], rax
0x1800066d7  xorps   xmm0, xmm0
0x1800066da  mov     rax, [rbx+28h]
0x1800066de  movups  xmmword ptr [rsp+88h+pvargDest], xmm0
0x1800066e3  mov     rcx, [rax+10h]
0x1800066e7  movsx   eax, word ptr [rcx+24h]
0x1800066eb  cmp     eax, edx
0x1800066ed  jnz     loc_180006D06
0x1800066f3  lea     rcx, [rdx+rdx*2]
0x1800066f7  lea     r12, [r14+rcx*8]
0x1800066fb  mov     [rbx+50h], r12
0x1800066ff  test    edx, edx
0x180006701  jz      short loc_180006780
0x180006703  mov     r15d, 0FFFFFFFFh
0x180006709  lea     r8, __ImageBase
0x180006710  mov     rdi, r12
0x180006713  mov     edx, 4000h
0x180006718  mov     ecx, 400Ch
0x18000671d  cmp     rdi, r14
0x180006720  jbe     short loc_180006780
0x180006722  movzx   eax, word ptr [rdi-18h]
0x180006726  mov     r13, rdi
0x180006729  sub     rdi, 18h
0x18000672d  test    dx, ax
0x180006730  jz      loc_180006978
0x180006736  cmp     ax, cx
0x180006739  jnz     loc_1800069C6
0x18000673f  mov     ecx, r15d
0x180006742  not     ecx
0x180006744  test    ecx, ecx
0x180006746  js      loc_1800069C6
0x18000674c  mov     rax, [rbx+28h]
0x180006750  mov     rdx, [rax+10h]
0x180006754  movsx   eax, word ptr [rdx+24h]
0x180006758  cmp     ecx, eax
0x18000675a  jge     loc_1800069C6
0x180006760  movsxd  rax, ecx
0x180006763  test    dword ptr [rdx+rax*8+34h], 200h
0x18000676b  jz      loc_1800069C6
0x180006771  mov     edx, 4000h
0x180006776  mov     ecx, 400Ch; jumptable 0000000180006D24 cases 0-7,10,11,16-19,22,23
0x18000677b  dec     r15d
0x18000677e  jmp     short loc_18000671D
0x180006780  mov     rax, [rbx+28h]
0x180006784  mov     rcx, [rax+10h]
0x180006788  movsx   eax, word ptr [rcx+28h]
0x18000678c  movsx   r14d, word ptr [rcx+2Ah]
0x180006791  add     r14d, eax
0x180006794  movsx   eax, word ptr [rcx+26h]
0x180006798  add     r14d, eax
0x18000679b  mov     rax, [rbx]
0x18000679e  mov     rdi, [rax+0C8h]
0x1800067a5  test    rdi, rdi
0x1800067a8  jnz     short loc_1800067C8
0x1800067aa  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800067b0  call    cs:__imp_TlsGetValue
0x1800067b7  nop     dword ptr [rax+rax+00h]
0x1800067bc  mov     rdi, rbp
0x1800067bf  test    rax, rax
0x1800067c2  jz      short loc_1800067C8
0x1800067c4  mov     rdi, [rax+28h]
0x1800067c8  mov     rax, [rbx+28h]
0x1800067cc  mov     rdx, [rdi+8]
0x1800067d0  mov     rcx, [rax+10h]
0x1800067d4  mov     esi, [rcx+4]
0x1800067d7  add     esi, 7
0x1800067da  add     esi, r14d
0x1800067dd  test    rdx, rdx
0x1800067e0  jz      loc_180006A10
0x1800067e6  mov     rax, [rdi+18h]
0x1800067ea  mov     r8, [rax]
0x1800067ed  mov     rax, 2AAAAAAAAAAAAAABh
0x1800067f7  mov     rcx, r8
0x1800067fa  sub     rcx, rdx
0x1800067fd  sub     rcx, 10h
0x180006801  imul    rcx
0x180006804  sar     rdx, 2
0x180006808  mov     rax, rdx
0x18000680b  shr     rax, 3Fh
0x18000680f  add     rdx, rax
0x180006812  movsxd  rax, esi
0x180006815  cmp     rdx, rax
0x180006818  jl      loc_180006A10
0x18000681e  sub     r8, 18h
0x180006822  lea     rax, [rbx+1D0h]
0x180006829  mov     [rax], r8
0x18000682c  xor     edx, edx; Val
0x18000682e  movups  xmm0, xmmword ptr [rdi+18h]
0x180006832  movups  xmmword ptr [r8], xmm0
0x180006836  mov     [rdi+18h], rax
0x18000683a  mov     [rdi+20h], r8
0x18000683e  mov     rax, [rbx+1D0h]
0x180006845  add     rax, 0FFFFFFFFFFFFFFE8h
0x180006849  mov     [rbx+1D0h], rax
0x180006850  mov     [rax], bp
0x180006853  mov     rcx, [rbx+1D0h]
0x18000685a  movsxd  rax, r14d
0x18000685d  mov     [rbx+48h], rcx
0x180006861  lea     r8, [rax+rax*2]
0x180006865  shl     r8, 3; Size
0x180006869  sub     rcx, r8; void *
0x18000686c  mov     [rbx+1D0h], rcx
0x180006873  call    memset_0
0x180006878  mov     rax, [rbx+1D0h]
0x18000687f  mov     [rbx+40h], rax
0x180006883  mov     rax, [rbx]
0x180006886  mov     [rbx+78h], rbp
0x18000688a  mov     [rbx+80h], rbp
0x180006891  mov     [rbx+88h], rbp
0x180006898  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x1800068a2  mov     [rbx+94h], ebp
0x1800068a8  mov     [rbx+98h], rbp
0x1800068af  mov     [rbx+0A0h], ebp
0x1800068b5  mov     [rax+48h], rbx
0x1800068b9  xor     eax, eax
0x1800068bb  jmp     short loc_1800068E9
0x1800068bd  mov     rcx, [rbx]; struct CSession *
0x1800068c0  lea     rdx, [rbx+1B8h]; struct VAR *
0x1800068c7  mov     r9d, 2; unsigned int
0x1800068cd  mov     r8, r12; struct VAR *
0x1800068d0  call    ?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z; AssignVar(CSession *,VAR *,VAR *,ulong)
0x1800068d5  mov     esi, eax
0x1800068d7  test    eax, eax
0x1800068d9  jns     loc_1800066BE
0x1800068df  mov     rcx, rbx; this
0x1800068e2  call    ?Cleanup@CScriptRuntime@@AEAAXXZ; CScriptRuntime::Cleanup(void)
0x1800068e7  mov     eax, esi
0x1800068e9  mov     r13, [rsp+88h+var_30]
0x1800068ee  mov     r15, [rsp+88h+var_38]
0x1800068f3  mov     rbp, [rsp+88h+arg_8]
0x1800068fb  mov     rcx, [rsp+88h+var_40]
0x180006900  xor     rcx, rsp; StackCookie
0x180006903  call    __security_check_cookie
0x180006908  add     rsp, 60h
0x18000690c  pop     r14
0x18000690e  pop     r12
0x180006910  pop     rdi
0x180006911  pop     rsi
0x180006912  pop     rbx
0x180006913  retn
0x180006915  test    cl, cl
0x180006917  jns     loc_18000667B
0x18000691d  bt      ecx, 8
0x180006921  jnb     loc_18000667B
0x180006927  mov     rcx, rax; this
0x18000692a  call    ?EnsureLocalsNameTbl@CScriptRuntime@@AEAAJXZ; CScriptRuntime::EnsureLocalsNameTbl(void)
0x18000692f  mov     esi, eax
0x180006931  test    eax, eax
0x180006933  js      short loc_1800068DF
0x180006935  mov     rax, [rbx+10h]
0x180006939  mov     rcx, [rax+58h]
0x18000693d  mov     [rbx+58h], rcx
0x180006941  test    rcx, rcx
0x180006944  jz      short loc_180006952
0x180006946  mov     rax, [rcx]
0x180006949  mov     rax, [rax+8]
0x18000694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006952  mov     rax, [rbx+10h]
0x180006956  mov     rcx, [rax+60h]
0x18000695a  mov     [rbx+60h], rcx
0x18000695e  test    rcx, rcx
  ... truncated ...
```
