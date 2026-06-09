# HyperVStorage::SetVariantValue(ushort const *,tagVARIANT const &)

- ea: `0x140275fc4`
- end: `0x14027632c`
- name: `?SetVariantValue@HyperVStorage@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `872`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1402442e0`

## callees

- `0x140056c70`
- `0x1400e07d0`
- `0x1401332f0`
- `0x140275fc4`
- `0x1402c4010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140276008`
- `OLEAUT32!__imp_VariantInit` at `0x140276008`
- `OLEAUT32!__imp_VariantClear` at `0x140276301`
- `OLEAUT32!__imp_VariantClear` at `0x140276301`
- `OLEAUT32!__imp_VariantChangeType` at `0x14027607e`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276192`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276260`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276295`
- `OLEAUT32!__imp_VariantChangeType` at `0x14027607e`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276192`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276260`
- `OLEAUT32!__imp_VariantChangeType` at `0x140276295`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14027610d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14027610d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1402760d8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1402760d8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1402760a3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1402760a3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1402762f0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1402762f0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1402761d3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1402761d3`

## pseudocode

```c
__int64 __fastcall HyperVStorage::SetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        const struct tagVARIANT *p_pvarg)
{
  SAFEARRAY *parray; // rsi
  unsigned int vt; // eax
  HRESULT v8; // eax
  HRESULT v9; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  HRESULT v14; // eax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v15; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdi
  HRESULT v17; // eax
  HRESULT v18; // eax
  void *ppvData; // [rsp+40h] [rbp-68h] BYREF
  LONG plLbound; // [rsp+48h] [rbp-60h] BYREF
  LONG plUbound; // [rsp+4Ch] [rbp-5Ch] BYREF
  BOOL v23; // [rsp+50h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  parray = 0;
  VariantInit(&pvarg);
  try
  {
    if ( !(*(unsigned int (**)(void))(*(_QWORD *)this + 288LL))() )
      HvsThrowHResultError(-2147467259);
    if ( !a2 )
      HvsThrowHResultError(-2147024809);
    ppvData = 0;
    v23 = 0;
    vt = p_pvarg->vt;
    if ( (vt & 0x2000) != 0 )
    {
      if ( (vt & 0xFFF) != 0x11 )
      {
        v8 = VariantChangeType(&pvarg, p_pvarg, 0, 0x2011u);
        if ( v8 < 0 )
          HvsThrowHResultError(v8);
        p_pvarg = &pvarg;
      }
      v9 = SafeArrayAccessData(p_pvarg->parray, &ppvData);
      if ( v9 < 0 )
        HvsThrowHResultError(v9);
      parray = p_pvarg->parray;
      plUbound = 0;
      plLbound = 0;
      LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
      if ( LBound < 0 )
        HvsThrowHResultError(LBound);
      if ( plLbound )
        HvsThrowHResultError(-2147024809);
      UBound = SafeArrayGetUBound(p_pvarg->parray, 1u, &plUbound);
      if ( UBound < 0 )
        HvsThrowHResultError(UBound);
      v12 = (unsigned int)(plUbound + 1);
      v13 = 7;
      goto LABEL_55;
    }
    if ( vt <= 0x10 )
    {
      if ( vt != 16 && vt != 2 && vt != 3 )
      {
        switch ( vt )
        {
          case 4u:
LABEL_29:
            v14 = VariantChangeType(&pvarg, p_pvarg, 0, 5u);
            if ( v14 < 0 )
              HvsThrowHResultError(v14);
            p_pvarg = &pvarg;
            goto LABEL_34;
          case 5u:
LABEL_34:
            p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
            if ( p_llVal->dblVal > 1.797693134862314e308 )
              HvsThrowHResultError(-2147352566);
            ppvData = p_llVal;
            v12 = 8;
            v13 = 5;
            goto LABEL_55;
          case 8u:
            ppvData = p_pvarg->bstrVal;
            v12 = SysStringByteLen((BSTR)ppvData);
            v13 = 6;
LABEL_55:
            HyperVStorage::SetValueInternal(this, a2, v13, v12, ppvData);
            goto LABEL_62;
        }
        if ( vt != 11 )
        {
          if ( vt == 14 )
            goto LABEL_29;
LABEL_44:
          HvsThrowHResultError(-2147352571);
        }
        v23 = p_pvarg->iVal != 0;
        v15 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v23;
        v12 = 4;
        v13 = 8;
LABEL_54:
        ppvData = v15;
        goto LABEL_55;
      }
      goto LABEL_45;
    }
    if ( vt != 17 && vt != 18 && vt != 19 )
    {
      switch ( vt )
      {
        case 0x14u:
LABEL_48:
          v13 = 3;
LABEL_53:
          v12 = 8;
          v15 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
          goto LABEL_54;
        case 0x15u:
LABEL_52:
          v13 = 4;
          goto LABEL_53;
        case 0x16u:
LABEL_45:
          v17 = VariantChangeType(&pvarg, p_pvarg, 0, 0x14u);
          if ( v17 < 0 )
            HvsThrowHResultError(v17);
          p_pvarg = &pvarg;
          goto LABEL_48;
      }
      if ( vt != 23 )
        goto LABEL_44;
    }
    v18 = VariantChangeType(&pvarg, p_pvarg, 0, 0x15u);
    if ( v18 < 0 )
      HvsThrowHResultError(v18);
    p_pvarg = &pvarg;
    goto LABEL_52;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
LABEL_62:
  if ( parray )
    SafeArrayUnaccessData(parray);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x140275fc4  push    rbx
0x140275fc6  push    rsi
0x140275fc7  push    rdi
0x140275fc8  push    r14
0x140275fca  push    r15
0x140275fcc  sub     rsp, 80h
0x140275fd3  mov     rax, cs:__security_cookie
0x140275fda  xor     rax, rsp
0x140275fdd  mov     [rsp+0A8h+var_38], rax
0x140275fe2  mov     rdi, r8
0x140275fe5  mov     r14, rdx
0x140275fe8  mov     r15, rcx
0x140275feb  xorps   xmm0, xmm0
0x140275fee  xor     eax, eax
0x140275ff0  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x140275ff5  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x140275ffa  xor     ebx, ebx
0x140275ffc  mov     esi, ebx
0x140275ffe  mov     [rsp+0A8h+var_70], rbx
0x140276003  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x140276008  call    cs:__imp_VariantInit
0x14027600f  nop     dword ptr [rax+rax+00h]
0x140276014  nop
0x140276015  mov     rax, [r15]
0x140276018  mov     rcx, r15
0x14027601b  mov     rax, [rax+120h]
0x140276022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140276027  test    eax, eax
0x140276029  jnz     short loc_140276035
0x14027602b  mov     ecx, 80004005h; int
0x140276030  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140276035  test    r14, r14
0x140276038  jnz     short loc_140276044
0x14027603a  mov     ecx, 80070057h; int
0x14027603f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140276044  mov     [rsp+0A8h+ppvData], rbx
0x140276049  mov     [rsp+0A8h+var_58], ebx
0x14027604d  movzx   eax, word ptr [rdi]
0x140276050  bt      ax, 0Dh
0x140276055  jnb     loc_140276137
0x14027605b  mov     ecx, 0FFFh
0x140276060  and     ax, cx
0x140276063  mov     edx, 11h
0x140276068  cmp     ax, dx
0x14027606b  jz      short loc_14027609A
0x14027606d  mov     r9d, 2011h; vt
0x140276073  xor     r8d, r8d; wFlags
0x140276076  mov     rdx, rdi; pvarSrc
0x140276079  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x14027607e  call    cs:__imp_VariantChangeType
0x140276085  nop     dword ptr [rax+rax+00h]
0x14027608a  test    eax, eax
0x14027608c  jns     short loc_140276095
0x14027608e  mov     ecx, eax; int
0x140276090  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140276095  lea     rdi, [rsp+0A8h+pvarg]
0x14027609a  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x14027609f  mov     rcx, [rdi+8]; psa
0x1402760a3  call    cs:__imp_SafeArrayAccessData
0x1402760aa  nop     dword ptr [rax+rax+00h]
0x1402760af  test    eax, eax
0x1402760b1  jns     short loc_1402760BA
0x1402760b3  mov     ecx, eax; int
0x1402760b5  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1402760ba  mov     rsi, [rdi+8]
0x1402760be  mov     [rsp+0A8h+var_70], rsi
0x1402760c3  mov     [rsp+0A8h+plUbound], ebx
0x1402760c7  mov     [rsp+0A8h+plLbound], ebx
0x1402760cb  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x1402760d0  mov     edx, 1; nDim
0x1402760d5  mov     rcx, rsi; psa
0x1402760d8  call    cs:__imp_SafeArrayGetLBound
0x1402760df  nop     dword ptr [rax+rax+00h]
0x1402760e4  test    eax, eax
0x1402760e6  jns     short loc_1402760EF
0x1402760e8  mov     ecx, eax; int
0x1402760ea  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1402760ef  cmp     [rsp+0A8h+plLbound], ebx
0x1402760f3  jz      short loc_1402760FF
0x1402760f5  mov     ecx, 80070057h; int
0x1402760fa  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1402760ff  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x140276104  mov     edx, 1; nDim
0x140276109  mov     rcx, [rdi+8]; psa
0x14027610d  call    cs:__imp_SafeArrayGetUBound
0x140276114  nop     dword ptr [rax+rax+00h]
0x140276119  test    eax, eax
0x14027611b  jns     short loc_140276124
0x14027611d  mov     ecx, eax; int
0x14027611f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140276124  mov     r9d, [rsp+0A8h+plUbound]
0x140276129  inc     r9d
0x14027612c  mov     r8d, 7
0x140276132  jmp     loc_1402762C6
0x140276137  mov     ecx, eax
0x140276139  cmp     eax, 10h
0x14027613c  ja      loc_140276222
0x140276142  jz      loc_14027624F
0x140276148  sub     ecx, 2
0x14027614b  jz      loc_14027624F
0x140276151  sub     ecx, 1
0x140276154  jz      loc_14027624F
0x14027615a  sub     ecx, 1
0x14027615d  jz      short loc_140276181
0x14027615f  sub     ecx, 1
0x140276162  jz      loc_1402761F2
0x140276168  mov     r8d, 3
0x14027616e  sub     ecx, r8d
0x140276171  jz      short loc_1402761CA
0x140276173  sub     ecx, r8d
0x140276176  jz      short loc_1402761A9
0x140276178  cmp     ecx, r8d
0x14027617b  jnz     loc_140276245
0x140276181  mov     r9d, 5; vt
0x140276187  xor     r8d, r8d; wFlags
0x14027618a  mov     rdx, rdi; pvarSrc
0x14027618d  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x140276192  call    cs:__imp_VariantChangeType
0x140276199  nop     dword ptr [rax+rax+00h]
0x14027619e  test    eax, eax
0x1402761a0  jns     short loc_1402761ED
0x1402761a2  mov     ecx, eax; int
0x1402761a4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1402761a9  mov     eax, ebx
0x1402761ab  cmp     [rdi+8], bx
0x1402761af  setnz   al
0x1402761b2  mov     [rsp+0A8h+var_58], eax
0x1402761b6  lea     rax, [rsp+0A8h+var_58]
0x1402761bb  mov     r9d, 4
0x1402761c1  lea     r8d, [r9+4]
0x1402761c5  jmp     loc_1402762C1
0x1402761ca  mov     rcx, [rdi+8]; bstr
0x1402761ce  mov     [rsp+0A8h+ppvData], rcx
0x1402761d3  call    cs:__imp_SysStringByteLen
0x1402761da  nop     dword ptr [rax+rax+00h]
0x1402761df  mov     r9d, eax
0x1402761e2  mov     r8d, 6
0x1402761e8  jmp     loc_1402762C6
0x1402761ed  lea     rdi, [rsp+0A8h+pvarg]
0x1402761f2  add     rdi, 8
0x1402761f6  movsd   xmm0, qword ptr [rdi]
0x1402761fa  comisd  xmm0, cs:__real@7feffffffffffff6
0x140276202  jbe     short loc_14027620E
0x140276204  mov     ecx, 8002000Ah; int
0x140276209  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14027620e  mov     [rsp+0A8h+ppvData], rdi
0x140276213  mov     r9d, 8
0x140276219  lea     r8d, [r9-3]
0x14027621d  jmp     loc_1402762C6
0x140276222  sub     ecx, 11h
0x140276225  jz      short loc_140276284
0x140276227  sub     ecx, 1
0x14027622a  jz      short loc_140276284
0x14027622c  sub     ecx, 1
0x14027622f  jz      short loc_140276284
0x140276231  sub     ecx, 1
0x140276234  jz      short loc_14027627C
0x140276236  sub     ecx, 1
0x140276239  jz      short loc_1402762B1
0x14027623b  sub     ecx, 1
0x14027623e  jz      short loc_14027624F
0x140276240  cmp     ecx, 1
0x140276243  jz      short loc_140276284
0x140276245  mov     ecx, 80020005h; int
0x14027624a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14027624f  mov     r9d, 14h; vt
0x140276255  xor     r8d, r8d; wFlags
0x140276258  mov     rdx, rdi; pvarSrc
0x14027625b  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x140276260  call    cs:__imp_VariantChangeType
0x140276267  nop     dword ptr [rax+rax+00h]
0x14027626c  test    eax, eax
0x14027626e  jns     short loc_140276277
0x140276270  mov     ecx, eax; int
0x140276272  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140276277  lea     rdi, [rsp+0A8h+pvarg]
0x14027627c  mov     r8d, 3
0x140276282  jmp     short loc_1402762B7
0x140276284  mov     r9d, 15h; vt
0x14027628a  xor     r8d, r8d; wFlags
0x14027628d  mov     rdx, rdi; pvarSrc
0x140276290  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x140276295  call    cs:__imp_VariantChangeType
0x14027629c  nop     dword ptr [rax+rax+00h]
0x1402762a1  test    eax, eax
0x1402762a3  jns     short loc_1402762AC
0x1402762a5  mov     ecx, eax; int
0x1402762a7  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1402762ac  lea     rdi, [rsp+0A8h+pvarg]
0x1402762b1  mov     r8d, 4
0x1402762b7  mov     r9d, 8
0x1402762bd  lea     rax, [rdi+8]
0x1402762c1  mov     [rsp+0A8h+ppvData], rax
0x1402762c6  mov     rax, [rsp+0A8h+ppvData]
0x1402762cb  mov     [rsp+0A8h+var_88], rax
0x1402762d0  mov     rdx, r14
0x1402762d3  mov     rcx, r15
0x1402762d6  call    ?SetValueInternal@HyperVStorage@@IEAAXPEBGW4HyperVStorageKeyType@@IPEBE@Z; HyperVStorage::SetValueInternal(ushort const *,HyperVStorageKeyType,uint,uchar const *)
0x1402762db  mov     edi, ebx
0x1402762dd  jmp     short loc_1402762E8
0x1402762df  mov     edi, [rsp+0A8h+var_78]
0x1402762e3  mov     rsi, [rsp+0A8h+var_70]
0x1402762e8  test    rsi, rsi
0x1402762eb  jz      short loc_1402762FC
0x1402762ed  mov     rcx, rsi; psa
0x1402762f0  call    cs:__imp_SafeArrayUnaccessData
0x1402762f7  nop     dword ptr [rax+rax+00h]
0x1402762fc  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x140276301  call    cs:__imp_VariantClear
0x140276308  nop     dword ptr [rax+rax+00h]
0x14027630d  mov     eax, edi
0x14027630f  mov     rcx, [rsp+0A8h+var_38]
0x140276314  xor     rcx, rsp; StackCookie
0x140276317  call    __security_check_cookie
0x14027631c  add     rsp, 80h
0x140276323  pop     r15
0x140276325  pop     r14
0x140276327  pop     rdi
0x140276328  pop     rsi
0x140276329  pop     rbx
0x14027632a  retn
```
