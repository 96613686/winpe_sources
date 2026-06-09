# SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)

- ea: `0x180005ad0`
- end: `0x180005d59`
- name: `?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, SAFEARRAY *, struct _SDIAG_PARAMSET *)`
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180018a9c`
- `0x18001955c`
- `0x18001b3b8`
- `0x18001cb90`
- `0x180020314`
- `0x180023260`
- `0x180026710`

## callees

- `0x180005ad0`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005c65`
- `msvcrt!_wcsicmp` at `0x180005c65`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005be3`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bf6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005be3`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bf6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d3c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005c0b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005c30`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005c0b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005c30`

## string_xrefs

- `0x180005d14`: `SdpUpdateParamSet`

## pseudocode

```c
__int64 __fastcall SdpUpdateParamSet(SAFEARRAY *psa, SAFEARRAY *a2, struct _SDIAG_PARAMSET *a3)
{
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // rax
  unsigned int v10; // edx
  OLECHAR *v11; // rcx
  ULONG cElements; // eax
  HRESULT Element; // eax
  unsigned int v14; // r14d
  unsigned int v15; // r8d
  __int64 v16; // r9
  unsigned int v17; // edx
  int v18; // r9d
  BSTR pv[2]; // [rsp+20h] [rbp-10h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+58h] BYREF

  bstrString = 0;
  pv[0] = 0;
  rgIndices = 0;
  v6 = 0;
  if ( !a3 )
  {
    v7 = 128;
    goto LABEL_44;
  }
  v8 = 0;
  if ( !*((_DWORD *)a3 + 2) )
    return v8;
  v9 = 0;
  v10 = 0;
  do
  {
    v11 = *(OLECHAR **)(*(_QWORD *)a3 + 24 * v9 + 8);
    if ( v11 != *(OLECHAR **)(*(_QWORD *)a3 + 24LL * v10 + 16) )
    {
      if ( v11 )
      {
        SysFreeString(v11);
        *(_QWORD *)(*(_QWORD *)a3 + 24LL * (unsigned int)rgIndices + 8) = 0;
        v6 = rgIndices;
      }
      *(_QWORD *)(*(_QWORD *)a3 + 24LL * v6 + 8) = *(_QWORD *)(*(_QWORD *)a3 + 24LL * v6 + 16);
      v6 = rgIndices;
    }
    v10 = ++v6;
    rgIndices = v6;
    v9 = v6;
  }
  while ( v6 < *((_DWORD *)a3 + 2) );
  if ( psa )
  {
    if ( !a2 )
    {
      v7 = 163;
      goto LABEL_44;
    }
    if ( psa->cDims > 1u
      || a2->cDims > 1u
      || (cElements = psa->rgsabound[0].cElements, cElements != a2->rgsabound[0].cElements) )
    {
      v7 = 171;
      goto LABEL_44;
    }
    rgIndices = 0;
    if ( cElements )
    {
      while ( 1 )
      {
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        if ( pv[0] )
        {
          SysFreeString(pv[0]);
          pv[0] = 0;
        }
        Element = SafeArrayGetElement(psa, &rgIndices, &bstrString);
        v8 = Element;
        if ( Element < 0 )
          break;
        if ( !bstrString )
        {
          v7 = 181;
          goto LABEL_37;
        }
        Element = SafeArrayGetElement(a2, &rgIndices, pv);
        v8 = Element;
        if ( Element < 0 )
        {
          v7 = 184;
          goto LABEL_39;
        }
        if ( !pv[0] )
        {
          v7 = 185;
LABEL_37:
          v18 = -2147467261;
          goto LABEL_45;
        }
        v14 = 0;
        if ( *((_DWORD *)a3 + 2) )
        {
          while ( _wcsicmp(bstrString, *(const wchar_t **)(*(_QWORD *)a3 + 24LL * v14)) )
          {
            if ( ++v14 >= *((_DWORD *)a3 + 2) )
              goto LABEL_30;
          }
          *(BSTR *)(*(_QWORD *)a3 + 24LL * v14 + 8) = pv[0];
          pv[0] = 0;
        }
LABEL_30:
        if ( ++rgIndices >= psa->rgsabound[0].cElements )
          goto LABEL_31;
      }
      v7 = 180;
LABEL_39:
      v18 = Element;
      goto LABEL_46;
    }
  }
LABEL_31:
  v15 = *((_DWORD *)a3 + 2);
  rgIndices = 0;
  if ( v15 )
  {
    v16 = *(_QWORD *)a3;
    v17 = 0;
    while ( *(_QWORD *)(v16 + 24LL * v17 + 8) )
    {
      rgIndices = ++v17;
      if ( v17 >= v15 )
        goto LABEL_47;
    }
    v7 = 211;
LABEL_44:
    v18 = -2147024809;
LABEL_45:
    v8 = v18;
LABEL_46:
    SdpDebugTrace(1u, L"SdpUpdateParamSet", v7, v18);
  }
LABEL_47:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( pv[0] )
    SysFreeString(pv[0]);
  return v8;
}

```

