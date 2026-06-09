# ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(tagSAFEARRAY const *)

- ea: `0x18008a5d8`
- end: `0x18008a6c2`
- name: `??0?$CComSafeArray@E$0BB@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a5d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a656`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a656`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a67f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a67f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a649`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a649`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a66d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a66d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a607`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a607`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(
        SAFEARRAY **ppsaOut,
        SAFEARRAY *psa)
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
  if ( v5 != 17 )
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
0x18008a5d8  mov     [rsp+arg_8], rbx
0x18008a5dd  push    rdi
0x18008a5de  sub     rsp, 20h
0x18008a5e2  mov     qword ptr [rcx], 0
0x18008a5e9  mov     rdi, rdx
0x18008a5ec  mov     rbx, rcx
0x18008a5ef  test    rdx, rdx
0x18008a5f2  jz      loc_18008A697
0x18008a5f8  xor     eax, eax
0x18008a5fa  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a5ff  mov     rcx, rdi; psa
0x18008a602  mov     [rsp+28h+pvt], ax
0x18008a607  call    cs:__imp_SafeArrayGetVartype
0x18008a60d  test    eax, eax
0x18008a60f  js      loc_18008A6BA
0x18008a615  movzx   ecx, [rsp+28h+pvt]
0x18008a61a  cmp     cx, 0Dh
0x18008a61e  jnz     short loc_18008A63B
0x18008a620  movzx   eax, word ptr [rdi+2]
0x18008a624  mov     edx, 440h
0x18008a629  and     ax, dx
0x18008a62c  cmp     ax, dx
0x18008a62f  jnz     short loc_18008A63B
0x18008a631  mov     ecx, 9
0x18008a636  mov     [rsp+28h+pvt], cx
0x18008a63b  cmp     cx, 11h
0x18008a63f  jnz     short loc_18008A697
0x18008a641  mov     rcx, [rbx]; psa
0x18008a644  test    rcx, rcx
0x18008a647  jz      short loc_18008A667
0x18008a649  call    cs:__imp_SafeArrayUnlock
0x18008a64f  test    eax, eax
0x18008a651  js      short loc_18008A6AA
0x18008a653  mov     rcx, [rbx]; psa
0x18008a656  call    cs:__imp_SafeArrayDestroy
0x18008a65c  test    eax, eax
0x18008a65e  js      short loc_18008A6AA
0x18008a660  mov     qword ptr [rbx], 0
0x18008a667  mov     rdx, rbx; ppsaOut
0x18008a66a  mov     rcx, rdi; psa
0x18008a66d  call    cs:__imp_SafeArrayCopy
0x18008a673  test    eax, eax
0x18008a675  js      short loc_18008A6A2
0x18008a677  mov     rcx, [rbx]; psa
0x18008a67a  test    rcx, rcx
0x18008a67d  jz      short loc_18008A689
0x18008a67f  call    cs:__imp_SafeArrayLock
0x18008a685  test    eax, eax
0x18008a687  js      short loc_18008A6B2
0x18008a689  mov     rax, rbx
0x18008a68c  mov     rbx, [rsp+28h+arg_8]
0x18008a691  add     rsp, 20h
0x18008a695  pop     rdi
0x18008a696  retn
0x18008a697  mov     ecx, 80070057h; int
0x18008a69c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a6a2  mov     ecx, eax; int
0x18008a6a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a6aa  mov     ecx, eax; int
0x18008a6ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a6b2  mov     ecx, eax; int
0x18008a6b4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a6ba  mov     ecx, eax; int
0x18008a6bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
