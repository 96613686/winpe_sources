# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b7bc`
- end: `0x18000b869`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5a4`

## callees

- `0x18000d590`
- `0x18000e650`
- `0x18001558e`
- `0x180015650`

## string_xrefs

- `0x18000b805`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000b7bc  mov     [rsp+arg_10], rbx
0x18000b7c1  mov     [rsp+arg_18], rsi
0x18000b7c6  push    rdi
0x18000b7c7  mov     eax, 1520h
0x18000b7cc  call    _alloca_probe
0x18000b7d1  sub     rsp, rax
0x18000b7d4  mov     rbx, [rsp+1528h+arg_28]
0x18000b7dc  mov     esi, edx
0x18000b7de  mov     rdi, rcx
0x18000b7e1  xor     edx, edx; Val
0x18000b7e3  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18000b7eb  mov     r8d, 98h; Size
0x18000b7f1  call    memset_0
0x18000b7f6  xor     ecx, ecx
0x18000b7f8  lea     rax, [rsp+1528h+var_14A8]
0x18000b800  mov     [rsp+1528h+var_14B0], rax
0x18000b805  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b80c  mov     [rsp+1528h+var_14B8], ecx
0x18000b810  lea     rax, [rsp+1528h+var_1408]
0x18000b818  mov     [rsp+1528h+var_14C8], rax
0x18000b81d  xor     r9d, r9d
0x18000b820  lea     rax, [rsp+1528h+var_1008]
0x18000b828  mov     edx, esi
0x18000b82a  mov     [rsp+1528h+var_14D8], rax
0x18000b82f  mov     rax, [rsp+1528h+arg_30]
0x18000b837  mov     [rsp+1528h+var_14E8], rcx
0x18000b83c  mov     [rsp+1528h+var_14F0], rax
0x18000b841  mov     [rsp+1528h+var_14F8], 3
0x18000b849  mov     [rsp+1528h+var_1500], rbx
0x18000b84e  mov     [rsp+1528h+var_1508], rcx
0x18000b853  mov     rcx, rdi
0x18000b856  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000b85b  lea     rcx, [rsp+1528h+var_14A8]; this
0x18000b863  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
