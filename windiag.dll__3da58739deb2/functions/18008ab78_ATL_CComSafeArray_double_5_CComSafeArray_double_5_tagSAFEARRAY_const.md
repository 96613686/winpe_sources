# ATL::CComSafeArray<double,5>::CComSafeArray<double,5>(tagSAFEARRAY const *)

- ea: `0x18008ab78`
- end: `0x18008ac62`
- name: `??0?$CComSafeArray@N$04@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008ab78`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008abf6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008abf6`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ac1f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ac1f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008abe9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008abe9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ac0d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ac0d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008aba7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008aba7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<double,5>::CComSafeArray<double,5>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
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
  if ( v5 != 5 )
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
0x18008ab78  mov     [rsp+arg_8], rbx
0x18008ab7d  push    rdi
0x18008ab7e  sub     rsp, 20h
0x18008ab82  mov     qword ptr [rcx], 0
0x18008ab89  mov     rdi, rdx
0x18008ab8c  mov     rbx, rcx
0x18008ab8f  test    rdx, rdx
0x18008ab92  jz      loc_18008AC37
0x18008ab98  xor     eax, eax
0x18008ab9a  lea     rdx, [rsp+28h+pvt]; pvt
0x18008ab9f  mov     rcx, rdi; psa
0x18008aba2  mov     [rsp+28h+pvt], ax
0x18008aba7  call    cs:__imp_SafeArrayGetVartype
0x18008abad  test    eax, eax
0x18008abaf  js      loc_18008AC5A
0x18008abb5  movzx   ecx, [rsp+28h+pvt]
0x18008abba  cmp     cx, 0Dh
0x18008abbe  jnz     short loc_18008ABDB
0x18008abc0  movzx   eax, word ptr [rdi+2]
0x18008abc4  mov     edx, 440h
0x18008abc9  and     ax, dx
0x18008abcc  cmp     ax, dx
0x18008abcf  jnz     short loc_18008ABDB
0x18008abd1  mov     ecx, 9
0x18008abd6  mov     [rsp+28h+pvt], cx
0x18008abdb  cmp     cx, 5
0x18008abdf  jnz     short loc_18008AC37
0x18008abe1  mov     rcx, [rbx]; psa
0x18008abe4  test    rcx, rcx
0x18008abe7  jz      short loc_18008AC07
0x18008abe9  call    cs:__imp_SafeArrayUnlock
0x18008abef  test    eax, eax
0x18008abf1  js      short loc_18008AC4A
0x18008abf3  mov     rcx, [rbx]; psa
0x18008abf6  call    cs:__imp_SafeArrayDestroy
0x18008abfc  test    eax, eax
0x18008abfe  js      short loc_18008AC4A
0x18008ac00  mov     qword ptr [rbx], 0
0x18008ac07  mov     rdx, rbx; ppsaOut
0x18008ac0a  mov     rcx, rdi; psa
0x18008ac0d  call    cs:__imp_SafeArrayCopy
0x18008ac13  test    eax, eax
0x18008ac15  js      short loc_18008AC42
0x18008ac17  mov     rcx, [rbx]; psa
0x18008ac1a  test    rcx, rcx
0x18008ac1d  jz      short loc_18008AC29
0x18008ac1f  call    cs:__imp_SafeArrayLock
0x18008ac25  test    eax, eax
0x18008ac27  js      short loc_18008AC52
0x18008ac29  mov     rax, rbx
0x18008ac2c  mov     rbx, [rsp+28h+arg_8]
0x18008ac31  add     rsp, 20h
0x18008ac35  pop     rdi
0x18008ac36  retn
0x18008ac37  mov     ecx, 80070057h; int
0x18008ac3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ac42  mov     ecx, eax; int
0x18008ac44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ac4a  mov     ecx, eax; int
0x18008ac4c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ac52  mov     ecx, eax; int
0x18008ac54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ac5a  mov     ecx, eax; int
0x18008ac5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
