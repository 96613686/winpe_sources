# CWebWizardPage::_GetSignInSignUpProperties(void)

- ea: `0x18003e33c`
- end: `0x18003e5b9`
- name: `?_GetSignInSignUpProperties@CWebWizardPage@@AEAAJXZ`
- size: `637`
- prototype: `__int64 __fastcall(CWebWizardPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d380`

## callees

- `0x18003e0f8`
- `0x18003e33c`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003e350`
- `OLEAUT32!__imp_VariantInit` at `0x18003e3f3`
- `OLEAUT32!__imp_VariantInit` at `0x18003e487`
- `OLEAUT32!__imp_VariantInit` at `0x18003e51b`
- `OLEAUT32!__imp_VariantInit` at `0x18003e350`
- `OLEAUT32!__imp_VariantInit` at `0x18003e3f3`
- `OLEAUT32!__imp_VariantInit` at `0x18003e487`
- `OLEAUT32!__imp_VariantInit` at `0x18003e51b`
- `OLEAUT32!__imp_VariantClear` at `0x18003e475`
- `OLEAUT32!__imp_VariantClear` at `0x18003e509`
- `OLEAUT32!__imp_VariantClear` at `0x18003e59d`
- `OLEAUT32!__imp_VariantClear` at `0x18003e5a7`
- `OLEAUT32!__imp_VariantClear` at `0x18003e475`
- `OLEAUT32!__imp_VariantClear` at `0x18003e509`
- `OLEAUT32!__imp_VariantClear` at `0x18003e59d`
- `OLEAUT32!__imp_VariantClear` at `0x18003e5a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e3b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e449`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e4dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e571`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e3b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e449`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e4dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e571`

## pseudocode

```c
__int64 __fastcall CWebWizardPage::_GetSignInSignUpProperties(CWebWizardPage *this)
{
  __int64 v2; // rcx
  int AuthenticationBuffer; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  VARIANTARG v8; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v2 = *(_QWORD *)(*((_QWORD *)this + 15) + 376LL);
  if ( !v2
    || (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v2 + 24LL))(
         v2,
         L"Username",
         &pvarg,
         0) < 0 )
  {
    goto LABEL_7;
  }
  if ( pvarg.vt != 8 )
  {
    AuthenticationBuffer = -2147418113;
    goto LABEL_29;
  }
  if ( CompareStringOrdinal(pvarg.bstrVal, -1, &Class, -1, 1) == 2
    || (AuthenticationBuffer = (*(__int64 (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 14) + 32LL))(
                                 *((_QWORD *)this + 14),
                                 pvarg.llVal),
        AuthenticationBuffer >= 0) )
  {
LABEL_7:
    AuthenticationBuffer = CWebWizardPage::_GetAuthenticationBuffer(this, 1);
    if ( AuthenticationBuffer >= 0 )
    {
      VariantInit(&v8);
      v4 = *(_QWORD *)(*((_QWORD *)this + 15) + 376LL);
      if ( v4
        && (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v4 + 24LL))(
             v4,
             L"UserTileURL",
             &v8,
             0) >= 0 )
      {
        if ( v8.vt == 8 )
        {
          AuthenticationBuffer = 0;
          if ( CompareStringOrdinal(v8.bstrVal, -1, &Class, -1, 1) != 2 )
            AuthenticationBuffer = (*(__int64 (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 14) + 56LL))(
                                     *((_QWORD *)this + 14),
                                     v8.llVal);
        }
        else
        {
          AuthenticationBuffer = -2147418113;
        }
      }
      VariantClear(&v8);
      if ( AuthenticationBuffer >= 0 )
      {
        VariantInit(&v8);
        v5 = *(_QWORD *)(*((_QWORD *)this + 15) + 376LL);
        if ( v5
          && (*(int (__fastcall **)(__int64, const WCHAR *, VARIANTARG *, _QWORD))(*(_QWORD *)v5 + 24LL))(
               v5,
               L"FirstName",
               &v8,
               0) >= 0 )
        {
          if ( v8.vt == 8 )
          {
            AuthenticationBuffer = 0;
            if ( CompareStringOrdinal(v8.bstrVal, -1, &Class, -1, 1) != 2 )
              AuthenticationBuffer = (*(__int64 (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 14) + 64LL))(
                                       *((_QWORD *)this + 14),
                                       v8.llVal);
          }
          else
          {
            AuthenticationBuffer = -2147418113;
          }
        }
        VariantClear(&v8);
        if ( AuthenticationBuffer >= 0 )
        {
          VariantInit(&v8);
          v6 = *(_QWORD *)(*((_QWORD *)this + 15) + 376LL);
          if ( v6
            && (*(int (__fastcall **)(__int64, const WCHAR *, VARIANTARG *, _QWORD))(*(_QWORD *)v6 + 24LL))(
                 v6,
                 L"LastName",
                 &v8,
                 0) >= 0 )
          {
            if ( v8.vt == 8 )
            {
              AuthenticationBuffer = 0;
              if ( CompareStringOrdinal(v8.bstrVal, -1, &Class, -1, 1) != 2 )
                AuthenticationBuffer = (*(__int64 (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 14) + 72LL))(
                                         *((_QWORD *)this + 14),
                                         v8.llVal);
            }
            else
            {
              AuthenticationBuffer = -2147418113;
            }
          }
          VariantClear(&v8);
        }
      }
    }
  }
LABEL_29:
  VariantClear(&pvarg);
  return (unsigned int)AuthenticationBuffer;
}

```

