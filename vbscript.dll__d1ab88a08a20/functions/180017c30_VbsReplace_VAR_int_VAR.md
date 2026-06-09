# VbsReplace(VAR *,int,VAR *)

- ea: `0x180017c30`
- end: `0x1800184af`
- name: `?VbsReplace@@YAJPEAVVAR@@H0@Z`
- size: `2175`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180011650`
- `0x180015fec`
- `0x180016a60`
- `0x180017c30`
- `0x180018aa0`
- `0x180019650`
- `0x1800196f0`
- `0x180019d50`
- `0x1800252c0`
- `0x180026150`
- `0x1800261b8`
- `0x18004237c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017e79`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017e79`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180018412`
- `OLEAUT32!__imp_SysFreeString` at `0x180018426`
- `OLEAUT32!__imp_SysFreeString` at `0x18001843a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001844e`
- `OLEAUT32!__imp_SysFreeString` at `0x180018462`
- `OLEAUT32!__imp_SysFreeString` at `0x180018476`
- `OLEAUT32!__imp_SysFreeString` at `0x18001848a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001849e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180018412`
- `OLEAUT32!__imp_SysFreeString` at `0x180018426`
- `OLEAUT32!__imp_SysFreeString` at `0x18001843a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001844e`
- `OLEAUT32!__imp_SysFreeString` at `0x180018462`
- `OLEAUT32!__imp_SysFreeString` at `0x180018476`
- `OLEAUT32!__imp_SysFreeString` at `0x18001848a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001849e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180017f1f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180017f1f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180017fef`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018098`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018166`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180017fef`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018098`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018166`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001800a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800180b3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180018181`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001800a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800180b3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180018181`
- `KERNEL32!IsValidLocale` at `0x18001833d`
- `KERNEL32!IsValidLocale` at `0x18001833d`
- `KERNEL32!TlsGetValue` at `0x180017c8a`
- `KERNEL32!TlsGetValue` at `0x180017c8a`

## pseudocode

