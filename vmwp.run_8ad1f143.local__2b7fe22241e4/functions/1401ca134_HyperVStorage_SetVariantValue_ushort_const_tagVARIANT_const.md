# HyperVStorage::SetVariantValue(ushort const *,tagVARIANT const &)

- ea: `0x1401ca134`
- end: `0x1401ca49c`
- name: `?SetVariantValue@HyperVStorage@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `872`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401ea910`

## callees

- `0x140036ccc`
- `0x1400b9bc4`
- `0x140132960`
- `0x1401ca134`
- `0x1402c2010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401ca178`
- `OLEAUT32!__imp_VariantInit` at `0x1401ca178`
- `OLEAUT32!__imp_VariantClear` at `0x1401ca471`
- `OLEAUT32!__imp_VariantClear` at `0x1401ca471`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca1ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca302`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca3d0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca405`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca1ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca302`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca3d0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401ca405`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ca27d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ca27d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ca248`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ca248`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ca213`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ca213`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ca460`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ca460`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401ca343`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401ca343`

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
0x1401ca134  push    rbx
0x1401ca136  push    rsi
0x1401ca137  push    rdi
0x1401ca138  push    r14
0x1401ca13a  push    r15
0x1401ca13c  sub     rsp, 80h
0x1401ca143  mov     rax, cs:__security_cookie
0x1401ca14a  xor     rax, rsp
0x1401ca14d  mov     [rsp+0A8h+var_38], rax
0x1401ca152  mov     rdi, r8
0x1401ca155  mov     r14, rdx
0x1401ca158  mov     r15, rcx
0x1401ca15b  xorps   xmm0, xmm0
0x1401ca15e  xor     eax, eax
0x1401ca160  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1401ca165  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1401ca16a  xor     ebx, ebx
0x1401ca16c  mov     esi, ebx
0x1401ca16e  mov     [rsp+0A8h+var_70], rbx
0x1401ca173  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401ca178  call    cs:__imp_VariantInit
0x1401ca17f  nop     dword ptr [rax+rax+00h]
0x1401ca184  nop
0x1401ca185  mov     rax, [r15]
0x1401ca188  mov     rcx, r15
0x1401ca18b  mov     rax, [rax+120h]
0x1401ca192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca197  test    eax, eax
0x1401ca199  jnz     short loc_1401CA1A5
0x1401ca19b  mov     ecx, 80004005h; int
0x1401ca1a0  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca1a5  test    r14, r14
0x1401ca1a8  jnz     short loc_1401CA1B4
0x1401ca1aa  mov     ecx, 80070057h; int
0x1401ca1af  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca1b4  mov     [rsp+0A8h+ppvData], rbx
0x1401ca1b9  mov     [rsp+0A8h+var_58], ebx
0x1401ca1bd  movzx   eax, word ptr [rdi]
0x1401ca1c0  bt      ax, 0Dh
0x1401ca1c5  jnb     loc_1401CA2A7
0x1401ca1cb  mov     ecx, 0FFFh
0x1401ca1d0  and     ax, cx
0x1401ca1d3  mov     edx, 11h
0x1401ca1d8  cmp     ax, dx
0x1401ca1db  jz      short loc_1401CA20A
0x1401ca1dd  mov     r9d, 2011h; vt
0x1401ca1e3  xor     r8d, r8d; wFlags
0x1401ca1e6  mov     rdx, rdi; pvarSrc
0x1401ca1e9  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca1ee  call    cs:__imp_VariantChangeType
0x1401ca1f5  nop     dword ptr [rax+rax+00h]
0x1401ca1fa  test    eax, eax
0x1401ca1fc  jns     short loc_1401CA205
0x1401ca1fe  mov     ecx, eax; int
0x1401ca200  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca205  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca20a  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401ca20f  mov     rcx, [rdi+8]; psa
0x1401ca213  call    cs:__imp_SafeArrayAccessData
0x1401ca21a  nop     dword ptr [rax+rax+00h]
0x1401ca21f  test    eax, eax
0x1401ca221  jns     short loc_1401CA22A
0x1401ca223  mov     ecx, eax; int
0x1401ca225  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca22a  mov     rsi, [rdi+8]
0x1401ca22e  mov     [rsp+0A8h+var_70], rsi
0x1401ca233  mov     [rsp+0A8h+plUbound], ebx
0x1401ca237  mov     [rsp+0A8h+plLbound], ebx
0x1401ca23b  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x1401ca240  mov     edx, 1; nDim
0x1401ca245  mov     rcx, rsi; psa
0x1401ca248  call    cs:__imp_SafeArrayGetLBound
0x1401ca24f  nop     dword ptr [rax+rax+00h]
0x1401ca254  test    eax, eax
0x1401ca256  jns     short loc_1401CA25F
0x1401ca258  mov     ecx, eax; int
0x1401ca25a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca25f  cmp     [rsp+0A8h+plLbound], ebx
0x1401ca263  jz      short loc_1401CA26F
0x1401ca265  mov     ecx, 80070057h; int
0x1401ca26a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca26f  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x1401ca274  mov     edx, 1; nDim
0x1401ca279  mov     rcx, [rdi+8]; psa
0x1401ca27d  call    cs:__imp_SafeArrayGetUBound
0x1401ca284  nop     dword ptr [rax+rax+00h]
0x1401ca289  test    eax, eax
0x1401ca28b  jns     short loc_1401CA294
0x1401ca28d  mov     ecx, eax; int
0x1401ca28f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca294  mov     r9d, [rsp+0A8h+plUbound]
0x1401ca299  inc     r9d
0x1401ca29c  mov     r8d, 7
0x1401ca2a2  jmp     loc_1401CA436
0x1401ca2a7  mov     ecx, eax
0x1401ca2a9  cmp     eax, 10h
0x1401ca2ac  ja      loc_1401CA392
0x1401ca2b2  jz      loc_1401CA3BF
0x1401ca2b8  sub     ecx, 2
0x1401ca2bb  jz      loc_1401CA3BF
0x1401ca2c1  sub     ecx, 1
0x1401ca2c4  jz      loc_1401CA3BF
0x1401ca2ca  sub     ecx, 1
0x1401ca2cd  jz      short loc_1401CA2F1
0x1401ca2cf  sub     ecx, 1
0x1401ca2d2  jz      loc_1401CA362
0x1401ca2d8  mov     r8d, 3
0x1401ca2de  sub     ecx, r8d
0x1401ca2e1  jz      short loc_1401CA33A
0x1401ca2e3  sub     ecx, r8d
0x1401ca2e6  jz      short loc_1401CA319
0x1401ca2e8  cmp     ecx, r8d
0x1401ca2eb  jnz     loc_1401CA3B5
0x1401ca2f1  mov     r9d, 5; vt
0x1401ca2f7  xor     r8d, r8d; wFlags
0x1401ca2fa  mov     rdx, rdi; pvarSrc
0x1401ca2fd  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca302  call    cs:__imp_VariantChangeType
0x1401ca309  nop     dword ptr [rax+rax+00h]
0x1401ca30e  test    eax, eax
0x1401ca310  jns     short loc_1401CA35D
0x1401ca312  mov     ecx, eax; int
0x1401ca314  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca319  mov     eax, ebx
0x1401ca31b  cmp     [rdi+8], bx
0x1401ca31f  setnz   al
0x1401ca322  mov     [rsp+0A8h+var_58], eax
0x1401ca326  lea     rax, [rsp+0A8h+var_58]
0x1401ca32b  mov     r9d, 4
0x1401ca331  lea     r8d, [r9+4]
0x1401ca335  jmp     loc_1401CA431
0x1401ca33a  mov     rcx, [rdi+8]; bstr
0x1401ca33e  mov     [rsp+0A8h+ppvData], rcx
0x1401ca343  call    cs:__imp_SysStringByteLen
0x1401ca34a  nop     dword ptr [rax+rax+00h]
0x1401ca34f  mov     r9d, eax
0x1401ca352  mov     r8d, 6
0x1401ca358  jmp     loc_1401CA436
0x1401ca35d  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca362  add     rdi, 8
0x1401ca366  movsd   xmm0, qword ptr [rdi]
0x1401ca36a  comisd  xmm0, cs:__real@7feffffffffffff6
0x1401ca372  jbe     short loc_1401CA37E
0x1401ca374  mov     ecx, 8002000Ah; int
0x1401ca379  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca37e  mov     [rsp+0A8h+ppvData], rdi
0x1401ca383  mov     r9d, 8
0x1401ca389  lea     r8d, [r9-3]
0x1401ca38d  jmp     loc_1401CA436
0x1401ca392  sub     ecx, 11h
0x1401ca395  jz      short loc_1401CA3F4
0x1401ca397  sub     ecx, 1
0x1401ca39a  jz      short loc_1401CA3F4
0x1401ca39c  sub     ecx, 1
0x1401ca39f  jz      short loc_1401CA3F4
0x1401ca3a1  sub     ecx, 1
0x1401ca3a4  jz      short loc_1401CA3EC
0x1401ca3a6  sub     ecx, 1
0x1401ca3a9  jz      short loc_1401CA421
0x1401ca3ab  sub     ecx, 1
0x1401ca3ae  jz      short loc_1401CA3BF
0x1401ca3b0  cmp     ecx, 1
0x1401ca3b3  jz      short loc_1401CA3F4
0x1401ca3b5  mov     ecx, 80020005h; int
0x1401ca3ba  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca3bf  mov     r9d, 14h; vt
0x1401ca3c5  xor     r8d, r8d; wFlags
0x1401ca3c8  mov     rdx, rdi; pvarSrc
0x1401ca3cb  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca3d0  call    cs:__imp_VariantChangeType
0x1401ca3d7  nop     dword ptr [rax+rax+00h]
0x1401ca3dc  test    eax, eax
0x1401ca3de  jns     short loc_1401CA3E7
0x1401ca3e0  mov     ecx, eax; int
0x1401ca3e2  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca3e7  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca3ec  mov     r8d, 3
0x1401ca3f2  jmp     short loc_1401CA427
0x1401ca3f4  mov     r9d, 15h; vt
0x1401ca3fa  xor     r8d, r8d; wFlags
0x1401ca3fd  mov     rdx, rdi; pvarSrc
0x1401ca400  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401ca405  call    cs:__imp_VariantChangeType
0x1401ca40c  nop     dword ptr [rax+rax+00h]
0x1401ca411  test    eax, eax
0x1401ca413  jns     short loc_1401CA41C
0x1401ca415  mov     ecx, eax; int
0x1401ca417  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401ca41c  lea     rdi, [rsp+0A8h+pvarg]
0x1401ca421  mov     r8d, 4
0x1401ca427  mov     r9d, 8
0x1401ca42d  lea     rax, [rdi+8]
0x1401ca431  mov     [rsp+0A8h+ppvData], rax
0x1401ca436  mov     rax, [rsp+0A8h+ppvData]
0x1401ca43b  mov     [rsp+0A8h+var_88], rax
0x1401ca440  mov     rdx, r14
0x1401ca443  mov     rcx, r15
0x1401ca446  call    ?SetValueInternal@HyperVStorage@@IEAAXPEBGW4HyperVStorageKeyType@@IPEBE@Z; HyperVStorage::SetValueInternal(ushort const *,HyperVStorageKeyType,uint,uchar const *)
0x1401ca44b  mov     edi, ebx
0x1401ca44d  jmp     short loc_1401CA458
0x1401ca44f  mov     edi, [rsp+0A8h+var_78]
0x1401ca453  mov     rsi, [rsp+0A8h+var_70]
0x1401ca458  test    rsi, rsi
0x1401ca45b  jz      short loc_1401CA46C
0x1401ca45d  mov     rcx, rsi; psa
0x1401ca460  call    cs:__imp_SafeArrayUnaccessData
0x1401ca467  nop     dword ptr [rax+rax+00h]
0x1401ca46c  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401ca471  call    cs:__imp_VariantClear
0x1401ca478  nop     dword ptr [rax+rax+00h]
0x1401ca47d  mov     eax, edi
0x1401ca47f  mov     rcx, [rsp+0A8h+var_38]
0x1401ca484  xor     rcx, rsp; StackCookie
0x1401ca487  call    __security_check_cookie
0x1401ca48c  add     rsp, 80h
0x1401ca493  pop     r15
0x1401ca495  pop     r14
0x1401ca497  pop     rdi
0x1401ca498  pop     rsi
0x1401ca499  pop     rbx
0x1401ca49a  retn
```
