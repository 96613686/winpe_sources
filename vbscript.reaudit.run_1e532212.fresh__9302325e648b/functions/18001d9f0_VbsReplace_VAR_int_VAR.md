# VbsReplace(VAR *,int,VAR *)

- ea: `0x18001d9f0`
- end: `0x18001e1fb`
- name: `?VbsReplace@@YAJPEAVVAR@@H0@Z`
- size: `2059`
- prototype: `int(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180003850`
- `0x1800040d4`
- `0x18001bf24`
- `0x18001c950`
- `0x18001d9f0`
- `0x18001e7a0`
- `0x18001f2b0`
- `0x18001f420`
- `0x18001fa40`
- `0x180035154`
- `0x180036c90`
- `0x180040cc4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001dc33`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001dc33`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dcbd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e18e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e19c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dcbd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e18e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e19c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1f0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001dccd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001dccd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001dd96`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001de33`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001def5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001dd96`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001de33`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001def5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ddab`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001de48`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001df0a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ddab`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001de48`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001df0a`
- `KERNEL32!IsValidLocale` at `0x18001e0bf`
- `KERNEL32!IsValidLocale` at `0x18001e0bf`
- `KERNEL32!TlsGetValue` at `0x18001da4a`
- `KERNEL32!TlsGetValue` at `0x18001da4a`

## pseudocode

