# VbsVarRel(VAR *,VAR *)

- ea: `0x18001e850`
- end: `0x18001f2a4`
- name: `?VbsVarRel@@YA?AW4Comparison@@PEAVVAR@@0@Z`
- size: `2644`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023ad0`
- `0x18006b020`

## callees

- `0x1800040d4`
- `0x180019edc`
- `0x18001b104`
- `0x18001cf8c`
- `0x18001e850`
- `0x18001f2b0`
- `0x180040cc4`
- `0x18006e5f0`
- `0x18006e654`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ec49`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ecdf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eed4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef63`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f005`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f06c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f08e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ec49`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ecdf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eed4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef63`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f005`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f06c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f08e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec05`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec11`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec97`
- `OLEAUT32!__imp_SysStringLen` at `0x18001eca3`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef01`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef0d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f028`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f034`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec05`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec11`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ec97`
- `OLEAUT32!__imp_SysStringLen` at `0x18001eca3`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef01`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ef0d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f028`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f034`
- `OLEAUT32!__imp_VariantClear` at `0x18001ec52`
- `OLEAUT32!__imp_VariantClear` at `0x18001ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18001ed7f`
- `OLEAUT32!__imp_VariantClear` at `0x18001edca`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef4a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f075`
- `OLEAUT32!__imp_VariantClear` at `0x18001ec52`
- `OLEAUT32!__imp_VariantClear` at `0x18001ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18001ed7f`
- `OLEAUT32!__imp_VariantClear` at `0x18001edca`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef4a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f075`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001e9e2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001eb47`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ef9f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001f0c5`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001e9e2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001eb47`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ef9f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001f0c5`

## pseudocode

```c
__int64 __fastcall VbsVarRel(__int16 *a1, struct IDispatch **a2, const unsigned __int16 *a3, int a4)
{
  __int16 v4; // di
  struct IDispatch **v5; // rsi
  __int16 v6; // ax
  unsigned int v8; // r15d
  __int16 v9; // bx
  __int16 v10; // ax
  unsigned int v11; // ebp
  int v12; // ebx
  int v13; // edi
  int v14; // edi
  __int64 result; // rax
  int v16; // eax
  unsigned int v17; // ebx
  VARTYPE vt; // r12
  const unsigned __int16 *v19; // r8
  int v20; // r9d
  VARIANTARG *v21; // r13
  HRESULT v22; // eax
  const unsigned __int16 *v23; // r8
  int v24; // r9d
  __int16 v25; // cx
  __int16 v26; // dx
  unsigned int v27; // ecx
  int v28; // ecx
  int v29; // edx
  struct IDispatch *v30; // rdi
  struct IDispatch *v31; // r10
  unsigned int lpVtbl_high; // r11d
  unsigned int v33; // ebx
  unsigned int v34; // esi
  struct IDispatch *v35; // rcx
  unsigned int v36; // eax
  struct IDispatch *v37; // rdx
  bool v38; // cf
  const unsigned __int16 *v39; // r8
  int v40; // r9d
  VARIANTARG *v41; // r13
  unsigned int ConversionLocale; // r9d
  HRESULT v43; // eax
  const unsigned __int16 *v44; // r8
  int v45; // r9d
  unsigned int v46; // r10d
  bool v47; // zf
  OLECHAR *v48; // rax
  UINT v49; // ebx
  UINT v50; // eax
  OLECHAR *v51; // rbx
  struct VAR *v52; // rax
  UINT v53; // ebx
  UINT v54; // eax
  int Default; // eax
  int v56; // eax
  unsigned int v57; // edx
  unsigned __int16 *ResourceString; // rax
  unsigned __int16 *v59; // rax
  OLECHAR *v60; // rax
  UINT v61; // ebx
  UINT v62; // eax
  OLECHAR *v63; // rbx
  double dblVal; // xmm1_8
  struct VAR *v65; // rax
  UINT v66; // ebx
  UINT v67; // eax
  double v68; // xmm1_8
  float v69; // xmm0_4
  float v70; // xmm1_4
  double v71; // xmm0_8
  double v72; // xmm1_8
  unsigned __int8 v73; // cl
  unsigned __int8 v74; // dl
  unsigned int v75; // r8d
  __int64 v76; // rcx
  unsigned __int8 v77; // al
  int v78; // [rsp+28h] [rbp-40h]
  int v79; // [rsp+28h] [rbp-40h]
  int v80; // [rsp+28h] [rbp-40h]
  int v81; // [rsp+28h] [rbp-40h]
  OLECHAR *lcid; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v83; // [rsp+80h] [rbp+18h]
  BSTR bstrString; // [rsp+88h] [rbp+20h]

  v4 = *a1;
  v5 = (struct IDispatch **)a1;
  v6 = v4 & 0x7FFF;
  *a1 &= ~0x8000u;
  if ( (v4 & 0x7FFF) == 0x400C || v6 == 74 )
  {
    v5 = (struct IDispatch **)*((_QWORD *)a1 + 1);
    v6 = *(_WORD *)v5;
  }
  lcid = (OLECHAR *)v5;
  if ( v6 == 9 )
  {
    Default = VAR::ObjGetDefault(v5[1], (struct VAR **)&lcid);
    if ( Default < 0 )
      RaiseErrorHr(Default, 0, a3, a4);
    v5 = (struct IDispatch **)lcid;
  }
  v8 = *(unsigned __int16 *)v5;
  if ( v8 > 0x11 )
  {
    if ( (v8 & 0x2000) != 0 )
      RaiseErrorHr(-2146828275, 0, a3, a4);
    RaiseErrorHr(-2146827830, 0, a3, a4);
  }
  v9 = *(_WORD *)a2;
  v10 = v9 & 0x7FFF;
  *(_WORD *)a2 &= ~0x8000u;
  if ( (v9 & 0x7FFF) == 0x400C || v10 == 74 )
  {
    a2 = (struct IDispatch **)a2[1];
    v10 = *(_WORD *)a2;
  }
  lcid = (OLECHAR *)a2;
  if ( v10 == 9 )
  {
    v56 = VAR::ObjGetDefault(a2[1], (struct VAR **)&lcid);
    if ( v56 < 0 )
      RaiseErrorHr(v56, 0, a3, a4);
    a2 = (struct IDispatch **)lcid;
  }
  v11 = *(unsigned __int16 *)a2;
  if ( v11 > 0x11 )
  {
    if ( (v11 & 0x2000) != 0 )
      RaiseErrorHr(-2146828275, 0, a3, a4);
    RaiseErrorHr(-2146827830, 0, a3, a4);
  }
  v12 = v9 & 0x8000;
  v13 = v4 & 0x8000;
  if ( v13 | v12 )
  {
    if ( v8 == 8 )
    {
      if ( v11 == 8 )
        goto LABEL_12;
    }
    else if ( v11 != 8 )
    {
      goto LABEL_12;
    }
    if ( v12 )
    {
      if ( v13 )
      {
        if ( v8 == 8 )
          v8 = 5;
        else
          v11 = 5;
      }
      else if ( v8 != 1 )
      {
        v8 = 5;
        if ( v11 == 8 )
          v8 = 8;
      }
    }
    else if ( v11 != 1 )
    {
      v11 = 5;
      if ( v8 == 8 )
        v11 = 8;
    }
  }
LABEL_12:
  v14 = *((unsigned __int8 *)qword_180081E80 + 18 * v11 + v8);
  switch ( v14 )
  {
    case 10:
      RaiseErrorHr(-2146828275, 0, a3, a4);
    case 1:
      return 4294967294LL;
    case 13:
      return 0xFFFFFFFFLL;
  }
  result = 1;
  if ( v14 != 12 )
  {
    v16 = *(unsigned __int16 *)v5;
    v17 = 1024;
    v83 = 1024;
    if ( v16 == v14 )
    {
      vt = v14;
      goto LABEL_18;
    }
    v41 = (VARIANTARG *)PvarAlloc();
    if ( !v41 )
      RaiseErrorHr(-2146828281, 0, v39, v40);
    vt = v14;
    if ( (_WORD)v14 == 8 || (ConversionLocale = 1024, LODWORD(lcid) = 1024, *(_WORD *)v5 == 8) )
    {
      ConversionLocale = COleScript::GetConversionLocale();
      LODWORD(lcid) = ConversionLocale;
    }
    if ( (_WORD)v14 != 11 )
    {
      if ( (_WORD)v14 == 8 && *(_WORD *)v5 == 11 )
      {
        VariantClear(v41);
        v57 = (unsigned int)lcid;
        v41->vt = 8;
        ResourceString = BstrGetResourceString((unsigned int)(*((_WORD *)v5 + 4) == 0) + 32766, v57);
        v41->llVal = (LONGLONG)ResourceString;
        if ( !ResourceString )
        {
          v43 = -2146828281;
          goto LABEL_132;
        }
        goto LABEL_53;
      }
LABEL_52:
      v43 = VariantChangeTypeEx(v41, (const VARIANTARG *)v5, (LCID)lcid, 2u, v14);
      if ( v43 < 0 )
      {
        if ( (_WORD)v14 == 7
          && *(_WORD *)v5 == 8
          && (v43 = VariantChangeTypeEx(v41, (const VARIANTARG *)v5, (LCID)lcid, 2u, 5u), v43 >= 0) )
        {
          dblVal = v41->dblVal;
          if ( dblVal <= 2958466.0 && dblVal >= -657434.9999999999 )
          {
            v41->vt = 7;
            goto LABEL_53;
          }
          v43 = -2146828275;
        }
        else if ( v43 == -2147352571 && *(_WORD *)v5 == 1 )
        {
          v43 = -2146828194;
        }
LABEL_132:
        RaiseErrorHr(v43, (struct VAR *)v5, v44, v45);
      }
LABEL_53:
      v5 = (struct IDispatch **)v41;
LABEL_18:
      if ( *(unsigned __int16 *)a2 == v14 )
        goto LABEL_26;
      v21 = (VARIANTARG *)PvarAlloc();
      if ( !v21 )
        RaiseErrorHr(-2146828281, 0, v19, v20);
      if ( vt == 8 || *(_WORD *)a2 == 8 )
      {
        v17 = COleScript::GetConversionLocale();
        v83 = v17;
      }
      if ( vt == 11 )
      {
        if ( *(_WORD *)a2 == 8 )
        {
          v52 = (struct VAR *)BstrGetResourceString(32766, v17);
          lcid = (OLECHAR *)v52;
          if ( v52 )
          {
            v53 = SysStringLen((BSTR)v52);
            v54 = SysStringLen((BSTR)a2[1]);
            v79 = v53;
            v17 = v83;
            if ( oCompareString(v83, 1u, (unsigned __int16 *)a2[1], v54, lcid, v79) == 2 )
            {
              SysFreeString(lcid);
              VariantClear(v21);
              v21->vt = 11;
              v21->iVal = -1;
              goto LABEL_25;
            }
            SysFreeString(lcid);
          }
          v65 = (struct VAR *)BstrGetResourceString(0x7FFF, v17);
          lcid = (OLECHAR *)v65;
          if ( v65 )
          {
            v66 = SysStringLen((BSTR)v65);
            v67 = SysStringLen((BSTR)a2[1]);
            v81 = v66;
            v17 = v83;
            if ( oCompareString(v83, 1u, (unsigned __int16 *)a2[1], v67, lcid, v81) == 2 )
            {
              SysFreeString(lcid);
              VariantClear(v21);
              v21->vt = 11;
              v21->iVal = 0;
              goto LABEL_25;
            }
            SysFreeString(lcid);
          }
        }
      }
      else if ( vt == 8 && *(_WORD *)a2 == 11 )
      {
        VariantClear(v21);
        v21->vt = 8;
        v59 = BstrGetResourceString((unsigned int)(*((_WORD *)a2 + 4) == 0) + 32766, v17);
        v21->llVal = (LONGLONG)v59;
        if ( !v59 )
        {
          v22 = -2146828281;
          goto LABEL_149;
        }
        goto LABEL_25;
      }
      v22 = VariantChangeTypeEx(v21, (const VARIANTARG *)a2, v17, 2u, vt);
      if ( v22 < 0 )
      {
        if ( vt == 7
          && *(_WORD *)a2 == 8
          && (v22 = VariantChangeTypeEx(v21, (const VARIANTARG *)a2, v17, 2u, 5u), v22 >= 0) )
        {
          v68 = v21->dblVal;
          if ( v68 <= 2958466.0 && v68 >= -657434.9999999999 )
          {
            v21->vt = 7;
            goto LABEL_25;
          }
          v22 = -2146828275;
        }
        else if ( v22 == -2147352571 && *(_WORD *)a2 == 1 )
        {
          v22 = -2146828194;
        }
LABEL_149:
        RaiseErrorHr(v22, (struct VAR *)a2, v23, v24);
      }
LABEL_25:
      a2 = (struct IDispatch **)v21;
LABEL_26:
      if ( v14 == 2 )
      {
        v25 = *((_WORD *)a2 + 4);
        v26 = *((_WORD *)v5 + 4);
        if ( v26 < v25 )
        {
          return (unsigned int)-1;
        }
        else if ( v26 <= v25 )
        {
          v47 = v26 == v25;
          v27 = 2;
LABEL_60:
          if ( v47 )
            return 0;
        }
        else
        {
          return 1;
        }
        return v27;
      }
      switch ( v14 )
      {
        case 3:
          v28 = *((_DWORD *)a2 + 2);
          v29 = *((_DWORD *)v5 + 2);
          if ( v29 < v28 )
            return (unsigned int)-1;
          if ( v29 > v28 )
            return 1;
          LODWORD(lcid) = 2;
          v47 = v29 == v28;
          v27 = 2;
          goto LABEL_60;
        case 4:
          v69 = *((float *)a2 + 2);
          v70 = *((float *)v5 + 2);
          if ( v69 > v70 )
            return 0xFFFFFFFFLL;
          if ( v70 > v69 )
            return 1;
          if ( v70 == v69 )
            return 0;
          return 2;
        case 5:
          if ( v8 == 5 )
          {
            if ( v11 == 4 )
              *((double *)v5 + 1) = RoundR4();
          }
          else if ( v8 == 4 && v11 == 5 )
          {
            *((double *)a2 + 1) = RoundR4();
          }
          v71 = *((double *)a2 + 1);
          v72 = *((double *)v5 + 1);
          if ( v71 > v72 )
            return 0xFFFFFFFFLL;
          if ( v72 > v71 )
            return 1;
          if ( v72 == v71 )
            return 0;
          return 2;
        case 6:
          return rtCmpCy(v5[1], a2[1]);
        case 8:
          v30 = v5[1];
          v31 = a2[1];
          if ( v30 )
            lpVtbl_high = HIDWORD(v30[-1].lpVtbl);
          else
            lpVtbl_high = 0;
          if ( v31 )
          {
            v33 = HIDWORD(v31[-1].lpVtbl);
            v34 = lpVtbl_high;
            if ( lpVtbl_high < v33 )
              goto LABEL_42;
          }
          else
          {
            v33 = 0;
          }
          v34 = v33;
LABEL_42:
          if ( v34 )
          {
            v35 = a2[1];
            v36 = v34 >> 1;
            v37 = v30;
            while ( v36 )
            {
              v38 = LOWORD(v37->lpVtbl) < LOWORD(v35->lpVtbl);
              if ( LOWORD(v37->lpVtbl) != LOWORD(v35->lpVtbl) )
                goto LABEL_172;
              --v36;
              v37 = (struct IDispatch *)((char *)v37 + 2);
              v35 = (struct IDispatch *)((char *)v35 + 2);
            }
            if ( (v34 & 1) != 0 )
            {
              v76 = v34 - 1;
              v77 = *((_BYTE *)&v30->lpVtbl + v76);
              v38 = v77 < *((_BYTE *)&v31->lpVtbl + v76);
              if ( v77 != *((_BYTE *)&v31->lpVtbl + v76) )
              {
LABEL_172:
                v46 = -1;
                if ( !v38 )
                  return 1;
                return v46;
              }
            }
            if ( lpVtbl_high < v33 )
              return (unsigned int)-1;
            if ( lpVtbl_high <= v33 )
            {
              v46 = 2;
              if ( lpVtbl_high == v33 )
                return 0;
              return v46;
            }
          }
          else
          {
            if ( lpVtbl_high < v33 )
              return (unsigned int)-1;
            if ( lpVtbl_high <= v33 )
            {
              v46 = 2;
              if ( lpVtbl_high == v33 )
                return 0;
              return v46;
            }
          }
          return 1;
        case 12:
          return 1;
        case 13:
          return 0xFFFFFFFFLL;
        case 17:
          v73 = *((_BYTE *)a2 + 8);
          v74 = *((_BYTE *)v5 + 8);
          if ( v74 >= v73 )
          {
            if ( v74 <= v73 )
            {
              v75 = 2;
              if ( v74 == v73 )
                return 0;
            }
            else
            {
              return 1;
            }
          }
          else
          {
            return (unsigned int)-1;
          }
          return v75;
        default:
          return 0;
      }
    }
    if ( *(_WORD *)v5 != 8 )
      goto LABEL_52;
    v48 = BstrGetResourceString(32766, ConversionLocale);
    bstrString = v48;
    if ( v48 )
    {
      v49 = SysStringLen(v48);
      v50 = SysStringLen((BSTR)v5[1]);
      v78 = v49;
      v51 = bstrString;
      if ( oCompareString((LCID)lcid, 1u, (unsigned __int16 *)v5[1], v50, bstrString, v78) == 2 )
      {
        SysFreeString(v51);
        VariantClear(v41);
        v41->vt = 11;
        v41->iVal = -1;
        goto LABEL_72;
      }
      SysFreeString(v51);
      v17 = 1024;
    }
    v60 = BstrGetResourceString(0x7FFF, (unsigned int)lcid);
    bstrString = v60;
    if ( !v60 )
      goto LABEL_52;
    v61 = SysStringLen(v60);
    v62 = SysStringLen((BSTR)v5[1]);
    v80 = v61;
    v63 = bstrString;
    if ( oCompareString((LCID)lcid, 1u, (unsigned __int16 *)v5[1], v62, bstrString, v80) != 2 )
    {
      SysFreeString(v63);
      v17 = 1024;
      goto LABEL_52;
    }
    SysFreeString(v63);
    VariantClear(v41);
    v41->vt = 11;
    v41->iVal = 0;
LABEL_72:
    v17 = 1024;
    goto LABEL_53;
  }
  return result;
}

