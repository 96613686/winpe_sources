# VAR::PvarConvert(int)

- ea: `0x18001c950`
- end: `0x18001cc69`
- name: `?PvarConvert@VAR@@QEAAPEAV1@H@Z`
- size: `793`
- prototype: `struct VAR *__fastcall(VAR *__hidden this, VARTYPE vt)`
- caller_count: `34`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001484`
- `0x180001920`
- `0x180001a14`
- `0x180001bd0`
- `0x180001ce0`
- `0x180001e58`
- `0x180001f70`
- `0x180002450`
- `0x180002600`
- `0x180002780`
- `0x180019e78`
- `0x18001aa50`
- `0x18001bd44`
- `0x18001c050`
- `0x18001c1f0`
- `0x18001c600`
- `0x18001d6c0`
- `0x18001d9f0`
- `0x18001e210`
- `0x18001e7a0`
- `0x18002fde0`
- `0x180037150`
- `0x18003b1d8`
- `0x18003ef64`
- `0x18003f09c`
- `0x180041130`
- `0x1800674c0`
- `0x180067670`
- `0x1800677d0`
- `0x18006e930`
- `0x18006ee10`
- `0x18006f150`
- `0x180071da0`
- `0x180072200`

## callees

- `0x180019edc`
- `0x18001b104`
- `0x18001c950`
- `0x18001cf8c`
- `0x180040cc4`
- `0x1800692dc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001cacb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbe2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cacb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbe2`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca91`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca9d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb8d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb99`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca91`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca9d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb8d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cb99`
- `OLEAUT32!__imp_VariantClear` at `0x18001cad4`
- `OLEAUT32!__imp_VariantClear` at `0x18001caf7`
- `OLEAUT32!__imp_VariantClear` at `0x18001cbcc`
- `OLEAUT32!__imp_VariantClear` at `0x18001cad4`
- `OLEAUT32!__imp_VariantClear` at `0x18001caf7`
- `OLEAUT32!__imp_VariantClear` at `0x18001cbcc`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ca26`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001cc13`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ca26`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001cc13`
- `KERNEL32!TlsGetValue` at `0x18001c97d`
- `KERNEL32!TlsGetValue` at `0x18001c97d`

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
0x18001c950  push    rsi
0x18001c952  push    rdi
0x18001c953  sub     rsp, 48h
0x18001c957  movzx   eax, word ptr [rcx]
0x18001c95a  mov     esi, edx
0x18001c95c  mov     rdi, rcx
0x18001c95f  cmp     eax, edx
0x18001c961  jnz     short loc_18001C96D
0x18001c963  mov     rax, rcx
0x18001c966  add     rsp, 48h
0x18001c96a  pop     rdi
0x18001c96b  pop     rsi
0x18001c96c  retn
0x18001c96d  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001c973  mov     [rsp+58h+arg_0], rbx
0x18001c978  mov     [rsp+58h+var_20], r14
0x18001c97d  call    cs:__imp_TlsGetValue
0x18001c983  test    rax, rax
0x18001c986  jz      loc_18001CA5A
0x18001c98c  mov     rbx, [rax+20h]
0x18001c990  test    rbx, rbx
0x18001c993  jz      loc_18001CA5A
0x18001c999  mov     rax, [rbx+10h]
0x18001c99d  cmp     rax, [rbx+8]
0x18001c9a1  jz      loc_18001CB30
0x18001c9a7  inc     dword ptr [rbx+18h]
0x18001c9aa  lea     rcx, [rax-18h]
0x18001c9ae  xor     eax, eax
0x18001c9b0  mov     [rbx+10h], rcx
0x18001c9b4  mov     [rcx], ax
0x18001c9b7  cmp     dword ptr [rbx+18h], 1
0x18001c9bb  jnz     short loc_18001C9C4
0x18001c9bd  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x18001c9c4  mov     r14, [rbx+10h]
0x18001c9c8  test    r14, r14
0x18001c9cb  jz      loc_18001CA5A
0x18001c9d1  mov     [rsp+58h+arg_10], r12
0x18001c9d6  mov     r12d, 8
0x18001c9dc  mov     [rsp+58h+var_18], r13
0x18001c9e1  mov     [rsp+58h+arg_8], rbp
0x18001c9e6  cmp     r12w, si
0x18001c9ea  jz      short loc_18001CA67
0x18001c9ec  mov     ebp, 400h
0x18001c9f1  cmp     r12w, [rdi]
0x18001c9f5  jz      short loc_18001CA67
0x18001c9f7  mov     r13d, 0Bh
0x18001c9fd  mov     [rsp+58h+var_28], r15
0x18001ca02  cmp     r13w, si
0x18001ca06  jz      short loc_18001CA70
0x18001ca08  cmp     r12w, si
0x18001ca0c  jz      loc_18001CAEA
0x18001ca12  mov     r9d, 2; wFlags
0x18001ca18  mov     [rsp+58h+vt], si; vt
0x18001ca1d  mov     r8d, ebp; lcid
0x18001ca20  mov     rdx, rdi; pvarSrc
0x18001ca23  mov     rcx, r14; pvargDest
0x18001ca26  call    cs:__imp_VariantChangeTypeEx
0x18001ca2c  test    eax, eax
0x18001ca2e  js      loc_18001CBED
0x18001ca34  mov     r15, [rsp+58h+var_28]
0x18001ca39  mov     rax, r14
0x18001ca3c  mov     r14, [rsp+58h+var_20]
0x18001ca41  mov     rbp, [rsp+58h+arg_8]
0x18001ca46  mov     r12, [rsp+58h+arg_10]
0x18001ca4b  mov     r13, [rsp+58h+var_18]
0x18001ca50  mov     rbx, [rsp+58h+arg_0]
0x18001ca55  jmp     loc_18001C966
0x18001ca5a  xor     edx, edx; struct VAR *
0x18001ca5c  mov     ecx, 800A0007h; int
0x18001ca61  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001ca67  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18001ca6c  mov     ebp, eax
0x18001ca6e  jmp     short loc_18001C9F7
0x18001ca70  cmp     r12w, [rdi]
0x18001ca74  jnz     short loc_18001CA12
0x18001ca76  mov     edx, ebp; unsigned int
0x18001ca78  mov     ecx, 7FFEh; int
0x18001ca7d  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ca82  mov     r15, rax
0x18001ca85  test    rax, rax
0x18001ca88  jz      loc_18001CB72
0x18001ca8e  mov     rcx, rax; pbstr
0x18001ca91  call    cs:__imp_SysStringLen
0x18001ca97  mov     rcx, [rdi+8]; pbstr
0x18001ca9b  mov     ebx, eax
0x18001ca9d  call    cs:__imp_SysStringLen
0x18001caa3  mov     r8, [rdi+8]; unsigned __int16 *
0x18001caa7  mov     edx, 1; unsigned int
0x18001caac  mov     r9d, eax; int
0x18001caaf  mov     [rsp+58h+var_30], ebx; int
0x18001cab3  mov     ecx, ebp; unsigned int
0x18001cab5  mov     qword ptr [rsp+58h+vt], r15; unsigned __int16 *
0x18001caba  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001cabf  mov     rcx, r15; bstrString
0x18001cac2  cmp     eax, 2
0x18001cac5  jnz     loc_18001CB6C
0x18001cacb  call    cs:__imp_SysFreeString
0x18001cad1  mov     rcx, r14; pvarg
0x18001cad4  call    cs:__imp_VariantClear
0x18001cada  mov     [r14], r13w
0x18001cade  mov     word ptr [r14+8], 0FFFFh
0x18001cae5  jmp     loc_18001CA34
0x18001caea  cmp     r13w, [rdi]
0x18001caee  jnz     loc_18001CA12
0x18001caf4  mov     rcx, r14; pvarg
0x18001caf7  call    cs:__imp_VariantClear
0x18001cafd  xor     ecx, ecx
0x18001caff  mov     [r14], r12w
0x18001cb03  xor     eax, eax
0x18001cb05  mov     edx, ebp; unsigned int
0x18001cb07  cmp     ax, [rdi+8]
0x18001cb0b  setz    cl
0x18001cb0e  add     ecx, 7FFEh; int
0x18001cb14  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001cb19  mov     [r14+8], rax
0x18001cb1d  test    rax, rax
0x18001cb20  jnz     loc_18001CA34
0x18001cb26  mov     eax, 800A0007h
0x18001cb2b  jmp     loc_18001CC5E
0x18001cb30  mov     rdx, [rbx]
0x18001cb33  test    rdx, rdx
0x18001cb36  jz      short loc_18001CB59
0x18001cb38  mov     rax, [rdx+4B0h]
0x18001cb3f  mov     [rbx], rax
0x18001cb42  mov     rcx, [rbx+8]
0x18001cb46  lea     rax, [rdx+4B0h]
0x18001cb4d  mov     [rax], rcx
0x18001cb50  mov     [rbx+8], rdx
0x18001cb54  jmp     loc_18001C9A7
0x18001cb59  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x18001cb5e  mov     rdx, rax
0x18001cb61  test    rax, rax
0x18001cb64  jz      loc_18001CA5A
0x18001cb6a  jmp     short loc_18001CB42
0x18001cb6c  call    cs:__imp_SysFreeString
0x18001cb72  mov     edx, ebp; unsigned int
0x18001cb74  mov     ecx, 7FFFh; int
0x18001cb79  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001cb7e  mov     r15, rax
0x18001cb81  test    rax, rax
0x18001cb84  jz      loc_18001CA12
0x18001cb8a  mov     rcx, rax; pbstr
0x18001cb8d  call    cs:__imp_SysStringLen
0x18001cb93  mov     rcx, [rdi+8]; pbstr
0x18001cb97  mov     ebx, eax
0x18001cb99  call    cs:__imp_SysStringLen
0x18001cb9f  mov     r8, [rdi+8]; unsigned __int16 *
0x18001cba3  mov     edx, 1; unsigned int
0x18001cba8  mov     r9d, eax; int
0x18001cbab  mov     [rsp+58h+var_30], ebx; int
0x18001cbaf  mov     ecx, ebp; unsigned int
0x18001cbb1  mov     qword ptr [rsp+58h+vt], r15; unsigned __int16 *
0x18001cbb6  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001cbbb  mov     rcx, r15; bstrString
0x18001cbbe  cmp     eax, 2
0x18001cbc1  jnz     short loc_18001CBE2
0x18001cbc3  call    cs:__imp_SysFreeString
0x18001cbc9  mov     rcx, r14; pvarg
0x18001cbcc  call    cs:__imp_VariantClear
0x18001cbd2  xor     eax, eax
0x18001cbd4  mov     [r14], r13w
0x18001cbd8  mov     [r14+8], ax
0x18001cbdd  jmp     loc_18001CA34
0x18001cbe2  call    cs:__imp_SysFreeString
0x18001cbe8  jmp     loc_18001CA12
0x18001cbed  mov     ebx, 7
0x18001cbf2  cmp     bx, si
0x18001cbf5  jnz     short loc_18001CC4B
0x18001cbf7  cmp     r12w, [rdi]
0x18001cbfb  jnz     short loc_18001CC4B
0x18001cbfd  mov     r9d, 2; wFlags
0x18001cc03  mov     [rsp+58h+vt], 5; vt
0x18001cc0a  mov     r8d, ebp; lcid
0x18001cc0d  mov     rdx, rdi; pvarSrc
0x18001cc10  mov     rcx, r14; pvargDest
0x18001cc13  call    cs:__imp_VariantChangeTypeEx
0x18001cc19  test    eax, eax
0x18001cc1b  js      short loc_18001CC4B
0x18001cc1d  movsd   xmm1, qword ptr [r14+8]
0x18001cc23  comisd  xmm1, cs:?MaxDateR8@@3TIEEEdouble@@B; IEEEdouble const MaxDateR8
0x18001cc2b  ja      short loc_18001CC44
0x18001cc2d  movsd   xmm0, cs:?MinDateR8@@3TIEEEdouble@@B; IEEEdouble const MinDateR8
0x18001cc35  comisd  xmm0, xmm1
0x18001cc39  ja      short loc_18001CC44
0x18001cc3b  mov     [r14], bx
0x18001cc3f  jmp     loc_18001CA34
0x18001cc44  mov     eax, 800A000Dh
0x18001cc49  jmp     short loc_18001CC5E
0x18001cc4b  cmp     eax, 80020005h
0x18001cc50  jnz     short loc_18001CC5E
0x18001cc52  cmp     word ptr [rdi], 1
0x18001cc56  mov     ecx, 800A005Eh
0x18001cc5b  cmovz   eax, ecx
0x18001cc5e  mov     rdx, rdi; struct VAR *
0x18001cc61  mov     ecx, eax; int
0x18001cc63  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
```
