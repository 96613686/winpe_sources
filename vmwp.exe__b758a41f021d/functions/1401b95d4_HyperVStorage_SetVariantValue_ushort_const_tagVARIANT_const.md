# HyperVStorage::SetVariantValue(ushort const *,tagVARIANT const &)

- ea: `0x1401b95d4`
- end: `0x1401b993c`
- name: `?SetVariantValue@HyperVStorage@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `872`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401da300`

## callees

- `0x140029a4c`
- `0x1400af904`
- `0x14011ea40`
- `0x1401b95d4`
- `0x1402cb010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401b9618`
- `OLEAUT32!__imp_VariantInit` at `0x1401b9618`
- `OLEAUT32!__imp_VariantClear` at `0x1401b9911`
- `OLEAUT32!__imp_VariantClear` at `0x1401b9911`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b968e`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b97a2`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b9870`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b98a5`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b968e`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b97a2`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b9870`
- `OLEAUT32!__imp_VariantChangeType` at `0x1401b98a5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401b971d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401b971d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401b96e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401b96e8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401b96b3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401b96b3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401b9900`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401b9900`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401b97e3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1401b97e3`

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
0x1401b95d4  push    rbx
0x1401b95d6  push    rsi
0x1401b95d7  push    rdi
0x1401b95d8  push    r14
0x1401b95da  push    r15
0x1401b95dc  sub     rsp, 80h
0x1401b95e3  mov     rax, cs:__security_cookie
0x1401b95ea  xor     rax, rsp
0x1401b95ed  mov     [rsp+0A8h+var_38], rax
0x1401b95f2  mov     rdi, r8
0x1401b95f5  mov     r14, rdx
0x1401b95f8  mov     r15, rcx
0x1401b95fb  xorps   xmm0, xmm0
0x1401b95fe  xor     eax, eax
0x1401b9600  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1401b9605  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1401b960a  xor     ebx, ebx
0x1401b960c  mov     esi, ebx
0x1401b960e  mov     [rsp+0A8h+var_70], rbx
0x1401b9613  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401b9618  call    cs:__imp_VariantInit
0x1401b961f  nop     dword ptr [rax+rax+00h]
0x1401b9624  nop
0x1401b9625  mov     rax, [r15]
0x1401b9628  mov     rcx, r15
0x1401b962b  mov     rax, [rax+120h]
0x1401b9632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401b9637  test    eax, eax
0x1401b9639  jnz     short loc_1401B9645
0x1401b963b  mov     ecx, 80004005h; int
0x1401b9640  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b9645  test    r14, r14
0x1401b9648  jnz     short loc_1401B9654
0x1401b964a  mov     ecx, 80070057h; int
0x1401b964f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b9654  mov     [rsp+0A8h+ppvData], rbx
0x1401b9659  mov     [rsp+0A8h+var_58], ebx
0x1401b965d  movzx   eax, word ptr [rdi]
0x1401b9660  bt      ax, 0Dh
0x1401b9665  jnb     loc_1401B9747
0x1401b966b  mov     ecx, 0FFFh
0x1401b9670  and     ax, cx
0x1401b9673  mov     edx, 11h
0x1401b9678  cmp     ax, dx
0x1401b967b  jz      short loc_1401B96AA
0x1401b967d  mov     r9d, 2011h; vt
0x1401b9683  xor     r8d, r8d; wFlags
0x1401b9686  mov     rdx, rdi; pvarSrc
0x1401b9689  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401b968e  call    cs:__imp_VariantChangeType
0x1401b9695  nop     dword ptr [rax+rax+00h]
0x1401b969a  test    eax, eax
0x1401b969c  jns     short loc_1401B96A5
0x1401b969e  mov     ecx, eax; int
0x1401b96a0  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b96a5  lea     rdi, [rsp+0A8h+pvarg]
0x1401b96aa  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401b96af  mov     rcx, [rdi+8]; psa
0x1401b96b3  call    cs:__imp_SafeArrayAccessData
0x1401b96ba  nop     dword ptr [rax+rax+00h]
0x1401b96bf  test    eax, eax
0x1401b96c1  jns     short loc_1401B96CA
0x1401b96c3  mov     ecx, eax; int
0x1401b96c5  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b96ca  mov     rsi, [rdi+8]
0x1401b96ce  mov     [rsp+0A8h+var_70], rsi
0x1401b96d3  mov     [rsp+0A8h+plUbound], ebx
0x1401b96d7  mov     [rsp+0A8h+plLbound], ebx
0x1401b96db  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x1401b96e0  mov     edx, 1; nDim
0x1401b96e5  mov     rcx, rsi; psa
0x1401b96e8  call    cs:__imp_SafeArrayGetLBound
0x1401b96ef  nop     dword ptr [rax+rax+00h]
0x1401b96f4  test    eax, eax
0x1401b96f6  jns     short loc_1401B96FF
0x1401b96f8  mov     ecx, eax; int
0x1401b96fa  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b96ff  cmp     [rsp+0A8h+plLbound], ebx
0x1401b9703  jz      short loc_1401B970F
0x1401b9705  mov     ecx, 80070057h; int
0x1401b970a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b970f  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x1401b9714  mov     edx, 1; nDim
0x1401b9719  mov     rcx, [rdi+8]; psa
0x1401b971d  call    cs:__imp_SafeArrayGetUBound
0x1401b9724  nop     dword ptr [rax+rax+00h]
0x1401b9729  test    eax, eax
0x1401b972b  jns     short loc_1401B9734
0x1401b972d  mov     ecx, eax; int
0x1401b972f  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b9734  mov     r9d, [rsp+0A8h+plUbound]
0x1401b9739  inc     r9d
0x1401b973c  mov     r8d, 7
0x1401b9742  jmp     loc_1401B98D6
0x1401b9747  mov     ecx, eax
0x1401b9749  cmp     eax, 10h
0x1401b974c  ja      loc_1401B9832
0x1401b9752  jz      loc_1401B985F
0x1401b9758  sub     ecx, 2
0x1401b975b  jz      loc_1401B985F
0x1401b9761  sub     ecx, 1
0x1401b9764  jz      loc_1401B985F
0x1401b976a  sub     ecx, 1
0x1401b976d  jz      short loc_1401B9791
0x1401b976f  sub     ecx, 1
0x1401b9772  jz      loc_1401B9802
0x1401b9778  mov     r8d, 3
0x1401b977e  sub     ecx, r8d
0x1401b9781  jz      short loc_1401B97DA
0x1401b9783  sub     ecx, r8d
0x1401b9786  jz      short loc_1401B97B9
0x1401b9788  cmp     ecx, r8d
0x1401b978b  jnz     loc_1401B9855
0x1401b9791  mov     r9d, 5; vt
0x1401b9797  xor     r8d, r8d; wFlags
0x1401b979a  mov     rdx, rdi; pvarSrc
0x1401b979d  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401b97a2  call    cs:__imp_VariantChangeType
0x1401b97a9  nop     dword ptr [rax+rax+00h]
0x1401b97ae  test    eax, eax
0x1401b97b0  jns     short loc_1401B97FD
0x1401b97b2  mov     ecx, eax; int
0x1401b97b4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b97b9  mov     eax, ebx
0x1401b97bb  cmp     [rdi+8], bx
0x1401b97bf  setnz   al
0x1401b97c2  mov     [rsp+0A8h+var_58], eax
0x1401b97c6  lea     rax, [rsp+0A8h+var_58]
0x1401b97cb  mov     r9d, 4
0x1401b97d1  lea     r8d, [r9+4]
0x1401b97d5  jmp     loc_1401B98D1
0x1401b97da  mov     rcx, [rdi+8]; bstr
0x1401b97de  mov     [rsp+0A8h+ppvData], rcx
0x1401b97e3  call    cs:__imp_SysStringByteLen
0x1401b97ea  nop     dword ptr [rax+rax+00h]
0x1401b97ef  mov     r9d, eax
0x1401b97f2  mov     r8d, 6
0x1401b97f8  jmp     loc_1401B98D6
0x1401b97fd  lea     rdi, [rsp+0A8h+pvarg]
0x1401b9802  add     rdi, 8
0x1401b9806  movsd   xmm0, qword ptr [rdi]
0x1401b980a  comisd  xmm0, cs:__real@7feffffffffffff6
0x1401b9812  jbe     short loc_1401B981E
0x1401b9814  mov     ecx, 8002000Ah; int
0x1401b9819  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b981e  mov     [rsp+0A8h+ppvData], rdi
0x1401b9823  mov     r9d, 8
0x1401b9829  lea     r8d, [r9-3]
0x1401b982d  jmp     loc_1401B98D6
0x1401b9832  sub     ecx, 11h
0x1401b9835  jz      short loc_1401B9894
0x1401b9837  sub     ecx, 1
0x1401b983a  jz      short loc_1401B9894
0x1401b983c  sub     ecx, 1
0x1401b983f  jz      short loc_1401B9894
0x1401b9841  sub     ecx, 1
0x1401b9844  jz      short loc_1401B988C
0x1401b9846  sub     ecx, 1
0x1401b9849  jz      short loc_1401B98C1
0x1401b984b  sub     ecx, 1
0x1401b984e  jz      short loc_1401B985F
0x1401b9850  cmp     ecx, 1
0x1401b9853  jz      short loc_1401B9894
0x1401b9855  mov     ecx, 80020005h; int
0x1401b985a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b985f  mov     r9d, 14h; vt
0x1401b9865  xor     r8d, r8d; wFlags
0x1401b9868  mov     rdx, rdi; pvarSrc
0x1401b986b  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401b9870  call    cs:__imp_VariantChangeType
0x1401b9877  nop     dword ptr [rax+rax+00h]
0x1401b987c  test    eax, eax
0x1401b987e  jns     short loc_1401B9887
0x1401b9880  mov     ecx, eax; int
0x1401b9882  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b9887  lea     rdi, [rsp+0A8h+pvarg]
0x1401b988c  mov     r8d, 3
0x1401b9892  jmp     short loc_1401B98C7
0x1401b9894  mov     r9d, 15h; vt
0x1401b989a  xor     r8d, r8d; wFlags
0x1401b989d  mov     rdx, rdi; pvarSrc
0x1401b98a0  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1401b98a5  call    cs:__imp_VariantChangeType
0x1401b98ac  nop     dword ptr [rax+rax+00h]
0x1401b98b1  test    eax, eax
0x1401b98b3  jns     short loc_1401B98BC
0x1401b98b5  mov     ecx, eax; int
0x1401b98b7  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b98bc  lea     rdi, [rsp+0A8h+pvarg]
0x1401b98c1  mov     r8d, 4
0x1401b98c7  mov     r9d, 8
0x1401b98cd  lea     rax, [rdi+8]
0x1401b98d1  mov     [rsp+0A8h+ppvData], rax
0x1401b98d6  mov     rax, [rsp+0A8h+ppvData]
0x1401b98db  mov     [rsp+0A8h+var_88], rax
0x1401b98e0  mov     rdx, r14
0x1401b98e3  mov     rcx, r15
0x1401b98e6  call    ?SetValueInternal@HyperVStorage@@IEAAXPEBGW4HyperVStorageKeyType@@IPEBE@Z; HyperVStorage::SetValueInternal(ushort const *,HyperVStorageKeyType,uint,uchar const *)
0x1401b98eb  mov     edi, ebx
0x1401b98ed  jmp     short loc_1401B98F8
0x1401b98ef  mov     edi, [rsp+0A8h+var_78]
0x1401b98f3  mov     rsi, [rsp+0A8h+var_70]
0x1401b98f8  test    rsi, rsi
0x1401b98fb  jz      short loc_1401B990C
0x1401b98fd  mov     rcx, rsi; psa
0x1401b9900  call    cs:__imp_SafeArrayUnaccessData
0x1401b9907  nop     dword ptr [rax+rax+00h]
0x1401b990c  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1401b9911  call    cs:__imp_VariantClear
0x1401b9918  nop     dword ptr [rax+rax+00h]
0x1401b991d  mov     eax, edi
0x1401b991f  mov     rcx, [rsp+0A8h+var_38]
0x1401b9924  xor     rcx, rsp; StackCookie
0x1401b9927  call    __security_check_cookie
0x1401b992c  add     rsp, 80h
0x1401b9933  pop     r15
0x1401b9935  pop     r14
0x1401b9937  pop     rdi
0x1401b9938  pop     rsi
0x1401b9939  pop     rbx
0x1401b993a  retn
```