```

## disassembly

```asm
0x18001e850  push    rbp
0x18001e852  push    rsi
0x18001e853  push    rdi
0x18001e854  push    r12
0x18001e856  push    r14
0x18001e858  sub     rsp, 40h
0x18001e85c  movzx   edi, word ptr [rcx]
0x18001e85f  mov     rsi, rcx
0x18001e862  movzx   eax, di
0x18001e865  mov     ecx, 7FFFh
0x18001e86a  and     ax, cx
0x18001e86d  mov     ebp, 400Ch
0x18001e872  mov     r14, rdx
0x18001e875  mov     [rsi], ax
0x18001e878  cmp     ax, bp
0x18001e87b  jz      loc_18001EA67
0x18001e881  cmp     ax, 4Ah ; 'J'
0x18001e885  jz      loc_18001EA67
0x18001e88b  mov     r12d, 9
0x18001e891  mov     [rsp+68h+lcid], rsi
0x18001e896  cmp     r12w, ax
0x18001e89a  jz      loc_18001ED24
0x18001e8a0  mov     [rsp+68h+var_38], r15
0x18001e8a5  movzx   r15d, word ptr [rsi]
0x18001e8a9  cmp     r15d, 11h
0x18001e8ad  ja      loc_18001EE35
0x18001e8b3  mov     [rsp+68h+arg_8], rbx
0x18001e8b8  movzx   ebx, word ptr [r14]
0x18001e8bc  movzx   eax, bx
0x18001e8bf  and     ax, cx
0x18001e8c2  mov     [r14], ax
0x18001e8c6  cmp     ax, bp
0x18001e8c9  jz      loc_18001EA76
0x18001e8cf  cmp     ax, 4Ah ; 'J'
0x18001e8d3  jz      loc_18001EA76
0x18001e8d9  mov     [rsp+68h+lcid], r14
0x18001e8de  cmp     r12w, ax
0x18001e8e2  jz      loc_18001ED49
0x18001e8e8  movzx   ebp, word ptr [r14]
0x18001e8ec  cmp     ebp, 11h
0x18001e8ef  ja      loc_18001EE5E
0x18001e8f5  and     ebx, 8000h
0x18001e8fb  and     edi, 8000h
0x18001e901  mov     eax, ebx
0x18001e903  mov     ecx, 8
0x18001e908  or      eax, edi
0x18001e90a  jz      short loc_18001E91D
0x18001e90c  cmp     r15d, ecx
0x18001e90f  jz      loc_18001EE07
0x18001e915  cmp     ebp, ecx
0x18001e917  jz      loc_18001EE0F
0x18001e91d  mov     eax, ebp
0x18001e91f  lea     rcx, [rax+rax*8]
0x18001e923  mov     eax, r15d
0x18001e926  lea     rdx, [rax+rcx*2]
0x18001e92a  lea     rax, __ImageBase
0x18001e931  movzx   edi, byte ptr [rdx+rax+81E80h]
0x18001e939  cmp     edi, 0Ah
0x18001e93c  jz      loc_18001EEBA
0x18001e942  cmp     edi, 1
0x18001e945  jz      loc_18001EA13
0x18001e94b  mov     [rsp+68h+var_30], r13
0x18001e950  cmp     edi, 0Dh
0x18001e953  jz      loc_18001ED69; jumptable 000000018001EA34 case 13
0x18001e959  mov     eax, 1
0x18001e95e  cmp     edi, 0Ch
0x18001e961  jz      loc_18001EA4C
0x18001e967  movzx   eax, word ptr [rsi]
0x18001e96a  mov     ebx, 400h
0x18001e96f  mov     [rsp+68h+arg_10], ebx
0x18001e976  cmp     eax, edi
0x18001e978  jnz     loc_18001EAE7
0x18001e97e  movzx   r12d, di
0x18001e982  movzx   eax, word ptr [r14]
0x18001e986  cmp     eax, edi
0x18001e988  jz      short loc_18001E9F3
0x18001e98a  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x18001e98f  mov     r13, rax
0x18001e992  test    rax, rax
0x18001e995  jz      loc_18001EFF8
0x18001e99b  mov     eax, 8
0x18001e9a0  cmp     ax, r12w
0x18001e9a4  jz      loc_18001EBC3
0x18001e9aa  cmp     ax, [r14]
0x18001e9ae  jz      loc_18001EBC3
0x18001e9b4  mov     ecx, 0Bh
0x18001e9b9  cmp     cx, r12w
0x18001e9bd  jz      loc_18001EC70
0x18001e9c3  cmp     ax, r12w
0x18001e9c7  jz      loc_18001EDBD
0x18001e9cd  mov     r9d, 2; wFlags
0x18001e9d3  mov     [rsp+68h+vt], r12w; vt
0x18001e9d9  mov     r8d, ebx; lcid
0x18001e9dc  mov     rdx, r14; pvarSrc
0x18001e9df  mov     rcx, r13; pvargDest
0x18001e9e2  call    cs:__imp_VariantChangeTypeEx
0x18001e9e8  test    eax, eax
0x18001e9ea  js      loc_18001F099
0x18001e9f0  mov     r14, r13
0x18001e9f3  cmp     edi, 2
0x18001e9f6  jnz     short loc_18001EA1A
0x18001e9f8  movzx   ecx, word ptr [r14+8]
0x18001e9fd  movzx   edx, word ptr [rsi+8]
0x18001ea01  cmp     dx, cx
0x18001ea04  jl      short loc_18001EA45
0x18001ea06  jle     loc_18001F243
0x18001ea0c  mov     ecx, 1
0x18001ea11  jmp     short loc_18001EA4A
0x18001ea13  mov     eax, 0FFFFFFFEh
0x18001ea18  jmp     short loc_18001EA51
0x18001ea1a  cmp     edi, 11h; switch 18 cases
0x18001ea1d  ja      def_18001EA34; jumptable 000000018001EA34 default case, cases 0-2,7,9-11,14-16
0x18001ea23  lea     rdx, __ImageBase
0x18001ea2a  mov     ecx, ds:(jpt_18001EA34 - 180000000h)[rdx+rdi*4]
0x18001ea31  add     rcx, rdx
0x18001ea34  jmp     rcx; switch jump
0x18001ea36  mov     ecx, [r14+8]; jumptable 000000018001EA34 case 3
0x18001ea3a  mov     edx, [rsi+8]
0x18001ea3d  cmp     edx, ecx
0x18001ea3f  jge     loc_18001EB7E
0x18001ea45  mov     ecx, 0FFFFFFFFh
0x18001ea4a  mov     eax, ecx
0x18001ea4c  mov     r13, [rsp+68h+var_30]
0x18001ea51  mov     rbx, [rsp+68h+arg_8]
0x18001ea56  mov     r15, [rsp+68h+var_38]
0x18001ea5b  add     rsp, 40h
0x18001ea5f  pop     r14
0x18001ea61  pop     r12
0x18001ea63  pop     rdi
0x18001ea64  pop     rsi
0x18001ea65  pop     rbp
0x18001ea66  retn
0x18001ea67  mov     rax, [rsi+8]
0x18001ea6b  mov     rsi, rax
0x18001ea6e  movzx   eax, word ptr [rax]
0x18001ea71  jmp     loc_18001E88B
0x18001ea76  mov     rax, [r14+8]
0x18001ea7a  mov     r14, rax
0x18001ea7d  movzx   eax, word ptr [rax]
0x18001ea80  jmp     loc_18001E8D9
0x18001ea85  mov     rdi, [rsi+8]; jumptable 000000018001EA34 case 8
0x18001ea89  mov     r10, [r14+8]
0x18001ea8d  test    rdi, rdi
0x18001ea90  jz      loc_18001EBA5
0x18001ea96  mov     r11d, [rdi-4]
0x18001ea9a  test    r10, r10
0x18001ea9d  jz      loc_18001EB9C
0x18001eaa3  mov     ebx, [r10-4]
0x18001eaa7  mov     esi, r11d
0x18001eaaa  cmp     r11d, ebx
0x18001eaad  jnb     loc_18001EB9E
0x18001eab3  test    esi, esi
0x18001eab5  jz      loc_18001ED01
0x18001eabb  mov     eax, esi
0x18001eabd  mov     rcx, r10
0x18001eac0  shr     eax, 1
0x18001eac2  mov     rdx, rdi
0x18001eac5  test    eax, eax
0x18001eac7  jz      loc_18001EB5D
0x18001eacd  movzx   r8d, word ptr [rdx]
0x18001ead1  cmp     r8w, [rcx]
0x18001ead5  jnz     loc_18001F1FA
0x18001eadb  dec     eax
0x18001eadd  add     rdx, 2
0x18001eae1  add     rcx, 2
0x18001eae5  jmp     short loc_18001EAC5
0x18001eae7  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x18001eaec  mov     r13, rax
0x18001eaef  test    rax, rax
0x18001eaf2  jz      loc_18001EEC7
0x18001eaf8  mov     eax, 8
0x18001eafd  movzx   r12d, di
0x18001eb01  cmp     ax, di
0x18001eb04  jz      loc_18001EBAD
0x18001eb0a  mov     r9d, ebx
0x18001eb0d  mov     dword ptr [rsp+68h+lcid], ebx
0x18001eb11  cmp     ax, [rsi]
0x18001eb14  jz      loc_18001EBAD
0x18001eb1a  mov     ecx, 0Bh
0x18001eb1f  cmp     cx, di
0x18001eb22  jz      loc_18001EBDB
0x18001eb28  cmp     ax, di
0x18001eb2b  jz      loc_18001ED73
0x18001eb31  mov     r8d, dword ptr [rsp+68h+lcid]; lcid
0x18001eb36  mov     r9d, 2; wFlags
0x18001eb3c  mov     rdx, rsi; pvarSrc
0x18001eb3f  mov     [rsp+68h+vt], di; vt
0x18001eb44  mov     rcx, r13; pvargDest
0x18001eb47  call    cs:__imp_VariantChangeTypeEx
0x18001eb4d  test    eax, eax
0x18001eb4f  js      loc_18001EF73
0x18001eb55  mov     rsi, r13
0x18001eb58  jmp     loc_18001E982
0x18001eb5d  test    sil, 1
0x18001eb61  jnz     loc_18001F20E
0x18001eb67  cmp     r11d, ebx
0x18001eb6a  jnb     loc_18001F222
0x18001eb70  mov     r10d, 0FFFFFFFFh
0x18001eb76  mov     eax, r10d
0x18001eb79  jmp     loc_18001EA4C
0x18001eb7e  jg      loc_18001EA0C
0x18001eb84  xor     eax, eax
0x18001eb86  mov     dword ptr [rsp+68h+lcid], 2
0x18001eb8e  cmp     edx, ecx
0x18001eb90  mov     ecx, dword ptr [rsp+68h+lcid]
0x18001eb94  cmovz   ecx, eax
0x18001eb97  jmp     loc_18001EA4A
0x18001eb9c  xor     ebx, ebx
0x18001eb9e  mov     esi, ebx
0x18001eba0  jmp     loc_18001EAB3
0x18001eba5  xor     r11d, r11d
0x18001eba8  jmp     loc_18001EA9A
0x18001ebad  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18001ebb2  mov     r9d, eax
0x18001ebb5  mov     dword ptr [rsp+68h+lcid], eax
0x18001ebb9  mov     eax, 8
0x18001ebbe  jmp     loc_18001EB1A
0x18001ebc3  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18001ebc8  mov     ebx, eax
0x18001ebca  mov     [rsp+68h+arg_10], eax
0x18001ebd1  mov     eax, 8
0x18001ebd6  jmp     loc_18001E9B4
0x18001ebdb  cmp     ax, [rsi]
0x18001ebde  jnz     loc_18001EB31
0x18001ebe4  mov     edx, r9d; unsigned int
0x18001ebe7  mov     ecx, 7FFEh; int
0x18001ebec  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ebf1  mov     [rsp+68h+bstrString], rax
0x18001ebf9  test    rax, rax
0x18001ebfc  jz      loc_18001EEDF
0x18001ec02  mov     rcx, rax; pbstr
0x18001ec05  call    cs:__imp_SysStringLen
0x18001ec0b  mov     rcx, [rsi+8]; pbstr
0x18001ec0f  mov     ebx, eax
0x18001ec11  call    cs:__imp_SysStringLen
0x18001ec17  mov     r8, [rsi+8]; unsigned __int16 *
0x18001ec1b  mov     edx, 1; unsigned int
0x18001ec20  mov     ecx, dword ptr [rsp+68h+lcid]; unsigned int
0x18001ec24  mov     r9d, eax; int
0x18001ec27  mov     [rsp+68h+var_40], ebx; int
0x18001ec2b  mov     rbx, [rsp+68h+bstrString]
0x18001ec33  mov     qword ptr [rsp+68h+vt], rbx; unsigned __int16 *
0x18001ec38  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001ec3d  mov     rcx, rbx; bstrString
0x18001ec40  cmp     eax, 2
0x18001ec43  jnz     loc_18001EED4
0x18001ec49  call    cs:__imp_SysFreeString
0x18001ec4f  mov     rcx, r13; pvarg
0x18001ec52  call    cs:__imp_VariantClear
0x18001ec58  mov     word ptr [r13+0], 0Bh
0x18001ec5f  mov     word ptr [r13+8], 0FFFFh
0x18001ec66  mov     ebx, 400h
0x18001ec6b  jmp     loc_18001EB55
0x18001ec70  cmp     ax, [r14]
0x18001ec74  jnz     loc_18001E9CD
0x18001ec7a  mov     edx, ebx; unsigned int
0x18001ec7c  mov     ecx, 7FFEh; int
0x18001ec81  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ec86  mov     [rsp+68h+lcid], rax
0x18001ec8b  test    rax, rax
0x18001ec8e  jz      loc_18001F00B
0x18001ec94  mov     rcx, rax; pbstr
0x18001ec97  call    cs:__imp_SysStringLen
0x18001ec9d  mov     rcx, [r14+8]; pbstr
0x18001eca1  mov     ebx, eax
0x18001eca3  call    cs:__imp_SysStringLen
0x18001eca9  mov     rcx, [rsp+68h+lcid]
0x18001ecae  mov     edx, 1; unsigned int
0x18001ecb3  mov     r8, [r14+8]; unsigned __int16 *
0x18001ecb7  mov     r9d, eax; int
0x18001ecba  mov     [rsp+68h+var_40], ebx; int
0x18001ecbe  mov     ebx, [rsp+68h+arg_10]
0x18001ecc5  mov     qword ptr [rsp+68h+vt], rcx; unsigned __int16 *
0x18001ecca  mov     ecx, ebx; unsigned int
0x18001eccc  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001ecd1  mov     rcx, [rsp+68h+lcid]; bstrString
0x18001ecd6  cmp     eax, 2
0x18001ecd9  jnz     loc_18001F005
0x18001ecdf  call    cs:__imp_SysFreeString
0x18001ece5  mov     rcx, r13; pvarg
0x18001ece8  call    cs:__imp_VariantClear
0x18001ecee  mov     word ptr [r13+0], 0Bh
0x18001ecf5  mov     word ptr [r13+8], 0FFFFh
0x18001ecfc  jmp     loc_18001E9F0
0x18001ed01  cmp     r11d, ebx
0x18001ed04  jb      loc_18001EB70
0x18001ed0a  ja      loc_18001F238
0x18001ed10  xor     eax, eax
0x18001ed12  mov     r10d, 2
0x18001ed18  cmp     r11d, ebx
0x18001ed1b  cmovz   r10d, eax
0x18001ed1f  jmp     loc_18001EB76
0x18001ed24  mov     rcx, [rsi+8]; struct IDispatch *
0x18001ed28  lea     rdx, [rsp+68h+lcid]; struct VAR **
0x18001ed2d  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x18001ed32  test    eax, eax
0x18001ed34  js      loc_18001EE2B
0x18001ed3a  mov     rsi, [rsp+68h+lcid]
0x18001ed3f  mov     ecx, 7FFFh
0x18001ed44  jmp     loc_18001E8A0
  ... truncated ...
```
