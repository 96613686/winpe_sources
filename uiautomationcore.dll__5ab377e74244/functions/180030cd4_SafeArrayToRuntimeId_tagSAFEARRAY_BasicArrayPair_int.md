# SafeArrayToRuntimeId(tagSAFEARRAY *,BasicArrayPair<int> *)

- ea: `0x180030cd4`
- end: `0x180030ede`
- name: `?SafeArrayToRuntimeId@@YAXPEAUtagSAFEARRAY@@PEAU?$BasicArrayPair@H@@@Z`
- size: `522`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004cc00`
- `0x180066654`
- `0x180067d64`
- `0x180170c00`
- `0x180199948`

## callees

- `0x18002f580`
- `0x180030cd4`
- `0x180032724`
- `0x1801e8344`
- `0x1801e8840`
- `0x1801e9240`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180030d01`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180030d01`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180030d6f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180030d6f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180030d55`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180030d55`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180030d92`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180030d92`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180030e60`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180030e60`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180030d22`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180030d22`

## string_xrefs

- `0x180030e79`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180030e35`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x180030daf`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x180030e17`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SafeArrayToRuntimeId(SAFEARRAY *a1, __int64 a2)
{
  HRESULT Vartype; // eax
  int v4; // ebx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v7; // eax
  void *v8; // rsi
  unsigned __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  SAFEARRAY *psa; // [rsp+20h] [rbp-20h]
  int v14; // [rsp+28h] [rbp-18h]
  void *ppvData; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *pvt; // [rsp+70h] [rbp+30h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+40h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+48h] BYREF

  if ( !a1 )
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)a2 = 0;
    return;
  }
  v14 = 0;
  ppvData = 0;
  psa = a1;
  if ( SafeArrayGetDim(a1) != 1 )
  {
    v12 = 92;
LABEL_23:
    v4 = -2147024809;
    v11 = 2147942487LL;
    goto LABEL_20;
  }
  LOWORD(pvt) = 0;
  Vartype = SafeArrayGetVartype(psa, (VARTYPE *)&pvt);
  v4 = Vartype;
  if ( Vartype < 0 )
  {
    v11 = (unsigned int)Vartype;
    v12 = 95;
    goto LABEL_20;
  }
  if ( (_WORD)pvt != 3 && (_WORD)pvt != 22 )
  {
    v12 = 106;
    goto LABEL_23;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
  v4 = LBound;
  if ( LBound < 0 )
  {
    v11 = (unsigned int)LBound;
    v12 = 111;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v11,
      (int)psa);
    goto LABEL_9;
  }
  UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
  v4 = UBound;
  if ( UBound < 0 )
  {
    v11 = (unsigned int)UBound;
    v12 = 112;
    goto LABEL_20;
  }
  v14 = plUbound - plLbound + 1;
  v7 = SafeArrayAccessData(psa, &ppvData);
  v4 = v7;
  if ( v7 < 0 )
  {
    v11 = (unsigned int)v7;
    v12 = 115;
    goto LABEL_20;
  }
  v4 = 0;
LABEL_9:
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
      (const char *)(unsigned int)v4,
      (int)psa);
  v8 = operator new[](saturated_mul(v14, 4u));
  pvt = v8;
  v9 = 4LL * (unsigned int)v14;
  if ( v9 > 0xFFFFFFFF )
  {
    v10 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
      (const char *)0x80070216LL,
      (int)psa);
  }
  else
  {
    memcpy_0(v8, ppvData, (unsigned int)v9);
    v10 = 0;
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
      (const char *)(unsigned int)v10,
      (int)psa);
  *(_QWORD *)(a2 + 8) = v8;
  *(_DWORD *)a2 = v14;
  operator delete(0);
  if ( psa )
    SafeArrayUnaccessData(psa);
}

