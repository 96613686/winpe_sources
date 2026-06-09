# ArrayToSafeArray<int>(int const *,int,ushort,tagSAFEARRAY * *)

- ea: `0x180034528`
- end: `0x180034753`
- name: `??$ArrayToSafeArray@H@@YAJPEBHHGPEAPEAUtagSAFEARRAY@@@Z`
- size: `555`
- prototype: ``
- caller_count: `24`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e7a8`
- `0x180010940`
- `0x180011e4c`
- `0x180011f7c`
- `0x180013ee4`
- `0x180026efc`
- `0x180032744`
- `0x18003331c`
- `0x1800337f0`
- `0x18005fe58`
- `0x180060050`
- `0x1800604c0`
- `0x1800c8578`
- `0x1800d89ec`
- `0x1800dfaf0`
- `0x180169760`
- `0x1801937cc`
- `0x1801bbdc0`
- `0x1801cc5d0`
- `0x1801d9c50`
- `0x180204840`
- `0x180240100`
- `0x18028b3a0`
- `0x180294f30`

## callees

- `0x18002f580`
- `0x180032724`
- `0x180034528`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180034599`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180034599`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180034626`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180034626`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180034607`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180034607`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180034651`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180034651`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800346b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800346b7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800345bf`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800345bf`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180034564`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180034564`

## string_xrefs

- `0x18003466f`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180034680`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800346d4`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800346ee`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArrayToSafeArray<int>(__int64 a1, signed int a2, __int16 a3, SAFEARRAY **a4)
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
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        (const char *)0x80070057LL,
        v20);
    Vector = SafeArrayCreateVector(3u, 0, a2);
    v9 = Vector;
    v21 = (int)Vector;
    if ( !Vector )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
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
      if ( (_WORD)pvt == 3 || (_WORD)pvt == 22 )
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
LABEL_11:
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
        goto LABEL_11;
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
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180034528  mov     word ptr [rsp+pvt], r8w
0x18003452e  push    rbx
0x18003452f  push    rsi
0x180034530  push    rdi
0x180034531  push    r14
0x180034533  push    r15
0x180034535  sub     rsp, 40h
0x180034539  mov     r14, r9
0x18003453c  mov     esi, edx
0x18003453e  mov     r15, rcx
0x180034541  mov     qword ptr [r9], 0
0x180034548  mov     rcx, [rsp+68h]; this
0x18003454d  mov     eax, edx
0x18003454f  shr     eax, 1Fh
0x180034552  test    al, al
0x180034554  jnz     loc_1800346CE
0x18003455a  mov     ecx, 3; vt
0x18003455f  mov     r8d, edx; cElements
0x180034562  xor     edx, edx; lLbound
0x180034564  call    cs:__imp_SafeArrayCreateVector
0x18003456a  mov     rbx, rax
0x18003456d  mov     qword ptr [rsp+68h+var_48], rax; int
0x180034572  mov     rcx, [rsp+68h]; this
0x180034577  test    rax, rax
0x18003457a  jz      loc_180034680
0x180034580  mov     [rsp+68h+var_38], 0
0x180034588  mov     [rsp+68h+ppvData], 0
0x180034591  mov     [rsp+68h+psa], rax
0x180034596  mov     rcx, rax; psa
0x180034599  call    cs:__imp_SafeArrayGetDim
0x18003459f  cmp     eax, 1
0x1800345a2  jnz     loc_18003470E
0x1800345a8  xor     eax, eax
0x1800345aa  mov     word ptr [rsp+68h+pvt], ax
0x1800345b2  lea     rdx, [rsp+68h+pvt]; pvt
0x1800345ba  mov     rcx, [rsp+68h+psa]; psa
0x1800345bf  call    cs:__imp_SafeArrayGetVartype
0x1800345c5  mov     edi, eax
0x1800345c7  test    eax, eax
0x1800345c9  js      loc_18003471D
0x1800345cf  mov     eax, 3
0x1800345d4  cmp     word ptr [rsp+68h+pvt], ax
0x1800345dc  jnz     loc_180034731
0x1800345e2  mov     [rsp+68h+plLbound], 0
0x1800345ed  mov     [rsp+68h+plUbound], 0
0x1800345f5  lea     r8, [rsp+68h+plLbound]; plLbound
0x1800345fd  mov     edx, 1; nDim
0x180034602  mov     rcx, [rsp+68h+psa]; psa
0x180034607  call    cs:__imp_SafeArrayGetLBound
0x18003460d  mov     edi, eax
0x18003460f  test    eax, eax
0x180034611  js      loc_1800346E6
0x180034617  lea     r8, [rsp+68h+plUbound]; plUbound
0x18003461c  mov     edx, 1; nDim
0x180034621  mov     rcx, [rsp+68h+psa]; psa
0x180034626  call    cs:__imp_SafeArrayGetUBound
0x18003462c  mov     edi, eax
0x18003462e  test    eax, eax
0x180034630  js      loc_180034704
0x180034636  mov     eax, [rsp+68h+plUbound]
0x18003463a  sub     eax, [rsp+68h+plLbound]
0x180034641  inc     eax
0x180034643  mov     [rsp+68h+var_38], eax
0x180034647  lea     rdx, [rsp+68h+ppvData]; ppvData
0x18003464c  mov     rcx, [rsp+68h+psa]; psa
0x180034651  call    cs:__imp_SafeArrayAccessData
0x180034657  mov     edi, eax
0x180034659  test    eax, eax
0x18003465b  js      loc_180034727
0x180034661  xor     edi, edi
0x180034663  mov     rcx, [rsp+68h]; this
0x180034668  test    edi, edi
0x18003466a  jns     short loc_180034691
0x18003466c  mov     r9d, edi; char *
0x18003466f  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x180034676  mov     edx, 43h ; 'C'; void *
0x18003467b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034680  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x180034687  mov     edx, 0EAh; void *
0x18003468c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180034691  xor     r8d, r8d
0x180034694  test    esi, esi
0x180034696  jz      short loc_1800346AD
0x180034698  mov     ecx, [r15+r8*4]
0x18003469c  mov     rax, [rsp+68h+ppvData]
0x1800346a1  mov     [rax+r8*4], ecx
0x1800346a5  inc     r8d
0x1800346a8  cmp     r8d, esi
0x1800346ab  jb      short loc_180034698
0x1800346ad  mov     rcx, [rsp+68h+psa]; psa
0x1800346b2  test    rcx, rcx
0x1800346b5  jz      short loc_1800346BD
0x1800346b7  call    cs:__imp_SafeArrayUnaccessData
0x1800346bd  mov     [r14], rbx
0x1800346c0  xor     eax, eax
0x1800346c2  add     rsp, 40h
0x1800346c6  pop     r15
0x1800346c8  pop     r14
0x1800346ca  pop     rdi
0x1800346cb  pop     rsi
0x1800346cc  pop     rbx
0x1800346cd  retn
0x1800346ce  mov     r9d, 80070057h; char *
0x1800346d4  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800346db  mov     edx, 0E8h; void *
0x1800346e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800346e6  mov     r9d, eax; char *
0x1800346e9  mov     edx, 6Fh ; 'o'; void *
0x1800346ee  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800346f5  mov     rcx, [rsp+68h]; this
0x1800346fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346ff  jmp     loc_180034663
0x180034704  mov     r9d, eax
0x180034707  mov     edx, 70h ; 'p'
0x18003470c  jmp     short loc_1800346EE
0x18003470e  mov     edx, 5Ch ; '\'
0x180034713  mov     edi, 80070057h
0x180034718  mov     r9d, edi
0x18003471b  jmp     short loc_1800346EE
0x18003471d  mov     r9d, eax
0x180034720  mov     edx, 5Fh ; '_'
0x180034725  jmp     short loc_1800346EE
0x180034727  mov     r9d, eax
0x18003472a  mov     edx, 73h ; 's'
0x18003472f  jmp     short loc_1800346EE
0x180034731  cmp     word ptr [rsp+68h+pvt], 16h
0x18003473a  jz      loc_1800345E2
0x180034740  mov     edx, 6Ah ; 'j'
0x180034745  jmp     short loc_180034713
0x180034747  mov     eax, [rsp+68h+pvt]
0x18003474e  jmp     loc_1800346C2
```
