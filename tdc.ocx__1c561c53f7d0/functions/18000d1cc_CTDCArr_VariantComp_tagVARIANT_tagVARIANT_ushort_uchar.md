# CTDCArr::VariantComp(tagVARIANT *,tagVARIANT *,ushort,uchar)

- ea: `0x18000d1cc`
- end: `0x18000d2aa`
- name: `?VariantComp@CTDCArr@@AEAAHPEAUtagVARIANT@@0GE@Z`
- size: `222`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned __int16, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b670`
- `0x18000bd8c`
- `0x18000ca08`
- `0x18000d670`

## callees

- `0x18000d1cc`
- `0x18000ec3c`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18000d26f`

## pseudocode

```c
char __fastcall CTDCArr::VariantComp(CTDCArr *this, struct tagVARIANT *a2, struct tagVARIANT *a3, VARTYPE a4, char a5)
{
  VARTYPE vt; // cx
  int v6; // eax
  SHORT iVal; // cx
  bool v8; // zf
  unsigned __int16 *bstrVal; // r9
  unsigned __int16 *v10; // r8
  const WCHAR *v11; // rdx
  const WCHAR *v12; // rcx
  double dblVal; // xmm1_8
  double v14; // xmm0_8
  LONG lVal; // ecx

  vt = a3->vt;
  LOBYTE(v6) = 1;
  if ( a2->vt == 1 )
  {
    iVal = vt - 1;
    return -(iVal != 0);
  }
  if ( vt == 1 )
    return v6;
  if ( a2->vt != a4 )
  {
    v8 = vt == a4;
    goto LABEL_7;
  }
  if ( vt != a4 )
  {
LABEL_26:
    LOBYTE(v6) = -1;
    return v6;
  }
  if ( a4 == 3 )
  {
    lVal = a2->lVal;
    if ( lVal >= a3->lVal )
    {
      LOBYTE(v6) = lVal > a3->lVal;
      return v6;
    }
    goto LABEL_26;
  }
  if ( a4 == 5 || a4 == 7 )
  {
    dblVal = a2->dblVal;
    v14 = a3->dblVal;
    if ( v14 <= dblVal )
    {
      LOBYTE(v6) = dblVal > v14;
      return v6;
    }
    goto LABEL_26;
  }
  if ( a4 != 8 )
  {
    LOBYTE(v6) = 0;
    if ( a4 != 11 )
      return v6;
    iVal = a3->iVal;
    if ( !a2->iVal )
      return -(iVal != 0);
    v8 = iVal == 0;
LABEL_7:
    LOBYTE(v6) = v8;
    return v6;
  }
  bstrVal = a3->bstrVal;
  v10 = a2->bstrVal;
  if ( a5 )
  {
    LOBYTE(v6) = wch_cmp(v10, bstrVal);
  }
  else
  {
    v11 = &psz1;
    v12 = &psz1;
    if ( v10 )
      v12 = v10;
    if ( bstrVal )
      v11 = bstrVal;
    LOBYTE(v6) = StrCmpIW(v12, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x18000d1cc  movzx   ecx, word ptr [r8]
0x18000d1d0  mov     eax, 1
0x18000d1d5  cmp     [rdx], ax
0x18000d1d8  jnz     short loc_18000D1E7
0x18000d1da  sub     cx, ax
0x18000d1dd  neg     cx
0x18000d1e0  sbb     eax, eax
0x18000d1e2  jmp     locret_18000D2A9
0x18000d1e7  cmp     cx, ax
0x18000d1ea  jz      locret_18000D2A9
0x18000d1f0  cmp     [rdx], r9w
0x18000d1f4  jz      short loc_18000D204
0x18000d1f6  xor     eax, eax
0x18000d1f8  cmp     cx, r9w
0x18000d1fc  setz    al
0x18000d1ff  jmp     locret_18000D2A9
0x18000d204  cmp     cx, r9w
0x18000d208  jnz     loc_18000D29B
0x18000d20e  movzx   ecx, r9w
0x18000d212  sub     ecx, 3
0x18000d215  jz      short loc_18000D292
0x18000d217  sub     ecx, 2
0x18000d21a  jz      short loc_18000D276
0x18000d21c  sub     ecx, 2
0x18000d21f  jz      short loc_18000D276
0x18000d221  sub     ecx, eax
0x18000d223  jz      short loc_18000D23C
0x18000d225  xor     eax, eax
0x18000d227  cmp     ecx, 3
0x18000d22a  jnz     short locret_18000D2A9
0x18000d22c  movzx   ecx, word ptr [r8+8]
0x18000d231  cmp     [rdx+8], ax
0x18000d235  jz      short loc_18000D1DD
0x18000d237  test    cx, cx
0x18000d23a  jmp     short loc_18000D1FC
0x18000d23c  mov     r9, [r8+8]
0x18000d240  xor     eax, eax
0x18000d242  mov     r8, [rdx+8]
0x18000d246  cmp     [rsp+arg_20], al
0x18000d24a  jz      short loc_18000D257
0x18000d24c  mov     rdx, r9; unsigned __int16 *
0x18000d24f  mov     rcx, r8; unsigned __int16 *
0x18000d252  jmp     ?wch_cmp@@YAHPEAG0@Z; wch_cmp(ushort *,ushort *)
0x18000d257  test    r8, r8
0x18000d25a  lea     rdx, psz1
0x18000d261  mov     rcx, rdx
0x18000d264  cmovnz  rcx, r8
0x18000d268  test    r9, r9
0x18000d26b  cmovnz  rdx, r9
0x18000d26f  jmp     cs:__imp_StrCmpIW
0x18000d276  movsd   xmm1, qword ptr [rdx+8]
0x18000d27b  movsd   xmm0, qword ptr [r8+8]
0x18000d281  comisd  xmm0, xmm1
0x18000d285  ja      short loc_18000D29B
0x18000d287  xor     eax, eax
0x18000d289  comisd  xmm1, xmm0
0x18000d28d  setnbe  al
0x18000d290  jmp     short locret_18000D2A9
0x18000d292  mov     ecx, [rdx+8]
0x18000d295  cmp     ecx, [r8+8]
0x18000d299  jge     short loc_18000D2A0
0x18000d29b  or      eax, 0FFFFFFFFh
0x18000d29e  jmp     short locret_18000D2A9
0x18000d2a0  xor     eax, eax
0x18000d2a2  cmp     ecx, [r8+8]
0x18000d2a6  setnle  al
0x18000d2a9  retn
```
