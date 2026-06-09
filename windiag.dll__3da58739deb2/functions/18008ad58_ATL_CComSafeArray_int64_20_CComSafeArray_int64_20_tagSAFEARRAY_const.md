# ATL::CComSafeArray<__int64,20>::CComSafeArray<__int64,20>(tagSAFEARRAY const *)

- ea: `0x18008ad58`
- end: `0x18008ae42`
- name: `??0?$CComSafeArray@_J$0BE@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x18008ad58`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008add6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18008add6`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008adff`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18008adff`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008adc9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18008adc9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aded`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008aded`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ad87`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18008ad87`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<__int64,20>::CComSafeArray<__int64,20>(SAFEARRAY **ppsaOut, SAFEARRAY *psa)
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
  if ( v5 != 20 )
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
0x18008ad58  mov     [rsp+arg_8], rbx
0x18008ad5d  push    rdi
0x18008ad5e  sub     rsp, 20h
0x18008ad62  mov     qword ptr [rcx], 0
0x18008ad69  mov     rdi, rdx
0x18008ad6c  mov     rbx, rcx
0x18008ad6f  test    rdx, rdx
0x18008ad72  jz      loc_18008AE17
0x18008ad78  xor     eax, eax
0x18008ad7a  lea     rdx, [rsp+28h+pvt]; pvt
0x18008ad7f  mov     rcx, rdi; psa
0x18008ad82  mov     [rsp+28h+pvt], ax
0x18008ad87  call    cs:__imp_SafeArrayGetVartype
0x18008ad8d  test    eax, eax
0x18008ad8f  js      loc_18008AE3A
0x18008ad95  movzx   ecx, [rsp+28h+pvt]
0x18008ad9a  cmp     cx, 0Dh
0x18008ad9e  jnz     short loc_18008ADBB
0x18008ada0  movzx   eax, word ptr [rdi+2]
0x18008ada4  mov     edx, 440h
0x18008ada9  and     ax, dx
0x18008adac  cmp     ax, dx
0x18008adaf  jnz     short loc_18008ADBB
0x18008adb1  mov     ecx, 9
0x18008adb6  mov     [rsp+28h+pvt], cx
0x18008adbb  cmp     cx, 14h
0x18008adbf  jnz     short loc_18008AE17
0x18008adc1  mov     rcx, [rbx]; psa
0x18008adc4  test    rcx, rcx
0x18008adc7  jz      short loc_18008ADE7
0x18008adc9  call    cs:__imp_SafeArrayUnlock
0x18008adcf  test    eax, eax
0x18008add1  js      short loc_18008AE2A
0x18008add3  mov     rcx, [rbx]; psa
0x18008add6  call    cs:__imp_SafeArrayDestroy
0x18008addc  test    eax, eax
0x18008adde  js      short loc_18008AE2A
0x18008ade0  mov     qword ptr [rbx], 0
0x18008ade7  mov     rdx, rbx; ppsaOut
0x18008adea  mov     rcx, rdi; psa
0x18008aded  call    cs:__imp_SafeArrayCopy
0x18008adf3  test    eax, eax
0x18008adf5  js      short loc_18008AE22
0x18008adf7  mov     rcx, [rbx]; psa
0x18008adfa  test    rcx, rcx
0x18008adfd  jz      short loc_18008AE09
0x18008adff  call    cs:__imp_SafeArrayLock
0x18008ae05  test    eax, eax
0x18008ae07  js      short loc_18008AE32
0x18008ae09  mov     rax, rbx
0x18008ae0c  mov     rbx, [rsp+28h+arg_8]
0x18008ae11  add     rsp, 20h
0x18008ae15  pop     rdi
0x18008ae16  retn
0x18008ae17  mov     ecx, 80070057h; int
0x18008ae1c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ae22  mov     ecx, eax; int
0x18008ae24  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ae2a  mov     ecx, eax; int
0x18008ae2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ae32  mov     ecx, eax; int
0x18008ae34  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008ae3a  mov     ecx, eax; int
0x18008ae3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
