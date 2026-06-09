# CRegExp::Replace(ushort *,tagVARIANT,ushort * *)

- ea: `0x18006fe80`
- end: `0x180070196`
- name: `?Replace@CRegExp@@UEAAJPEAGUtagVARIANT@@PEAPEAG@Z`
- size: `790`
- prototype: `__int64 __fastcall(CRegExp *this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callees

- `0x180011650`
- `0x18001a970`
- `0x18001ed10`
- `0x180038df0`
- `0x180040a9c`
- `0x180046878`
- `0x1800468c4`
- `0x18005f654`
- `0x18005f804`
- `0x180061c30`
- `0x18006fe80`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800700ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1800700ec`

## pseudocode

```c
__int64 __fastcall CRegExp::Replace(CRegExp *this, unsigned __int16 *a2, struct tagVARIANT *a3, unsigned __int16 **a4)
{
  __int64 v6; // rax
  __int64 (__fastcall *v8)(CRegExp *, unsigned __int16 *, void **, unsigned int *); // rax
  struct REGrpRange *v9; // rsi
  int v10; // edi
  unsigned __int8 **v11; // r12
  __int64 v12; // r14
  int v13; // r14d
  struct REGrpRange *v14; // rax
  bool v16; // zf
  struct IDispatch *pdispVal; // rbx
  LONGLONG llVal; // rax
  OLECHAR *bstrVal; // rbx
  UINT v20; // eax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rcx
  int v23; // eax
  unsigned __int8 *v24; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h]
  unsigned int v26; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+80h] [rbp-80h]
  struct REGrpRange *v30[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 **v31; // [rsp+98h] [rbp-68h]
  VARIANTARG pvargDest; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[264]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+1C8h] [rbp+C8h]
  int v35; // [rsp+1D0h] [rbp+D0h]
  __int64 v36; // [rsp+1D4h] [rbp+D4h]
  char *v37; // [rsp+228h] [rbp+128h]
  char v38; // [rsp+230h] [rbp+130h] BYREF
  int v39; // [rsp+258h] [rbp+158h]
  char *v40; // [rsp+260h] [rbp+160h]
  char v41; // [rsp+268h] [rbp+168h] BYREF
  int v42; // [rsp+290h] [rbp+190h]

  v31 = a4;
  *a4 = 0;
  v34 = 0;
  v36 = 0;
  v37 = &v38;
  v6 = *(_QWORD *)this;
  v39 = 10;
  v40 = &v41;
  v42 = 10;
  v8 = *(__int64 (__fastcall **)(CRegExp *, unsigned __int16 *, void **, unsigned int *))(v6 + 144);
  v35 = 0;
  v9 = 0;
  Block = 0;
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  v26 = 0;
  v10 = v8(this, a2, &Block, &v26);
  if ( v10 < 0 )
    goto LABEL_7;
  v11 = (unsigned __int8 **)((char *)this + 96);
  v12 = *((_QWORD *)this + 12);
  if ( v12 )
    v13 = *(_DWORD *)(v12 + 24);
  else
    v13 = 1;
  v14 = (struct REGrpRange *)operator new[](saturated_mul(v13, 8u));
  v9 = v14;
  if ( !v14 )
  {
    v10 = -2147024882;
    goto LABEL_7;
  }
  v16 = a3->vt == 9;
  v30[1] = v14;
  v30[0] = v14;
  if ( v16 )
  {
    pdispVal = a3->pdispVal;
  }
  else
  {
    if ( a3->vt != 16396 || (llVal = a3->llVal, *(_WORD *)llVal != 9) )
    {
      memset(&pvargDest, 0, sizeof(pvargDest));
      if ( a3->vt == 8 )
      {
        bstrVal = a3->bstrVal;
      }
      else
      {
        v10 = rtVariantChangeTypeEx(&pvargDest, a3, 0x400u, 0, 8u);
        if ( v10 < 0 )
          goto LABEL_7;
        bstrVal = pvargDest.bstrVal;
      }
      v20 = SysStringLen(bstrVal);
      v10 = RegExpExec::ReplaceUsingString(
              (RegExpExec *)v33,
              a2,
              (unsigned __int16 *)Block,
              v26,
              *v11,
              *((_DWORD *)this + 26),
              v30,
              v13,
              bstrVal,
              v20,
              (struct BuildString *)v28);
      if ( pvargDest.vt )
        VAR::Clear((VAR *)&pvargDest);
      goto LABEL_26;
    }
    pdispVal = *(struct IDispatch **)(llVal + 8);
  }
  ((void (__fastcall *)(struct IDispatch *))pdispVal->lpVtbl->AddRef)(pdispVal);
  v25 = *((_DWORD *)this + 26);
  v24 = *v11;
  *(_QWORD *)&pvargDest.vt = 8;
  *(_OWORD *)&pvargDest.decVal.Lo32 = (unsigned __int64)a2;
  v10 = RegExpExec::ReplaceUsingDispatch(
          (RegExpExec *)v33,
          (struct VAR *)&pvargDest,
          (struct VAR *)&pvargDest,
          (unsigned __int16 *)Block,
          v26,
          (unsigned __int8 **)this + 12,
          v24,
          v25,
          v30,
          v13,
          (struct BuildString *)v28,
          pdispVal);
  ((void (__fastcall *)(struct IDispatch *))pdispVal->lpVtbl->Release)(pdispVal);
LABEL_26:
  if ( v10 >= 0 )
  {
    if ( v10 )
      v21 = _SysAllocStringLen(a2, v26);
    else
      v21 = BuildString::BstrReset((BuildString *)v28);
    v22 = v21;
    *v31 = v21;
    v23 = 0;
    if ( !v22 )
      v23 = -2147024882;
    v10 = v23;
  }
LABEL_7:
  if ( Block && Block != a2 && (int)v26 > 0 )
    operator delete[](Block);
  if ( v9 )
    operator delete[](v9);
  BuildString::Reset((BuildString *)v28);
  RegExpExec::~RegExpExec((RegExpExec *)v33);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006fe80  push    rbp
0x18006fe82  push    rbx
0x18006fe83  push    rsi
0x18006fe84  push    rdi
0x18006fe85  push    r12
0x18006fe87  push    r13
0x18006fe89  push    r14
0x18006fe8b  push    r15
0x18006fe8d  lea     rbp, [rsp-1B8h]
0x18006fe95  sub     rsp, 2B8h
0x18006fe9c  mov     rax, cs:__security_cookie
0x18006fea3  xor     rax, rsp
0x18006fea6  mov     [rbp+1F0h+var_50], rax
0x18006fead  xor     r14d, r14d
0x18006feb0  mov     [rbp+1F0h+var_258], r9
0x18006feb4  mov     r13, rcx
0x18006feb7  mov     [r9], r14
0x18006feba  mov     r15, rdx
0x18006febd  mov     [rbp+1F0h+var_128], r14
0x18006fec4  lea     rcx, [rbp+1F0h+var_C0]
0x18006fecb  mov     [rbp+1F0h+var_11C], r14
0x18006fed2  mov     [rbp+1F0h+var_C8], rcx
0x18006fed9  lea     edx, [r14+0Ah]
0x18006fedd  mov     rax, [r13+0]
0x18006fee1  lea     rcx, [rbp+1F0h+var_88]
0x18006fee8  mov     rbx, r8
0x18006feeb  mov     [rbp+1F0h+var_98], edx
0x18006fef1  mov     [rbp+1F0h+var_90], rcx
0x18006fef8  lea     r9, [rsp+2F0h+var_290]
0x18006fefd  mov     [rbp+1F0h+var_60], edx
0x18006ff03  lea     r8, [rsp+2F0h+Block]
0x18006ff08  mov     rax, [rax+90h]
0x18006ff0f  mov     rdx, r15
0x18006ff12  mov     rcx, r13
0x18006ff15  mov     [rbp+1F0h+var_120], r14d
0x18006ff1c  mov     esi, r14d
0x18006ff1f  mov     [rsp+2F0h+Block], r14
0x18006ff24  mov     [rsp+2F0h+var_280], r14
0x18006ff29  mov     [rsp+2F0h+var_278], r14
0x18006ff2e  mov     [rbp+1F0h+var_270], r14d
0x18006ff32  mov     [rsp+2F0h+var_290], r14d
0x18006ff37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff3c  mov     edi, eax
0x18006ff3e  test    eax, eax
0x18006ff40  js      short loc_18006FF86
0x18006ff42  lea     r12, [r13+60h]
0x18006ff46  mov     r14, [r12]
0x18006ff4a  test    r14, r14
0x18006ff4d  jnz     short loc_18006FF55
0x18006ff4f  lea     r14d, [rsi+1]
0x18006ff53  jmp     short loc_18006FF59
0x18006ff55  mov     r14d, [r14+18h]
0x18006ff59  mov     edi, 8
0x18006ff5e  movsxd  rcx, r14d
0x18006ff61  mov     eax, edi
0x18006ff63  mul     rcx
0x18006ff66  lea     rcx, [rdi-9]
0x18006ff6a  cmovb   rax, rcx
0x18006ff6e  mov     rcx, rax; unsigned __int64
0x18006ff71  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006ff76  mov     rsi, rax
0x18006ff79  test    rax, rax
0x18006ff7c  jnz     short loc_18006FFE7
0x18006ff7e  mov     edi, 8007000Eh
0x18006ff83  xor     r14d, r14d
0x18006ff86  mov     rcx, [rsp+2F0h+Block]; Block
0x18006ff8b  test    rcx, rcx
0x18006ff8e  jz      short loc_18006FFA1
0x18006ff90  cmp     rcx, r15
0x18006ff93  jz      short loc_18006FFA1
0x18006ff95  cmp     [rsp+2F0h+var_290], r14d
0x18006ff9a  jle     short loc_18006FFA1
0x18006ff9c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18006ffa1  test    rsi, rsi
0x18006ffa4  jz      short loc_18006FFAE
0x18006ffa6  mov     rcx, rsi; Block
0x18006ffa9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18006ffae  lea     rcx, [rsp+2F0h+var_280]; this
0x18006ffb3  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006ffb8  lea     rcx, [rbp+1F0h+var_230]; this
0x18006ffbc  call    ??1RegExpExec@@QEAA@XZ; RegExpExec::~RegExpExec(void)
0x18006ffc1  mov     eax, edi
0x18006ffc3  mov     rcx, [rbp+1F0h+var_50]
0x18006ffca  xor     rcx, rsp; StackCookie
0x18006ffcd  call    __security_check_cookie
0x18006ffd2  add     rsp, 2B8h
0x18006ffd9  pop     r15
0x18006ffdb  pop     r14
0x18006ffdd  pop     r13
0x18006ffdf  pop     r12
0x18006ffe1  pop     rdi
0x18006ffe2  pop     rsi
0x18006ffe3  pop     rbx
0x18006ffe4  pop     rbp
0x18006ffe5  retn
0x18006ffe7  cmp     word ptr [rbx], 9
0x18006ffeb  mov     [rbp+1F0h+var_260], rax
0x18006ffef  mov     [rbp+1F0h+var_268], rax
0x18006fff3  jnz     short loc_18006FFFB
0x18006fff5  mov     rbx, [rbx+8]
0x18006fff9  jmp     short loc_18007001B
0x18006fffb  mov     eax, 400Ch
0x180070000  cmp     [rbx], ax
0x180070003  jnz     loc_1800700A9
0x180070009  mov     rax, [rbx+8]
0x18007000d  cmp     word ptr [rax], 9
0x180070011  jnz     loc_1800700A9
0x180070017  mov     rbx, [rax+8]
0x18007001b  mov     rax, [rbx]
0x18007001e  mov     rcx, rbx
0x180070021  mov     rax, [rax+8]
0x180070025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007002a  mov     r9, [rsp+2F0h+Block]; unsigned __int16 *
0x18007002f  lea     r8, [rbp+1F0h+pvargDest]; struct VAR *
0x180070033  xor     eax, eax
0x180070035  mov     [rsp+2F0h+var_298], rbx; struct IDispatch *
0x18007003a  mov     qword ptr [rbp+1F0h+pvargDest+10h], rax
0x18007003e  lea     rdx, [rbp+1F0h+pvargDest]; struct VAR *
0x180070042  lea     rax, [rsp+2F0h+var_280]
0x180070047  xorps   xmm0, xmm0
0x18007004a  mov     [rsp+2F0h+var_2A0], rax; struct BuildString *
0x18007004f  lea     rcx, [rbp+1F0h+var_230]; this
0x180070053  mov     [rsp+2F0h+var_2A8], r14d; int
0x180070058  lea     rax, [rbp+1F0h+var_268]
0x18007005c  mov     [rsp+2F0h+var_2B0], rax; struct REGrpRange **
0x180070061  mov     eax, [r13+68h]
0x180070065  mov     [rsp+2F0h+var_2B8], eax; int
0x180070069  mov     rax, [r12]
0x18007006d  mov     [rsp+2F0h+var_2C0], rax; unsigned __int8 *
0x180070072  mov     eax, [rsp+2F0h+var_290]
0x180070076  movups  xmmword ptr [rbp+1F0h+pvargDest], xmm0
0x18007007a  mov     [rsp+2F0h+var_2C8], r12; unsigned __int8 **
0x18007007f  mov     dword ptr [rsp+2F0h+var_2D0], eax; int
0x180070083  mov     word ptr [rbp+1F0h+pvargDest], di
0x180070087  mov     qword ptr [rbp+1F0h+pvargDest+8], r15
0x18007008b  call    ?ReplaceUsingDispatch@RegExpExec@@QEAAJPEAVVAR@@0PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAUIDispatch@@@Z; RegExpExec::ReplaceUsingDispatch(VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,IDispatch *)
0x180070090  mov     edi, eax
0x180070092  mov     rcx, rbx
0x180070095  mov     rax, [rbx]
0x180070098  mov     rax, [rax+10h]
0x18007009c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700a1  xor     r14d, r14d
0x1800700a4  jmp     loc_180070155
0x1800700a9  xor     eax, eax
0x1800700ab  xorps   xmm0, xmm0
0x1800700ae  movups  xmmword ptr [rbp+1F0h+pvargDest], xmm0
0x1800700b2  mov     qword ptr [rbp+1F0h+pvargDest+10h], rax
0x1800700b6  cmp     [rbx], di
0x1800700b9  jnz     short loc_1800700C1
0x1800700bb  mov     rbx, [rbx+8]
0x1800700bf  jmp     short loc_1800700E9
0x1800700c1  xor     r9d, r9d; unsigned __int16
0x1800700c4  mov     word ptr [rsp+2F0h+var_2D0], di; unsigned __int16
0x1800700c9  mov     r8d, 400h; unsigned int
0x1800700cf  lea     rcx, [rbp+1F0h+pvargDest]; pvargDest
0x1800700d3  mov     rdx, rbx; pvarSrc
0x1800700d6  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x1800700db  mov     edi, eax
0x1800700dd  test    eax, eax
0x1800700df  js      loc_18006FF83
0x1800700e5  mov     rbx, qword ptr [rbp+1F0h+pvargDest+8]
0x1800700e9  mov     rcx, rbx; pbstr
0x1800700ec  call    cs:__imp_SysStringLen
0x1800700f3  nop     dword ptr [rax+rax+00h]
0x1800700f8  mov     r9d, [rsp+2F0h+var_290]; int
0x1800700fd  lea     rcx, [rsp+2F0h+var_280]
0x180070102  mov     r8, [rsp+2F0h+Block]; unsigned __int16 *
0x180070107  mov     rdx, r15; unsigned __int16 *
0x18007010a  mov     [rsp+2F0h+var_2A0], rcx; struct BuildString *
0x18007010f  lea     rcx, [rbp+1F0h+var_230]; this
0x180070113  mov     [rsp+2F0h+var_2A8], eax; int
0x180070117  lea     rax, [rbp+1F0h+var_268]
0x18007011b  mov     [rsp+2F0h+var_2B0], rbx; unsigned __int16 *
0x180070120  mov     [rsp+2F0h+var_2B8], r14d; int
0x180070125  mov     [rsp+2F0h+var_2C0], rax; struct REGrpRange **
0x18007012a  mov     eax, [r13+68h]
0x18007012e  mov     dword ptr [rsp+2F0h+var_2C8], eax; int
0x180070132  mov     rax, [r12]
0x180070136  mov     [rsp+2F0h+var_2D0], rax; unsigned __int8 *
0x18007013b  call    ?ReplaceUsingString@RegExpExec@@QEAAJPEAG0JPEAEJPEAPEAUREGrpRange@@H0JPEAVBuildString@@@Z; RegExpExec::ReplaceUsingString(ushort *,ushort *,long,uchar *,long,REGrpRange * *,int,ushort *,long,BuildString *)
0x180070140  xor     r14d, r14d
0x180070143  mov     edi, eax
0x180070145  cmp     word ptr [rbp+1F0h+pvargDest], r14w
0x18007014a  jz      short loc_180070155
0x18007014c  lea     rcx, [rbp+1F0h+pvargDest]; this
0x180070150  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180070155  test    edi, edi
0x180070157  js      loc_18006FF86
0x18007015d  jnz     short loc_18007016B
0x18007015f  lea     rcx, [rsp+2F0h+var_280]; this
0x180070164  call    ?BstrReset@BuildString@@QEAAPEAGXZ; BuildString::BstrReset(void)
0x180070169  jmp     short loc_180070177
0x18007016b  mov     edx, [rsp+2F0h+var_290]; unsigned int
0x18007016f  mov     rcx, r15; unsigned __int16 *
0x180070172  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180070177  mov     rcx, rax
0x18007017a  mov     edi, 8007000Eh
0x18007017f  mov     rax, [rbp+1F0h+var_258]
0x180070183  test    rcx, rcx
0x180070186  mov     [rax], rcx
0x180070189  mov     eax, r14d
0x18007018c  cmovz   eax, edi
0x18007018f  mov     edi, eax
0x180070191  jmp     loc_18006FF86
```
