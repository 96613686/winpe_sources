# SafeArrayToArray<int>(tagSAFEARRAY *,int * *,int *,ushort)

- ea: `0x1800c4970`
- end: `0x1800c4b94`
- name: `??$SafeArrayToArray@H@@YAJPEAUtagSAFEARRAY@@PEAPEAHPEAHG@Z`
- size: `548`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023028`
- `0x180060050`
- `0x1800c3f08`
- `0x1800caef0`
- `0x1800d12e4`
- `0x1801432a0`
- `0x18026d1c0`

## callees

- `0x18002f580`
- `0x1800c4970`
- `0x1801e88a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c49ad`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c49ad`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c4a19`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c4a19`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c49fc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c49fc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4a3c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4a3c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4aad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4aec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4b4c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4aad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4aec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4b4c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c49c9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c49c9`

## string_xrefs

- `0x1800c4acc`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c4b1f`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c4b2f`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
__int64 __fastcall SafeArrayToArray<int>(SAFEARRAY *a1, _QWORD *a2, unsigned int *a3, VARTYPE a4)
{
  HRESULT Vartype; // eax
  unsigned int v7; // ebx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned __int64 v10; // rax
  _DWORD *v11; // rax
  unsigned int v12; // edx
  unsigned int i; // ecx
  __int64 v14; // rdx
  SAFEARRAY *v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  LONG plUbound; // [rsp+20h] [rbp-20h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-1Ch] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-18h]
  unsigned int v22; // [rsp+30h] [rbp-10h]
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  VARTYPE pvt; // [rsp+78h] [rbp+38h] BYREF

  pvt = a4;
  psa = 0;
  v22 = 0;
  ppvData = 0;
  if ( !a1 )
  {
    v18 = 2147942487LL;
    v17 = 87;
    v7 = -2147024809;
    goto LABEL_23;
  }
  psa = a1;
  if ( SafeArrayGetDim(a1) != 1 )
  {
    v18 = 2147942487LL;
    v17 = 92;
    v7 = -2147024809;
    goto LABEL_23;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v7 = Vartype;
  if ( Vartype < 0 )
  {
    v17 = 95;
    v18 = (unsigned int)Vartype;
    goto LABEL_23;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v18 = 2147942487LL;
    v17 = 106;
    v7 = -2147024809;
    goto LABEL_23;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
  v7 = LBound;
  if ( LBound < 0 )
  {
    v17 = 111;
LABEL_20:
    v18 = (unsigned int)LBound;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v18,
      plUbound);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v7,
      plUbound);
    if ( psa )
      SafeArrayUnaccessData(psa);
    return v7;
  }
  UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
  v7 = UBound;
  if ( UBound < 0 )
  {
    v17 = 112;
    v18 = (unsigned int)UBound;
    goto LABEL_23;
  }
  v22 = plUbound - plLbound + 1;
  LBound = SafeArrayAccessData(psa, &ppvData);
  v7 = LBound;
  if ( LBound < 0 )
  {
    v17 = 115;
    goto LABEL_20;
  }
  v10 = 4LL * v22;
  if ( !is_mul_ok(v22, 4u) )
    v10 = -1;
  v11 = operator new[](v10, (const struct std::nothrow_t *)std::nothrow);
  if ( v11 )
  {
    v12 = v22;
    for ( i = 0; i < v22; v12 = v22 )
    {
      v14 = i++;
      v11[v14] = *((_DWORD *)ppvData + v14);
    }
    v15 = psa;
    *a3 = v12;
    *a2 = v11;
    if ( v15 )
      SafeArrayUnaccessData(v15);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x8007000ELL,
      plUbound);
    if ( psa )
      SafeArrayUnaccessData(psa);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800c4970  mov     [rsp-18h+arg_0], rbx
0x1800c4975  mov     [rsp-18h+arg_8], rsi
0x1800c497a  mov     [rsp-18h+pvt], r9w
0x1800c4980  push    rbp
0x1800c4981  push    rdi
0x1800c4982  push    r14
0x1800c4984  mov     rbp, rsp
0x1800c4987  sub     rsp, 40h
0x1800c498b  xor     r14d, r14d
0x1800c498e  mov     rdi, r8
0x1800c4991  mov     [rbp+psa], r14
0x1800c4995  mov     rsi, rdx
0x1800c4998  mov     [rbp+var_10], r14d
0x1800c499c  mov     [rbp+ppvData], r14
0x1800c49a0  test    rcx, rcx
0x1800c49a3  jz      loc_1800C4B84
0x1800c49a9  mov     [rbp+psa], rcx
0x1800c49ad  call    cs:__imp_SafeArrayGetDim
0x1800c49b3  cmp     eax, 1
0x1800c49b6  jnz     loc_1800C4B0D
0x1800c49bc  mov     rcx, [rbp+psa]; psa
0x1800c49c0  lea     rdx, [rbp+pvt]; pvt
0x1800c49c4  mov     [rbp+pvt], r14w
0x1800c49c9  call    cs:__imp_SafeArrayGetVartype
0x1800c49cf  mov     ebx, eax
0x1800c49d1  test    eax, eax
0x1800c49d3  js      loc_1800C4B59
0x1800c49d9  movzx   eax, [rbp+pvt]
0x1800c49dd  cmp     ax, 3
0x1800c49e1  jnz     loc_1800C4B6A
0x1800c49e7  mov     rcx, [rbp+psa]; psa
0x1800c49eb  lea     r8, [rbp+plLbound]; plLbound
0x1800c49ef  mov     edx, 1; nDim
0x1800c49f4  mov     [rbp+plLbound], r14d
0x1800c49f8  mov     [rbp+plUbound], r14d
0x1800c49fc  call    cs:__imp_SafeArrayGetLBound
0x1800c4a02  mov     ebx, eax
0x1800c4a04  test    eax, eax
0x1800c4a06  js      loc_1800C4AF9
0x1800c4a0c  mov     rcx, [rbp+psa]; psa
0x1800c4a10  lea     r8, [rbp+plUbound]; plUbound
0x1800c4a14  mov     edx, 1; nDim
0x1800c4a19  call    cs:__imp_SafeArrayGetUBound
0x1800c4a1f  mov     ebx, eax
0x1800c4a21  test    eax, eax
0x1800c4a23  js      loc_1800C4B03
0x1800c4a29  mov     eax, [rbp+plUbound]
0x1800c4a2c  lea     rdx, [rbp+ppvData]; ppvData
0x1800c4a30  sub     eax, [rbp+plLbound]
0x1800c4a33  mov     rcx, [rbp+psa]; psa
0x1800c4a37  inc     eax
0x1800c4a39  mov     [rbp+var_10], eax
0x1800c4a3c  call    cs:__imp_SafeArrayAccessData
0x1800c4a42  mov     ebx, eax
0x1800c4a44  test    eax, eax
0x1800c4a46  js      loc_1800C4B63
0x1800c4a4c  mov     ecx, [rbp+var_10]
0x1800c4a4f  mov     eax, 4
0x1800c4a54  mul     rcx
0x1800c4a57  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c4a5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c4a65  cmovb   rax, rcx
0x1800c4a69  mov     rcx, rax; unsigned __int64
0x1800c4a6c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c4a71  test    rax, rax
0x1800c4a74  jz      short loc_1800C4AC8
0x1800c4a76  mov     edx, [rbp+var_10]
0x1800c4a79  mov     ecx, r14d
0x1800c4a7c  test    edx, edx
0x1800c4a7e  jz      short loc_1800C4A9F
0x1800c4a80  mov     edx, ecx
0x1800c4a82  inc     ecx
0x1800c4a84  lea     r9, ds:0[rdx*4]
0x1800c4a8c  mov     rdx, [rbp+ppvData]
0x1800c4a90  mov     r8d, [r9+rdx]
0x1800c4a94  mov     [r9+rax], r8d
0x1800c4a98  mov     edx, [rbp+var_10]
0x1800c4a9b  cmp     ecx, edx
0x1800c4a9d  jb      short loc_1800C4A80
0x1800c4a9f  mov     rcx, [rbp+psa]; psa
0x1800c4aa3  mov     [rdi], edx
0x1800c4aa5  mov     [rsi], rax
0x1800c4aa8  test    rcx, rcx
0x1800c4aab  jz      short loc_1800C4AB3
0x1800c4aad  call    cs:__imp_SafeArrayUnaccessData
0x1800c4ab3  xor     eax, eax
0x1800c4ab5  mov     rbx, [rsp+40h+arg_0]
0x1800c4aba  mov     rsi, [rsp+40h+arg_8]
0x1800c4abf  add     rsp, 40h
0x1800c4ac3  pop     r14
0x1800c4ac5  pop     rdi
0x1800c4ac6  pop     rbp
0x1800c4ac7  retn
0x1800c4ac8  mov     rcx, [rbp+18h]; this
0x1800c4acc  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c4ad3  mov     r9d, 8007000Eh; char *
0x1800c4ad9  mov     edx, 0A2h; void *
0x1800c4ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4ae3  mov     rcx, [rbp+psa]; psa
0x1800c4ae7  test    rcx, rcx
0x1800c4aea  jz      short loc_1800C4AF2
0x1800c4aec  call    cs:__imp_SafeArrayUnaccessData
0x1800c4af2  mov     eax, 8007000Eh
0x1800c4af7  jmp     short loc_1800C4AB5
0x1800c4af9  mov     edx, 6Fh ; 'o'
0x1800c4afe  mov     r9d, eax
0x1800c4b01  jmp     short loc_1800C4B1B
0x1800c4b03  mov     edx, 70h ; 'p'
0x1800c4b08  mov     r9d, eax
0x1800c4b0b  jmp     short loc_1800C4B1B
0x1800c4b0d  mov     r9d, 80070057h; char *
0x1800c4b13  mov     edx, 5Ch ; '\'; void *
0x1800c4b18  mov     ebx, r9d
0x1800c4b1b  mov     rcx, [rbp+18h]; this
0x1800c4b1f  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c4b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4b2b  mov     rcx, [rbp+18h]; this
0x1800c4b2f  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c4b36  mov     r9d, ebx; char *
0x1800c4b39  mov     edx, 9Fh; void *
0x1800c4b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4b43  mov     rcx, [rbp+psa]; psa
0x1800c4b47  test    rcx, rcx
0x1800c4b4a  jz      short loc_1800C4B52
0x1800c4b4c  call    cs:__imp_SafeArrayUnaccessData
0x1800c4b52  mov     eax, ebx
0x1800c4b54  jmp     loc_1800C4AB5
0x1800c4b59  mov     edx, 5Fh ; '_'
0x1800c4b5e  mov     r9d, eax
0x1800c4b61  jmp     short loc_1800C4B1B
0x1800c4b63  mov     edx, 73h ; 's'
0x1800c4b68  jmp     short loc_1800C4AFE
0x1800c4b6a  cmp     ax, 16h
0x1800c4b6e  jz      loc_1800C49E7
0x1800c4b74  mov     r9d, 80070057h
0x1800c4b7a  mov     edx, 6Ah ; 'j'
0x1800c4b7f  mov     ebx, r9d
0x1800c4b82  jmp     short loc_1800C4B1B
0x1800c4b84  mov     r9d, 80070057h
0x1800c4b8a  mov     edx, 57h ; 'W'
0x1800c4b8f  mov     ebx, r9d
0x1800c4b92  jmp     short loc_1800C4B1B
```
