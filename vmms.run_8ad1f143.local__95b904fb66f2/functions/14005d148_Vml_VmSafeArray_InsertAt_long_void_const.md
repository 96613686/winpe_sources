# Vml::VmSafeArray::InsertAt(long,void const *)

- ea: `0x14005d148`
- end: `0x14005d48c`
- name: `?InsertAt@VmSafeArray@Vml@@QEAAXJPEBX@Z`
- size: `836`
- prototype: `void __fastcall(Vml::VmSafeArray *__hidden this, int, const void *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14005cba8`
- `0x14005d970`
- `0x140082ba8`
- `0x14012cb98`
- `0x1407fad48`

## callees

- `0x14005d148`
- `0x140188e18`
- `0x1404828e0`
- `0x1404835a0`
- `0x140486541`
- `0x140498a40`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14005d300`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14005d300`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005d189`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005d189`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14005d1bc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14005d219`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14005d1bc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14005d219`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005d287`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005d287`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d33e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d33e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14005d39a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14005d39a`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x14005d23a`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x14005d23a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14005d366`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14005d366`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14005d2d2`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14005d2f1`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14005d2d2`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14005d2f1`

## string_xrefs

- `0x14005d24e`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d29b`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d3ae`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d3f9`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d412`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d42b`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d444`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d474`: `onecore\vm\common\vml\VmAutomation.h`

## pseudocode

```c
void __fastcall Vml::VmSafeArray::InsertAt(SAFEARRAY **this, int a2, const void **a3)
{
  SAFEARRAY *v4; // rcx
  HRESULT UBound; // eax
  LONG v7; // r14d
  SAFEARRAY *v8; // rcx
  HRESULT LBound; // eax
  int v10; // eax
  SAFEARRAY *v11; // rcx
  HRESULT v12; // eax
  LONG v13; // eax
  SAFEARRAY *v14; // rcx
  HRESULT v15; // eax
  HRESULT v16; // eax
  SAFEARRAY *v17; // rcx
  SAFEARRAY *v18; // rcx
  UINT Elemsize; // ebx
  SAFEARRAY *v20; // rcx
  __int16 v21; // ax
  HRESULT Vartype; // eax
  SAFEARRAY *v23; // r9
  HRESULT v24; // eax
  SAFEARRAYBOUND psaboundNew; // [rsp+20h] [rbp-40h] BYREF
  void *v26; // [rsp+28h] [rbp-38h] BYREF
  LONG plUbound; // [rsp+30h] [rbp-30h] BYREF
  LONG rgIndices; // [rsp+38h] [rbp-28h] BYREF
  SAFEARRAY *psa; // [rsp+40h] [rbp-20h]
  void *ppvData; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  rgIndices = a2;
  v4 = *this;
  plUbound = 0;
  if ( v4 )
  {
    UBound = SafeArrayGetUBound(v4, 1u, &plUbound);
    if ( UBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)UBound,
        psaboundNew.cElements);
    v7 = plUbound;
    a2 = rgIndices;
  }
  else
  {
    v7 = -1;
  }
  v8 = *this;
  plUbound = 0;
  if ( v8 )
  {
    LBound = SafeArrayGetLBound(v8, 1u, &plUbound);
    if ( LBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)LBound,
        psaboundNew.cElements);
    LODWORD(v8) = plUbound;
    a2 = rgIndices;
  }
  if ( a2 < (int)v8 || a2 > v7 + 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8002000BLL,
      psaboundNew.cElements);
  psaboundNew = 0;
  v10 = v7 - (_DWORD)v8;
  plUbound = 0;
  v11 = *this;
  psaboundNew = (SAFEARRAYBOUND)(unsigned int)(v10 + 2);
  if ( v11 )
  {
    v12 = SafeArrayGetLBound(v11, 1u, &plUbound);
    if ( v12 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v12,
        psaboundNew.cElements);
    v13 = plUbound;
  }
  else
  {
    v13 = 0;
  }
  v14 = *this;
  psaboundNew.lLbound = v13;
  v15 = SafeArrayRedim(v14, &psaboundNew);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x435,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v15,
      psaboundNew.cElements);
  if ( rgIndices != v7 + 1 )
  {
    psa = *this;
    ppvData = 0;
    v16 = SafeArrayAccessData(psa, &ppvData);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B2,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v16,
        psaboundNew.cElements);
    v17 = *this;
    psaboundNew = 0;
    plUbound = 0;
    v26 = 0;
    SafeArrayPtrOfIndex(v17, &rgIndices, (void **)&psaboundNew);
    v18 = *this;
    plUbound = rgIndices + 1;
    SafeArrayPtrOfIndex(v18, &plUbound, &v26);
    Elemsize = SafeArrayGetElemsize(*this);
    memmove_0(v26, *(const void **)&psaboundNew, Elemsize * (v7 - rgIndices + 1));
    memset_0(*(void **)&psaboundNew, 0, Elemsize);
    if ( psa )
      SafeArrayUnaccessData(psa);
  }
  v20 = *this;
  psaboundNew.cElements = rgIndices;
  v21 = 0;
  LOWORD(plUbound) = 0;
  if ( v20 )
  {
    Vartype = SafeArrayGetVartype(v20, (VARTYPE *)&plUbound);
    if ( Vartype < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x38D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)Vartype,
        psaboundNew.cElements);
    v21 = plUbound;
    v23 = *this;
  }
  else
  {
    v23 = 0;
  }
  if ( v21 == 8 || v21 == 9 || v21 == 13 )
    a3 = (const void **)*a3;
  v24 = SafeArrayPutElement(v23, (LONG *)&psaboundNew, a3);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3A,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v24,
      psaboundNew.cElements);
}

