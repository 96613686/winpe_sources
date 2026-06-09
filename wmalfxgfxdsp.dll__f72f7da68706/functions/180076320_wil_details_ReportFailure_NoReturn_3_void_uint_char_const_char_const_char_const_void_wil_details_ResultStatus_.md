# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180076320`
- end: `0x1800763cd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180076150`

## callees

- `0x180015ea8`
- `0x18007832c`
- `0x180079788`
- `0x1800859f0`

## string_xrefs

- `0x180076369`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  const struct wil::FailureInfo *v9; // rdx
  __int64 v10; // [rsp+48h] [rbp-14E0h]
  __int64 v11; // [rsp+58h] [rbp-14D0h]
  __int64 v12; // [rsp+68h] [rbp-14C0h]
  _BYTE v13[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v14[1024]; // [rsp+120h] [rbp-1408h] BYREF
  _BYTE v15[4104]; // [rsp+520h] [rbp-1008h] BYREF

  memset_0(v13, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    a2,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    3,
    a7,
    0,
    v10,
    (wil *)v15,
    v11,
    v14,
    v12,
    0,
    (unsigned __int64)v13);
  wil::details::WilFailFast((wil::details *)v13, v9);
}

```

## disassembly

```asm
0x180076320  mov     [rsp+arg_10], rbx
0x180076325  mov     [rsp+arg_18], rsi
0x18007632a  push    rdi
0x18007632b  mov     eax, 1520h
0x180076330  call    _alloca_probe
0x180076335  sub     rsp, rax
0x180076338  mov     rbx, [rsp+1528h+arg_28]
0x180076340  mov     esi, edx
0x180076342  mov     rdi, rcx
0x180076345  xor     edx, edx; Val
0x180076347  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18007634f  mov     r8d, 98h; Size
0x180076355  call    memset_0
0x18007635a  xor     ecx, ecx
0x18007635c  lea     rax, [rsp+1528h+var_14A8]
0x180076364  mov     [rsp+1528h+var_14B0], rax
0x180076369  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180076370  mov     [rsp+1528h+var_14B8], ecx
0x180076374  lea     rax, [rsp+1528h+var_1408]
0x18007637c  mov     [rsp+1528h+var_14C8], rax
0x180076381  xor     r9d, r9d
0x180076384  lea     rax, [rsp+1528h+var_1008]
0x18007638c  mov     edx, esi
0x18007638e  mov     [rsp+1528h+var_14D8], rax
0x180076393  mov     rax, [rsp+1528h+arg_30]
0x18007639b  mov     [rsp+1528h+var_14E8], rcx
0x1800763a0  mov     [rsp+1528h+var_14F0], rax
0x1800763a5  mov     [rsp+1528h+var_14F8], 3
0x1800763ad  mov     [rsp+1528h+var_1500], rbx
0x1800763b2  mov     [rsp+1528h+var_1508], rcx
0x1800763b7  mov     rcx, rdi
0x1800763ba  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x1800763bf  lea     rcx, [rsp+1528h+var_14A8]; this
0x1800763c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
