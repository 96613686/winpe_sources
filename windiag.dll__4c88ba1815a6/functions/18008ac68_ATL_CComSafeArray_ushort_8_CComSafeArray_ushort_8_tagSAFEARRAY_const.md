# ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAY const *)

- ea: `0x18008ac68`
- end: `0x18008ad52`
- name: `??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `SAFEARRAY **__fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008ac68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008ace6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008ace6`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ad0f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008ad0f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008acd9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008acd9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008acfd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008acfd`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ac97`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ac97`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(
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
  if ( v5 != 8 )
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
0x18008ac68  mov     [rsp+arg_8], rbx
0x18008ac6d  push    rdi
0x18008ac6e  sub     rsp, 20h
0x18008ac72  mov     qword ptr [rcx], 0
0x18008ac79  mov     rdi, rdx
0x18008ac7c  mov     rbx, rcx
0x18008ac7f  test    rdx, rdx
0x18008ac82  jz      loc_18008AD27
0x18008ac88  xor     eax, eax
0x18008ac8a  lea     rdx, [rsp+28h+pvt]; pvt
0x18008ac8f  mov     rcx, rdi; psa
0x18008ac92  mov     [rsp+28h+pvt], ax
0x18008ac97  call    cs:__imp_SafeArrayGetVartype
0x18008ac9d  test    eax, eax
0x18008ac9f  js      loc_18008AD4A
0x18008aca5  movzx   ecx, [rsp+28h+pvt]
0x18008acaa  cmp     cx, 0Dh
0x18008acae  jnz     short loc_18008ACCB
0x18008acb0  movzx   eax, word ptr [rdi+2]
0x18008acb4  mov     edx, 440h
0x18008acb9  and     ax, dx
0x18008acbc  cmp     ax, dx
0x18008acbf  jnz     short loc_18008ACCB
0x18008acc1  mov     ecx, 9
0x18008acc6  mov     [rsp+28h+pvt], cx
0x18008accb  cmp     cx, 8
0x18008accf  jnz     short loc_18008AD27
0x18008acd1  mov     rcx, [rbx]; psa
0x18008acd4  test    rcx, rcx
0x18008acd7  jz      short loc_18008ACF7
0x18008acd9  call    cs:__imp_SafeArrayUnlock
0x18008acdf  test    eax, eax
0x18008ace1  js      short loc_18008AD3A
0x18008ace3  mov     rcx, [rbx]; psa
0x18008ace6  call    cs:__imp_SafeArrayDestroy
0x18008acec  test    eax, eax
0x18008acee  js      short loc_18008AD3A
0x18008acf0  mov     qword ptr [rbx], 0
0x18008acf7  mov     rdx, rbx; ppsaOut
0x18008acfa  mov     rcx, rdi; psa
0x18008acfd  call    cs:__imp_SafeArrayCopy
0x18008ad03  test    eax, eax
0x18008ad05  js      short loc_18008AD32
0x18008ad07  mov     rcx, [rbx]; psa
0x18008ad0a  test    rcx, rcx
0x18008ad0d  jz      short loc_18008AD19
0x18008ad0f  call    cs:__imp_SafeArrayLock
0x18008ad15  test    eax, eax
0x18008ad17  js      short loc_18008AD42
0x18008ad19  mov     rax, rbx
0x18008ad1c  mov     rbx, [rsp+28h+arg_8]
0x18008ad21  add     rsp, 20h
0x18008ad25  pop     rdi
0x18008ad26  retn
0x18008ad27  mov     ecx, 80070057h; int
0x18008ad2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ad32  mov     ecx, eax; int
0x18008ad34  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ad3a  mov     ecx, eax; int
0x18008ad3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ad42  mov     ecx, eax; int
0x18008ad44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ad4a  mov     ecx, eax; int
0x18008ad4c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