## disassembly

```asm
0x180005ad0  mov     [rsp-38h+arg_0], rbx
0x180005ad5  push    rbp
0x180005ad6  push    rsi
0x180005ad7  push    rdi
0x180005ad8  push    r12
0x180005ada  push    r13
0x180005adc  push    r14
0x180005ade  push    r15
0x180005ae0  mov     rbp, rsp
0x180005ae3  sub     rsp, 30h
0x180005ae7  xor     r13d, r13d
0x180005aea  mov     rsi, r8
0x180005aed  mov     [rbp+bstrString], r13
0x180005af1  mov     r12, rdx
0x180005af4  mov     [rbp+pv], r13
0x180005af8  mov     r15, rcx
0x180005afb  mov     [rbp+rgIndices], r13d
0x180005aff  mov     r9d, r13d
0x180005b02  test    r8, r8
0x180005b05  jnz     short loc_180005B15
0x180005b07  mov     r8d, 80h
0x180005b0d  lea     ecx, [rsi+1]
0x180005b10  jmp     loc_180005D0B
0x180005b15  mov     eax, [r8+8]
0x180005b19  mov     edi, r13d
0x180005b1c  test    eax, eax
0x180005b1e  jz      loc_180005D42
0x180005b24  mov     ebx, 1
0x180005b29  mov     eax, r13d
0x180005b2c  mov     edx, r13d
0x180005b2f  mov     r8, [rsi]
0x180005b32  lea     rcx, [rax+rax*2]
0x180005b36  mov     eax, edx
0x180005b38  mov     rcx, [r8+rcx*8+8]; bstrString
0x180005b3d  lea     rdx, [rax+rax*2]
0x180005b41  cmp     rcx, [r8+rdx*8+10h]
0x180005b46  jz      short loc_180005B7E
0x180005b48  test    rcx, rcx
0x180005b4b  jz      short loc_180005B66
0x180005b4d  call    cs:__imp_SysFreeString
0x180005b53  mov     eax, [rbp+rgIndices]
0x180005b56  lea     rcx, [rax+rax*2]
0x180005b5a  mov     rax, [rsi]
0x180005b5d  mov     [rax+rcx*8+8], r13
0x180005b62  mov     r9d, [rbp+rgIndices]
0x180005b66  mov     rcx, [rsi]
0x180005b69  mov     eax, r9d
0x180005b6c  lea     rdx, [rax+rax*2]
0x180005b70  mov     rax, [rcx+rdx*8+10h]
0x180005b75  mov     [rcx+rdx*8+8], rax
0x180005b7a  mov     r9d, [rbp+rgIndices]
0x180005b7e  add     r9d, ebx
0x180005b81  mov     edx, r9d
0x180005b84  mov     [rbp+rgIndices], r9d
0x180005b88  mov     eax, r9d
0x180005b8b  cmp     r9d, [rsi+8]
0x180005b8f  jb      short loc_180005B2F
0x180005b91  test    r15, r15
0x180005b94  jz      loc_180005CA2
0x180005b9a  test    r12, r12
0x180005b9d  jnz     short loc_180005BAA
0x180005b9f  mov     r8d, 0A3h
0x180005ba5  jmp     loc_180005D09
0x180005baa  cmp     [r15], bx
0x180005bae  ja      loc_180005CFB
0x180005bb4  cmp     [r12], bx
0x180005bb9  ja      loc_180005CFB
0x180005bbf  mov     eax, [r15+18h]
0x180005bc3  cmp     eax, [r12+18h]
0x180005bc8  jnz     loc_180005CFB
0x180005bce  mov     [rbp+rgIndices], r13d
0x180005bd2  test    eax, eax
0x180005bd4  jz      loc_180005CA2
0x180005bda  mov     rcx, [rbp+bstrString]; bstrString
0x180005bde  test    rcx, rcx
0x180005be1  jz      short loc_180005BED
0x180005be3  call    cs:__imp_SysFreeString
0x180005be9  mov     [rbp+bstrString], r13
0x180005bed  mov     rcx, [rbp+pv]; bstrString
0x180005bf1  test    rcx, rcx
0x180005bf4  jz      short loc_180005C00
0x180005bf6  call    cs:__imp_SysFreeString
0x180005bfc  mov     [rbp+pv], r13
0x180005c00  lea     r8, [rbp+bstrString]; pv
0x180005c04  mov     rcx, r15; psa
0x180005c07  lea     rdx, [rbp+rgIndices]; rgIndices
0x180005c0b  call    cs:__imp_SafeArrayGetElement
0x180005c11  mov     edi, eax
0x180005c13  test    eax, eax
0x180005c15  js      loc_180005CF3
0x180005c1b  cmp     [rbp+bstrString], r13
0x180005c1f  jz      loc_180005CEB
0x180005c25  lea     r8, [rbp+pv]; pv
0x180005c29  mov     rcx, r12; psa
0x180005c2c  lea     rdx, [rbp+rgIndices]; rgIndices
0x180005c30  call    cs:__imp_SafeArrayGetElement
0x180005c36  mov     edi, eax
0x180005c38  test    eax, eax
0x180005c3a  js      loc_180005CDE
0x180005c40  cmp     [rbp+pv], r13
0x180005c44  jz      loc_180005CCE
0x180005c4a  mov     r14d, r13d
0x180005c4d  cmp     [rsi+8], r13d
0x180005c51  jbe     short loc_180005C90
0x180005c53  mov     rdx, [rsi]
0x180005c56  mov     rcx, [rbp+bstrString]; String1
0x180005c5a  mov     eax, r14d
0x180005c5d  lea     r13, [rax+rax*2]
0x180005c61  mov     rdx, [rdx+r13*8]; String2
0x180005c65  call    cs:__imp__wcsicmp
0x180005c6b  test    eax, eax
0x180005c6d  jz      short loc_180005C7D
0x180005c6f  add     r14d, ebx
0x180005c72  cmp     r14d, [rsi+8]
0x180005c76  jb      short loc_180005C53
0x180005c78  xor     r13d, r13d
0x180005c7b  jmp     short loc_180005C90
0x180005c7d  mov     rax, [rbp+pv]
0x180005c81  mov     rcx, [rsi]
0x180005c84  mov     [rcx+r13*8+8], rax
0x180005c89  xor     r13d, r13d
0x180005c8c  mov     [rbp+pv], r13
0x180005c90  mov     eax, [rbp+rgIndices]
0x180005c93  add     eax, ebx
0x180005c95  mov     [rbp+rgIndices], eax
0x180005c98  cmp     eax, [r15+18h]
0x180005c9c  jb      loc_180005BDA
0x180005ca2  mov     r8d, [rsi+8]
0x180005ca6  mov     [rbp+rgIndices], r13d
0x180005caa  test    r8d, r8d
0x180005cad  jz      short loc_180005D20
0x180005caf  mov     r9, [rsi]
0x180005cb2  mov     edx, r13d
0x180005cb5  mov     eax, edx
0x180005cb7  lea     rcx, [rax+rax*2]
0x180005cbb  cmp     [r9+rcx*8+8], r13
0x180005cc0  jz      short loc_180005D03
0x180005cc2  inc     edx
0x180005cc4  mov     [rbp+rgIndices], edx
0x180005cc7  cmp     edx, r8d
0x180005cca  jb      short loc_180005CB5
0x180005ccc  jmp     short loc_180005D20
0x180005cce  mov     r8d, 0B9h
0x180005cd4  mov     r9d, 80004003h
0x180005cda  mov     ecx, ebx
0x180005cdc  jmp     short loc_180005D11
0x180005cde  mov     r8d, 0B8h
0x180005ce4  mov     r9d, eax
0x180005ce7  mov     ecx, ebx
0x180005ce9  jmp     short loc_180005D14
0x180005ceb  mov     r8d, 0B5h
0x180005cf1  jmp     short loc_180005CD4
0x180005cf3  mov     r8d, 0B4h
0x180005cf9  jmp     short loc_180005CE4
0x180005cfb  mov     r8d, 0ABh
0x180005d01  jmp     short loc_180005D09
0x180005d03  mov     r8d, 0D3h; int
0x180005d09  mov     ecx, ebx; Level
0x180005d0b  mov     r9d, 80070057h; int
0x180005d11  mov     edi, r9d
0x180005d14  lea     rdx, aSdpupdateparam; "SdpUpdateParamSet"
0x180005d1b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005d20  mov     rcx, [rbp+bstrString]; bstrString
0x180005d24  test    rcx, rcx
0x180005d27  jz      short loc_180005D33
0x180005d29  call    cs:__imp_SysFreeString
0x180005d2f  mov     [rbp+bstrString], r13
0x180005d33  mov     rcx, [rbp+pv]; bstrString
0x180005d37  test    rcx, rcx
0x180005d3a  jz      short loc_180005D42
0x180005d3c  call    cs:__imp_SysFreeString
0x180005d42  mov     rbx, [rsp+30h+arg_0]
0x180005d47  mov     eax, edi
0x180005d49  add     rsp, 30h
0x180005d4d  pop     r15
0x180005d4f  pop     r14
0x180005d51  pop     r13
0x180005d53  pop     r12
0x180005d55  pop     rdi
0x180005d56  pop     rsi
0x180005d57  pop     rbp
0x180005d58  retn
```
