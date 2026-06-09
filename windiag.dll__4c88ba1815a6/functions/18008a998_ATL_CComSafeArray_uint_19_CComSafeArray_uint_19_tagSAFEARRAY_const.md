# ATL::CComSafeArray<uint,19>::CComSafeArray<uint,19>(tagSAFEARRAY const *)

- ea: `0x18008a998`
- end: `0x18008aa82`
- name: `??0?$CComSafeArray@I$0BD@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `SAFEARRAY **__fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a998`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008aa16`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008aa16`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008aa3f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008aa3f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aa09`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aa09`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aa2d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aa2d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a9c7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a9c7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned int,19>::CComSafeArray<unsigned int,19>(
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
  if ( v5 != 19 )
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
0x18008a998  mov     [rsp+arg_8], rbx
0x18008a99d  push    rdi
0x18008a99e  sub     rsp, 20h
0x18008a9a2  mov     qword ptr [rcx], 0
0x18008a9a9  mov     rdi, rdx
0x18008a9ac  mov     rbx, rcx
0x18008a9af  test    rdx, rdx
0x18008a9b2  jz      loc_18008AA57
0x18008a9b8  xor     eax, eax
0x18008a9ba  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a9bf  mov     rcx, rdi; psa
0x18008a9c2  mov     [rsp+28h+pvt], ax
0x18008a9c7  call    cs:__imp_SafeArrayGetVartype
0x18008a9cd  test    eax, eax
0x18008a9cf  js      loc_18008AA7A
0x18008a9d5  movzx   ecx, [rsp+28h+pvt]
0x18008a9da  cmp     cx, 0Dh
0x18008a9de  jnz     short loc_18008A9FB
0x18008a9e0  movzx   eax, word ptr [rdi+2]
0x18008a9e4  mov     edx, 440h
0x18008a9e9  and     ax, dx
0x18008a9ec  cmp     ax, dx
0x18008a9ef  jnz     short loc_18008A9FB
0x18008a9f1  mov     ecx, 9
0x18008a9f6  mov     [rsp+28h+pvt], cx
0x18008a9fb  cmp     cx, 13h
0x18008a9ff  jnz     short loc_18008AA57
0x18008aa01  mov     rcx, [rbx]; psa
0x18008aa04  test    rcx, rcx
0x18008aa07  jz      short loc_18008AA27
0x18008aa09  call    cs:__imp_SafeArrayUnlock
0x18008aa0f  test    eax, eax
0x18008aa11  js      short loc_18008AA6A
0x18008aa13  mov     rcx, [rbx]; psa
0x18008aa16  call    cs:__imp_SafeArrayDestroy
0x18008aa1c  test    eax, eax
0x18008aa1e  js      short loc_18008AA6A
0x18008aa20  mov     qword ptr [rbx], 0
0x18008aa27  mov     rdx, rbx; ppsaOut
0x18008aa2a  mov     rcx, rdi; psa
0x18008aa2d  call    cs:__imp_SafeArrayCopy
0x18008aa33  test    eax, eax
0x18008aa35  js      short loc_18008AA62
0x18008aa37  mov     rcx, [rbx]; psa
0x18008aa3a  test    rcx, rcx
0x18008aa3d  jz      short loc_18008AA49
0x18008aa3f  call    cs:__imp_SafeArrayLock
0x18008aa45  test    eax, eax
0x18008aa47  js      short loc_18008AA72
0x18008aa49  mov     rax, rbx
0x18008aa4c  mov     rbx, [rsp+28h+arg_8]
0x18008aa51  add     rsp, 20h
0x18008aa55  pop     rdi
0x18008aa56  retn
0x18008aa57  mov     ecx, 80070057h; int
0x18008aa5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008aa62  mov     ecx, eax; int
0x18008aa64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008aa6a  mov     ecx, eax; int
0x18008aa6c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008aa72  mov     ecx, eax; int
0x18008aa74  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008aa7a  mov     ecx, eax; int
0x18008aa7c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
