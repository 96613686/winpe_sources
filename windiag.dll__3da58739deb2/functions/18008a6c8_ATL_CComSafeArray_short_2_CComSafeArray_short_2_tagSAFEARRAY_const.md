# ATL::CComSafeArray<short,2>::CComSafeArray<short,2>(tagSAFEARRAY const *)

- ea: `0x18008a6c8`
- end: `0x18008a7b2`
- name: `??0?$CComSafeArray@F$01@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a6c8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a746`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a746`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a76f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a76f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a739`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a739`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a75d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a75d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a6f7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a6f7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<short,2>::CComSafeArray<short,2>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
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
  if ( v5 != 2 )
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
0x18008a6c8  mov     [rsp+arg_8], rbx
0x18008a6cd  push    rdi
0x18008a6ce  sub     rsp, 20h
0x18008a6d2  mov     qword ptr [rcx], 0
0x18008a6d9  mov     rdi, rdx
0x18008a6dc  mov     rbx, rcx
0x18008a6df  test    rdx, rdx
0x18008a6e2  jz      loc_18008A787
0x18008a6e8  xor     eax, eax
0x18008a6ea  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a6ef  mov     rcx, rdi; psa
0x18008a6f2  mov     [rsp+28h+pvt], ax
0x18008a6f7  call    cs:__imp_SafeArrayGetVartype
0x18008a6fd  test    eax, eax
0x18008a6ff  js      loc_18008A7AA
0x18008a705  movzx   ecx, [rsp+28h+pvt]
0x18008a70a  cmp     cx, 0Dh
0x18008a70e  jnz     short loc_18008A72B
0x18008a710  movzx   eax, word ptr [rdi+2]
0x18008a714  mov     edx, 440h
0x18008a719  and     ax, dx
0x18008a71c  cmp     ax, dx
0x18008a71f  jnz     short loc_18008A72B
0x18008a721  mov     ecx, 9
0x18008a726  mov     [rsp+28h+pvt], cx
0x18008a72b  cmp     cx, 2
0x18008a72f  jnz     short loc_18008A787
0x18008a731  mov     rcx, [rbx]; psa
0x18008a734  test    rcx, rcx
0x18008a737  jz      short loc_18008A757
0x18008a739  call    cs:__imp_SafeArrayUnlock
0x18008a73f  test    eax, eax
0x18008a741  js      short loc_18008A79A
0x18008a743  mov     rcx, [rbx]; psa
0x18008a746  call    cs:__imp_SafeArrayDestroy
0x18008a74c  test    eax, eax
0x18008a74e  js      short loc_18008A79A
0x18008a750  mov     qword ptr [rbx], 0
0x18008a757  mov     rdx, rbx; ppsaOut
0x18008a75a  mov     rcx, rdi; psa
0x18008a75d  call    cs:__imp_SafeArrayCopy
0x18008a763  test    eax, eax
0x18008a765  js      short loc_18008A792
0x18008a767  mov     rcx, [rbx]; psa
0x18008a76a  test    rcx, rcx
0x18008a76d  jz      short loc_18008A779
0x18008a76f  call    cs:__imp_SafeArrayLock
0x18008a775  test    eax, eax
0x18008a777  js      short loc_18008A7A2
0x18008a779  mov     rax, rbx
0x18008a77c  mov     rbx, [rsp+28h+arg_8]
0x18008a781  add     rsp, 20h
0x18008a785  pop     rdi
0x18008a786  retn
0x18008a787  mov     ecx, 80070057h; int
0x18008a78c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a792  mov     ecx, eax; int
0x18008a794  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a79a  mov     ecx, eax; int
0x18008a79c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a7a2  mov     ecx, eax; int
0x18008a7a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a7aa  mov     ecx, eax; int
0x18008a7ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