```

## disassembly

```asm
0x180030cd4  push    rbp
0x180030cd6  push    rbx
0x180030cd7  push    rsi
0x180030cd8  push    rdi
0x180030cd9  push    r14
0x180030cdb  mov     rbp, rsp
0x180030cde  sub     rsp, 40h
0x180030ce2  mov     rdi, rdx
0x180030ce5  test    rcx, rcx
0x180030ce8  jz      loc_180030EB1
0x180030cee  mov     [rbp+var_18], 0
0x180030cf5  mov     [rbp+ppvData], 0
0x180030cfd  mov     [rbp+psa], rcx
0x180030d01  call    cs:__imp_SafeArrayGetDim
0x180030d07  mov     esi, 1
0x180030d0c  cmp     eax, esi
0x180030d0e  jnz     loc_180030E98
0x180030d14  xor     eax, eax
0x180030d16  mov     word ptr [rbp+pvt], ax
0x180030d1a  lea     rdx, [rbp+pvt]; pvt
0x180030d1e  mov     rcx, [rbp+psa]; psa
0x180030d22  call    cs:__imp_SafeArrayGetVartype
0x180030d28  mov     ebx, eax
0x180030d2a  test    eax, eax
0x180030d2c  js      loc_180030EA7
0x180030d32  cmp     word ptr [rbp+pvt], 3
0x180030d37  jnz     loc_180030ECB
0x180030d3d  mov     [rbp+plLbound], 0
0x180030d44  mov     [rbp+plUbound], 0
0x180030d4b  lea     r8, [rbp+plLbound]; plLbound
0x180030d4f  mov     edx, esi; nDim
0x180030d51  mov     rcx, [rbp+psa]; psa
0x180030d55  call    cs:__imp_SafeArrayGetLBound
0x180030d5b  mov     ebx, eax
0x180030d5d  test    eax, eax
0x180030d5f  js      loc_180030E71
0x180030d65  lea     r8, [rbp+plUbound]; plUbound
0x180030d69  mov     edx, esi; nDim
0x180030d6b  mov     rcx, [rbp+psa]; psa
0x180030d6f  call    cs:__imp_SafeArrayGetUBound
0x180030d75  mov     ebx, eax
0x180030d77  test    eax, eax
0x180030d79  js      loc_180030E8E
0x180030d7f  mov     eax, [rbp+plUbound]
0x180030d82  sub     eax, [rbp+plLbound]
0x180030d85  add     eax, esi
0x180030d87  mov     [rbp+var_18], eax
0x180030d8a  lea     rdx, [rbp+ppvData]; ppvData
0x180030d8e  mov     rcx, [rbp+psa]; psa
0x180030d92  call    cs:__imp_SafeArrayAccessData
0x180030d98  mov     ebx, eax
0x180030d9a  test    eax, eax
0x180030d9c  js      loc_180030EC1
0x180030da2  xor     ebx, ebx
0x180030da4  mov     rcx, [rbp+28h]; this
0x180030da8  test    ebx, ebx
0x180030daa  jns     short loc_180030DC1
0x180030dac  mov     r9d, ebx; char *
0x180030daf  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x180030db6  mov     edx, 138h; void *
0x180030dbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030dc1  mov     r14d, [rbp+var_18]
0x180030dc5  movsxd  rcx, r14d
0x180030dc8  mov     eax, 4
0x180030dcd  mul     rcx
0x180030dd0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180030dd7  cmovb   rax, rcx
0x180030ddb  mov     rcx, rax; unsigned __int64
0x180030dde  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180030de3  mov     rsi, rax
0x180030de6  mov     [rbp+pvt], rax
0x180030dea  mov     eax, r14d
0x180030ded  shl     rax, 2
0x180030df1  mov     ecx, 0FFFFFFFFh
0x180030df6  cmp     rax, rcx
0x180030df9  ja      short loc_180030E29
0x180030dfb  mov     r8d, eax; Size
0x180030dfe  mov     rdx, [rbp+ppvData]; Src
0x180030e02  mov     rcx, rsi; void *
0x180030e05  call    memcpy_0
0x180030e0a  xor     ebx, ebx
0x180030e0c  mov     rcx, [rbp+28h]; this
0x180030e10  test    ebx, ebx
0x180030e12  jns     short loc_180030E48
0x180030e14  mov     r9d, ebx; char *
0x180030e17  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x180030e1e  mov     edx, 13Ch; void *
0x180030e23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030e29  mov     rcx, [rbp+28h]; this
0x180030e2d  mov     ebx, 80070216h
0x180030e32  mov     r9d, ebx; char *
0x180030e35  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x180030e3c  mov     edx, 46h ; 'F'; void *
0x180030e41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030e46  jmp     short loc_180030E0C
0x180030e48  mov     [rdi+8], rsi
0x180030e4c  mov     [rdi], r14d
0x180030e4f  xor     ecx, ecx; Block
0x180030e51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030e56  nop
0x180030e57  mov     rcx, [rbp+psa]; psa
0x180030e5b  test    rcx, rcx
0x180030e5e  jz      short loc_180030E66
0x180030e60  call    cs:__imp_SafeArrayUnaccessData
0x180030e66  add     rsp, 40h
0x180030e6a  pop     r14
0x180030e6c  pop     rdi
0x180030e6d  pop     rsi
0x180030e6e  pop     rbx
0x180030e6f  pop     rbp
0x180030e70  retn
0x180030e71  mov     r9d, eax; char *
0x180030e74  mov     edx, 6Fh ; 'o'; void *
0x180030e79  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x180030e80  mov     rcx, [rbp+28h]; this
0x180030e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030e89  jmp     loc_180030DA4
0x180030e8e  mov     r9d, eax
0x180030e91  mov     edx, 70h ; 'p'
0x180030e96  jmp     short loc_180030E79
0x180030e98  mov     edx, 5Ch ; '\'
0x180030e9d  mov     ebx, 80070057h
0x180030ea2  mov     r9d, ebx
0x180030ea5  jmp     short loc_180030E79
0x180030ea7  mov     r9d, eax
0x180030eaa  mov     edx, 5Fh ; '_'
0x180030eaf  jmp     short loc_180030E79
0x180030eb1  mov     qword ptr [rdx+8], 0
0x180030eb9  mov     dword ptr [rdx], 0
0x180030ebf  jmp     short loc_180030E66
0x180030ec1  mov     r9d, eax
0x180030ec4  mov     edx, 73h ; 's'
0x180030ec9  jmp     short loc_180030E79
0x180030ecb  cmp     word ptr [rbp+pvt], 16h
0x180030ed0  jz      loc_180030D3D
0x180030ed6  mov     edx, 6Ah ; 'j'
0x180030edb  jmp     short loc_180030E9D
```
