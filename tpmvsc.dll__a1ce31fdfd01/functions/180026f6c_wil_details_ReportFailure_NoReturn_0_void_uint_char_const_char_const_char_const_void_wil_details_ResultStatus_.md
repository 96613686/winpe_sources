# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180026f6c`
- end: `0x180027074`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `264`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180026ef0`

## callees

- `0x180002a90`
- `0x1800047bc`
- `0x180005a78`
- `0x180026f6c`
- `0x180034a90`
- `0x180037010`

## string_xrefs

- `0x180026fc0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  bool v8; // si
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v11[4104]; // [rsp+520h] [rbp-1008h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(v10, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    4897,
    "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    0,
    a7,
    0);
  if ( (v10[4] & 1) == 0 )
  {
    if ( v8 )
      ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v10, v11);
    if ( wil::details::g_pfnThrowResultException )
      wil::details::g_pfnThrowResultException((const struct wil::FailureInfo *)v10);
  }
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x180026f6c  mov     [rsp+arg_8], rbx
0x180026f71  mov     [rsp+arg_10], rsi
0x180026f76  push    rdi
0x180026f77  mov     eax, 1520h
0x180026f7c  call    _alloca_probe
0x180026f81  sub     rsp, rax
0x180026f84  cmp     cs:g_pfnThrowPlatformException, 0
0x180026f8c  mov     rdi, rcx
0x180026f8f  mov     rbx, [rsp+1528h+arg_28]
0x180026f97  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180026f9f  setnz   sil
0x180026fa3  mov     r8d, 98h; Size
0x180026fa9  xor     edx, edx; Val
0x180026fab  call    memset_0
0x180026fb0  lea     rax, [rsp+1528h+var_14A8]
0x180026fb8  xor     r9d, r9d
0x180026fbb  mov     [rsp+1528h+var_14B0], rax
0x180026fc0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026fc7  mov     [rsp+1528h+var_14B8], 0
0x180026fcf  lea     rax, [rsp+1528h+var_1408]
0x180026fd7  mov     [rsp+1528h+var_14C8], rax
0x180026fdc  mov     edx, 1321h
0x180026fe1  lea     rax, [rsp+1528h+var_1008]
0x180026fe9  mov     rcx, rdi
0x180026fec  mov     [rsp+1528h+var_14D8], rax
0x180026ff1  mov     rax, [rsp+1528h+arg_30]
0x180026ff9  mov     [rsp+1528h+var_14E8], 0
0x180027002  mov     [rsp+1528h+var_14F0], rax
0x180027007  mov     [rsp+1528h+var_14F8], 0
0x18002700f  mov     [rsp+1528h+var_1500], rbx
0x180027014  mov     [rsp+1528h+var_1508], 0
0x18002701d  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180027022  test    [rsp+1528h+var_14A4], 1
0x18002702a  jnz     short loc_180027066
0x18002702c  test    sil, sil
0x18002702f  jz      short loc_18002704D
0x180027031  mov     rax, cs:g_pfnThrowPlatformException
0x180027038  lea     rdx, [rsp+1528h+var_1008]
0x180027040  lea     rcx, [rsp+1528h+var_14A8]
0x180027048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002704d  mov     rax, cs:?g_pfnThrowResultException@details@wil@@3P6AXAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnThrowResultException)(wil::FailureInfo const &)
0x180027054  test    rax, rax
0x180027057  jz      short loc_180027066
0x180027059  lea     rcx, [rsp+1528h+var_14A8]
0x180027061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027066  lea     rcx, [rsp+1528h+var_14A8]; this
0x18002706e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
