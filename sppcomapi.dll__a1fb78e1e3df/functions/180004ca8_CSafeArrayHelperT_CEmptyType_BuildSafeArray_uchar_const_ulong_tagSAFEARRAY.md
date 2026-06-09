# CSafeArrayHelperT<CEmptyType>::BuildSafeArray(uchar const *,ulong,tagSAFEARRAY * *)

- ea: `0x180004ca8`
- end: `0x180004d56`
- name: `?BuildSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEBEKPEAPEAUtagSAFEARRAY@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64, SAFEARRAY **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800052a0`
- `0x180022388`
- `0x180022720`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004ca8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180004d3d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180004d3d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180004cf6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180004cf6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180004d17`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180004d17`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180004ccc`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180004ccc`

## pseudocode

```c
__int64 __fastcall CSafeArrayHelperT<CEmptyType>::BuildSafeArray(__int64 a1, __int64 a2, SAFEARRAY **a3)
{
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v5; // rsi
  unsigned int v6; // edi
  HRESULT v7; // eax
  SAFEARRAY *v8; // rbx
  void *ppvData; // [rsp+50h] [rbp+8h] BYREF

  ppvData = 0;
  Vector = SafeArrayCreateVector(0x11u, 0, 0);
  v5 = Vector;
  if ( Vector )
  {
    v7 = SafeArrayAccessData(Vector, &ppvData);
    v6 = v7;
    if ( v7 < 0 || (v7 = SafeArrayUnaccessData(v5), v6 = v7, v7 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
      v8 = v5;
      goto LABEL_8;
    }
    *a3 = v5;
  }
  else
  {
    v6 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  v8 = 0;
LABEL_8:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v8 )
    SafeArrayDestroy(v8);
  return v6;
}

```

## disassembly

```asm
0x180004ca8  mov     [rsp+ppvData], rcx
0x180004cad  push    rbx
0x180004cae  push    rsi
0x180004caf  push    rdi
0x180004cb0  push    r14
0x180004cb2  sub     rsp, 28h
0x180004cb6  mov     r14, r8
0x180004cb9  mov     [rsp+48h+ppvData], 0
0x180004cc2  xor     r8d, r8d; cElements
0x180004cc5  mov     ecx, 11h; vt
0x180004cca  xor     edx, edx; lLbound
0x180004ccc  call    cs:__imp_SafeArrayCreateVector
0x180004cd3  nop     dword ptr [rax+rax+00h]
0x180004cd8  mov     rsi, rax
0x180004cdb  test    rax, rax
0x180004cde  jnz     short loc_180004CEE
0x180004ce0  mov     edi, 8007000Eh
0x180004ce5  mov     ecx, edi
0x180004ce7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004cec  jmp     short loc_180004D2C
0x180004cee  mov     rcx, rsi; psa
0x180004cf1  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180004cf6  call    cs:__imp_SafeArrayAccessData
0x180004cfd  nop     dword ptr [rax+rax+00h]
0x180004d02  mov     edi, eax
0x180004d04  test    eax, eax
0x180004d06  jns     short loc_180004D14
0x180004d08  mov     ecx, eax
0x180004d0a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004d0f  mov     rbx, rsi
0x180004d12  jmp     short loc_180004D2E
0x180004d14  mov     rcx, rsi; psa
0x180004d17  call    cs:__imp_SafeArrayUnaccessData
0x180004d1e  nop     dword ptr [rax+rax+00h]
0x180004d23  mov     edi, eax
0x180004d25  test    eax, eax
0x180004d27  js      short loc_180004D08
0x180004d29  mov     [r14], rsi
0x180004d2c  xor     ebx, ebx
0x180004d2e  mov     ecx, edi
0x180004d30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004d35  test    rbx, rbx
0x180004d38  jz      short loc_180004D49
0x180004d3a  mov     rcx, rbx; psa
0x180004d3d  call    cs:__imp_SafeArrayDestroy
0x180004d44  nop     dword ptr [rax+rax+00h]
0x180004d49  mov     eax, edi
0x180004d4b  add     rsp, 28h
0x180004d4f  pop     r14
0x180004d51  pop     rdi
0x180004d52  pop     rsi
0x180004d53  pop     rbx
0x180004d54  retn
```
