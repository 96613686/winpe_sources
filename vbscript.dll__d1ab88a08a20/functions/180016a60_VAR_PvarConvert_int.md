# VAR::PvarConvert(int)

- ea: `0x180016a60`
- end: `0x180016dd2`
- name: `?PvarConvert@VAR@@QEAAPEAV1@H@Z`
- size: `882`
- prototype: `struct VAR *__fastcall(VAR *__hidden this, VARTYPE vt)`
- caller_count: `34`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800021c0`
- `0x180002d48`
- `0x180014d2c`
- `0x180015e00`
- `0x180016120`
- `0x1800162c0`
- `0x1800166f0`
- `0x1800178e0`
- `0x180017c30`
- `0x1800184c0`
- `0x180018aa0`
- `0x180023250`
- `0x180023320`
- `0x180023414`
- `0x1800235d0`
- `0x1800236e0`
- `0x180023858`
- `0x180023970`
- `0x180023e50`
- `0x180024010`
- `0x1800241a0`
- `0x1800268b8`
- `0x18003caa0`
- `0x180040830`
- `0x18004096c`
- `0x180042ae4`
- `0x180069540`
- `0x1800696f0`
- `0x180069850`
- `0x180070b90`
- `0x1800711a0`
- `0x180071510`
- `0x180074300`
- `0x180074780`

## callees

- `0x180014b00`
- `0x180014c8c`
- `0x180016a60`
- `0x180017138`
- `0x18004237c`
- `0x18006b41c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016bf8`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cab`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016bf8`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cab`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d3f`
- `OLEAUT32!__imp_SysStringLen` at `0x180016bb2`
- `OLEAUT32!__imp_SysStringLen` at `0x180016bc4`
- `OLEAUT32!__imp_SysStringLen` at `0x180016cd2`
- `OLEAUT32!__imp_SysStringLen` at `0x180016ce4`
- `OLEAUT32!__imp_SysStringLen` at `0x180016bb2`
- `OLEAUT32!__imp_SysStringLen` at `0x180016bc4`
- `OLEAUT32!__imp_SysStringLen` at `0x180016cd2`
- `OLEAUT32!__imp_SysStringLen` at `0x180016ce4`
- `OLEAUT32!__imp_VariantClear` at `0x180016c07`
- `OLEAUT32!__imp_VariantClear` at `0x180016c30`
- `OLEAUT32!__imp_VariantClear` at `0x180016d23`
- `OLEAUT32!__imp_VariantClear` at `0x180016c07`
- `OLEAUT32!__imp_VariantClear` at `0x180016c30`
- `OLEAUT32!__imp_VariantClear` at `0x180016d23`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180016b41`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180016d76`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180016b41`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180016d76`
- `KERNEL32!TlsGetValue` at `0x180016a8e`
- `KERNEL32!TlsGetValue` at `0x180016a8e`

## pseudocode

```c
VARIANTARG *__fastcall VAR::PvarConvert(VARIANTARG *this, int vt)
{
  VARTYPE v2; // si
  _QWORD *Value; // rax
  GcBlockFactory *v6; // rcx
  const unsigned __int16 *v7; // r8
  int v8; // r9d
  __int64 v9; // rbx
  char *v10; // rax
  VARIANTARG *v11; // r14
  unsigned int ConversionLocale; // ebp
  HRESULT v13; // eax
  const unsigned __int16 *v14; // r8
  int v15; // r9d
  OLECHAR *ResourceString; // rax
  OLECHAR *v17; // r15
  UINT v18; // ebx
  UINT v19; // eax
  unsigned __int16 *v20; // rax
  struct GcBlock *v21; // rdx
  OLECHAR *v22; // rax
  OLECHAR *v23; // r15
  UINT v24; // ebx
  UINT v25; // eax
  double dblVal; // xmm1_8

  v2 = vt;
  if ( this->vt == vt )
    return this;
  Value = TlsGetValue(g_luTls);
  if ( !Value )
    goto LABEL_15;
  v9 = Value[4];
  if ( !v9 )
    goto LABEL_15;
  v10 = *(char **)(v9 + 16);
  if ( v10 == *(char **)(v9 + 8) )
  {
    v21 = *(struct GcBlock **)v9;
    if ( *(_QWORD *)v9 )
    {
      *(_QWORD *)v9 = *((_QWORD *)v21 + 150);
    }
    else
    {
      v21 = GcBlockFactory::PblkAlloc(v6);
      if ( !v21 )
        goto LABEL_15;
    }
    v10 = (char *)v21 + 1200;
    *((_QWORD *)v21 + 150) = *(_QWORD *)(v9 + 8);
    *(_QWORD *)(v9 + 8) = v21;
  }
  ++*(_DWORD *)(v9 + 24);
  *(_QWORD *)(v9 + 16) = v10 - 24;
  *((_WORD *)v10 - 12) = 0;
  if ( *(_DWORD *)(v9 + 24) == 1 )
    _InterlockedIncrement(&g_cLibRef);
  v11 = *(VARIANTARG **)(v9 + 16);
  if ( !v11 )
LABEL_15:
    RaiseErrorHr(-2146828281, 0, v7, v8);
  if ( v2 == 8 || (ConversionLocale = 1024, this->vt == 8) )
    ConversionLocale = COleScript::GetConversionLocale();
  if ( v2 == 11 )
  {
    if ( this->vt == 8 )
    {
      ResourceString = BstrGetResourceString(32766, ConversionLocale);
      v17 = ResourceString;
      if ( ResourceString )
      {
        v18 = SysStringLen(ResourceString);
        v19 = SysStringLen(this->bstrVal);
        if ( oCompareString(ConversionLocale, 1u, this->bstrVal, v19, v17, v18) == 2 )
        {
          SysFreeString(v17);
          VariantClear(v11);
          v11->vt = 11;
          v11->iVal = -1;
          return v11;
        }
        SysFreeString(v17);
      }
      v22 = BstrGetResourceString(0x7FFF, ConversionLocale);
      v23 = v22;
      if ( v22 )
      {
        v24 = SysStringLen(v22);
        v25 = SysStringLen(this->bstrVal);
        if ( oCompareString(ConversionLocale, 1u, this->bstrVal, v25, v23, v24) == 2 )
        {
          SysFreeString(v23);
          VariantClear(v11);
          v11->vt = 11;
          v11->iVal = 0;
          return v11;
        }
        SysFreeString(v23);
      }
    }
  }
  else if ( v2 == 8 && this->vt == 11 )
  {
    VariantClear(v11);
    v11->vt = 8;
    v20 = BstrGetResourceString((unsigned int)(this->iVal == 0) + 32766, ConversionLocale);
    v11->llVal = (LONGLONG)v20;
    if ( !v20 )
    {
      v13 = -2146828281;
      goto LABEL_44;
    }
    return v11;
  }
  v13 = VariantChangeTypeEx(v11, this, ConversionLocale, 2u, v2);
  if ( v13 < 0 )
  {
    if ( v2 == 7 && this->vt == 8 && (v13 = VariantChangeTypeEx(v11, this, ConversionLocale, 2u, 5u), v13 >= 0) )
    {
      dblVal = v11->dblVal;
      if ( dblVal <= 2958466.0 && dblVal >= -657434.9999999999 )
      {
        v11->vt = 7;
        return v11;
      }
      v13 = -2146828275;
    }
    else if ( v13 == -2147352571 && this->vt == 1 )
    {
      v13 = -2146828194;
    }
LABEL_44:
    RaiseErrorHr(v13, (struct VAR *)this, v14, v15);
  }
  return v11;
}

