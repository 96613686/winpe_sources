# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180001840`
- end: `0x1800018b8`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `120`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001810`

## callees

- `0x1800018c0`
- `0x1800018d0`

## string_xrefs

- `0x180001868`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // [rsp+50h] [rbp-18h]

  v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(a1, 106, "onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp");
  return v9;
}

```

## disassembly

```asm
0x180001840  mov     [rsp+arg_0], rbx
0x180001845  mov     [rsp+arg_8], rsi
0x18000184a  push    rdi
0x18000184b  sub     rsp, 60h
0x18000184f  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180001856  mov     rsi, rcx
0x180001859  mov     ecx, ebx; this
0x18000185b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180001860  mov     rdx, [rsp+68h+arg_28]
0x180001868  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x18000186f  mov     edi, eax
0x180001871  mov     [rsp+68h+var_18], eax
0x180001875  lea     rax, [rsp+68h+var_18]
0x18000187a  mov     [rsp+68h+var_30], 0
0x180001883  mov     [rsp+68h+var_38], rax
0x180001888  mov     rcx, rsi
0x18000188b  mov     [rsp+68h+var_40], rdx
0x180001890  mov     edx, 6Ah ; 'j'
0x180001895  mov     [rsp+68h+var_14], ebx
0x180001899  mov     [rsp+68h+var_10], 1
0x1800018a1  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800018a6  mov     rbx, [rsp+68h+arg_0]
0x1800018ab  mov     eax, edi
0x1800018ad  mov     rsi, [rsp+68h+arg_8]
0x1800018b2  add     rsp, 60h
0x1800018b6  pop     rdi
0x1800018b7  retn
```
