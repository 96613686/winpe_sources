# CRegExp::Replace(ushort *,tagVARIANT,ushort * *)

- ea: `0x18006dc90`
- end: `0x18006df9f`
- name: `?Replace@CRegExp@@UEAAJPEAGUtagVARIANT@@PEAPEAG@Z`
- size: `783`
- prototype: `int(CRegExp *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callees

- `0x18001b960`
- `0x180022b20`
- `0x1800322d0`
- `0x180035154`
- `0x18003f1fc`
- `0x180045484`
- `0x1800454d0`
- `0x18005da6c`
- `0x18005dc1c`
- `0x18005ff9c`
- `0x18006dc90`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18006defb`
- `OLEAUT32!__imp_SysStringLen` at `0x18006defb`

## pseudocode

```c
__int64 __fastcall CRegExp::Replace(CRegExp *this, unsigned __int16 *a2, struct tagVARIANT *a3, unsigned __int16 **a4)
{
  __int64 v6; // rax
  __int64 (__fastcall *v8)(CRegExp *, unsigned __int16 *, void **, unsigned int *); // rax
  struct REGrpRange *v9; // rsi
  HRESULT v10; // edi
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
0x18006dc90  push    rbp
0x18006dc92  push    rbx
0x18006dc93  push    rsi
0x18006dc94  push    rdi
0x18006dc95  push    r12
0x18006dc97  push    r13
0x18006dc99  push    r14
0x18006dc9b  push    r15
0x18006dc9d  lea     rbp, [rsp-1B8h]
0x18006dca5  sub     rsp, 2B8h
0x18006dcac  mov     rax, cs:__security_cookie
0x18006dcb3  xor     rax, rsp
0x18006dcb6  mov     [rbp+1F0h+var_50], rax
0x18006dcbd  xor     r14d, r14d
0x18006dcc0  mov     [rbp+1F0h+var_258], r9
0x18006dcc4  mov     r13, rcx
0x18006dcc7  mov     [r9], r14
0x18006dcca  mov     r15, rdx
0x18006dccd  mov     [rbp+1F0h+var_128], r14
0x18006dcd4  lea     rcx, [rbp+1F0h+var_C0]
0x18006dcdb  mov     [rbp+1F0h+var_11C], r14
0x18006dce2  mov     [rbp+1F0h+var_C8], rcx
0x18006dce9  lea     edx, [r14+0Ah]
0x18006dced  mov     rax, [r13+0]
0x18006dcf1  lea     rcx, [rbp+1F0h+var_88]
0x18006dcf8  mov     rbx, r8
0x18006dcfb  mov     [rbp+1F0h+var_98], edx
0x18006dd01  mov     [rbp+1F0h+var_90], rcx
0x18006dd08  lea     r9, [rsp+2F0h+var_290]
0x18006dd0d  mov     [rbp+1F0h+var_60], edx
0x18006dd13  lea     r8, [rsp+2F0h+Block]
0x18006dd18  mov     rax, [rax+90h]
0x18006dd1f  mov     rdx, r15
0x18006dd22  mov     rcx, r13
0x18006dd25  mov     [rbp+1F0h+var_120], r14d
0x18006dd2c  mov     esi, r14d
0x18006dd2f  mov     [rsp+2F0h+Block], r14
0x18006dd34  mov     [rsp+2F0h+var_280], r14
0x18006dd39  mov     [rsp+2F0h+var_278], r14
0x18006dd3e  mov     [rbp+1F0h+var_270], r14d
0x18006dd42  mov     [rsp+2F0h+var_290], r14d
0x18006dd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd4c  mov     edi, eax
0x18006dd4e  test    eax, eax
0x18006dd50  js      short loc_18006DD96
0x18006dd52  lea     r12, [r13+60h]
0x18006dd56  mov     r14, [r12]
0x18006dd5a  test    r14, r14
0x18006dd5d  jnz     short loc_18006DD65
0x18006dd5f  lea     r14d, [rsi+1]
0x18006dd63  jmp     short loc_18006DD69
0x18006dd65  mov     r14d, [r14+18h]
0x18006dd69  mov     edi, 8
0x18006dd6e  movsxd  rcx, r14d
0x18006dd71  mov     eax, edi
0x18006dd73  mul     rcx
0x18006dd76  lea     rcx, [rdi-9]
0x18006dd7a  cmovb   rax, rcx
0x18006dd7e  mov     rcx, rax; unsigned __int64
0x18006dd81  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006dd86  mov     rsi, rax
0x18006dd89  test    rax, rax
0x18006dd8c  jnz     short loc_18006DDF6
0x18006dd8e  mov     edi, 8007000Eh
0x18006dd93  xor     r14d, r14d
0x18006dd96  mov     rcx, [rsp+2F0h+Block]; Block
0x18006dd9b  test    rcx, rcx
0x18006dd9e  jz      short loc_18006DDB1
0x18006dda0  cmp     rcx, r15
0x18006dda3  jz      short loc_18006DDB1
0x18006dda5  cmp     [rsp+2F0h+var_290], r14d
0x18006ddaa  jle     short loc_18006DDB1
0x18006ddac  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18006ddb1  test    rsi, rsi
0x18006ddb4  jz      short loc_18006DDBE
0x18006ddb6  mov     rcx, rsi; Block
0x18006ddb9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18006ddbe  lea     rcx, [rsp+2F0h+var_280]; this
0x18006ddc3  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006ddc8  lea     rcx, [rbp+1F0h+var_230]; this
0x18006ddcc  call    ??1RegExpExec@@QEAA@XZ; RegExpExec::~RegExpExec(void)
0x18006ddd1  mov     eax, edi
0x18006ddd3  mov     rcx, [rbp+1F0h+var_50]
0x18006ddda  xor     rcx, rsp; StackCookie
0x18006dddd  call    __security_check_cookie
0x18006dde2  add     rsp, 2B8h
0x18006dde9  pop     r15
0x18006ddeb  pop     r14
0x18006dded  pop     r13
0x18006ddef  pop     r12
0x18006ddf1  pop     rdi
0x18006ddf2  pop     rsi
0x18006ddf3  pop     rbx
0x18006ddf4  pop     rbp
0x18006ddf5  retn
0x18006ddf6  cmp     word ptr [rbx], 9
0x18006ddfa  mov     [rbp+1F0h+var_260], rax
0x18006ddfe  mov     [rbp+1F0h+var_268], rax
0x18006de02  jnz     short loc_18006DE0A
0x18006de04  mov     rbx, [rbx+8]
0x18006de08  jmp     short loc_18006DE2A
0x18006de0a  mov     eax, 400Ch
0x18006de0f  cmp     [rbx], ax
0x18006de12  jnz     loc_18006DEB8
0x18006de18  mov     rax, [rbx+8]
0x18006de1c  cmp     word ptr [rax], 9
0x18006de20  jnz     loc_18006DEB8
0x18006de26  mov     rbx, [rax+8]
0x18006de2a  mov     rax, [rbx]
0x18006de2d  mov     rcx, rbx
0x18006de30  mov     rax, [rax+8]
0x18006de34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de39  mov     r9, [rsp+2F0h+Block]; unsigned __int16 *
0x18006de3e  lea     r8, [rbp+1F0h+pvargDest]; struct VAR *
0x18006de42  xor     eax, eax
0x18006de44  mov     [rsp+2F0h+var_298], rbx; struct IDispatch *
0x18006de49  mov     qword ptr [rbp+1F0h+pvargDest+10h], rax
0x18006de4d  lea     rdx, [rbp+1F0h+pvargDest]; struct VAR *
0x18006de51  lea     rax, [rsp+2F0h+var_280]
0x18006de56  xorps   xmm0, xmm0
0x18006de59  mov     [rsp+2F0h+var_2A0], rax; struct BuildString *
0x18006de5e  lea     rcx, [rbp+1F0h+var_230]; this
0x18006de62  mov     [rsp+2F0h+var_2A8], r14d; int
0x18006de67  lea     rax, [rbp+1F0h+var_268]
0x18006de6b  mov     [rsp+2F0h+var_2B0], rax; struct REGrpRange **
0x18006de70  mov     eax, [r13+68h]
0x18006de74  mov     [rsp+2F0h+var_2B8], eax; int
0x18006de78  mov     rax, [r12]
0x18006de7c  mov     [rsp+2F0h+var_2C0], rax; unsigned __int8 *
0x18006de81  mov     eax, [rsp+2F0h+var_290]
0x18006de85  movups  xmmword ptr [rbp+1F0h+pvargDest], xmm0
0x18006de89  mov     [rsp+2F0h+var_2C8], r12; unsigned __int8 **
0x18006de8e  mov     dword ptr [rsp+2F0h+var_2D0], eax; int
0x18006de92  mov     word ptr [rbp+1F0h+pvargDest], di
0x18006de96  mov     qword ptr [rbp+1F0h+pvargDest+8], r15
0x18006de9a  call    ?ReplaceUsingDispatch@RegExpExec@@QEAAJPEAVVAR@@0PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAUIDispatch@@@Z; RegExpExec::ReplaceUsingDispatch(VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,IDispatch *)
0x18006de9f  mov     edi, eax
0x18006dea1  mov     rcx, rbx
0x18006dea4  mov     rax, [rbx]
0x18006dea7  mov     rax, [rax+10h]
0x18006deab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006deb0  xor     r14d, r14d
0x18006deb3  jmp     loc_18006DF5E
0x18006deb8  xor     eax, eax
0x18006deba  xorps   xmm0, xmm0
0x18006debd  movups  xmmword ptr [rbp+1F0h+pvargDest], xmm0
0x18006dec1  mov     qword ptr [rbp+1F0h+pvargDest+10h], rax
0x18006dec5  cmp     [rbx], di
0x18006dec8  jnz     short loc_18006DED0
0x18006deca  mov     rbx, [rbx+8]
0x18006dece  jmp     short loc_18006DEF8
0x18006ded0  xor     r9d, r9d; unsigned __int16
0x18006ded3  mov     word ptr [rsp+2F0h+var_2D0], di; unsigned __int16
0x18006ded8  mov     r8d, 400h; unsigned int
0x18006dede  lea     rcx, [rbp+1F0h+pvargDest]; pvargDest
0x18006dee2  mov     rdx, rbx; pvarSrc
0x18006dee5  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x18006deea  mov     edi, eax
0x18006deec  test    eax, eax
0x18006deee  js      loc_18006DD93
0x18006def4  mov     rbx, qword ptr [rbp+1F0h+pvargDest+8]
0x18006def8  mov     rcx, rbx; pbstr
0x18006defb  call    cs:__imp_SysStringLen
0x18006df01  mov     r9d, [rsp+2F0h+var_290]; int
0x18006df06  lea     rcx, [rsp+2F0h+var_280]
0x18006df0b  mov     r8, [rsp+2F0h+Block]; unsigned __int16 *
0x18006df10  mov     rdx, r15; unsigned __int16 *
0x18006df13  mov     [rsp+2F0h+var_2A0], rcx; struct BuildString *
0x18006df18  lea     rcx, [rbp+1F0h+var_230]; this
0x18006df1c  mov     [rsp+2F0h+var_2A8], eax; int
0x18006df20  lea     rax, [rbp+1F0h+var_268]
0x18006df24  mov     [rsp+2F0h+var_2B0], rbx; unsigned __int16 *
0x18006df29  mov     [rsp+2F0h+var_2B8], r14d; int
0x18006df2e  mov     [rsp+2F0h+var_2C0], rax; struct REGrpRange **
0x18006df33  mov     eax, [r13+68h]
0x18006df37  mov     dword ptr [rsp+2F0h+var_2C8], eax; int
0x18006df3b  mov     rax, [r12]
0x18006df3f  mov     [rsp+2F0h+var_2D0], rax; unsigned __int8 *
0x18006df44  call    ?ReplaceUsingString@RegExpExec@@QEAAJPEAG0JPEAEJPEAPEAUREGrpRange@@H0JPEAVBuildString@@@Z; RegExpExec::ReplaceUsingString(ushort *,ushort *,long,uchar *,long,REGrpRange * *,int,ushort *,long,BuildString *)
0x18006df49  xor     r14d, r14d
0x18006df4c  mov     edi, eax
0x18006df4e  cmp     word ptr [rbp+1F0h+pvargDest], r14w
0x18006df53  jz      short loc_18006DF5E
0x18006df55  lea     rcx, [rbp+1F0h+pvargDest]; this
0x18006df59  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18006df5e  test    edi, edi
0x18006df60  js      loc_18006DD96
0x18006df66  jnz     short loc_18006DF74
0x18006df68  lea     rcx, [rsp+2F0h+var_280]; this
0x18006df6d  call    ?BstrReset@BuildString@@QEAAPEAGXZ; BuildString::BstrReset(void)
0x18006df72  jmp     short loc_18006DF80
0x18006df74  mov     edx, [rsp+2F0h+var_290]; unsigned int
0x18006df78  mov     rcx, r15; unsigned __int16 *
0x18006df7b  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006df80  mov     rcx, rax
0x18006df83  mov     edi, 8007000Eh
0x18006df88  mov     rax, [rbp+1F0h+var_258]
0x18006df8c  test    rcx, rcx
0x18006df8f  mov     [rax], rcx
0x18006df92  mov     eax, r14d
0x18006df95  cmovz   eax, edi
0x18006df98  mov     edi, eax
0x18006df9a  jmp     loc_18006DD96
```
