# ATL::CComSafeArray<unsigned __int64,21>::CComSafeArray<unsigned __int64,21>(tagSAFEARRAY const *)

- ea: `0x18008ae48`
- end: `0x18008af32`
- name: `??0?$CComSafeArray@_K$0BF@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008ae48`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008aec6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008aec6`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008aeef`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008aeef`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aeb9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008aeb9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aedd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aedd`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ae77`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ae77`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned __int64,21>::CComSafeArray<unsigned __int64,21>(
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
  if ( v5 != 21 )
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
0x18008ae48  mov     [rsp+arg_8], rbx
0x18008ae4d  push    rdi
0x18008ae4e  sub     rsp, 20h
0x18008ae52  mov     qword ptr [rcx], 0
0x18008ae59  mov     rdi, rdx
0x18008ae5c  mov     rbx, rcx
0x18008ae5f  test    rdx, rdx
0x18008ae62  jz      loc_18008AF07
0x18008ae68  xor     eax, eax
0x18008ae6a  lea     rdx, [rsp+28h+pvt]; pvt
0x18008ae6f  mov     rcx, rdi; psa
0x18008ae72  mov     [rsp+28h+pvt], ax
0x18008ae77  call    cs:__imp_SafeArrayGetVartype
0x18008ae7d  test    eax, eax
0x18008ae7f  js      loc_18008AF2A
0x18008ae85  movzx   ecx, [rsp+28h+pvt]
0x18008ae8a  cmp     cx, 0Dh
0x18008ae8e  jnz     short loc_18008AEAB
0x18008ae90  movzx   eax, word ptr [rdi+2]
0x18008ae94  mov     edx, 440h
0x18008ae99  and     ax, dx
0x18008ae9c  cmp     ax, dx
0x18008ae9f  jnz     short loc_18008AEAB
0x18008aea1  mov     ecx, 9
0x18008aea6  mov     [rsp+28h+pvt], cx
0x18008aeab  cmp     cx, 15h
0x18008aeaf  jnz     short loc_18008AF07
0x18008aeb1  mov     rcx, [rbx]; psa
0x18008aeb4  test    rcx, rcx
0x18008aeb7  jz      short loc_18008AED7
0x18008aeb9  call    cs:__imp_SafeArrayUnlock
0x18008aebf  test    eax, eax
0x18008aec1  js      short loc_18008AF1A
0x18008aec3  mov     rcx, [rbx]; psa
0x18008aec6  call    cs:__imp_SafeArrayDestroy
0x18008aecc  test    eax, eax
0x18008aece  js      short loc_18008AF1A
0x18008aed0  mov     qword ptr [rbx], 0
0x18008aed7  mov     rdx, rbx; ppsaOut
0x18008aeda  mov     rcx, rdi; psa
0x18008aedd  call    cs:__imp_SafeArrayCopy
0x18008aee3  test    eax, eax
0x18008aee5  js      short loc_18008AF12
0x18008aee7  mov     rcx, [rbx]; psa
0x18008aeea  test    rcx, rcx
0x18008aeed  jz      short loc_18008AEF9
0x18008aeef  call    cs:__imp_SafeArrayLock
0x18008aef5  test    eax, eax
0x18008aef7  js      short loc_18008AF22
0x18008aef9  mov     rax, rbx
0x18008aefc  mov     rbx, [rsp+28h+arg_8]
0x18008af01  add     rsp, 20h
0x18008af05  pop     rdi
0x18008af06  retn
0x18008af07  mov     ecx, 80070057h; int
0x18008af0c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008af12  mov     ecx, eax; int
0x18008af14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008af1a  mov     ecx, eax; int
0x18008af1c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008af22  mov     ecx, eax; int
0x18008af24  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008af2a  mov     ecx, eax; int
0x18008af2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
