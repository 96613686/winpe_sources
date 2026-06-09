# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b248`
- end: `0x18000b2f5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b0ac`

## callees

- `0x18000a192`
- `0x18000c6a0`
- `0x18000d770`
- `0x180015490`

## string_xrefs

- `0x18000b291`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+80h] [rbp-14A8h] BYREF

  memset_0(v10, 0, 0x98u);
  wil::details::LogFailure(a1, a2, "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h", 0, 0, a6, 3, a7, 0);
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x18000b248  mov     [rsp+arg_10], rbx
0x18000b24d  mov     [rsp+arg_18], rsi
0x18000b252  push    rdi
0x18000b253  mov     eax, 1520h
0x18000b258  call    _alloca_probe
0x18000b25d  sub     rsp, rax
0x18000b260  mov     rbx, [rsp+1528h+arg_28]
0x18000b268  mov     esi, edx
0x18000b26a  mov     rdi, rcx
0x18000b26d  xor     edx, edx; Val
0x18000b26f  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18000b277  mov     r8d, 98h; Size
0x18000b27d  call    memset_0
0x18000b282  xor     ecx, ecx
0x18000b284  lea     rax, [rsp+1528h+var_14A8]
0x18000b28c  mov     [rsp+1528h+var_14B0], rax
0x18000b291  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b298  mov     [rsp+1528h+var_14B8], ecx
0x18000b29c  lea     rax, [rsp+1528h+var_1408]
0x18000b2a4  mov     [rsp+1528h+var_14C8], rax
0x18000b2a9  xor     r9d, r9d
0x18000b2ac  lea     rax, [rsp+1528h+var_1008]
0x18000b2b4  mov     edx, esi
0x18000b2b6  mov     [rsp+1528h+var_14D8], rax
0x18000b2bb  mov     rax, [rsp+1528h+arg_30]
0x18000b2c3  mov     [rsp+1528h+var_14E8], rcx
0x18000b2c8  mov     [rsp+1528h+var_14F0], rax
0x18000b2cd  mov     [rsp+1528h+var_14F8], 3
0x18000b2d5  mov     [rsp+1528h+var_1500], rbx
0x18000b2da  mov     [rsp+1528h+var_1508], rcx
0x18000b2df  mov     rcx, rdi
0x18000b2e2  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000b2e7  lea     rcx, [rsp+1528h+var_14A8]; this
0x18000b2ef  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
