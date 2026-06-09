# VbsVarRel(VAR *,VAR *)

- ea: `0x180018b50`
- end: `0x180019648`
- name: `?VbsVarRel@@YA?AW4Comparison@@PEAVVAR@@0@Z`
- size: `2808`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f0f0`
- `0x18006d184`

## callees

- `0x180014b00`
- `0x180014c8c`
- `0x180017138`
- `0x180018b50`
- `0x180019650`
- `0x1800252c0`
- `0x18004237c`
- `0x180070840`
- `0x1800708a4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018f66`
- `OLEAUT32!__imp_SysFreeString` at `0x180019014`
- `OLEAUT32!__imp_SysFreeString` at `0x180019221`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001937c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800193f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180019423`
- `OLEAUT32!__imp_SysFreeString` at `0x180018f66`
- `OLEAUT32!__imp_SysFreeString` at `0x180019014`
- `OLEAUT32!__imp_SysFreeString` at `0x180019221`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001937c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800193f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180019423`
- `OLEAUT32!__imp_SysStringLen` at `0x180018f16`
- `OLEAUT32!__imp_SysStringLen` at `0x180018f28`
- `OLEAUT32!__imp_SysStringLen` at `0x180018fc0`
- `OLEAUT32!__imp_SysStringLen` at `0x180018fd2`
- `OLEAUT32!__imp_SysStringLen` at `0x180019254`
- `OLEAUT32!__imp_SysStringLen` at `0x180019266`
- `OLEAUT32!__imp_SysStringLen` at `0x1800193a5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800193b7`
- `OLEAUT32!__imp_SysStringLen` at `0x180018f16`
- `OLEAUT32!__imp_SysStringLen` at `0x180018f28`
- `OLEAUT32!__imp_SysStringLen` at `0x180018fc0`
- `OLEAUT32!__imp_SysStringLen` at `0x180018fd2`
- `OLEAUT32!__imp_SysStringLen` at `0x180019254`
- `OLEAUT32!__imp_SysStringLen` at `0x180019266`
- `OLEAUT32!__imp_SysStringLen` at `0x1800193a5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800193b7`
- `OLEAUT32!__imp_VariantClear` at `0x180018f75`
- `OLEAUT32!__imp_VariantClear` at `0x180019023`
- `OLEAUT32!__imp_VariantClear` at `0x1800190c0`
- `OLEAUT32!__imp_VariantClear` at `0x180019111`
- `OLEAUT32!__imp_VariantClear` at `0x1800192af`
- `OLEAUT32!__imp_VariantClear` at `0x180019404`
- `OLEAUT32!__imp_VariantClear` at `0x180018f75`
- `OLEAUT32!__imp_VariantClear` at `0x180019023`
- `OLEAUT32!__imp_VariantClear` at `0x1800190c0`
- `OLEAUT32!__imp_VariantClear` at `0x180019111`
- `OLEAUT32!__imp_VariantClear` at `0x1800192af`
- `OLEAUT32!__imp_VariantClear` at `0x180019404`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180018ce2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180018e52`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180019310`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180019460`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180018ce2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180018e52`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180019310`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180019460`

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
  v14 = *((unsigned __int8 *)qword_180084E90 + 18 * v11 + v8);
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
0x180018b50  push    rbp
0x180018b52  push    rsi
0x180018b53  push    rdi
0x180018b54  push    r12
0x180018b56  push    r14
0x180018b58  sub     rsp, 40h
0x180018b5c  movzx   edi, word ptr [rcx]
0x180018b5f  mov     rsi, rcx
0x180018b62  movzx   eax, di
0x180018b65  mov     ecx, 7FFFh
0x180018b6a  and     ax, cx
0x180018b6d  mov     ebp, 400Ch
0x180018b72  mov     r14, rdx
0x180018b75  mov     [rsi], ax
0x180018b78  cmp     ax, bp
0x180018b7b  jz      loc_180018D72
0x180018b81  cmp     ax, 4Ah ; 'J'
0x180018b85  jz      loc_180018D72
0x180018b8b  mov     r12d, 9
0x180018b91  mov     [rsp+68h+lcid], rsi
0x180018b96  cmp     r12w, ax
0x180018b9a  jz      loc_180019065
0x180018ba0  mov     [rsp+68h+var_38], r15
0x180018ba5  movzx   r15d, word ptr [rsi]
0x180018ba9  cmp     r15d, 11h
0x180018bad  ja      loc_180019182
0x180018bb3  mov     [rsp+68h+arg_8], rbx
0x180018bb8  movzx   ebx, word ptr [r14]
0x180018bbc  movzx   eax, bx
0x180018bbf  and     ax, cx
0x180018bc2  mov     [r14], ax
0x180018bc6  cmp     ax, bp
0x180018bc9  jz      loc_180018D81
0x180018bcf  cmp     ax, 4Ah ; 'J'
0x180018bd3  jz      loc_180018D81
0x180018bd9  mov     [rsp+68h+lcid], r14
0x180018bde  cmp     r12w, ax
0x180018be2  jz      loc_18001908A
0x180018be8  movzx   ebp, word ptr [r14]
0x180018bec  cmp     ebp, 11h
0x180018bef  ja      loc_1800191AB
0x180018bf5  and     ebx, 8000h
0x180018bfb  and     edi, 8000h
0x180018c01  mov     eax, ebx
0x180018c03  mov     ecx, 8
0x180018c08  or      eax, edi
0x180018c0a  jz      short loc_180018C1D
0x180018c0c  cmp     r15d, ecx
0x180018c0f  jz      loc_180019154
0x180018c15  cmp     ebp, ecx
0x180018c17  jz      loc_18001915C
0x180018c1d  mov     eax, ebp
0x180018c1f  lea     rcx, [rax+rax*8]
0x180018c23  mov     eax, r15d
0x180018c26  lea     rdx, [rax+rcx*2]
0x180018c2a  lea     rax, __ImageBase
0x180018c31  movzx   edi, byte ptr [rdx+rax+84E90h]
0x180018c39  cmp     edi, 0Ah
0x180018c3c  jz      loc_180019207
0x180018c42  cmp     edi, 1
0x180018c45  jz      loc_180018D19
0x180018c4b  mov     [rsp+68h+var_30], r13
0x180018c50  cmp     edi, 0Dh
0x180018c53  jz      loc_1800190AA; jumptable 0000000180018D3A case 13
0x180018c59  mov     eax, 1
0x180018c5e  cmp     edi, 0Ch
0x180018c61  jz      loc_180018D56
0x180018c67  movzx   eax, word ptr [rsi]
0x180018c6a  mov     ebx, 400h
0x180018c6f  mov     [rsp+68h+arg_10], ebx
0x180018c76  cmp     eax, edi
0x180018c78  jnz     loc_180018DF2
0x180018c7e  movzx   r12d, di
0x180018c82  movzx   eax, word ptr [r14]
0x180018c86  cmp     eax, edi
0x180018c88  jz      short loc_180018CF9
0x180018c8a  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x180018c8f  mov     r13, rax
0x180018c92  test    rax, rax
0x180018c95  jz      loc_18001936F
0x180018c9b  mov     eax, 8
0x180018ca0  cmp     ax, r12w
0x180018ca4  jz      loc_180018ED4
0x180018caa  cmp     ax, [r14]
0x180018cae  jz      loc_180018ED4
0x180018cb4  mov     ecx, 0Bh
0x180018cb9  cmp     cx, r12w
0x180018cbd  jz      loc_180018F99
0x180018cc3  cmp     ax, r12w
0x180018cc7  jz      loc_180019104
0x180018ccd  mov     r9d, 2; wFlags
0x180018cd3  mov     [rsp+68h+vt], r12w; vt
0x180018cd9  mov     r8d, ebx; lcid
0x180018cdc  mov     rdx, r14; pvarSrc
0x180018cdf  mov     rcx, r13; pvargDest
0x180018ce2  call    cs:__imp_VariantChangeTypeEx
0x180018ce9  nop     dword ptr [rax+rax+00h]
0x180018cee  test    eax, eax
0x180018cf0  js      loc_180019434
0x180018cf6  mov     r14, r13
0x180018cf9  cmp     edi, 2
0x180018cfc  jnz     short loc_180018D20
0x180018cfe  movzx   ecx, word ptr [r14+8]
0x180018d03  movzx   edx, word ptr [rsi+8]
0x180018d07  cmp     dx, cx
0x180018d0a  jl      short loc_180018D4F
0x180018d0c  jle     loc_1800195E4
0x180018d12  mov     ecx, 1
0x180018d17  jmp     short loc_180018D54
0x180018d19  mov     eax, 0FFFFFFFEh
0x180018d1e  jmp     short loc_180018D5B
0x180018d20  cmp     edi, 11h; switch 18 cases
0x180018d23  ja      def_180018D3A; jumptable 0000000180018D3A default case, cases 0-2,7,9-11,14-16
0x180018d29  lea     rdx, __ImageBase
0x180018d30  mov     ecx, ds:(jpt_180018D3A - 180000000h)[rdx+rdi*4]
0x180018d37  add     rcx, rdx
0x180018d3a  jmp     rcx; switch jump
0x180018d40  mov     ecx, [r14+8]; jumptable 0000000180018D3A case 3
0x180018d44  mov     edx, [rsi+8]
0x180018d47  cmp     edx, ecx
0x180018d49  jge     loc_180018E8F
0x180018d4f  mov     ecx, 0FFFFFFFFh
0x180018d54  mov     eax, ecx
0x180018d56  mov     r13, [rsp+68h+var_30]
0x180018d5b  mov     rbx, [rsp+68h+arg_8]
0x180018d60  mov     r15, [rsp+68h+var_38]
0x180018d65  add     rsp, 40h
0x180018d69  pop     r14
0x180018d6b  pop     r12
0x180018d6d  pop     rdi
0x180018d6e  pop     rsi
0x180018d6f  pop     rbp
0x180018d70  retn
0x180018d72  mov     rax, [rsi+8]
0x180018d76  mov     rsi, rax
0x180018d79  movzx   eax, word ptr [rax]
0x180018d7c  jmp     loc_180018B8B
0x180018d81  mov     rax, [r14+8]
0x180018d85  mov     r14, rax
0x180018d88  movzx   eax, word ptr [rax]
0x180018d8b  jmp     loc_180018BD9
0x180018d90  mov     rdi, [rsi+8]; jumptable 0000000180018D3A case 8
0x180018d94  mov     r10, [r14+8]
0x180018d98  test    rdi, rdi
0x180018d9b  jz      loc_180018EB6
0x180018da1  mov     r11d, [rdi-4]
0x180018da5  test    r10, r10
0x180018da8  jz      loc_180018EAD
0x180018dae  mov     ebx, [r10-4]
0x180018db2  mov     esi, r11d
0x180018db5  cmp     r11d, ebx
0x180018db8  jnb     loc_180018EAF
0x180018dbe  test    esi, esi
0x180018dc0  jz      loc_180019042
0x180018dc6  mov     eax, esi
0x180018dc8  mov     rcx, r10
0x180018dcb  shr     eax, 1
0x180018dcd  mov     rdx, rdi
0x180018dd0  test    eax, eax
0x180018dd2  jz      loc_180018E6E
0x180018dd8  movzx   r8d, word ptr [rdx]
0x180018ddc  cmp     r8w, [rcx]
0x180018de0  jnz     loc_18001959B
0x180018de6  dec     eax
0x180018de8  add     rdx, 2
0x180018dec  add     rcx, 2
0x180018df0  jmp     short loc_180018DD0
0x180018df2  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x180018df7  mov     r13, rax
0x180018dfa  test    rax, rax
0x180018dfd  jz      loc_180019214
0x180018e03  mov     eax, 8
0x180018e08  movzx   r12d, di
0x180018e0c  cmp     ax, di
0x180018e0f  jz      loc_180018EBE
0x180018e15  mov     r9d, ebx
0x180018e18  mov     dword ptr [rsp+68h+lcid], ebx
0x180018e1c  cmp     ax, [rsi]
0x180018e1f  jz      loc_180018EBE
0x180018e25  mov     ecx, 0Bh
0x180018e2a  cmp     cx, di
0x180018e2d  jz      loc_180018EEC
0x180018e33  cmp     ax, di
0x180018e36  jz      loc_1800190B4
0x180018e3c  mov     r8d, dword ptr [rsp+68h+lcid]; lcid
0x180018e41  mov     r9d, 2; wFlags
0x180018e47  mov     rdx, rsi; pvarSrc
0x180018e4a  mov     [rsp+68h+vt], di; vt
0x180018e4f  mov     rcx, r13; pvargDest
0x180018e52  call    cs:__imp_VariantChangeTypeEx
0x180018e59  nop     dword ptr [rax+rax+00h]
0x180018e5e  test    eax, eax
0x180018e60  js      loc_1800192E4
0x180018e66  mov     rsi, r13
0x180018e69  jmp     loc_180018C82
0x180018e6e  test    sil, 1
0x180018e72  jnz     loc_1800195AF
0x180018e78  cmp     r11d, ebx
0x180018e7b  jnb     loc_1800195C3
0x180018e81  mov     r10d, 0FFFFFFFFh
0x180018e87  mov     eax, r10d
0x180018e8a  jmp     loc_180018D56
0x180018e8f  jg      loc_180018D12
0x180018e95  xor     eax, eax
0x180018e97  mov     dword ptr [rsp+68h+lcid], 2
0x180018e9f  cmp     edx, ecx
0x180018ea1  mov     ecx, dword ptr [rsp+68h+lcid]
0x180018ea5  cmovz   ecx, eax
0x180018ea8  jmp     loc_180018D54
0x180018ead  xor     ebx, ebx
0x180018eaf  mov     esi, ebx
0x180018eb1  jmp     loc_180018DBE
0x180018eb6  xor     r11d, r11d
0x180018eb9  jmp     loc_180018DA5
0x180018ebe  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x180018ec3  mov     r9d, eax
0x180018ec6  mov     dword ptr [rsp+68h+lcid], eax
0x180018eca  mov     eax, 8
0x180018ecf  jmp     loc_180018E25
0x180018ed4  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x180018ed9  mov     ebx, eax
0x180018edb  mov     [rsp+68h+arg_10], eax
0x180018ee2  mov     eax, 8
0x180018ee7  jmp     loc_180018CB4
0x180018eec  cmp     ax, [rsi]
0x180018eef  jnz     loc_180018E3C
0x180018ef5  mov     edx, r9d; unsigned int
0x180018ef8  mov     ecx, 7FFEh; int
0x180018efd  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180018f02  mov     [rsp+68h+bstrString], rax
0x180018f0a  test    rax, rax
0x180018f0d  jz      loc_180019232
0x180018f13  mov     rcx, rax; pbstr
0x180018f16  call    cs:__imp_SysStringLen
0x180018f1d  nop     dword ptr [rax+rax+00h]
0x180018f22  mov     rcx, [rsi+8]; pbstr
0x180018f26  mov     ebx, eax
0x180018f28  call    cs:__imp_SysStringLen
0x180018f2f  nop     dword ptr [rax+rax+00h]
0x180018f34  mov     r8, [rsi+8]; unsigned __int16 *
0x180018f38  mov     edx, 1; unsigned int
0x180018f3d  mov     ecx, dword ptr [rsp+68h+lcid]; unsigned int
0x180018f41  mov     r9d, eax; int
0x180018f44  mov     [rsp+68h+var_40], ebx; int
0x180018f48  mov     rbx, [rsp+68h+bstrString]
0x180018f50  mov     qword ptr [rsp+68h+vt], rbx; unsigned __int16 *
0x180018f55  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x180018f5a  mov     rcx, rbx; bstrString
0x180018f5d  cmp     eax, 2
0x180018f60  jnz     loc_180019221
0x180018f66  call    cs:__imp_SysFreeString
0x180018f6d  nop     dword ptr [rax+rax+00h]
0x180018f72  mov     rcx, r13; pvarg
0x180018f75  call    cs:__imp_VariantClear
0x180018f7c  nop     dword ptr [rax+rax+00h]
0x180018f81  mov     word ptr [r13+0], 0Bh
0x180018f88  mov     word ptr [r13+8], 0FFFFh
0x180018f8f  mov     ebx, 400h
0x180018f94  jmp     loc_180018E66
0x180018f99  cmp     ax, [r14]
0x180018f9d  jnz     loc_180018CCD
0x180018fa3  mov     edx, ebx; unsigned int
0x180018fa5  mov     ecx, 7FFEh; int
0x180018faa  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180018faf  mov     [rsp+68h+lcid], rax
0x180018fb4  test    rax, rax
0x180018fb7  jz      loc_180019388
0x180018fbd  mov     rcx, rax; pbstr
0x180018fc0  call    cs:__imp_SysStringLen
0x180018fc7  nop     dword ptr [rax+rax+00h]
0x180018fcc  mov     rcx, [r14+8]; pbstr
0x180018fd0  mov     ebx, eax
0x180018fd2  call    cs:__imp_SysStringLen
0x180018fd9  nop     dword ptr [rax+rax+00h]
0x180018fde  mov     rcx, [rsp+68h+lcid]
0x180018fe3  mov     edx, 1; unsigned int
0x180018fe8  mov     r8, [r14+8]; unsigned __int16 *
0x180018fec  mov     r9d, eax; int
0x180018fef  mov     [rsp+68h+var_40], ebx; int
0x180018ff3  mov     ebx, [rsp+68h+arg_10]
0x180018ffa  mov     qword ptr [rsp+68h+vt], rcx; unsigned __int16 *
0x180018fff  mov     ecx, ebx; unsigned int
0x180019001  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x180019006  mov     rcx, [rsp+68h+lcid]; bstrString
0x18001900b  cmp     eax, 2
0x18001900e  jnz     loc_18001937C
0x180019014  call    cs:__imp_SysFreeString
0x18001901b  nop     dword ptr [rax+rax+00h]
0x180019020  mov     rcx, r13; pvarg
0x180019023  call    cs:__imp_VariantClear
0x18001902a  nop     dword ptr [rax+rax+00h]
0x18001902f  mov     word ptr [r13+0], 0Bh
0x180019036  mov     word ptr [r13+8], 0FFFFh
0x18001903d  jmp     loc_180018CF6
0x180019042  cmp     r11d, ebx
0x180019045  jb      loc_180018E81
0x18001904b  ja      loc_1800195D9
0x180019051  xor     eax, eax
0x180019053  mov     r10d, 2
0x180019059  cmp     r11d, ebx
  ... truncated ...
```
