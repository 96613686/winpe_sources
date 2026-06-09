# ATL::CComSafeArray<char,16>::CComSafeArray<char,16>(tagSAFEARRAY const *)

- ea: `0x18008a4e8`
- end: `0x18008a5d2`
- name: `??0?$CComSafeArray@D$0BA@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a4e8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a566`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a566`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a58f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a58f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a559`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a559`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a57d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a57d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a517`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a517`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<char,16>::CComSafeArray<char,16>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
{
  HRESULT Vartype; // eax
  VARTYPE v5; // cx
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  VARTYPE pvt; // [rsp+30h] [rbp+8h] BYREF

  *ppsaOut = 0;
  if ( !psa )
    goto LABEL_15;
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  if ( Vartype < 0 )
    ATL::AtlThrowImpl(Vartype);
  v5 = pvt;
  if ( pvt == 13 && (psa->fFeatures & 0x440) == 0x440 )
  {
    v5 = 9;
    pvt = 9;
  }
  if ( v5 != 16 )
LABEL_15:
    ATL::AtlThrowImpl(-2147024809);
  if ( *ppsaOut )
  {
    v6 = SafeArrayUnlock(*ppsaOut);
    if ( v6 < 0 || (v6 = SafeArrayDestroy(*ppsaOut), v6 < 0) )
      ATL::AtlThrowImpl(v6);
    *ppsaOut = 0;
  }
  v7 = SafeArrayCopy(psa, ppsaOut);
  if ( v7 < 0 )
    ATL::AtlThrowImpl(v7);
  if ( *ppsaOut )
  {
    v8 = SafeArrayLock(*ppsaOut);
    if ( v8 < 0 )
      ATL::AtlThrowImpl(v8);
  }
  return ppsaOut;
}

```

## disassembly

```asm
0x18008a4e8  mov     [rsp+arg_8], rbx
0x18008a4ed  push    rdi
0x18008a4ee  sub     rsp, 20h
0x18008a4f2  mov     qword ptr [rcx], 0
0x18008a4f9  mov     rdi, rdx
0x18008a4fc  mov     rbx, rcx
0x18008a4ff  test    rdx, rdx
0x18008a502  jz      loc_18008A5A7
0x18008a508  xor     eax, eax
0x18008a50a  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a50f  mov     rcx, rdi; psa
0x18008a512  mov     [rsp+28h+pvt], ax
0x18008a517  call    cs:__imp_SafeArrayGetVartype
0x18008a51d  test    eax, eax
0x18008a51f  js      loc_18008A5CA
0x18008a525  movzx   ecx, [rsp+28h+pvt]
0x18008a52a  cmp     cx, 0Dh
0x18008a52e  jnz     short loc_18008A54B
0x18008a530  movzx   eax, word ptr [rdi+2]
0x18008a534  mov     edx, 440h
0x18008a539  and     ax, dx
0x18008a53c  cmp     ax, dx
0x18008a53f  jnz     short loc_18008A54B
0x18008a541  mov     ecx, 9
0x18008a546  mov     [rsp+28h+pvt], cx
0x18008a54b  cmp     cx, 10h
0x18008a54f  jnz     short loc_18008A5A7
0x18008a551  mov     rcx, [rbx]; psa
0x18008a554  test    rcx, rcx
0x18008a557  jz      short loc_18008A577
0x18008a559  call    cs:__imp_SafeArrayUnlock
0x18008a55f  test    eax, eax
0x18008a561  js      short loc_18008A5BA
0x18008a563  mov     rcx, [rbx]; psa
0x18008a566  call    cs:__imp_SafeArrayDestroy
0x18008a56c  test    eax, eax
0x18008a56e  js      short loc_18008A5BA
0x18008a570  mov     qword ptr [rbx], 0
0x18008a577  mov     rdx, rbx; ppsaOut
0x18008a57a  mov     rcx, rdi; psa
0x18008a57d  call    cs:__imp_SafeArrayCopy
0x18008a583  test    eax, eax
0x18008a585  js      short loc_18008A5B2
0x18008a587  mov     rcx, [rbx]; psa
0x18008a58a  test    rcx, rcx
0x18008a58d  jz      short loc_18008A599
0x18008a58f  call    cs:__imp_SafeArrayLock
0x18008a595  test    eax, eax
0x18008a597  js      short loc_18008A5C2
0x18008a599  mov     rax, rbx
0x18008a59c  mov     rbx, [rsp+28h+arg_8]
0x18008a5a1  add     rsp, 20h
0x18008a5a5  pop     rdi
0x18008a5a6  retn
0x18008a5a7  mov     ecx, 80070057h; int
0x18008a5ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a5b2  mov     ecx, eax; int
0x18008a5b4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a5ba  mov     ecx, eax; int
0x18008a5bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a5c2  mov     ecx, eax; int
0x18008a5c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a5ca  mov     ecx, eax; int
0x18008a5cc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
