# SafeArrayAccessor<int>::Access(tagSAFEARRAY *,ushort)

- ea: `0x18002f2f0`
- end: `0x18002f51e`
- name: `?Access@?$SafeArrayAccessor@H@@QEAAJPEAUtagSAFEARRAY@@G@Z`
- size: `558`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005fe58`
- `0x180061b50`
- `0x180091bf4`
- `0x1800bf960`
- `0x1800c8578`
- `0x1800ca400`
- `0x180156c48`
- `0x18016e9d0`
- `0x18017a36c`
- `0x1801a2264`
- `0x180204984`

## callees

- `0x18002f2f0`
- `0x18002f580`
- `0x1801b2924`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002f317`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002f317`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002f38c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002f38c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002f373`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002f373`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002f3b0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002f3b0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18002f33f`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18002f33f`

## string_xrefs

- `0x18002f3d7`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f3fe`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f429`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f454`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f47b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f4a6`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f4db`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18002f50c`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
__int64 __fastcall SafeArrayAccessor<int>::Access(__int64 a1, SAFEARRAY *a2, VARTYPE a3, const char *a4)
{
  int v4; // edi
  SAFEARRAY *v6; // rcx
  HRESULT Vartype; // eax
  unsigned int v8; // edi
  SAFEARRAY *v9; // rcx
  HRESULT LBound; // eax
  unsigned int v11; // edi
  HRESULT UBound; // eax
  unsigned int v13; // edi
  SAFEARRAY *v14; // rcx
  HRESULT v15; // eax
  unsigned int v16; // ebx
  int v18; // [rsp+20h] [rbp-18h]
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LONG plUbound; // [rsp+40h] [rbp+8h] BYREF
  VARTYPE pvt; // [rsp+50h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+58h] [rbp+20h] BYREF

  pvt = a3;
  if ( *(_QWORD *)a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      a4);
  if ( a2 )
  {
    *(_QWORD *)a1 = a2;
    if ( SafeArrayGetDim(a2) == 1 )
    {
      v6 = *(SAFEARRAY **)a1;
      pvt = 0;
      v19 = v4;
      Vartype = SafeArrayGetVartype(v6, &pvt);
      v8 = Vartype;
      if ( Vartype < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)(unsigned int)Vartype,
          v19);
        return v8;
      }
      else if ( pvt == 3 || pvt == 22 )
      {
        v9 = *(SAFEARRAY **)a1;
        plLbound = 0;
        plUbound = 0;
        LBound = SafeArrayGetLBound(v9, 1u, &plLbound);
        v11 = LBound;
        if ( LBound < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
            (const char *)(unsigned int)LBound,
            v19);
          return v11;
        }
        else
        {
          UBound = SafeArrayGetUBound(*(SAFEARRAY **)a1, 1u, &plUbound);
          v13 = UBound;
          if ( UBound < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x70,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
              (const char *)(unsigned int)UBound,
              v19);
            return v13;
          }
          else
          {
            v14 = *(SAFEARRAY **)a1;
            *(_DWORD *)(a1 + 8) = plUbound - plLbound + 1;
            v15 = SafeArrayAccessData(v14, (void **)(a1 + 16));
            v16 = v15;
            if ( v15 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x73,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)v15,
                v19);
              return v16;
            }
            else
            {
              return 0;
            }
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)0x80070057LL,
          v19);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        (const char *)0x80070057LL,
        v18);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002f2f0  mov     [rsp+pvt], r8w
0x18002f2f6  push    rbx
0x18002f2f7  sub     rsp, 30h
0x18002f2fb  cmp     qword ptr [rcx], 0
0x18002f2ff  mov     rbx, rcx
0x18002f302  jnz     loc_18002F507
0x18002f308  test    rdx, rdx
0x18002f30b  jz      loc_18002F3D2
0x18002f311  mov     [rcx], rdx
0x18002f314  mov     rcx, rdx; psa
0x18002f317  call    cs:__imp_SafeArrayGetDim
0x18002f31d  cmp     eax, 1
0x18002f320  jnz     loc_18002F44F
0x18002f326  mov     rcx, [rbx]; psa
0x18002f329  lea     rdx, [rsp+38h+pvt]; pvt
0x18002f32e  mov     [rsp+38h+var_10], rsi
0x18002f333  xor     esi, esi
0x18002f335  mov     [rsp+38h+pvt], si
0x18002f33a  mov     qword ptr [rsp+38h+var_18], rdi; int
0x18002f33f  call    cs:__imp_SafeArrayGetVartype
0x18002f345  mov     edi, eax
0x18002f347  test    eax, eax
0x18002f349  js      loc_18002F476
0x18002f34f  movzx   eax, [rsp+38h+pvt]
0x18002f354  cmp     ax, 3
0x18002f358  jnz     loc_18002F4CC
0x18002f35e  mov     rcx, [rbx]; psa
0x18002f361  lea     r8, [rsp+38h+plLbound]; plLbound
0x18002f366  mov     edx, 1; nDim
0x18002f36b  mov     [rsp+38h+plLbound], esi
0x18002f36f  mov     [rsp+38h+plUbound], esi
0x18002f373  call    cs:__imp_SafeArrayGetLBound
0x18002f379  mov     edi, eax
0x18002f37b  test    eax, eax
0x18002f37d  js      short loc_18002F3F9
0x18002f37f  mov     rcx, [rbx]; psa
0x18002f382  lea     r8, [rsp+38h+plUbound]; plUbound
0x18002f387  mov     edx, 1; nDim
0x18002f38c  call    cs:__imp_SafeArrayGetUBound
0x18002f392  mov     edi, eax
0x18002f394  test    eax, eax
0x18002f396  js      loc_18002F424
0x18002f39c  mov     eax, [rsp+38h+plUbound]
0x18002f3a0  lea     rdx, [rbx+10h]; ppvData
0x18002f3a4  sub     eax, [rsp+38h+plLbound]
0x18002f3a8  mov     rcx, [rbx]; psa
0x18002f3ab  inc     eax
0x18002f3ad  mov     [rbx+8], eax
0x18002f3b0  call    cs:__imp_SafeArrayAccessData
0x18002f3b6  mov     ebx, eax
0x18002f3b8  test    eax, eax
0x18002f3ba  js      loc_18002F4A1
0x18002f3c0  mov     rsi, [rsp+38h+var_10]
0x18002f3c5  xor     eax, eax
0x18002f3c7  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f3cc  add     rsp, 30h
0x18002f3d0  pop     rbx
0x18002f3d1  retn
0x18002f3d2  mov     rcx, [rsp+38h]; this
0x18002f3d7  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f3de  mov     r9d, 80070057h; char *
0x18002f3e4  mov     edx, 57h ; 'W'; void *
0x18002f3e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f3ee  mov     eax, 80070057h
0x18002f3f3  add     rsp, 30h
0x18002f3f7  pop     rbx
0x18002f3f8  retn
0x18002f3f9  mov     rcx, [rsp+38h]; this
0x18002f3fe  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f405  mov     r9d, edi; char *
0x18002f408  mov     edx, 6Fh ; 'o'; void *
0x18002f40d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f412  mov     rsi, [rsp+38h+var_10]
0x18002f417  mov     eax, edi
0x18002f419  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f41e  add     rsp, 30h
0x18002f422  pop     rbx
0x18002f423  retn
0x18002f424  mov     rcx, [rsp+38h]; this
0x18002f429  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f430  mov     r9d, edi; char *
0x18002f433  mov     edx, 70h ; 'p'; void *
0x18002f438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f43d  mov     rsi, [rsp+38h+var_10]
0x18002f442  mov     eax, edi
0x18002f444  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f449  add     rsp, 30h
0x18002f44d  pop     rbx
0x18002f44e  retn
0x18002f44f  mov     rcx, [rsp+38h]; this
0x18002f454  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f45b  mov     r9d, 80070057h; char *
0x18002f461  mov     edx, 5Ch ; '\'; void *
0x18002f466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f46b  mov     eax, 80070057h
0x18002f470  add     rsp, 30h
0x18002f474  pop     rbx
0x18002f475  retn
0x18002f476  mov     rcx, [rsp+38h]; this
0x18002f47b  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f482  mov     r9d, edi; char *
0x18002f485  mov     edx, 5Fh ; '_'; void *
0x18002f48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f48f  mov     rsi, [rsp+38h+var_10]
0x18002f494  mov     eax, edi
0x18002f496  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f49b  add     rsp, 30h
0x18002f49f  pop     rbx
0x18002f4a0  retn
0x18002f4a1  mov     rcx, [rsp+38h]; this
0x18002f4a6  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f4ad  mov     r9d, ebx; char *
0x18002f4b0  mov     edx, 73h ; 's'; void *
0x18002f4b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f4ba  mov     rsi, [rsp+38h+var_10]
0x18002f4bf  mov     eax, ebx
0x18002f4c1  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f4c6  add     rsp, 30h
0x18002f4ca  pop     rbx
0x18002f4cb  retn
0x18002f4cc  cmp     ax, 16h
0x18002f4d0  jz      loc_18002F35E
0x18002f4d6  mov     rcx, [rsp+38h]; this
0x18002f4db  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f4e2  mov     r9d, 80070057h; char *
0x18002f4e8  mov     edx, 6Ah ; 'j'; void *
0x18002f4ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f4f2  mov     rsi, [rsp+38h+var_10]
0x18002f4f7  mov     eax, 80070057h
0x18002f4fc  mov     rdi, qword ptr [rsp+38h+var_18]
0x18002f501  add     rsp, 30h
0x18002f505  pop     rbx
0x18002f506  retn
0x18002f507  mov     rcx, [rsp+38h]; this
0x18002f50c  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18002f513  mov     edx, 55h ; 'U'; void *
0x18002f518  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
