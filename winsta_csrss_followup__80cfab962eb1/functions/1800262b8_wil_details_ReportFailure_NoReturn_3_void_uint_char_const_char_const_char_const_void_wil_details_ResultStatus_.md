# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800262b8`
- end: `0x180026365`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026164`

## callees

- `0x18002832c`
- `0x180029250`
- `0x180032be6`
- `0x180032ce0`

## string_xrefs

- `0x180026301`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800262b8  mov     [rsp+arg_10], rbx
0x1800262bd  mov     [rsp+arg_18], rsi
0x1800262c2  push    rdi
0x1800262c3  mov     eax, 1520h
0x1800262c8  call    _alloca_probe
0x1800262cd  sub     rsp, rax
0x1800262d0  mov     rbx, [rsp+1528h+arg_28]
0x1800262d8  mov     esi, edx
0x1800262da  mov     rdi, rcx
0x1800262dd  xor     edx, edx; Val
0x1800262df  lea     rcx, [rsp+1528h+var_14A8]; void *
0x1800262e7  mov     r8d, 98h; Size
0x1800262ed  call    memset_0
0x1800262f2  xor     ecx, ecx
0x1800262f4  lea     rax, [rsp+1528h+var_14A8]
0x1800262fc  mov     [rsp+1528h+var_14B0], rax
0x180026301  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026308  mov     [rsp+1528h+var_14B8], ecx
0x18002630c  lea     rax, [rsp+1528h+var_1408]
0x180026314  mov     [rsp+1528h+var_14C8], rax
0x180026319  xor     r9d, r9d
0x18002631c  lea     rax, [rsp+1528h+var_1008]
0x180026324  mov     edx, esi
0x180026326  mov     [rsp+1528h+var_14D8], rax
0x18002632b  mov     rax, [rsp+1528h+arg_30]
0x180026333  mov     [rsp+1528h+var_14E8], rcx
0x180026338  mov     [rsp+1528h+var_14F0], rax
0x18002633d  mov     [rsp+1528h+var_14F8], 3
0x180026345  mov     [rsp+1528h+var_1500], rbx
0x18002634a  mov     [rsp+1528h+var_1508], rcx
0x18002634f  mov     rcx, rdi
0x180026352  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180026357  lea     rcx, [rsp+1528h+var_14A8]; this
0x18002635f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
