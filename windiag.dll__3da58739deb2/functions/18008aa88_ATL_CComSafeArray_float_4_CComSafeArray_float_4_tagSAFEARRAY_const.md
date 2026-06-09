# ATL::CComSafeArray<float,4>::CComSafeArray<float,4>(tagSAFEARRAY const *)

- ea: `0x18008aa88`
- end: `0x18008ab72`
- name: `??0?$CComSafeArray@M$03@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008aa88`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008ab06`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008ab06`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ab2f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ab2f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aaf9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aaf9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ab1d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ab1d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008aab7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008aab7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<float,4>::CComSafeArray<float,4>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
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
  if ( v5 != 4 )
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
0x18008aa88  mov     [rsp+arg_8], rbx
0x18008aa8d  push    rdi
0x18008aa8e  sub     rsp, 20h
0x18008aa92  mov     qword ptr [rcx], 0
0x18008aa99  mov     rdi, rdx
0x18008aa9c  mov     rbx, rcx
0x18008aa9f  test    rdx, rdx
0x18008aaa2  jz      loc_18008AB47
0x18008aaa8  xor     eax, eax
0x18008aaaa  lea     rdx, [rsp+28h+pvt]; pvt
0x18008aaaf  mov     rcx, rdi; psa
0x18008aab2  mov     [rsp+28h+pvt], ax
0x18008aab7  call    cs:__imp_SafeArrayGetVartype
0x18008aabd  test    eax, eax
0x18008aabf  js      loc_18008AB6A
0x18008aac5  movzx   ecx, [rsp+28h+pvt]
0x18008aaca  cmp     cx, 0Dh
0x18008aace  jnz     short loc_18008AAEB
0x18008aad0  movzx   eax, word ptr [rdi+2]
0x18008aad4  mov     edx, 440h
0x18008aad9  and     ax, dx
0x18008aadc  cmp     ax, dx
0x18008aadf  jnz     short loc_18008AAEB
0x18008aae1  mov     ecx, 9
0x18008aae6  mov     [rsp+28h+pvt], cx
0x18008aaeb  cmp     cx, 4
0x18008aaef  jnz     short loc_18008AB47
0x18008aaf1  mov     rcx, [rbx]; psa
0x18008aaf4  test    rcx, rcx
0x18008aaf7  jz      short loc_18008AB17
0x18008aaf9  call    cs:__imp_SafeArrayUnlock
0x18008aaff  test    eax, eax
0x18008ab01  js      short loc_18008AB5A
0x18008ab03  mov     rcx, [rbx]; psa
0x18008ab06  call    cs:__imp_SafeArrayDestroy
0x18008ab0c  test    eax, eax
0x18008ab0e  js      short loc_18008AB5A
0x18008ab10  mov     qword ptr [rbx], 0
0x18008ab17  mov     rdx, rbx; ppsaOut
0x18008ab1a  mov     rcx, rdi; psa
0x18008ab1d  call    cs:__imp_SafeArrayCopy
0x18008ab23  test    eax, eax
0x18008ab25  js      short loc_18008AB52
0x18008ab27  mov     rcx, [rbx]; psa
0x18008ab2a  test    rcx, rcx
0x18008ab2d  jz      short loc_18008AB39
0x18008ab2f  call    cs:__imp_SafeArrayLock
0x18008ab35  test    eax, eax
0x18008ab37  js      short loc_18008AB62
0x18008ab39  mov     rax, rbx
0x18008ab3c  mov     rbx, [rsp+28h+arg_8]
0x18008ab41  add     rsp, 20h
0x18008ab45  pop     rdi
0x18008ab46  retn
0x18008ab47  mov     ecx, 80070057h; int
0x18008ab4c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ab52  mov     ecx, eax; int
0x18008ab54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ab5a  mov     ecx, eax; int
0x18008ab5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ab62  mov     ecx, eax; int
0x18008ab64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ab6a  mov     ecx, eax; int
0x18008ab6c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