```c
__int64 __fastcall VbsReplace(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v3; // rdi
  LCID v5; // r15d
  LCID Val; // eax
  _QWORD *Value; // rax
  unsigned int v8; // eax
  __int16 v9; // ax
  struct IDispatch **v10; // rcx
  VARTYPE v11; // r10
  __int64 v12; // r14
  __int64 v13; // rbp
  struct IDispatch **v14; // rbx
  char v15; // r12
  unsigned __int16 v16; // ax
  __int64 v17; // r13
  struct IDispatch **v18; // rdi
  char v19; // bl
  __int16 v20; // r9
  char v21; // r12
  unsigned __int16 v22; // ax
  unsigned __int16 *v23; // rsi
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  WCHAR *v27; // rbx
  int v28; // edi
  struct VAR *v29; // rax
  unsigned __int16 v31; // ax
  UINT v32; // edx
  const unsigned __int16 *v33; // r8
  int v34; // r9d
  BSTR v35; // rax
  unsigned __int16 lpVtbl; // ax
  unsigned __int16 v37; // ax
  UINT v38; // edx
  const unsigned __int16 *v39; // r8
  int v40; // r9d
  BSTR v41; // rax
  UINT v42; // edx
  const unsigned __int16 *v43; // r8
  int v44; // r9d
  BSTR v45; // rax
  struct VAR *v46; // rax
  struct VAR *v47; // rax
  int Default; // eax
  const unsigned __int16 *v49; // r8
  int v50; // r9d
  int v51; // eax
  const unsigned __int16 *v52; // r8
  int v53; // r9d
  int v54; // eax
  const unsigned __int16 *v55; // r8
  int v56; // r9d
  int v57; // r9d
  int v58; // eax
  int v59; // eax
  unsigned int v60; // eax
  int v61; // [rsp+30h] [rbp-68h]
  SAFEARRAY *psa; // [rsp+38h] [rbp-60h] BYREF
  struct VAR *v63[3]; // [rsp+40h] [rbp-58h] BYREF
  char v65; // [rsp+A8h] [rbp+10h]
  unsigned int v66; // [rsp+B0h] [rbp+18h]
  int v67; // [rsp+B8h] [rbp+20h]

  *(_WORD *)a1 = 1;
  v3 = a3;
  if ( (unsigned int)(a2 - 3) > 3 )
    return 2148139458LL;
  if ( a2 == 6 )
  {
    Val = VAR::UlGetVal(a3);
    v3 = (struct VAR *)((char *)v3 + 24);
    v5 = Val;
    if ( Val >= 2 )
    {
      v61 = 1;
      if ( !IsValidLocale(Val, 1u) )
        return 2148139013LL;
      goto LABEL_140;
    }
  }
  else
  {
    v5 = 0;
  }
  v61 = v5;
  Value = TlsGetValue(g_luTls);
  if ( !Value || !Value[3] )
    GetDefaultLocale();
  if ( a2 < 5 )
    goto LABEL_8;
LABEL_140:
  v59 = VAR::UlGetVal(v3);
  v3 = (struct VAR *)((char *)v3 + 24);
  v67 = v59;
  if ( v59 == -1 )
  {
LABEL_8:
    v67 = 0x7FFFFFFF;
    goto LABEL_9;
  }
  if ( v59 < 0 )
    return 2148139013LL;
LABEL_9:
  if ( a2 >= 4 )
  {
    v60 = VAR::UlGetVal(v3);
    if ( v60 - 1 <= 0x3FFFFFFD )
    {
      v3 = (struct VAR *)((char *)v3 + 24);
      v8 = v60 - 1;
      goto LABEL_11;
    }
    return 2148139013LL;
  }
  v8 = 0;
LABEL_11:
  v66 = v8;
  v9 = *(_WORD *)v3;
  if ( *(_WORD *)v3 == 16396 || v9 == 74 )
  {
    v10 = (struct IDispatch **)*((_QWORD *)v3 + 1);
    v9 = *(_WORD *)v10;
  }
  else
  {
    v10 = (struct IDispatch **)v3;
  }
  v63[0] = (struct VAR *)v10;
  if ( v9 == 9 )
  {
    Default = VAR::ObjGetDefault(v10[1], v63);
    if ( Default < 0 )
      RaiseErrorHr(Default, 0, v49, v50);
    v10 = (struct IDispatch **)v63[0];
  }
  v11 = 8;
  v12 = -1;
  if ( *(_WORD *)v10 == 8 )
  {
    v13 = (__int64)v10[1];
  }
  else
  {
    if ( *(_WORD *)v10 == 1 )
    {
      v13 = -1;
      v14 = (struct IDispatch **)((char *)v3 + 24);
LABEL_20:
      v15 = 0;
      goto LABEL_21;
    }
    v46 = VAR::PvarConvert((VAR *)v10, 8u);
    v11 = 8;
    v13 = *((_QWORD *)v46 + 1);
  }
  v14 = (struct IDispatch **)((char *)v3 + 24);
  if ( !v13 || v13 == -1 || v3 == (struct VAR *)-24LL )
    goto LABEL_20;
  v31 = *(_WORD *)v14;
  if ( *(_WORD *)v14 == 16396 || v31 == 74 )
    v31 = **((_WORD **)v3 + 4);
  if ( v31 == 8 || (v31 & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(v31) )
    goto LABEL_20;
  v32 = SysStringByteLen((BSTR)v13);
  v35 = 0;
  if ( v32 < 0x7FFFFFFD )
    v35 = SysAllocStringByteLen((LPCSTR)v13, v32);
  if ( !v35 )
    RaiseErrorHr(-2146828281, 0, v33, v34);
  v13 = (__int64)v35;
  v15 = 1;
  v11 = 8;
LABEL_21:
  v16 = *(_WORD *)v14;
  v65 = v15;
  if ( *(_WORD *)v14 == 16396 || v16 == 74 )
  {
    v14 = (struct IDispatch **)*((_QWORD *)v3 + 4);
    v16 = *(_WORD *)v14;
  }
  v63[0] = (struct VAR *)v14;
  if ( v16 == 9 )
  {
    v51 = VAR::ObjGetDefault(v14[1], v63);
    if ( v51 < 0 )
      RaiseErrorHr(v51, 0, v52, v53);
    v14 = (struct IDispatch **)v63[0];
    v11 = 8;
  }
  if ( v11 == *(_WORD *)v14 )
  {
    v17 = (__int64)v14[1];
  }
  else if ( *(_WORD *)v14 == 1 )
  {
    v17 = -1;
  }
  else
  {
    v47 = VAR::PvarConvert((VAR *)v14, v11);
    v11 = 8;
    v17 = *((_QWORD *)v47 + 1);
  }
  v18 = (struct IDispatch **)((char *)v3 + 48);
  if ( !v15 && (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v18 )
  {
    lpVtbl = *(_WORD *)v18;
    if ( *(_WORD *)v18 == 16396 || lpVtbl == 74 )
      lpVtbl = (unsigned __int16)v18[1]->lpVtbl;
    v20 = 0x4000;
    if ( lpVtbl == 8 || (lpVtbl & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(lpVtbl) )
    {
      v19 = v15;
      goto LABEL_31;
    }
    v42 = SysStringByteLen((BSTR)v13);
    v45 = 0;
    if ( v42 < 0x7FFFFFFD )
      v45 = SysAllocStringByteLen((LPCSTR)v13, v42);
    if ( !v45 )
      RaiseErrorHr(-2146828281, 0, v43, v44);
    v19 = 1;
    v13 = (__int64)v45;
    v65 = 1;
    v11 = 8;
  }
  else
  {
    v19 = v15;
  }
  v20 = 0x4000;
LABEL_31:
  v21 = 0;
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v18 )
  {
    v37 = *(_WORD *)v18;
    if ( *(_WORD *)v18 == 16396 || v37 == 74 )
      v37 = (unsigned __int16)v18[1]->lpVtbl;
    if ( v37 != 8 && ((v37 & (unsigned __int16)v20) != 0 || !(unsigned int)VAR::IsSimpleType(v37)) )
    {
      v38 = SysStringByteLen((BSTR)v17);
      v41 = 0;
      if ( v38 < 0x7FFFFFFD )
        v41 = SysAllocStringByteLen((LPCSTR)v17, v38);
      if ( !v41 )
        RaiseErrorHr(-2146828281, 0, v39, v40);
      v17 = (__int64)v41;
      v21 = 1;
      v11 = 8;
    }
  }
  v22 = *(_WORD *)v18;
  if ( *(_WORD *)v18 == 16396 || v22 == 74 )
  {
    v18 = (struct IDispatch **)v18[1];
    v22 = *(_WORD *)v18;
  }
  v63[0] = (struct VAR *)v18;
  if ( v22 == 9 )
  {
    v54 = VAR::ObjGetDefault(v18[1], v63);
    if ( v54 < 0 )
      RaiseErrorHr(v54, 0, v55, v56);
    v18 = (struct IDispatch **)v63[0];
    v11 = 8;
  }
  if ( v11 == *(_WORD *)v18 )
  {
    v12 = (__int64)v18[1];
  }
  else if ( *(_WORD *)v18 != 1 )
  {
    v12 = *((_QWORD *)VAR::PvarConvert((VAR *)v18, v11) + 1);
  }
  if ( v13 == -1 || v17 == -1 || v12 == -1 )
  {
    if ( v21 )
      SysFreeString((BSTR)v17);
    if ( v19 )
      SysFreeString((BSTR)v13);
    return 2148139102LL;
  }
  v23 = 0;
  psa = 0;
  v63[0] = 0;
  if ( v12 )
    v24 = *(_DWORD *)(v12 - 4);
  else
    v24 = 0;
  v25 = v24 >> 1;
  if ( v66 > v25 )
  {
    v28 = -2146828274;
    v23 = _SysAllocStringLen(&String, 0);
    if ( v23 )
      v28 = 0;
    goto LABEL_56;
  }
  v26 = v25 - v66;
  if ( (unsigned __int64)(2 * v26) < 0x7FFFFFFD )
  {
    v27 = SysAllocStringLen((const OLECHAR *)(v12 + 2LL * v66), v26);
    if ( v27 )
    {
      if ( !v12 || !*(_DWORD *)(v12 - 4) || !v17 || !*(_DWORD *)(v17 - 4) || !v67 )
      {
        v23 = v27;
LABEL_57:
        *(_WORD *)a1 = 74;
        v29 = PvarAlloc();
        if ( v29 )
        {
          *(_WORD *)v29 = 8;
          *((_QWORD *)v29 + 1) = v23;
          *((_QWORD *)a1 + 1) = v29;
          if ( v21 )
            SysFreeString((BSTR)v17);
          if ( v65 )
            SysFreeString((BSTR)v13);
          return 0;
        }
        else
        {
          *((_QWORD *)a1 + 1) = 0;
          if ( v21 )
            SysFreeString((BSTR)v17);
          if ( v65 )
            SysFreeString((BSTR)v13);
          return 2148139015LL;
        }
      }
      if ( *((_DWORD *)v27 - 1) )
      {
        v28 = rtStandardSplit(v27, (LPCWCH)v17, v61, (__int64)&psa);
        if ( v28 < 0 )
        {
LABEL_53:
          SysFreeString(v27);
          goto LABEL_54;
        }
      }
      else
      {
        psa = psaMakeOneDim(0);
        if ( !psa )
        {
          v28 = -2146828281;
          goto LABEL_53;
        }
      }
      if ( v13 )
        v57 = *(_DWORD *)(v13 - 4);
      else
        v57 = 0;
      v58 = rtJoin(0, (unsigned int)&psa, v13, v57, (__int64)v63);
      v23 = (unsigned __int16 *)v63[0];
      v28 = v58;
      if ( v58 >= 0 )
        v28 = 0;
      goto LABEL_53;
    }
  }
  v28 = -2146828274;
LABEL_54:
  if ( psa )
    SafeArrayDestroy(psa);
LABEL_56:
  if ( v28 >= 0 )
    goto LABEL_57;
  if ( v21 )
    SysFreeString((BSTR)v17);
  if ( v65 )
    SysFreeString((BSTR)v13);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180017c30  mov     [rsp+arg_0], rcx
0x180017c35  push    rbx
0x180017c36  push    rbp
0x180017c37  push    rdi
0x180017c38  sub     rsp, 80h
0x180017c3f  lea     eax, [rdx-3]
0x180017c42  mov     ebp, 1
0x180017c47  mov     [rcx], bp
0x180017c4a  mov     rdi, r8
0x180017c4d  mov     ebx, edx
0x180017c4f  cmp     eax, 3
0x180017c52  ja      loc_180018267
0x180017c58  mov     [rsp+98h+var_40], r15
0x180017c5d  cmp     edx, 6
0x180017c60  jz      short loc_180017C67
0x180017c62  xor     r15d, r15d
0x180017c65  jmp     short loc_180017C7F
0x180017c67  mov     rcx, rdi; this
0x180017c6a  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x180017c6f  add     rdi, 18h
0x180017c73  mov     r15d, eax
0x180017c76  cmp     eax, 2
0x180017c79  jnb     loc_180018335
0x180017c7f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180017c85  mov     [rsp+98h+var_68], r15d
0x180017c8a  call    cs:__imp_TlsGetValue
0x180017c91  nop     dword ptr [rax+rax+00h]
0x180017c96  test    rax, rax
0x180017c99  jz      loc_1800180D5
0x180017c9f  mov     rax, [rax+18h]
0x180017ca3  test    rax, rax
0x180017ca6  jz      loc_1800180D5
0x180017cac  mov     r15d, [rax+0BCh]
0x180017cb3  cmp     ebx, 5
0x180017cb6  jge     loc_18001834D
0x180017cbc  mov     eax, 7FFFFFFFh
0x180017cc1  mov     [rsp+98h+arg_18], eax
0x180017cc8  cmp     ebx, 4
0x180017ccb  jge     loc_18001837B
0x180017cd1  xor     eax, eax
0x180017cd3  mov     [rsp+98h+var_20], rsi
0x180017cd8  mov     esi, 400Ch
0x180017cdd  mov     [rsp+98h+arg_10], eax
0x180017ce4  movzx   eax, word ptr [rdi]
0x180017ce7  mov     [rsp+98h+var_30], r13
0x180017cec  cmp     ax, si
0x180017cef  jz      loc_1800181A3
0x180017cf5  cmp     ax, 4Ah ; 'J'
0x180017cf9  jz      loc_1800181A3
0x180017cff  mov     rcx, rdi; this
0x180017d02  mov     r13d, 9
0x180017d08  mov     [rsp+98h+var_58], rcx
0x180017d0d  cmp     r13w, ax
0x180017d11  jz      loc_18001828C
0x180017d17  movzx   eax, word ptr [rcx]
0x180017d1a  mov     r10d, 8
0x180017d20  mov     [rsp+98h+var_28], r12
0x180017d25  mov     edx, 4000h
0x180017d2a  mov     [rsp+98h+var_38], r14
0x180017d2f  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180017d36  cmp     r10w, ax
0x180017d3a  jnz     loc_1800181CA
0x180017d40  mov     rbp, [rcx+8]
0x180017d44  lea     rbx, [rdi+18h]
0x180017d48  test    rbp, rbp
0x180017d4b  jz      short loc_180017D5B
0x180017d4d  cmp     rbp, r14
0x180017d50  jz      short loc_180017D5B
0x180017d52  test    rbx, rbx
0x180017d55  jnz     loc_180017FB7
0x180017d5b  xor     r12b, r12b
0x180017d5e  movzx   eax, word ptr [rbx]
0x180017d61  mov     [rsp+98h+arg_8], r12b
0x180017d69  cmp     ax, si
0x180017d6c  jz      loc_1800181AF
0x180017d72  cmp     ax, 4Ah ; 'J'
0x180017d76  jz      loc_1800181AF
0x180017d7c  mov     [rsp+98h+var_58], rbx
0x180017d81  cmp     r13w, ax
0x180017d85  jz      loc_1800182AC
0x180017d8b  movzx   eax, word ptr [rbx]
0x180017d8e  cmp     r10w, ax
0x180017d92  jnz     loc_1800181EF
0x180017d98  mov     r13, [rbx+8]
0x180017d9c  add     rdi, 30h ; '0'
0x180017da0  test    r12b, r12b
0x180017da3  jnz     short loc_180017DB8
0x180017da5  lea     rax, [rbp-1]
0x180017da9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017dad  ja      short loc_180017DB8
0x180017daf  test    rdi, rdi
0x180017db2  jnz     loc_18001802C
0x180017db8  movzx   ebx, [rsp+98h+arg_8]
0x180017dc0  mov     r9d, 4000h
0x180017dc6  xor     r12b, r12b
0x180017dc9  lea     rax, [r13-1]
0x180017dcd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017dd1  ja      short loc_180017DDC
0x180017dd3  test    rdi, rdi
0x180017dd6  jnz     loc_18001805F
0x180017ddc  movzx   eax, word ptr [rdi]
0x180017ddf  cmp     ax, si
0x180017de2  jz      loc_1800181BB
0x180017de8  cmp     ax, 4Ah ; 'J'
0x180017dec  jz      loc_1800181BB
0x180017df2  mov     ecx, 9
0x180017df7  mov     [rsp+98h+var_58], rdi
0x180017dfc  cmp     cx, ax
0x180017dff  jz      loc_1800182D2
0x180017e05  movzx   eax, word ptr [rdi]
0x180017e08  cmp     r10w, ax
0x180017e0c  jnz     loc_180018217
0x180017e12  mov     r14, [rdi+8]
0x180017e16  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180017e1a  jz      loc_180018132
0x180017e20  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180017e24  jz      loc_180018132
0x180017e2a  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180017e2e  jz      loc_180018132
0x180017e34  xor     esi, esi
0x180017e36  mov     [rsp+98h+psa], 0
0x180017e3f  mov     [rsp+98h+var_58], rsi
0x180017e44  test    r14, r14
0x180017e47  jz      loc_18001812B
0x180017e4d  mov     eax, [r14-4]
0x180017e51  mov     ecx, [rsp+98h+arg_10]
0x180017e58  shr     eax, 1
0x180017e5a  cmp     ecx, eax
0x180017e5c  ja      loc_180018108
0x180017e62  sub     eax, ecx
0x180017e64  mov     edx, eax; ui
0x180017e66  add     rax, rax
0x180017e69  cmp     rax, 7FFFFFFDh
0x180017e6f  jnb     loc_18001825D
0x180017e75  lea     rcx, [r14+rcx*2]; strIn
0x180017e79  call    cs:__imp_SysAllocStringLen
0x180017e80  nop     dword ptr [rax+rax+00h]
0x180017e85  mov     rbx, rax
0x180017e88  test    rax, rax
0x180017e8b  jz      loc_18001825D
0x180017e91  test    r14, r14
0x180017e94  jz      loc_1800180E2
0x180017e9a  cmp     [r14-4], esi
0x180017e9e  jz      loc_1800180E2
0x180017ea4  test    r13, r13
0x180017ea7  jz      loc_1800180E2
0x180017ead  cmp     [r13-4], esi
0x180017eb1  jz      loc_1800180E2
0x180017eb7  mov     eax, [rsp+98h+arg_18]
0x180017ebe  test    eax, eax
0x180017ec0  jz      loc_1800180E2
0x180017ec6  cmp     eax, 7FFFFFFFh
0x180017ecb  lea     r8d, [rax+1]
0x180017ecf  cmovnb  r8d, eax
0x180017ed3  cmp     [rbx-4], esi
0x180017ed6  jz      loc_1800183F0
0x180017edc  lea     rax, [rsp+98h+psa]
0x180017ee1  mov     r9d, r15d
0x180017ee4  mov     [rsp+98h+var_70], rax; __int64
0x180017ee9  mov     rdx, r13; LPCWCH
0x180017eec  mov     eax, [rsp+98h+var_68]
0x180017ef0  mov     rcx, rbx; lpWideCharStr
0x180017ef3  mov     [rsp+98h+var_78], eax; int
0x180017ef7  call    rtStandardSplit
0x180017efc  mov     edi, eax
0x180017efe  test    eax, eax
0x180017f00  jns     loc_1800182F8
0x180017f06  mov     rcx, rbx; bstrString
0x180017f09  call    cs:__imp_SysFreeString
0x180017f10  nop     dword ptr [rax+rax+00h]
0x180017f15  mov     rcx, [rsp+98h+psa]; psa
0x180017f1a  test    rcx, rcx
0x180017f1d  jz      short loc_180017F2B
0x180017f1f  call    cs:__imp_SafeArrayDestroy
0x180017f26  nop     dword ptr [rax+rax+00h]
0x180017f2b  test    edi, edi
0x180017f2d  js      loc_1800180EA
0x180017f33  mov     rbx, [rsp+98h+arg_0]
0x180017f3b  mov     word ptr [rbx], 4Ah ; 'J'
0x180017f40  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x180017f45  test    rax, rax
0x180017f48  jz      short loc_180017F72
0x180017f4a  mov     word ptr [rax], 8
0x180017f4f  mov     [rax+8], rsi
0x180017f53  mov     [rbx+8], rax
0x180017f57  test    r12b, r12b
0x180017f5a  jnz     loc_180018437
0x180017f60  cmp     [rsp+98h+arg_8], 0
0x180017f68  jnz     loc_18001844B
0x180017f6e  xor     eax, eax
0x180017f70  jmp     short loc_180017F92
0x180017f72  mov     [rbx+8], rax
0x180017f76  test    r12b, r12b
0x180017f79  jnz     loc_18001845F
0x180017f7f  cmp     [rsp+98h+arg_8], 0
0x180017f87  jnz     loc_180018473
0x180017f8d  mov     eax, 800A0007h
0x180017f92  mov     r14, [rsp+98h+var_38]
0x180017f97  mov     r12, [rsp+98h+var_28]
0x180017f9c  mov     r13, [rsp+98h+var_30]
0x180017fa1  mov     rsi, [rsp+98h+var_20]
0x180017fa6  mov     r15, [rsp+98h+var_40]
0x180017fab  add     rsp, 80h
0x180017fb2  pop     rdi
0x180017fb3  pop     rbp
0x180017fb4  pop     rbx
0x180017fb5  retn
0x180017fb7  movzx   eax, word ptr [rbx]
0x180017fba  cmp     ax, si
0x180017fbd  jz      loc_180018239
0x180017fc3  cmp     ax, 4Ah ; 'J'
0x180017fc7  jz      loc_180018239
0x180017fcd  cmp     ax, 8
0x180017fd1  jz      loc_180017D5B
0x180017fd7  test    dx, ax
0x180017fda  jnz     short loc_180017FEC
0x180017fdc  movzx   ecx, ax; int
0x180017fdf  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x180017fe4  test    eax, eax
0x180017fe6  jnz     loc_180017D5B
0x180017fec  mov     rcx, rbp; bstr
0x180017fef  call    cs:__imp_SysStringByteLen
0x180017ff6  nop     dword ptr [rax+rax+00h]
0x180017ffb  mov     edx, eax; len
0x180017ffd  xor     eax, eax
0x180017fff  cmp     edx, 7FFFFFFDh
0x180018005  jnb     short loc_180018016
0x180018007  mov     rcx, rbp; psz
0x18001800a  call    cs:__imp_SysAllocStringByteLen
0x180018011  nop     dword ptr [rax+rax+00h]
0x180018016  test    rax, rax
0x180018019  jnz     loc_1800183A3
0x18001801f  xor     edx, edx; struct VAR *
0x180018021  mov     ecx, 800A0007h; int
0x180018026  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001802c  movzx   eax, word ptr [rdi]
0x18001802f  cmp     ax, si
0x180018032  jz      loc_180018245
0x180018038  cmp     ax, 4Ah ; 'J'
0x18001803c  jz      loc_180018245
0x180018042  mov     r9d, 4000h
0x180018048  cmp     ax, 8
0x18001804c  jnz     loc_18001814D
0x180018052  movzx   ebx, [rsp+98h+arg_8]
0x18001805a  jmp     loc_180017DC6
0x18001805f  movzx   eax, word ptr [rdi]
0x180018062  cmp     ax, si
0x180018065  jz      loc_180018251
0x18001806b  cmp     ax, 4Ah ; 'J'
0x18001806f  jz      loc_180018251
0x180018075  cmp     ax, 8
0x180018079  jz      loc_180017DDC
0x18001807f  test    r9w, ax
0x180018083  jnz     short loc_180018095
0x180018085  movzx   ecx, ax; int
0x180018088  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001808d  test    eax, eax
0x18001808f  jnz     loc_180017DDC
0x180018095  mov     rcx, r13; bstr
0x180018098  call    cs:__imp_SysStringByteLen
0x18001809f  nop     dword ptr [rax+rax+00h]
0x1800180a4  mov     edx, eax; len
0x1800180a6  xor     eax, eax
0x1800180a8  cmp     edx, 7FFFFFFDh
0x1800180ae  jnb     short loc_1800180BF
0x1800180b0  mov     rcx, r13; psz
0x1800180b3  call    cs:__imp_SysAllocStringByteLen
0x1800180ba  nop     dword ptr [rax+rax+00h]
0x1800180bf  test    rax, rax
0x1800180c2  jnz     loc_1800183D5
0x1800180c8  xor     edx, edx; struct VAR *
0x1800180ca  mov     ecx, 800A0007h; int
0x1800180cf  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x1800180d5  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x1800180da  mov     r15d, eax
0x1800180dd  jmp     loc_180017CB3
0x1800180e2  mov     rsi, rbx
0x1800180e5  jmp     loc_180017F33
0x1800180ea  test    r12b, r12b
0x1800180ed  jnz     loc_18001840F
0x1800180f3  cmp     [rsp+98h+arg_8], 0
0x1800180fb  jnz     loc_180018423
0x180018101  mov     eax, edi
0x180018103  jmp     loc_180017F92
0x180018108  xor     edx, edx; unsigned int
0x18001810a  lea     rcx, String; unsigned __int16 *
0x180018111  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180018116  xor     ecx, ecx
0x180018118  mov     edi, 800A000Eh
0x18001811d  test    rax, rax
0x180018120  mov     rsi, rax
0x180018123  cmovnz  edi, ecx
0x180018126  jmp     loc_180017F2B
0x18001812b  xor     eax, eax
0x18001812d  jmp     loc_180017E51
0x180018132  test    r12b, r12b
0x180018135  jnz     loc_180018487
0x18001813b  test    bl, bl
0x18001813d  jnz     loc_18001849B
0x180018143  mov     eax, 800A005Eh
  ... truncated ...
```
