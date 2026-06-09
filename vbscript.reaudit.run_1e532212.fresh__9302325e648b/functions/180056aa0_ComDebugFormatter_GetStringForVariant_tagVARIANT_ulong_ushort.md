# ComDebugFormatter::GetStringForVariant(tagVARIANT *,ulong,ushort * *)

- ea: `0x180056aa0`
- end: `0x180056cb3`
- name: `?GetStringForVariant@ComDebugFormatter@@UEAAJPEAUtagVARIANT@@KPEAPEAG@Z`
- size: `531`
- prototype: `int(ComDebugFormatter *__hidden this, struct tagVARIANT *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18003512c`
- `0x1800567a4`
- `0x180056858`
- `0x1800568e0`
- `0x180056aa0`
- `0x180056cbc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180056c94`
- `OLEAUT32!__imp_VariantClear` at `0x180056c94`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180056b0f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180056b0f`
- `OLEAUT32!__imp_VarBstrFromR4` at `0x180056bda`
- `OLEAUT32!__imp_VarBstrFromR4` at `0x180056bda`
- `OLEAUT32!__imp_VarBstrFromR8` at `0x180056bbe`
- `OLEAUT32!__imp_VarBstrFromR8` at `0x180056bbe`

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
0x180056aa0  mov     [rsp+arg_0], rbx
0x180056aa5  mov     [rsp+arg_8], rsi
0x180056aaa  push    rdi
0x180056aab  sub     rsp, 40h
0x180056aaf  mov     rdi, r9
0x180056ab2  mov     esi, r8d
0x180056ab5  mov     r10, rdx
0x180056ab8  test    r9, r9
0x180056abb  jnz     short loc_180056AC7
0x180056abd  mov     eax, 80004003h
0x180056ac2  jmp     loc_180056CA3
0x180056ac7  mov     qword ptr [r9], 0
0x180056ace  test    rdx, rdx
0x180056ad1  jnz     short loc_180056ADD
0x180056ad3  mov     eax, 80070057h
0x180056ad8  jmp     loc_180056CA3
0x180056add  cmp     esi, 10h
0x180056ae0  jz      short loc_180056AF1
0x180056ae2  cmp     esi, 0Ah
0x180056ae5  jz      short loc_180056AF1
0x180056ae7  mov     eax, 80004001h
0x180056aec  jmp     loc_180056CA3
0x180056af1  xor     eax, eax
0x180056af3  xorps   xmm0, xmm0
0x180056af6  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180056afb  movzx   eax, word ptr [rdx]
0x180056afe  bt      ax, 0Eh
0x180056b03  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180056b08  jnb     short loc_180056B2B
0x180056b0a  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180056b0f  call    cs:__imp_VariantCopyInd
0x180056b15  mov     ebx, eax
0x180056b17  test    eax, eax
0x180056b19  js      loc_180056CA3
0x180056b1f  movzx   eax, word ptr [rsp+48h+pvarDest]
0x180056b24  lea     r10, [rsp+48h+pvarDest]
0x180056b29  jmp     short loc_180056B2D
0x180056b2b  xor     ebx, ebx
0x180056b2d  movzx   ecx, ax
0x180056b30  cmp     ecx, 9
0x180056b33  ja      loc_180056BFA
0x180056b39  jz      loc_180056C4A
0x180056b3f  test    ecx, ecx
0x180056b41  jz      loc_180056BEE
0x180056b47  sub     ecx, 1
0x180056b4a  jz      loc_180056BE2
0x180056b50  sub     ecx, 1
0x180056b53  jz      loc_180056C2B
0x180056b59  sub     ecx, 1
0x180056b5c  jz      loc_180056C2B
0x180056b62  sub     ecx, 1
0x180056b65  jz      short loc_180056BC6
0x180056b67  sub     ecx, 1
0x180056b6a  jz      short loc_180056BAA
0x180056b6c  sub     ecx, 2
0x180056b6f  jz      short loc_180056B9A
0x180056b71  cmp     ecx, 1
0x180056b74  jnz     loc_180056C22
0x180056b7a  cmp     qword ptr [r10+8], 0
0x180056b7f  lea     rcx, String
0x180056b86  mov     rdx, rdi
0x180056b89  cmovnz  rcx, [r10+8]
0x180056b8e  call    GetStringLiteral
0x180056b93  mov     ebx, eax
0x180056b95  jmp     loc_180056C8F
0x180056b9a  movsd   xmm0, qword ptr [r10+8]
0x180056ba0  mov     rdx, rdi
0x180056ba3  call    GetDateLiteral
0x180056ba8  jmp     short loc_180056B93
0x180056baa  movsd   xmm0, qword ptr [r10+8]; dblIn
0x180056bb0  mov     r9, rdi; pbstrOut
0x180056bb3  mov     edx, 409h; lcid
0x180056bb8  mov     r8d, 80000000h; dwFlags
0x180056bbe  call    cs:__imp_VarBstrFromR8
0x180056bc4  jmp     short loc_180056B93
0x180056bc6  movss   xmm0, dword ptr [r10+8]; fltIn
0x180056bcc  mov     r9, rdi; pbstrOut
0x180056bcf  mov     edx, 409h; lcid
0x180056bd4  mov     r8d, 80000000h; dwFlags
0x180056bda  call    cs:__imp_VarBstrFromR4
0x180056be0  jmp     short loc_180056B93
0x180056be2  lea     rcx, aNull; "Null"
0x180056be9  jmp     loc_180056C7C
0x180056bee  lea     rcx, aEmpty; "Empty"
0x180056bf5  jmp     loc_180056C7C
0x180056bfa  sub     ecx, 0Bh
0x180056bfd  jz      short loc_180056C63
0x180056bff  sub     ecx, 2
0x180056c02  jz      short loc_180056C4A
0x180056c04  sub     ecx, 3
0x180056c07  jz      short loc_180056C2B
0x180056c09  sub     ecx, 1
0x180056c0c  jz      short loc_180056C2B
0x180056c0e  sub     ecx, 1
0x180056c11  jz      short loc_180056C2B
0x180056c13  sub     ecx, 1
0x180056c16  jz      short loc_180056C2B
0x180056c18  sub     ecx, 3
0x180056c1b  jz      short loc_180056C2B
0x180056c1d  cmp     ecx, 1
0x180056c20  jz      short loc_180056C2B
0x180056c22  mov     qword ptr [rdi], 0
0x180056c29  jmp     short loc_180056C8F
0x180056c2b  mov     rdx, rdi
0x180056c2e  mov     rcx, r10
0x180056c31  cmp     esi, 10h
0x180056c34  jnz     short loc_180056C40
0x180056c36  call    GetHexLiteral
0x180056c3b  jmp     loc_180056B93
0x180056c40  call    GetDecimalLiteral
0x180056c45  jmp     loc_180056B93
0x180056c4a  cmp     qword ptr [r10+8], 0
0x180056c4f  lea     rcx, aNothing; "Nothing"
0x180056c56  lea     rax, String
0x180056c5d  cmovnz  rcx, rax
0x180056c61  jmp     short loc_180056C7C
0x180056c63  xor     eax, eax
0x180056c65  lea     rcx, aFalse_0; "False"
0x180056c6c  cmp     ax, [r10+8]
0x180056c71  lea     rdx, aTrue_0; "True"
0x180056c78  cmovnz  rcx, rdx; unsigned __int16 *
0x180056c7c  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180056c81  test    rax, rax
0x180056c84  mov     [rdi], rax
0x180056c87  mov     ecx, 8007000Eh
0x180056c8c  cmovz   ebx, ecx
0x180056c8f  lea     rcx, [rsp+48h+pvarDest]; pvarg
0x180056c94  call    cs:__imp_VariantClear
0x180056c9a  xor     eax, eax
0x180056c9c  test    ebx, ebx
0x180056c9e  cmovns  ebx, eax
0x180056ca1  mov     eax, ebx
0x180056ca3  mov     rbx, [rsp+48h+arg_0]
0x180056ca8  mov     rsi, [rsp+48h+arg_8]
0x180056cad  add     rsp, 40h
0x180056cb1  pop     rdi
0x180056cb2  retn
```
