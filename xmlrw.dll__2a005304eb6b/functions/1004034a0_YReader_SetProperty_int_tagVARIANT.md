# YReader::SetProperty(int,tagVARIANT)

- ea: `0x1004034a0`
- end: `0x1004037ec`
- name: `?SetProperty@YReader@@UEAAJHUtagVARIANT@@@Z`
- size: `844`
- prototype: `int(YReader *__hidden this, int, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1004034a0`
- `0x100418330`
- `0x1004236e0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1004034f8`
- `OLEAUT32!__imp_SysStringLen` at `0x10040353f`
- `OLEAUT32!__imp_SysStringLen` at `0x1004034f8`
- `OLEAUT32!__imp_SysStringLen` at `0x10040353f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1004036ac`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x100403737`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1004036ac`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x100403737`

## pseudocode

```c
__int64 __fastcall YReader::SetProperty(YReader *this, int a2, struct tagVARIANT *a3)
{
  __int64 result; // rax
  UINT v6; // eax
  struct IMalloc *v7; // rdx
  UINT v8; // ecx
  LONGLONG llVal; // rax
  UINT v10; // ecx
  LONGLONG v11; // rax
  __int64 v12; // rcx
  unsigned int IsSupported; // ebx
  SHORT iVal; // cx
  VARIANTARG *p_pvargDest; // rax
  __int128 v16; // xmm0
  LONG lVal; // esi
  void (__fastcall *v18)(YReader *); // [rsp+30h] [rbp-38h] BYREF
  UINT v19; // [rsp+38h] [rbp-30h]
  VARIANTARG pvargDest; // [rsp+40h] [rbp-28h] BYREF

  switch ( a2 )
  {
    case 0:
      if ( a3->vt != 8 )
        goto LABEL_3;
      v6 = SysStringLen(a3->bstrVal);
      v7 = (struct IMalloc *)*((_QWORD *)this - 3);
      v8 = v6;
      llVal = a3->llVal;
      v19 = v8;
      v18 = (void (__fastcall *)(YReader *))llVal;
      CloneStringPtr::Assign((YReader *)((char *)this + 1680), v7, (struct StringPtr *)&v18);
      result = 0;
      break;
    case 1:
      if ( a3->vt != 8 )
        goto LABEL_3;
      v10 = SysStringLen(a3->bstrVal);
      v11 = a3->llVal;
      v19 = v10;
      v12 = *((_QWORD *)this - 3);
      v18 = (void (__fastcall *)(YReader *))v11;
      IsSupported = CharacterSourceFactory::IsSupported(v12, &v18, 0, 0xFFFFFFFFLL);
      if ( IsSupported )
        goto LABEL_35;
      CloneStringPtr::Assign((YReader *)((char *)this + 1696), *((struct IMalloc **)this - 3), (struct StringPtr *)&v18);
      result = 0;
      break;
    case 2:
      if ( a3->vt != 11 || !*((_DWORD *)this + 437) )
        goto LABEL_3;
      *((_BYTE *)this + 1756) = a3->iVal != 0;
      result = 0;
      break;
    case 3:
      if ( a3->vt != 11 || !*((_DWORD *)this + 437) )
        goto LABEL_3;
      *((_BYTE *)this + 1757) = a3->iVal != 0;
      result = 0;
      break;
    case 4:
      if ( a3->vt != 11 || !*((_DWORD *)this + 437) )
        goto LABEL_3;
      iVal = a3->iVal;
      *((_BYTE *)this + 1759) = iVal != 0;
      if ( iVal )
      {
        pvargDest.lVal = 0;
        *(_QWORD *)&pvargDest.vt = YReader::ParseAttributesS;
      }
      else
      {
        v19 = 0;
        v18 = YReader::ParseAttributesN;
      }
      *((_BYTE *)this + 285) = iVal != 0;
      p_pvargDest = (VARIANTARG *)&v18;
      if ( iVal )
        p_pvargDest = &pvargDest;
      v16 = *(_OWORD *)&p_pvargDest->vt;
      result = 0;
      *((_OWORD *)this + 95) = v16;
      break;
    case 5:
      pvargDest.vt = 0;
      IsSupported = VariantChangeTypeEx(&pvargDest, a3, 0x409u, 0, 3u);
      if ( IsSupported )
        goto LABEL_35;
      if ( pvargDest.lVal < 0 )
        goto LABEL_34;
      *((_DWORD *)this + 450) = pvargDest.lVal;
      result = 0;
      break;
    case 6:
      if ( a3->vt != 11 || !*((_DWORD *)this + 437) )
        goto LABEL_3;
      *((_BYTE *)this + 1760) = a3->iVal != 0;
      result = 0;
      break;
    case 7:
      pvargDest.vt = 0;
      IsSupported = VariantChangeTypeEx(&pvargDest, a3, 0x409u, 0, 3u);
      if ( IsSupported )
        goto LABEL_35;
      lVal = pvargDest.lVal;
      result = CharacterSourceFactory::IsSupported(
                 *((_QWORD *)this - 3),
                 &CodeStringPtr::empty,
                 pvargDest.cyVal.Lo,
                 0xFFFFFFFFLL);
      IsSupported = result;
      if ( (_DWORD)result )
        goto LABEL_35;
      *((_DWORD *)this + 451) = lVal;
      break;
    case 8:
      if ( a3->vt == 11 && *((_DWORD *)this + 437) )
      {
        *((_BYTE *)this + 1764) = a3->iVal != 0;
        result = 0;
      }
      else
      {
LABEL_3:
        result = 2147500037LL;
      }
      break;
    default:
LABEL_34:
      IsSupported = -2147024809;
LABEL_35:
      result = IsSupported;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1004034a0  mov     [rsp+arg_0], rbx
0x1004034a5  mov     [rsp+arg_8], rsi
0x1004034aa  push    rdi
0x1004034ab  sub     rsp, 60h
0x1004034af  xor     ebx, ebx
0x1004034b1  mov     rsi, r8
0x1004034b4  mov     rdi, rcx
0x1004034b7  cmp     edx, 8; switch 9 cases
0x1004034ba  ja      def_1004034D4; jumptable 00000001004034D4 default case
0x1004034c0  movsxd  rax, edx
0x1004034c3  lea     rcx, __ImageBase
0x1004034ca  mov     edx, ds:(jpt_1004034D4 - 100400000h)[rcx+rax*4]
0x1004034d1  add     rdx, rcx
0x1004034d4  jmp     rdx; switch jump
0x1004034d6  cmp     word ptr [r8], 8; jumptable 00000001004034D4 case 0
0x1004034db  jz      short loc_1004034F4
0x1004034dd  mov     ebx, 80004005h
0x1004034e2  mov     eax, ebx
0x1004034e4  mov     rbx, [rsp+68h+arg_0]
0x1004034e9  mov     rsi, [rsp+68h+arg_8]
0x1004034ee  add     rsp, 60h
0x1004034f2  pop     rdi
0x1004034f3  retn
0x1004034f4  mov     rcx, [r8+8]; pbstr
0x1004034f8  call    cs:__imp_SysStringLen
0x1004034fe  mov     rdx, [rdi-18h]; struct IMalloc *
0x100403502  lea     r8, [rsp+68h+var_38]; struct StringPtr *
0x100403507  mov     ecx, eax
0x100403509  mov     rax, [rsi+8]
0x10040350d  mov     [rsp+68h+var_30], ecx
0x100403511  lea     rcx, [rdi+690h]; this
0x100403518  mov     [rsp+68h+var_38], rax
0x10040351d  call    ?Assign@CloneStringPtr@@QEAAXPEAUIMalloc@@PEAUStringPtr@@@Z; CloneStringPtr::Assign(IMalloc *,StringPtr *)
0x100403522  mov     eax, ebx
0x100403524  mov     rbx, [rsp+68h+arg_0]
0x100403529  mov     rsi, [rsp+68h+arg_8]
0x10040352e  add     rsp, 60h
0x100403532  pop     rdi
0x100403533  retn
0x100403534  cmp     word ptr [r8], 8; jumptable 00000001004034D4 case 1
0x100403539  jnz     short loc_1004034DD
0x10040353b  mov     rcx, [r8+8]; pbstr
0x10040353f  call    cs:__imp_SysStringLen
0x100403545  mov     r9d, 0FFFFFFFFh
0x10040354b  lea     rdx, [rsp+68h+var_38]
0x100403550  mov     ecx, eax
0x100403552  xor     r8d, r8d
0x100403555  mov     rax, [rsi+8]
0x100403559  mov     [rsp+68h+var_30], ecx
0x10040355d  mov     rcx, [rdi-18h]
0x100403561  mov     [rsp+68h+var_38], rax
0x100403566  call    ?IsSupported@CharacterSourceFactory@@SAJPEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z; CharacterSourceFactory::IsSupported(IMalloc *,StringPtr *,uint,TriState)
0x10040356b  mov     ebx, eax
0x10040356d  test    eax, eax
0x10040356f  jnz     loc_1004037B6
0x100403575  mov     rdx, [rdi-18h]; struct IMalloc *
0x100403579  lea     rcx, [rdi+6A0h]; this
0x100403580  lea     r8, [rsp+68h+var_38]; struct StringPtr *
0x100403585  call    ?Assign@CloneStringPtr@@QEAAXPEAUIMalloc@@PEAUStringPtr@@@Z; CloneStringPtr::Assign(IMalloc *,StringPtr *)
0x10040358a  mov     eax, ebx
0x10040358c  mov     rbx, [rsp+68h+arg_0]
0x100403591  mov     rsi, [rsp+68h+arg_8]
0x100403596  add     rsp, 60h
0x10040359a  pop     rdi
0x10040359b  retn
0x10040359c  cmp     word ptr [r8], 0Bh; jumptable 00000001004034D4 case 2
0x1004035a1  jnz     loc_1004034DD
0x1004035a7  cmp     [rdi+6D4h], ebx
0x1004035ad  jz      loc_1004034DD
0x1004035b3  cmp     [r8+8], bx
0x1004035b8  setnz   al
0x1004035bb  mov     [rdi+6DCh], al
0x1004035c1  mov     eax, ebx
0x1004035c3  mov     rbx, [rsp+68h+arg_0]
0x1004035c8  mov     rsi, [rsp+68h+arg_8]
0x1004035cd  add     rsp, 60h
0x1004035d1  pop     rdi
0x1004035d2  retn
0x1004035d3  cmp     word ptr [r8], 0Bh; jumptable 00000001004034D4 case 3
0x1004035d8  jnz     loc_1004034DD
0x1004035de  cmp     [rdi+6D4h], ebx
0x1004035e4  jz      loc_1004034DD
0x1004035ea  cmp     [r8+8], bx
0x1004035ef  setnz   al
0x1004035f2  mov     [rdi+6DDh], al
0x1004035f8  mov     eax, ebx
0x1004035fa  mov     rbx, [rsp+68h+arg_0]
0x1004035ff  mov     rsi, [rsp+68h+arg_8]
0x100403604  add     rsp, 60h
0x100403608  pop     rdi
0x100403609  retn
0x10040360a  cmp     word ptr [r8], 0Bh; jumptable 00000001004034D4 case 4
0x10040360f  jnz     loc_1004034DD
0x100403615  cmp     [rdi+6D4h], ebx
0x10040361b  jz      loc_1004034DD
0x100403621  movzx   ecx, word ptr [r8+8]
0x100403626  test    cx, cx
0x100403629  setnz   dl
0x10040362c  mov     [rdi+6DFh], dl
0x100403632  test    cx, cx
0x100403635  jz      short loc_100403649
0x100403637  lea     rax, ?ParseAttributesS@YReader@@AEAAXXZ; YReader::ParseAttributesS(void)
0x10040363e  mov     dword ptr [rsp+68h+pvargDest+8], ebx
0x100403642  mov     qword ptr [rsp+68h+pvargDest], rax
0x100403647  jmp     short loc_100403659
0x100403649  lea     rax, ?ParseAttributesN@YReader@@AEAAXXZ; YReader::ParseAttributesN(void)
0x100403650  mov     [rsp+68h+var_30], ebx
0x100403654  mov     [rsp+68h+var_38], rax
0x100403659  test    cx, cx
0x10040365c  mov     [rdi+11Dh], dl
0x100403662  lea     rax, [rsp+68h+var_38]
0x100403667  lea     r8, [rsp+68h+pvargDest]
0x10040366c  cmovnz  rax, r8
0x100403670  movups  xmm0, xmmword ptr [rax]
0x100403673  mov     eax, ebx
0x100403675  movups  xmmword ptr [rdi+5F0h], xmm0
0x10040367c  mov     rbx, [rsp+68h+arg_0]
0x100403681  mov     rsi, [rsp+68h+arg_8]
0x100403686  add     rsp, 60h
0x10040368a  pop     rdi
0x10040368b  retn
0x10040368c  mov     eax, 3; jumptable 00000001004034D4 case 5
0x100403691  mov     word ptr [rsp+68h+pvargDest], bx
0x100403696  xor     r9d, r9d; wFlags
0x100403699  mov     [rsp+68h+vt], ax; vt
0x10040369e  mov     r8d, 409h; lcid
0x1004036a4  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x1004036a9  mov     rdx, rsi; pvarSrc
0x1004036ac  call    cs:__imp_VariantChangeTypeEx
0x1004036b2  mov     ebx, eax
0x1004036b4  test    eax, eax
0x1004036b6  jnz     loc_1004037B6
0x1004036bc  mov     eax, dword ptr [rsp+68h+pvargDest+8]
0x1004036c0  test    eax, eax
0x1004036c2  js      def_1004034D4; jumptable 00000001004034D4 default case
0x1004036c8  mov     [rdi+708h], eax
0x1004036ce  mov     eax, ebx
0x1004036d0  mov     rbx, [rsp+68h+arg_0]
0x1004036d5  mov     rsi, [rsp+68h+arg_8]
0x1004036da  add     rsp, 60h
0x1004036de  pop     rdi
0x1004036df  retn
0x1004036e0  cmp     word ptr [r8], 0Bh; jumptable 00000001004034D4 case 6
0x1004036e5  jnz     loc_1004034DD
0x1004036eb  cmp     [rdi+6D4h], ebx
0x1004036f1  jz      loc_1004034DD
0x1004036f7  cmp     [r8+8], bx
0x1004036fc  setnz   al
0x1004036ff  mov     [rdi+6E0h], al
0x100403705  mov     eax, ebx
0x100403707  mov     rbx, [rsp+68h+arg_0]
0x10040370c  mov     rsi, [rsp+68h+arg_8]
0x100403711  add     rsp, 60h
0x100403715  pop     rdi
0x100403716  retn
0x100403717  mov     eax, 3; jumptable 00000001004034D4 case 7
0x10040371c  mov     word ptr [rsp+68h+pvargDest], bx
0x100403721  xor     r9d, r9d; wFlags
0x100403724  mov     [rsp+68h+vt], ax; vt
0x100403729  mov     r8d, 409h; lcid
0x10040372f  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x100403734  mov     rdx, rsi; pvarSrc
0x100403737  call    cs:__imp_VariantChangeTypeEx
0x10040373d  mov     ebx, eax
0x10040373f  test    eax, eax
0x100403741  jnz     short loc_1004037B6
0x100403743  mov     esi, dword ptr [rsp+68h+pvargDest+8]
0x100403747  lea     r9d, [rax-1]
0x10040374b  mov     rcx, [rdi-18h]
0x10040374f  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100403756  mov     r8d, esi
0x100403759  call    ?IsSupported@CharacterSourceFactory@@SAJPEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z; CharacterSourceFactory::IsSupported(IMalloc *,StringPtr *,uint,TriState)
0x10040375e  mov     ebx, eax
0x100403760  test    eax, eax
0x100403762  jnz     short loc_1004037B6
0x100403764  mov     [rdi+70Ch], esi
0x10040376a  mov     rbx, [rsp+68h+arg_0]
0x10040376f  mov     rsi, [rsp+68h+arg_8]
0x100403774  add     rsp, 60h
0x100403778  pop     rdi
0x100403779  retn
0x10040377a  cmp     word ptr [r8], 0Bh; jumptable 00000001004034D4 case 8
0x10040377f  jnz     loc_1004034DD
0x100403785  cmp     [rdi+6D4h], ebx
0x10040378b  jz      loc_1004034DD
0x100403791  cmp     [r8+8], bx
0x100403796  setnz   al
0x100403799  mov     [rdi+6E4h], al
0x10040379f  mov     eax, ebx
0x1004037a1  mov     rbx, [rsp+68h+arg_0]
0x1004037a6  mov     rsi, [rsp+68h+arg_8]
0x1004037ab  add     rsp, 60h
0x1004037af  pop     rdi
0x1004037b0  retn
0x1004037b1  mov     ebx, 80070057h; jumptable 00000001004034D4 default case
0x1004037b6  mov     rsi, [rsp+68h+arg_8]
0x1004037bb  mov     eax, ebx
0x1004037bd  mov     rbx, [rsp+68h+arg_0]
0x1004037c2  add     rsp, 60h
0x1004037c6  pop     rdi
0x1004037c7  retn
```