## disassembly

```asm
0x18003e33c  push    rbp
0x18003e33e  push    rbx
0x18003e33f  push    rsi
0x18003e340  push    r14
0x18003e342  mov     rbp, rsp
0x18003e345  sub     rsp, 68h
0x18003e349  mov     rsi, rcx
0x18003e34c  lea     rcx, [rbp+pvarg]; pvarg
0x18003e350  call    cs:__imp_VariantInit
0x18003e356  mov     rax, [rsi+78h]
0x18003e35a  or      r14d, 0FFFFFFFFh
0x18003e35e  mov     rcx, [rax+178h]
0x18003e365  test    rcx, rcx
0x18003e368  jz      short loc_18003E3DB
0x18003e36a  mov     rax, [rcx]
0x18003e36d  lea     r8, [rbp+pvarg]
0x18003e371  xor     r9d, r9d
0x18003e374  lea     rdx, aUsername_0; "Username"
0x18003e37b  mov     rax, [rax+18h]
0x18003e37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e384  test    eax, eax
0x18003e386  js      short loc_18003E3DB
0x18003e388  cmp     word ptr [rbp+pvarg], 8
0x18003e38d  jz      short loc_18003E399
0x18003e38f  mov     ebx, 8000FFFFh
0x18003e394  jmp     loc_18003E5A3
0x18003e399  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x18003e39d  lea     r8, Class; lpString2
0x18003e3a4  mov     r9d, r14d; cchCount2
0x18003e3a7  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003e3af  mov     edx, r14d; cchCount1
0x18003e3b2  call    cs:__imp_CompareStringOrdinal
0x18003e3b8  cmp     eax, 2
0x18003e3bb  jz      short loc_18003E3DB
0x18003e3bd  mov     rcx, [rsi+70h]
0x18003e3c1  mov     rdx, qword ptr [rbp+pvarg+8]
0x18003e3c5  mov     rax, [rcx]
0x18003e3c8  mov     rax, [rax+20h]
0x18003e3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3d1  mov     ebx, eax
0x18003e3d3  test    eax, eax
0x18003e3d5  js      loc_18003E5A3
0x18003e3db  mov     dl, 1; bool
0x18003e3dd  mov     rcx, rsi; this
0x18003e3e0  call    ?_GetAuthenticationBuffer@CWebWizardPage@@AEAAJ_N@Z; CWebWizardPage::_GetAuthenticationBuffer(bool)
0x18003e3e5  mov     ebx, eax
0x18003e3e7  test    eax, eax
0x18003e3e9  js      loc_18003E5A3
0x18003e3ef  lea     rcx, [rbp+var_38]; pvarg
0x18003e3f3  call    cs:__imp_VariantInit
0x18003e3f9  mov     rax, [rsi+78h]
0x18003e3fd  mov     rcx, [rax+178h]
0x18003e404  test    rcx, rcx
0x18003e407  jz      short loc_18003E471
0x18003e409  mov     rax, [rcx]
0x18003e40c  lea     r8, [rbp+var_38]
0x18003e410  xor     r9d, r9d
0x18003e413  lea     rdx, aUsertileurl; "UserTileURL"
0x18003e41a  mov     rax, [rax+18h]
0x18003e41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e423  test    eax, eax
0x18003e425  js      short loc_18003E471
0x18003e427  cmp     word ptr [rbp+var_38], 8
0x18003e42c  jnz     short loc_18003E46C
0x18003e42e  mov     rcx, qword ptr [rbp+var_38+8]; lpString1
0x18003e432  lea     r8, Class; lpString2
0x18003e439  mov     r9d, r14d; cchCount2
0x18003e43c  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003e444  mov     edx, r14d; cchCount1
0x18003e447  xor     ebx, ebx
0x18003e449  call    cs:__imp_CompareStringOrdinal
0x18003e44f  cmp     eax, 2
0x18003e452  jz      short loc_18003E471
0x18003e454  mov     rcx, [rsi+70h]
0x18003e458  mov     rdx, qword ptr [rbp+var_38+8]
0x18003e45c  mov     rax, [rcx]
0x18003e45f  mov     rax, [rax+38h]
0x18003e463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e468  mov     ebx, eax
0x18003e46a  jmp     short loc_18003E471
0x18003e46c  mov     ebx, 8000FFFFh
0x18003e471  lea     rcx, [rbp+var_38]; pvarg
0x18003e475  call    cs:__imp_VariantClear
0x18003e47b  test    ebx, ebx
0x18003e47d  js      loc_18003E5A3
0x18003e483  lea     rcx, [rbp+var_38]; pvarg
0x18003e487  call    cs:__imp_VariantInit
0x18003e48d  mov     rax, [rsi+78h]
0x18003e491  mov     rcx, [rax+178h]
0x18003e498  test    rcx, rcx
0x18003e49b  jz      short loc_18003E505
0x18003e49d  mov     rax, [rcx]
0x18003e4a0  lea     r8, [rbp+var_38]
0x18003e4a4  xor     r9d, r9d
0x18003e4a7  lea     rdx, aFirstname; "FirstName"
0x18003e4ae  mov     rax, [rax+18h]
0x18003e4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4b7  test    eax, eax
0x18003e4b9  js      short loc_18003E505
0x18003e4bb  cmp     word ptr [rbp+var_38], 8
0x18003e4c0  jnz     short loc_18003E500
0x18003e4c2  mov     rcx, qword ptr [rbp+var_38+8]; lpString1
0x18003e4c6  lea     r8, Class; lpString2
0x18003e4cd  mov     r9d, r14d; cchCount2
0x18003e4d0  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003e4d8  mov     edx, r14d; cchCount1
0x18003e4db  xor     ebx, ebx
0x18003e4dd  call    cs:__imp_CompareStringOrdinal
0x18003e4e3  cmp     eax, 2
0x18003e4e6  jz      short loc_18003E505
0x18003e4e8  mov     rcx, [rsi+70h]
0x18003e4ec  mov     rdx, qword ptr [rbp+var_38+8]
0x18003e4f0  mov     rax, [rcx]
0x18003e4f3  mov     rax, [rax+40h]
0x18003e4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4fc  mov     ebx, eax
0x18003e4fe  jmp     short loc_18003E505
0x18003e500  mov     ebx, 8000FFFFh
0x18003e505  lea     rcx, [rbp+var_38]; pvarg
0x18003e509  call    cs:__imp_VariantClear
0x18003e50f  test    ebx, ebx
0x18003e511  js      loc_18003E5A3
0x18003e517  lea     rcx, [rbp+var_38]; pvarg
0x18003e51b  call    cs:__imp_VariantInit
0x18003e521  mov     rax, [rsi+78h]
0x18003e525  mov     rcx, [rax+178h]
0x18003e52c  test    rcx, rcx
0x18003e52f  jz      short loc_18003E599
0x18003e531  mov     rax, [rcx]
0x18003e534  lea     r8, [rbp+var_38]
0x18003e538  xor     r9d, r9d
0x18003e53b  lea     rdx, aLastname; "LastName"
0x18003e542  mov     rax, [rax+18h]
0x18003e546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e54b  test    eax, eax
0x18003e54d  js      short loc_18003E599
0x18003e54f  cmp     word ptr [rbp+var_38], 8
0x18003e554  jnz     short loc_18003E594
0x18003e556  mov     rcx, qword ptr [rbp+var_38+8]; lpString1
0x18003e55a  lea     r8, Class; lpString2
0x18003e561  mov     r9d, r14d; cchCount2
0x18003e564  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003e56c  mov     edx, r14d; cchCount1
0x18003e56f  xor     ebx, ebx
0x18003e571  call    cs:__imp_CompareStringOrdinal
0x18003e577  cmp     eax, 2
0x18003e57a  jz      short loc_18003E599
0x18003e57c  mov     rcx, [rsi+70h]
0x18003e580  mov     rdx, qword ptr [rbp+var_38+8]
0x18003e584  mov     rax, [rcx]
0x18003e587  mov     rax, [rax+48h]
0x18003e58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e590  mov     ebx, eax
0x18003e592  jmp     short loc_18003E599
0x18003e594  mov     ebx, 8000FFFFh
0x18003e599  lea     rcx, [rbp+var_38]; pvarg
0x18003e59d  call    cs:__imp_VariantClear
0x18003e5a3  lea     rcx, [rbp+pvarg]; pvarg
0x18003e5a7  call    cs:__imp_VariantClear
0x18003e5ad  mov     eax, ebx
0x18003e5af  add     rsp, 68h
0x18003e5b3  pop     r14
0x18003e5b5  pop     rsi
0x18003e5b6  pop     rbx
0x18003e5b7  pop     rbp
0x18003e5b8  retn
```
