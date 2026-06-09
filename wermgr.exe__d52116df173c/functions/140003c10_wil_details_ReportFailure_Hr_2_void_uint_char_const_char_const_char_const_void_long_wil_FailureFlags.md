# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140003c10`
- end: `0x140003c6b`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140003aec`
- `0x140004090`
- `0x140007624`
- `0x14000d928`
- `0x14000f984`
- `0x140011a34`

## callees

- `0x140003a98`
- `0x140007a8c`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x140003c10  sub     rsp, 68h
0x140003c14  mov     r10, rcx
0x140003c17  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x140003c1e  mov     [rsp+68h+var_18], ecx
0x140003c22  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003c27  mov     [rsp+68h+var_14], eax
0x140003c2b  mov     rcx, r10
0x140003c2e  xor     eax, eax
0x140003c30  mov     [rsp+68h+var_20], eax
0x140003c34  mov     [rsp+68h+var_30], rax
0x140003c39  mov     [rsp+68h+var_10], eax
0x140003c3d  lea     rax, [rsp+68h+var_18]
0x140003c42  mov     [rsp+68h+var_38], rax
0x140003c47  mov     rax, [rsp+68h+arg_28]
0x140003c4f  mov     [rsp+68h+var_40], rax
0x140003c54  mov     rax, [rsp+68h+arg_20]
0x140003c5c  mov     [rsp+68h+var_48], rax
0x140003c61  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140003c66  add     rsp, 68h
0x140003c6a  retn
```
