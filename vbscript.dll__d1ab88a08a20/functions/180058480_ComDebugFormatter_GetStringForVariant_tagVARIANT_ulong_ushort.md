# ComDebugFormatter::GetStringForVariant(tagVARIANT *,ulong,ushort * *)

- ea: `0x180058480`
- end: `0x1800586ac`
- name: `?GetStringForVariant@ComDebugFormatter@@UEAAJPEAUtagVARIANT@@KPEAPEAG@Z`
- size: `556`
- prototype: `int(ComDebugFormatter *__hidden this, struct tagVARIANT *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001199c`
- `0x180058158`
- `0x180058228`
- `0x1800582bc`
- `0x180058480`
- `0x1800586b4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180058686`
- `OLEAUT32!__imp_VariantClear` at `0x180058686`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800584ef`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800584ef`
- `OLEAUT32!__imp_VarBstrFromR4` at `0x1800585c6`
- `OLEAUT32!__imp_VarBstrFromR4` at `0x1800585c6`
- `OLEAUT32!__imp_VarBstrFromR8` at `0x1800585a4`
- `OLEAUT32!__imp_VarBstrFromR8` at `0x1800585a4`

## pseudocode

```c
HRESULT __fastcall ComDebugFormatter::GetStringForVariant(
        ComDebugFormatter *this,
        struct tagVARIANT *a2,
        int a3,
        unsigned __int16 **a4)
{
  VARIANT *p_pvarDest; // r10
  HRESULT result; // eax
  VARTYPE vt; // ax
  int v9; // ebx
  const wchar_t *bstrVal; // rcx
  HRESULT HexLiteral; // eax
  const unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rax
  VARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  p_pvarDest = a2;
  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( !a2 )
    return -2147024809;
  if ( a3 != 16 && a3 != 10 )
    return -2147467263;
  vt = a2->vt;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( (vt & 0x4000) != 0 )
  {
    result = VariantCopyInd(&pvarDest, a2);
    v9 = result;
    if ( result < 0 )
      return result;
    vt = pvarDest.vt;
    p_pvarDest = &pvarDest;
  }
  else
  {
    v9 = 0;
  }
  if ( vt > 9u )
  {
    if ( vt == 11 )
    {
      v12 = L"False";
      if ( p_pvarDest->iVal )
        v12 = L"True";
      goto LABEL_47;
    }
    if ( vt != 13 )
    {
      if ( vt != 16 && vt != 17 && vt != 18 && vt != 19 && (unsigned int)vt - 22 >= 2 )
        goto LABEL_38;
      goto LABEL_39;
    }
    goto LABEL_42;
  }
  switch ( vt )
  {
    case 9u:
LABEL_42:
      v12 = L"Nothing";
      if ( p_pvarDest->llVal )
        v12 = &String;
      goto LABEL_47;
    case 0u:
      v12 = L"Empty";
LABEL_47:
      v13 = _SysAllocString(v12);
      *a4 = v13;
      if ( !v13 )
        v9 = -2147024882;
      goto LABEL_49;
    case 1u:
      v12 = L"Null";
      goto LABEL_47;
    case 2u:
    case 3u:
LABEL_39:
      if ( a3 == 16 )
        HexLiteral = GetHexLiteral(p_pvarDest, a4);
      else
        HexLiteral = GetDecimalLiteral(p_pvarDest, a4);
      break;
    case 4u:
      HexLiteral = VarBstrFromR4(p_pvarDest->fltVal, 0x409u, 0x80000000, a4);
      break;
    case 5u:
      HexLiteral = VarBstrFromR8(p_pvarDest->dblVal, 0x409u, 0x80000000, a4);
      break;
    case 7u:
      HexLiteral = GetDateLiteral((unsigned int)vt - 7, a4);
      break;
    case 8u:
      bstrVal = &String;
      if ( p_pvarDest->llVal )
        bstrVal = p_pvarDest->bstrVal;
      HexLiteral = GetStringLiteral(bstrVal, a4);
      break;
    default:
LABEL_38:
      *a4 = 0;
      goto LABEL_49;
  }
  v9 = HexLiteral;
LABEL_49:
  VariantClear(&pvarDest);
  if ( v9 >= 0 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x180058480  mov     [rsp+arg_0], rbx
0x180058485  mov     [rsp+arg_8], rsi
0x18005848a  push    rdi
0x18005848b  sub     rsp, 40h
0x18005848f  mov     rdi, r9
0x180058492  mov     esi, r8d
0x180058495  mov     r10, rdx
0x180058498  test    r9, r9
0x18005849b  jnz     short loc_1800584A7
0x18005849d  mov     eax, 80004003h
0x1800584a2  jmp     loc_18005869B
0x1800584a7  mov     qword ptr [r9], 0
0x1800584ae  test    rdx, rdx
0x1800584b1  jnz     short loc_1800584BD
0x1800584b3  mov     eax, 80070057h
0x1800584b8  jmp     loc_18005869B
0x1800584bd  cmp     esi, 10h
0x1800584c0  jz      short loc_1800584D1
0x1800584c2  cmp     esi, 0Ah
0x1800584c5  jz      short loc_1800584D1
0x1800584c7  mov     eax, 80004001h
0x1800584cc  jmp     loc_18005869B
0x1800584d1  xor     eax, eax
0x1800584d3  xorps   xmm0, xmm0
0x1800584d6  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x1800584db  movzx   eax, word ptr [rdx]
0x1800584de  bt      ax, 0Eh
0x1800584e3  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x1800584e8  jnb     short loc_180058511
0x1800584ea  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x1800584ef  call    cs:__imp_VariantCopyInd
0x1800584f6  nop     dword ptr [rax+rax+00h]
0x1800584fb  mov     ebx, eax
0x1800584fd  test    eax, eax
0x1800584ff  js      loc_18005869B
0x180058505  movzx   eax, word ptr [rsp+48h+pvarDest]
0x18005850a  lea     r10, [rsp+48h+pvarDest]
0x18005850f  jmp     short loc_180058513
0x180058511  xor     ebx, ebx
0x180058513  movzx   ecx, ax
0x180058516  cmp     ecx, 9
0x180058519  ja      loc_1800585EC
0x18005851f  jz      loc_18005863C
0x180058525  test    ecx, ecx
0x180058527  jz      loc_1800585E0
0x18005852d  sub     ecx, 1
0x180058530  jz      loc_1800585D4
0x180058536  sub     ecx, 1
0x180058539  jz      loc_18005861D
0x18005853f  sub     ecx, 1
0x180058542  jz      loc_18005861D
0x180058548  sub     ecx, 1
0x18005854b  jz      short loc_1800585B2
0x18005854d  sub     ecx, 1
0x180058550  jz      short loc_180058590
0x180058552  sub     ecx, 2
0x180058555  jz      short loc_180058580
0x180058557  cmp     ecx, 1
0x18005855a  jnz     loc_180058614
0x180058560  cmp     qword ptr [r10+8], 0
0x180058565  lea     rcx, String
0x18005856c  mov     rdx, rdi
0x18005856f  cmovnz  rcx, [r10+8]
0x180058574  call    GetStringLiteral
0x180058579  mov     ebx, eax
0x18005857b  jmp     loc_180058681
0x180058580  movsd   xmm0, qword ptr [r10+8]
0x180058586  mov     rdx, rdi
0x180058589  call    GetDateLiteral
0x18005858e  jmp     short loc_180058579
0x180058590  movsd   xmm0, qword ptr [r10+8]; dblIn
0x180058596  mov     r9, rdi; pbstrOut
0x180058599  mov     edx, 409h; lcid
0x18005859e  mov     r8d, 80000000h; dwFlags
0x1800585a4  call    cs:__imp_VarBstrFromR8
0x1800585ab  nop     dword ptr [rax+rax+00h]
0x1800585b0  jmp     short loc_180058579
0x1800585b2  movss   xmm0, dword ptr [r10+8]; fltIn
0x1800585b8  mov     r9, rdi; pbstrOut
0x1800585bb  mov     edx, 409h; lcid
0x1800585c0  mov     r8d, 80000000h; dwFlags
0x1800585c6  call    cs:__imp_VarBstrFromR4
0x1800585cd  nop     dword ptr [rax+rax+00h]
0x1800585d2  jmp     short loc_180058579
0x1800585d4  lea     rcx, aNull; "Null"
0x1800585db  jmp     loc_18005866E
0x1800585e0  lea     rcx, aEmpty; "Empty"
0x1800585e7  jmp     loc_18005866E
0x1800585ec  sub     ecx, 0Bh
0x1800585ef  jz      short loc_180058655
0x1800585f1  sub     ecx, 2
0x1800585f4  jz      short loc_18005863C
0x1800585f6  sub     ecx, 3
0x1800585f9  jz      short loc_18005861D
0x1800585fb  sub     ecx, 1
0x1800585fe  jz      short loc_18005861D
0x180058600  sub     ecx, 1
0x180058603  jz      short loc_18005861D
0x180058605  sub     ecx, 1
0x180058608  jz      short loc_18005861D
0x18005860a  sub     ecx, 3
0x18005860d  jz      short loc_18005861D
0x18005860f  cmp     ecx, 1
0x180058612  jz      short loc_18005861D
0x180058614  mov     qword ptr [rdi], 0
0x18005861b  jmp     short loc_180058681
0x18005861d  mov     rdx, rdi
0x180058620  mov     rcx, r10
0x180058623  cmp     esi, 10h
0x180058626  jnz     short loc_180058632
0x180058628  call    GetHexLiteral
0x18005862d  jmp     loc_180058579
0x180058632  call    GetDecimalLiteral
0x180058637  jmp     loc_180058579
0x18005863c  cmp     qword ptr [r10+8], 0
0x180058641  lea     rcx, aNothing; "Nothing"
0x180058648  lea     rax, String
0x18005864f  cmovnz  rcx, rax
0x180058653  jmp     short loc_18005866E
0x180058655  xor     eax, eax
0x180058657  lea     rcx, aFalse_0; "False"
0x18005865e  cmp     ax, [r10+8]
0x180058663  lea     rdx, aTrue_0; "True"
0x18005866a  cmovnz  rcx, rdx; unsigned __int16 *
0x18005866e  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180058673  test    rax, rax
0x180058676  mov     [rdi], rax
0x180058679  mov     ecx, 8007000Eh
0x18005867e  cmovz   ebx, ecx
0x180058681  lea     rcx, [rsp+48h+pvarDest]; pvarg
0x180058686  call    cs:__imp_VariantClear
0x18005868d  nop     dword ptr [rax+rax+00h]
0x180058692  xor     eax, eax
0x180058694  test    ebx, ebx
0x180058696  cmovns  ebx, eax
0x180058699  mov     eax, ebx
0x18005869b  mov     rbx, [rsp+48h+arg_0]
0x1800586a0  mov     rsi, [rsp+48h+arg_8]
0x1800586a5  add     rsp, 40h
0x1800586a9  pop     rdi
0x1800586aa  retn
```