```c
__int64 __fastcall VbsReplace(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v3; // rdi
  LCID DefaultLocale; // r15d
  LCID Val; // eax
  _QWORD *Value; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int16 v10; // ax
  struct IDispatch **v11; // rcx
  VARTYPE v12; // r10
  __int64 v13; // r14
  __int64 v14; // rbp
  struct IDispatch **v15; // rbx
  char v16; // r12
  unsigned __int16 v17; // ax
  __int64 v18; // r13
  struct IDispatch **v19; // rdi
  char v20; // bl
  __int16 v21; // r9
  char v22; // r12
  unsigned __int16 v23; // ax
  unsigned __int16 *v24; // rsi
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rax
  OLECHAR *v28; // rbx
  int v29; // r8d
  int v30; // edi
  struct VAR *v31; // rax
  unsigned __int16 v33; // ax
  UINT v34; // edx
  const unsigned __int16 *v35; // r8
  int v36; // r9d
  BSTR v37; // rax
  unsigned __int16 lpVtbl; // ax
  unsigned __int16 v39; // ax
  UINT v40; // edx
  const unsigned __int16 *v41; // r8
  int v42; // r9d
  BSTR v43; // rax
  UINT v44; // edx
  const unsigned __int16 *v45; // r8
  int v46; // r9d
  BSTR v47; // rax
  struct VAR *v48; // rax
  struct VAR *v49; // rax
  int Default; // eax
  const unsigned __int16 *v51; // r8
  int v52; // r9d
  int v53; // eax
  const unsigned __int16 *v54; // r8
  int v55; // r9d
  int v56; // eax
  const unsigned __int16 *v57; // r8
  int v58; // r9d
  int v59; // r9d
  int v60; // eax
  int v61; // eax
  unsigned int v62; // eax
  int v63; // [rsp+30h] [rbp-68h]
  SAFEARRAY *psa; // [rsp+38h] [rbp-60h] BYREF
  struct VAR *v65[3]; // [rsp+40h] [rbp-58h] BYREF
  char v67; // [rsp+A8h] [rbp+10h]
  unsigned int v68; // [rsp+B0h] [rbp+18h]
  unsigned int v69; // [rsp+B8h] [rbp+20h]

  *(_WORD *)a1 = 1;
  v3 = a3;
  if ( (unsigned int)(a2 - 3) > 3 )
    return 2148139458LL;
  if ( a2 == 6 )
  {
    Val = VAR::UlGetVal(a3);
    v3 = (struct VAR *)((char *)v3 + 24);
    DefaultLocale = Val;
    if ( Val >= 2 )
    {
      v63 = 1;
      if ( !IsValidLocale(Val, 1u) )
        return 2148139013LL;
      goto LABEL_143;
    }
  }
  else
  {
    DefaultLocale = 0;
  }
  v63 = DefaultLocale;
  Value = TlsGetValue(g_luTls);
  if ( Value && (v8 = Value[3]) != 0 )
    DefaultLocale = *(_DWORD *)(v8 + 188);
  else
    DefaultLocale = GetDefaultLocale();
  if ( a2 < 5 )
    goto LABEL_9;
LABEL_143:
  v61 = VAR::UlGetVal(v3);
  v3 = (struct VAR *)((char *)v3 + 24);
  v69 = v61;
  if ( v61 == -1 )
  {
LABEL_9:
    v69 = 0x7FFFFFFF;
    goto LABEL_10;
  }
  if ( v61 < 0 )
    return 2148139013LL;
LABEL_10:
  if ( a2 >= 4 )
  {
    v62 = VAR::UlGetVal(v3);
    if ( v62 - 1 <= 0x3FFFFFFD )
    {
      v3 = (struct VAR *)((char *)v3 + 24);
      v9 = v62 - 1;
      goto LABEL_12;
    }
    return 2148139013LL;
  }
  v9 = 0;
LABEL_12:
  v68 = v9;
  v10 = *(_WORD *)v3;
  if ( *(_WORD *)v3 == 16396 || v10 == 74 )
  {
    v11 = (struct IDispatch **)*((_QWORD *)v3 + 1);
    v10 = *(_WORD *)v11;
  }
  else
  {
    v11 = (struct IDispatch **)v3;
  }
  v65[0] = (struct VAR *)v11;
  if ( v10 == 9 )
  {
    Default = VAR::ObjGetDefault(v11[1], v65);
    if ( Default < 0 )
      RaiseErrorHr(Default, 0, v51, v52);
    v11 = (struct IDispatch **)v65[0];
  }
  v12 = 8;
  v13 = -1;
  if ( *(_WORD *)v11 == 8 )
  {
    v14 = (__int64)v11[1];
  }
  else
  {
    if ( *(_WORD *)v11 == 1 )
    {
      v14 = -1;
      v15 = (struct IDispatch **)((char *)v3 + 24);
LABEL_21:
      v16 = 0;
      goto LABEL_22;
    }
    v48 = VAR::PvarConvert((VAR *)v11, 8u);
    v12 = 8;
    v14 = *((_QWORD *)v48 + 1);
  }
  v15 = (struct IDispatch **)((char *)v3 + 24);
  if ( !v14 || v14 == -1 || v3 == (struct VAR *)-24LL )
    goto LABEL_21;
  v33 = *(_WORD *)v15;
  if ( *(_WORD *)v15 == 16396 || v33 == 74 )
    v33 = **((_WORD **)v3 + 4);
  if ( v33 == 8 || (v33 & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(v33) )
    goto LABEL_21;
  v34 = SysStringByteLen((BSTR)v14);
  v37 = 0;
  if ( v34 < 0x7FFFFFFD )
    v37 = SysAllocStringByteLen((LPCSTR)v14, v34);
  if ( !v37 )
    RaiseErrorHr(-2146828281, 0, v35, v36);
  v14 = (__int64)v37;
  v16 = 1;
  v12 = 8;
LABEL_22:
  v17 = *(_WORD *)v15;
  v67 = v16;
  if ( *(_WORD *)v15 == 16396 || v17 == 74 )
  {
    v15 = (struct IDispatch **)*((_QWORD *)v3 + 4);
    v17 = *(_WORD *)v15;
  }
  v65[0] = (struct VAR *)v15;
  if ( v17 == 9 )
  {
    v53 = VAR::ObjGetDefault(v15[1], v65);
    if ( v53 < 0 )
      RaiseErrorHr(v53, 0, v54, v55);
    v15 = (struct IDispatch **)v65[0];
    v12 = 8;
  }
  if ( v12 == *(_WORD *)v15 )
  {
    v18 = (__int64)v15[1];
  }
  else if ( *(_WORD *)v15 == 1 )
  {
    v18 = -1;
  }
  else
  {
    v49 = VAR::PvarConvert((VAR *)v15, v12);
    v12 = 8;
    v18 = *((_QWORD *)v49 + 1);
  }
  v19 = (struct IDispatch **)((char *)v3 + 48);
  if ( !v16 && (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v19 )
  {
    lpVtbl = *(_WORD *)v19;
    if ( *(_WORD *)v19 == 16396 || lpVtbl == 74 )
      lpVtbl = (unsigned __int16)v19[1]->lpVtbl;
    v21 = 0x4000;
    if ( lpVtbl == 8 || (lpVtbl & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(lpVtbl) )
    {
      v20 = v16;
      goto LABEL_32;
    }
    v44 = SysStringByteLen((BSTR)v14);
    v47 = 0;
    if ( v44 < 0x7FFFFFFD )
      v47 = SysAllocStringByteLen((LPCSTR)v14, v44);
    if ( !v47 )
      RaiseErrorHr(-2146828281, 0, v45, v46);
    v20 = 1;
    v14 = (__int64)v47;
    v67 = 1;
    v12 = 8;
  }
  else
  {
    v20 = v16;
  }
  v21 = 0x4000;
LABEL_32:
  v22 = 0;
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v19 )
  {
    v39 = *(_WORD *)v19;
    if ( *(_WORD *)v19 == 16396 || v39 == 74 )
      v39 = (unsigned __int16)v19[1]->lpVtbl;
    if ( v39 != 8 && ((v39 & (unsigned __int16)v21) != 0 || !(unsigned int)VAR::IsSimpleType(v39)) )
    {
      v40 = SysStringByteLen((BSTR)v18);
      v43 = 0;
      if ( v40 < 0x7FFFFFFD )
        v43 = SysAllocStringByteLen((LPCSTR)v18, v40);
      if ( !v43 )
        RaiseErrorHr(-2146828281, 0, v41, v42);
      v18 = (__int64)v43;
      v22 = 1;
      v12 = 8;
    }
  }
  v23 = *(_WORD *)v19;
  if ( *(_WORD *)v19 == 16396 || v23 == 74 )
  {
    v19 = (struct IDispatch **)v19[1];
    v23 = *(_WORD *)v19;
  }
  v65[0] = (struct VAR *)v19;
  if ( v23 == 9 )
  {
    v56 = VAR::ObjGetDefault(v19[1], v65);
    if ( v56 < 0 )
      RaiseErrorHr(v56, 0, v57, v58);
    v19 = (struct IDispatch **)v65[0];
    v12 = 8;
  }
  if ( v12 == *(_WORD *)v19 )
  {
    v13 = (__int64)v19[1];
  }
  else if ( *(_WORD *)v19 != 1 )
  {
    v13 = *((_QWORD *)VAR::PvarConvert((VAR *)v19, v12) + 1);
  }
  if ( v14 == -1 || v18 == -1 || v13 == -1 )
  {
    if ( v22 )
      SysFreeString((BSTR)v18);
    if ( v20 )
      SysFreeString((BSTR)v14);
    return 2148139102LL;
  }
  v24 = 0;
  psa = 0;
  v65[0] = 0;
  if ( v13 )
    v25 = *(_DWORD *)(v13 - 4);
  else
    v25 = 0;
  v26 = v25 >> 1;
  if ( v68 > v26 )
  {
    v30 = -2146828274;
    v24 = _SysAllocStringLen(&String, 0);
    if ( v24 )
      v30 = 0;
    goto LABEL_59;
  }
  v27 = v26 - v68;
  if ( (unsigned __int64)(2 * v27) < 0x7FFFFFFD )
  {
    v28 = SysAllocStringLen((const OLECHAR *)(v13 + 2LL * v68), v27);
    if ( v28 )
    {
      if ( !v13 || !*(_DWORD *)(v13 - 4) || !v18 || !*(_DWORD *)(v18 - 4) || !v69 )
      {
        v24 = v28;
LABEL_60:
        *(_WORD *)a1 = 74;
        v31 = PvarAlloc();
        if ( v31 )
        {
          *(_WORD *)v31 = 8;
          *((_QWORD *)v31 + 1) = v24;
          *((_QWORD *)a1 + 1) = v31;
          if ( v22 )
            SysFreeString((BSTR)v18);
          if ( v67 )
            SysFreeString((BSTR)v14);
          return 0;
        }
        else
        {
          *((_QWORD *)a1 + 1) = 0;
          if ( v22 )
            SysFreeString((BSTR)v18);
          if ( v67 )
            SysFreeString((BSTR)v14);
          return 2148139015LL;
        }
      }
      v29 = v69 + 1;
      if ( v69 >= 0x7FFFFFFF )
        v29 = v69;
      if ( *((_DWORD *)v28 - 1) )
      {
        v30 = rtStandardSplit(v28, (BSTR)v18, v29, DefaultLocale, v63, &psa);
        if ( v30 < 0 )
        {
LABEL_56:
          SysFreeString(v28);
          goto LABEL_57;
        }
      }
      else
      {
        psa = psaMakeOneDim(0);
        if ( !psa )
        {
          v30 = -2146828281;
          goto LABEL_56;
        }
      }
      if ( v14 )
        v59 = *(_DWORD *)(v14 - 4);
      else
        v59 = 0;
      v60 = rtJoin(0, (unsigned int)&psa, v14, v59, (__int64)v65);
      v24 = (unsigned __int16 *)v65[0];
      v30 = v60;
      if ( v60 >= 0 )
        v30 = 0;
      goto LABEL_56;
    }
  }
  v30 = -2146828274;
LABEL_57:
  if ( psa )
    SafeArrayDestroy(psa);
LABEL_59:
  if ( v30 >= 0 )
    goto LABEL_60;
  if ( v22 )
    SysFreeString((BSTR)v18);
  if ( v67 )
    SysFreeString((BSTR)v14);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18001d9f0  mov     [rsp+arg_0], rcx
0x18001d9f5  push    rbx
0x18001d9f6  push    rbp
0x18001d9f7  push    rdi
0x18001d9f8  sub     rsp, 80h
0x18001d9ff  lea     eax, [rdx-3]
0x18001da02  mov     ebp, 1
0x18001da07  mov     [rcx], bp
0x18001da0a  mov     rdi, r8
0x18001da0d  mov     ebx, edx
0x18001da0f  cmp     eax, 3
0x18001da12  ja      loc_18001DFEA
0x18001da18  mov     [rsp+98h+var_40], r15
0x18001da1d  cmp     edx, 6
0x18001da20  jz      short loc_18001DA27
0x18001da22  xor     r15d, r15d
0x18001da25  jmp     short loc_18001DA3F
0x18001da27  mov     rcx, rdi; this
0x18001da2a  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x18001da2f  add     rdi, 18h
0x18001da33  mov     r15d, eax
0x18001da36  cmp     eax, 2
0x18001da39  jnb     loc_18001E0B7
0x18001da3f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001da45  mov     [rsp+98h+var_68], r15d
0x18001da4a  call    cs:__imp_TlsGetValue
0x18001da50  test    rax, rax
0x18001da53  jz      loc_18001DE64
0x18001da59  mov     rax, [rax+18h]
0x18001da5d  test    rax, rax
0x18001da60  jz      loc_18001DE64
0x18001da66  mov     r15d, [rax+0BCh]
0x18001da6d  cmp     ebx, 5
0x18001da70  jge     loc_18001E0C9
0x18001da76  mov     eax, 7FFFFFFFh
0x18001da7b  mov     [rsp+98h+arg_18], eax
0x18001da82  cmp     ebx, 4
0x18001da85  jge     loc_18001E0F7
0x18001da8b  xor     eax, eax
0x18001da8d  mov     [rsp+98h+var_20], rsi
0x18001da92  mov     esi, 400Ch
0x18001da97  mov     [rsp+98h+arg_10], eax
0x18001da9e  movzx   eax, word ptr [rdi]
0x18001daa1  mov     [rsp+98h+var_30], r13
0x18001daa6  cmp     ax, si
0x18001daa9  jz      loc_18001DF26
0x18001daaf  cmp     ax, 4Ah ; 'J'
0x18001dab3  jz      loc_18001DF26
0x18001dab9  mov     rcx, rdi; this
0x18001dabc  mov     r13d, 9
0x18001dac2  mov     [rsp+98h+var_58], rcx
0x18001dac7  cmp     r13w, ax
0x18001dacb  jz      loc_18001E00E
0x18001dad1  movzx   eax, word ptr [rcx]
0x18001dad4  mov     r10d, 8
0x18001dada  mov     [rsp+98h+var_28], r12
0x18001dadf  mov     edx, 4000h
0x18001dae4  mov     [rsp+98h+var_38], r14
0x18001dae9  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001daf0  cmp     r10w, ax
0x18001daf4  jnz     loc_18001DF4D
0x18001dafa  mov     rbp, [rcx+8]
0x18001dafe  lea     rbx, [rdi+18h]
0x18001db02  test    rbp, rbp
0x18001db05  jz      short loc_18001DB15
0x18001db07  cmp     rbp, r14
0x18001db0a  jz      short loc_18001DB15
0x18001db0c  test    rbx, rbx
0x18001db0f  jnz     loc_18001DD5E
0x18001db15  xor     r12b, r12b
0x18001db18  movzx   eax, word ptr [rbx]
0x18001db1b  mov     [rsp+98h+arg_8], r12b
0x18001db23  cmp     ax, si
0x18001db26  jz      loc_18001DF32
0x18001db2c  cmp     ax, 4Ah ; 'J'
0x18001db30  jz      loc_18001DF32
0x18001db36  mov     [rsp+98h+var_58], rbx
0x18001db3b  cmp     r13w, ax
0x18001db3f  jz      loc_18001E02E
0x18001db45  movzx   eax, word ptr [rbx]
0x18001db48  cmp     r10w, ax
0x18001db4c  jnz     loc_18001DF72
0x18001db52  mov     r13, [rbx+8]
0x18001db56  add     rdi, 30h ; '0'
0x18001db5a  test    r12b, r12b
0x18001db5d  jnz     short loc_18001DB72
0x18001db5f  lea     rax, [rbp-1]
0x18001db63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001db67  ja      short loc_18001DB72
0x18001db69  test    rdi, rdi
0x18001db6c  jnz     loc_18001DDC7
0x18001db72  movzx   ebx, [rsp+98h+arg_8]
0x18001db7a  mov     r9d, 4000h
0x18001db80  xor     r12b, r12b
0x18001db83  lea     rax, [r13-1]
0x18001db87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001db8b  ja      short loc_18001DB96
0x18001db8d  test    rdi, rdi
0x18001db90  jnz     loc_18001DDFA
0x18001db96  movzx   eax, word ptr [rdi]
0x18001db99  cmp     ax, si
0x18001db9c  jz      loc_18001DF3E
0x18001dba2  cmp     ax, 4Ah ; 'J'
0x18001dba6  jz      loc_18001DF3E
0x18001dbac  mov     ecx, 9
0x18001dbb1  mov     [rsp+98h+var_58], rdi
0x18001dbb6  cmp     cx, ax
0x18001dbb9  jz      loc_18001E054
0x18001dbbf  movzx   eax, word ptr [rdi]
0x18001dbc2  cmp     r10w, ax
0x18001dbc6  jnz     loc_18001DF9A
0x18001dbcc  mov     r14, [rdi+8]
0x18001dbd0  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18001dbd4  jz      loc_18001DEC1
0x18001dbda  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18001dbde  jz      loc_18001DEC1
0x18001dbe4  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001dbe8  jz      loc_18001DEC1
0x18001dbee  xor     esi, esi
0x18001dbf0  mov     [rsp+98h+psa], 0
0x18001dbf9  mov     [rsp+98h+var_58], rsi
0x18001dbfe  test    r14, r14
0x18001dc01  jz      loc_18001DEBA
0x18001dc07  mov     eax, [r14-4]
0x18001dc0b  mov     ecx, [rsp+98h+arg_10]
0x18001dc12  shr     eax, 1
0x18001dc14  cmp     ecx, eax
0x18001dc16  ja      loc_18001DE97
0x18001dc1c  sub     eax, ecx
0x18001dc1e  mov     edx, eax; ui
0x18001dc20  add     rax, rax
0x18001dc23  cmp     rax, 7FFFFFFDh
0x18001dc29  jnb     loc_18001DFE0
0x18001dc2f  lea     rcx, [r14+rcx*2]; strIn
0x18001dc33  call    cs:__imp_SysAllocStringLen
0x18001dc39  mov     rbx, rax
0x18001dc3c  test    rax, rax
0x18001dc3f  jz      loc_18001DFE0
0x18001dc45  test    r14, r14
0x18001dc48  jz      loc_18001DE71
0x18001dc4e  cmp     [r14-4], esi
0x18001dc52  jz      loc_18001DE71
0x18001dc58  test    r13, r13
0x18001dc5b  jz      loc_18001DE71
0x18001dc61  cmp     [r13-4], esi
0x18001dc65  jz      loc_18001DE71
0x18001dc6b  mov     eax, [rsp+98h+arg_18]
0x18001dc72  test    eax, eax
0x18001dc74  jz      loc_18001DE71
0x18001dc7a  cmp     eax, 7FFFFFFFh
0x18001dc7f  lea     r8d, [rax+1]
0x18001dc83  cmovnb  r8d, eax
0x18001dc87  cmp     [rbx-4], esi
0x18001dc8a  jz      loc_18001E16C
0x18001dc90  lea     rax, [rsp+98h+psa]
0x18001dc95  mov     r9d, r15d
0x18001dc98  mov     [rsp+98h+var_70], rax; __int64
0x18001dc9d  mov     rdx, r13; LPCWCH
0x18001dca0  mov     eax, [rsp+98h+var_68]
0x18001dca4  mov     rcx, rbx; lpWideCharStr
0x18001dca7  mov     [rsp+98h+var_78], eax; int
0x18001dcab  call    rtStandardSplit
0x18001dcb0  mov     edi, eax
0x18001dcb2  test    eax, eax
0x18001dcb4  jns     loc_18001E07A
0x18001dcba  mov     rcx, rbx; bstrString
0x18001dcbd  call    cs:__imp_SysFreeString
0x18001dcc3  mov     rcx, [rsp+98h+psa]; psa
0x18001dcc8  test    rcx, rcx
0x18001dccb  jz      short loc_18001DCD3
0x18001dccd  call    cs:__imp_SafeArrayDestroy
0x18001dcd3  test    edi, edi
0x18001dcd5  js      loc_18001DE79
0x18001dcdb  mov     rbx, [rsp+98h+arg_0]
0x18001dce3  mov     word ptr [rbx], 4Ah ; 'J'
0x18001dce8  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x18001dced  test    rax, rax
0x18001dcf0  jz      short loc_18001DD1A
0x18001dcf2  mov     word ptr [rax], 8
0x18001dcf7  mov     [rax+8], rsi
0x18001dcfb  mov     [rbx+8], rax
0x18001dcff  test    r12b, r12b
0x18001dd02  jnz     loc_18001E1A7
0x18001dd08  cmp     [rsp+98h+arg_8], 0
0x18001dd10  jnz     loc_18001E1B5
0x18001dd16  xor     eax, eax
0x18001dd18  jmp     short loc_18001DD3A
0x18001dd1a  mov     [rbx+8], rax
0x18001dd1e  test    r12b, r12b
0x18001dd21  jnz     loc_18001E1C3
0x18001dd27  cmp     [rsp+98h+arg_8], 0
0x18001dd2f  jnz     loc_18001E1D1
0x18001dd35  mov     eax, 800A0007h
0x18001dd3a  mov     r14, [rsp+98h+var_38]
0x18001dd3f  mov     r12, [rsp+98h+var_28]
0x18001dd44  mov     r13, [rsp+98h+var_30]
0x18001dd49  mov     rsi, [rsp+98h+var_20]
0x18001dd4e  mov     r15, [rsp+98h+var_40]
0x18001dd53  add     rsp, 80h
0x18001dd5a  pop     rdi
0x18001dd5b  pop     rbp
0x18001dd5c  pop     rbx
0x18001dd5d  retn
0x18001dd5e  movzx   eax, word ptr [rbx]
0x18001dd61  cmp     ax, si
0x18001dd64  jz      loc_18001DFBC
0x18001dd6a  cmp     ax, 4Ah ; 'J'
0x18001dd6e  jz      loc_18001DFBC
0x18001dd74  cmp     ax, 8
0x18001dd78  jz      loc_18001DB15
0x18001dd7e  test    dx, ax
0x18001dd81  jnz     short loc_18001DD93
0x18001dd83  movzx   ecx, ax; int
0x18001dd86  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001dd8b  test    eax, eax
0x18001dd8d  jnz     loc_18001DB15
0x18001dd93  mov     rcx, rbp; bstr
0x18001dd96  call    cs:__imp_SysStringByteLen
0x18001dd9c  mov     edx, eax; len
0x18001dd9e  xor     eax, eax
0x18001dda0  cmp     edx, 7FFFFFFDh
0x18001dda6  jnb     short loc_18001DDB1
0x18001dda8  mov     rcx, rbp; psz
0x18001ddab  call    cs:__imp_SysAllocStringByteLen
0x18001ddb1  test    rax, rax
0x18001ddb4  jnz     loc_18001E11F
0x18001ddba  xor     edx, edx; struct VAR *
0x18001ddbc  mov     ecx, 800A0007h; int
0x18001ddc1  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001ddc7  movzx   eax, word ptr [rdi]
0x18001ddca  cmp     ax, si
0x18001ddcd  jz      loc_18001DFC8
0x18001ddd3  cmp     ax, 4Ah ; 'J'
0x18001ddd7  jz      loc_18001DFC8
0x18001dddd  mov     r9d, 4000h
0x18001dde3  cmp     ax, 8
0x18001dde7  jnz     loc_18001DEDC
0x18001dded  movzx   ebx, [rsp+98h+arg_8]
0x18001ddf5  jmp     loc_18001DB80
0x18001ddfa  movzx   eax, word ptr [rdi]
0x18001ddfd  cmp     ax, si
0x18001de00  jz      loc_18001DFD4
0x18001de06  cmp     ax, 4Ah ; 'J'
0x18001de0a  jz      loc_18001DFD4
0x18001de10  cmp     ax, 8
0x18001de14  jz      loc_18001DB96
0x18001de1a  test    r9w, ax
0x18001de1e  jnz     short loc_18001DE30
0x18001de20  movzx   ecx, ax; int
0x18001de23  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001de28  test    eax, eax
0x18001de2a  jnz     loc_18001DB96
0x18001de30  mov     rcx, r13; bstr
0x18001de33  call    cs:__imp_SysStringByteLen
0x18001de39  mov     edx, eax; len
0x18001de3b  xor     eax, eax
0x18001de3d  cmp     edx, 7FFFFFFDh
0x18001de43  jnb     short loc_18001DE4E
0x18001de45  mov     rcx, r13; psz
0x18001de48  call    cs:__imp_SysAllocStringByteLen
0x18001de4e  test    rax, rax
0x18001de51  jnz     loc_18001E151
0x18001de57  xor     edx, edx; struct VAR *
0x18001de59  mov     ecx, 800A0007h; int
0x18001de5e  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001de64  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x18001de69  mov     r15d, eax
0x18001de6c  jmp     loc_18001DA6D
0x18001de71  mov     rsi, rbx
0x18001de74  jmp     loc_18001DCDB
0x18001de79  test    r12b, r12b
0x18001de7c  jnz     loc_18001E18B
0x18001de82  cmp     [rsp+98h+arg_8], 0
0x18001de8a  jnz     loc_18001E199
0x18001de90  mov     eax, edi
0x18001de92  jmp     loc_18001DD3A
0x18001de97  xor     edx, edx; unsigned int
0x18001de99  lea     rcx, String; unsigned __int16 *
0x18001dea0  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18001dea5  xor     ecx, ecx
0x18001dea7  mov     edi, 800A000Eh
0x18001deac  test    rax, rax
0x18001deaf  mov     rsi, rax
0x18001deb2  cmovnz  edi, ecx
0x18001deb5  jmp     loc_18001DCD3
0x18001deba  xor     eax, eax
0x18001debc  jmp     loc_18001DC0B
0x18001dec1  test    r12b, r12b
0x18001dec4  jnz     loc_18001E1DF
0x18001deca  test    bl, bl
0x18001decc  jnz     loc_18001E1ED
0x18001ded2  mov     eax, 800A005Eh
0x18001ded7  jmp     loc_18001DD3A
0x18001dedc  test    r9w, ax
0x18001dee0  jnz     short loc_18001DEF2
0x18001dee2  movzx   ecx, ax; int
0x18001dee5  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001deea  test    eax, eax
0x18001deec  jnz     loc_18001DDED
0x18001def2  mov     rcx, rbp; bstr
  ... truncated ...
```
