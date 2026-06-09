# ArrayToSafeArray<uint>(uint const *,int,ushort,tagSAFEARRAY * *)

- ea: `0x1800c3cec`
- end: `0x1800c3eff`
- name: `??$ArrayToSafeArray@I@@YAJPEBIHGPEAPEAUtagSAFEARRAY@@@Z`
- size: `531`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c37b0`
- `0x1800c3950`
- `0x1800c3a50`
- `0x1800c3bc4`
- `0x1800c4870`
- `0x1801637b0`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800c3cec`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c3d6a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c3d6a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c3df5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c3df5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c3dd6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c3dd6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c3e20`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c3e20`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c3e75`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c3e75`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c3d90`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c3d90`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c3d28`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c3d28`

## string_xrefs

- `0x1800c3e3e`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c3eac`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c3d40`: `onecore\windows\accessibletech\Common\SafeArray.h`
- `0x1800c3e92`: `onecore\windows\accessibletech\Common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArrayToSafeArray<unsigned int>(__int64 a1, signed int a2, __int16 a3, SAFEARRAY **a4)
{
  SAFEARRAY *Vector; // rax
  const char *v8; // r9
  SAFEARRAY *v9; // rbx
  HRESULT Vartype; // eax
  int v11; // edi
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v14; // eax
  __int64 i; // r8
  const char *v16; // r9
  __int64 result; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+20h] [rbp-48h]
  SAFEARRAY *psa; // [rsp+28h] [rbp-40h]
  void *ppvData; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LONG plUbound; // [rsp+78h] [rbp+10h] BYREF
  int pvt; // [rsp+80h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+20h] BYREF

  LOWORD(pvt) = a3;
  try
  {
    *a4 = 0;
    if ( a2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
        (const char *)0x80070057LL,
        v20);
    Vector = SafeArrayCreateVector(0x13u, 0, a2);
    v9 = Vector;
    v21 = (int)Vector;
    if ( !Vector )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
        v8);
    ppvData = 0;
    psa = Vector;
    if ( SafeArrayGetDim(Vector) == 1 )
    {
      LOWORD(pvt) = 0;
      Vartype = SafeArrayGetVartype(psa, (VARTYPE *)&pvt);
      v11 = Vartype;
      if ( Vartype < 0 )
      {
        v18 = (unsigned int)Vartype;
        v19 = 95;
        goto LABEL_19;
      }
      if ( (_WORD)pvt == 19 )
      {
        plLbound = 0;
        plUbound = 0;
        LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
        v11 = LBound;
        if ( LBound < 0 )
        {
          v18 = (unsigned int)LBound;
          v19 = 111;
        }
        else
        {
          UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
          v11 = UBound;
          if ( UBound < 0 )
          {
            v18 = (unsigned int)UBound;
            v19 = 112;
          }
          else
          {
            v14 = SafeArrayAccessData(psa, &ppvData);
            v11 = v14;
            if ( v14 >= 0 )
            {
              v11 = 0;
LABEL_12:
              if ( v11 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                  (const char *)(unsigned int)v11,
                  v21);
              for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
                *((_DWORD *)ppvData + i) = *(_DWORD *)(a1 + 4 * i);
              SafeArrayUnaccessData(psa);
              *a4 = v9;
              return 0;
            }
            v18 = (unsigned int)v14;
            v19 = 115;
          }
        }
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)v18,
          v21);
        goto LABEL_12;
      }
      v19 = 106;
    }
    else
    {
      v19 = 92;
    }
    v11 = -2147024809;
    v18 = 2147942487LL;
    goto LABEL_19;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF8,
                           (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800c3cec  mov     word ptr [rsp+pvt], r8w
0x1800c3cf2  push    rbx
0x1800c3cf3  push    rsi
0x1800c3cf4  push    rdi
0x1800c3cf5  push    r14
0x1800c3cf7  push    r15
0x1800c3cf9  sub     rsp, 40h
0x1800c3cfd  mov     r14, r9
0x1800c3d00  mov     esi, edx
0x1800c3d02  mov     r15, rcx
0x1800c3d05  mov     qword ptr [r9], 0
0x1800c3d0c  mov     rcx, [rsp+68h]; this
0x1800c3d11  mov     eax, edx
0x1800c3d13  shr     eax, 1Fh
0x1800c3d16  test    al, al
0x1800c3d18  jnz     loc_1800C3E8C
0x1800c3d1e  mov     ecx, 13h; vt
0x1800c3d23  mov     r8d, edx; cElements
0x1800c3d26  xor     edx, edx; lLbound
0x1800c3d28  call    cs:__imp_SafeArrayCreateVector
0x1800c3d2e  mov     rbx, rax
0x1800c3d31  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800c3d36  mov     rcx, [rsp+68h]; this
0x1800c3d3b  test    rax, rax
0x1800c3d3e  jnz     short loc_1800C3D51
0x1800c3d40  lea     r8, aOnecoreWindows_120; "onecore\\windows\\accessibletech\\Commo"...
0x1800c3d47  mov     edx, 0EAh; void *
0x1800c3d4c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800c3d51  mov     [rsp+68h+var_38], 0
0x1800c3d59  mov     [rsp+68h+ppvData], 0
0x1800c3d62  mov     [rsp+68h+psa], rbx
0x1800c3d67  mov     rcx, rbx; psa
0x1800c3d6a  call    cs:__imp_SafeArrayGetDim
0x1800c3d70  cmp     eax, 1
0x1800c3d73  jnz     loc_1800C3EC2
0x1800c3d79  xor     eax, eax
0x1800c3d7b  mov     word ptr [rsp+68h+pvt], ax
0x1800c3d83  lea     rdx, [rsp+68h+pvt]; pvt
0x1800c3d8b  mov     rcx, [rsp+68h+psa]; psa
0x1800c3d90  call    cs:__imp_SafeArrayGetVartype
0x1800c3d96  mov     edi, eax
0x1800c3d98  test    eax, eax
0x1800c3d9a  js      loc_1800C3EA4
0x1800c3da0  mov     eax, 13h
0x1800c3da5  cmp     word ptr [rsp+68h+pvt], ax
0x1800c3dad  jnz     loc_1800C3EE5
0x1800c3db3  mov     [rsp+68h+plLbound], 0
0x1800c3dbe  mov     [rsp+68h+plUbound], 0
0x1800c3dc6  lea     r8, [rsp+68h+plLbound]; plLbound
0x1800c3dce  lea     edx, [rax-12h]; nDim
0x1800c3dd1  mov     rcx, [rsp+68h+psa]; psa
0x1800c3dd6  call    cs:__imp_SafeArrayGetLBound
0x1800c3ddc  mov     edi, eax
0x1800c3dde  test    eax, eax
0x1800c3de0  js      loc_1800C3EDB
0x1800c3de6  lea     r8, [rsp+68h+plUbound]; plUbound
0x1800c3deb  mov     edx, 1; nDim
0x1800c3df0  mov     rcx, [rsp+68h+psa]; psa
0x1800c3df5  call    cs:__imp_SafeArrayGetUBound
0x1800c3dfb  mov     edi, eax
0x1800c3dfd  test    eax, eax
0x1800c3dff  js      loc_1800C3ED1
0x1800c3e05  mov     eax, [rsp+68h+plUbound]
0x1800c3e09  sub     eax, [rsp+68h+plLbound]
0x1800c3e10  inc     eax
0x1800c3e12  mov     [rsp+68h+var_38], eax
0x1800c3e16  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800c3e1b  mov     rcx, [rsp+68h+psa]; psa
0x1800c3e20  call    cs:__imp_SafeArrayAccessData
0x1800c3e26  mov     edi, eax
0x1800c3e28  test    eax, eax
0x1800c3e2a  js      loc_1800C3EEC
0x1800c3e30  xor     edi, edi
0x1800c3e32  mov     rcx, [rsp+68h]; this
0x1800c3e37  test    edi, edi
0x1800c3e39  jns     short loc_1800C3E4F
0x1800c3e3b  mov     r9d, edi; char *
0x1800c3e3e  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c3e45  mov     edx, 43h ; 'C'; void *
0x1800c3e4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c3e4f  xor     r8d, r8d
0x1800c3e52  test    esi, esi
0x1800c3e54  jz      short loc_1800C3E6B
0x1800c3e56  mov     ecx, [r15+r8*4]
0x1800c3e5a  mov     rax, [rsp+68h+ppvData]
0x1800c3e5f  mov     [rax+r8*4], ecx
0x1800c3e63  inc     r8d
0x1800c3e66  cmp     r8d, esi
0x1800c3e69  jb      short loc_1800C3E56
0x1800c3e6b  mov     rcx, [rsp+68h+psa]; psa
0x1800c3e70  test    rcx, rcx
0x1800c3e73  jz      short loc_1800C3E7B
0x1800c3e75  call    cs:__imp_SafeArrayUnaccessData
0x1800c3e7b  mov     [r14], rbx
0x1800c3e7e  xor     eax, eax
0x1800c3e80  add     rsp, 40h
0x1800c3e84  pop     r15
0x1800c3e86  pop     r14
0x1800c3e88  pop     rdi
0x1800c3e89  pop     rsi
0x1800c3e8a  pop     rbx
0x1800c3e8b  retn
0x1800c3e8c  mov     r9d, 80070057h; char *
0x1800c3e92  lea     r8, aOnecoreWindows_120; "onecore\\windows\\accessibletech\\Commo"...
0x1800c3e99  mov     edx, 0E8h; void *
0x1800c3e9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c3ea4  mov     r9d, eax; char *
0x1800c3ea7  mov     edx, 5Fh ; '_'; void *
0x1800c3eac  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c3eb3  mov     rcx, [rsp+68h]; this
0x1800c3eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3ebd  jmp     loc_1800C3E32
0x1800c3ec2  mov     edx, 5Ch ; '\'
0x1800c3ec7  mov     edi, 80070057h
0x1800c3ecc  mov     r9d, edi
0x1800c3ecf  jmp     short loc_1800C3EAC
0x1800c3ed1  mov     r9d, eax
0x1800c3ed4  mov     edx, 70h ; 'p'
0x1800c3ed9  jmp     short loc_1800C3EAC
0x1800c3edb  mov     r9d, eax
0x1800c3ede  mov     edx, 6Fh ; 'o'
0x1800c3ee3  jmp     short loc_1800C3EAC
0x1800c3ee5  mov     edx, 6Ah ; 'j'
0x1800c3eea  jmp     short loc_1800C3EC7
0x1800c3eec  mov     r9d, eax
0x1800c3eef  mov     edx, 73h ; 's'
0x1800c3ef4  jmp     short loc_1800C3EAC
0x1800c3ef6  mov     eax, [rsp+68h+pvt]
0x1800c3efd  jmp     short loc_1800C3E80
```
