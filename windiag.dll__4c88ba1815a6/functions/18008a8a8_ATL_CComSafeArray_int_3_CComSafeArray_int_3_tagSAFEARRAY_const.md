# ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(tagSAFEARRAY const *)

- ea: `0x18008a8a8`
- end: `0x18008a992`
- name: `??0?$CComSafeArray@H$02@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `SAFEARRAY **__fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008a8a8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a926`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008a926`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a94f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008a94f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a919`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008a919`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a93d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008a93d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a8d7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008a8d7`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
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
  if ( v5 != 3 )
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
0x18008a8a8  mov     [rsp+arg_8], rbx
0x18008a8ad  push    rdi
0x18008a8ae  sub     rsp, 20h
0x18008a8b2  mov     qword ptr [rcx], 0
0x18008a8b9  mov     rdi, rdx
0x18008a8bc  mov     rbx, rcx
0x18008a8bf  test    rdx, rdx
0x18008a8c2  jz      loc_18008A967
0x18008a8c8  xor     eax, eax
0x18008a8ca  lea     rdx, [rsp+28h+pvt]; pvt
0x18008a8cf  mov     rcx, rdi; psa
0x18008a8d2  mov     [rsp+28h+pvt], ax
0x18008a8d7  call    cs:__imp_SafeArrayGetVartype
0x18008a8dd  test    eax, eax
0x18008a8df  js      loc_18008A98A
0x18008a8e5  movzx   ecx, [rsp+28h+pvt]
0x18008a8ea  cmp     cx, 0Dh
0x18008a8ee  jnz     short loc_18008A90B
0x18008a8f0  movzx   eax, word ptr [rdi+2]
0x18008a8f4  mov     edx, 440h
0x18008a8f9  and     ax, dx
0x18008a8fc  cmp     ax, dx
0x18008a8ff  jnz     short loc_18008A90B
0x18008a901  mov     ecx, 9
0x18008a906  mov     [rsp+28h+pvt], cx
0x18008a90b  cmp     cx, 3
0x18008a90f  jnz     short loc_18008A967
0x18008a911  mov     rcx, [rbx]; psa
0x18008a914  test    rcx, rcx
0x18008a917  jz      short loc_18008A937
0x18008a919  call    cs:__imp_SafeArrayUnlock
0x18008a91f  test    eax, eax
0x18008a921  js      short loc_18008A97A
0x18008a923  mov     rcx, [rbx]; psa
0x18008a926  call    cs:__imp_SafeArrayDestroy
0x18008a92c  test    eax, eax
0x18008a92e  js      short loc_18008A97A
0x18008a930  mov     qword ptr [rbx], 0
0x18008a937  mov     rdx, rbx; ppsaOut
0x18008a93a  mov     rcx, rdi; psa
0x18008a93d  call    cs:__imp_SafeArrayCopy
0x18008a943  test    eax, eax
0x18008a945  js      short loc_18008A972
0x18008a947  mov     rcx, [rbx]; psa
0x18008a94a  test    rcx, rcx
0x18008a94d  jz      short loc_18008A959
0x18008a94f  call    cs:__imp_SafeArrayLock
0x18008a955  test    eax, eax
0x18008a957  js      short loc_18008A982
0x18008a959  mov     rax, rbx
0x18008a95c  mov     rbx, [rsp+28h+arg_8]
0x18008a961  add     rsp, 20h
0x18008a965  pop     rdi
0x18008a966  retn
0x18008a967  mov     ecx, 80070057h; int
0x18008a96c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a972  mov     ecx, eax; int
0x18008a974  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a97a  mov     ecx, eax; int
0x18008a97c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a982  mov     ecx, eax; int
0x18008a984  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a98a  mov     ecx, eax; int
0x18008a98c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