```

## disassembly

```asm
0x180016a60  push    rsi
0x180016a62  push    rdi
0x180016a63  sub     rsp, 48h
0x180016a67  movzx   eax, word ptr [rcx]
0x180016a6a  mov     esi, edx
0x180016a6c  mov     rdi, rcx
0x180016a6f  cmp     eax, edx
0x180016a71  jnz     short loc_180016A7E
0x180016a73  mov     rax, rcx
0x180016a76  add     rsp, 48h
0x180016a7a  pop     rdi
0x180016a7b  pop     rsi
0x180016a7c  retn
0x180016a7e  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180016a84  mov     [rsp+58h+arg_0], rbx
0x180016a89  mov     [rsp+58h+var_20], r14
0x180016a8e  call    cs:__imp_TlsGetValue
0x180016a95  nop     dword ptr [rax+rax+00h]
0x180016a9a  test    rax, rax
0x180016a9d  jz      loc_180016B7B
0x180016aa3  mov     rbx, [rax+20h]
0x180016aa7  test    rbx, rbx
0x180016aaa  jz      loc_180016B7B
0x180016ab0  mov     rax, [rbx+10h]
0x180016ab4  cmp     rax, [rbx+8]
0x180016ab8  jz      loc_180016C6F
0x180016abe  inc     dword ptr [rbx+18h]
0x180016ac1  lea     rcx, [rax-18h]
0x180016ac5  xor     eax, eax
0x180016ac7  mov     [rbx+10h], rcx
0x180016acb  mov     [rcx], ax
0x180016ace  cmp     dword ptr [rbx+18h], 1
0x180016ad2  jnz     short loc_180016ADB
0x180016ad4  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180016adb  mov     r14, [rbx+10h]
0x180016adf  test    r14, r14
0x180016ae2  jz      loc_180016B7B
0x180016ae8  mov     [rsp+58h+arg_10], r12
0x180016aed  mov     r12d, 8
0x180016af3  mov     [rsp+58h+var_18], r13
0x180016af8  mov     [rsp+58h+arg_8], rbp
0x180016afd  cmp     r12w, si
0x180016b01  jz      loc_180016B88
0x180016b07  mov     ebp, 400h
0x180016b0c  cmp     r12w, [rdi]
0x180016b10  jz      short loc_180016B88
0x180016b12  mov     r13d, 0Bh
0x180016b18  mov     [rsp+58h+var_28], r15
0x180016b1d  cmp     r13w, si
0x180016b21  jz      short loc_180016B91
0x180016b23  cmp     r12w, si
0x180016b27  jz      loc_180016C23
0x180016b2d  mov     r9d, 2; wFlags
0x180016b33  mov     [rsp+58h+vt], si; vt
0x180016b38  mov     r8d, ebp; lcid
0x180016b3b  mov     rdx, rdi; pvarSrc
0x180016b3e  mov     rcx, r14; pvargDest
0x180016b41  call    cs:__imp_VariantChangeTypeEx
0x180016b48  nop     dword ptr [rax+rax+00h]
0x180016b4d  test    eax, eax
0x180016b4f  js      loc_180016D50
0x180016b55  mov     r15, [rsp+58h+var_28]
0x180016b5a  mov     rax, r14
0x180016b5d  mov     r14, [rsp+58h+var_20]
0x180016b62  mov     rbp, [rsp+58h+arg_8]
0x180016b67  mov     r12, [rsp+58h+arg_10]
0x180016b6c  mov     r13, [rsp+58h+var_18]
0x180016b71  mov     rbx, [rsp+58h+arg_0]
0x180016b76  jmp     loc_180016A76
0x180016b7b  xor     edx, edx; struct VAR *
0x180016b7d  mov     ecx, 800A0007h; int
0x180016b82  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180016b88  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x180016b8d  mov     ebp, eax
0x180016b8f  jmp     short loc_180016B12
0x180016b91  cmp     r12w, [rdi]
0x180016b95  jnz     short loc_180016B2D
0x180016b97  mov     edx, ebp; unsigned int
0x180016b99  mov     ecx, 7FFEh; int
0x180016b9e  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180016ba3  mov     r15, rax
0x180016ba6  test    rax, rax
0x180016ba9  jz      loc_180016CB7
0x180016baf  mov     rcx, rax; pbstr
0x180016bb2  call    cs:__imp_SysStringLen
0x180016bb9  nop     dword ptr [rax+rax+00h]
0x180016bbe  mov     rcx, [rdi+8]; pbstr
0x180016bc2  mov     ebx, eax
0x180016bc4  call    cs:__imp_SysStringLen
0x180016bcb  nop     dword ptr [rax+rax+00h]
0x180016bd0  mov     r8, [rdi+8]; unsigned __int16 *
0x180016bd4  mov     edx, 1; unsigned int
0x180016bd9  mov     r9d, eax; int
0x180016bdc  mov     [rsp+58h+var_30], ebx; int
0x180016be0  mov     ecx, ebp; unsigned int
0x180016be2  mov     qword ptr [rsp+58h+vt], r15; unsigned __int16 *
0x180016be7  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x180016bec  mov     rcx, r15; bstrString
0x180016bef  cmp     eax, 2
0x180016bf2  jnz     loc_180016CAB
0x180016bf8  call    cs:__imp_SysFreeString
0x180016bff  nop     dword ptr [rax+rax+00h]
0x180016c04  mov     rcx, r14; pvarg
0x180016c07  call    cs:__imp_VariantClear
0x180016c0e  nop     dword ptr [rax+rax+00h]
0x180016c13  mov     [r14], r13w
0x180016c17  mov     word ptr [r14+8], 0FFFFh
0x180016c1e  jmp     loc_180016B55
0x180016c23  cmp     r13w, [rdi]
0x180016c27  jnz     loc_180016B2D
0x180016c2d  mov     rcx, r14; pvarg
0x180016c30  call    cs:__imp_VariantClear
0x180016c37  nop     dword ptr [rax+rax+00h]
0x180016c3c  xor     ecx, ecx
0x180016c3e  mov     [r14], r12w
0x180016c42  xor     eax, eax
0x180016c44  mov     edx, ebp; unsigned int
0x180016c46  cmp     ax, [rdi+8]
0x180016c4a  setz    cl
0x180016c4d  add     ecx, 7FFEh; int
0x180016c53  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180016c58  mov     [r14+8], rax
0x180016c5c  test    rax, rax
0x180016c5f  jnz     loc_180016B55
0x180016c65  mov     eax, 800A0007h
0x180016c6a  jmp     loc_180016DC7
0x180016c6f  mov     rdx, [rbx]
0x180016c72  test    rdx, rdx
0x180016c75  jz      short loc_180016C98
0x180016c77  mov     rax, [rdx+4B0h]
0x180016c7e  mov     [rbx], rax
0x180016c81  mov     rcx, [rbx+8]
0x180016c85  lea     rax, [rdx+4B0h]
0x180016c8c  mov     [rax], rcx
0x180016c8f  mov     [rbx+8], rdx
0x180016c93  jmp     loc_180016ABE
0x180016c98  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x180016c9d  mov     rdx, rax
0x180016ca0  test    rax, rax
0x180016ca3  jz      loc_180016B7B
0x180016ca9  jmp     short loc_180016C81
0x180016cab  call    cs:__imp_SysFreeString
0x180016cb2  nop     dword ptr [rax+rax+00h]
0x180016cb7  mov     edx, ebp; unsigned int
0x180016cb9  mov     ecx, 7FFFh; int
0x180016cbe  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180016cc3  mov     r15, rax
0x180016cc6  test    rax, rax
0x180016cc9  jz      loc_180016B2D
0x180016ccf  mov     rcx, rax; pbstr
0x180016cd2  call    cs:__imp_SysStringLen
0x180016cd9  nop     dword ptr [rax+rax+00h]
0x180016cde  mov     rcx, [rdi+8]; pbstr
0x180016ce2  mov     ebx, eax
0x180016ce4  call    cs:__imp_SysStringLen
0x180016ceb  nop     dword ptr [rax+rax+00h]
0x180016cf0  mov     r8, [rdi+8]; unsigned __int16 *
0x180016cf4  mov     edx, 1; unsigned int
0x180016cf9  mov     r9d, eax; int
0x180016cfc  mov     [rsp+58h+var_30], ebx; int
0x180016d00  mov     ecx, ebp; unsigned int
0x180016d02  mov     qword ptr [rsp+58h+vt], r15; unsigned __int16 *
0x180016d07  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x180016d0c  mov     rcx, r15; bstrString
0x180016d0f  cmp     eax, 2
0x180016d12  jnz     short loc_180016D3F
0x180016d14  call    cs:__imp_SysFreeString
0x180016d1b  nop     dword ptr [rax+rax+00h]
0x180016d20  mov     rcx, r14; pvarg
0x180016d23  call    cs:__imp_VariantClear
0x180016d2a  nop     dword ptr [rax+rax+00h]
0x180016d2f  xor     eax, eax
0x180016d31  mov     [r14], r13w
0x180016d35  mov     [r14+8], ax
0x180016d3a  jmp     loc_180016B55
0x180016d3f  call    cs:__imp_SysFreeString
0x180016d46  nop     dword ptr [rax+rax+00h]
0x180016d4b  jmp     loc_180016B2D
0x180016d50  mov     ebx, 7
0x180016d55  cmp     bx, si
0x180016d58  jnz     short loc_180016DB4
0x180016d5a  cmp     r12w, [rdi]
0x180016d5e  jnz     short loc_180016DB4
0x180016d60  mov     r9d, 2; wFlags
0x180016d66  mov     [rsp+58h+vt], 5; vt
0x180016d6d  mov     r8d, ebp; lcid
0x180016d70  mov     rdx, rdi; pvarSrc
0x180016d73  mov     rcx, r14; pvargDest
0x180016d76  call    cs:__imp_VariantChangeTypeEx
0x180016d7d  nop     dword ptr [rax+rax+00h]
0x180016d82  test    eax, eax
0x180016d84  js      short loc_180016DB4
0x180016d86  movsd   xmm1, qword ptr [r14+8]
0x180016d8c  comisd  xmm1, cs:?MaxDateR8@@3TIEEEdouble@@B; IEEEdouble const MaxDateR8
0x180016d94  ja      short loc_180016DAD
0x180016d96  movsd   xmm0, cs:?MinDateR8@@3TIEEEdouble@@B; IEEEdouble const MinDateR8
0x180016d9e  comisd  xmm0, xmm1
0x180016da2  ja      short loc_180016DAD
0x180016da4  mov     [r14], bx
0x180016da8  jmp     loc_180016B55
0x180016dad  mov     eax, 800A000Dh
0x180016db2  jmp     short loc_180016DC7
0x180016db4  cmp     eax, 80020005h
0x180016db9  jnz     short loc_180016DC7
0x180016dbb  cmp     word ptr [rdi], 1
0x180016dbf  mov     ecx, 800A005Eh
0x180016dc4  cmovz   eax, ecx
0x180016dc7  mov     rdx, rdi; struct VAR *
0x180016dca  mov     ecx, eax; int
0x180016dcc  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
```
