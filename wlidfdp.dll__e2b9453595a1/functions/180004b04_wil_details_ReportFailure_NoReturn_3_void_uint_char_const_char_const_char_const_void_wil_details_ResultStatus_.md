# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004b04`
- end: `0x180004bb1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800048e4`

## callees

- `0x1800033b4`
- `0x180007480`
- `0x180009348`
- `0x1800105e0`

## string_xrefs

- `0x180004b4d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004b04  mov     [rsp+arg_10], rbx
0x180004b09  mov     [rsp+arg_18], rsi
0x180004b0e  push    rdi
0x180004b0f  mov     eax, 1520h
0x180004b14  call    _alloca_probe
0x180004b19  sub     rsp, rax
0x180004b1c  mov     rbx, [rsp+1528h+arg_28]
0x180004b24  mov     esi, edx
0x180004b26  mov     rdi, rcx
0x180004b29  xor     edx, edx; Val
0x180004b2b  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180004b33  mov     r8d, 98h; Size
0x180004b39  call    memset_0
0x180004b3e  xor     ecx, ecx
0x180004b40  lea     rax, [rsp+1528h+var_14A8]
0x180004b48  mov     [rsp+1528h+var_14B0], rax
0x180004b4d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004b54  mov     [rsp+1528h+var_14B8], ecx
0x180004b58  lea     rax, [rsp+1528h+var_1408]
0x180004b60  mov     [rsp+1528h+var_14C8], rax
0x180004b65  xor     r9d, r9d
0x180004b68  lea     rax, [rsp+1528h+var_1008]
0x180004b70  mov     edx, esi
0x180004b72  mov     [rsp+1528h+var_14D8], rax
0x180004b77  mov     rax, [rsp+1528h+arg_30]
0x180004b7f  mov     [rsp+1528h+var_14E8], rcx
0x180004b84  mov     [rsp+1528h+var_14F0], rax
0x180004b89  mov     [rsp+1528h+var_14F8], 3
0x180004b91  mov     [rsp+1528h+var_1500], rbx
0x180004b96  mov     [rsp+1528h+var_1508], rcx
0x180004b9b  mov     rcx, rdi
0x180004b9e  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180004ba3  lea     rcx, [rsp+1528h+var_14A8]; this
0x180004bab  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
