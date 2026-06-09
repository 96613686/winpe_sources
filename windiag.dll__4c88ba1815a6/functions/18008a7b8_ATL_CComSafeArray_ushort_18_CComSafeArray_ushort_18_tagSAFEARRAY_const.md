# ATL::CComSafeArray<ushort,18>::CComSafeArray<ushort,18>(tagSAFEARRAY const *)

- ea: `0x18008a7b8`
- end: `0x18008a8a2`
- name: `??0?$CComSafeArray@G$0BC@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `SAFEARRAY **__fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a7b8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a836`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a836`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a85f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a85f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a829`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a829`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a84d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a84d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a7e7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a7e7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned short,18>::CComSafeArray<unsigned short,18>(
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
  if ( v5 != 18 )
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
0x18008a7b8  mov     [rsp+arg_8], rbx
0x18008a7bd  push    rdi
0x18008a7be  sub     rsp, 20h
0x18008a7c2  mov     qword ptr [rcx], 0
0x18008a7c9  mov     rdi, rdx
0x18008a7cc  mov     rbx, rcx
0x18008a7cf  test    rdx, rdx
0x18008a7d2  jz      loc_18008A877
0x18008a7d8  xor     eax, eax
0x18008a7da  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a7df  mov     rcx, rdi; psa
0x18008a7e2  mov     [rsp+28h+pvt], ax
0x18008a7e7  call    cs:__imp_SafeArrayGetVartype
0x18008a7ed  test    eax, eax
0x18008a7ef  js      loc_18008A89A
0x18008a7f5  movzx   ecx, [rsp+28h+pvt]
0x18008a7fa  cmp     cx, 0Dh
0x18008a7fe  jnz     short loc_18008A81B
0x18008a800  movzx   eax, word ptr [rdi+2]
0x18008a804  mov     edx, 440h
0x18008a809  and     ax, dx
0x18008a80c  cmp     ax, dx
0x18008a80f  jnz     short loc_18008A81B
0x18008a811  mov     ecx, 9
0x18008a816  mov     [rsp+28h+pvt], cx
0x18008a81b  cmp     cx, 12h
0x18008a81f  jnz     short loc_18008A877
0x18008a821  mov     rcx, [rbx]; psa
0x18008a824  test    rcx, rcx
0x18008a827  jz      short loc_18008A847
0x18008a829  call    cs:__imp_SafeArrayUnlock
0x18008a82f  test    eax, eax
0x18008a831  js      short loc_18008A88A
0x18008a833  mov     rcx, [rbx]; psa
0x18008a836  call    cs:__imp_SafeArrayDestroy
0x18008a83c  test    eax, eax
0x18008a83e  js      short loc_18008A88A
0x18008a840  mov     qword ptr [rbx], 0
0x18008a847  mov     rdx, rbx; ppsaOut
0x18008a84a  mov     rcx, rdi; psa
0x18008a84d  call    cs:__imp_SafeArrayCopy
0x18008a853  test    eax, eax
0x18008a855  js      short loc_18008A882
0x18008a857  mov     rcx, [rbx]; psa
0x18008a85a  test    rcx, rcx
0x18008a85d  jz      short loc_18008A869
0x18008a85f  call    cs:__imp_SafeArrayLock
0x18008a865  test    eax, eax
0x18008a867  js      short loc_18008A892
0x18008a869  mov     rax, rbx
0x18008a86c  mov     rbx, [rsp+28h+arg_8]
0x18008a871  add     rsp, 20h
0x18008a875  pop     rdi
0x18008a876  retn
0x18008a877  mov     ecx, 80070057h; int
0x18008a87c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a882  mov     ecx, eax; int
0x18008a884  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a88a  mov     ecx, eax; int
0x18008a88c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a892  mov     ecx, eax; int
0x18008a894  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a89a  mov     ecx, eax; int
0x18008a89c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