```

## disassembly

```asm
0x14005d148  push    rbp
0x14005d14a  push    rbx
0x14005d14b  push    rsi
0x14005d14c  push    rdi
0x14005d14d  push    r14
0x14005d14f  mov     rbp, rsp
0x14005d152  sub     rsp, 60h
0x14005d156  mov     rax, cs:__security_cookie
0x14005d15d  xor     rax, rsp
0x14005d160  mov     [rbp+var_10], rax
0x14005d164  mov     rsi, rcx
0x14005d167  mov     [rbp+rgIndices], edx
0x14005d16a  mov     rcx, [rcx]; psa
0x14005d16d  mov     rdi, r8
0x14005d170  mov     [rbp+plUbound], 0
0x14005d177  test    rcx, rcx
0x14005d17a  jz      loc_14005D3EC
0x14005d180  lea     r8, [rbp+plUbound]; plUbound
0x14005d184  mov     edx, 1; nDim
0x14005d189  call    cs:__imp_SafeArrayGetUBound
0x14005d190  nop     dword ptr [rax+rax+00h]
0x14005d195  test    eax, eax
0x14005d197  js      loc_14005D3F5
0x14005d19d  mov     r14d, [rbp+plUbound]
0x14005d1a1  mov     edx, [rbp+rgIndices]
0x14005d1a4  mov     rcx, [rsi]; psa
0x14005d1a7  mov     [rbp+plUbound], 0
0x14005d1ae  test    rcx, rcx
0x14005d1b1  jz      short loc_14005D1D6
0x14005d1b3  lea     r8, [rbp+plUbound]; plLbound
0x14005d1b7  mov     edx, 1; nDim
0x14005d1bc  call    cs:__imp_SafeArrayGetLBound
0x14005d1c3  nop     dword ptr [rax+rax+00h]
0x14005d1c8  test    eax, eax
0x14005d1ca  js      loc_14005D40E
0x14005d1d0  mov     ecx, [rbp+plUbound]
0x14005d1d3  mov     edx, [rbp+rgIndices]
0x14005d1d6  cmp     edx, ecx
0x14005d1d8  jl      loc_14005D470
0x14005d1de  lea     ebx, [r14+1]
0x14005d1e2  cmp     edx, ebx
0x14005d1e4  jg      loc_14005D470
0x14005d1ea  mov     eax, r14d
0x14005d1ed  mov     qword ptr [rbp+psaboundNew.cElements], 0
0x14005d1f5  sub     eax, ecx
0x14005d1f7  mov     [rbp+plUbound], 0
0x14005d1fe  mov     rcx, [rsi]; psa
0x14005d201  add     eax, 2
0x14005d204  mov     [rbp+psaboundNew.cElements], eax
0x14005d207  test    rcx, rcx
0x14005d20a  jz      loc_14005D3E0
0x14005d210  lea     r8, [rbp+plUbound]; plLbound
0x14005d214  mov     edx, 1; nDim
0x14005d219  call    cs:__imp_SafeArrayGetLBound
0x14005d220  nop     dword ptr [rax+rax+00h]
0x14005d225  test    eax, eax
0x14005d227  js      loc_14005D427
0x14005d22d  mov     eax, [rbp+plUbound]
0x14005d230  mov     rcx, [rsi]; psa
0x14005d233  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x14005d237  mov     [rbp+psaboundNew.lLbound], eax
0x14005d23a  call    cs:__imp_SafeArrayRedim
0x14005d241  nop     dword ptr [rax+rax+00h]
0x14005d246  test    eax, eax
0x14005d248  jns     short loc_14005D263
0x14005d24a  mov     rcx, [rbp+28h]; this
0x14005d24e  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d255  mov     r9d, eax; char *
0x14005d258  mov     edx, 435h; void *
0x14005d25d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005d263  cmp     [rbp+rgIndices], ebx
0x14005d266  jz      loc_14005D34A
0x14005d26c  mov     rcx, [rsi]; psa
0x14005d26f  lea     rdx, [rbp+ppvData]; ppvData
0x14005d273  mov     [rbp+psa], 0
0x14005d27b  mov     [rbp+psa], rcx
0x14005d27f  mov     [rbp+ppvData], 0
0x14005d287  call    cs:__imp_SafeArrayAccessData
0x14005d28e  nop     dword ptr [rax+rax+00h]
0x14005d293  test    eax, eax
0x14005d295  jns     short loc_14005D2B0
0x14005d297  mov     rcx, [rbp+28h]; this
0x14005d29b  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d2a2  mov     r9d, eax; char *
0x14005d2a5  mov     edx, 7B2h; void *
0x14005d2aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005d2b0  mov     rcx, [rsi]; psa
0x14005d2b3  lea     r8, [rbp+psaboundNew]; ppvData
0x14005d2b7  lea     rdx, [rbp+rgIndices]; rgIndices
0x14005d2bb  mov     qword ptr [rbp+psaboundNew.cElements], 0
0x14005d2c3  mov     [rbp+plUbound], 0
0x14005d2ca  mov     [rbp+var_38], 0
0x14005d2d2  call    cs:__imp_SafeArrayPtrOfIndex
0x14005d2d9  nop     dword ptr [rax+rax+00h]
0x14005d2de  mov     eax, [rbp+rgIndices]
0x14005d2e1  lea     r8, [rbp+var_38]; ppvData
0x14005d2e5  mov     rcx, [rsi]; psa
0x14005d2e8  lea     rdx, [rbp+plUbound]; rgIndices
0x14005d2ec  inc     eax
0x14005d2ee  mov     [rbp+plUbound], eax
0x14005d2f1  call    cs:__imp_SafeArrayPtrOfIndex
0x14005d2f8  nop     dword ptr [rax+rax+00h]
0x14005d2fd  mov     rcx, [rsi]; psa
0x14005d300  call    cs:__imp_SafeArrayGetElemsize
0x14005d307  nop     dword ptr [rax+rax+00h]
0x14005d30c  sub     r14d, [rbp+rgIndices]
0x14005d310  mov     rdx, qword ptr [rbp+psaboundNew.cElements]; Src
0x14005d314  mov     rcx, [rbp+var_38]; void *
0x14005d318  mov     ebx, eax
0x14005d31a  lea     r8d, [r14+1]
0x14005d31e  imul    r8d, eax; Size
0x14005d322  call    memmove_0
0x14005d327  mov     rcx, qword ptr [rbp+psaboundNew.cElements]; void *
0x14005d32b  mov     r8d, ebx; Size
0x14005d32e  xor     edx, edx; Val
0x14005d330  call    memset_0
0x14005d335  mov     rcx, [rbp+psa]; psa
0x14005d339  test    rcx, rcx
0x14005d33c  jz      short loc_14005D34A
0x14005d33e  call    cs:__imp_SafeArrayUnaccessData
0x14005d345  nop     dword ptr [rax+rax+00h]
0x14005d34a  mov     eax, [rbp+rgIndices]
0x14005d34d  mov     rcx, [rsi]; psa
0x14005d350  mov     [rbp+psaboundNew.cElements], eax
0x14005d353  xor     eax, eax
0x14005d355  mov     word ptr [rbp+plUbound], ax
0x14005d359  test    rcx, rcx
0x14005d35c  jz      loc_14005D3E7
0x14005d362  lea     rdx, [rbp+plUbound]; pvt
0x14005d366  call    cs:__imp_SafeArrayGetVartype
0x14005d36d  nop     dword ptr [rax+rax+00h]
0x14005d372  test    eax, eax
0x14005d374  js      loc_14005D440
0x14005d37a  movzx   eax, word ptr [rbp+plUbound]
0x14005d37e  mov     r9, [rsi]
0x14005d381  movzx   ecx, ax
0x14005d384  sub     ecx, 8
0x14005d387  jnz     loc_14005D459
0x14005d38d  mov     rdi, [rdi]
0x14005d390  mov     r8, rdi; pv
0x14005d393  lea     rdx, [rbp+psaboundNew]; rgIndices
0x14005d397  mov     rcx, r9; psa
0x14005d39a  call    cs:__imp_SafeArrayPutElement
0x14005d3a1  nop     dword ptr [rax+rax+00h]
0x14005d3a6  test    eax, eax
0x14005d3a8  jns     short loc_14005D3C3
0x14005d3aa  mov     rcx, [rbp+28h]; this
0x14005d3ae  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d3b5  mov     r9d, eax; char *
0x14005d3b8  mov     edx, 0B3Ah; void *
0x14005d3bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005d3c3  mov     rcx, [rbp+var_10]
0x14005d3c7  xor     rcx, rsp; StackCookie
0x14005d3ca  call    __security_check_cookie
0x14005d3cf  add     rsp, 60h
0x14005d3d3  pop     r14
0x14005d3d5  pop     rdi
0x14005d3d6  pop     rsi
0x14005d3d7  pop     rbx
0x14005d3d8  pop     rbp
0x14005d3d9  retn
0x14005d3db  jmp     loc_14005D1D6
0x14005d3e0  xor     eax, eax
0x14005d3e2  jmp     loc_14005D230
0x14005d3e7  xor     r9d, r9d
0x14005d3ea  jmp     short loc_14005D381
0x14005d3ec  or      r14d, 0FFFFFFFFh
0x14005d3f0  jmp     loc_14005D1A4
0x14005d3f5  mov     rcx, [rbp+28h]; this
0x14005d3f9  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d400  mov     r9d, eax; char *
0x14005d403  mov     edx, 3AEh; void *
0x14005d408  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14005d40e  mov     rcx, [rbp+28h]; this
0x14005d412  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d419  mov     r9d, eax; char *
0x14005d41c  mov     edx, 3CEh; void *
0x14005d421  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14005d427  mov     rcx, [rbp+28h]; this
0x14005d42b  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d432  mov     r9d, eax; char *
0x14005d435  mov     edx, 3CEh; void *
0x14005d43a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14005d440  mov     rcx, [rbp+28h]; this
0x14005d444  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d44b  mov     r9d, eax; char *
0x14005d44e  mov     edx, 38Dh; void *
0x14005d453  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14005d459  sub     ecx, 1
0x14005d45c  jz      loc_14005D38D
0x14005d462  cmp     ecx, 4
0x14005d465  jnz     loc_14005D390
0x14005d46b  jmp     loc_14005D38D
0x14005d470  mov     rcx, [rbp+28h]; this
0x14005d474  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005d47b  mov     r9d, 8002000Bh; char *
0x14005d481  mov     edx, 0B5Dh; void *
0x14005d486  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
